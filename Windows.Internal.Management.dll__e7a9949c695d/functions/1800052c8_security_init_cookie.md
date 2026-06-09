# __security_init_cookie

- ea: `0x1800052c8`
- end: `0x18000537d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004cf0`

## callees

- `0x1800052c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005317`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005317`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000530b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000530b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005327`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005327`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800052fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800052fd`

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
0x1800052c8  mov     [rsp-8+arg_10], rbx
0x1800052cd  push    rbp
0x1800052ce  mov     rbp, rsp
0x1800052d1  sub     rsp, 30h
0x1800052d5  mov     rax, cs:__security_cookie
0x1800052dc  mov     rbx, 2B992DDFA232h
0x1800052e6  cmp     rax, rbx
0x1800052e9  jnz     short loc_180005368
0x1800052eb  xor     eax, eax
0x1800052ed  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800052f1  mov     [rbp+var_10], rax
0x1800052f5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800052f9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800052fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180005303  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005307  mov     [rbp+var_10], rax
0x18000530b  call    cs:__imp_GetCurrentThreadId
0x180005311  mov     eax, eax
0x180005313  xor     [rbp+var_10], rax
0x180005317  call    cs:__imp_GetCurrentProcessId
0x18000531d  mov     eax, eax
0x18000531f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005323  xor     [rbp+var_10], rax
0x180005327  call    cs:__imp_QueryPerformanceCounter
0x18000532d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005330  lea     rcx, [rbp+var_10]
0x180005334  shl     rax, 20h
0x180005338  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000533c  xor     rax, [rbp+var_10]
0x180005340  xor     rax, rcx
0x180005343  mov     rcx, 0FFFFFFFFFFFFh
0x18000534d  and     rax, rcx
0x180005350  mov     rcx, 2B992DDFA233h
0x18000535a  cmp     rax, rbx
0x18000535d  cmovz   rax, rcx
0x180005361  mov     cs:__security_cookie, rax
0x180005368  mov     rbx, [rsp+30h+arg_10]
0x18000536d  not     rax
0x180005370  mov     cs:__security_cookie_complement, rax
0x180005377  add     rsp, 30h
0x18000537b  pop     rbp
0x18000537c  retn
```
