# __security_init_cookie

- ea: `0x140001080`
- end: `0x14000112f`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001ab0`

## callees

- `0x140001080`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1400010c9`
- `KERNEL32!GetCurrentProcessId` at `0x1400010c9`
- `KERNEL32!GetCurrentThreadId` at `0x1400010bd`
- `KERNEL32!GetCurrentThreadId` at `0x1400010bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400010af`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400010af`
- `KERNEL32!QueryPerformanceCounter` at `0x1400010d9`
- `KERNEL32!QueryPerformanceCounter` at `0x1400010d9`

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
0x140001080  mov     [rsp-8+arg_10], rbx
0x140001085  push    rbp
0x140001086  mov     rbp, rsp
0x140001089  sub     rsp, 30h
0x14000108d  mov     rax, cs:__security_cookie
0x140001094  mov     rbx, 2B992DDFA232h
0x14000109e  cmp     rax, rbx
0x1400010a1  jnz     short loc_14000111A
0x1400010a3  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400010a7  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1400010af  call    cs:__imp_GetSystemTimeAsFileTime
0x1400010b5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400010b9  mov     [rbp+var_10], rax
0x1400010bd  call    cs:__imp_GetCurrentThreadId
0x1400010c3  mov     eax, eax
0x1400010c5  xor     [rbp+var_10], rax
0x1400010c9  call    cs:__imp_GetCurrentProcessId
0x1400010cf  mov     eax, eax
0x1400010d1  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400010d5  xor     [rbp+var_10], rax
0x1400010d9  call    cs:__imp_QueryPerformanceCounter
0x1400010df  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400010e2  lea     rcx, [rbp+var_10]
0x1400010e6  shl     rax, 20h
0x1400010ea  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400010ee  xor     rax, [rbp+var_10]
0x1400010f2  xor     rax, rcx
0x1400010f5  mov     rcx, 0FFFFFFFFFFFFh
0x1400010ff  and     rax, rcx
0x140001102  mov     rcx, 2B992DDFA233h
0x14000110c  cmp     rax, rbx
0x14000110f  cmovz   rax, rcx
0x140001113  mov     cs:__security_cookie, rax
0x14000111a  mov     rbx, [rsp+30h+arg_10]
0x14000111f  not     rax
0x140001122  mov     cs:__security_cookie_complement, rax
0x140001129  add     rsp, 30h
0x14000112d  pop     rbp
0x14000112e  retn
```
