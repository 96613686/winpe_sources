# __security_init_cookie

- ea: `0x18030d3f0`
- end: `0x18030d49c`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18030c7d0`

## callees

- `0x18030d3f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18030d42a`
- `KERNEL32!GetCurrentThreadId` at `0x18030d42a`
- `KERNEL32!QueryPerformanceCounter` at `0x18030d446`
- `KERNEL32!QueryPerformanceCounter` at `0x18030d446`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18030d41c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18030d41c`
- `KERNEL32!GetCurrentProcessId` at `0x18030d436`
- `KERNEL32!GetCurrentProcessId` at `0x18030d436`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x18030d3f0  mov     [rsp-8+arg_18], rbx
0x18030d3f5  push    rbp
0x18030d3f6  mov     rbp, rsp
0x18030d3f9  sub     rsp, 20h
0x18030d3fd  mov     rax, cs:__security_cookie
0x18030d404  mov     rbx, 2B992DDFA232h
0x18030d40e  cmp     rax, rbx
0x18030d411  jnz     short loc_18030D487
0x18030d413  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18030d418  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18030d41c  call    cs:__imp_GetSystemTimeAsFileTime
0x18030d422  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18030d426  mov     [rbp+arg_0], rax
0x18030d42a  call    cs:__imp_GetCurrentThreadId
0x18030d430  mov     eax, eax
0x18030d432  xor     [rbp+arg_0], rax
0x18030d436  call    cs:__imp_GetCurrentProcessId
0x18030d43c  mov     eax, eax
0x18030d43e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18030d442  xor     [rbp+arg_0], rax
0x18030d446  call    cs:__imp_QueryPerformanceCounter
0x18030d44c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18030d44f  lea     rcx, [rbp+arg_0]
0x18030d453  shl     rax, 20h
0x18030d457  xor     rax, qword ptr [rbp+PerformanceCount]
0x18030d45b  xor     rax, [rbp+arg_0]
0x18030d45f  xor     rax, rcx
0x18030d462  mov     rcx, 0FFFFFFFFFFFFh
0x18030d46c  and     rax, rcx
0x18030d46f  mov     rcx, 2B992DDFA233h
0x18030d479  cmp     rax, rbx
0x18030d47c  cmovz   rax, rcx
0x18030d480  mov     cs:__security_cookie, rax
0x18030d487  mov     rbx, [rsp+20h+arg_18]
0x18030d48c  not     rax
0x18030d48f  mov     cs:__security_cookie_complement, rax
0x18030d496  add     rsp, 20h
0x18030d49a  pop     rbp
0x18030d49b  retn
```
