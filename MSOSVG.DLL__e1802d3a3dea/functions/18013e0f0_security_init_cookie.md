# __security_init_cookie

- ea: `0x18013e0f0`
- end: `0x18013e19f`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18013d610`

## callees

- `0x18013e0f0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18013e12d`
- `KERNEL32!GetCurrentThreadId` at `0x18013e12d`
- `KERNEL32!QueryPerformanceCounter` at `0x18013e149`
- `KERNEL32!QueryPerformanceCounter` at `0x18013e149`
- `KERNEL32!GetCurrentProcessId` at `0x18013e139`
- `KERNEL32!GetCurrentProcessId` at `0x18013e139`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18013e11f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18013e11f`

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
0x18013e0f0  mov     [rsp-8+arg_10], rbx
0x18013e0f5  push    rbp
0x18013e0f6  mov     rbp, rsp
0x18013e0f9  sub     rsp, 30h
0x18013e0fd  mov     rax, cs:__security_cookie
0x18013e104  mov     rbx, 2B992DDFA232h
0x18013e10e  cmp     rax, rbx
0x18013e111  jnz     short loc_18013E18A
0x18013e113  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18013e117  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18013e11f  call    cs:__imp_GetSystemTimeAsFileTime
0x18013e125  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18013e129  mov     [rbp+var_10], rax
0x18013e12d  call    cs:__imp_GetCurrentThreadId
0x18013e133  mov     eax, eax
0x18013e135  xor     [rbp+var_10], rax
0x18013e139  call    cs:__imp_GetCurrentProcessId
0x18013e13f  mov     eax, eax
0x18013e141  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18013e145  xor     [rbp+var_10], rax
0x18013e149  call    cs:__imp_QueryPerformanceCounter
0x18013e14f  mov     eax, dword ptr [rbp+PerformanceCount]
0x18013e152  lea     rcx, [rbp+var_10]
0x18013e156  shl     rax, 20h
0x18013e15a  xor     rax, qword ptr [rbp+PerformanceCount]
0x18013e15e  xor     rax, [rbp+var_10]
0x18013e162  xor     rax, rcx
0x18013e165  mov     rcx, 0FFFFFFFFFFFFh
0x18013e16f  and     rax, rcx
0x18013e172  mov     rcx, 2B992DDFA233h
0x18013e17c  cmp     rax, rbx
0x18013e17f  cmovz   rax, rcx
0x18013e183  mov     cs:__security_cookie, rax
0x18013e18a  mov     rbx, [rsp+30h+arg_10]
0x18013e18f  not     rax
0x18013e192  mov     cs:__security_cookie_complement, rax
0x18013e199  add     rsp, 30h
0x18013e19d  pop     rbp
0x18013e19e  retn
```
