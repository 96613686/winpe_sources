# __security_init_cookie

- ea: `0x180003294`
- end: `0x180003371`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800028b0`

## callees

- `0x180003294`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800032e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800032db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800032db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000331e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000331e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800032cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800032cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800032f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003303`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800032f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003303`

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
0x180003294  mov     [rsp-8+arg_18], rbx
0x180003299  push    rbp
0x18000329a  mov     rbp, rsp
0x18000329d  sub     rsp, 20h
0x1800032a1  xor     eax, eax
0x1800032a3  mov     rbx, 2B992DDFA232h
0x1800032ad  mov     [rbp+arg_0], rax
0x1800032b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800032b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800032b9  mov     rax, cs:__security_cookie
0x1800032c0  cmp     rax, rbx
0x1800032c3  jnz     loc_18000335C
0x1800032c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800032cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800032d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800032d7  mov     [rbp+arg_0], rax
0x1800032db  call    cs:__imp_GetCurrentProcessId
0x1800032e1  mov     eax, eax
0x1800032e3  xor     [rbp+arg_0], rax
0x1800032e7  call    cs:__imp_GetCurrentThreadId
0x1800032ed  mov     eax, eax
0x1800032ef  xor     [rbp+arg_0], rax
0x1800032f3  call    cs:__imp_GetTickCount
0x1800032f9  mov     eax, eax
0x1800032fb  shl     rax, 18h
0x1800032ff  xor     [rbp+arg_0], rax
0x180003303  call    cs:__imp_GetTickCount
0x180003309  mov     eax, eax
0x18000330b  lea     rcx, [rbp+arg_0]
0x18000330f  xor     rax, [rbp+arg_0]
0x180003313  xor     rax, rcx
0x180003316  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000331a  mov     [rbp+arg_0], rax
0x18000331e  call    cs:__imp_QueryPerformanceCounter
0x180003324  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003327  mov     rcx, 0FFFFFFFFFFFFh
0x180003331  shl     rax, 20h
0x180003335  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003339  xor     rax, [rbp+arg_0]
0x18000333d  and     rax, rcx
0x180003340  mov     rcx, rax
0x180003343  cmp     rax, rbx
0x180003346  jnz     short loc_180003355
0x180003348  mov     rax, 2B992DDFA233h
0x180003352  mov     rcx, rax
0x180003355  mov     cs:__security_cookie, rcx
0x18000335c  mov     rbx, [rsp+20h+arg_18]
0x180003361  not     rax
0x180003364  mov     cs:__security_cookie_complement, rax
0x18000336b  add     rsp, 20h
0x18000336f  pop     rbp
0x180003370  retn
```
