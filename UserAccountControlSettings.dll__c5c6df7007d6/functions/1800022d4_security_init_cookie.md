# __security_init_cookie

- ea: `0x1800022d4`
- end: `0x1800023b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001cc0`

## callees

- `0x1800022d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000231b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000231b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002327`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002327`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000235e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000235e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002333`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002343`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002333`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002343`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000230d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000230d`

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
0x1800022d4  mov     [rsp-8+arg_18], rbx
0x1800022d9  push    rbp
0x1800022da  mov     rbp, rsp
0x1800022dd  sub     rsp, 20h
0x1800022e1  xor     eax, eax
0x1800022e3  mov     rbx, 2B992DDFA232h
0x1800022ed  mov     [rbp+arg_0], rax
0x1800022f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800022f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800022f9  mov     rax, cs:__security_cookie
0x180002300  cmp     rax, rbx
0x180002303  jnz     loc_18000239C
0x180002309  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000230d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002313  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002317  mov     [rbp+arg_0], rax
0x18000231b  call    cs:__imp_GetCurrentProcessId
0x180002321  mov     eax, eax
0x180002323  xor     [rbp+arg_0], rax
0x180002327  call    cs:__imp_GetCurrentThreadId
0x18000232d  mov     eax, eax
0x18000232f  xor     [rbp+arg_0], rax
0x180002333  call    cs:__imp_GetTickCount
0x180002339  mov     eax, eax
0x18000233b  shl     rax, 18h
0x18000233f  xor     [rbp+arg_0], rax
0x180002343  call    cs:__imp_GetTickCount
0x180002349  mov     eax, eax
0x18000234b  lea     rcx, [rbp+arg_0]
0x18000234f  xor     rax, [rbp+arg_0]
0x180002353  xor     rax, rcx
0x180002356  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000235a  mov     [rbp+arg_0], rax
0x18000235e  call    cs:__imp_QueryPerformanceCounter
0x180002364  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002367  mov     rcx, 0FFFFFFFFFFFFh
0x180002371  shl     rax, 20h
0x180002375  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002379  xor     rax, [rbp+arg_0]
0x18000237d  and     rax, rcx
0x180002380  mov     rcx, rax
0x180002383  cmp     rax, rbx
0x180002386  jnz     short loc_180002395
0x180002388  mov     rax, 2B992DDFA233h
0x180002392  mov     rcx, rax
0x180002395  mov     cs:__security_cookie, rcx
0x18000239c  mov     rbx, [rsp+20h+arg_18]
0x1800023a1  not     rax
0x1800023a4  mov     cs:__security_cookie_complement, rax
0x1800023ab  add     rsp, 20h
0x1800023af  pop     rbp
0x1800023b0  retn
```
