# __security_init_cookie

- ea: `0x180004238`
- end: `0x1800042ed`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a10`

## callees

- `0x180004238`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000427b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000427b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004297`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004297`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000426d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000426d`

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
0x180004238  mov     [rsp-8+arg_10], rbx
0x18000423d  push    rbp
0x18000423e  mov     rbp, rsp
0x180004241  sub     rsp, 30h
0x180004245  mov     rax, cs:__security_cookie
0x18000424c  mov     rbx, 2B992DDFA232h
0x180004256  cmp     rax, rbx
0x180004259  jnz     short loc_1800042D8
0x18000425b  xor     eax, eax
0x18000425d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004261  mov     [rbp+var_10], rax
0x180004265  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004269  mov     qword ptr [rbp+PerformanceCount], rax
0x18000426d  call    cs:__imp_GetSystemTimeAsFileTime
0x180004273  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004277  mov     [rbp+var_10], rax
0x18000427b  call    cs:__imp_GetCurrentThreadId
0x180004281  mov     eax, eax
0x180004283  xor     [rbp+var_10], rax
0x180004287  call    cs:__imp_GetCurrentProcessId
0x18000428d  mov     eax, eax
0x18000428f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004293  xor     [rbp+var_10], rax
0x180004297  call    cs:__imp_QueryPerformanceCounter
0x18000429d  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800042a0  lea     rcx, [rbp+var_10]
0x1800042a4  shl     rax, 20h
0x1800042a8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800042ac  xor     rax, [rbp+var_10]
0x1800042b0  xor     rax, rcx
0x1800042b3  mov     rcx, 0FFFFFFFFFFFFh
0x1800042bd  and     rax, rcx
0x1800042c0  mov     rcx, 2B992DDFA233h
0x1800042ca  cmp     rax, rbx
0x1800042cd  cmovz   rax, rcx
0x1800042d1  mov     cs:__security_cookie, rax
0x1800042d8  mov     rbx, [rsp+30h+arg_10]
0x1800042dd  not     rax
0x1800042e0  mov     cs:__security_cookie_complement, rax
0x1800042e7  add     rsp, 30h
0x1800042eb  pop     rbp
0x1800042ec  retn
```
