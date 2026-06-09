# __security_init_cookie

- ea: `0x1800026a4`
- end: `0x180002781`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e10`

## callees

- `0x1800026a4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180002703`
- `KERNEL32!GetTickCount` at `0x180002713`
- `KERNEL32!GetTickCount` at `0x180002703`
- `KERNEL32!GetTickCount` at `0x180002713`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800026dd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800026dd`
- `KERNEL32!GetCurrentThreadId` at `0x1800026f7`
- `KERNEL32!GetCurrentThreadId` at `0x1800026f7`
- `KERNEL32!GetCurrentProcessId` at `0x1800026eb`
- `KERNEL32!GetCurrentProcessId` at `0x1800026eb`
- `KERNEL32!QueryPerformanceCounter` at `0x18000272e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000272e`

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
0x1800026a4  mov     [rsp-8+arg_18], rbx
0x1800026a9  push    rbp
0x1800026aa  mov     rbp, rsp
0x1800026ad  sub     rsp, 20h
0x1800026b1  xor     eax, eax
0x1800026b3  mov     rbx, 2B992DDFA232h
0x1800026bd  mov     [rbp+arg_0], rax
0x1800026c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800026c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800026c9  mov     rax, cs:__security_cookie
0x1800026d0  cmp     rax, rbx
0x1800026d3  jnz     loc_18000276C
0x1800026d9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800026dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800026e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800026e7  mov     [rbp+arg_0], rax
0x1800026eb  call    cs:__imp_GetCurrentProcessId
0x1800026f1  mov     eax, eax
0x1800026f3  xor     [rbp+arg_0], rax
0x1800026f7  call    cs:__imp_GetCurrentThreadId
0x1800026fd  mov     eax, eax
0x1800026ff  xor     [rbp+arg_0], rax
0x180002703  call    cs:__imp_GetTickCount
0x180002709  mov     eax, eax
0x18000270b  shl     rax, 18h
0x18000270f  xor     [rbp+arg_0], rax
0x180002713  call    cs:__imp_GetTickCount
0x180002719  mov     eax, eax
0x18000271b  lea     rcx, [rbp+arg_0]
0x18000271f  xor     rax, [rbp+arg_0]
0x180002723  xor     rax, rcx
0x180002726  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000272a  mov     [rbp+arg_0], rax
0x18000272e  call    cs:__imp_QueryPerformanceCounter
0x180002734  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002737  mov     rcx, 0FFFFFFFFFFFFh
0x180002741  shl     rax, 20h
0x180002745  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002749  xor     rax, [rbp+arg_0]
0x18000274d  and     rax, rcx
0x180002750  mov     rcx, rax
0x180002753  cmp     rax, rbx
0x180002756  jnz     short loc_180002765
0x180002758  mov     rax, 2B992DDFA233h
0x180002762  mov     rcx, rax
0x180002765  mov     cs:__security_cookie, rcx
0x18000276c  mov     rbx, [rsp+20h+arg_18]
0x180002771  not     rax
0x180002774  mov     cs:__security_cookie_complement, rax
0x18000277b  add     rsp, 20h
0x18000277f  pop     rbp
0x180002780  retn
```
