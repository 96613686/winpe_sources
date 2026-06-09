# __security_init_cookie

- ea: `0x180001d28`
- end: `0x180001ddd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c60`

## callees

- `0x180001d28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001d77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001d77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001d87`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001d87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001d5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001d5d`

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
0x180001d28  mov     [rsp-8+arg_10], rbx
0x180001d2d  push    rbp
0x180001d2e  mov     rbp, rsp
0x180001d31  sub     rsp, 30h
0x180001d35  mov     rax, cs:__security_cookie
0x180001d3c  mov     rbx, 2B992DDFA232h
0x180001d46  cmp     rax, rbx
0x180001d49  jnz     short loc_180001DC8
0x180001d4b  xor     eax, eax
0x180001d4d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d51  mov     [rbp+var_10], rax
0x180001d55  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d59  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d5d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d63  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d67  mov     [rbp+var_10], rax
0x180001d6b  call    cs:__imp_GetCurrentThreadId
0x180001d71  mov     eax, eax
0x180001d73  xor     [rbp+var_10], rax
0x180001d77  call    cs:__imp_GetCurrentProcessId
0x180001d7d  mov     eax, eax
0x180001d7f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001d83  xor     [rbp+var_10], rax
0x180001d87  call    cs:__imp_QueryPerformanceCounter
0x180001d8d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001d90  lea     rcx, [rbp+var_10]
0x180001d94  shl     rax, 20h
0x180001d98  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001d9c  xor     rax, [rbp+var_10]
0x180001da0  xor     rax, rcx
0x180001da3  mov     rcx, 0FFFFFFFFFFFFh
0x180001dad  and     rax, rcx
0x180001db0  mov     rcx, 2B992DDFA233h
0x180001dba  cmp     rax, rbx
0x180001dbd  cmovz   rax, rcx
0x180001dc1  mov     cs:__security_cookie, rax
0x180001dc8  mov     rbx, [rsp+30h+arg_10]
0x180001dcd  not     rax
0x180001dd0  mov     cs:__security_cookie_complement, rax
0x180001dd7  add     rsp, 30h
0x180001ddb  pop     rbp
0x180001ddc  retn
```
