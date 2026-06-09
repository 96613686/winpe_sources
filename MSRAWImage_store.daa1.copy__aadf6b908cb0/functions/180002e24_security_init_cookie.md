# __security_init_cookie

- ea: `0x180002e24`
- end: `0x180002edb`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800029b0`

## callees

- `0x180002e24`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002e85`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002e85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002e75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002e75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e69`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002e5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002e5b`

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
0x180002e24  mov     [rsp-8+arg_10], rbx
0x180002e29  push    rbp
0x180002e2a  mov     rbp, rsp
0x180002e2d  sub     rsp, 30h
0x180002e31  mov     rax, cs:__security_cookie
0x180002e38  mov     rbx, 2B992DDFA232h
0x180002e42  cmp     rax, rbx
0x180002e45  jnz     short loc_180002EC6
0x180002e47  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002e4b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002e53  mov     qword ptr [rbp+PerformanceCount], 0
0x180002e5b  call    cs:__imp_GetSystemTimeAsFileTime
0x180002e61  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002e65  mov     [rbp+var_10], rax
0x180002e69  call    cs:__imp_GetCurrentThreadId
0x180002e6f  mov     eax, eax
0x180002e71  xor     [rbp+var_10], rax
0x180002e75  call    cs:__imp_GetCurrentProcessId
0x180002e7b  mov     eax, eax
0x180002e7d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002e81  xor     [rbp+var_10], rax
0x180002e85  call    cs:__imp_QueryPerformanceCounter
0x180002e8b  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002e8e  lea     rcx, [rbp+var_10]
0x180002e92  shl     rax, 20h
0x180002e96  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002e9a  xor     rax, [rbp+var_10]
0x180002e9e  xor     rax, rcx
0x180002ea1  mov     rcx, 0FFFFFFFFFFFFh
0x180002eab  and     rax, rcx
0x180002eae  mov     rcx, 2B992DDFA233h
0x180002eb8  cmp     rax, rbx
0x180002ebb  cmovz   rax, rcx
0x180002ebf  mov     cs:__security_cookie, rax
0x180002ec6  mov     rbx, [rsp+30h+arg_10]
0x180002ecb  not     rax
0x180002ece  mov     cs:__security_cookie_complement, rax
0x180002ed5  add     rsp, 30h
0x180002ed9  pop     rbp
0x180002eda  retn
```
