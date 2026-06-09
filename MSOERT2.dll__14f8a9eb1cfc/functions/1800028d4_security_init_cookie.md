# __security_init_cookie

- ea: `0x1800028d4`
- end: `0x1800029b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002250`

## callees

- `0x1800028d4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000295e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000295e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000290d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000290d`
- `KERNEL32!GetTickCount` at `0x180002933`
- `KERNEL32!GetTickCount` at `0x180002943`
- `KERNEL32!GetTickCount` at `0x180002933`
- `KERNEL32!GetTickCount` at `0x180002943`
- `KERNEL32!GetCurrentThreadId` at `0x180002927`
- `KERNEL32!GetCurrentThreadId` at `0x180002927`
- `KERNEL32!GetCurrentProcessId` at `0x18000291b`
- `KERNEL32!GetCurrentProcessId` at `0x18000291b`

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
0x1800028d4  mov     [rsp-8+arg_18], rbx
0x1800028d9  push    rbp
0x1800028da  mov     rbp, rsp
0x1800028dd  sub     rsp, 20h
0x1800028e1  xor     eax, eax
0x1800028e3  mov     rbx, 2B992DDFA232h
0x1800028ed  mov     [rbp+arg_0], rax
0x1800028f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800028f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800028f9  mov     rax, cs:__security_cookie
0x180002900  cmp     rax, rbx
0x180002903  jnz     loc_18000299C
0x180002909  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000290d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002913  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002917  mov     [rbp+arg_0], rax
0x18000291b  call    cs:__imp_GetCurrentProcessId
0x180002921  mov     eax, eax
0x180002923  xor     [rbp+arg_0], rax
0x180002927  call    cs:__imp_GetCurrentThreadId
0x18000292d  mov     eax, eax
0x18000292f  xor     [rbp+arg_0], rax
0x180002933  call    cs:__imp_GetTickCount
0x180002939  mov     eax, eax
0x18000293b  shl     rax, 18h
0x18000293f  xor     [rbp+arg_0], rax
0x180002943  call    cs:__imp_GetTickCount
0x180002949  mov     eax, eax
0x18000294b  lea     rcx, [rbp+arg_0]
0x18000294f  xor     rax, [rbp+arg_0]
0x180002953  xor     rax, rcx
0x180002956  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000295a  mov     [rbp+arg_0], rax
0x18000295e  call    cs:__imp_QueryPerformanceCounter
0x180002964  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002967  mov     rcx, 0FFFFFFFFFFFFh
0x180002971  shl     rax, 20h
0x180002975  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002979  xor     rax, [rbp+arg_0]
0x18000297d  and     rax, rcx
0x180002980  mov     rcx, rax
0x180002983  cmp     rax, rbx
0x180002986  jnz     short loc_180002995
0x180002988  mov     rax, 2B992DDFA233h
0x180002992  mov     rcx, rax
0x180002995  mov     cs:__security_cookie, rcx
0x18000299c  mov     rbx, [rsp+20h+arg_18]
0x1800029a1  not     rax
0x1800029a4  mov     cs:__security_cookie_complement, rax
0x1800029ab  add     rsp, 20h
0x1800029af  pop     rbp
0x1800029b0  retn
```
