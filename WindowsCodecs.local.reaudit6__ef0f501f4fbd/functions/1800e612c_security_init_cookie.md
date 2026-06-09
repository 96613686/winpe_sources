# __security_init_cookie

- ea: `0x1800e612c`
- end: `0x1800e61e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e5e10`

## callees

- `0x1800e612c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e618b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e618b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e617b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e617b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e616f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e616f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e6161`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e6161`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x1800e612c  mov     [rsp-8+arg_10], rbx
0x1800e6131  push    rbp
0x1800e6132  mov     rbp, rsp
0x1800e6135  sub     rsp, 30h
0x1800e6139  mov     rax, cs:__security_cookie
0x1800e6140  mov     rbx, 2B992DDFA232h
0x1800e614a  cmp     rax, rbx
0x1800e614d  jnz     short loc_1800E61CC
0x1800e614f  xor     eax, eax
0x1800e6151  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800e6155  mov     [rbp+var_10], rax
0x1800e6159  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800e615d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800e6161  call    cs:__imp_GetSystemTimeAsFileTime
0x1800e6167  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800e616b  mov     [rbp+var_10], rax
0x1800e616f  call    cs:__imp_GetCurrentThreadId
0x1800e6175  mov     eax, eax
0x1800e6177  xor     [rbp+var_10], rax
0x1800e617b  call    cs:__imp_GetCurrentProcessId
0x1800e6181  mov     eax, eax
0x1800e6183  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800e6187  xor     [rbp+var_10], rax
0x1800e618b  call    cs:__imp_QueryPerformanceCounter
0x1800e6191  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800e6194  lea     rcx, [rbp+var_10]
0x1800e6198  shl     rax, 20h
0x1800e619c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800e61a0  xor     rax, [rbp+var_10]
0x1800e61a4  xor     rax, rcx
0x1800e61a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800e61b1  and     rax, rcx
0x1800e61b4  mov     rcx, 2B992DDFA233h
0x1800e61be  cmp     rax, rbx
0x1800e61c1  cmovz   rax, rcx
0x1800e61c5  mov     cs:__security_cookie, rax
0x1800e61cc  mov     rbx, [rsp+30h+arg_10]
0x1800e61d1  not     rax
0x1800e61d4  mov     cs:__security_cookie_complement, rax
0x1800e61db  add     rsp, 30h
0x1800e61df  pop     rbp
0x1800e61e0  retn
```
