# __security_init_cookie

- ea: `0x18000261c`
- end: `0x1800026d1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002180`

## callees

- `0x18000261c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000266b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000266b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000265f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000265f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000267b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000267b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002651`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002651`

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
0x18000261c  mov     [rsp-8+arg_10], rbx
0x180002621  push    rbp
0x180002622  mov     rbp, rsp
0x180002625  sub     rsp, 30h
0x180002629  mov     rax, cs:__security_cookie
0x180002630  mov     rbx, 2B992DDFA232h
0x18000263a  cmp     rax, rbx
0x18000263d  jnz     short loc_1800026BC
0x18000263f  xor     eax, eax
0x180002641  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002645  mov     [rbp+var_10], rax
0x180002649  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000264d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002651  call    cs:__imp_GetSystemTimeAsFileTime
0x180002657  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000265b  mov     [rbp+var_10], rax
0x18000265f  call    cs:__imp_GetCurrentThreadId
0x180002665  mov     eax, eax
0x180002667  xor     [rbp+var_10], rax
0x18000266b  call    cs:__imp_GetCurrentProcessId
0x180002671  mov     eax, eax
0x180002673  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002677  xor     [rbp+var_10], rax
0x18000267b  call    cs:__imp_QueryPerformanceCounter
0x180002681  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002684  lea     rcx, [rbp+var_10]
0x180002688  shl     rax, 20h
0x18000268c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002690  xor     rax, [rbp+var_10]
0x180002694  xor     rax, rcx
0x180002697  mov     rcx, 0FFFFFFFFFFFFh
0x1800026a1  and     rax, rcx
0x1800026a4  mov     rcx, 2B992DDFA233h
0x1800026ae  cmp     rax, rbx
0x1800026b1  cmovz   rax, rcx
0x1800026b5  mov     cs:__security_cookie, rax
0x1800026bc  mov     rbx, [rsp+30h+arg_10]
0x1800026c1  not     rax
0x1800026c4  mov     cs:__security_cookie_complement, rax
0x1800026cb  add     rsp, 30h
0x1800026cf  pop     rbp
0x1800026d0  retn
```
