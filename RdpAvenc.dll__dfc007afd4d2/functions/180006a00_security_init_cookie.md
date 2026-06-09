# __security_init_cookie

- ea: `0x180006a00`
- end: `0x180006ab5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006530`

## callees

- `0x180006a00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006a4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006a4f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006a5f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006a5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006a35`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006a35`

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
0x180006a00  mov     [rsp-8+arg_10], rbx
0x180006a05  push    rbp
0x180006a06  mov     rbp, rsp
0x180006a09  sub     rsp, 30h
0x180006a0d  mov     rax, cs:__security_cookie
0x180006a14  mov     rbx, 2B992DDFA232h
0x180006a1e  cmp     rax, rbx
0x180006a21  jnz     short loc_180006AA0
0x180006a23  xor     eax, eax
0x180006a25  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006a29  mov     [rbp+var_10], rax
0x180006a2d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006a31  mov     qword ptr [rbp+PerformanceCount], rax
0x180006a35  call    cs:__imp_GetSystemTimeAsFileTime
0x180006a3b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180006a3f  mov     [rbp+var_10], rax
0x180006a43  call    cs:__imp_GetCurrentThreadId
0x180006a49  mov     eax, eax
0x180006a4b  xor     [rbp+var_10], rax
0x180006a4f  call    cs:__imp_GetCurrentProcessId
0x180006a55  mov     eax, eax
0x180006a57  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180006a5b  xor     [rbp+var_10], rax
0x180006a5f  call    cs:__imp_QueryPerformanceCounter
0x180006a65  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006a68  lea     rcx, [rbp+var_10]
0x180006a6c  shl     rax, 20h
0x180006a70  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006a74  xor     rax, [rbp+var_10]
0x180006a78  xor     rax, rcx
0x180006a7b  mov     rcx, 0FFFFFFFFFFFFh
0x180006a85  and     rax, rcx
0x180006a88  mov     rcx, 2B992DDFA233h
0x180006a92  cmp     rax, rbx
0x180006a95  cmovz   rax, rcx
0x180006a99  mov     cs:__security_cookie, rax
0x180006aa0  mov     rbx, [rsp+30h+arg_10]
0x180006aa5  not     rax
0x180006aa8  mov     cs:__security_cookie_complement, rax
0x180006aaf  add     rsp, 30h
0x180006ab3  pop     rbp
0x180006ab4  retn
```
