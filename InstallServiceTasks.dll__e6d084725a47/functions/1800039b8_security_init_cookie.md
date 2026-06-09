# __security_init_cookie

- ea: `0x1800039b8`
- end: `0x180003a6d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003400`

## callees

- `0x1800039b8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003a17`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003a17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800039ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800039ed`

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
0x1800039b8  mov     [rsp-8+arg_10], rbx
0x1800039bd  push    rbp
0x1800039be  mov     rbp, rsp
0x1800039c1  sub     rsp, 30h
0x1800039c5  mov     rax, cs:__security_cookie
0x1800039cc  mov     rbx, 2B992DDFA232h
0x1800039d6  cmp     rax, rbx
0x1800039d9  jnz     short loc_180003A58
0x1800039db  xor     eax, eax
0x1800039dd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800039e1  mov     [rbp+var_10], rax
0x1800039e5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800039e9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800039ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800039f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800039f7  mov     [rbp+var_10], rax
0x1800039fb  call    cs:__imp_GetCurrentThreadId
0x180003a01  mov     eax, eax
0x180003a03  xor     [rbp+var_10], rax
0x180003a07  call    cs:__imp_GetCurrentProcessId
0x180003a0d  mov     eax, eax
0x180003a0f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003a13  xor     [rbp+var_10], rax
0x180003a17  call    cs:__imp_QueryPerformanceCounter
0x180003a1d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003a20  lea     rcx, [rbp+var_10]
0x180003a24  shl     rax, 20h
0x180003a28  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003a2c  xor     rax, [rbp+var_10]
0x180003a30  xor     rax, rcx
0x180003a33  mov     rcx, 0FFFFFFFFFFFFh
0x180003a3d  and     rax, rcx
0x180003a40  mov     rcx, 2B992DDFA233h
0x180003a4a  cmp     rax, rbx
0x180003a4d  cmovz   rax, rcx
0x180003a51  mov     cs:__security_cookie, rax
0x180003a58  mov     rbx, [rsp+30h+arg_10]
0x180003a5d  not     rax
0x180003a60  mov     cs:__security_cookie_complement, rax
0x180003a67  add     rsp, 30h
0x180003a6b  pop     rbp
0x180003a6c  retn
```
