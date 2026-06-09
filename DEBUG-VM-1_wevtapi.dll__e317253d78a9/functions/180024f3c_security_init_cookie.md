# __security_init_cookie

- ea: `0x180024f3c`
- end: `0x180024ff1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800249a0`

## callees

- `0x180024f3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024f8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024f7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024f7f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180024f9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180024f9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024f71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024f71`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180024f3c  mov     [rsp-8+arg_10], rbx
0x180024f41  push    rbp
0x180024f42  mov     rbp, rsp
0x180024f45  sub     rsp, 30h
0x180024f49  mov     rax, cs:__security_cookie
0x180024f50  mov     rbx, 2B992DDFA232h
0x180024f5a  cmp     rax, rbx
0x180024f5d  jnz     short loc_180024FDC
0x180024f5f  xor     eax, eax
0x180024f61  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024f65  mov     [rbp+var_10], rax
0x180024f69  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180024f6d  mov     qword ptr [rbp+PerformanceCount], rax
0x180024f71  call    cs:__imp_GetSystemTimeAsFileTime
0x180024f77  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180024f7b  mov     [rbp+var_10], rax
0x180024f7f  call    cs:__imp_GetCurrentThreadId
0x180024f85  mov     eax, eax
0x180024f87  xor     [rbp+var_10], rax
0x180024f8b  call    cs:__imp_GetCurrentProcessId
0x180024f91  mov     eax, eax
0x180024f93  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180024f97  xor     [rbp+var_10], rax
0x180024f9b  call    cs:__imp_QueryPerformanceCounter
0x180024fa1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180024fa4  lea     rcx, [rbp+var_10]
0x180024fa8  shl     rax, 20h
0x180024fac  xor     rax, qword ptr [rbp+PerformanceCount]
0x180024fb0  xor     rax, [rbp+var_10]
0x180024fb4  xor     rax, rcx
0x180024fb7  mov     rcx, 0FFFFFFFFFFFFh
0x180024fc1  and     rax, rcx
0x180024fc4  mov     rcx, 2B992DDFA233h
0x180024fce  cmp     rax, rbx
0x180024fd1  cmovz   rax, rcx
0x180024fd5  mov     cs:__security_cookie, rax
0x180024fdc  mov     rbx, [rsp+30h+arg_10]
0x180024fe1  not     rax
0x180024fe4  mov     cs:__security_cookie_complement, rax
0x180024feb  add     rsp, 30h
0x180024fef  pop     rbp
0x180024ff0  retn
```
