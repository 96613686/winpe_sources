# __security_init_cookie

- ea: `0x180002844`
- end: `0x180002921`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002300`

## callees

- `0x180002844`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800028ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800028ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000288b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000288b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000287d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000287d`

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
0x180002844  mov     [rsp-8+arg_18], rbx
0x180002849  push    rbp
0x18000284a  mov     rbp, rsp
0x18000284d  sub     rsp, 20h
0x180002851  xor     eax, eax
0x180002853  mov     rbx, 2B992DDFA232h
0x18000285d  mov     [rbp+arg_0], rax
0x180002861  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002865  mov     qword ptr [rbp+PerformanceCount], rax
0x180002869  mov     rax, cs:__security_cookie
0x180002870  cmp     rax, rbx
0x180002873  jnz     loc_18000290C
0x180002879  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000287d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002883  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002887  mov     [rbp+arg_0], rax
0x18000288b  call    cs:__imp_GetCurrentProcessId
0x180002891  mov     eax, eax
0x180002893  xor     [rbp+arg_0], rax
0x180002897  call    cs:__imp_GetCurrentThreadId
0x18000289d  mov     eax, eax
0x18000289f  xor     [rbp+arg_0], rax
0x1800028a3  call    cs:__imp_GetTickCount
0x1800028a9  mov     eax, eax
0x1800028ab  shl     rax, 18h
0x1800028af  xor     [rbp+arg_0], rax
0x1800028b3  call    cs:__imp_GetTickCount
0x1800028b9  mov     eax, eax
0x1800028bb  lea     rcx, [rbp+arg_0]
0x1800028bf  xor     rax, [rbp+arg_0]
0x1800028c3  xor     rax, rcx
0x1800028c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800028ca  mov     [rbp+arg_0], rax
0x1800028ce  call    cs:__imp_QueryPerformanceCounter
0x1800028d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800028d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800028e1  shl     rax, 20h
0x1800028e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800028e9  xor     rax, [rbp+arg_0]
0x1800028ed  and     rax, rcx
0x1800028f0  mov     rcx, rax
0x1800028f3  cmp     rax, rbx
0x1800028f6  jnz     short loc_180002905
0x1800028f8  mov     rax, 2B992DDFA233h
0x180002902  mov     rcx, rax
0x180002905  mov     cs:__security_cookie, rcx
0x18000290c  mov     rbx, [rsp+20h+arg_18]
0x180002911  not     rax
0x180002914  mov     cs:__security_cookie_complement, rax
0x18000291b  add     rsp, 20h
0x18000291f  pop     rbp
0x180002920  retn
```
