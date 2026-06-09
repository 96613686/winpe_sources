# __security_init_cookie

- ea: `0x180004d24`
- end: `0x180004dd9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004560`

## callees

- `0x180004d24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d73`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004d83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004d83`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d59`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d59`

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
0x180004d24  mov     [rsp-8+arg_10], rbx
0x180004d29  push    rbp
0x180004d2a  mov     rbp, rsp
0x180004d2d  sub     rsp, 30h
0x180004d31  mov     rax, cs:__security_cookie
0x180004d38  mov     rbx, 2B992DDFA232h
0x180004d42  cmp     rax, rbx
0x180004d45  jnz     short loc_180004DC4
0x180004d47  xor     eax, eax
0x180004d49  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004d4d  mov     [rbp+var_10], rax
0x180004d51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004d55  mov     qword ptr [rbp+PerformanceCount], rax
0x180004d59  call    cs:__imp_GetSystemTimeAsFileTime
0x180004d5f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004d63  mov     [rbp+var_10], rax
0x180004d67  call    cs:__imp_GetCurrentThreadId
0x180004d6d  mov     eax, eax
0x180004d6f  xor     [rbp+var_10], rax
0x180004d73  call    cs:__imp_GetCurrentProcessId
0x180004d79  mov     eax, eax
0x180004d7b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004d7f  xor     [rbp+var_10], rax
0x180004d83  call    cs:__imp_QueryPerformanceCounter
0x180004d89  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004d8c  lea     rcx, [rbp+var_10]
0x180004d90  shl     rax, 20h
0x180004d94  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004d98  xor     rax, [rbp+var_10]
0x180004d9c  xor     rax, rcx
0x180004d9f  mov     rcx, 0FFFFFFFFFFFFh
0x180004da9  and     rax, rcx
0x180004dac  mov     rcx, 2B992DDFA233h
0x180004db6  cmp     rax, rbx
0x180004db9  cmovz   rax, rcx
0x180004dbd  mov     cs:__security_cookie, rax
0x180004dc4  mov     rbx, [rsp+30h+arg_10]
0x180004dc9  not     rax
0x180004dcc  mov     cs:__security_cookie_complement, rax
0x180004dd3  add     rsp, 30h
0x180004dd7  pop     rbp
0x180004dd8  retn
```
