# __security_init_cookie

- ea: `0x180049d5c`
- end: `0x180049e11`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180049cb0`

## callees

- `0x180049d5c`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180049d91`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180049d91`
- `KERNEL32!GetCurrentThreadId` at `0x180049d9f`
- `KERNEL32!GetCurrentThreadId` at `0x180049d9f`
- `KERNEL32!GetCurrentProcessId` at `0x180049dab`
- `KERNEL32!GetCurrentProcessId` at `0x180049dab`
- `KERNEL32!QueryPerformanceCounter` at `0x180049dbb`
- `KERNEL32!QueryPerformanceCounter` at `0x180049dbb`

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
0x180049d5c  mov     [rsp-8+arg_10], rbx
0x180049d61  push    rbp
0x180049d62  mov     rbp, rsp
0x180049d65  sub     rsp, 30h
0x180049d69  mov     rax, cs:__security_cookie
0x180049d70  mov     rbx, 2B992DDFA232h
0x180049d7a  cmp     rax, rbx
0x180049d7d  jnz     short loc_180049DFC
0x180049d7f  xor     eax, eax
0x180049d81  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180049d85  mov     [rbp+var_10], rax
0x180049d89  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180049d8d  mov     qword ptr [rbp+PerformanceCount], rax
0x180049d91  call    cs:__imp_GetSystemTimeAsFileTime
0x180049d97  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180049d9b  mov     [rbp+var_10], rax
0x180049d9f  call    cs:__imp_GetCurrentThreadId
0x180049da5  mov     eax, eax
0x180049da7  xor     [rbp+var_10], rax
0x180049dab  call    cs:__imp_GetCurrentProcessId
0x180049db1  mov     eax, eax
0x180049db3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180049db7  xor     [rbp+var_10], rax
0x180049dbb  call    cs:__imp_QueryPerformanceCounter
0x180049dc1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180049dc4  lea     rcx, [rbp+var_10]
0x180049dc8  shl     rax, 20h
0x180049dcc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180049dd0  xor     rax, [rbp+var_10]
0x180049dd4  xor     rax, rcx
0x180049dd7  mov     rcx, 0FFFFFFFFFFFFh
0x180049de1  and     rax, rcx
0x180049de4  mov     rcx, 2B992DDFA233h
0x180049dee  cmp     rax, rbx
0x180049df1  cmovz   rax, rcx
0x180049df5  mov     cs:__security_cookie, rax
0x180049dfc  mov     rbx, [rsp+30h+arg_10]
0x180049e01  not     rax
0x180049e04  mov     cs:__security_cookie_complement, rax
0x180049e0b  add     rsp, 30h
0x180049e0f  pop     rbp
0x180049e10  retn
```
