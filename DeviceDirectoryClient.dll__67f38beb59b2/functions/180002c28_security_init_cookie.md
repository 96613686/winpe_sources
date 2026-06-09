# __security_init_cookie

- ea: `0x180002c28`
- end: `0x180002cdd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002460`

## callees

- `0x180002c28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002c77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002c77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002c87`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002c87`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002c5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002c5d`

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
0x180002c28  mov     [rsp-8+arg_10], rbx
0x180002c2d  push    rbp
0x180002c2e  mov     rbp, rsp
0x180002c31  sub     rsp, 30h
0x180002c35  mov     rax, cs:__security_cookie
0x180002c3c  mov     rbx, 2B992DDFA232h
0x180002c46  cmp     rax, rbx
0x180002c49  jnz     short loc_180002CC8
0x180002c4b  xor     eax, eax
0x180002c4d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002c51  mov     [rbp+var_10], rax
0x180002c55  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002c59  mov     qword ptr [rbp+PerformanceCount], rax
0x180002c5d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002c63  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002c67  mov     [rbp+var_10], rax
0x180002c6b  call    cs:__imp_GetCurrentThreadId
0x180002c71  mov     eax, eax
0x180002c73  xor     [rbp+var_10], rax
0x180002c77  call    cs:__imp_GetCurrentProcessId
0x180002c7d  mov     eax, eax
0x180002c7f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002c83  xor     [rbp+var_10], rax
0x180002c87  call    cs:__imp_QueryPerformanceCounter
0x180002c8d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002c90  lea     rcx, [rbp+var_10]
0x180002c94  shl     rax, 20h
0x180002c98  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002c9c  xor     rax, [rbp+var_10]
0x180002ca0  xor     rax, rcx
0x180002ca3  mov     rcx, 0FFFFFFFFFFFFh
0x180002cad  and     rax, rcx
0x180002cb0  mov     rcx, 2B992DDFA233h
0x180002cba  cmp     rax, rbx
0x180002cbd  cmovz   rax, rcx
0x180002cc1  mov     cs:__security_cookie, rax
0x180002cc8  mov     rbx, [rsp+30h+arg_10]
0x180002ccd  not     rax
0x180002cd0  mov     cs:__security_cookie_complement, rax
0x180002cd7  add     rsp, 30h
0x180002cdb  pop     rbp
0x180002cdc  retn
```
