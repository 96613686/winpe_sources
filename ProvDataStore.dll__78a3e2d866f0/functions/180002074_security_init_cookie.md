# __security_init_cookie

- ea: `0x180002074`
- end: `0x180002151`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ba0`

## callees

- `0x180002074`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800020c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800020c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800020bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800020bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800020fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800020fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800020ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800020ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020e3`

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
0x180002074  mov     [rsp-8+arg_18], rbx
0x180002079  push    rbp
0x18000207a  mov     rbp, rsp
0x18000207d  sub     rsp, 20h
0x180002081  xor     eax, eax
0x180002083  mov     rbx, 2B992DDFA232h
0x18000208d  mov     [rbp+arg_0], rax
0x180002091  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002095  mov     qword ptr [rbp+PerformanceCount], rax
0x180002099  mov     rax, cs:__security_cookie
0x1800020a0  cmp     rax, rbx
0x1800020a3  jnz     loc_18000213C
0x1800020a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800020ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800020b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800020b7  mov     [rbp+arg_0], rax
0x1800020bb  call    cs:__imp_GetCurrentProcessId
0x1800020c1  mov     eax, eax
0x1800020c3  xor     [rbp+arg_0], rax
0x1800020c7  call    cs:__imp_GetCurrentThreadId
0x1800020cd  mov     eax, eax
0x1800020cf  xor     [rbp+arg_0], rax
0x1800020d3  call    cs:__imp_GetTickCount
0x1800020d9  mov     eax, eax
0x1800020db  shl     rax, 18h
0x1800020df  xor     [rbp+arg_0], rax
0x1800020e3  call    cs:__imp_GetTickCount
0x1800020e9  mov     eax, eax
0x1800020eb  lea     rcx, [rbp+arg_0]
0x1800020ef  xor     rax, [rbp+arg_0]
0x1800020f3  xor     rax, rcx
0x1800020f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800020fa  mov     [rbp+arg_0], rax
0x1800020fe  call    cs:__imp_QueryPerformanceCounter
0x180002104  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002107  mov     rcx, 0FFFFFFFFFFFFh
0x180002111  shl     rax, 20h
0x180002115  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002119  xor     rax, [rbp+arg_0]
0x18000211d  and     rax, rcx
0x180002120  mov     rcx, rax
0x180002123  cmp     rax, rbx
0x180002126  jnz     short loc_180002135
0x180002128  mov     rax, 2B992DDFA233h
0x180002132  mov     rcx, rax
0x180002135  mov     cs:__security_cookie, rcx
0x18000213c  mov     rbx, [rsp+20h+arg_18]
0x180002141  not     rax
0x180002144  mov     cs:__security_cookie_complement, rax
0x18000214b  add     rsp, 20h
0x18000214f  pop     rbp
0x180002150  retn
```
