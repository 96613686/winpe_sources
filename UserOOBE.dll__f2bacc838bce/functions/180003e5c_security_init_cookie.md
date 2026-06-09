# __security_init_cookie

- ea: `0x180003e5c`
- end: `0x180003f11`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003260`

## callees

- `0x180003e5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003e9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003eab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003eab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003e91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003e91`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003ebb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003ebb`

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
0x180003e5c  mov     [rsp-8+arg_10], rbx
0x180003e61  push    rbp
0x180003e62  mov     rbp, rsp
0x180003e65  sub     rsp, 30h
0x180003e69  mov     rax, cs:__security_cookie
0x180003e70  mov     rbx, 2B992DDFA232h
0x180003e7a  cmp     rax, rbx
0x180003e7d  jnz     short loc_180003EFC
0x180003e7f  xor     eax, eax
0x180003e81  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003e85  mov     [rbp+var_10], rax
0x180003e89  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003e8d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003e91  call    cs:__imp_GetSystemTimeAsFileTime
0x180003e97  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003e9b  mov     [rbp+var_10], rax
0x180003e9f  call    cs:__imp_GetCurrentThreadId
0x180003ea5  mov     eax, eax
0x180003ea7  xor     [rbp+var_10], rax
0x180003eab  call    cs:__imp_GetCurrentProcessId
0x180003eb1  mov     eax, eax
0x180003eb3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003eb7  xor     [rbp+var_10], rax
0x180003ebb  call    cs:__imp_QueryPerformanceCounter
0x180003ec1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003ec4  lea     rcx, [rbp+var_10]
0x180003ec8  shl     rax, 20h
0x180003ecc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003ed0  xor     rax, [rbp+var_10]
0x180003ed4  xor     rax, rcx
0x180003ed7  mov     rcx, 0FFFFFFFFFFFFh
0x180003ee1  and     rax, rcx
0x180003ee4  mov     rcx, 2B992DDFA233h
0x180003eee  cmp     rax, rbx
0x180003ef1  cmovz   rax, rcx
0x180003ef5  mov     cs:__security_cookie, rax
0x180003efc  mov     rbx, [rsp+30h+arg_10]
0x180003f01  not     rax
0x180003f04  mov     cs:__security_cookie_complement, rax
0x180003f0b  add     rsp, 30h
0x180003f0f  pop     rbp
0x180003f10  retn
```
