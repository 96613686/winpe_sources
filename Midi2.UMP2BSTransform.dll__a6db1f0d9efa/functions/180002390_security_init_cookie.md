# __security_init_cookie

- ea: `0x180002390`
- end: `0x180002445`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e90`

## callees

- `0x180002390`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800023ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800023ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800023c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800023c5`

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
0x180002390  mov     [rsp-8+arg_10], rbx
0x180002395  push    rbp
0x180002396  mov     rbp, rsp
0x180002399  sub     rsp, 30h
0x18000239d  mov     rax, cs:__security_cookie
0x1800023a4  mov     rbx, 2B992DDFA232h
0x1800023ae  cmp     rax, rbx
0x1800023b1  jnz     short loc_180002430
0x1800023b3  xor     eax, eax
0x1800023b5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800023b9  mov     [rbp+var_10], rax
0x1800023bd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800023c1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800023c5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800023cb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800023cf  mov     [rbp+var_10], rax
0x1800023d3  call    cs:__imp_GetCurrentThreadId
0x1800023d9  mov     eax, eax
0x1800023db  xor     [rbp+var_10], rax
0x1800023df  call    cs:__imp_GetCurrentProcessId
0x1800023e5  mov     eax, eax
0x1800023e7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800023eb  xor     [rbp+var_10], rax
0x1800023ef  call    cs:__imp_QueryPerformanceCounter
0x1800023f5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800023f8  lea     rcx, [rbp+var_10]
0x1800023fc  shl     rax, 20h
0x180002400  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002404  xor     rax, [rbp+var_10]
0x180002408  xor     rax, rcx
0x18000240b  mov     rcx, 0FFFFFFFFFFFFh
0x180002415  and     rax, rcx
0x180002418  mov     rcx, 2B992DDFA233h
0x180002422  cmp     rax, rbx
0x180002425  cmovz   rax, rcx
0x180002429  mov     cs:__security_cookie, rax
0x180002430  mov     rbx, [rsp+30h+arg_10]
0x180002435  not     rax
0x180002438  mov     cs:__security_cookie_complement, rax
0x18000243f  add     rsp, 30h
0x180002443  pop     rbp
0x180002444  retn
```
