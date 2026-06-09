# __security_init_cookie

- ea: `0x180004f30`
- end: `0x180004fe5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800043b0`

## callees

- `0x180004f30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f73`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004f8f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004f8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004f65`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004f65`

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
0x180004f30  mov     [rsp-8+arg_10], rbx
0x180004f35  push    rbp
0x180004f36  mov     rbp, rsp
0x180004f39  sub     rsp, 30h
0x180004f3d  mov     rax, cs:__security_cookie
0x180004f44  mov     rbx, 2B992DDFA232h
0x180004f4e  cmp     rax, rbx
0x180004f51  jnz     short loc_180004FD0
0x180004f53  xor     eax, eax
0x180004f55  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004f59  mov     [rbp+var_10], rax
0x180004f5d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004f61  mov     qword ptr [rbp+PerformanceCount], rax
0x180004f65  call    cs:__imp_GetSystemTimeAsFileTime
0x180004f6b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004f6f  mov     [rbp+var_10], rax
0x180004f73  call    cs:__imp_GetCurrentThreadId
0x180004f79  mov     eax, eax
0x180004f7b  xor     [rbp+var_10], rax
0x180004f7f  call    cs:__imp_GetCurrentProcessId
0x180004f85  mov     eax, eax
0x180004f87  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004f8b  xor     [rbp+var_10], rax
0x180004f8f  call    cs:__imp_QueryPerformanceCounter
0x180004f95  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004f98  lea     rcx, [rbp+var_10]
0x180004f9c  shl     rax, 20h
0x180004fa0  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004fa4  xor     rax, [rbp+var_10]
0x180004fa8  xor     rax, rcx
0x180004fab  mov     rcx, 0FFFFFFFFFFFFh
0x180004fb5  and     rax, rcx
0x180004fb8  mov     rcx, 2B992DDFA233h
0x180004fc2  cmp     rax, rbx
0x180004fc5  cmovz   rax, rcx
0x180004fc9  mov     cs:__security_cookie, rax
0x180004fd0  mov     rbx, [rsp+30h+arg_10]
0x180004fd5  not     rax
0x180004fd8  mov     cs:__security_cookie_complement, rax
0x180004fdf  add     rsp, 30h
0x180004fe3  pop     rbp
0x180004fe4  retn
```
