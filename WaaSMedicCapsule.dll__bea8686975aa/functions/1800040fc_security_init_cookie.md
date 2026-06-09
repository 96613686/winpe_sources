# __security_init_cookie

- ea: `0x1800040fc`
- end: `0x1800041b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003b60`

## callees

- `0x1800040fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000414b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000414b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000413f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000413f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000415b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000415b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004131`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004131`

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
0x1800040fc  mov     [rsp-8+arg_10], rbx
0x180004101  push    rbp
0x180004102  mov     rbp, rsp
0x180004105  sub     rsp, 30h
0x180004109  mov     rax, cs:__security_cookie
0x180004110  mov     rbx, 2B992DDFA232h
0x18000411a  cmp     rax, rbx
0x18000411d  jnz     short loc_18000419C
0x18000411f  xor     eax, eax
0x180004121  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004125  mov     [rbp+var_10], rax
0x180004129  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000412d  mov     qword ptr [rbp+PerformanceCount], rax
0x180004131  call    cs:__imp_GetSystemTimeAsFileTime
0x180004137  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000413b  mov     [rbp+var_10], rax
0x18000413f  call    cs:__imp_GetCurrentThreadId
0x180004145  mov     eax, eax
0x180004147  xor     [rbp+var_10], rax
0x18000414b  call    cs:__imp_GetCurrentProcessId
0x180004151  mov     eax, eax
0x180004153  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004157  xor     [rbp+var_10], rax
0x18000415b  call    cs:__imp_QueryPerformanceCounter
0x180004161  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004164  lea     rcx, [rbp+var_10]
0x180004168  shl     rax, 20h
0x18000416c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004170  xor     rax, [rbp+var_10]
0x180004174  xor     rax, rcx
0x180004177  mov     rcx, 0FFFFFFFFFFFFh
0x180004181  and     rax, rcx
0x180004184  mov     rcx, 2B992DDFA233h
0x18000418e  cmp     rax, rbx
0x180004191  cmovz   rax, rcx
0x180004195  mov     cs:__security_cookie, rax
0x18000419c  mov     rbx, [rsp+30h+arg_10]
0x1800041a1  not     rax
0x1800041a4  mov     cs:__security_cookie_complement, rax
0x1800041ab  add     rsp, 30h
0x1800041af  pop     rbp
0x1800041b0  retn
```
