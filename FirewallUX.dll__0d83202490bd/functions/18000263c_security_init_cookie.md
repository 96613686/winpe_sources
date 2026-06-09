# __security_init_cookie

- ea: `0x18000263c`
- end: `0x1800026f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002170`

## callees

- `0x18000263c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000267f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000267f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000268b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000268b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000269b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000269b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002671`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002671`

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
0x18000263c  mov     [rsp-8+arg_10], rbx
0x180002641  push    rbp
0x180002642  mov     rbp, rsp
0x180002645  sub     rsp, 30h
0x180002649  mov     rax, cs:__security_cookie
0x180002650  mov     rbx, 2B992DDFA232h
0x18000265a  cmp     rax, rbx
0x18000265d  jnz     short loc_1800026DC
0x18000265f  xor     eax, eax
0x180002661  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002665  mov     [rbp+var_10], rax
0x180002669  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000266d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002671  call    cs:__imp_GetSystemTimeAsFileTime
0x180002677  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000267b  mov     [rbp+var_10], rax
0x18000267f  call    cs:__imp_GetCurrentThreadId
0x180002685  mov     eax, eax
0x180002687  xor     [rbp+var_10], rax
0x18000268b  call    cs:__imp_GetCurrentProcessId
0x180002691  mov     eax, eax
0x180002693  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002697  xor     [rbp+var_10], rax
0x18000269b  call    cs:__imp_QueryPerformanceCounter
0x1800026a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800026a4  lea     rcx, [rbp+var_10]
0x1800026a8  shl     rax, 20h
0x1800026ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800026b0  xor     rax, [rbp+var_10]
0x1800026b4  xor     rax, rcx
0x1800026b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800026c1  and     rax, rcx
0x1800026c4  mov     rcx, 2B992DDFA233h
0x1800026ce  cmp     rax, rbx
0x1800026d1  cmovz   rax, rcx
0x1800026d5  mov     cs:__security_cookie, rax
0x1800026dc  mov     rbx, [rsp+30h+arg_10]
0x1800026e1  not     rax
0x1800026e4  mov     cs:__security_cookie_complement, rax
0x1800026eb  add     rsp, 30h
0x1800026ef  pop     rbp
0x1800026f0  retn
```
