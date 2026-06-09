# __security_init_cookie

- ea: `0x180002774`
- end: `0x180002851`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ec0`

## callees

- `0x180002774`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800027bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800027bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800027fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800027fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800027d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800027e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800027d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800027e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800027ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800027ad`

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
0x180002774  mov     [rsp-8+arg_18], rbx
0x180002779  push    rbp
0x18000277a  mov     rbp, rsp
0x18000277d  sub     rsp, 20h
0x180002781  xor     eax, eax
0x180002783  mov     rbx, 2B992DDFA232h
0x18000278d  mov     [rbp+arg_0], rax
0x180002791  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002795  mov     qword ptr [rbp+PerformanceCount], rax
0x180002799  mov     rax, cs:__security_cookie
0x1800027a0  cmp     rax, rbx
0x1800027a3  jnz     loc_18000283C
0x1800027a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800027ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800027b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800027b7  mov     [rbp+arg_0], rax
0x1800027bb  call    cs:__imp_GetCurrentProcessId
0x1800027c1  mov     eax, eax
0x1800027c3  xor     [rbp+arg_0], rax
0x1800027c7  call    cs:__imp_GetCurrentThreadId
0x1800027cd  mov     eax, eax
0x1800027cf  xor     [rbp+arg_0], rax
0x1800027d3  call    cs:__imp_GetTickCount
0x1800027d9  mov     eax, eax
0x1800027db  shl     rax, 18h
0x1800027df  xor     [rbp+arg_0], rax
0x1800027e3  call    cs:__imp_GetTickCount
0x1800027e9  mov     eax, eax
0x1800027eb  lea     rcx, [rbp+arg_0]
0x1800027ef  xor     rax, [rbp+arg_0]
0x1800027f3  xor     rax, rcx
0x1800027f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800027fa  mov     [rbp+arg_0], rax
0x1800027fe  call    cs:__imp_QueryPerformanceCounter
0x180002804  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002807  mov     rcx, 0FFFFFFFFFFFFh
0x180002811  shl     rax, 20h
0x180002815  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002819  xor     rax, [rbp+arg_0]
0x18000281d  and     rax, rcx
0x180002820  mov     rcx, rax
0x180002823  cmp     rax, rbx
0x180002826  jnz     short loc_180002835
0x180002828  mov     rax, 2B992DDFA233h
0x180002832  mov     rcx, rax
0x180002835  mov     cs:__security_cookie, rcx
0x18000283c  mov     rbx, [rsp+20h+arg_18]
0x180002841  not     rax
0x180002844  mov     cs:__security_cookie_complement, rax
0x18000284b  add     rsp, 20h
0x18000284f  pop     rbp
0x180002850  retn
```
