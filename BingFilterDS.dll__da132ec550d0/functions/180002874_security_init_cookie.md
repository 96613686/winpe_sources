# __security_init_cookie

- ea: `0x180002874`
- end: `0x180002951`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002330`

## callees

- `0x180002874`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800028bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800028bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800028fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800028fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800028ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800028ad`

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
0x180002874  mov     [rsp-8+arg_18], rbx
0x180002879  push    rbp
0x18000287a  mov     rbp, rsp
0x18000287d  sub     rsp, 20h
0x180002881  xor     eax, eax
0x180002883  mov     rbx, 2B992DDFA232h
0x18000288d  mov     [rbp+arg_0], rax
0x180002891  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002895  mov     qword ptr [rbp+PerformanceCount], rax
0x180002899  mov     rax, cs:__security_cookie
0x1800028a0  cmp     rax, rbx
0x1800028a3  jnz     loc_18000293C
0x1800028a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800028ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800028b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800028b7  mov     [rbp+arg_0], rax
0x1800028bb  call    cs:__imp_GetCurrentProcessId
0x1800028c1  mov     eax, eax
0x1800028c3  xor     [rbp+arg_0], rax
0x1800028c7  call    cs:__imp_GetCurrentThreadId
0x1800028cd  mov     eax, eax
0x1800028cf  xor     [rbp+arg_0], rax
0x1800028d3  call    cs:__imp_GetTickCount
0x1800028d9  mov     eax, eax
0x1800028db  shl     rax, 18h
0x1800028df  xor     [rbp+arg_0], rax
0x1800028e3  call    cs:__imp_GetTickCount
0x1800028e9  mov     eax, eax
0x1800028eb  lea     rcx, [rbp+arg_0]
0x1800028ef  xor     rax, [rbp+arg_0]
0x1800028f3  xor     rax, rcx
0x1800028f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800028fa  mov     [rbp+arg_0], rax
0x1800028fe  call    cs:__imp_QueryPerformanceCounter
0x180002904  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002907  mov     rcx, 0FFFFFFFFFFFFh
0x180002911  shl     rax, 20h
0x180002915  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002919  xor     rax, [rbp+arg_0]
0x18000291d  and     rax, rcx
0x180002920  mov     rcx, rax
0x180002923  cmp     rax, rbx
0x180002926  jnz     short loc_180002935
0x180002928  mov     rax, 2B992DDFA233h
0x180002932  mov     rcx, rax
0x180002935  mov     cs:__security_cookie, rcx
0x18000293c  mov     rbx, [rsp+20h+arg_18]
0x180002941  not     rax
0x180002944  mov     cs:__security_cookie_complement, rax
0x18000294b  add     rsp, 20h
0x18000294f  pop     rbp
0x180002950  retn
```
