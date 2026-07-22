# resource-management
Takes input from files containing "departments" and items that department desires, and uses a global budget to buy items for each department.

This project was created in cooperation with a partner, Jany Hernandez. Unfortunately, I no longer possess the external notes that were taken of each other's contributions.

The Item and Department classes define the basic objects the driver class resourceManagement and our priority queue work with.
When the program runs, resourceManagement searches for predefined text files that each contain one department, its desired items, and the price of each desired item. If it finds each text file it was instructed to look for, it hands them to PriorityQueue to be contained.
Until the predefined global budget is reduced to 0, resourceManagement then iteratively examines the first item on each department's desired list and compares it to the current global budget. If the item is within budget, the item is added to a "purchased" list, global budget is reduced by the item's price, and that department's budget variable increases to represent the cumulative money spent on that department. If not, the item is instead added to a "denied" list, and both the global budget and the per-department budget are unmodified.
In either case, the item is removed from the desired list, and the department is removed from the priority queue and re-added, using the aforementioned per-department budget to sort- departments with the least money spent on them are the soonest to be reexamined.
If a department has no more desired items but global budget is still positive, the department is given a "scholarship" item of either 1000 or the remaining budget, whichever is smaller.
Once the budget reaches 0, resourceManagement iteratively retrieves a report from each department in the queue detailing what items were purchased for what price, what items were denied, the total budget spent on that department, and the percentage of the global budget it received.
resourceManagement also outputs a list of each purchase that was made, in order.
