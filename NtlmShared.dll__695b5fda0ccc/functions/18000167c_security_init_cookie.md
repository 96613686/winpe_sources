# __security_init_cookie

- ea: `0x18000167c`
- end: `0x180001759`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001450`

## callees

- `0x18000167c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800016cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800016cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001706`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001706`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800016b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800016b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016db`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800016eb`

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
0x18000167c  mov     [rsp-8+arg_18], rbx
0x180001681  push    rbp
0x180001682  mov     rbp, rsp
0x180001685  sub     rsp, 20h
0x180001689  xor     eax, eax
0x18000168b  mov     rbx, 2B992DDFA232h
0x180001695  mov     [rbp+arg_0], rax
0x180001699  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000169d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800016a1  mov     rax, cs:__security_cookie
0x1800016a8  cmp     rax, rbx
0x1800016ab  jnz     loc_180001744
0x1800016b1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800016b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800016bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800016bf  mov     [rbp+arg_0], rax
0x1800016c3  call    cs:__imp_GetCurrentProcessId
0x1800016c9  mov     eax, eax
0x1800016cb  xor     [rbp+arg_0], rax
0x1800016cf  call    cs:__imp_GetCurrentThreadId
0x1800016d5  mov     eax, eax
0x1800016d7  xor     [rbp+arg_0], rax
0x1800016db  call    cs:__imp_GetTickCount
0x1800016e1  mov     eax, eax
0x1800016e3  shl     rax, 18h
0x1800016e7  xor     [rbp+arg_0], rax
0x1800016eb  call    cs:__imp_GetTickCount
0x1800016f1  mov     eax, eax
0x1800016f3  lea     rcx, [rbp+arg_0]
0x1800016f7  xor     rax, [rbp+arg_0]
0x1800016fb  xor     rax, rcx
0x1800016fe  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001702  mov     [rbp+arg_0], rax
0x180001706  call    cs:__imp_QueryPerformanceCounter
0x18000170c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000170f  mov     rcx, 0FFFFFFFFFFFFh
0x180001719  shl     rax, 20h
0x18000171d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001721  xor     rax, [rbp+arg_0]
0x180001725  and     rax, rcx
0x180001728  mov     rcx, rax
0x18000172b  cmp     rax, rbx
0x18000172e  jnz     short loc_18000173D
0x180001730  mov     rax, 2B992DDFA233h
0x18000173a  mov     rcx, rax
0x18000173d  mov     cs:__security_cookie, rcx
0x180001744  mov     rbx, [rsp+20h+arg_18]
0x180001749  not     rax
0x18000174c  mov     cs:__security_cookie_complement, rax
0x180001753  add     rsp, 20h
0x180001757  pop     rbp
0x180001758  retn
```
