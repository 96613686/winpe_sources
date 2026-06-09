# __security_init_cookie

- ea: `0x1800027a0`
- end: `0x180002855`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800021f0`

## callees

- `0x1800027a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800027e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800027ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800027ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800027ff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800027ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800027d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800027d5`

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
0x1800027a0  mov     [rsp-8+arg_10], rbx
0x1800027a5  push    rbp
0x1800027a6  mov     rbp, rsp
0x1800027a9  sub     rsp, 30h
0x1800027ad  mov     rax, cs:__security_cookie
0x1800027b4  mov     rbx, 2B992DDFA232h
0x1800027be  cmp     rax, rbx
0x1800027c1  jnz     short loc_180002840
0x1800027c3  xor     eax, eax
0x1800027c5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800027c9  mov     [rbp+var_10], rax
0x1800027cd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800027d1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800027d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800027db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800027df  mov     [rbp+var_10], rax
0x1800027e3  call    cs:__imp_GetCurrentThreadId
0x1800027e9  mov     eax, eax
0x1800027eb  xor     [rbp+var_10], rax
0x1800027ef  call    cs:__imp_GetCurrentProcessId
0x1800027f5  mov     eax, eax
0x1800027f7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800027fb  xor     [rbp+var_10], rax
0x1800027ff  call    cs:__imp_QueryPerformanceCounter
0x180002805  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002808  lea     rcx, [rbp+var_10]
0x18000280c  shl     rax, 20h
0x180002810  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002814  xor     rax, [rbp+var_10]
0x180002818  xor     rax, rcx
0x18000281b  mov     rcx, 0FFFFFFFFFFFFh
0x180002825  and     rax, rcx
0x180002828  mov     rcx, 2B992DDFA233h
0x180002832  cmp     rax, rbx
0x180002835  cmovz   rax, rcx
0x180002839  mov     cs:__security_cookie, rax
0x180002840  mov     rbx, [rsp+30h+arg_10]
0x180002845  not     rax
0x180002848  mov     cs:__security_cookie_complement, rax
0x18000284f  add     rsp, 30h
0x180002853  pop     rbp
0x180002854  retn
```
