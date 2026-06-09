# __security_init_cookie

- ea: `0x1800029c0`
- end: `0x180002a75`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800024f0`

## callees

- `0x1800029c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002a0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a1f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002a1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800029f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800029f5`

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
0x1800029c0  mov     [rsp-8+arg_10], rbx
0x1800029c5  push    rbp
0x1800029c6  mov     rbp, rsp
0x1800029c9  sub     rsp, 30h
0x1800029cd  mov     rax, cs:__security_cookie
0x1800029d4  mov     rbx, 2B992DDFA232h
0x1800029de  cmp     rax, rbx
0x1800029e1  jnz     short loc_180002A60
0x1800029e3  xor     eax, eax
0x1800029e5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800029e9  mov     [rbp+var_10], rax
0x1800029ed  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800029f1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800029f5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800029fb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800029ff  mov     [rbp+var_10], rax
0x180002a03  call    cs:__imp_GetCurrentThreadId
0x180002a09  mov     eax, eax
0x180002a0b  xor     [rbp+var_10], rax
0x180002a0f  call    cs:__imp_GetCurrentProcessId
0x180002a15  mov     eax, eax
0x180002a17  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002a1b  xor     [rbp+var_10], rax
0x180002a1f  call    cs:__imp_QueryPerformanceCounter
0x180002a25  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002a28  lea     rcx, [rbp+var_10]
0x180002a2c  shl     rax, 20h
0x180002a30  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002a34  xor     rax, [rbp+var_10]
0x180002a38  xor     rax, rcx
0x180002a3b  mov     rcx, 0FFFFFFFFFFFFh
0x180002a45  and     rax, rcx
0x180002a48  mov     rcx, 2B992DDFA233h
0x180002a52  cmp     rax, rbx
0x180002a55  cmovz   rax, rcx
0x180002a59  mov     cs:__security_cookie, rax
0x180002a60  mov     rbx, [rsp+30h+arg_10]
0x180002a65  not     rax
0x180002a68  mov     cs:__security_cookie_complement, rax
0x180002a6f  add     rsp, 30h
0x180002a73  pop     rbp
0x180002a74  retn
```
