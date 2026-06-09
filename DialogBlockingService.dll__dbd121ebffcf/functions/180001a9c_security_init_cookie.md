# __security_init_cookie

- ea: `0x180001a9c`
- end: `0x180001b51`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015d0`

## callees

- `0x180001a9c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001aeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001aeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001adf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001afb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ad1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ad1`

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
0x180001a9c  mov     [rsp-8+arg_10], rbx
0x180001aa1  push    rbp
0x180001aa2  mov     rbp, rsp
0x180001aa5  sub     rsp, 30h
0x180001aa9  mov     rax, cs:__security_cookie
0x180001ab0  mov     rbx, 2B992DDFA232h
0x180001aba  cmp     rax, rbx
0x180001abd  jnz     short loc_180001B3C
0x180001abf  xor     eax, eax
0x180001ac1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001ac5  mov     [rbp+var_10], rax
0x180001ac9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001acd  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ad1  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ad7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001adb  mov     [rbp+var_10], rax
0x180001adf  call    cs:__imp_GetCurrentThreadId
0x180001ae5  mov     eax, eax
0x180001ae7  xor     [rbp+var_10], rax
0x180001aeb  call    cs:__imp_GetCurrentProcessId
0x180001af1  mov     eax, eax
0x180001af3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001af7  xor     [rbp+var_10], rax
0x180001afb  call    cs:__imp_QueryPerformanceCounter
0x180001b01  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001b04  lea     rcx, [rbp+var_10]
0x180001b08  shl     rax, 20h
0x180001b0c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b10  xor     rax, [rbp+var_10]
0x180001b14  xor     rax, rcx
0x180001b17  mov     rcx, 0FFFFFFFFFFFFh
0x180001b21  and     rax, rcx
0x180001b24  mov     rcx, 2B992DDFA233h
0x180001b2e  cmp     rax, rbx
0x180001b31  cmovz   rax, rcx
0x180001b35  mov     cs:__security_cookie, rax
0x180001b3c  mov     rbx, [rsp+30h+arg_10]
0x180001b41  not     rax
0x180001b44  mov     cs:__security_cookie_complement, rax
0x180001b4b  add     rsp, 30h
0x180001b4f  pop     rbp
0x180001b50  retn
```
