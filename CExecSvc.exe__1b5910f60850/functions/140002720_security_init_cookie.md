# __security_init_cookie

- ea: `0x140002720`
- end: `0x1400027d5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022e0`

## callees

- `0x140002720`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000276f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000276f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002763`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002763`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002755`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002755`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000277f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000277f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x140002720  mov     [rsp-8+arg_10], rbx
0x140002725  push    rbp
0x140002726  mov     rbp, rsp
0x140002729  sub     rsp, 30h
0x14000272d  mov     rax, cs:__security_cookie
0x140002734  mov     rbx, 2B992DDFA232h
0x14000273e  cmp     rax, rbx
0x140002741  jnz     short loc_1400027C0
0x140002743  xor     eax, eax
0x140002745  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002749  mov     [rbp+var_10], rax
0x14000274d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002751  mov     qword ptr [rbp+PerformanceCount], rax
0x140002755  call    cs:__imp_GetSystemTimeAsFileTime
0x14000275b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000275f  mov     [rbp+var_10], rax
0x140002763  call    cs:__imp_GetCurrentThreadId
0x140002769  mov     eax, eax
0x14000276b  xor     [rbp+var_10], rax
0x14000276f  call    cs:__imp_GetCurrentProcessId
0x140002775  mov     eax, eax
0x140002777  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000277b  xor     [rbp+var_10], rax
0x14000277f  call    cs:__imp_QueryPerformanceCounter
0x140002785  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002788  lea     rcx, [rbp+var_10]
0x14000278c  shl     rax, 20h
0x140002790  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002794  xor     rax, [rbp+var_10]
0x140002798  xor     rax, rcx
0x14000279b  mov     rcx, 0FFFFFFFFFFFFh
0x1400027a5  and     rax, rcx
0x1400027a8  mov     rcx, 2B992DDFA233h
0x1400027b2  cmp     rax, rbx
0x1400027b5  cmovz   rax, rcx
0x1400027b9  mov     cs:__security_cookie, rax
0x1400027c0  mov     rbx, [rsp+30h+arg_10]
0x1400027c5  not     rax
0x1400027c8  mov     cs:__security_cookie_complement, rax
0x1400027cf  add     rsp, 30h
0x1400027d3  pop     rbp
0x1400027d4  retn
```
