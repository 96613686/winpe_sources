# __security_init_cookie

- ea: `0x180005004`
- end: `0x1800050e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800049e0`

## callees

- `0x180005004`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005063`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005073`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005063`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005073`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000503d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000503d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000504b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000504b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000508e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000508e`

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
0x180005004  mov     [rsp-8+arg_18], rbx
0x180005009  push    rbp
0x18000500a  mov     rbp, rsp
0x18000500d  sub     rsp, 20h
0x180005011  xor     eax, eax
0x180005013  mov     rbx, 2B992DDFA232h
0x18000501d  mov     [rbp+arg_0], rax
0x180005021  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005025  mov     qword ptr [rbp+PerformanceCount], rax
0x180005029  mov     rax, cs:__security_cookie
0x180005030  cmp     rax, rbx
0x180005033  jnz     loc_1800050CC
0x180005039  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000503d  call    cs:__imp_GetSystemTimeAsFileTime
0x180005043  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005047  mov     [rbp+arg_0], rax
0x18000504b  call    cs:__imp_GetCurrentProcessId
0x180005051  mov     eax, eax
0x180005053  xor     [rbp+arg_0], rax
0x180005057  call    cs:__imp_GetCurrentThreadId
0x18000505d  mov     eax, eax
0x18000505f  xor     [rbp+arg_0], rax
0x180005063  call    cs:__imp_GetTickCount
0x180005069  mov     eax, eax
0x18000506b  shl     rax, 18h
0x18000506f  xor     [rbp+arg_0], rax
0x180005073  call    cs:__imp_GetTickCount
0x180005079  mov     eax, eax
0x18000507b  lea     rcx, [rbp+arg_0]
0x18000507f  xor     rax, [rbp+arg_0]
0x180005083  xor     rax, rcx
0x180005086  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000508a  mov     [rbp+arg_0], rax
0x18000508e  call    cs:__imp_QueryPerformanceCounter
0x180005094  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005097  mov     rcx, 0FFFFFFFFFFFFh
0x1800050a1  shl     rax, 20h
0x1800050a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800050a9  xor     rax, [rbp+arg_0]
0x1800050ad  and     rax, rcx
0x1800050b0  mov     rcx, rax
0x1800050b3  cmp     rax, rbx
0x1800050b6  jnz     short loc_1800050C5
0x1800050b8  mov     rax, 2B992DDFA233h
0x1800050c2  mov     rcx, rax
0x1800050c5  mov     cs:__security_cookie, rcx
0x1800050cc  mov     rbx, [rsp+20h+arg_18]
0x1800050d1  not     rax
0x1800050d4  mov     cs:__security_cookie_complement, rax
0x1800050db  add     rsp, 20h
0x1800050df  pop     rbp
0x1800050e0  retn
```
