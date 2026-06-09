# __security_init_cookie

- ea: `0x180001f58`
- end: `0x18000200d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001770`

## callees

- `0x180001f58`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001f9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001fb7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001fb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001f8d`

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
0x180001f58  mov     [rsp-8+arg_10], rbx
0x180001f5d  push    rbp
0x180001f5e  mov     rbp, rsp
0x180001f61  sub     rsp, 30h
0x180001f65  mov     rax, cs:__security_cookie
0x180001f6c  mov     rbx, 2B992DDFA232h
0x180001f76  cmp     rax, rbx
0x180001f79  jnz     short loc_180001FF8
0x180001f7b  xor     eax, eax
0x180001f7d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f81  mov     [rbp+var_10], rax
0x180001f85  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f89  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f8d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001f93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001f97  mov     [rbp+var_10], rax
0x180001f9b  call    cs:__imp_GetCurrentThreadId
0x180001fa1  mov     eax, eax
0x180001fa3  xor     [rbp+var_10], rax
0x180001fa7  call    cs:__imp_GetCurrentProcessId
0x180001fad  mov     eax, eax
0x180001faf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001fb3  xor     [rbp+var_10], rax
0x180001fb7  call    cs:__imp_QueryPerformanceCounter
0x180001fbd  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001fc0  lea     rcx, [rbp+var_10]
0x180001fc4  shl     rax, 20h
0x180001fc8  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001fcc  xor     rax, [rbp+var_10]
0x180001fd0  xor     rax, rcx
0x180001fd3  mov     rcx, 0FFFFFFFFFFFFh
0x180001fdd  and     rax, rcx
0x180001fe0  mov     rcx, 2B992DDFA233h
0x180001fea  cmp     rax, rbx
0x180001fed  cmovz   rax, rcx
0x180001ff1  mov     cs:__security_cookie, rax
0x180001ff8  mov     rbx, [rsp+30h+arg_10]
0x180001ffd  not     rax
0x180002000  mov     cs:__security_cookie_complement, rax
0x180002007  add     rsp, 30h
0x18000200b  pop     rbp
0x18000200c  retn
```
