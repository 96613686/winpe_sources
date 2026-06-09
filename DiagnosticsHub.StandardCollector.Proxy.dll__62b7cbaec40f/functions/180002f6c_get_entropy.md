# __get_entropy

- ea: `0x180002f6c`
- end: `0x180002fda`
- name: `__get_entropy`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180002fab`
- `KERNEL32!QueryPerformanceCounter` at `0x180002fab`
- `KERNEL32!GetCurrentProcessId` at `0x180002f9b`
- `KERNEL32!GetCurrentProcessId` at `0x180002f9b`
- `KERNEL32!GetCurrentThreadId` at `0x180002f8f`
- `KERNEL32!GetCurrentThreadId` at `0x180002f8f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002f81`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002f81`

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
0x180002f6c  push    rbp
0x180002f6e  mov     rbp, rsp
0x180002f71  sub     rsp, 20h
0x180002f75  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002f79  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002f81  call    cs:__imp_GetSystemTimeAsFileTime
0x180002f87  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002f8b  mov     [rbp+arg_0], rax
0x180002f8f  call    cs:__imp_GetCurrentThreadId
0x180002f95  mov     eax, eax
0x180002f97  xor     [rbp+arg_0], rax
0x180002f9b  call    cs:__imp_GetCurrentProcessId
0x180002fa1  mov     eax, eax
0x180002fa3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002fa7  xor     [rbp+arg_0], rax
0x180002fab  call    cs:__imp_QueryPerformanceCounter
0x180002fb1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002fb4  lea     rcx, [rbp+arg_0]
0x180002fb8  shl     rax, 20h
0x180002fbc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002fc0  xor     rax, [rbp+arg_0]
0x180002fc4  xor     rax, rcx
0x180002fc7  mov     rcx, 0FFFFFFFFFFFFh
0x180002fd1  and     rax, rcx
0x180002fd4  add     rsp, 20h
0x180002fd8  pop     rbp
0x180002fd9  retn
```
