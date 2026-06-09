# __security_init_cookie

- ea: `0x180003214`
- end: `0x1800032f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a30`

## callees

- `0x180003214`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000325b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000325b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003267`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003267`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000329e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000329e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000324d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000324d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003273`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003283`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003273`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003283`

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
0x180003214  mov     [rsp-8+arg_18], rbx
0x180003219  push    rbp
0x18000321a  mov     rbp, rsp
0x18000321d  sub     rsp, 20h
0x180003221  xor     eax, eax
0x180003223  mov     rbx, 2B992DDFA232h
0x18000322d  mov     [rbp+arg_0], rax
0x180003231  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003235  mov     qword ptr [rbp+PerformanceCount], rax
0x180003239  mov     rax, cs:__security_cookie
0x180003240  cmp     rax, rbx
0x180003243  jnz     loc_1800032DC
0x180003249  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000324d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003253  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003257  mov     [rbp+arg_0], rax
0x18000325b  call    cs:__imp_GetCurrentProcessId
0x180003261  mov     eax, eax
0x180003263  xor     [rbp+arg_0], rax
0x180003267  call    cs:__imp_GetCurrentThreadId
0x18000326d  mov     eax, eax
0x18000326f  xor     [rbp+arg_0], rax
0x180003273  call    cs:__imp_GetTickCount
0x180003279  mov     eax, eax
0x18000327b  shl     rax, 18h
0x18000327f  xor     [rbp+arg_0], rax
0x180003283  call    cs:__imp_GetTickCount
0x180003289  mov     eax, eax
0x18000328b  lea     rcx, [rbp+arg_0]
0x18000328f  xor     rax, [rbp+arg_0]
0x180003293  xor     rax, rcx
0x180003296  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000329a  mov     [rbp+arg_0], rax
0x18000329e  call    cs:__imp_QueryPerformanceCounter
0x1800032a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800032a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800032b1  shl     rax, 20h
0x1800032b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800032b9  xor     rax, [rbp+arg_0]
0x1800032bd  and     rax, rcx
0x1800032c0  mov     rcx, rax
0x1800032c3  cmp     rax, rbx
0x1800032c6  jnz     short loc_1800032D5
0x1800032c8  mov     rax, 2B992DDFA233h
0x1800032d2  mov     rcx, rax
0x1800032d5  mov     cs:__security_cookie, rcx
0x1800032dc  mov     rbx, [rsp+20h+arg_18]
0x1800032e1  not     rax
0x1800032e4  mov     cs:__security_cookie_complement, rax
0x1800032eb  add     rsp, 20h
0x1800032ef  pop     rbp
0x1800032f0  retn
```
