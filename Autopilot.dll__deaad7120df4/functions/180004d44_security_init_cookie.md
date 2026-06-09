# __security_init_cookie

- ea: `0x180004d44`
- end: `0x180004df9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004580`

## callees

- `0x180004d44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d93`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004da3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004da3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d79`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d79`

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
0x180004d44  mov     [rsp-8+arg_10], rbx
0x180004d49  push    rbp
0x180004d4a  mov     rbp, rsp
0x180004d4d  sub     rsp, 30h
0x180004d51  mov     rax, cs:__security_cookie
0x180004d58  mov     rbx, 2B992DDFA232h
0x180004d62  cmp     rax, rbx
0x180004d65  jnz     short loc_180004DE4
0x180004d67  xor     eax, eax
0x180004d69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004d6d  mov     [rbp+var_10], rax
0x180004d71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004d75  mov     qword ptr [rbp+PerformanceCount], rax
0x180004d79  call    cs:__imp_GetSystemTimeAsFileTime
0x180004d7f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004d83  mov     [rbp+var_10], rax
0x180004d87  call    cs:__imp_GetCurrentThreadId
0x180004d8d  mov     eax, eax
0x180004d8f  xor     [rbp+var_10], rax
0x180004d93  call    cs:__imp_GetCurrentProcessId
0x180004d99  mov     eax, eax
0x180004d9b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004d9f  xor     [rbp+var_10], rax
0x180004da3  call    cs:__imp_QueryPerformanceCounter
0x180004da9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004dac  lea     rcx, [rbp+var_10]
0x180004db0  shl     rax, 20h
0x180004db4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004db8  xor     rax, [rbp+var_10]
0x180004dbc  xor     rax, rcx
0x180004dbf  mov     rcx, 0FFFFFFFFFFFFh
0x180004dc9  and     rax, rcx
0x180004dcc  mov     rcx, 2B992DDFA233h
0x180004dd6  cmp     rax, rbx
0x180004dd9  cmovz   rax, rcx
0x180004ddd  mov     cs:__security_cookie, rax
0x180004de4  mov     rbx, [rsp+30h+arg_10]
0x180004de9  not     rax
0x180004dec  mov     cs:__security_cookie_complement, rax
0x180004df3  add     rsp, 30h
0x180004df7  pop     rbp
0x180004df8  retn
```
