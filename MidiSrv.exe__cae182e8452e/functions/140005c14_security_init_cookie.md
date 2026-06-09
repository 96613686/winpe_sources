# __security_init_cookie

- ea: `0x140005c14`
- end: `0x140005cc9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005490`

## callees

- `0x140005c14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005c63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140005c63`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140005c49`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140005c49`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140005c73`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140005c73`

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
0x140005c14  mov     [rsp-8+arg_10], rbx
0x140005c19  push    rbp
0x140005c1a  mov     rbp, rsp
0x140005c1d  sub     rsp, 30h
0x140005c21  mov     rax, cs:__security_cookie
0x140005c28  mov     rbx, 2B992DDFA232h
0x140005c32  cmp     rax, rbx
0x140005c35  jnz     short loc_140005CB4
0x140005c37  xor     eax, eax
0x140005c39  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140005c3d  mov     [rbp+var_10], rax
0x140005c41  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140005c45  mov     qword ptr [rbp+PerformanceCount], rax
0x140005c49  call    cs:__imp_GetSystemTimeAsFileTime
0x140005c4f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140005c53  mov     [rbp+var_10], rax
0x140005c57  call    cs:__imp_GetCurrentThreadId
0x140005c5d  mov     eax, eax
0x140005c5f  xor     [rbp+var_10], rax
0x140005c63  call    cs:__imp_GetCurrentProcessId
0x140005c69  mov     eax, eax
0x140005c6b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140005c6f  xor     [rbp+var_10], rax
0x140005c73  call    cs:__imp_QueryPerformanceCounter
0x140005c79  mov     eax, dword ptr [rbp+PerformanceCount]
0x140005c7c  lea     rcx, [rbp+var_10]
0x140005c80  shl     rax, 20h
0x140005c84  xor     rax, qword ptr [rbp+PerformanceCount]
0x140005c88  xor     rax, [rbp+var_10]
0x140005c8c  xor     rax, rcx
0x140005c8f  mov     rcx, 0FFFFFFFFFFFFh
0x140005c99  and     rax, rcx
0x140005c9c  mov     rcx, 2B992DDFA233h
0x140005ca6  cmp     rax, rbx
0x140005ca9  cmovz   rax, rcx
0x140005cad  mov     cs:__security_cookie, rax
0x140005cb4  mov     rbx, [rsp+30h+arg_10]
0x140005cb9  not     rax
0x140005cbc  mov     cs:__security_cookie_complement, rax
0x140005cc3  add     rsp, 30h
0x140005cc7  pop     rbp
0x140005cc8  retn
```
