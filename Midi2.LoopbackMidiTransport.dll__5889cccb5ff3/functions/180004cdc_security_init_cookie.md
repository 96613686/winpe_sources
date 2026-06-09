# __security_init_cookie

- ea: `0x180004cdc`
- end: `0x180004d91`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004120`

## callees

- `0x180004cdc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d1f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004d3b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004d3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d11`

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
0x180004cdc  mov     [rsp-8+arg_10], rbx
0x180004ce1  push    rbp
0x180004ce2  mov     rbp, rsp
0x180004ce5  sub     rsp, 30h
0x180004ce9  mov     rax, cs:__security_cookie
0x180004cf0  mov     rbx, 2B992DDFA232h
0x180004cfa  cmp     rax, rbx
0x180004cfd  jnz     short loc_180004D7C
0x180004cff  xor     eax, eax
0x180004d01  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004d05  mov     [rbp+var_10], rax
0x180004d09  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004d0d  mov     qword ptr [rbp+PerformanceCount], rax
0x180004d11  call    cs:__imp_GetSystemTimeAsFileTime
0x180004d17  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004d1b  mov     [rbp+var_10], rax
0x180004d1f  call    cs:__imp_GetCurrentThreadId
0x180004d25  mov     eax, eax
0x180004d27  xor     [rbp+var_10], rax
0x180004d2b  call    cs:__imp_GetCurrentProcessId
0x180004d31  mov     eax, eax
0x180004d33  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004d37  xor     [rbp+var_10], rax
0x180004d3b  call    cs:__imp_QueryPerformanceCounter
0x180004d41  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004d44  lea     rcx, [rbp+var_10]
0x180004d48  shl     rax, 20h
0x180004d4c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004d50  xor     rax, [rbp+var_10]
0x180004d54  xor     rax, rcx
0x180004d57  mov     rcx, 0FFFFFFFFFFFFh
0x180004d61  and     rax, rcx
0x180004d64  mov     rcx, 2B992DDFA233h
0x180004d6e  cmp     rax, rbx
0x180004d71  cmovz   rax, rcx
0x180004d75  mov     cs:__security_cookie, rax
0x180004d7c  mov     rbx, [rsp+30h+arg_10]
0x180004d81  not     rax
0x180004d84  mov     cs:__security_cookie_complement, rax
0x180004d8b  add     rsp, 30h
0x180004d8f  pop     rbp
0x180004d90  retn
```
