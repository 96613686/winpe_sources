# __security_init_cookie

- ea: `0x180001550`
- end: `0x180001605`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014d0`

## callees

- `0x180001550`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800015af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800015af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000159f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000159f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001593`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001593`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001585`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001585`

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
0x180001550  mov     [rsp-8+arg_10], rbx
0x180001555  push    rbp
0x180001556  mov     rbp, rsp
0x180001559  sub     rsp, 30h
0x18000155d  mov     rax, cs:__security_cookie
0x180001564  mov     rbx, 2B992DDFA232h
0x18000156e  cmp     rax, rbx
0x180001571  jnz     short loc_1800015F0
0x180001573  xor     eax, eax
0x180001575  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001579  mov     [rbp+var_10], rax
0x18000157d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001581  mov     qword ptr [rbp+PerformanceCount], rax
0x180001585  call    cs:__imp_GetSystemTimeAsFileTime
0x18000158b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000158f  mov     [rbp+var_10], rax
0x180001593  call    cs:__imp_GetCurrentThreadId
0x180001599  mov     eax, eax
0x18000159b  xor     [rbp+var_10], rax
0x18000159f  call    cs:__imp_GetCurrentProcessId
0x1800015a5  mov     eax, eax
0x1800015a7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800015ab  xor     [rbp+var_10], rax
0x1800015af  call    cs:__imp_QueryPerformanceCounter
0x1800015b5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800015b8  lea     rcx, [rbp+var_10]
0x1800015bc  shl     rax, 20h
0x1800015c0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800015c4  xor     rax, [rbp+var_10]
0x1800015c8  xor     rax, rcx
0x1800015cb  mov     rcx, 0FFFFFFFFFFFFh
0x1800015d5  and     rax, rcx
0x1800015d8  mov     rcx, 2B992DDFA233h
0x1800015e2  cmp     rax, rbx
0x1800015e5  cmovz   rax, rcx
0x1800015e9  mov     cs:__security_cookie, rax
0x1800015f0  mov     rbx, [rsp+30h+arg_10]
0x1800015f5  not     rax
0x1800015f8  mov     cs:__security_cookie_complement, rax
0x1800015ff  add     rsp, 30h
0x180001603  pop     rbp
0x180001604  retn
```
