# __security_init_cookie

- ea: `0x180002540`
- end: `0x1800025f5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800020f0`

## callees

- `0x180002540`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000258f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000258f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002583`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000259f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000259f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002575`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002575`

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
0x180002540  mov     [rsp-8+arg_10], rbx
0x180002545  push    rbp
0x180002546  mov     rbp, rsp
0x180002549  sub     rsp, 30h
0x18000254d  mov     rax, cs:__security_cookie
0x180002554  mov     rbx, 2B992DDFA232h
0x18000255e  cmp     rax, rbx
0x180002561  jnz     short loc_1800025E0
0x180002563  xor     eax, eax
0x180002565  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002569  mov     [rbp+var_10], rax
0x18000256d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002571  mov     qword ptr [rbp+PerformanceCount], rax
0x180002575  call    cs:__imp_GetSystemTimeAsFileTime
0x18000257b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000257f  mov     [rbp+var_10], rax
0x180002583  call    cs:__imp_GetCurrentThreadId
0x180002589  mov     eax, eax
0x18000258b  xor     [rbp+var_10], rax
0x18000258f  call    cs:__imp_GetCurrentProcessId
0x180002595  mov     eax, eax
0x180002597  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000259b  xor     [rbp+var_10], rax
0x18000259f  call    cs:__imp_QueryPerformanceCounter
0x1800025a5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800025a8  lea     rcx, [rbp+var_10]
0x1800025ac  shl     rax, 20h
0x1800025b0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800025b4  xor     rax, [rbp+var_10]
0x1800025b8  xor     rax, rcx
0x1800025bb  mov     rcx, 0FFFFFFFFFFFFh
0x1800025c5  and     rax, rcx
0x1800025c8  mov     rcx, 2B992DDFA233h
0x1800025d2  cmp     rax, rbx
0x1800025d5  cmovz   rax, rcx
0x1800025d9  mov     cs:__security_cookie, rax
0x1800025e0  mov     rbx, [rsp+30h+arg_10]
0x1800025e5  not     rax
0x1800025e8  mov     cs:__security_cookie_complement, rax
0x1800025ef  add     rsp, 30h
0x1800025f3  pop     rbp
0x1800025f4  retn
```
