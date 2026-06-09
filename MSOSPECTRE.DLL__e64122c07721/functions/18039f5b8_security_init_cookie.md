# __security_init_cookie

- ea: `0x18039f5b8`
- end: `0x18039f667`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18039e560`

## callees

- `0x18039f5b8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18039f5f5`
- `KERNEL32!GetCurrentThreadId` at `0x18039f5f5`
- `KERNEL32!QueryPerformanceCounter` at `0x18039f611`
- `KERNEL32!QueryPerformanceCounter` at `0x18039f611`
- `KERNEL32!GetCurrentProcessId` at `0x18039f601`
- `KERNEL32!GetCurrentProcessId` at `0x18039f601`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18039f5e7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18039f5e7`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

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
0x18039f5b8  mov     [rsp-8+arg_10], rbx
0x18039f5bd  push    rbp
0x18039f5be  mov     rbp, rsp
0x18039f5c1  sub     rsp, 30h
0x18039f5c5  mov     rax, cs:__security_cookie
0x18039f5cc  mov     rbx, 2B992DDFA232h
0x18039f5d6  cmp     rax, rbx
0x18039f5d9  jnz     short loc_18039F652
0x18039f5db  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18039f5df  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18039f5e7  call    cs:__imp_GetSystemTimeAsFileTime
0x18039f5ed  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18039f5f1  mov     [rbp+var_10], rax
0x18039f5f5  call    cs:__imp_GetCurrentThreadId
0x18039f5fb  mov     eax, eax
0x18039f5fd  xor     [rbp+var_10], rax
0x18039f601  call    cs:__imp_GetCurrentProcessId
0x18039f607  mov     eax, eax
0x18039f609  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18039f60d  xor     [rbp+var_10], rax
0x18039f611  call    cs:__imp_QueryPerformanceCounter
0x18039f617  mov     eax, dword ptr [rbp+PerformanceCount]
0x18039f61a  lea     rcx, [rbp+var_10]
0x18039f61e  shl     rax, 20h
0x18039f622  xor     rax, qword ptr [rbp+PerformanceCount]
0x18039f626  xor     rax, [rbp+var_10]
0x18039f62a  xor     rax, rcx
0x18039f62d  mov     rcx, 0FFFFFFFFFFFFh
0x18039f637  and     rax, rcx
0x18039f63a  mov     rcx, 2B992DDFA233h
0x18039f644  cmp     rax, rbx
0x18039f647  cmovz   rax, rcx
0x18039f64b  mov     cs:__security_cookie, rax
0x18039f652  mov     rbx, [rsp+30h+arg_10]
0x18039f657  not     rax
0x18039f65a  mov     cs:__security_cookie_complement, rax
0x18039f661  add     rsp, 30h
0x18039f665  pop     rbp
0x18039f666  retn
```
