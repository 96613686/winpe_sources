# __security_init_cookie

- ea: `0x180001ff4`
- end: `0x1800020d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ac0`

## callees

- `0x180001ff4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002047`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002047`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000203b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000203b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000207e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000207e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002053`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002063`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002053`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002063`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000202d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000202d`

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
0x180001ff4  mov     [rsp-8+arg_18], rbx
0x180001ff9  push    rbp
0x180001ffa  mov     rbp, rsp
0x180001ffd  sub     rsp, 20h
0x180002001  xor     eax, eax
0x180002003  mov     rbx, 2B992DDFA232h
0x18000200d  mov     [rbp+arg_0], rax
0x180002011  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002015  mov     qword ptr [rbp+PerformanceCount], rax
0x180002019  mov     rax, cs:__security_cookie
0x180002020  cmp     rax, rbx
0x180002023  jnz     loc_1800020BC
0x180002029  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000202d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002033  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002037  mov     [rbp+arg_0], rax
0x18000203b  call    cs:__imp_GetCurrentProcessId
0x180002041  mov     eax, eax
0x180002043  xor     [rbp+arg_0], rax
0x180002047  call    cs:__imp_GetCurrentThreadId
0x18000204d  mov     eax, eax
0x18000204f  xor     [rbp+arg_0], rax
0x180002053  call    cs:__imp_GetTickCount
0x180002059  mov     eax, eax
0x18000205b  shl     rax, 18h
0x18000205f  xor     [rbp+arg_0], rax
0x180002063  call    cs:__imp_GetTickCount
0x180002069  mov     eax, eax
0x18000206b  lea     rcx, [rbp+arg_0]
0x18000206f  xor     rax, [rbp+arg_0]
0x180002073  xor     rax, rcx
0x180002076  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000207a  mov     [rbp+arg_0], rax
0x18000207e  call    cs:__imp_QueryPerformanceCounter
0x180002084  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002087  mov     rcx, 0FFFFFFFFFFFFh
0x180002091  shl     rax, 20h
0x180002095  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002099  xor     rax, [rbp+arg_0]
0x18000209d  and     rax, rcx
0x1800020a0  mov     rcx, rax
0x1800020a3  cmp     rax, rbx
0x1800020a6  jnz     short loc_1800020B5
0x1800020a8  mov     rax, 2B992DDFA233h
0x1800020b2  mov     rcx, rax
0x1800020b5  mov     cs:__security_cookie, rcx
0x1800020bc  mov     rbx, [rsp+20h+arg_18]
0x1800020c1  not     rax
0x1800020c4  mov     cs:__security_cookie_complement, rax
0x1800020cb  add     rsp, 20h
0x1800020cf  pop     rbp
0x1800020d0  retn
```
