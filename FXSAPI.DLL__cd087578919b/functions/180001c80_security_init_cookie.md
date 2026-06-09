# __security_init_cookie

- ea: `0x180001c80`
- end: `0x180001d5d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x180001c80`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001cb9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001cb9`
- `KERNEL32!GetCurrentProcessId` at `0x180001cc7`
- `KERNEL32!GetCurrentProcessId` at `0x180001cc7`
- `KERNEL32!QueryPerformanceCounter` at `0x180001d0a`
- `KERNEL32!QueryPerformanceCounter` at `0x180001d0a`
- `KERNEL32!GetTickCount` at `0x180001cdf`
- `KERNEL32!GetTickCount` at `0x180001cef`
- `KERNEL32!GetTickCount` at `0x180001cdf`
- `KERNEL32!GetTickCount` at `0x180001cef`
- `KERNEL32!GetCurrentThreadId` at `0x180001cd3`
- `KERNEL32!GetCurrentThreadId` at `0x180001cd3`

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
0x180001c80  mov     [rsp-8+arg_18], rbx
0x180001c85  push    rbp
0x180001c86  mov     rbp, rsp
0x180001c89  sub     rsp, 20h
0x180001c8d  xor     eax, eax
0x180001c8f  mov     rbx, 2B992DDFA232h
0x180001c99  mov     [rbp+arg_0], rax
0x180001c9d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ca1  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ca5  mov     rax, cs:__security_cookie
0x180001cac  cmp     rax, rbx
0x180001caf  jnz     loc_180001D48
0x180001cb5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001cb9  call    cs:__imp_GetSystemTimeAsFileTime
0x180001cbf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001cc3  mov     [rbp+arg_0], rax
0x180001cc7  call    cs:__imp_GetCurrentProcessId
0x180001ccd  mov     eax, eax
0x180001ccf  xor     [rbp+arg_0], rax
0x180001cd3  call    cs:__imp_GetCurrentThreadId
0x180001cd9  mov     eax, eax
0x180001cdb  xor     [rbp+arg_0], rax
0x180001cdf  call    cs:__imp_GetTickCount
0x180001ce5  mov     eax, eax
0x180001ce7  shl     rax, 18h
0x180001ceb  xor     [rbp+arg_0], rax
0x180001cef  call    cs:__imp_GetTickCount
0x180001cf5  mov     eax, eax
0x180001cf7  lea     rcx, [rbp+arg_0]
0x180001cfb  xor     rax, [rbp+arg_0]
0x180001cff  xor     rax, rcx
0x180001d02  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001d06  mov     [rbp+arg_0], rax
0x180001d0a  call    cs:__imp_QueryPerformanceCounter
0x180001d10  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001d13  mov     rcx, 0FFFFFFFFFFFFh
0x180001d1d  shl     rax, 20h
0x180001d21  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001d25  xor     rax, [rbp+arg_0]
0x180001d29  and     rax, rcx
0x180001d2c  mov     rcx, rax
0x180001d2f  cmp     rax, rbx
0x180001d32  jnz     short loc_180001D41
0x180001d34  mov     rax, 2B992DDFA233h
0x180001d3e  mov     rcx, rax
0x180001d41  mov     cs:__security_cookie, rcx
0x180001d48  mov     rbx, [rsp+20h+arg_18]
0x180001d4d  not     rax
0x180001d50  mov     cs:__security_cookie_complement, rax
0x180001d57  add     rsp, 20h
0x180001d5b  pop     rbp
0x180001d5c  retn
```
