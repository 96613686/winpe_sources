# __security_init_cookie

- ea: `0x180007dc4`
- end: `0x180007e70`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800076a0`

## callees

- `0x180007dc4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180007e1a`
- `KERNEL32!QueryPerformanceCounter` at `0x180007e1a`
- `KERNEL32!GetCurrentProcessId` at `0x180007e0a`
- `KERNEL32!GetCurrentProcessId` at `0x180007e0a`
- `KERNEL32!GetCurrentThreadId` at `0x180007dfe`
- `KERNEL32!GetCurrentThreadId` at `0x180007dfe`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180007df0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180007df0`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x180007dc4  mov     [rsp-8+arg_10], rbx
0x180007dc9  push    rbp
0x180007dca  mov     rbp, rsp
0x180007dcd  sub     rsp, 30h
0x180007dd1  mov     rax, cs:__security_cookie
0x180007dd8  mov     rbx, 2B992DDFA232h
0x180007de2  cmp     rax, rbx
0x180007de5  jnz     short loc_180007E5B
0x180007de7  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180007dec  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007df0  call    cs:__imp_GetSystemTimeAsFileTime
0x180007df6  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180007dfa  mov     [rbp+var_10], rax
0x180007dfe  call    cs:__imp_GetCurrentThreadId
0x180007e04  mov     eax, eax
0x180007e06  xor     [rbp+var_10], rax
0x180007e0a  call    cs:__imp_GetCurrentProcessId
0x180007e10  mov     eax, eax
0x180007e12  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180007e16  xor     [rbp+var_10], rax
0x180007e1a  call    cs:__imp_QueryPerformanceCounter
0x180007e20  mov     eax, dword ptr [rbp+PerformanceCount]
0x180007e23  lea     rcx, [rbp+var_10]
0x180007e27  shl     rax, 20h
0x180007e2b  xor     rax, qword ptr [rbp+PerformanceCount]
0x180007e2f  xor     rax, [rbp+var_10]
0x180007e33  xor     rax, rcx
0x180007e36  mov     rcx, 0FFFFFFFFFFFFh
0x180007e40  and     rax, rcx
0x180007e43  mov     rcx, 2B992DDFA233h
0x180007e4d  cmp     rax, rbx
0x180007e50  cmovz   rax, rcx
0x180007e54  mov     cs:__security_cookie, rax
0x180007e5b  mov     rbx, [rsp+30h+arg_10]
0x180007e60  not     rax
0x180007e63  mov     cs:__security_cookie_complement, rax
0x180007e6a  add     rsp, 30h
0x180007e6e  pop     rbp
0x180007e6f  retn
```
