# __security_init_cookie

- ea: `0x18001904c`
- end: `0x1800190fb`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800188f0`

## callees

- `0x18001904c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180019089`
- `KERNEL32!GetCurrentThreadId` at `0x180019089`
- `KERNEL32!GetCurrentProcessId` at `0x180019095`
- `KERNEL32!GetCurrentProcessId` at `0x180019095`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001907b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001907b`
- `KERNEL32!QueryPerformanceCounter` at `0x1800190a5`
- `KERNEL32!QueryPerformanceCounter` at `0x1800190a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18001904c  mov     [rsp-8+arg_10], rbx
0x180019051  push    rbp
0x180019052  mov     rbp, rsp
0x180019055  sub     rsp, 30h
0x180019059  mov     rax, cs:__security_cookie
0x180019060  mov     rbx, 2B992DDFA232h
0x18001906a  cmp     rax, rbx
0x18001906d  jnz     short loc_1800190E6
0x18001906f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019073  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001907b  call    cs:__imp_GetSystemTimeAsFileTime
0x180019081  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180019085  mov     [rbp+var_10], rax
0x180019089  call    cs:__imp_GetCurrentThreadId
0x18001908f  mov     eax, eax
0x180019091  xor     [rbp+var_10], rax
0x180019095  call    cs:__imp_GetCurrentProcessId
0x18001909b  mov     eax, eax
0x18001909d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800190a1  xor     [rbp+var_10], rax
0x1800190a5  call    cs:__imp_QueryPerformanceCounter
0x1800190ab  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800190ae  lea     rcx, [rbp+var_10]
0x1800190b2  shl     rax, 20h
0x1800190b6  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800190ba  xor     rax, [rbp+var_10]
0x1800190be  xor     rax, rcx
0x1800190c1  mov     rcx, 0FFFFFFFFFFFFh
0x1800190cb  and     rax, rcx
0x1800190ce  mov     rcx, 2B992DDFA233h
0x1800190d8  cmp     rax, rbx
0x1800190db  cmovz   rax, rcx
0x1800190df  mov     cs:__security_cookie, rax
0x1800190e6  mov     rbx, [rsp+30h+arg_10]
0x1800190eb  not     rax
0x1800190ee  mov     cs:__security_cookie_complement, rax
0x1800190f5  add     rsp, 30h
0x1800190f9  pop     rbp
0x1800190fa  retn
```
