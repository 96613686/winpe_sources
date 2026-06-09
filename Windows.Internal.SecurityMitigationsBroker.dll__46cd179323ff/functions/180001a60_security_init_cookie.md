# __security_init_cookie

- ea: `0x180001a60`
- end: `0x180001b3d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x180001a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ab3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ab3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a99`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001abf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001acf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001abf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001acf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aea`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180001a60  mov     [rsp-8+arg_18], rbx
0x180001a65  push    rbp
0x180001a66  mov     rbp, rsp
0x180001a69  sub     rsp, 20h
0x180001a6d  xor     eax, eax
0x180001a6f  mov     rbx, 2B992DDFA232h
0x180001a79  mov     [rbp+arg_0], rax
0x180001a7d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a81  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a85  mov     rax, cs:__security_cookie
0x180001a8c  cmp     rax, rbx
0x180001a8f  jnz     loc_180001B28
0x180001a95  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a99  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a9f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001aa3  mov     [rbp+arg_0], rax
0x180001aa7  call    cs:__imp_GetCurrentProcessId
0x180001aad  mov     eax, eax
0x180001aaf  xor     [rbp+arg_0], rax
0x180001ab3  call    cs:__imp_GetCurrentThreadId
0x180001ab9  mov     eax, eax
0x180001abb  xor     [rbp+arg_0], rax
0x180001abf  call    cs:__imp_GetTickCount
0x180001ac5  mov     eax, eax
0x180001ac7  shl     rax, 18h
0x180001acb  xor     [rbp+arg_0], rax
0x180001acf  call    cs:__imp_GetTickCount
0x180001ad5  mov     eax, eax
0x180001ad7  lea     rcx, [rbp+arg_0]
0x180001adb  xor     rax, [rbp+arg_0]
0x180001adf  xor     rax, rcx
0x180001ae2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001ae6  mov     [rbp+arg_0], rax
0x180001aea  call    cs:__imp_QueryPerformanceCounter
0x180001af0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001af3  mov     rcx, 0FFFFFFFFFFFFh
0x180001afd  shl     rax, 20h
0x180001b01  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b05  xor     rax, [rbp+arg_0]
0x180001b09  and     rax, rcx
0x180001b0c  mov     rcx, rax
0x180001b0f  cmp     rax, rbx
0x180001b12  jnz     short loc_180001B21
0x180001b14  mov     rax, 2B992DDFA233h
0x180001b1e  mov     rcx, rax
0x180001b21  mov     cs:__security_cookie, rcx
0x180001b28  mov     rbx, [rsp+20h+arg_18]
0x180001b2d  not     rax
0x180001b30  mov     cs:__security_cookie_complement, rax
0x180001b37  add     rsp, 20h
0x180001b3b  pop     rbp
0x180001b3c  retn
```
