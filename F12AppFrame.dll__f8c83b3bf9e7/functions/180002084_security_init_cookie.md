# __security_init_cookie

- ea: `0x180002084`
- end: `0x180002139`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800017a0`

## callees

- `0x180002084`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800020c7`
- `KERNEL32!GetCurrentThreadId` at `0x1800020c7`
- `KERNEL32!GetCurrentProcessId` at `0x1800020d3`
- `KERNEL32!GetCurrentProcessId` at `0x1800020d3`
- `KERNEL32!QueryPerformanceCounter` at `0x1800020e3`
- `KERNEL32!QueryPerformanceCounter` at `0x1800020e3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800020b9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800020b9`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
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
0x180002084  mov     [rsp-8+arg_10], rbx
0x180002089  push    rbp
0x18000208a  mov     rbp, rsp
0x18000208d  sub     rsp, 30h
0x180002091  mov     rax, cs:__security_cookie
0x180002098  mov     rbx, 2B992DDFA232h
0x1800020a2  cmp     rax, rbx
0x1800020a5  jnz     short loc_180002124
0x1800020a7  xor     eax, eax
0x1800020a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800020ad  mov     [rbp+var_10], rax
0x1800020b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800020b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800020b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800020bf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800020c3  mov     [rbp+var_10], rax
0x1800020c7  call    cs:__imp_GetCurrentThreadId
0x1800020cd  mov     eax, eax
0x1800020cf  xor     [rbp+var_10], rax
0x1800020d3  call    cs:__imp_GetCurrentProcessId
0x1800020d9  mov     eax, eax
0x1800020db  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800020df  xor     [rbp+var_10], rax
0x1800020e3  call    cs:__imp_QueryPerformanceCounter
0x1800020e9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800020ec  lea     rcx, [rbp+var_10]
0x1800020f0  shl     rax, 20h
0x1800020f4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800020f8  xor     rax, [rbp+var_10]
0x1800020fc  xor     rax, rcx
0x1800020ff  mov     rcx, 0FFFFFFFFFFFFh
0x180002109  and     rax, rcx
0x18000210c  mov     rcx, 2B992DDFA233h
0x180002116  cmp     rax, rbx
0x180002119  cmovz   rax, rcx
0x18000211d  mov     cs:__security_cookie, rax
0x180002124  mov     rbx, [rsp+30h+arg_10]
0x180002129  not     rax
0x18000212c  mov     cs:__security_cookie_complement, rax
0x180002133  add     rsp, 30h
0x180002137  pop     rbp
0x180002138  retn
```
