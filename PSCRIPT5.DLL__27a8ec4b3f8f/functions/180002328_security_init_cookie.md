# __security_init_cookie

- ea: `0x180002328`
- end: `0x1800023dd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ed0`

## callees

- `0x180002328`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000235d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000235d`
- `KERNEL32!QueryPerformanceCounter` at `0x180002387`
- `KERNEL32!QueryPerformanceCounter` at `0x180002387`
- `KERNEL32!GetCurrentProcessId` at `0x180002377`
- `KERNEL32!GetCurrentProcessId` at `0x180002377`
- `KERNEL32!GetCurrentThreadId` at `0x18000236b`
- `KERNEL32!GetCurrentThreadId` at `0x18000236b`

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
0x180002328  mov     [rsp-8+arg_10], rbx
0x18000232d  push    rbp
0x18000232e  mov     rbp, rsp
0x180002331  sub     rsp, 30h
0x180002335  mov     rax, cs:__security_cookie
0x18000233c  mov     rbx, 2B992DDFA232h
0x180002346  cmp     rax, rbx
0x180002349  jnz     short loc_1800023C8
0x18000234b  xor     eax, eax
0x18000234d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002351  mov     [rbp+var_10], rax
0x180002355  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002359  mov     qword ptr [rbp+PerformanceCount], rax
0x18000235d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002363  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002367  mov     [rbp+var_10], rax
0x18000236b  call    cs:__imp_GetCurrentThreadId
0x180002371  mov     eax, eax
0x180002373  xor     [rbp+var_10], rax
0x180002377  call    cs:__imp_GetCurrentProcessId
0x18000237d  mov     eax, eax
0x18000237f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002383  xor     [rbp+var_10], rax
0x180002387  call    cs:__imp_QueryPerformanceCounter
0x18000238d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002390  lea     rcx, [rbp+var_10]
0x180002394  shl     rax, 20h
0x180002398  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000239c  xor     rax, [rbp+var_10]
0x1800023a0  xor     rax, rcx
0x1800023a3  mov     rcx, 0FFFFFFFFFFFFh
0x1800023ad  and     rax, rcx
0x1800023b0  mov     rcx, 2B992DDFA233h
0x1800023ba  cmp     rax, rbx
0x1800023bd  cmovz   rax, rcx
0x1800023c1  mov     cs:__security_cookie, rax
0x1800023c8  mov     rbx, [rsp+30h+arg_10]
0x1800023cd  not     rax
0x1800023d0  mov     cs:__security_cookie_complement, rax
0x1800023d7  add     rsp, 30h
0x1800023db  pop     rbp
0x1800023dc  retn
```
