# __security_init_cookie

- ea: `0x180002b8c`
- end: `0x180002c41`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002660`

## callees

- `0x180002b8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002bdb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002beb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002beb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002bc1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002bc1`

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
0x180002b8c  mov     [rsp-8+arg_10], rbx
0x180002b91  push    rbp
0x180002b92  mov     rbp, rsp
0x180002b95  sub     rsp, 30h
0x180002b99  mov     rax, cs:__security_cookie
0x180002ba0  mov     rbx, 2B992DDFA232h
0x180002baa  cmp     rax, rbx
0x180002bad  jnz     short loc_180002C2C
0x180002baf  xor     eax, eax
0x180002bb1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002bb5  mov     [rbp+var_10], rax
0x180002bb9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002bbd  mov     qword ptr [rbp+PerformanceCount], rax
0x180002bc1  call    cs:__imp_GetSystemTimeAsFileTime
0x180002bc7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002bcb  mov     [rbp+var_10], rax
0x180002bcf  call    cs:__imp_GetCurrentThreadId
0x180002bd5  mov     eax, eax
0x180002bd7  xor     [rbp+var_10], rax
0x180002bdb  call    cs:__imp_GetCurrentProcessId
0x180002be1  mov     eax, eax
0x180002be3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002be7  xor     [rbp+var_10], rax
0x180002beb  call    cs:__imp_QueryPerformanceCounter
0x180002bf1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002bf4  lea     rcx, [rbp+var_10]
0x180002bf8  shl     rax, 20h
0x180002bfc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002c00  xor     rax, [rbp+var_10]
0x180002c04  xor     rax, rcx
0x180002c07  mov     rcx, 0FFFFFFFFFFFFh
0x180002c11  and     rax, rcx
0x180002c14  mov     rcx, 2B992DDFA233h
0x180002c1e  cmp     rax, rbx
0x180002c21  cmovz   rax, rcx
0x180002c25  mov     cs:__security_cookie, rax
0x180002c2c  mov     rbx, [rsp+30h+arg_10]
0x180002c31  not     rax
0x180002c34  mov     cs:__security_cookie_complement, rax
0x180002c3b  add     rsp, 30h
0x180002c3f  pop     rbp
0x180002c40  retn
```
