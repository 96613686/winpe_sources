# __security_init_cookie

- ea: `0x180001560`
- end: `0x18000160c`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001470`

## callees

- `0x180001560`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000158c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000158c`
- `KERNEL32!GetCurrentThreadId` at `0x18000159a`
- `KERNEL32!GetCurrentThreadId` at `0x18000159a`
- `KERNEL32!GetCurrentProcessId` at `0x1800015a6`
- `KERNEL32!GetCurrentProcessId` at `0x1800015a6`
- `KERNEL32!QueryPerformanceCounter` at `0x1800015b6`
- `KERNEL32!QueryPerformanceCounter` at `0x1800015b6`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

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
0x180001560  mov     [rsp-8+arg_18], rbx
0x180001565  push    rbp
0x180001566  mov     rbp, rsp
0x180001569  sub     rsp, 20h
0x18000156d  mov     rax, cs:__security_cookie
0x180001574  mov     rbx, 2B992DDFA232h
0x18000157e  cmp     rax, rbx
0x180001581  jnz     short loc_1800015F7
0x180001583  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001588  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000158c  call    cs:__imp_GetSystemTimeAsFileTime
0x180001592  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001596  mov     [rbp+arg_0], rax
0x18000159a  call    cs:__imp_GetCurrentThreadId
0x1800015a0  mov     eax, eax
0x1800015a2  xor     [rbp+arg_0], rax
0x1800015a6  call    cs:__imp_GetCurrentProcessId
0x1800015ac  mov     eax, eax
0x1800015ae  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800015b2  xor     [rbp+arg_0], rax
0x1800015b6  call    cs:__imp_QueryPerformanceCounter
0x1800015bc  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800015bf  lea     rcx, [rbp+arg_0]
0x1800015c3  shl     rax, 20h
0x1800015c7  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800015cb  xor     rax, [rbp+arg_0]
0x1800015cf  xor     rax, rcx
0x1800015d2  mov     rcx, 0FFFFFFFFFFFFh
0x1800015dc  and     rax, rcx
0x1800015df  mov     rcx, 2B992DDFA233h
0x1800015e9  cmp     rax, rbx
0x1800015ec  cmovz   rax, rcx
0x1800015f0  mov     cs:__security_cookie, rax
0x1800015f7  mov     rbx, [rsp+20h+arg_18]
0x1800015fc  not     rax
0x1800015ff  mov     cs:__security_cookie_complement, rax
0x180001606  add     rsp, 20h
0x18000160a  pop     rbp
0x18000160b  retn
```
