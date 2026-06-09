# __security_init_cookie

- ea: `0x180002910`
- end: `0x1800029c5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002410`

## callees

- `0x180002910`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000295f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000295f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002953`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002953`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000296f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000296f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002945`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002945`

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
0x180002910  mov     [rsp-8+arg_10], rbx
0x180002915  push    rbp
0x180002916  mov     rbp, rsp
0x180002919  sub     rsp, 30h
0x18000291d  mov     rax, cs:__security_cookie
0x180002924  mov     rbx, 2B992DDFA232h
0x18000292e  cmp     rax, rbx
0x180002931  jnz     short loc_1800029B0
0x180002933  xor     eax, eax
0x180002935  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002939  mov     [rbp+var_10], rax
0x18000293d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002941  mov     qword ptr [rbp+PerformanceCount], rax
0x180002945  call    cs:__imp_GetSystemTimeAsFileTime
0x18000294b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000294f  mov     [rbp+var_10], rax
0x180002953  call    cs:__imp_GetCurrentThreadId
0x180002959  mov     eax, eax
0x18000295b  xor     [rbp+var_10], rax
0x18000295f  call    cs:__imp_GetCurrentProcessId
0x180002965  mov     eax, eax
0x180002967  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000296b  xor     [rbp+var_10], rax
0x18000296f  call    cs:__imp_QueryPerformanceCounter
0x180002975  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002978  lea     rcx, [rbp+var_10]
0x18000297c  shl     rax, 20h
0x180002980  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002984  xor     rax, [rbp+var_10]
0x180002988  xor     rax, rcx
0x18000298b  mov     rcx, 0FFFFFFFFFFFFh
0x180002995  and     rax, rcx
0x180002998  mov     rcx, 2B992DDFA233h
0x1800029a2  cmp     rax, rbx
0x1800029a5  cmovz   rax, rcx
0x1800029a9  mov     cs:__security_cookie, rax
0x1800029b0  mov     rbx, [rsp+30h+arg_10]
0x1800029b5  not     rax
0x1800029b8  mov     cs:__security_cookie_complement, rax
0x1800029bf  add     rsp, 30h
0x1800029c3  pop     rbp
0x1800029c4  retn
```
