import time
start_time = time.time()
t = int(input())
for _ in range(t):
    m, k, n = map(int, input().split())
    masses = [float(i) for i in input().split()]
    adducts = [float(i) for i in input().split()]
    signals = [float(i) for i in input().split()]
    for i, num in enumerate(adducts):
        adducts[i] = (num, i+1)
    adducts.sort()
    for i, num in enumerate(masses):
        masses[i] = (num, i+1)
    masses.sort()
    ans = []
    for s in signals:
        mindiff = float('inf')
        best = None
        found = False
        j = k-1
        for i in range(m):
            while True:
                total = masses[i][0] + adducts[j][0]
                diff = round(abs(total - s), 6)
                if diff < mindiff:
                    best = (masses[i][1], adducts[j][1])
                    mindiff = diff
                if total > s:
                    j -= 1
                    if j < 0:
                        break
                else:
                    break
            if j < 0:
                break
            if mindiff == 0:
                break
        ans.append(best)
    for res in ans:
        print(*res)
print('My program took', time.time() - start_time, 'to run')
