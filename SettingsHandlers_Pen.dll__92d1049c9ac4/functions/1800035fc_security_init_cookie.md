# __security_init_cookie

- ea: `0x1800035fc`
- end: `0x1800036b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003090`

## callees

- `0x1800035fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000364b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000364b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000363f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000363f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000365b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000365b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003631`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003631`

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
0x1800035fc  mov     [rsp-8+arg_10], rbx
0x180003601  push    rbp
0x180003602  mov     rbp, rsp
0x180003605  sub     rsp, 30h
0x180003609  mov     rax, cs:__security_cookie
0x180003610  mov     rbx, 2B992DDFA232h
0x18000361a  cmp     rax, rbx
0x18000361d  jnz     short loc_18000369C
0x18000361f  xor     eax, eax
0x180003621  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003625  mov     [rbp+var_10], rax
0x180003629  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000362d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003631  call    cs:__imp_GetSystemTimeAsFileTime
0x180003637  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000363b  mov     [rbp+var_10], rax
0x18000363f  call    cs:__imp_GetCurrentThreadId
0x180003645  mov     eax, eax
0x180003647  xor     [rbp+var_10], rax
0x18000364b  call    cs:__imp_GetCurrentProcessId
0x180003651  mov     eax, eax
0x180003653  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003657  xor     [rbp+var_10], rax
0x18000365b  call    cs:__imp_QueryPerformanceCounter
0x180003661  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003664  lea     rcx, [rbp+var_10]
0x180003668  shl     rax, 20h
0x18000366c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003670  xor     rax, [rbp+var_10]
0x180003674  xor     rax, rcx
0x180003677  mov     rcx, 0FFFFFFFFFFFFh
0x180003681  and     rax, rcx
0x180003684  mov     rcx, 2B992DDFA233h
0x18000368e  cmp     rax, rbx
0x180003691  cmovz   rax, rcx
0x180003695  mov     cs:__security_cookie, rax
0x18000369c  mov     rbx, [rsp+30h+arg_10]
0x1800036a1  not     rax
0x1800036a4  mov     cs:__security_cookie_complement, rax
0x1800036ab  add     rsp, 30h
0x1800036af  pop     rbp
0x1800036b0  retn
```
