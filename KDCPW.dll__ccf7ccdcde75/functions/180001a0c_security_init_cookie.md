# __security_init_cookie

- ea: `0x180001a0c`
- end: `0x180001ac1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015e0`

## callees

- `0x180001a0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a4f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a6b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a6b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a41`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a41`

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
0x180001a0c  mov     [rsp-8+arg_10], rbx
0x180001a11  push    rbp
0x180001a12  mov     rbp, rsp
0x180001a15  sub     rsp, 30h
0x180001a19  mov     rax, cs:__security_cookie
0x180001a20  mov     rbx, 2B992DDFA232h
0x180001a2a  cmp     rax, rbx
0x180001a2d  jnz     short loc_180001AAC
0x180001a2f  xor     eax, eax
0x180001a31  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a35  mov     [rbp+var_10], rax
0x180001a39  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a3d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a41  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a47  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a4b  mov     [rbp+var_10], rax
0x180001a4f  call    cs:__imp_GetCurrentThreadId
0x180001a55  mov     eax, eax
0x180001a57  xor     [rbp+var_10], rax
0x180001a5b  call    cs:__imp_GetCurrentProcessId
0x180001a61  mov     eax, eax
0x180001a63  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a67  xor     [rbp+var_10], rax
0x180001a6b  call    cs:__imp_QueryPerformanceCounter
0x180001a71  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a74  lea     rcx, [rbp+var_10]
0x180001a78  shl     rax, 20h
0x180001a7c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a80  xor     rax, [rbp+var_10]
0x180001a84  xor     rax, rcx
0x180001a87  mov     rcx, 0FFFFFFFFFFFFh
0x180001a91  and     rax, rcx
0x180001a94  mov     rcx, 2B992DDFA233h
0x180001a9e  cmp     rax, rbx
0x180001aa1  cmovz   rax, rcx
0x180001aa5  mov     cs:__security_cookie, rax
0x180001aac  mov     rbx, [rsp+30h+arg_10]
0x180001ab1  not     rax
0x180001ab4  mov     cs:__security_cookie_complement, rax
0x180001abb  add     rsp, 30h
0x180001abf  pop     rbp
0x180001ac0  retn
```
