# __security_init_cookie

- ea: `0x180003d5c`
- end: `0x180003e11`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003930`

## callees

- `0x180003d5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003dab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003dab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003dbb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003dbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003d91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003d91`

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
0x180003d5c  mov     [rsp-8+arg_10], rbx
0x180003d61  push    rbp
0x180003d62  mov     rbp, rsp
0x180003d65  sub     rsp, 30h
0x180003d69  mov     rax, cs:__security_cookie
0x180003d70  mov     rbx, 2B992DDFA232h
0x180003d7a  cmp     rax, rbx
0x180003d7d  jnz     short loc_180003DFC
0x180003d7f  xor     eax, eax
0x180003d81  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003d85  mov     [rbp+var_10], rax
0x180003d89  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003d8d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003d91  call    cs:__imp_GetSystemTimeAsFileTime
0x180003d97  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003d9b  mov     [rbp+var_10], rax
0x180003d9f  call    cs:__imp_GetCurrentThreadId
0x180003da5  mov     eax, eax
0x180003da7  xor     [rbp+var_10], rax
0x180003dab  call    cs:__imp_GetCurrentProcessId
0x180003db1  mov     eax, eax
0x180003db3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003db7  xor     [rbp+var_10], rax
0x180003dbb  call    cs:__imp_QueryPerformanceCounter
0x180003dc1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003dc4  lea     rcx, [rbp+var_10]
0x180003dc8  shl     rax, 20h
0x180003dcc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003dd0  xor     rax, [rbp+var_10]
0x180003dd4  xor     rax, rcx
0x180003dd7  mov     rcx, 0FFFFFFFFFFFFh
0x180003de1  and     rax, rcx
0x180003de4  mov     rcx, 2B992DDFA233h
0x180003dee  cmp     rax, rbx
0x180003df1  cmovz   rax, rcx
0x180003df5  mov     cs:__security_cookie, rax
0x180003dfc  mov     rbx, [rsp+30h+arg_10]
0x180003e01  not     rax
0x180003e04  mov     cs:__security_cookie_complement, rax
0x180003e0b  add     rsp, 30h
0x180003e0f  pop     rbp
0x180003e10  retn
```
