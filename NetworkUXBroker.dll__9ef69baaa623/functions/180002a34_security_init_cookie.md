# __security_init_cookie

- ea: `0x180002a34`
- end: `0x180002ae9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800024d0`

## callees

- `0x180002a34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002a83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002a83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a93`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a69`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002a69`

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
0x180002a34  mov     [rsp-8+arg_10], rbx
0x180002a39  push    rbp
0x180002a3a  mov     rbp, rsp
0x180002a3d  sub     rsp, 30h
0x180002a41  mov     rax, cs:__security_cookie
0x180002a48  mov     rbx, 2B992DDFA232h
0x180002a52  cmp     rax, rbx
0x180002a55  jnz     short loc_180002AD4
0x180002a57  xor     eax, eax
0x180002a59  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002a5d  mov     [rbp+var_10], rax
0x180002a61  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002a65  mov     qword ptr [rbp+PerformanceCount], rax
0x180002a69  call    cs:__imp_GetSystemTimeAsFileTime
0x180002a6f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002a73  mov     [rbp+var_10], rax
0x180002a77  call    cs:__imp_GetCurrentThreadId
0x180002a7d  mov     eax, eax
0x180002a7f  xor     [rbp+var_10], rax
0x180002a83  call    cs:__imp_GetCurrentProcessId
0x180002a89  mov     eax, eax
0x180002a8b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002a8f  xor     [rbp+var_10], rax
0x180002a93  call    cs:__imp_QueryPerformanceCounter
0x180002a99  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002a9c  lea     rcx, [rbp+var_10]
0x180002aa0  shl     rax, 20h
0x180002aa4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002aa8  xor     rax, [rbp+var_10]
0x180002aac  xor     rax, rcx
0x180002aaf  mov     rcx, 0FFFFFFFFFFFFh
0x180002ab9  and     rax, rcx
0x180002abc  mov     rcx, 2B992DDFA233h
0x180002ac6  cmp     rax, rbx
0x180002ac9  cmovz   rax, rcx
0x180002acd  mov     cs:__security_cookie, rax
0x180002ad4  mov     rbx, [rsp+30h+arg_10]
0x180002ad9  not     rax
0x180002adc  mov     cs:__security_cookie_complement, rax
0x180002ae3  add     rsp, 30h
0x180002ae7  pop     rbp
0x180002ae8  retn
```
