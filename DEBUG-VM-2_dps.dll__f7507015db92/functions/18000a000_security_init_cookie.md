# __security_init_cookie

- ea: `0x18000a000`
- end: `0x18000a0b5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009f60`

## callees

- `0x18000a000`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a04f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a04f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a043`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a043`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a035`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a035`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a05f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a05f`

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
0x18000a000  mov     [rsp-8+arg_10], rbx
0x18000a005  push    rbp
0x18000a006  mov     rbp, rsp
0x18000a009  sub     rsp, 30h
0x18000a00d  mov     rax, cs:__security_cookie
0x18000a014  mov     rbx, 2B992DDFA232h
0x18000a01e  cmp     rax, rbx
0x18000a021  jnz     short loc_18000A0A0
0x18000a023  xor     eax, eax
0x18000a025  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000a029  mov     [rbp+var_10], rax
0x18000a02d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000a031  mov     qword ptr [rbp+PerformanceCount], rax
0x18000a035  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a03b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000a03f  mov     [rbp+var_10], rax
0x18000a043  call    cs:__imp_GetCurrentThreadId
0x18000a049  mov     eax, eax
0x18000a04b  xor     [rbp+var_10], rax
0x18000a04f  call    cs:__imp_GetCurrentProcessId
0x18000a055  mov     eax, eax
0x18000a057  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000a05b  xor     [rbp+var_10], rax
0x18000a05f  call    cs:__imp_QueryPerformanceCounter
0x18000a065  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000a068  lea     rcx, [rbp+var_10]
0x18000a06c  shl     rax, 20h
0x18000a070  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000a074  xor     rax, [rbp+var_10]
0x18000a078  xor     rax, rcx
0x18000a07b  mov     rcx, 0FFFFFFFFFFFFh
0x18000a085  and     rax, rcx
0x18000a088  mov     rcx, 2B992DDFA233h
0x18000a092  cmp     rax, rbx
0x18000a095  cmovz   rax, rcx
0x18000a099  mov     cs:__security_cookie, rax
0x18000a0a0  mov     rbx, [rsp+30h+arg_10]
0x18000a0a5  not     rax
0x18000a0a8  mov     cs:__security_cookie_complement, rax
0x18000a0af  add     rsp, 30h
0x18000a0b3  pop     rbp
0x18000a0b4  retn
```
