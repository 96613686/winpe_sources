# __security_init_cookie

- ea: `0x14000276c`
- end: `0x140002821`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002440`

## callees

- `0x14000276c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400027bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400027bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400027af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400027af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400027cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400027cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400027a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400027a1`

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
0x14000276c  mov     [rsp-8+arg_10], rbx
0x140002771  push    rbp
0x140002772  mov     rbp, rsp
0x140002775  sub     rsp, 30h
0x140002779  mov     rax, cs:__security_cookie
0x140002780  mov     rbx, 2B992DDFA232h
0x14000278a  cmp     rax, rbx
0x14000278d  jnz     short loc_14000280C
0x14000278f  xor     eax, eax
0x140002791  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002795  mov     [rbp+var_10], rax
0x140002799  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000279d  mov     qword ptr [rbp+PerformanceCount], rax
0x1400027a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400027a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400027ab  mov     [rbp+var_10], rax
0x1400027af  call    cs:__imp_GetCurrentThreadId
0x1400027b5  mov     eax, eax
0x1400027b7  xor     [rbp+var_10], rax
0x1400027bb  call    cs:__imp_GetCurrentProcessId
0x1400027c1  mov     eax, eax
0x1400027c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400027c7  xor     [rbp+var_10], rax
0x1400027cb  call    cs:__imp_QueryPerformanceCounter
0x1400027d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400027d4  lea     rcx, [rbp+var_10]
0x1400027d8  shl     rax, 20h
0x1400027dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400027e0  xor     rax, [rbp+var_10]
0x1400027e4  xor     rax, rcx
0x1400027e7  mov     rcx, 0FFFFFFFFFFFFh
0x1400027f1  and     rax, rcx
0x1400027f4  mov     rcx, 2B992DDFA233h
0x1400027fe  cmp     rax, rbx
0x140002801  cmovz   rax, rcx
0x140002805  mov     cs:__security_cookie, rax
0x14000280c  mov     rbx, [rsp+30h+arg_10]
0x140002811  not     rax
0x140002814  mov     cs:__security_cookie_complement, rax
0x14000281b  add     rsp, 30h
0x14000281f  pop     rbp
0x140002820  retn
```
