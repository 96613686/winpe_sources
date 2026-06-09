# __security_init_cookie

- ea: `0x1800034e4`
- end: `0x180003599`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a40`

## callees

- `0x1800034e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003533`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003533`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003543`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003543`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003519`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003519`

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
0x1800034e4  mov     [rsp-8+arg_10], rbx
0x1800034e9  push    rbp
0x1800034ea  mov     rbp, rsp
0x1800034ed  sub     rsp, 30h
0x1800034f1  mov     rax, cs:__security_cookie
0x1800034f8  mov     rbx, 2B992DDFA232h
0x180003502  cmp     rax, rbx
0x180003505  jnz     short loc_180003584
0x180003507  xor     eax, eax
0x180003509  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000350d  mov     [rbp+var_10], rax
0x180003511  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003515  mov     qword ptr [rbp+PerformanceCount], rax
0x180003519  call    cs:__imp_GetSystemTimeAsFileTime
0x18000351f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003523  mov     [rbp+var_10], rax
0x180003527  call    cs:__imp_GetCurrentThreadId
0x18000352d  mov     eax, eax
0x18000352f  xor     [rbp+var_10], rax
0x180003533  call    cs:__imp_GetCurrentProcessId
0x180003539  mov     eax, eax
0x18000353b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000353f  xor     [rbp+var_10], rax
0x180003543  call    cs:__imp_QueryPerformanceCounter
0x180003549  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000354c  lea     rcx, [rbp+var_10]
0x180003550  shl     rax, 20h
0x180003554  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003558  xor     rax, [rbp+var_10]
0x18000355c  xor     rax, rcx
0x18000355f  mov     rcx, 0FFFFFFFFFFFFh
0x180003569  and     rax, rcx
0x18000356c  mov     rcx, 2B992DDFA233h
0x180003576  cmp     rax, rbx
0x180003579  cmovz   rax, rcx
0x18000357d  mov     cs:__security_cookie, rax
0x180003584  mov     rbx, [rsp+30h+arg_10]
0x180003589  not     rax
0x18000358c  mov     cs:__security_cookie_complement, rax
0x180003593  add     rsp, 30h
0x180003597  pop     rbp
0x180003598  retn
```
