# __security_init_cookie

- ea: `0x180002a60`
- end: `0x180002b15`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800024d0`

## callees

- `0x180002a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002aa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002aa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002aaf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002aaf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002abf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002abf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a95`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a95`

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
0x180002a60  mov     [rsp-8+arg_10], rbx
0x180002a65  push    rbp
0x180002a66  mov     rbp, rsp
0x180002a69  sub     rsp, 30h
0x180002a6d  mov     rax, cs:__security_cookie
0x180002a74  mov     rbx, 2B992DDFA232h
0x180002a7e  cmp     rax, rbx
0x180002a81  jnz     short loc_180002B00
0x180002a83  xor     eax, eax
0x180002a85  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002a89  mov     [rbp+var_10], rax
0x180002a8d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002a91  mov     qword ptr [rbp+PerformanceCount], rax
0x180002a95  call    cs:__imp_GetSystemTimeAsFileTime
0x180002a9b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002a9f  mov     [rbp+var_10], rax
0x180002aa3  call    cs:__imp_GetCurrentThreadId
0x180002aa9  mov     eax, eax
0x180002aab  xor     [rbp+var_10], rax
0x180002aaf  call    cs:__imp_GetCurrentProcessId
0x180002ab5  mov     eax, eax
0x180002ab7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002abb  xor     [rbp+var_10], rax
0x180002abf  call    cs:__imp_QueryPerformanceCounter
0x180002ac5  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002ac8  lea     rcx, [rbp+var_10]
0x180002acc  shl     rax, 20h
0x180002ad0  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002ad4  xor     rax, [rbp+var_10]
0x180002ad8  xor     rax, rcx
0x180002adb  mov     rcx, 0FFFFFFFFFFFFh
0x180002ae5  and     rax, rcx
0x180002ae8  mov     rcx, 2B992DDFA233h
0x180002af2  cmp     rax, rbx
0x180002af5  cmovz   rax, rcx
0x180002af9  mov     cs:__security_cookie, rax
0x180002b00  mov     rbx, [rsp+30h+arg_10]
0x180002b05  not     rax
0x180002b08  mov     cs:__security_cookie_complement, rax
0x180002b0f  add     rsp, 30h
0x180002b13  pop     rbp
0x180002b14  retn
```
