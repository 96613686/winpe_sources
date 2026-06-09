# __security_init_cookie

- ea: `0x18000219c`
- end: `0x180002251`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d10`

## callees

- `0x18000219c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800021eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800021eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800021df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800021df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800021fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800021fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800021d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800021d1`

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
0x18000219c  mov     [rsp-8+arg_10], rbx
0x1800021a1  push    rbp
0x1800021a2  mov     rbp, rsp
0x1800021a5  sub     rsp, 30h
0x1800021a9  mov     rax, cs:__security_cookie
0x1800021b0  mov     rbx, 2B992DDFA232h
0x1800021ba  cmp     rax, rbx
0x1800021bd  jnz     short loc_18000223C
0x1800021bf  xor     eax, eax
0x1800021c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800021c5  mov     [rbp+var_10], rax
0x1800021c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800021cd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800021d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800021d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800021db  mov     [rbp+var_10], rax
0x1800021df  call    cs:__imp_GetCurrentThreadId
0x1800021e5  mov     eax, eax
0x1800021e7  xor     [rbp+var_10], rax
0x1800021eb  call    cs:__imp_GetCurrentProcessId
0x1800021f1  mov     eax, eax
0x1800021f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800021f7  xor     [rbp+var_10], rax
0x1800021fb  call    cs:__imp_QueryPerformanceCounter
0x180002201  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002204  lea     rcx, [rbp+var_10]
0x180002208  shl     rax, 20h
0x18000220c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002210  xor     rax, [rbp+var_10]
0x180002214  xor     rax, rcx
0x180002217  mov     rcx, 0FFFFFFFFFFFFh
0x180002221  and     rax, rcx
0x180002224  mov     rcx, 2B992DDFA233h
0x18000222e  cmp     rax, rbx
0x180002231  cmovz   rax, rcx
0x180002235  mov     cs:__security_cookie, rax
0x18000223c  mov     rbx, [rsp+30h+arg_10]
0x180002241  not     rax
0x180002244  mov     cs:__security_cookie_complement, rax
0x18000224b  add     rsp, 30h
0x18000224f  pop     rbp
0x180002250  retn
```
