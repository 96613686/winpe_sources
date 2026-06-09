# __security_init_cookie

- ea: `0x180004378`
- end: `0x18000442d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003890`

## callees

- `0x180004378`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800043c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800043c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800043d7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800043d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800043ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800043ad`

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
0x180004378  mov     [rsp-8+arg_10], rbx
0x18000437d  push    rbp
0x18000437e  mov     rbp, rsp
0x180004381  sub     rsp, 30h
0x180004385  mov     rax, cs:__security_cookie
0x18000438c  mov     rbx, 2B992DDFA232h
0x180004396  cmp     rax, rbx
0x180004399  jnz     short loc_180004418
0x18000439b  xor     eax, eax
0x18000439d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800043a1  mov     [rbp+var_10], rax
0x1800043a5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800043a9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800043ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800043b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800043b7  mov     [rbp+var_10], rax
0x1800043bb  call    cs:__imp_GetCurrentThreadId
0x1800043c1  mov     eax, eax
0x1800043c3  xor     [rbp+var_10], rax
0x1800043c7  call    cs:__imp_GetCurrentProcessId
0x1800043cd  mov     eax, eax
0x1800043cf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800043d3  xor     [rbp+var_10], rax
0x1800043d7  call    cs:__imp_QueryPerformanceCounter
0x1800043dd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800043e0  lea     rcx, [rbp+var_10]
0x1800043e4  shl     rax, 20h
0x1800043e8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800043ec  xor     rax, [rbp+var_10]
0x1800043f0  xor     rax, rcx
0x1800043f3  mov     rcx, 0FFFFFFFFFFFFh
0x1800043fd  and     rax, rcx
0x180004400  mov     rcx, 2B992DDFA233h
0x18000440a  cmp     rax, rbx
0x18000440d  cmovz   rax, rcx
0x180004411  mov     cs:__security_cookie, rax
0x180004418  mov     rbx, [rsp+30h+arg_10]
0x18000441d  not     rax
0x180004420  mov     cs:__security_cookie_complement, rax
0x180004427  add     rsp, 30h
0x18000442b  pop     rbp
0x18000442c  retn
```
