# __security_init_cookie

- ea: `0x180003c18`
- end: `0x180003ccd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003380`

## callees

- `0x180003c18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c67`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003c77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003c77`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003c4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003c4d`

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
0x180003c18  mov     [rsp-8+arg_10], rbx
0x180003c1d  push    rbp
0x180003c1e  mov     rbp, rsp
0x180003c21  sub     rsp, 30h
0x180003c25  mov     rax, cs:__security_cookie
0x180003c2c  mov     rbx, 2B992DDFA232h
0x180003c36  cmp     rax, rbx
0x180003c39  jnz     short loc_180003CB8
0x180003c3b  xor     eax, eax
0x180003c3d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003c41  mov     [rbp+var_10], rax
0x180003c45  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003c49  mov     qword ptr [rbp+PerformanceCount], rax
0x180003c4d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003c53  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003c57  mov     [rbp+var_10], rax
0x180003c5b  call    cs:__imp_GetCurrentThreadId
0x180003c61  mov     eax, eax
0x180003c63  xor     [rbp+var_10], rax
0x180003c67  call    cs:__imp_GetCurrentProcessId
0x180003c6d  mov     eax, eax
0x180003c6f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003c73  xor     [rbp+var_10], rax
0x180003c77  call    cs:__imp_QueryPerformanceCounter
0x180003c7d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003c80  lea     rcx, [rbp+var_10]
0x180003c84  shl     rax, 20h
0x180003c88  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003c8c  xor     rax, [rbp+var_10]
0x180003c90  xor     rax, rcx
0x180003c93  mov     rcx, 0FFFFFFFFFFFFh
0x180003c9d  and     rax, rcx
0x180003ca0  mov     rcx, 2B992DDFA233h
0x180003caa  cmp     rax, rbx
0x180003cad  cmovz   rax, rcx
0x180003cb1  mov     cs:__security_cookie, rax
0x180003cb8  mov     rbx, [rsp+30h+arg_10]
0x180003cbd  not     rax
0x180003cc0  mov     cs:__security_cookie_complement, rax
0x180003cc7  add     rsp, 30h
0x180003ccb  pop     rbp
0x180003ccc  retn
```
