# __security_init_cookie

- ea: `0x18000399c`
- end: `0x180003a51`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003510`

## callees

- `0x18000399c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800039eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800039eb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800039fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800039fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800039d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800039d1`

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
0x18000399c  mov     [rsp-8+arg_10], rbx
0x1800039a1  push    rbp
0x1800039a2  mov     rbp, rsp
0x1800039a5  sub     rsp, 30h
0x1800039a9  mov     rax, cs:__security_cookie
0x1800039b0  mov     rbx, 2B992DDFA232h
0x1800039ba  cmp     rax, rbx
0x1800039bd  jnz     short loc_180003A3C
0x1800039bf  xor     eax, eax
0x1800039c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800039c5  mov     [rbp+var_10], rax
0x1800039c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800039cd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800039d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800039d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800039db  mov     [rbp+var_10], rax
0x1800039df  call    cs:__imp_GetCurrentThreadId
0x1800039e5  mov     eax, eax
0x1800039e7  xor     [rbp+var_10], rax
0x1800039eb  call    cs:__imp_GetCurrentProcessId
0x1800039f1  mov     eax, eax
0x1800039f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800039f7  xor     [rbp+var_10], rax
0x1800039fb  call    cs:__imp_QueryPerformanceCounter
0x180003a01  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003a04  lea     rcx, [rbp+var_10]
0x180003a08  shl     rax, 20h
0x180003a0c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003a10  xor     rax, [rbp+var_10]
0x180003a14  xor     rax, rcx
0x180003a17  mov     rcx, 0FFFFFFFFFFFFh
0x180003a21  and     rax, rcx
0x180003a24  mov     rcx, 2B992DDFA233h
0x180003a2e  cmp     rax, rbx
0x180003a31  cmovz   rax, rcx
0x180003a35  mov     cs:__security_cookie, rax
0x180003a3c  mov     rbx, [rsp+30h+arg_10]
0x180003a41  not     rax
0x180003a44  mov     cs:__security_cookie_complement, rax
0x180003a4b  add     rsp, 30h
0x180003a4f  pop     rbp
0x180003a50  retn
```
