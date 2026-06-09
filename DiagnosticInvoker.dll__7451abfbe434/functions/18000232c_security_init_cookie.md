# __security_init_cookie

- ea: `0x18000232c`
- end: `0x1800023e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001dd0`

## callees

- `0x18000232c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000236f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000236f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000237b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000237b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000238b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000238b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002361`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002361`

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
0x18000232c  mov     [rsp-8+arg_10], rbx
0x180002331  push    rbp
0x180002332  mov     rbp, rsp
0x180002335  sub     rsp, 30h
0x180002339  mov     rax, cs:__security_cookie
0x180002340  mov     rbx, 2B992DDFA232h
0x18000234a  cmp     rax, rbx
0x18000234d  jnz     short loc_1800023CC
0x18000234f  xor     eax, eax
0x180002351  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002355  mov     [rbp+var_10], rax
0x180002359  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000235d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002361  call    cs:__imp_GetSystemTimeAsFileTime
0x180002367  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000236b  mov     [rbp+var_10], rax
0x18000236f  call    cs:__imp_GetCurrentThreadId
0x180002375  mov     eax, eax
0x180002377  xor     [rbp+var_10], rax
0x18000237b  call    cs:__imp_GetCurrentProcessId
0x180002381  mov     eax, eax
0x180002383  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002387  xor     [rbp+var_10], rax
0x18000238b  call    cs:__imp_QueryPerformanceCounter
0x180002391  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002394  lea     rcx, [rbp+var_10]
0x180002398  shl     rax, 20h
0x18000239c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800023a0  xor     rax, [rbp+var_10]
0x1800023a4  xor     rax, rcx
0x1800023a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800023b1  and     rax, rcx
0x1800023b4  mov     rcx, 2B992DDFA233h
0x1800023be  cmp     rax, rbx
0x1800023c1  cmovz   rax, rcx
0x1800023c5  mov     cs:__security_cookie, rax
0x1800023cc  mov     rbx, [rsp+30h+arg_10]
0x1800023d1  not     rax
0x1800023d4  mov     cs:__security_cookie_complement, rax
0x1800023db  add     rsp, 30h
0x1800023df  pop     rbp
0x1800023e0  retn
```
