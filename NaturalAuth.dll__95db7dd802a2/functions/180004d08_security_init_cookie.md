# __security_init_cookie

- ea: `0x180004d08`
- end: `0x180004dbd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004120`

## callees

- `0x180004d08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d57`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d3d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d3d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004d67`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004d67`

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
0x180004d08  mov     [rsp-8+arg_10], rbx
0x180004d0d  push    rbp
0x180004d0e  mov     rbp, rsp
0x180004d11  sub     rsp, 30h
0x180004d15  mov     rax, cs:__security_cookie
0x180004d1c  mov     rbx, 2B992DDFA232h
0x180004d26  cmp     rax, rbx
0x180004d29  jnz     short loc_180004DA8
0x180004d2b  xor     eax, eax
0x180004d2d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004d31  mov     [rbp+var_10], rax
0x180004d35  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004d39  mov     qword ptr [rbp+PerformanceCount], rax
0x180004d3d  call    cs:__imp_GetSystemTimeAsFileTime
0x180004d43  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004d47  mov     [rbp+var_10], rax
0x180004d4b  call    cs:__imp_GetCurrentThreadId
0x180004d51  mov     eax, eax
0x180004d53  xor     [rbp+var_10], rax
0x180004d57  call    cs:__imp_GetCurrentProcessId
0x180004d5d  mov     eax, eax
0x180004d5f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004d63  xor     [rbp+var_10], rax
0x180004d67  call    cs:__imp_QueryPerformanceCounter
0x180004d6d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004d70  lea     rcx, [rbp+var_10]
0x180004d74  shl     rax, 20h
0x180004d78  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004d7c  xor     rax, [rbp+var_10]
0x180004d80  xor     rax, rcx
0x180004d83  mov     rcx, 0FFFFFFFFFFFFh
0x180004d8d  and     rax, rcx
0x180004d90  mov     rcx, 2B992DDFA233h
0x180004d9a  cmp     rax, rbx
0x180004d9d  cmovz   rax, rcx
0x180004da1  mov     cs:__security_cookie, rax
0x180004da8  mov     rbx, [rsp+30h+arg_10]
0x180004dad  not     rax
0x180004db0  mov     cs:__security_cookie_complement, rax
0x180004db7  add     rsp, 30h
0x180004dbb  pop     rbp
0x180004dbc  retn
```
