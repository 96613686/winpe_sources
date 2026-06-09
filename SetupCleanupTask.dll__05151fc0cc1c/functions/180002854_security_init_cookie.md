# __security_init_cookie

- ea: `0x180002854`
- end: `0x180002931`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002350`

## callees

- `0x180002854`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000289b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000289b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028a7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800028de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800028de`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800028c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000288d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000288d`

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
0x180002854  mov     [rsp-8+arg_18], rbx
0x180002859  push    rbp
0x18000285a  mov     rbp, rsp
0x18000285d  sub     rsp, 20h
0x180002861  xor     eax, eax
0x180002863  mov     rbx, 2B992DDFA232h
0x18000286d  mov     [rbp+arg_0], rax
0x180002871  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002875  mov     qword ptr [rbp+PerformanceCount], rax
0x180002879  mov     rax, cs:__security_cookie
0x180002880  cmp     rax, rbx
0x180002883  jnz     loc_18000291C
0x180002889  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000288d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002893  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002897  mov     [rbp+arg_0], rax
0x18000289b  call    cs:__imp_GetCurrentProcessId
0x1800028a1  mov     eax, eax
0x1800028a3  xor     [rbp+arg_0], rax
0x1800028a7  call    cs:__imp_GetCurrentThreadId
0x1800028ad  mov     eax, eax
0x1800028af  xor     [rbp+arg_0], rax
0x1800028b3  call    cs:__imp_GetTickCount
0x1800028b9  mov     eax, eax
0x1800028bb  shl     rax, 18h
0x1800028bf  xor     [rbp+arg_0], rax
0x1800028c3  call    cs:__imp_GetTickCount
0x1800028c9  mov     eax, eax
0x1800028cb  lea     rcx, [rbp+arg_0]
0x1800028cf  xor     rax, [rbp+arg_0]
0x1800028d3  xor     rax, rcx
0x1800028d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800028da  mov     [rbp+arg_0], rax
0x1800028de  call    cs:__imp_QueryPerformanceCounter
0x1800028e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800028e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800028f1  shl     rax, 20h
0x1800028f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800028f9  xor     rax, [rbp+arg_0]
0x1800028fd  and     rax, rcx
0x180002900  mov     rcx, rax
0x180002903  cmp     rax, rbx
0x180002906  jnz     short loc_180002915
0x180002908  mov     rax, 2B992DDFA233h
0x180002912  mov     rcx, rax
0x180002915  mov     cs:__security_cookie, rcx
0x18000291c  mov     rbx, [rsp+20h+arg_18]
0x180002921  not     rax
0x180002924  mov     cs:__security_cookie_complement, rax
0x18000292b  add     rsp, 20h
0x18000292f  pop     rbp
0x180002930  retn
```
