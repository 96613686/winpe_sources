# __security_init_cookie

- ea: `0x1800041fc`
- end: `0x1800042b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a60`

## callees

- `0x1800041fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000424b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000424b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000423f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000423f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000425b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000425b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004231`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004231`

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
0x1800041fc  mov     [rsp-8+arg_10], rbx
0x180004201  push    rbp
0x180004202  mov     rbp, rsp
0x180004205  sub     rsp, 30h
0x180004209  mov     rax, cs:__security_cookie
0x180004210  mov     rbx, 2B992DDFA232h
0x18000421a  cmp     rax, rbx
0x18000421d  jnz     short loc_18000429C
0x18000421f  xor     eax, eax
0x180004221  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004225  mov     [rbp+var_10], rax
0x180004229  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000422d  mov     qword ptr [rbp+PerformanceCount], rax
0x180004231  call    cs:__imp_GetSystemTimeAsFileTime
0x180004237  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000423b  mov     [rbp+var_10], rax
0x18000423f  call    cs:__imp_GetCurrentThreadId
0x180004245  mov     eax, eax
0x180004247  xor     [rbp+var_10], rax
0x18000424b  call    cs:__imp_GetCurrentProcessId
0x180004251  mov     eax, eax
0x180004253  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004257  xor     [rbp+var_10], rax
0x18000425b  call    cs:__imp_QueryPerformanceCounter
0x180004261  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004264  lea     rcx, [rbp+var_10]
0x180004268  shl     rax, 20h
0x18000426c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004270  xor     rax, [rbp+var_10]
0x180004274  xor     rax, rcx
0x180004277  mov     rcx, 0FFFFFFFFFFFFh
0x180004281  and     rax, rcx
0x180004284  mov     rcx, 2B992DDFA233h
0x18000428e  cmp     rax, rbx
0x180004291  cmovz   rax, rcx
0x180004295  mov     cs:__security_cookie, rax
0x18000429c  mov     rbx, [rsp+30h+arg_10]
0x1800042a1  not     rax
0x1800042a4  mov     cs:__security_cookie_complement, rax
0x1800042ab  add     rsp, 30h
0x1800042af  pop     rbp
0x1800042b0  retn
```
