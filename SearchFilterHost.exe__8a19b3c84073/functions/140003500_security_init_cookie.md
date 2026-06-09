# __security_init_cookie

- ea: `0x140003500`
- end: `0x1400035b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003070`

## callees

- `0x140003500`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000354f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000354f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003543`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000355f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000355f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003535`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003535`

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
0x140003500  mov     [rsp-8+arg_10], rbx
0x140003505  push    rbp
0x140003506  mov     rbp, rsp
0x140003509  sub     rsp, 30h
0x14000350d  mov     rax, cs:__security_cookie
0x140003514  mov     rbx, 2B992DDFA232h
0x14000351e  cmp     rax, rbx
0x140003521  jnz     short loc_1400035A0
0x140003523  xor     eax, eax
0x140003525  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003529  mov     [rbp+var_10], rax
0x14000352d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140003531  mov     qword ptr [rbp+PerformanceCount], rax
0x140003535  call    cs:__imp_GetSystemTimeAsFileTime
0x14000353b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000353f  mov     [rbp+var_10], rax
0x140003543  call    cs:__imp_GetCurrentThreadId
0x140003549  mov     eax, eax
0x14000354b  xor     [rbp+var_10], rax
0x14000354f  call    cs:__imp_GetCurrentProcessId
0x140003555  mov     eax, eax
0x140003557  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000355b  xor     [rbp+var_10], rax
0x14000355f  call    cs:__imp_QueryPerformanceCounter
0x140003565  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003568  lea     rcx, [rbp+var_10]
0x14000356c  shl     rax, 20h
0x140003570  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003574  xor     rax, [rbp+var_10]
0x140003578  xor     rax, rcx
0x14000357b  mov     rcx, 0FFFFFFFFFFFFh
0x140003585  and     rax, rcx
0x140003588  mov     rcx, 2B992DDFA233h
0x140003592  cmp     rax, rbx
0x140003595  cmovz   rax, rcx
0x140003599  mov     cs:__security_cookie, rax
0x1400035a0  mov     rbx, [rsp+30h+arg_10]
0x1400035a5  not     rax
0x1400035a8  mov     cs:__security_cookie_complement, rax
0x1400035af  add     rsp, 30h
0x1400035b3  pop     rbp
0x1400035b4  retn
```
