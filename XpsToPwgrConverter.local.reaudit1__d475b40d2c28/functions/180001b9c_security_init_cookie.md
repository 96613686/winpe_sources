# __security_init_cookie

- ea: `0x180001b9c`
- end: `0x180001c51`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001710`

## callees

- `0x180001b9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001bdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001bdf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001bfb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001bfb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001bd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001bd1`

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
0x180001b9c  mov     [rsp-8+arg_10], rbx
0x180001ba1  push    rbp
0x180001ba2  mov     rbp, rsp
0x180001ba5  sub     rsp, 30h
0x180001ba9  mov     rax, cs:__security_cookie
0x180001bb0  mov     rbx, 2B992DDFA232h
0x180001bba  cmp     rax, rbx
0x180001bbd  jnz     short loc_180001C3C
0x180001bbf  xor     eax, eax
0x180001bc1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001bc5  mov     [rbp+var_10], rax
0x180001bc9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001bcd  mov     qword ptr [rbp+PerformanceCount], rax
0x180001bd1  call    cs:__imp_GetSystemTimeAsFileTime
0x180001bd7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001bdb  mov     [rbp+var_10], rax
0x180001bdf  call    cs:__imp_GetCurrentThreadId
0x180001be5  mov     eax, eax
0x180001be7  xor     [rbp+var_10], rax
0x180001beb  call    cs:__imp_GetCurrentProcessId
0x180001bf1  mov     eax, eax
0x180001bf3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001bf7  xor     [rbp+var_10], rax
0x180001bfb  call    cs:__imp_QueryPerformanceCounter
0x180001c01  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c04  lea     rcx, [rbp+var_10]
0x180001c08  shl     rax, 20h
0x180001c0c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001c10  xor     rax, [rbp+var_10]
0x180001c14  xor     rax, rcx
0x180001c17  mov     rcx, 0FFFFFFFFFFFFh
0x180001c21  and     rax, rcx
0x180001c24  mov     rcx, 2B992DDFA233h
0x180001c2e  cmp     rax, rbx
0x180001c31  cmovz   rax, rcx
0x180001c35  mov     cs:__security_cookie, rax
0x180001c3c  mov     rbx, [rsp+30h+arg_10]
0x180001c41  not     rax
0x180001c44  mov     cs:__security_cookie_complement, rax
0x180001c4b  add     rsp, 30h
0x180001c4f  pop     rbp
0x180001c50  retn
```
