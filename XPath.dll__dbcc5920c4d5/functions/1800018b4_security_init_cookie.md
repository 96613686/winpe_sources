# __security_init_cookie

- ea: `0x1800018b4`
- end: `0x180001991`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001340`

## callees

- `0x1800018b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001907`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001907`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800018fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800018fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000193e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000193e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800018ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800018ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001913`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001923`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001913`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001923`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800018b4  mov     [rsp-8+arg_18], rbx
0x1800018b9  push    rbp
0x1800018ba  mov     rbp, rsp
0x1800018bd  sub     rsp, 20h
0x1800018c1  xor     eax, eax
0x1800018c3  mov     rbx, 2B992DDFA232h
0x1800018cd  mov     [rbp+arg_0], rax
0x1800018d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800018d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800018d9  mov     rax, cs:__security_cookie
0x1800018e0  cmp     rax, rbx
0x1800018e3  jnz     loc_18000197C
0x1800018e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800018ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800018f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800018f7  mov     [rbp+arg_0], rax
0x1800018fb  call    cs:__imp_GetCurrentProcessId
0x180001901  mov     eax, eax
0x180001903  xor     [rbp+arg_0], rax
0x180001907  call    cs:__imp_GetCurrentThreadId
0x18000190d  mov     eax, eax
0x18000190f  xor     [rbp+arg_0], rax
0x180001913  call    cs:__imp_GetTickCount
0x180001919  mov     eax, eax
0x18000191b  shl     rax, 18h
0x18000191f  xor     [rbp+arg_0], rax
0x180001923  call    cs:__imp_GetTickCount
0x180001929  mov     eax, eax
0x18000192b  lea     rcx, [rbp+arg_0]
0x18000192f  xor     rax, [rbp+arg_0]
0x180001933  xor     rax, rcx
0x180001936  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000193a  mov     [rbp+arg_0], rax
0x18000193e  call    cs:__imp_QueryPerformanceCounter
0x180001944  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001947  mov     rcx, 0FFFFFFFFFFFFh
0x180001951  shl     rax, 20h
0x180001955  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001959  xor     rax, [rbp+arg_0]
0x18000195d  and     rax, rcx
0x180001960  mov     rcx, rax
0x180001963  cmp     rax, rbx
0x180001966  jnz     short loc_180001975
0x180001968  mov     rax, 2B992DDFA233h
0x180001972  mov     rcx, rax
0x180001975  mov     cs:__security_cookie, rcx
0x18000197c  mov     rbx, [rsp+20h+arg_18]
0x180001981  not     rax
0x180001984  mov     cs:__security_cookie_complement, rax
0x18000198b  add     rsp, 20h
0x18000198f  pop     rbp
0x180001990  retn
```
