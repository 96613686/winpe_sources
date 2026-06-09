# __get_entropy

- ea: `0x180002820`
- end: `0x18000288e`
- name: `__get_entropy`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000285f`
- `KERNEL32!QueryPerformanceCounter` at `0x18000285f`
- `KERNEL32!GetCurrentProcessId` at `0x18000284f`
- `KERNEL32!GetCurrentProcessId` at `0x18000284f`
- `KERNEL32!GetCurrentThreadId` at `0x180002843`
- `KERNEL32!GetCurrentThreadId` at `0x180002843`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002835`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002835`

## pseudocode

```c
unsigned __int64 _get_entropy()
{
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v1 = SystemTimeAsFileTime;
  v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
  v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
  QueryPerformanceCounter(&PerformanceCount);
  return ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
}

```

## disassembly

```asm
0x180002820  push    rbp
0x180002822  mov     rbp, rsp
0x180002825  sub     rsp, 20h
0x180002829  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000282d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002835  call    cs:__imp_GetSystemTimeAsFileTime
0x18000283b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000283f  mov     [rbp+arg_0], rax
0x180002843  call    cs:__imp_GetCurrentThreadId
0x180002849  mov     eax, eax
0x18000284b  xor     [rbp+arg_0], rax
0x18000284f  call    cs:__imp_GetCurrentProcessId
0x180002855  mov     eax, eax
0x180002857  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000285b  xor     [rbp+arg_0], rax
0x18000285f  call    cs:__imp_QueryPerformanceCounter
0x180002865  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002868  lea     rcx, [rbp+arg_0]
0x18000286c  shl     rax, 20h
0x180002870  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002874  xor     rax, [rbp+arg_0]
0x180002878  xor     rax, rcx
0x18000287b  mov     rcx, 0FFFFFFFFFFFFh
0x180002885  and     rax, rcx
0x180002888  add     rsp, 20h
0x18000288c  pop     rbp
0x18000288d  retn
```
