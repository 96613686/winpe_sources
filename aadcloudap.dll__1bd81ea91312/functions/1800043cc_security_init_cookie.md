# __security_init_cookie

- ea: `0x1800043cc`
- end: `0x180004481`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003bd0`

## callees

- `0x1800043cc`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000442b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000442b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000441b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000441b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000440f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000440f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004401`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004401`

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
0x1800043cc  mov     [rsp-8+arg_10], rbx
0x1800043d1  push    rbp
0x1800043d2  mov     rbp, rsp
0x1800043d5  sub     rsp, 30h
0x1800043d9  mov     rax, cs:__security_cookie
0x1800043e0  mov     rbx, 2B992DDFA232h
0x1800043ea  cmp     rax, rbx
0x1800043ed  jnz     short loc_18000446C
0x1800043ef  xor     eax, eax
0x1800043f1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800043f5  mov     [rbp+var_10], rax
0x1800043f9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800043fd  mov     qword ptr [rbp+PerformanceCount], rax
0x180004401  call    cs:__imp_GetSystemTimeAsFileTime
0x180004407  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000440b  mov     [rbp+var_10], rax
0x18000440f  call    cs:__imp_GetCurrentThreadId
0x180004415  mov     eax, eax
0x180004417  xor     [rbp+var_10], rax
0x18000441b  call    cs:__imp_GetCurrentProcessId
0x180004421  mov     eax, eax
0x180004423  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004427  xor     [rbp+var_10], rax
0x18000442b  call    cs:__imp_QueryPerformanceCounter
0x180004431  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004434  lea     rcx, [rbp+var_10]
0x180004438  shl     rax, 20h
0x18000443c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004440  xor     rax, [rbp+var_10]
0x180004444  xor     rax, rcx
0x180004447  mov     rcx, 0FFFFFFFFFFFFh
0x180004451  and     rax, rcx
0x180004454  mov     rcx, 2B992DDFA233h
0x18000445e  cmp     rax, rbx
0x180004461  cmovz   rax, rcx
0x180004465  mov     cs:__security_cookie, rax
0x18000446c  mov     rbx, [rsp+30h+arg_10]
0x180004471  not     rax
0x180004474  mov     cs:__security_cookie_complement, rax
0x18000447b  add     rsp, 30h
0x18000447f  pop     rbp
0x180004480  retn
```
