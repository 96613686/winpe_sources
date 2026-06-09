# __security_init_cookie

- ea: `0x180003bc4`
- end: `0x180003c79`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800033b0`

## callees

- `0x180003bc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003c07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003c13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003bf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003bf9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003c23`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003c23`

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
0x180003bc4  mov     [rsp-8+arg_10], rbx
0x180003bc9  push    rbp
0x180003bca  mov     rbp, rsp
0x180003bcd  sub     rsp, 30h
0x180003bd1  mov     rax, cs:__security_cookie
0x180003bd8  mov     rbx, 2B992DDFA232h
0x180003be2  cmp     rax, rbx
0x180003be5  jnz     short loc_180003C64
0x180003be7  xor     eax, eax
0x180003be9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003bed  mov     [rbp+var_10], rax
0x180003bf1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003bf5  mov     qword ptr [rbp+PerformanceCount], rax
0x180003bf9  call    cs:__imp_GetSystemTimeAsFileTime
0x180003bff  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003c03  mov     [rbp+var_10], rax
0x180003c07  call    cs:__imp_GetCurrentThreadId
0x180003c0d  mov     eax, eax
0x180003c0f  xor     [rbp+var_10], rax
0x180003c13  call    cs:__imp_GetCurrentProcessId
0x180003c19  mov     eax, eax
0x180003c1b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003c1f  xor     [rbp+var_10], rax
0x180003c23  call    cs:__imp_QueryPerformanceCounter
0x180003c29  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003c2c  lea     rcx, [rbp+var_10]
0x180003c30  shl     rax, 20h
0x180003c34  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003c38  xor     rax, [rbp+var_10]
0x180003c3c  xor     rax, rcx
0x180003c3f  mov     rcx, 0FFFFFFFFFFFFh
0x180003c49  and     rax, rcx
0x180003c4c  mov     rcx, 2B992DDFA233h
0x180003c56  cmp     rax, rbx
0x180003c59  cmovz   rax, rcx
0x180003c5d  mov     cs:__security_cookie, rax
0x180003c64  mov     rbx, [rsp+30h+arg_10]
0x180003c69  not     rax
0x180003c6c  mov     cs:__security_cookie_complement, rax
0x180003c73  add     rsp, 30h
0x180003c77  pop     rbp
0x180003c78  retn
```
