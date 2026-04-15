#1.реализация

def proverka_nalich(n,a):
    for i in n:
        if i==a:
            return True
    else:
        return False


#2.функция генерации данных
def generate_array(n):
    arr = []
    for i in range(n):
        arr.append(random.randint(0, 10000))
    return arr


		
#3.функция измерения времени
def measure_time(func, data,a):
    start = time.perf_counter()
    func(data,a)
    end = time.perf_counter()
    return end - start


		
#4.реализация
import random
import time
def proverka_nalich(n,a):
    for i in n:
        if i==a:
            return True
    else:
        return False
def generate_array(n):
    arr = []
    for i in range(n):
        arr.append(random.randint(0, 10000))
    return arr

def measure_time(func, data,a):
    start = time.perf_counter()
    func(data,a)
    end = time.perf_counter()
    return end - start
print("1")
if __name__ == '__main__':
    sizes = [100, 1000, 5000, 10000]
    for n in sizes:
        a=random.randint(1,10)
        arr = generate_array(n)
        t = measure_time(proverka_nalich, arr,a)
        print(n, t*1000, "ms",proverka_nalich(arr,n))
