# __security_init_cookie

- ea: `0x180001a2c`
- end: `0x180001ae1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015d0`

## callees

- `0x180001a2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a8b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a61`

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
0x180001a2c  mov     [rsp-8+arg_10], rbx
0x180001a31  push    rbp
0x180001a32  mov     rbp, rsp
0x180001a35  sub     rsp, 30h
0x180001a39  mov     rax, cs:__security_cookie
0x180001a40  mov     rbx, 2B992DDFA232h
0x180001a4a  cmp     rax, rbx
0x180001a4d  jnz     short loc_180001ACC
0x180001a4f  xor     eax, eax
0x180001a51  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a55  mov     [rbp+var_10], rax
0x180001a59  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a5d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a61  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a67  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a6b  mov     [rbp+var_10], rax
0x180001a6f  call    cs:__imp_GetCurrentThreadId
0x180001a75  mov     eax, eax
0x180001a77  xor     [rbp+var_10], rax
0x180001a7b  call    cs:__imp_GetCurrentProcessId
0x180001a81  mov     eax, eax
0x180001a83  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a87  xor     [rbp+var_10], rax
0x180001a8b  call    cs:__imp_QueryPerformanceCounter
0x180001a91  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a94  lea     rcx, [rbp+var_10]
0x180001a98  shl     rax, 20h
0x180001a9c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001aa0  xor     rax, [rbp+var_10]
0x180001aa4  xor     rax, rcx
0x180001aa7  mov     rcx, 0FFFFFFFFFFFFh
0x180001ab1  and     rax, rcx
0x180001ab4  mov     rcx, 2B992DDFA233h
0x180001abe  cmp     rax, rbx
0x180001ac1  cmovz   rax, rcx
0x180001ac5  mov     cs:__security_cookie, rax
0x180001acc  mov     rbx, [rsp+30h+arg_10]
0x180001ad1  not     rax
0x180001ad4  mov     cs:__security_cookie_complement, rax
0x180001adb  add     rsp, 30h
0x180001adf  pop     rbp
0x180001ae0  retn
```
