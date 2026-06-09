# __security_init_cookie

- ea: `0x180001f1c`
- end: `0x180001fd1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a70`

## callees

- `0x180001f1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f51`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f7b`

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
0x180001f1c  mov     [rsp-8+arg_10], rbx
0x180001f21  push    rbp
0x180001f22  mov     rbp, rsp
0x180001f25  sub     rsp, 30h
0x180001f29  mov     rax, cs:__security_cookie
0x180001f30  mov     rbx, 2B992DDFA232h
0x180001f3a  cmp     rax, rbx
0x180001f3d  jnz     short loc_180001FBC
0x180001f3f  xor     eax, eax
0x180001f41  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f45  mov     [rbp+var_10], rax
0x180001f49  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f4d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f51  call    cs:__imp_GetSystemTimeAsFileTime
0x180001f57  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001f5b  mov     [rbp+var_10], rax
0x180001f5f  call    cs:__imp_GetCurrentThreadId
0x180001f65  mov     eax, eax
0x180001f67  xor     [rbp+var_10], rax
0x180001f6b  call    cs:__imp_GetCurrentProcessId
0x180001f71  mov     eax, eax
0x180001f73  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001f77  xor     [rbp+var_10], rax
0x180001f7b  call    cs:__imp_QueryPerformanceCounter
0x180001f81  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001f84  lea     rcx, [rbp+var_10]
0x180001f88  shl     rax, 20h
0x180001f8c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f90  xor     rax, [rbp+var_10]
0x180001f94  xor     rax, rcx
0x180001f97  mov     rcx, 0FFFFFFFFFFFFh
0x180001fa1  and     rax, rcx
0x180001fa4  mov     rcx, 2B992DDFA233h
0x180001fae  cmp     rax, rbx
0x180001fb1  cmovz   rax, rcx
0x180001fb5  mov     cs:__security_cookie, rax
0x180001fbc  mov     rbx, [rsp+30h+arg_10]
0x180001fc1  not     rax
0x180001fc4  mov     cs:__security_cookie_complement, rax
0x180001fcb  add     rsp, 30h
0x180001fcf  pop     rbp
0x180001fd0  retn
```
