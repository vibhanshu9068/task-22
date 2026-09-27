# task-22
tasks = []

while True:
    print("\n--- TO-DO LIST ---")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Mark Task as Completed")
    print("4. Delete Task")
    print("5. Exit")

    choice = input("Enter your choice: ")

    if choice == "1":
        task = input("Enter a task: ")
        tasks.append({"task": task, "completed": False})
        print("Task added successfully!")

    elif choice == "2":
        if not tasks:
            print("No tasks available.")
        else:
            print("\nYour Tasks:")
            for i, item in enumerate(tasks, 1):
                status = "✓ Completed" if item["completed"] else "Pending"
                print(f"{i}. {item['task']} - {status}")

    elif choice == "3":
        if not tasks:
            print("No tasks available.")
        else:
            for i, item in enumerate(tasks, 1):
                print(f"{i}. {item['task']}")

            num = int(input("Enter task number to complete: "))

            if 1 <= num <= len(tasks):
                tasks[num - 1]["completed"] = True
                print("Task marked as completed!")
            else:
                print("Invalid task number.")

    elif choice == "4":
        if not tasks:
            print("No tasks available.")
        else:
            for i, item in enumerate(tasks, 1):
                print(f"{i}. {item['task']}")

            num = int(input("Enter task number to delete: "))

            if 1 <= num <= len(tasks):
                deleted = tasks.pop(num - 1)
                print(f"Deleted: {deleted['task']}")
            else:
                print("Invalid task number.")

    elif choice == "5":
        print("Goodbye!")
        break

    else:
        print("Invalid choice. Please try again.")
