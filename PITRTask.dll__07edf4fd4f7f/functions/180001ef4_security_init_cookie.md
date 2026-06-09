# __security_init_cookie

- ea: `0x180001ef4`
- end: `0x180001fd1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800019b0`

## callees

- `0x180001ef4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001f3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001f63`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f2d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001f7e`

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
0x180001ef4  mov     [rsp-8+arg_18], rbx
0x180001ef9  push    rbp
0x180001efa  mov     rbp, rsp
0x180001efd  sub     rsp, 20h
0x180001f01  xor     eax, eax
0x180001f03  mov     rbx, 2B992DDFA232h
0x180001f0d  mov     [rbp+arg_0], rax
0x180001f11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f15  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f19  mov     rax, cs:__security_cookie
0x180001f20  cmp     rax, rbx
0x180001f23  jnz     loc_180001FBC
0x180001f29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001f33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001f37  mov     [rbp+arg_0], rax
0x180001f3b  call    cs:__imp_GetCurrentProcessId
0x180001f41  mov     eax, eax
0x180001f43  xor     [rbp+arg_0], rax
0x180001f47  call    cs:__imp_GetCurrentThreadId
0x180001f4d  mov     eax, eax
0x180001f4f  xor     [rbp+arg_0], rax
0x180001f53  call    cs:__imp_GetTickCount
0x180001f59  mov     eax, eax
0x180001f5b  shl     rax, 18h
0x180001f5f  xor     [rbp+arg_0], rax
0x180001f63  call    cs:__imp_GetTickCount
0x180001f69  mov     eax, eax
0x180001f6b  lea     rcx, [rbp+arg_0]
0x180001f6f  xor     rax, [rbp+arg_0]
0x180001f73  xor     rax, rcx
0x180001f76  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001f7a  mov     [rbp+arg_0], rax
0x180001f7e  call    cs:__imp_QueryPerformanceCounter
0x180001f84  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001f87  mov     rcx, 0FFFFFFFFFFFFh
0x180001f91  shl     rax, 20h
0x180001f95  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f99  xor     rax, [rbp+arg_0]
0x180001f9d  and     rax, rcx
0x180001fa0  mov     rcx, rax
0x180001fa3  cmp     rax, rbx
0x180001fa6  jnz     short loc_180001FB5
0x180001fa8  mov     rax, 2B992DDFA233h
0x180001fb2  mov     rcx, rax
0x180001fb5  mov     cs:__security_cookie, rcx
0x180001fbc  mov     rbx, [rsp+20h+arg_18]
0x180001fc1  not     rax
0x180001fc4  mov     cs:__security_cookie_complement, rax
0x180001fcb  add     rsp, 20h
0x180001fcf  pop     rbp
0x180001fd0  retn
```
