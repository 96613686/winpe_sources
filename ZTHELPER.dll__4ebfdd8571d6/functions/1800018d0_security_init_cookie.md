# __security_init_cookie

- ea: `0x1800018d0`
- end: `0x180001985`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001460`

## callees

- `0x1800018d0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000192f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000192f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000191f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000191f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001913`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001905`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001905`

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
0x1800018d0  mov     [rsp-8+arg_10], rbx
0x1800018d5  push    rbp
0x1800018d6  mov     rbp, rsp
0x1800018d9  sub     rsp, 30h
0x1800018dd  mov     rax, cs:__security_cookie
0x1800018e4  mov     rbx, 2B992DDFA232h
0x1800018ee  cmp     rax, rbx
0x1800018f1  jnz     short loc_180001970
0x1800018f3  xor     eax, eax
0x1800018f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800018f9  mov     [rbp+var_10], rax
0x1800018fd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001901  mov     qword ptr [rbp+PerformanceCount], rax
0x180001905  call    cs:__imp_GetSystemTimeAsFileTime
0x18000190b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000190f  mov     [rbp+var_10], rax
0x180001913  call    cs:__imp_GetCurrentThreadId
0x180001919  mov     eax, eax
0x18000191b  xor     [rbp+var_10], rax
0x18000191f  call    cs:__imp_GetCurrentProcessId
0x180001925  mov     eax, eax
0x180001927  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000192b  xor     [rbp+var_10], rax
0x18000192f  call    cs:__imp_QueryPerformanceCounter
0x180001935  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001938  lea     rcx, [rbp+var_10]
0x18000193c  shl     rax, 20h
0x180001940  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001944  xor     rax, [rbp+var_10]
0x180001948  xor     rax, rcx
0x18000194b  mov     rcx, 0FFFFFFFFFFFFh
0x180001955  and     rax, rcx
0x180001958  mov     rcx, 2B992DDFA233h
0x180001962  cmp     rax, rbx
0x180001965  cmovz   rax, rcx
0x180001969  mov     cs:__security_cookie, rax
0x180001970  mov     rbx, [rsp+30h+arg_10]
0x180001975  not     rax
0x180001978  mov     cs:__security_cookie_complement, rax
0x18000197f  add     rsp, 30h
0x180001983  pop     rbp
0x180001984  retn
```
