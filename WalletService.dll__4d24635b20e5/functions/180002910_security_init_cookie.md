# __security_init_cookie

- ea: `0x180002910`
- end: `0x1800029ed`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800024c0`

## callees

- `0x180002910`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002963`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002957`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002957`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000299a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000299a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002949`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002949`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000296f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000297f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000296f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000297f`

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
0x180002910  mov     [rsp-8+arg_18], rbx
0x180002915  push    rbp
0x180002916  mov     rbp, rsp
0x180002919  sub     rsp, 20h
0x18000291d  xor     eax, eax
0x18000291f  mov     rbx, 2B992DDFA232h
0x180002929  mov     [rbp+arg_0], rax
0x18000292d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002931  mov     qword ptr [rbp+PerformanceCount], rax
0x180002935  mov     rax, cs:__security_cookie
0x18000293c  cmp     rax, rbx
0x18000293f  jnz     loc_1800029D8
0x180002945  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002949  call    cs:__imp_GetSystemTimeAsFileTime
0x18000294f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002953  mov     [rbp+arg_0], rax
0x180002957  call    cs:__imp_GetCurrentProcessId
0x18000295d  mov     eax, eax
0x18000295f  xor     [rbp+arg_0], rax
0x180002963  call    cs:__imp_GetCurrentThreadId
0x180002969  mov     eax, eax
0x18000296b  xor     [rbp+arg_0], rax
0x18000296f  call    cs:__imp_GetTickCount
0x180002975  mov     eax, eax
0x180002977  shl     rax, 18h
0x18000297b  xor     [rbp+arg_0], rax
0x18000297f  call    cs:__imp_GetTickCount
0x180002985  mov     eax, eax
0x180002987  lea     rcx, [rbp+arg_0]
0x18000298b  xor     rax, [rbp+arg_0]
0x18000298f  xor     rax, rcx
0x180002992  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002996  mov     [rbp+arg_0], rax
0x18000299a  call    cs:__imp_QueryPerformanceCounter
0x1800029a0  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800029a3  mov     rcx, 0FFFFFFFFFFFFh
0x1800029ad  shl     rax, 20h
0x1800029b1  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800029b5  xor     rax, [rbp+arg_0]
0x1800029b9  and     rax, rcx
0x1800029bc  mov     rcx, rax
0x1800029bf  cmp     rax, rbx
0x1800029c2  jnz     short loc_1800029D1
0x1800029c4  mov     rax, 2B992DDFA233h
0x1800029ce  mov     rcx, rax
0x1800029d1  mov     cs:__security_cookie, rcx
0x1800029d8  mov     rbx, [rsp+20h+arg_18]
0x1800029dd  not     rax
0x1800029e0  mov     cs:__security_cookie_complement, rax
0x1800029e7  add     rsp, 20h
0x1800029eb  pop     rbp
0x1800029ec  retn
```
