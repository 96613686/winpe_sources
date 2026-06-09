# __security_init_cookie

- ea: `0x18000767c`
- end: `0x180007731`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007220`

## callees

- `0x18000767c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800076cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800076cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800076bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800076db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800076db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800076b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800076b1`

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
0x18000767c  mov     [rsp-8+arg_10], rbx
0x180007681  push    rbp
0x180007682  mov     rbp, rsp
0x180007685  sub     rsp, 30h
0x180007689  mov     rax, cs:__security_cookie
0x180007690  mov     rbx, 2B992DDFA232h
0x18000769a  cmp     rax, rbx
0x18000769d  jnz     short loc_18000771C
0x18000769f  xor     eax, eax
0x1800076a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800076a5  mov     [rbp+var_10], rax
0x1800076a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800076ad  mov     qword ptr [rbp+PerformanceCount], rax
0x1800076b1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800076b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800076bb  mov     [rbp+var_10], rax
0x1800076bf  call    cs:__imp_GetCurrentThreadId
0x1800076c5  mov     eax, eax
0x1800076c7  xor     [rbp+var_10], rax
0x1800076cb  call    cs:__imp_GetCurrentProcessId
0x1800076d1  mov     eax, eax
0x1800076d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800076d7  xor     [rbp+var_10], rax
0x1800076db  call    cs:__imp_QueryPerformanceCounter
0x1800076e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800076e4  lea     rcx, [rbp+var_10]
0x1800076e8  shl     rax, 20h
0x1800076ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800076f0  xor     rax, [rbp+var_10]
0x1800076f4  xor     rax, rcx
0x1800076f7  mov     rcx, 0FFFFFFFFFFFFh
0x180007701  and     rax, rcx
0x180007704  mov     rcx, 2B992DDFA233h
0x18000770e  cmp     rax, rbx
0x180007711  cmovz   rax, rcx
0x180007715  mov     cs:__security_cookie, rax
0x18000771c  mov     rbx, [rsp+30h+arg_10]
0x180007721  not     rax
0x180007724  mov     cs:__security_cookie_complement, rax
0x18000772b  add     rsp, 30h
0x18000772f  pop     rbp
0x180007730  retn
```
