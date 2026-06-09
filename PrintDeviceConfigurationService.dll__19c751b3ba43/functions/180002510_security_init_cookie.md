# __security_init_cookie

- ea: `0x180002510`
- end: `0x1800025c5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002070`

## callees

- `0x180002510`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000255f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000255f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002553`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000256f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000256f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002545`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002545`

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
0x180002510  mov     [rsp-8+arg_10], rbx
0x180002515  push    rbp
0x180002516  mov     rbp, rsp
0x180002519  sub     rsp, 30h
0x18000251d  mov     rax, cs:__security_cookie
0x180002524  mov     rbx, 2B992DDFA232h
0x18000252e  cmp     rax, rbx
0x180002531  jnz     short loc_1800025B0
0x180002533  xor     eax, eax
0x180002535  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002539  mov     [rbp+var_10], rax
0x18000253d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002541  mov     qword ptr [rbp+PerformanceCount], rax
0x180002545  call    cs:__imp_GetSystemTimeAsFileTime
0x18000254b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000254f  mov     [rbp+var_10], rax
0x180002553  call    cs:__imp_GetCurrentThreadId
0x180002559  mov     eax, eax
0x18000255b  xor     [rbp+var_10], rax
0x18000255f  call    cs:__imp_GetCurrentProcessId
0x180002565  mov     eax, eax
0x180002567  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000256b  xor     [rbp+var_10], rax
0x18000256f  call    cs:__imp_QueryPerformanceCounter
0x180002575  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002578  lea     rcx, [rbp+var_10]
0x18000257c  shl     rax, 20h
0x180002580  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002584  xor     rax, [rbp+var_10]
0x180002588  xor     rax, rcx
0x18000258b  mov     rcx, 0FFFFFFFFFFFFh
0x180002595  and     rax, rcx
0x180002598  mov     rcx, 2B992DDFA233h
0x1800025a2  cmp     rax, rbx
0x1800025a5  cmovz   rax, rcx
0x1800025a9  mov     cs:__security_cookie, rax
0x1800025b0  mov     rbx, [rsp+30h+arg_10]
0x1800025b5  not     rax
0x1800025b8  mov     cs:__security_cookie_complement, rax
0x1800025bf  add     rsp, 30h
0x1800025c3  pop     rbp
0x1800025c4  retn
```
