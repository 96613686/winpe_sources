# __security_init_cookie

- ea: `0x180003cbc`
- end: `0x180003d71`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003820`

## callees

- `0x180003cbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003d1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003d1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003cf1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003cf1`

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
0x180003cbc  mov     [rsp-8+arg_10], rbx
0x180003cc1  push    rbp
0x180003cc2  mov     rbp, rsp
0x180003cc5  sub     rsp, 30h
0x180003cc9  mov     rax, cs:__security_cookie
0x180003cd0  mov     rbx, 2B992DDFA232h
0x180003cda  cmp     rax, rbx
0x180003cdd  jnz     short loc_180003D5C
0x180003cdf  xor     eax, eax
0x180003ce1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003ce5  mov     [rbp+var_10], rax
0x180003ce9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003ced  mov     qword ptr [rbp+PerformanceCount], rax
0x180003cf1  call    cs:__imp_GetSystemTimeAsFileTime
0x180003cf7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003cfb  mov     [rbp+var_10], rax
0x180003cff  call    cs:__imp_GetCurrentThreadId
0x180003d05  mov     eax, eax
0x180003d07  xor     [rbp+var_10], rax
0x180003d0b  call    cs:__imp_GetCurrentProcessId
0x180003d11  mov     eax, eax
0x180003d13  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003d17  xor     [rbp+var_10], rax
0x180003d1b  call    cs:__imp_QueryPerformanceCounter
0x180003d21  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003d24  lea     rcx, [rbp+var_10]
0x180003d28  shl     rax, 20h
0x180003d2c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003d30  xor     rax, [rbp+var_10]
0x180003d34  xor     rax, rcx
0x180003d37  mov     rcx, 0FFFFFFFFFFFFh
0x180003d41  and     rax, rcx
0x180003d44  mov     rcx, 2B992DDFA233h
0x180003d4e  cmp     rax, rbx
0x180003d51  cmovz   rax, rcx
0x180003d55  mov     cs:__security_cookie, rax
0x180003d5c  mov     rbx, [rsp+30h+arg_10]
0x180003d61  not     rax
0x180003d64  mov     cs:__security_cookie_complement, rax
0x180003d6b  add     rsp, 30h
0x180003d6f  pop     rbp
0x180003d70  retn
```
