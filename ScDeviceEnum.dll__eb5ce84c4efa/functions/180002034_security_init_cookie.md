# __security_init_cookie

- ea: `0x180002034`
- end: `0x180002111`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001940`

## callees

- `0x180002034`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000207b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000207b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002087`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800020be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800020be`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000206d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000206d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002093`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002093`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020a3`

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
0x180002034  mov     [rsp-8+arg_18], rbx
0x180002039  push    rbp
0x18000203a  mov     rbp, rsp
0x18000203d  sub     rsp, 20h
0x180002041  xor     eax, eax
0x180002043  mov     rbx, 2B992DDFA232h
0x18000204d  mov     [rbp+arg_0], rax
0x180002051  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002055  mov     qword ptr [rbp+PerformanceCount], rax
0x180002059  mov     rax, cs:__security_cookie
0x180002060  cmp     rax, rbx
0x180002063  jnz     loc_1800020FC
0x180002069  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000206d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002073  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002077  mov     [rbp+arg_0], rax
0x18000207b  call    cs:__imp_GetCurrentProcessId
0x180002081  mov     eax, eax
0x180002083  xor     [rbp+arg_0], rax
0x180002087  call    cs:__imp_GetCurrentThreadId
0x18000208d  mov     eax, eax
0x18000208f  xor     [rbp+arg_0], rax
0x180002093  call    cs:__imp_GetTickCount
0x180002099  mov     eax, eax
0x18000209b  shl     rax, 18h
0x18000209f  xor     [rbp+arg_0], rax
0x1800020a3  call    cs:__imp_GetTickCount
0x1800020a9  mov     eax, eax
0x1800020ab  lea     rcx, [rbp+arg_0]
0x1800020af  xor     rax, [rbp+arg_0]
0x1800020b3  xor     rax, rcx
0x1800020b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800020ba  mov     [rbp+arg_0], rax
0x1800020be  call    cs:__imp_QueryPerformanceCounter
0x1800020c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800020c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800020d1  shl     rax, 20h
0x1800020d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800020d9  xor     rax, [rbp+arg_0]
0x1800020dd  and     rax, rcx
0x1800020e0  mov     rcx, rax
0x1800020e3  cmp     rax, rbx
0x1800020e6  jnz     short loc_1800020F5
0x1800020e8  mov     rax, 2B992DDFA233h
0x1800020f2  mov     rcx, rax
0x1800020f5  mov     cs:__security_cookie, rcx
0x1800020fc  mov     rbx, [rsp+20h+arg_18]
0x180002101  not     rax
0x180002104  mov     cs:__security_cookie_complement, rax
0x18000210b  add     rsp, 20h
0x18000210f  pop     rbp
0x180002110  retn
```
