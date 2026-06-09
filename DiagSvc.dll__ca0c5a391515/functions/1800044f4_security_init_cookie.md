# __security_init_cookie

- ea: `0x1800044f4`
- end: `0x1800045a9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003f70`

## callees

- `0x1800044f4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004553`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004537`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004529`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004529`

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
0x1800044f4  mov     [rsp-8+arg_10], rbx
0x1800044f9  push    rbp
0x1800044fa  mov     rbp, rsp
0x1800044fd  sub     rsp, 30h
0x180004501  mov     rax, cs:__security_cookie
0x180004508  mov     rbx, 2B992DDFA232h
0x180004512  cmp     rax, rbx
0x180004515  jnz     short loc_180004594
0x180004517  xor     eax, eax
0x180004519  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000451d  mov     [rbp+var_10], rax
0x180004521  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004525  mov     qword ptr [rbp+PerformanceCount], rax
0x180004529  call    cs:__imp_GetSystemTimeAsFileTime
0x18000452f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004533  mov     [rbp+var_10], rax
0x180004537  call    cs:__imp_GetCurrentThreadId
0x18000453d  mov     eax, eax
0x18000453f  xor     [rbp+var_10], rax
0x180004543  call    cs:__imp_GetCurrentProcessId
0x180004549  mov     eax, eax
0x18000454b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000454f  xor     [rbp+var_10], rax
0x180004553  call    cs:__imp_QueryPerformanceCounter
0x180004559  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000455c  lea     rcx, [rbp+var_10]
0x180004560  shl     rax, 20h
0x180004564  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004568  xor     rax, [rbp+var_10]
0x18000456c  xor     rax, rcx
0x18000456f  mov     rcx, 0FFFFFFFFFFFFh
0x180004579  and     rax, rcx
0x18000457c  mov     rcx, 2B992DDFA233h
0x180004586  cmp     rax, rbx
0x180004589  cmovz   rax, rcx
0x18000458d  mov     cs:__security_cookie, rax
0x180004594  mov     rbx, [rsp+30h+arg_10]
0x180004599  not     rax
0x18000459c  mov     cs:__security_cookie_complement, rax
0x1800045a3  add     rsp, 30h
0x1800045a7  pop     rbp
0x1800045a8  retn
```
