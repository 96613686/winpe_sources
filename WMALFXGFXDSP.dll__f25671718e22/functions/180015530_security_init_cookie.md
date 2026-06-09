# __security_init_cookie

- ea: `0x180015530`
- end: `0x1800155e5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800154d4`

## callees

- `0x180015530`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001558f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001558f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001557f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001557f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015565`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015565`

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
0x180015530  mov     [rsp-8+arg_10], rbx
0x180015535  push    rbp
0x180015536  mov     rbp, rsp
0x180015539  sub     rsp, 30h
0x18001553d  mov     rax, cs:__security_cookie
0x180015544  mov     rbx, 2B992DDFA232h
0x18001554e  cmp     rax, rbx
0x180015551  jnz     short loc_1800155D0
0x180015553  xor     eax, eax
0x180015555  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015559  mov     [rbp+var_10], rax
0x18001555d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180015561  mov     qword ptr [rbp+PerformanceCount], rax
0x180015565  call    cs:__imp_GetSystemTimeAsFileTime
0x18001556b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001556f  mov     [rbp+var_10], rax
0x180015573  call    cs:__imp_GetCurrentThreadId
0x180015579  mov     eax, eax
0x18001557b  xor     [rbp+var_10], rax
0x18001557f  call    cs:__imp_GetCurrentProcessId
0x180015585  mov     eax, eax
0x180015587  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001558b  xor     [rbp+var_10], rax
0x18001558f  call    cs:__imp_QueryPerformanceCounter
0x180015595  mov     eax, dword ptr [rbp+PerformanceCount]
0x180015598  lea     rcx, [rbp+var_10]
0x18001559c  shl     rax, 20h
0x1800155a0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800155a4  xor     rax, [rbp+var_10]
0x1800155a8  xor     rax, rcx
0x1800155ab  mov     rcx, 0FFFFFFFFFFFFh
0x1800155b5  and     rax, rcx
0x1800155b8  mov     rcx, 2B992DDFA233h
0x1800155c2  cmp     rax, rbx
0x1800155c5  cmovz   rax, rcx
0x1800155c9  mov     cs:__security_cookie, rax
0x1800155d0  mov     rbx, [rsp+30h+arg_10]
0x1800155d5  not     rax
0x1800155d8  mov     cs:__security_cookie_complement, rax
0x1800155df  add     rsp, 30h
0x1800155e3  pop     rbp
0x1800155e4  retn
```
