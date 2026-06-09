# __security_init_cookie

- ea: `0x180002fcc`
- end: `0x180003081`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b70`

## callees

- `0x180002fcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000300f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000300f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000301b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000301b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000302b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000302b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003001`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003001`

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
0x180002fcc  mov     [rsp-8+arg_10], rbx
0x180002fd1  push    rbp
0x180002fd2  mov     rbp, rsp
0x180002fd5  sub     rsp, 30h
0x180002fd9  mov     rax, cs:__security_cookie
0x180002fe0  mov     rbx, 2B992DDFA232h
0x180002fea  cmp     rax, rbx
0x180002fed  jnz     short loc_18000306C
0x180002fef  xor     eax, eax
0x180002ff1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002ff5  mov     [rbp+var_10], rax
0x180002ff9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002ffd  mov     qword ptr [rbp+PerformanceCount], rax
0x180003001  call    cs:__imp_GetSystemTimeAsFileTime
0x180003007  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000300b  mov     [rbp+var_10], rax
0x18000300f  call    cs:__imp_GetCurrentThreadId
0x180003015  mov     eax, eax
0x180003017  xor     [rbp+var_10], rax
0x18000301b  call    cs:__imp_GetCurrentProcessId
0x180003021  mov     eax, eax
0x180003023  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003027  xor     [rbp+var_10], rax
0x18000302b  call    cs:__imp_QueryPerformanceCounter
0x180003031  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003034  lea     rcx, [rbp+var_10]
0x180003038  shl     rax, 20h
0x18000303c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003040  xor     rax, [rbp+var_10]
0x180003044  xor     rax, rcx
0x180003047  mov     rcx, 0FFFFFFFFFFFFh
0x180003051  and     rax, rcx
0x180003054  mov     rcx, 2B992DDFA233h
0x18000305e  cmp     rax, rbx
0x180003061  cmovz   rax, rcx
0x180003065  mov     cs:__security_cookie, rax
0x18000306c  mov     rbx, [rsp+30h+arg_10]
0x180003071  not     rax
0x180003074  mov     cs:__security_cookie_complement, rax
0x18000307b  add     rsp, 30h
0x18000307f  pop     rbp
0x180003080  retn
```
