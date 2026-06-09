# __security_init_cookie

- ea: `0x180002608`
- end: `0x1800026bd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002120`

## callees

- `0x180002608`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000264b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000264b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002657`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002657`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000263d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000263d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002667`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002667`

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
0x180002608  mov     [rsp-8+arg_10], rbx
0x18000260d  push    rbp
0x18000260e  mov     rbp, rsp
0x180002611  sub     rsp, 30h
0x180002615  mov     rax, cs:__security_cookie
0x18000261c  mov     rbx, 2B992DDFA232h
0x180002626  cmp     rax, rbx
0x180002629  jnz     short loc_1800026A8
0x18000262b  xor     eax, eax
0x18000262d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002631  mov     [rbp+var_10], rax
0x180002635  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002639  mov     qword ptr [rbp+PerformanceCount], rax
0x18000263d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002643  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002647  mov     [rbp+var_10], rax
0x18000264b  call    cs:__imp_GetCurrentThreadId
0x180002651  mov     eax, eax
0x180002653  xor     [rbp+var_10], rax
0x180002657  call    cs:__imp_GetCurrentProcessId
0x18000265d  mov     eax, eax
0x18000265f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002663  xor     [rbp+var_10], rax
0x180002667  call    cs:__imp_QueryPerformanceCounter
0x18000266d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002670  lea     rcx, [rbp+var_10]
0x180002674  shl     rax, 20h
0x180002678  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000267c  xor     rax, [rbp+var_10]
0x180002680  xor     rax, rcx
0x180002683  mov     rcx, 0FFFFFFFFFFFFh
0x18000268d  and     rax, rcx
0x180002690  mov     rcx, 2B992DDFA233h
0x18000269a  cmp     rax, rbx
0x18000269d  cmovz   rax, rcx
0x1800026a1  mov     cs:__security_cookie, rax
0x1800026a8  mov     rbx, [rsp+30h+arg_10]
0x1800026ad  not     rax
0x1800026b0  mov     cs:__security_cookie_complement, rax
0x1800026b7  add     rsp, 30h
0x1800026bb  pop     rbp
0x1800026bc  retn
```
