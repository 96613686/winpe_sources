# __security_init_cookie

- ea: `0x180002248`
- end: `0x1800022fd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d70`

## callees

- `0x180002248`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000227d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000227d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000228b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000228b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002297`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800022a7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800022a7`

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
0x180002248  mov     [rsp-8+arg_10], rbx
0x18000224d  push    rbp
0x18000224e  mov     rbp, rsp
0x180002251  sub     rsp, 30h
0x180002255  mov     rax, cs:__security_cookie
0x18000225c  mov     rbx, 2B992DDFA232h
0x180002266  cmp     rax, rbx
0x180002269  jnz     short loc_1800022E8
0x18000226b  xor     eax, eax
0x18000226d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002271  mov     [rbp+var_10], rax
0x180002275  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002279  mov     qword ptr [rbp+PerformanceCount], rax
0x18000227d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002283  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002287  mov     [rbp+var_10], rax
0x18000228b  call    cs:__imp_GetCurrentThreadId
0x180002291  mov     eax, eax
0x180002293  xor     [rbp+var_10], rax
0x180002297  call    cs:__imp_GetCurrentProcessId
0x18000229d  mov     eax, eax
0x18000229f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800022a3  xor     [rbp+var_10], rax
0x1800022a7  call    cs:__imp_QueryPerformanceCounter
0x1800022ad  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800022b0  lea     rcx, [rbp+var_10]
0x1800022b4  shl     rax, 20h
0x1800022b8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800022bc  xor     rax, [rbp+var_10]
0x1800022c0  xor     rax, rcx
0x1800022c3  mov     rcx, 0FFFFFFFFFFFFh
0x1800022cd  and     rax, rcx
0x1800022d0  mov     rcx, 2B992DDFA233h
0x1800022da  cmp     rax, rbx
0x1800022dd  cmovz   rax, rcx
0x1800022e1  mov     cs:__security_cookie, rax
0x1800022e8  mov     rbx, [rsp+30h+arg_10]
0x1800022ed  not     rax
0x1800022f0  mov     cs:__security_cookie_complement, rax
0x1800022f7  add     rsp, 30h
0x1800022fb  pop     rbp
0x1800022fc  retn
```
