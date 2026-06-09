# __security_init_cookie

- ea: `0x180002cec`
- end: `0x180002da1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800028c0`

## callees

- `0x180002cec`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002d21`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002d21`
- `KERNEL32!QueryPerformanceCounter` at `0x180002d4b`
- `KERNEL32!QueryPerformanceCounter` at `0x180002d4b`
- `KERNEL32!GetCurrentProcessId` at `0x180002d3b`
- `KERNEL32!GetCurrentProcessId` at `0x180002d3b`
- `KERNEL32!GetCurrentThreadId` at `0x180002d2f`
- `KERNEL32!GetCurrentThreadId` at `0x180002d2f`

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
0x180002cec  mov     [rsp-8+arg_10], rbx
0x180002cf1  push    rbp
0x180002cf2  mov     rbp, rsp
0x180002cf5  sub     rsp, 30h
0x180002cf9  mov     rax, cs:__security_cookie
0x180002d00  mov     rbx, 2B992DDFA232h
0x180002d0a  cmp     rax, rbx
0x180002d0d  jnz     short loc_180002D8C
0x180002d0f  xor     eax, eax
0x180002d11  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002d15  mov     [rbp+var_10], rax
0x180002d19  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002d1d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002d21  call    cs:__imp_GetSystemTimeAsFileTime
0x180002d27  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002d2b  mov     [rbp+var_10], rax
0x180002d2f  call    cs:__imp_GetCurrentThreadId
0x180002d35  mov     eax, eax
0x180002d37  xor     [rbp+var_10], rax
0x180002d3b  call    cs:__imp_GetCurrentProcessId
0x180002d41  mov     eax, eax
0x180002d43  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002d47  xor     [rbp+var_10], rax
0x180002d4b  call    cs:__imp_QueryPerformanceCounter
0x180002d51  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002d54  lea     rcx, [rbp+var_10]
0x180002d58  shl     rax, 20h
0x180002d5c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002d60  xor     rax, [rbp+var_10]
0x180002d64  xor     rax, rcx
0x180002d67  mov     rcx, 0FFFFFFFFFFFFh
0x180002d71  and     rax, rcx
0x180002d74  mov     rcx, 2B992DDFA233h
0x180002d7e  cmp     rax, rbx
0x180002d81  cmovz   rax, rcx
0x180002d85  mov     cs:__security_cookie, rax
0x180002d8c  mov     rbx, [rsp+30h+arg_10]
0x180002d91  not     rax
0x180002d94  mov     cs:__security_cookie_complement, rax
0x180002d9b  add     rsp, 30h
0x180002d9f  pop     rbp
0x180002da0  retn
```
