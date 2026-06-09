# __security_init_cookie

- ea: `0x1800018d4`
- end: `0x180001989`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001860`

## callees

- `0x1800018d4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001933`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001933`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001917`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001917`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001923`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001909`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001909`

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
0x1800018d4  mov     [rsp-8+arg_10], rbx
0x1800018d9  push    rbp
0x1800018da  mov     rbp, rsp
0x1800018dd  sub     rsp, 30h
0x1800018e1  mov     rax, cs:__security_cookie
0x1800018e8  mov     rbx, 2B992DDFA232h
0x1800018f2  cmp     rax, rbx
0x1800018f5  jnz     short loc_180001974
0x1800018f7  xor     eax, eax
0x1800018f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800018fd  mov     [rbp+var_10], rax
0x180001901  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001905  mov     qword ptr [rbp+PerformanceCount], rax
0x180001909  call    cs:__imp_GetSystemTimeAsFileTime
0x18000190f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001913  mov     [rbp+var_10], rax
0x180001917  call    cs:__imp_GetCurrentThreadId
0x18000191d  mov     eax, eax
0x18000191f  xor     [rbp+var_10], rax
0x180001923  call    cs:__imp_GetCurrentProcessId
0x180001929  mov     eax, eax
0x18000192b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000192f  xor     [rbp+var_10], rax
0x180001933  call    cs:__imp_QueryPerformanceCounter
0x180001939  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000193c  lea     rcx, [rbp+var_10]
0x180001940  shl     rax, 20h
0x180001944  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001948  xor     rax, [rbp+var_10]
0x18000194c  xor     rax, rcx
0x18000194f  mov     rcx, 0FFFFFFFFFFFFh
0x180001959  and     rax, rcx
0x18000195c  mov     rcx, 2B992DDFA233h
0x180001966  cmp     rax, rbx
0x180001969  cmovz   rax, rcx
0x18000196d  mov     cs:__security_cookie, rax
0x180001974  mov     rbx, [rsp+30h+arg_10]
0x180001979  not     rax
0x18000197c  mov     cs:__security_cookie_complement, rax
0x180001983  add     rsp, 30h
0x180001987  pop     rbp
0x180001988  retn
```
