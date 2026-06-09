# __security_init_cookie

- ea: `0x1800031c4`
- end: `0x1800032a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002c50`

## callees

- `0x1800031c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000320b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000320b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800031fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800031fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003223`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003233`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003223`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003233`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000324e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000324e`

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
0x1800031c4  mov     [rsp-8+arg_18], rbx
0x1800031c9  push    rbp
0x1800031ca  mov     rbp, rsp
0x1800031cd  sub     rsp, 20h
0x1800031d1  xor     eax, eax
0x1800031d3  mov     rbx, 2B992DDFA232h
0x1800031dd  mov     [rbp+arg_0], rax
0x1800031e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800031e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800031e9  mov     rax, cs:__security_cookie
0x1800031f0  cmp     rax, rbx
0x1800031f3  jnz     loc_18000328C
0x1800031f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800031fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180003203  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003207  mov     [rbp+arg_0], rax
0x18000320b  call    cs:__imp_GetCurrentProcessId
0x180003211  mov     eax, eax
0x180003213  xor     [rbp+arg_0], rax
0x180003217  call    cs:__imp_GetCurrentThreadId
0x18000321d  mov     eax, eax
0x18000321f  xor     [rbp+arg_0], rax
0x180003223  call    cs:__imp_GetTickCount
0x180003229  mov     eax, eax
0x18000322b  shl     rax, 18h
0x18000322f  xor     [rbp+arg_0], rax
0x180003233  call    cs:__imp_GetTickCount
0x180003239  mov     eax, eax
0x18000323b  lea     rcx, [rbp+arg_0]
0x18000323f  xor     rax, [rbp+arg_0]
0x180003243  xor     rax, rcx
0x180003246  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000324a  mov     [rbp+arg_0], rax
0x18000324e  call    cs:__imp_QueryPerformanceCounter
0x180003254  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003257  mov     rcx, 0FFFFFFFFFFFFh
0x180003261  shl     rax, 20h
0x180003265  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003269  xor     rax, [rbp+arg_0]
0x18000326d  and     rax, rcx
0x180003270  mov     rcx, rax
0x180003273  cmp     rax, rbx
0x180003276  jnz     short loc_180003285
0x180003278  mov     rax, 2B992DDFA233h
0x180003282  mov     rcx, rax
0x180003285  mov     cs:__security_cookie, rcx
0x18000328c  mov     rbx, [rsp+20h+arg_18]
0x180003291  not     rax
0x180003294  mov     cs:__security_cookie_complement, rax
0x18000329b  add     rsp, 20h
0x18000329f  pop     rbp
0x1800032a0  retn
```
