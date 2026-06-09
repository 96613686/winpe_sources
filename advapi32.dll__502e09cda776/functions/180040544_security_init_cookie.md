# __security_init_cookie

- ea: `0x180040544`
- end: `0x180040621`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f1e0`
- `0x180040208`

## callees

- `0x180040544`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004058b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004058b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800405a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800405b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800405a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800405b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004057d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004057d`
- `KERNEL32!QueryPerformanceCounter` at `0x1800405ce`
- `KERNEL32!QueryPerformanceCounter` at `0x1800405ce`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180040544  mov     [rsp-8+arg_18], rbx
0x180040549  push    rbp
0x18004054a  mov     rbp, rsp
0x18004054d  sub     rsp, 20h
0x180040551  xor     eax, eax
0x180040553  mov     rbx, 2B992DDFA232h
0x18004055d  mov     [rbp+arg_0], rax
0x180040561  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180040565  mov     qword ptr [rbp+PerformanceCount], rax
0x180040569  mov     rax, cs:__security_cookie
0x180040570  cmp     rax, rbx
0x180040573  jnz     loc_18004060C
0x180040579  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004057d  call    cs:__imp_GetSystemTimeAsFileTime
0x180040583  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180040587  mov     [rbp+arg_0], rax
0x18004058b  call    cs:__imp_GetCurrentProcessId
0x180040591  mov     eax, eax
0x180040593  xor     [rbp+arg_0], rax
0x180040597  call    cs:__imp_GetCurrentThreadId
0x18004059d  mov     eax, eax
0x18004059f  xor     [rbp+arg_0], rax
0x1800405a3  call    cs:__imp_GetTickCount
0x1800405a9  mov     eax, eax
0x1800405ab  shl     rax, 18h
0x1800405af  xor     [rbp+arg_0], rax
0x1800405b3  call    cs:__imp_GetTickCount
0x1800405b9  mov     eax, eax
0x1800405bb  lea     rcx, [rbp+arg_0]
0x1800405bf  xor     rax, [rbp+arg_0]
0x1800405c3  xor     rax, rcx
0x1800405c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800405ca  mov     [rbp+arg_0], rax
0x1800405ce  call    cs:__imp_QueryPerformanceCounter
0x1800405d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800405d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800405e1  shl     rax, 20h
0x1800405e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800405e9  xor     rax, [rbp+arg_0]
0x1800405ed  and     rax, rcx
0x1800405f0  mov     rcx, rax
0x1800405f3  cmp     rax, rbx
0x1800405f6  jnz     short loc_180040605
0x1800405f8  mov     rax, 2B992DDFA233h
0x180040602  mov     rcx, rax
0x180040605  mov     cs:__security_cookie, rcx
0x18004060c  mov     rbx, [rsp+20h+arg_18]
0x180040611  not     rax
0x180040614  mov     cs:__security_cookie_complement, rax
0x18004061b  add     rsp, 20h
0x18004061f  pop     rbp
0x180040620  retn
```
