# __security_init_cookie

- ea: `0x180004110`
- end: `0x1800041c5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003c20`

## callees

- `0x180004110`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004153`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004153`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000415f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000415f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000416f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000416f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004145`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004145`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180004110  mov     [rsp-8+arg_10], rbx
0x180004115  push    rbp
0x180004116  mov     rbp, rsp
0x180004119  sub     rsp, 30h
0x18000411d  mov     rax, cs:__security_cookie
0x180004124  mov     rbx, 2B992DDFA232h
0x18000412e  cmp     rax, rbx
0x180004131  jnz     short loc_1800041B0
0x180004133  xor     eax, eax
0x180004135  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004139  mov     [rbp+var_10], rax
0x18000413d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004141  mov     qword ptr [rbp+PerformanceCount], rax
0x180004145  call    cs:__imp_GetSystemTimeAsFileTime
0x18000414b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000414f  mov     [rbp+var_10], rax
0x180004153  call    cs:__imp_GetCurrentThreadId
0x180004159  mov     eax, eax
0x18000415b  xor     [rbp+var_10], rax
0x18000415f  call    cs:__imp_GetCurrentProcessId
0x180004165  mov     eax, eax
0x180004167  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000416b  xor     [rbp+var_10], rax
0x18000416f  call    cs:__imp_QueryPerformanceCounter
0x180004175  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004178  lea     rcx, [rbp+var_10]
0x18000417c  shl     rax, 20h
0x180004180  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004184  xor     rax, [rbp+var_10]
0x180004188  xor     rax, rcx
0x18000418b  mov     rcx, 0FFFFFFFFFFFFh
0x180004195  and     rax, rcx
0x180004198  mov     rcx, 2B992DDFA233h
0x1800041a2  cmp     rax, rbx
0x1800041a5  cmovz   rax, rcx
0x1800041a9  mov     cs:__security_cookie, rax
0x1800041b0  mov     rbx, [rsp+30h+arg_10]
0x1800041b5  not     rax
0x1800041b8  mov     cs:__security_cookie_complement, rax
0x1800041bf  add     rsp, 30h
0x1800041c3  pop     rbp
0x1800041c4  retn
```
