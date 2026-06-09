# __security_init_cookie

- ea: `0x140002644`
- end: `0x140002721`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002130`

## callees

- `0x140002644`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002697`
- `KERNEL32!GetCurrentThreadId` at `0x140002697`
- `KERNEL32!GetCurrentProcessId` at `0x14000268b`
- `KERNEL32!GetCurrentProcessId` at `0x14000268b`
- `KERNEL32!GetTickCount` at `0x1400026a3`
- `KERNEL32!GetTickCount` at `0x1400026b3`
- `KERNEL32!GetTickCount` at `0x1400026a3`
- `KERNEL32!GetTickCount` at `0x1400026b3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000267d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000267d`
- `KERNEL32!QueryPerformanceCounter` at `0x1400026ce`
- `KERNEL32!QueryPerformanceCounter` at `0x1400026ce`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x140002644  mov     [rsp-8+arg_18], rbx
0x140002649  push    rbp
0x14000264a  mov     rbp, rsp
0x14000264d  sub     rsp, 20h
0x140002651  xor     eax, eax
0x140002653  mov     rbx, 2B992DDFA232h
0x14000265d  mov     [rbp+arg_0], rax
0x140002661  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002665  mov     qword ptr [rbp+PerformanceCount], rax
0x140002669  mov     rax, cs:__security_cookie
0x140002670  cmp     rax, rbx
0x140002673  jnz     loc_14000270C
0x140002679  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000267d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002683  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002687  mov     [rbp+arg_0], rax
0x14000268b  call    cs:__imp_GetCurrentProcessId
0x140002691  mov     eax, eax
0x140002693  xor     [rbp+arg_0], rax
0x140002697  call    cs:__imp_GetCurrentThreadId
0x14000269d  mov     eax, eax
0x14000269f  xor     [rbp+arg_0], rax
0x1400026a3  call    cs:__imp_GetTickCount
0x1400026a9  mov     eax, eax
0x1400026ab  shl     rax, 18h
0x1400026af  xor     [rbp+arg_0], rax
0x1400026b3  call    cs:__imp_GetTickCount
0x1400026b9  mov     eax, eax
0x1400026bb  lea     rcx, [rbp+arg_0]
0x1400026bf  xor     rax, [rbp+arg_0]
0x1400026c3  xor     rax, rcx
0x1400026c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400026ca  mov     [rbp+arg_0], rax
0x1400026ce  call    cs:__imp_QueryPerformanceCounter
0x1400026d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400026d7  mov     rcx, 0FFFFFFFFFFFFh
0x1400026e1  shl     rax, 20h
0x1400026e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400026e9  xor     rax, [rbp+arg_0]
0x1400026ed  and     rax, rcx
0x1400026f0  mov     rcx, rax
0x1400026f3  cmp     rax, rbx
0x1400026f6  jnz     short loc_140002705
0x1400026f8  mov     rax, 2B992DDFA233h
0x140002702  mov     rcx, rax
0x140002705  mov     cs:__security_cookie, rcx
0x14000270c  mov     rbx, [rsp+20h+arg_18]
0x140002711  not     rax
0x140002714  mov     cs:__security_cookie_complement, rax
0x14000271b  add     rsp, 20h
0x14000271f  pop     rbp
0x140002720  retn
```
