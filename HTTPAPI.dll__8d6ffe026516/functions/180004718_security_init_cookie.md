# __security_init_cookie

- ea: `0x180004718`
- end: `0x1800047f5`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800045a0`

## callees

- `0x180004718`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000475f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000475f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000476b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000476b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800047a2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800047a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004751`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004751`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004777`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004787`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004777`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004787`

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
0x180004718  mov     [rsp-8+arg_18], rbx
0x18000471d  push    rbp
0x18000471e  mov     rbp, rsp
0x180004721  sub     rsp, 20h
0x180004725  xor     eax, eax
0x180004727  mov     rbx, 2B992DDFA232h
0x180004731  mov     [rbp+arg_0], rax
0x180004735  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004739  mov     qword ptr [rbp+PerformanceCount], rax
0x18000473d  mov     rax, cs:__security_cookie
0x180004744  cmp     rax, rbx
0x180004747  jnz     loc_1800047E0
0x18000474d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004751  call    cs:__imp_GetSystemTimeAsFileTime
0x180004757  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000475b  mov     [rbp+arg_0], rax
0x18000475f  call    cs:__imp_GetCurrentProcessId
0x180004765  mov     eax, eax
0x180004767  xor     [rbp+arg_0], rax
0x18000476b  call    cs:__imp_GetCurrentThreadId
0x180004771  mov     eax, eax
0x180004773  xor     [rbp+arg_0], rax
0x180004777  call    cs:__imp_GetTickCount
0x18000477d  mov     eax, eax
0x18000477f  shl     rax, 18h
0x180004783  xor     [rbp+arg_0], rax
0x180004787  call    cs:__imp_GetTickCount
0x18000478d  mov     eax, eax
0x18000478f  lea     rcx, [rbp+arg_0]
0x180004793  xor     rax, [rbp+arg_0]
0x180004797  xor     rax, rcx
0x18000479a  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000479e  mov     [rbp+arg_0], rax
0x1800047a2  call    cs:__imp_QueryPerformanceCounter
0x1800047a8  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800047ab  mov     rcx, 0FFFFFFFFFFFFh
0x1800047b5  shl     rax, 20h
0x1800047b9  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800047bd  xor     rax, [rbp+arg_0]
0x1800047c1  and     rax, rcx
0x1800047c4  mov     rcx, rax
0x1800047c7  cmp     rax, rbx
0x1800047ca  jnz     short loc_1800047D9
0x1800047cc  mov     rax, 2B992DDFA233h
0x1800047d6  mov     rcx, rax
0x1800047d9  mov     cs:__security_cookie, rcx
0x1800047e0  mov     rbx, [rsp+20h+arg_18]
0x1800047e5  not     rax
0x1800047e8  mov     cs:__security_cookie_complement, rax
0x1800047ef  add     rsp, 20h
0x1800047f3  pop     rbp
0x1800047f4  retn
```
