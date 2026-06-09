# __security_init_cookie

- ea: `0x18000346c`
- end: `0x180003521`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003010`

## callees

- `0x18000346c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800034bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800034bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800034cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800034cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800034a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800034a1`

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
0x18000346c  mov     [rsp-8+arg_10], rbx
0x180003471  push    rbp
0x180003472  mov     rbp, rsp
0x180003475  sub     rsp, 30h
0x180003479  mov     rax, cs:__security_cookie
0x180003480  mov     rbx, 2B992DDFA232h
0x18000348a  cmp     rax, rbx
0x18000348d  jnz     short loc_18000350C
0x18000348f  xor     eax, eax
0x180003491  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003495  mov     [rbp+var_10], rax
0x180003499  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000349d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800034a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800034a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800034ab  mov     [rbp+var_10], rax
0x1800034af  call    cs:__imp_GetCurrentThreadId
0x1800034b5  mov     eax, eax
0x1800034b7  xor     [rbp+var_10], rax
0x1800034bb  call    cs:__imp_GetCurrentProcessId
0x1800034c1  mov     eax, eax
0x1800034c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800034c7  xor     [rbp+var_10], rax
0x1800034cb  call    cs:__imp_QueryPerformanceCounter
0x1800034d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800034d4  lea     rcx, [rbp+var_10]
0x1800034d8  shl     rax, 20h
0x1800034dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800034e0  xor     rax, [rbp+var_10]
0x1800034e4  xor     rax, rcx
0x1800034e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800034f1  and     rax, rcx
0x1800034f4  mov     rcx, 2B992DDFA233h
0x1800034fe  cmp     rax, rbx
0x180003501  cmovz   rax, rcx
0x180003505  mov     cs:__security_cookie, rax
0x18000350c  mov     rbx, [rsp+30h+arg_10]
0x180003511  not     rax
0x180003514  mov     cs:__security_cookie_complement, rax
0x18000351b  add     rsp, 30h
0x18000351f  pop     rbp
0x180003520  retn
```
