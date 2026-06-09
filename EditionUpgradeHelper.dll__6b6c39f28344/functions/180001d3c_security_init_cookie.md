# __security_init_cookie

- ea: `0x180001d3c`
- end: `0x180001df1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001890`

## callees

- `0x180001d3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001d7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001d8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001d8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001d71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001d71`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001d9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001d9b`

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
0x180001d3c  mov     [rsp-8+arg_10], rbx
0x180001d41  push    rbp
0x180001d42  mov     rbp, rsp
0x180001d45  sub     rsp, 30h
0x180001d49  mov     rax, cs:__security_cookie
0x180001d50  mov     rbx, 2B992DDFA232h
0x180001d5a  cmp     rax, rbx
0x180001d5d  jnz     short loc_180001DDC
0x180001d5f  xor     eax, eax
0x180001d61  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d65  mov     [rbp+var_10], rax
0x180001d69  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d6d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d71  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d77  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d7b  mov     [rbp+var_10], rax
0x180001d7f  call    cs:__imp_GetCurrentThreadId
0x180001d85  mov     eax, eax
0x180001d87  xor     [rbp+var_10], rax
0x180001d8b  call    cs:__imp_GetCurrentProcessId
0x180001d91  mov     eax, eax
0x180001d93  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001d97  xor     [rbp+var_10], rax
0x180001d9b  call    cs:__imp_QueryPerformanceCounter
0x180001da1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001da4  lea     rcx, [rbp+var_10]
0x180001da8  shl     rax, 20h
0x180001dac  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001db0  xor     rax, [rbp+var_10]
0x180001db4  xor     rax, rcx
0x180001db7  mov     rcx, 0FFFFFFFFFFFFh
0x180001dc1  and     rax, rcx
0x180001dc4  mov     rcx, 2B992DDFA233h
0x180001dce  cmp     rax, rbx
0x180001dd1  cmovz   rax, rcx
0x180001dd5  mov     cs:__security_cookie, rax
0x180001ddc  mov     rbx, [rsp+30h+arg_10]
0x180001de1  not     rax
0x180001de4  mov     cs:__security_cookie_complement, rax
0x180001deb  add     rsp, 30h
0x180001def  pop     rbp
0x180001df0  retn
```
