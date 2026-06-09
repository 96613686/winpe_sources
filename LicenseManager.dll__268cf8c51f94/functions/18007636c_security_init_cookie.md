# __security_init_cookie

- ea: `0x18007636c`
- end: `0x180076421`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180075e10`

## callees

- `0x18007636c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800763bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800763bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800763af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800763af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800763cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800763cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800763a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800763a1`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x18007636c  mov     [rsp-8+arg_10], rbx
0x180076371  push    rbp
0x180076372  mov     rbp, rsp
0x180076375  sub     rsp, 30h
0x180076379  mov     rax, cs:__security_cookie
0x180076380  mov     rbx, 2B992DDFA232h
0x18007638a  cmp     rax, rbx
0x18007638d  jnz     short loc_18007640C
0x18007638f  xor     eax, eax
0x180076391  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180076395  mov     [rbp+var_10], rax
0x180076399  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18007639d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800763a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800763a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800763ab  mov     [rbp+var_10], rax
0x1800763af  call    cs:__imp_GetCurrentThreadId
0x1800763b5  mov     eax, eax
0x1800763b7  xor     [rbp+var_10], rax
0x1800763bb  call    cs:__imp_GetCurrentProcessId
0x1800763c1  mov     eax, eax
0x1800763c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800763c7  xor     [rbp+var_10], rax
0x1800763cb  call    cs:__imp_QueryPerformanceCounter
0x1800763d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800763d4  lea     rcx, [rbp+var_10]
0x1800763d8  shl     rax, 20h
0x1800763dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800763e0  xor     rax, [rbp+var_10]
0x1800763e4  xor     rax, rcx
0x1800763e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800763f1  and     rax, rcx
0x1800763f4  mov     rcx, 2B992DDFA233h
0x1800763fe  cmp     rax, rbx
0x180076401  cmovz   rax, rcx
0x180076405  mov     cs:__security_cookie, rax
0x18007640c  mov     rbx, [rsp+30h+arg_10]
0x180076411  not     rax
0x180076414  mov     cs:__security_cookie_complement, rax
0x18007641b  add     rsp, 30h
0x18007641f  pop     rbp
0x180076420  retn
```
