# __security_init_cookie

- ea: `0x180002fdc`
- end: `0x18000308b`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b70`

## callees

- `0x180002fdc`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180003035`
- `KERNEL32!QueryPerformanceCounter` at `0x180003035`
- `KERNEL32!GetCurrentProcessId` at `0x180003025`
- `KERNEL32!GetCurrentProcessId` at `0x180003025`
- `KERNEL32!GetCurrentThreadId` at `0x180003019`
- `KERNEL32!GetCurrentThreadId` at `0x180003019`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000300b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000300b`

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
0x180002fdc  mov     [rsp-8+arg_10], rbx
0x180002fe1  push    rbp
0x180002fe2  mov     rbp, rsp
0x180002fe5  sub     rsp, 30h
0x180002fe9  mov     rax, cs:__security_cookie
0x180002ff0  mov     rbx, 2B992DDFA232h
0x180002ffa  cmp     rax, rbx
0x180002ffd  jnz     short loc_180003076
0x180002fff  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003003  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000300b  call    cs:__imp_GetSystemTimeAsFileTime
0x180003011  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003015  mov     [rbp+var_10], rax
0x180003019  call    cs:__imp_GetCurrentThreadId
0x18000301f  mov     eax, eax
0x180003021  xor     [rbp+var_10], rax
0x180003025  call    cs:__imp_GetCurrentProcessId
0x18000302b  mov     eax, eax
0x18000302d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003031  xor     [rbp+var_10], rax
0x180003035  call    cs:__imp_QueryPerformanceCounter
0x18000303b  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000303e  lea     rcx, [rbp+var_10]
0x180003042  shl     rax, 20h
0x180003046  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000304a  xor     rax, [rbp+var_10]
0x18000304e  xor     rax, rcx
0x180003051  mov     rcx, 0FFFFFFFFFFFFh
0x18000305b  and     rax, rcx
0x18000305e  mov     rcx, 2B992DDFA233h
0x180003068  cmp     rax, rbx
0x18000306b  cmovz   rax, rcx
0x18000306f  mov     cs:__security_cookie, rax
0x180003076  mov     rbx, [rsp+30h+arg_10]
0x18000307b  not     rax
0x18000307e  mov     cs:__security_cookie_complement, rax
0x180003085  add     rsp, 30h
0x180003089  pop     rbp
0x18000308a  retn
```
