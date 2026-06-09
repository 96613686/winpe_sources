# __security_init_cookie

- ea: `0x1800099f0`
- end: `0x180009aa5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009450`

## callees

- `0x1800099f0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009a4f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009a4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009a33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009a3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009a25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009a25`

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
0x1800099f0  mov     [rsp-8+arg_10], rbx
0x1800099f5  push    rbp
0x1800099f6  mov     rbp, rsp
0x1800099f9  sub     rsp, 30h
0x1800099fd  mov     rax, cs:__security_cookie
0x180009a04  mov     rbx, 2B992DDFA232h
0x180009a0e  cmp     rax, rbx
0x180009a11  jnz     short loc_180009A90
0x180009a13  xor     eax, eax
0x180009a15  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180009a19  mov     [rbp+var_10], rax
0x180009a1d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180009a21  mov     qword ptr [rbp+PerformanceCount], rax
0x180009a25  call    cs:__imp_GetSystemTimeAsFileTime
0x180009a2b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180009a2f  mov     [rbp+var_10], rax
0x180009a33  call    cs:__imp_GetCurrentThreadId
0x180009a39  mov     eax, eax
0x180009a3b  xor     [rbp+var_10], rax
0x180009a3f  call    cs:__imp_GetCurrentProcessId
0x180009a45  mov     eax, eax
0x180009a47  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180009a4b  xor     [rbp+var_10], rax
0x180009a4f  call    cs:__imp_QueryPerformanceCounter
0x180009a55  mov     eax, dword ptr [rbp+PerformanceCount]
0x180009a58  lea     rcx, [rbp+var_10]
0x180009a5c  shl     rax, 20h
0x180009a60  xor     rax, qword ptr [rbp+PerformanceCount]
0x180009a64  xor     rax, [rbp+var_10]
0x180009a68  xor     rax, rcx
0x180009a6b  mov     rcx, 0FFFFFFFFFFFFh
0x180009a75  and     rax, rcx
0x180009a78  mov     rcx, 2B992DDFA233h
0x180009a82  cmp     rax, rbx
0x180009a85  cmovz   rax, rcx
0x180009a89  mov     cs:__security_cookie, rax
0x180009a90  mov     rbx, [rsp+30h+arg_10]
0x180009a95  not     rax
0x180009a98  mov     cs:__security_cookie_complement, rax
0x180009a9f  add     rsp, 30h
0x180009aa3  pop     rbp
0x180009aa4  retn
```
