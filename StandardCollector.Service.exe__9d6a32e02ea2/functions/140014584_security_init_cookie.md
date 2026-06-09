# __security_init_cookie

- ea: `0x140014584`
- end: `0x140014633`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140013e50`

## callees

- `0x140014584`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1400145dd`
- `KERNEL32!QueryPerformanceCounter` at `0x1400145dd`
- `KERNEL32!GetCurrentThreadId` at `0x1400145c1`
- `KERNEL32!GetCurrentThreadId` at `0x1400145c1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400145b3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400145b3`
- `KERNEL32!GetCurrentProcessId` at `0x1400145cd`
- `KERNEL32!GetCurrentProcessId` at `0x1400145cd`

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
0x140014584  mov     [rsp-8+arg_10], rbx
0x140014589  push    rbp
0x14001458a  mov     rbp, rsp
0x14001458d  sub     rsp, 30h
0x140014591  mov     rax, cs:__security_cookie
0x140014598  mov     rbx, 2B992DDFA232h
0x1400145a2  cmp     rax, rbx
0x1400145a5  jnz     short loc_14001461E
0x1400145a7  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400145ab  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1400145b3  call    cs:__imp_GetSystemTimeAsFileTime
0x1400145b9  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400145bd  mov     [rbp+var_10], rax
0x1400145c1  call    cs:__imp_GetCurrentThreadId
0x1400145c7  mov     eax, eax
0x1400145c9  xor     [rbp+var_10], rax
0x1400145cd  call    cs:__imp_GetCurrentProcessId
0x1400145d3  mov     eax, eax
0x1400145d5  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400145d9  xor     [rbp+var_10], rax
0x1400145dd  call    cs:__imp_QueryPerformanceCounter
0x1400145e3  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400145e6  lea     rcx, [rbp+var_10]
0x1400145ea  shl     rax, 20h
0x1400145ee  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400145f2  xor     rax, [rbp+var_10]
0x1400145f6  xor     rax, rcx
0x1400145f9  mov     rcx, 0FFFFFFFFFFFFh
0x140014603  and     rax, rcx
0x140014606  mov     rcx, 2B992DDFA233h
0x140014610  cmp     rax, rbx
0x140014613  cmovz   rax, rcx
0x140014617  mov     cs:__security_cookie, rax
0x14001461e  mov     rbx, [rsp+30h+arg_10]
0x140014623  not     rax
0x140014626  mov     cs:__security_cookie_complement, rax
0x14001462d  add     rsp, 30h
0x140014631  pop     rbp
0x140014632  retn
```
