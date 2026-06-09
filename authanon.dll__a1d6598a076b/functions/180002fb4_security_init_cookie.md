# __security_init_cookie

- ea: `0x180002fb4`
- end: `0x180003091`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002c40`

## callees

- `0x180002fb4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ffb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003007`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000303e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000303e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002fed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002fed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003013`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003023`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003013`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003023`

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
0x180002fb4  mov     [rsp-8+arg_18], rbx
0x180002fb9  push    rbp
0x180002fba  mov     rbp, rsp
0x180002fbd  sub     rsp, 20h
0x180002fc1  xor     eax, eax
0x180002fc3  mov     rbx, 2B992DDFA232h
0x180002fcd  mov     [rbp+arg_0], rax
0x180002fd1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002fd5  mov     qword ptr [rbp+PerformanceCount], rax
0x180002fd9  mov     rax, cs:__security_cookie
0x180002fe0  cmp     rax, rbx
0x180002fe3  jnz     loc_18000307C
0x180002fe9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002fed  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ff3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002ff7  mov     [rbp+arg_0], rax
0x180002ffb  call    cs:__imp_GetCurrentProcessId
0x180003001  mov     eax, eax
0x180003003  xor     [rbp+arg_0], rax
0x180003007  call    cs:__imp_GetCurrentThreadId
0x18000300d  mov     eax, eax
0x18000300f  xor     [rbp+arg_0], rax
0x180003013  call    cs:__imp_GetTickCount
0x180003019  mov     eax, eax
0x18000301b  shl     rax, 18h
0x18000301f  xor     [rbp+arg_0], rax
0x180003023  call    cs:__imp_GetTickCount
0x180003029  mov     eax, eax
0x18000302b  lea     rcx, [rbp+arg_0]
0x18000302f  xor     rax, [rbp+arg_0]
0x180003033  xor     rax, rcx
0x180003036  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000303a  mov     [rbp+arg_0], rax
0x18000303e  call    cs:__imp_QueryPerformanceCounter
0x180003044  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003047  mov     rcx, 0FFFFFFFFFFFFh
0x180003051  shl     rax, 20h
0x180003055  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003059  xor     rax, [rbp+arg_0]
0x18000305d  and     rax, rcx
0x180003060  mov     rcx, rax
0x180003063  cmp     rax, rbx
0x180003066  jnz     short loc_180003075
0x180003068  mov     rax, 2B992DDFA233h
0x180003072  mov     rcx, rax
0x180003075  mov     cs:__security_cookie, rcx
0x18000307c  mov     rbx, [rsp+20h+arg_18]
0x180003081  not     rax
0x180003084  mov     cs:__security_cookie_complement, rax
0x18000308b  add     rsp, 20h
0x18000308f  pop     rbp
0x180003090  retn
```
