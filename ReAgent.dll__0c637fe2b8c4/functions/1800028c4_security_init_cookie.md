# __security_init_cookie

- ea: `0x1800028c4`
- end: `0x1800029a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800023b0`

## callees

- `0x1800028c4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000294e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000294e`
- `KERNEL32!GetCurrentProcessId` at `0x18000290b`
- `KERNEL32!GetCurrentProcessId` at `0x18000290b`
- `KERNEL32!GetCurrentThreadId` at `0x180002917`
- `KERNEL32!GetCurrentThreadId` at `0x180002917`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800028fd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800028fd`
- `KERNEL32!GetTickCount` at `0x180002923`
- `KERNEL32!GetTickCount` at `0x180002933`
- `KERNEL32!GetTickCount` at `0x180002923`
- `KERNEL32!GetTickCount` at `0x180002933`

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
0x1800028c4  mov     [rsp-8+arg_18], rbx
0x1800028c9  push    rbp
0x1800028ca  mov     rbp, rsp
0x1800028cd  sub     rsp, 20h
0x1800028d1  xor     eax, eax
0x1800028d3  mov     rbx, 2B992DDFA232h
0x1800028dd  mov     [rbp+arg_0], rax
0x1800028e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800028e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800028e9  mov     rax, cs:__security_cookie
0x1800028f0  cmp     rax, rbx
0x1800028f3  jnz     loc_18000298C
0x1800028f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800028fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002903  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002907  mov     [rbp+arg_0], rax
0x18000290b  call    cs:__imp_GetCurrentProcessId
0x180002911  mov     eax, eax
0x180002913  xor     [rbp+arg_0], rax
0x180002917  call    cs:__imp_GetCurrentThreadId
0x18000291d  mov     eax, eax
0x18000291f  xor     [rbp+arg_0], rax
0x180002923  call    cs:__imp_GetTickCount
0x180002929  mov     eax, eax
0x18000292b  shl     rax, 18h
0x18000292f  xor     [rbp+arg_0], rax
0x180002933  call    cs:__imp_GetTickCount
0x180002939  mov     eax, eax
0x18000293b  lea     rcx, [rbp+arg_0]
0x18000293f  xor     rax, [rbp+arg_0]
0x180002943  xor     rax, rcx
0x180002946  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000294a  mov     [rbp+arg_0], rax
0x18000294e  call    cs:__imp_QueryPerformanceCounter
0x180002954  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002957  mov     rcx, 0FFFFFFFFFFFFh
0x180002961  shl     rax, 20h
0x180002965  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002969  xor     rax, [rbp+arg_0]
0x18000296d  and     rax, rcx
0x180002970  mov     rcx, rax
0x180002973  cmp     rax, rbx
0x180002976  jnz     short loc_180002985
0x180002978  mov     rax, 2B992DDFA233h
0x180002982  mov     rcx, rax
0x180002985  mov     cs:__security_cookie, rcx
0x18000298c  mov     rbx, [rsp+20h+arg_18]
0x180002991  not     rax
0x180002994  mov     cs:__security_cookie_complement, rax
0x18000299b  add     rsp, 20h
0x18000299f  pop     rbp
0x1800029a0  retn
```
