# __security_init_cookie

- ea: `0x1400019ec`
- end: `0x140001aa1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001670`

## callees

- `0x1400019ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001a2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001a3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001a21`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001a21`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001a4b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001a4b`

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
0x1400019ec  mov     [rsp-8+arg_10], rbx
0x1400019f1  push    rbp
0x1400019f2  mov     rbp, rsp
0x1400019f5  sub     rsp, 30h
0x1400019f9  mov     rax, cs:__security_cookie
0x140001a00  mov     rbx, 2B992DDFA232h
0x140001a0a  cmp     rax, rbx
0x140001a0d  jnz     short loc_140001A8C
0x140001a0f  xor     eax, eax
0x140001a11  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001a15  mov     [rbp+var_10], rax
0x140001a19  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001a1d  mov     qword ptr [rbp+PerformanceCount], rax
0x140001a21  call    cs:__imp_GetSystemTimeAsFileTime
0x140001a27  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001a2b  mov     [rbp+var_10], rax
0x140001a2f  call    cs:__imp_GetCurrentThreadId
0x140001a35  mov     eax, eax
0x140001a37  xor     [rbp+var_10], rax
0x140001a3b  call    cs:__imp_GetCurrentProcessId
0x140001a41  mov     eax, eax
0x140001a43  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001a47  xor     [rbp+var_10], rax
0x140001a4b  call    cs:__imp_QueryPerformanceCounter
0x140001a51  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001a54  lea     rcx, [rbp+var_10]
0x140001a58  shl     rax, 20h
0x140001a5c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001a60  xor     rax, [rbp+var_10]
0x140001a64  xor     rax, rcx
0x140001a67  mov     rcx, 0FFFFFFFFFFFFh
0x140001a71  and     rax, rcx
0x140001a74  mov     rcx, 2B992DDFA233h
0x140001a7e  cmp     rax, rbx
0x140001a81  cmovz   rax, rcx
0x140001a85  mov     cs:__security_cookie, rax
0x140001a8c  mov     rbx, [rsp+30h+arg_10]
0x140001a91  not     rax
0x140001a94  mov     cs:__security_cookie_complement, rax
0x140001a9b  add     rsp, 30h
0x140001a9f  pop     rbp
0x140001aa0  retn
```
