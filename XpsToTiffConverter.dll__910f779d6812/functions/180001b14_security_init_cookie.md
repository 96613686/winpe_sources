# __security_init_cookie

- ea: `0x180001b14`
- end: `0x180001bc9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001650`

## callees

- `0x180001b14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b63`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b73`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b49`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b49`

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
0x180001b14  mov     [rsp-8+arg_10], rbx
0x180001b19  push    rbp
0x180001b1a  mov     rbp, rsp
0x180001b1d  sub     rsp, 30h
0x180001b21  mov     rax, cs:__security_cookie
0x180001b28  mov     rbx, 2B992DDFA232h
0x180001b32  cmp     rax, rbx
0x180001b35  jnz     short loc_180001BB4
0x180001b37  xor     eax, eax
0x180001b39  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001b3d  mov     [rbp+var_10], rax
0x180001b41  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001b45  mov     qword ptr [rbp+PerformanceCount], rax
0x180001b49  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b4f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001b53  mov     [rbp+var_10], rax
0x180001b57  call    cs:__imp_GetCurrentThreadId
0x180001b5d  mov     eax, eax
0x180001b5f  xor     [rbp+var_10], rax
0x180001b63  call    cs:__imp_GetCurrentProcessId
0x180001b69  mov     eax, eax
0x180001b6b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001b6f  xor     [rbp+var_10], rax
0x180001b73  call    cs:__imp_QueryPerformanceCounter
0x180001b79  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001b7c  lea     rcx, [rbp+var_10]
0x180001b80  shl     rax, 20h
0x180001b84  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b88  xor     rax, [rbp+var_10]
0x180001b8c  xor     rax, rcx
0x180001b8f  mov     rcx, 0FFFFFFFFFFFFh
0x180001b99  and     rax, rcx
0x180001b9c  mov     rcx, 2B992DDFA233h
0x180001ba6  cmp     rax, rbx
0x180001ba9  cmovz   rax, rcx
0x180001bad  mov     cs:__security_cookie, rax
0x180001bb4  mov     rbx, [rsp+30h+arg_10]
0x180001bb9  not     rax
0x180001bbc  mov     cs:__security_cookie_complement, rax
0x180001bc3  add     rsp, 30h
0x180001bc7  pop     rbp
0x180001bc8  retn
```
