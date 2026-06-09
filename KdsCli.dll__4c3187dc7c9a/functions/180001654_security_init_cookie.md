# __security_init_cookie

- ea: `0x180001654`
- end: `0x180001709`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015e0`
- `0x180004180`

## callees

- `0x180001654`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800016a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001697`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800016b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001689`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001689`

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
0x180001654  mov     [rsp-8+arg_10], rbx
0x180001659  push    rbp
0x18000165a  mov     rbp, rsp
0x18000165d  sub     rsp, 30h
0x180001661  mov     rax, cs:__security_cookie
0x180001668  mov     rbx, 2B992DDFA232h
0x180001672  cmp     rax, rbx
0x180001675  jnz     short loc_1800016F4
0x180001677  xor     eax, eax
0x180001679  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000167d  mov     [rbp+var_10], rax
0x180001681  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001685  mov     qword ptr [rbp+PerformanceCount], rax
0x180001689  call    cs:__imp_GetSystemTimeAsFileTime
0x18000168f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001693  mov     [rbp+var_10], rax
0x180001697  call    cs:__imp_GetCurrentThreadId
0x18000169d  mov     eax, eax
0x18000169f  xor     [rbp+var_10], rax
0x1800016a3  call    cs:__imp_GetCurrentProcessId
0x1800016a9  mov     eax, eax
0x1800016ab  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800016af  xor     [rbp+var_10], rax
0x1800016b3  call    cs:__imp_QueryPerformanceCounter
0x1800016b9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800016bc  lea     rcx, [rbp+var_10]
0x1800016c0  shl     rax, 20h
0x1800016c4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800016c8  xor     rax, [rbp+var_10]
0x1800016cc  xor     rax, rcx
0x1800016cf  mov     rcx, 0FFFFFFFFFFFFh
0x1800016d9  and     rax, rcx
0x1800016dc  mov     rcx, 2B992DDFA233h
0x1800016e6  cmp     rax, rbx
0x1800016e9  cmovz   rax, rcx
0x1800016ed  mov     cs:__security_cookie, rax
0x1800016f4  mov     rbx, [rsp+30h+arg_10]
0x1800016f9  not     rax
0x1800016fc  mov     cs:__security_cookie_complement, rax
0x180001703  add     rsp, 30h
0x180001707  pop     rbp
0x180001708  retn
```
