# __security_init_cookie

- ea: `0x180002a64`
- end: `0x180002b19`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022a0`

## callees

- `0x180002a64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ab3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ab3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002aa7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a99`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002ac3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002ac3`

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
0x180002a64  mov     [rsp-8+arg_10], rbx
0x180002a69  push    rbp
0x180002a6a  mov     rbp, rsp
0x180002a6d  sub     rsp, 30h
0x180002a71  mov     rax, cs:__security_cookie
0x180002a78  mov     rbx, 2B992DDFA232h
0x180002a82  cmp     rax, rbx
0x180002a85  jnz     short loc_180002B04
0x180002a87  xor     eax, eax
0x180002a89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002a8d  mov     [rbp+var_10], rax
0x180002a91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002a95  mov     qword ptr [rbp+PerformanceCount], rax
0x180002a99  call    cs:__imp_GetSystemTimeAsFileTime
0x180002a9f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002aa3  mov     [rbp+var_10], rax
0x180002aa7  call    cs:__imp_GetCurrentThreadId
0x180002aad  mov     eax, eax
0x180002aaf  xor     [rbp+var_10], rax
0x180002ab3  call    cs:__imp_GetCurrentProcessId
0x180002ab9  mov     eax, eax
0x180002abb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002abf  xor     [rbp+var_10], rax
0x180002ac3  call    cs:__imp_QueryPerformanceCounter
0x180002ac9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002acc  lea     rcx, [rbp+var_10]
0x180002ad0  shl     rax, 20h
0x180002ad4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002ad8  xor     rax, [rbp+var_10]
0x180002adc  xor     rax, rcx
0x180002adf  mov     rcx, 0FFFFFFFFFFFFh
0x180002ae9  and     rax, rcx
0x180002aec  mov     rcx, 2B992DDFA233h
0x180002af6  cmp     rax, rbx
0x180002af9  cmovz   rax, rcx
0x180002afd  mov     cs:__security_cookie, rax
0x180002b04  mov     rbx, [rsp+30h+arg_10]
0x180002b09  not     rax
0x180002b0c  mov     cs:__security_cookie_complement, rax
0x180002b13  add     rsp, 30h
0x180002b17  pop     rbp
0x180002b18  retn
```
