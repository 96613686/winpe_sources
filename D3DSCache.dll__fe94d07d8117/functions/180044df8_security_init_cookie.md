# __security_init_cookie

- ea: `0x180044df8`
- end: `0x180044ead`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800449a0`

## callees

- `0x180044df8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044e3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044e3b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180044e57`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180044e57`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044e2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044e2d`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180044df8  mov     [rsp-8+arg_10], rbx
0x180044dfd  push    rbp
0x180044dfe  mov     rbp, rsp
0x180044e01  sub     rsp, 30h
0x180044e05  mov     rax, cs:__security_cookie
0x180044e0c  mov     rbx, 2B992DDFA232h
0x180044e16  cmp     rax, rbx
0x180044e19  jnz     short loc_180044E98
0x180044e1b  xor     eax, eax
0x180044e1d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180044e21  mov     [rbp+var_10], rax
0x180044e25  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180044e29  mov     qword ptr [rbp+PerformanceCount], rax
0x180044e2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180044e33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180044e37  mov     [rbp+var_10], rax
0x180044e3b  call    cs:__imp_GetCurrentThreadId
0x180044e41  mov     eax, eax
0x180044e43  xor     [rbp+var_10], rax
0x180044e47  call    cs:__imp_GetCurrentProcessId
0x180044e4d  mov     eax, eax
0x180044e4f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180044e53  xor     [rbp+var_10], rax
0x180044e57  call    cs:__imp_QueryPerformanceCounter
0x180044e5d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180044e60  lea     rcx, [rbp+var_10]
0x180044e64  shl     rax, 20h
0x180044e68  xor     rax, qword ptr [rbp+PerformanceCount]
0x180044e6c  xor     rax, [rbp+var_10]
0x180044e70  xor     rax, rcx
0x180044e73  mov     rcx, 0FFFFFFFFFFFFh
0x180044e7d  and     rax, rcx
0x180044e80  mov     rcx, 2B992DDFA233h
0x180044e8a  cmp     rax, rbx
0x180044e8d  cmovz   rax, rcx
0x180044e91  mov     cs:__security_cookie, rax
0x180044e98  mov     rbx, [rsp+30h+arg_10]
0x180044e9d  not     rax
0x180044ea0  mov     cs:__security_cookie_complement, rax
0x180044ea7  add     rsp, 30h
0x180044eab  pop     rbp
0x180044eac  retn
```
