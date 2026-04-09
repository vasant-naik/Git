# Git
Git



class Cloudlet:
    def __init__(self, id, length):
        self.id = id
        self.length = length  # in MI (Million Instructions)
        self.start_time = 0
        self.finish_time = 0

def fcfs_schedule(cloudlets, mips=1000):
    """FCFS: tasks execute in submission order, one at a time."""
    current_time = 0
    print(f"{'Cloudlet ID':<15}{'Start Time':<15}{'Finish Time':<15}{'Exec Time'}")
    print("-" * 55)
    for c in cloudlets:
        c.start_time = current_time
        exec_time = c.length / mips
        c.finish_time = current_time + exec_time
        current_time = c.finish_time
        print(f"{c.id:<15}{c.start_time:<15.1f}{c.finish_time:<15.1f}{exec_time:.1f}")

# Define tasks (ID, length in MI)
cloudlets = [
    Cloudlet(0, 40000),   # Long task
    Cloudlet(1, 10000),   # Short task
    Cloudlet(2, 25000),   # Medium task
]

print("=== FCFS Scheduling Simulation ===")
print(f"VM Speed: 1000 MIPS\n")
fcfs_schedule(cloudlets)
