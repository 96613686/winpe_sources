# __security_init_cookie

- ea: `0x1800029a0`
- end: `0x180002a4f`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800579d0`

## callees

- `0x1800029a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800029dd`
- `KERNEL32!GetCurrentThreadId` at `0x1800029dd`
- `KERNEL32!GetCurrentProcessId` at `0x1800029e9`
- `KERNEL32!GetCurrentProcessId` at `0x1800029e9`
- `KERNEL32!QueryPerformanceCounter` at `0x1800029f9`
- `KERNEL32!QueryPerformanceCounter` at `0x1800029f9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800029cf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800029cf`

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
0x1800029a0  mov     [rsp-8+arg_10], rbx
0x1800029a5  push    rbp
0x1800029a6  mov     rbp, rsp
0x1800029a9  sub     rsp, 30h
0x1800029ad  mov     rax, cs:__security_cookie
0x1800029b4  mov     rbx, 2B992DDFA232h
0x1800029be  cmp     rax, rbx
0x1800029c1  jnz     short loc_180002A3A
0x1800029c3  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800029c7  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800029cf  call    cs:__imp_GetSystemTimeAsFileTime
0x1800029d5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800029d9  mov     [rbp+var_10], rax
0x1800029dd  call    cs:__imp_GetCurrentThreadId
0x1800029e3  mov     eax, eax
0x1800029e5  xor     [rbp+var_10], rax
0x1800029e9  call    cs:__imp_GetCurrentProcessId
0x1800029ef  mov     eax, eax
0x1800029f1  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800029f5  xor     [rbp+var_10], rax
0x1800029f9  call    cs:__imp_QueryPerformanceCounter
0x1800029ff  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002a02  lea     rcx, [rbp+var_10]
0x180002a06  shl     rax, 20h
0x180002a0a  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002a0e  xor     rax, [rbp+var_10]
0x180002a12  xor     rax, rcx
0x180002a15  mov     rcx, 0FFFFFFFFFFFFh
0x180002a1f  and     rax, rcx
0x180002a22  mov     rcx, 2B992DDFA233h
0x180002a2c  cmp     rax, rbx
0x180002a2f  cmovz   rax, rcx
0x180002a33  mov     cs:__security_cookie, rax
0x180002a3a  mov     rbx, [rsp+30h+arg_10]
0x180002a3f  not     rax
0x180002a42  mov     cs:__security_cookie_complement, rax
0x180002a49  add     rsp, 30h
0x180002a4d  pop     rbp
0x180002a4e  retn
```
