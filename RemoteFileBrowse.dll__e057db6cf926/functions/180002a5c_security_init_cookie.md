# __security_init_cookie

- ea: `0x180002a5c`
- end: `0x180002b11`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001fe0`

## callees

- `0x180002a5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002aab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002aab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a9f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002abb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002abb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a91`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
0x180002a5c  mov     [rsp-8+arg_10], rbx
0x180002a61  push    rbp
0x180002a62  mov     rbp, rsp
0x180002a65  sub     rsp, 30h
0x180002a69  mov     rax, cs:__security_cookie
0x180002a70  mov     rbx, 2B992DDFA232h
0x180002a7a  cmp     rax, rbx
0x180002a7d  jnz     short loc_180002AFC
0x180002a7f  xor     eax, eax
0x180002a81  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002a85  mov     [rbp+var_10], rax
0x180002a89  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002a8d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002a91  call    cs:__imp_GetSystemTimeAsFileTime
0x180002a97  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002a9b  mov     [rbp+var_10], rax
0x180002a9f  call    cs:__imp_GetCurrentThreadId
0x180002aa5  mov     eax, eax
0x180002aa7  xor     [rbp+var_10], rax
0x180002aab  call    cs:__imp_GetCurrentProcessId
0x180002ab1  mov     eax, eax
0x180002ab3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002ab7  xor     [rbp+var_10], rax
0x180002abb  call    cs:__imp_QueryPerformanceCounter
0x180002ac1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002ac4  lea     rcx, [rbp+var_10]
0x180002ac8  shl     rax, 20h
0x180002acc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002ad0  xor     rax, [rbp+var_10]
0x180002ad4  xor     rax, rcx
0x180002ad7  mov     rcx, 0FFFFFFFFFFFFh
0x180002ae1  and     rax, rcx
0x180002ae4  mov     rcx, 2B992DDFA233h
0x180002aee  cmp     rax, rbx
0x180002af1  cmovz   rax, rcx
0x180002af5  mov     cs:__security_cookie, rax
0x180002afc  mov     rbx, [rsp+30h+arg_10]
0x180002b01  not     rax
0x180002b04  mov     cs:__security_cookie_complement, rax
0x180002b0b  add     rsp, 30h
0x180002b0f  pop     rbp
0x180002b10  retn
```
