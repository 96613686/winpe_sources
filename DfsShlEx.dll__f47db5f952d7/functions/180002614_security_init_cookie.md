# __security_init_cookie

- ea: `0x180002614`
- end: `0x1800026f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d40`

## callees

- `0x180002614`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180002673`
- `KERNEL32!GetTickCount` at `0x180002683`
- `KERNEL32!GetTickCount` at `0x180002673`
- `KERNEL32!GetTickCount` at `0x180002683`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000264d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000264d`
- `KERNEL32!GetCurrentProcessId` at `0x18000265b`
- `KERNEL32!GetCurrentProcessId` at `0x18000265b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000269e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000269e`
- `KERNEL32!GetCurrentThreadId` at `0x180002667`
- `KERNEL32!GetCurrentThreadId` at `0x180002667`

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
0x180002614  mov     [rsp-8+arg_18], rbx
0x180002619  push    rbp
0x18000261a  mov     rbp, rsp
0x18000261d  sub     rsp, 20h
0x180002621  xor     eax, eax
0x180002623  mov     rbx, 2B992DDFA232h
0x18000262d  mov     [rbp+arg_0], rax
0x180002631  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002635  mov     qword ptr [rbp+PerformanceCount], rax
0x180002639  mov     rax, cs:__security_cookie
0x180002640  cmp     rax, rbx
0x180002643  jnz     loc_1800026DC
0x180002649  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000264d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002653  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002657  mov     [rbp+arg_0], rax
0x18000265b  call    cs:__imp_GetCurrentProcessId
0x180002661  mov     eax, eax
0x180002663  xor     [rbp+arg_0], rax
0x180002667  call    cs:__imp_GetCurrentThreadId
0x18000266d  mov     eax, eax
0x18000266f  xor     [rbp+arg_0], rax
0x180002673  call    cs:__imp_GetTickCount
0x180002679  mov     eax, eax
0x18000267b  shl     rax, 18h
0x18000267f  xor     [rbp+arg_0], rax
0x180002683  call    cs:__imp_GetTickCount
0x180002689  mov     eax, eax
0x18000268b  lea     rcx, [rbp+arg_0]
0x18000268f  xor     rax, [rbp+arg_0]
0x180002693  xor     rax, rcx
0x180002696  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000269a  mov     [rbp+arg_0], rax
0x18000269e  call    cs:__imp_QueryPerformanceCounter
0x1800026a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800026a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800026b1  shl     rax, 20h
0x1800026b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800026b9  xor     rax, [rbp+arg_0]
0x1800026bd  and     rax, rcx
0x1800026c0  mov     rcx, rax
0x1800026c3  cmp     rax, rbx
0x1800026c6  jnz     short loc_1800026D5
0x1800026c8  mov     rax, 2B992DDFA233h
0x1800026d2  mov     rcx, rax
0x1800026d5  mov     cs:__security_cookie, rcx
0x1800026dc  mov     rbx, [rsp+20h+arg_18]
0x1800026e1  not     rax
0x1800026e4  mov     cs:__security_cookie_complement, rax
0x1800026eb  add     rsp, 20h
0x1800026ef  pop     rbp
0x1800026f0  retn
```
