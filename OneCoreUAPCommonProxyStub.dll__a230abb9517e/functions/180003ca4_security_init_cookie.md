# __security_init_cookie

- ea: `0x180003ca4`
- end: `0x180003d59`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003c30`

## callees

- `0x180003ca4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003d03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003cf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003cf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ce7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ce7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003cd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003cd9`

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
0x180003ca4  mov     [rsp-8+arg_10], rbx
0x180003ca9  push    rbp
0x180003caa  mov     rbp, rsp
0x180003cad  sub     rsp, 30h
0x180003cb1  mov     rax, cs:__security_cookie
0x180003cb8  mov     rbx, 2B992DDFA232h
0x180003cc2  cmp     rax, rbx
0x180003cc5  jnz     short loc_180003D44
0x180003cc7  xor     eax, eax
0x180003cc9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003ccd  mov     [rbp+var_10], rax
0x180003cd1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003cd5  mov     qword ptr [rbp+PerformanceCount], rax
0x180003cd9  call    cs:__imp_GetSystemTimeAsFileTime
0x180003cdf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003ce3  mov     [rbp+var_10], rax
0x180003ce7  call    cs:__imp_GetCurrentThreadId
0x180003ced  mov     eax, eax
0x180003cef  xor     [rbp+var_10], rax
0x180003cf3  call    cs:__imp_GetCurrentProcessId
0x180003cf9  mov     eax, eax
0x180003cfb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003cff  xor     [rbp+var_10], rax
0x180003d03  call    cs:__imp_QueryPerformanceCounter
0x180003d09  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003d0c  lea     rcx, [rbp+var_10]
0x180003d10  shl     rax, 20h
0x180003d14  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003d18  xor     rax, [rbp+var_10]
0x180003d1c  xor     rax, rcx
0x180003d1f  mov     rcx, 0FFFFFFFFFFFFh
0x180003d29  and     rax, rcx
0x180003d2c  mov     rcx, 2B992DDFA233h
0x180003d36  cmp     rax, rbx
0x180003d39  cmovz   rax, rcx
0x180003d3d  mov     cs:__security_cookie, rax
0x180003d44  mov     rbx, [rsp+30h+arg_10]
0x180003d49  not     rax
0x180003d4c  mov     cs:__security_cookie_complement, rax
0x180003d53  add     rsp, 30h
0x180003d57  pop     rbp
0x180003d58  retn
```
