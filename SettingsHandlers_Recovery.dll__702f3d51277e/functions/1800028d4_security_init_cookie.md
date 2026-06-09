# __security_init_cookie

- ea: `0x1800028d4`
- end: `0x180002989`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002300`

## callees

- `0x1800028d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002917`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002917`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002909`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002909`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002933`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002933`

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
0x1800028d4  mov     [rsp-8+arg_10], rbx
0x1800028d9  push    rbp
0x1800028da  mov     rbp, rsp
0x1800028dd  sub     rsp, 30h
0x1800028e1  mov     rax, cs:__security_cookie
0x1800028e8  mov     rbx, 2B992DDFA232h
0x1800028f2  cmp     rax, rbx
0x1800028f5  jnz     short loc_180002974
0x1800028f7  xor     eax, eax
0x1800028f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800028fd  mov     [rbp+var_10], rax
0x180002901  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002905  mov     qword ptr [rbp+PerformanceCount], rax
0x180002909  call    cs:__imp_GetSystemTimeAsFileTime
0x18000290f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002913  mov     [rbp+var_10], rax
0x180002917  call    cs:__imp_GetCurrentThreadId
0x18000291d  mov     eax, eax
0x18000291f  xor     [rbp+var_10], rax
0x180002923  call    cs:__imp_GetCurrentProcessId
0x180002929  mov     eax, eax
0x18000292b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000292f  xor     [rbp+var_10], rax
0x180002933  call    cs:__imp_QueryPerformanceCounter
0x180002939  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000293c  lea     rcx, [rbp+var_10]
0x180002940  shl     rax, 20h
0x180002944  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002948  xor     rax, [rbp+var_10]
0x18000294c  xor     rax, rcx
0x18000294f  mov     rcx, 0FFFFFFFFFFFFh
0x180002959  and     rax, rcx
0x18000295c  mov     rcx, 2B992DDFA233h
0x180002966  cmp     rax, rbx
0x180002969  cmovz   rax, rcx
0x18000296d  mov     cs:__security_cookie, rax
0x180002974  mov     rbx, [rsp+30h+arg_10]
0x180002979  not     rax
0x18000297c  mov     cs:__security_cookie_complement, rax
0x180002983  add     rsp, 30h
0x180002987  pop     rbp
0x180002988  retn
```
