# __security_init_cookie

- ea: `0x180002300`
- end: `0x1800023b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e00`

## callees

- `0x180002300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002343`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002343`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000234f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000234f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000235f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000235f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002335`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002335`

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
0x180002300  mov     [rsp-8+arg_10], rbx
0x180002305  push    rbp
0x180002306  mov     rbp, rsp
0x180002309  sub     rsp, 30h
0x18000230d  mov     rax, cs:__security_cookie
0x180002314  mov     rbx, 2B992DDFA232h
0x18000231e  cmp     rax, rbx
0x180002321  jnz     short loc_1800023A0
0x180002323  xor     eax, eax
0x180002325  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002329  mov     [rbp+var_10], rax
0x18000232d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002331  mov     qword ptr [rbp+PerformanceCount], rax
0x180002335  call    cs:__imp_GetSystemTimeAsFileTime
0x18000233b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000233f  mov     [rbp+var_10], rax
0x180002343  call    cs:__imp_GetCurrentThreadId
0x180002349  mov     eax, eax
0x18000234b  xor     [rbp+var_10], rax
0x18000234f  call    cs:__imp_GetCurrentProcessId
0x180002355  mov     eax, eax
0x180002357  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000235b  xor     [rbp+var_10], rax
0x18000235f  call    cs:__imp_QueryPerformanceCounter
0x180002365  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002368  lea     rcx, [rbp+var_10]
0x18000236c  shl     rax, 20h
0x180002370  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002374  xor     rax, [rbp+var_10]
0x180002378  xor     rax, rcx
0x18000237b  mov     rcx, 0FFFFFFFFFFFFh
0x180002385  and     rax, rcx
0x180002388  mov     rcx, 2B992DDFA233h
0x180002392  cmp     rax, rbx
0x180002395  cmovz   rax, rcx
0x180002399  mov     cs:__security_cookie, rax
0x1800023a0  mov     rbx, [rsp+30h+arg_10]
0x1800023a5  not     rax
0x1800023a8  mov     cs:__security_cookie_complement, rax
0x1800023af  add     rsp, 30h
0x1800023b3  pop     rbp
0x1800023b4  retn
```
