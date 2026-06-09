# __security_init_cookie

- ea: `0x180001f04`
- end: `0x180001fe1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001490`

## callees

- `0x180001f04`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180001f4b`
- `KERNEL32!GetCurrentProcessId` at `0x180001f4b`
- `KERNEL32!GetCurrentThreadId` at `0x180001f57`
- `KERNEL32!GetCurrentThreadId` at `0x180001f57`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001f3d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001f3d`
- `KERNEL32!GetTickCount` at `0x180001f63`
- `KERNEL32!GetTickCount` at `0x180001f73`
- `KERNEL32!GetTickCount` at `0x180001f63`
- `KERNEL32!GetTickCount` at `0x180001f73`
- `KERNEL32!QueryPerformanceCounter` at `0x180001f8e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001f8e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001f04  mov     [rsp-8+arg_18], rbx
0x180001f09  push    rbp
0x180001f0a  mov     rbp, rsp
0x180001f0d  sub     rsp, 20h
0x180001f11  xor     eax, eax
0x180001f13  mov     rbx, 2B992DDFA232h
0x180001f1d  mov     [rbp+arg_0], rax
0x180001f21  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f25  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f29  mov     rax, cs:__security_cookie
0x180001f30  cmp     rax, rbx
0x180001f33  jnz     loc_180001FCC
0x180001f39  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f3d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001f43  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001f47  mov     [rbp+arg_0], rax
0x180001f4b  call    cs:__imp_GetCurrentProcessId
0x180001f51  mov     eax, eax
0x180001f53  xor     [rbp+arg_0], rax
0x180001f57  call    cs:__imp_GetCurrentThreadId
0x180001f5d  mov     eax, eax
0x180001f5f  xor     [rbp+arg_0], rax
0x180001f63  call    cs:__imp_GetTickCount
0x180001f69  mov     eax, eax
0x180001f6b  shl     rax, 18h
0x180001f6f  xor     [rbp+arg_0], rax
0x180001f73  call    cs:__imp_GetTickCount
0x180001f79  mov     eax, eax
0x180001f7b  lea     rcx, [rbp+arg_0]
0x180001f7f  xor     rax, [rbp+arg_0]
0x180001f83  xor     rax, rcx
0x180001f86  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001f8a  mov     [rbp+arg_0], rax
0x180001f8e  call    cs:__imp_QueryPerformanceCounter
0x180001f94  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001f97  mov     rcx, 0FFFFFFFFFFFFh
0x180001fa1  shl     rax, 20h
0x180001fa5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001fa9  xor     rax, [rbp+arg_0]
0x180001fad  and     rax, rcx
0x180001fb0  mov     rcx, rax
0x180001fb3  cmp     rax, rbx
0x180001fb6  jnz     short loc_180001FC5
0x180001fb8  mov     rax, 2B992DDFA233h
0x180001fc2  mov     rcx, rax
0x180001fc5  mov     cs:__security_cookie, rcx
0x180001fcc  mov     rbx, [rsp+20h+arg_18]
0x180001fd1  not     rax
0x180001fd4  mov     cs:__security_cookie_complement, rax
0x180001fdb  add     rsp, 20h
0x180001fdf  pop     rbp
0x180001fe0  retn
```
