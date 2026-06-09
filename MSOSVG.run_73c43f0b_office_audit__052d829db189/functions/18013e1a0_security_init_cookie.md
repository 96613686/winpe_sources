# __security_init_cookie

- ea: `0x18013e1a0`
- end: `0x18013e24f`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18013d6c0`

## callees

- `0x18013e1a0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18013e1dd`
- `KERNEL32!GetCurrentThreadId` at `0x18013e1dd`
- `KERNEL32!QueryPerformanceCounter` at `0x18013e1f9`
- `KERNEL32!QueryPerformanceCounter` at `0x18013e1f9`
- `KERNEL32!GetCurrentProcessId` at `0x18013e1e9`
- `KERNEL32!GetCurrentProcessId` at `0x18013e1e9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18013e1cf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18013e1cf`

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
0x18013e1a0  mov     [rsp-8+arg_10], rbx
0x18013e1a5  push    rbp
0x18013e1a6  mov     rbp, rsp
0x18013e1a9  sub     rsp, 30h
0x18013e1ad  mov     rax, cs:__security_cookie
0x18013e1b4  mov     rbx, 2B992DDFA232h
0x18013e1be  cmp     rax, rbx
0x18013e1c1  jnz     short loc_18013E23A
0x18013e1c3  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18013e1c7  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18013e1cf  call    cs:__imp_GetSystemTimeAsFileTime
0x18013e1d5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18013e1d9  mov     [rbp+var_10], rax
0x18013e1dd  call    cs:__imp_GetCurrentThreadId
0x18013e1e3  mov     eax, eax
0x18013e1e5  xor     [rbp+var_10], rax
0x18013e1e9  call    cs:__imp_GetCurrentProcessId
0x18013e1ef  mov     eax, eax
0x18013e1f1  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18013e1f5  xor     [rbp+var_10], rax
0x18013e1f9  call    cs:__imp_QueryPerformanceCounter
0x18013e1ff  mov     eax, dword ptr [rbp+PerformanceCount]
0x18013e202  lea     rcx, [rbp+var_10]
0x18013e206  shl     rax, 20h
0x18013e20a  xor     rax, qword ptr [rbp+PerformanceCount]
0x18013e20e  xor     rax, [rbp+var_10]
0x18013e212  xor     rax, rcx
0x18013e215  mov     rcx, 0FFFFFFFFFFFFh
0x18013e21f  and     rax, rcx
0x18013e222  mov     rcx, 2B992DDFA233h
0x18013e22c  cmp     rax, rbx
0x18013e22f  cmovz   rax, rcx
0x18013e233  mov     cs:__security_cookie, rax
0x18013e23a  mov     rbx, [rsp+30h+arg_10]
0x18013e23f  not     rax
0x18013e242  mov     cs:__security_cookie_complement, rax
0x18013e249  add     rsp, 30h
0x18013e24d  pop     rbp
0x18013e24e  retn
```
