# __security_init_cookie

- ea: `0x18000364c`
- end: `0x180003701`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002cf0`

## callees

- `0x18000364c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000368f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000368f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000369b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000369b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800036ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800036ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003681`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003681`

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
0x18000364c  mov     [rsp-8+arg_10], rbx
0x180003651  push    rbp
0x180003652  mov     rbp, rsp
0x180003655  sub     rsp, 30h
0x180003659  mov     rax, cs:__security_cookie
0x180003660  mov     rbx, 2B992DDFA232h
0x18000366a  cmp     rax, rbx
0x18000366d  jnz     short loc_1800036EC
0x18000366f  xor     eax, eax
0x180003671  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003675  mov     [rbp+var_10], rax
0x180003679  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000367d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003681  call    cs:__imp_GetSystemTimeAsFileTime
0x180003687  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000368b  mov     [rbp+var_10], rax
0x18000368f  call    cs:__imp_GetCurrentThreadId
0x180003695  mov     eax, eax
0x180003697  xor     [rbp+var_10], rax
0x18000369b  call    cs:__imp_GetCurrentProcessId
0x1800036a1  mov     eax, eax
0x1800036a3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800036a7  xor     [rbp+var_10], rax
0x1800036ab  call    cs:__imp_QueryPerformanceCounter
0x1800036b1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800036b4  lea     rcx, [rbp+var_10]
0x1800036b8  shl     rax, 20h
0x1800036bc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800036c0  xor     rax, [rbp+var_10]
0x1800036c4  xor     rax, rcx
0x1800036c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800036d1  and     rax, rcx
0x1800036d4  mov     rcx, 2B992DDFA233h
0x1800036de  cmp     rax, rbx
0x1800036e1  cmovz   rax, rcx
0x1800036e5  mov     cs:__security_cookie, rax
0x1800036ec  mov     rbx, [rsp+30h+arg_10]
0x1800036f1  not     rax
0x1800036f4  mov     cs:__security_cookie_complement, rax
0x1800036fb  add     rsp, 30h
0x1800036ff  pop     rbp
0x180003700  retn
```
