# __security_init_cookie

- ea: `0x18000fca4`
- end: `0x18000fd81`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f590`

## callees

- `0x18000fca4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fcf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fceb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fceb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000fd2e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000fd2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fcdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fcdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fd03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fd13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fd03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000fd13`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18000fca4  mov     [rsp-8+arg_18], rbx
0x18000fca9  push    rbp
0x18000fcaa  mov     rbp, rsp
0x18000fcad  sub     rsp, 20h
0x18000fcb1  xor     eax, eax
0x18000fcb3  mov     rbx, 2B992DDFA232h
0x18000fcbd  mov     [rbp+arg_0], rax
0x18000fcc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000fcc5  mov     qword ptr [rbp+PerformanceCount], rax
0x18000fcc9  mov     rax, cs:__security_cookie
0x18000fcd0  cmp     rax, rbx
0x18000fcd3  jnz     loc_18000FD6C
0x18000fcd9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fcdd  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fce3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000fce7  mov     [rbp+arg_0], rax
0x18000fceb  call    cs:__imp_GetCurrentProcessId
0x18000fcf1  mov     eax, eax
0x18000fcf3  xor     [rbp+arg_0], rax
0x18000fcf7  call    cs:__imp_GetCurrentThreadId
0x18000fcfd  mov     eax, eax
0x18000fcff  xor     [rbp+arg_0], rax
0x18000fd03  call    cs:__imp_GetTickCount
0x18000fd09  mov     eax, eax
0x18000fd0b  shl     rax, 18h
0x18000fd0f  xor     [rbp+arg_0], rax
0x18000fd13  call    cs:__imp_GetTickCount
0x18000fd19  mov     eax, eax
0x18000fd1b  lea     rcx, [rbp+arg_0]
0x18000fd1f  xor     rax, [rbp+arg_0]
0x18000fd23  xor     rax, rcx
0x18000fd26  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000fd2a  mov     [rbp+arg_0], rax
0x18000fd2e  call    cs:__imp_QueryPerformanceCounter
0x18000fd34  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000fd37  mov     rcx, 0FFFFFFFFFFFFh
0x18000fd41  shl     rax, 20h
0x18000fd45  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000fd49  xor     rax, [rbp+arg_0]
0x18000fd4d  and     rax, rcx
0x18000fd50  mov     rcx, rax
0x18000fd53  cmp     rax, rbx
0x18000fd56  jnz     short loc_18000FD65
0x18000fd58  mov     rax, 2B992DDFA233h
0x18000fd62  mov     rcx, rax
0x18000fd65  mov     cs:__security_cookie, rcx
0x18000fd6c  mov     rbx, [rsp+20h+arg_18]
0x18000fd71  not     rax
0x18000fd74  mov     cs:__security_cookie_complement, rax
0x18000fd7b  add     rsp, 20h
0x18000fd7f  pop     rbp
0x18000fd80  retn
```
