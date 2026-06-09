# __security_init_cookie

- ea: `0x180002ba4`
- end: `0x180002c81`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800025d0`

## callees

- `0x180002ba4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002beb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bf7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002c2e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002c2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002c03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002c13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002c03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002c13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002bdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002bdd`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180002ba4  mov     [rsp-8+arg_18], rbx
0x180002ba9  push    rbp
0x180002baa  mov     rbp, rsp
0x180002bad  sub     rsp, 20h
0x180002bb1  xor     eax, eax
0x180002bb3  mov     rbx, 2B992DDFA232h
0x180002bbd  mov     [rbp+arg_0], rax
0x180002bc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002bc5  mov     qword ptr [rbp+PerformanceCount], rax
0x180002bc9  mov     rax, cs:__security_cookie
0x180002bd0  cmp     rax, rbx
0x180002bd3  jnz     loc_180002C6C
0x180002bd9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002bdd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002be3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002be7  mov     [rbp+arg_0], rax
0x180002beb  call    cs:__imp_GetCurrentProcessId
0x180002bf1  mov     eax, eax
0x180002bf3  xor     [rbp+arg_0], rax
0x180002bf7  call    cs:__imp_GetCurrentThreadId
0x180002bfd  mov     eax, eax
0x180002bff  xor     [rbp+arg_0], rax
0x180002c03  call    cs:__imp_GetTickCount
0x180002c09  mov     eax, eax
0x180002c0b  shl     rax, 18h
0x180002c0f  xor     [rbp+arg_0], rax
0x180002c13  call    cs:__imp_GetTickCount
0x180002c19  mov     eax, eax
0x180002c1b  lea     rcx, [rbp+arg_0]
0x180002c1f  xor     rax, [rbp+arg_0]
0x180002c23  xor     rax, rcx
0x180002c26  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002c2a  mov     [rbp+arg_0], rax
0x180002c2e  call    cs:__imp_QueryPerformanceCounter
0x180002c34  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002c37  mov     rcx, 0FFFFFFFFFFFFh
0x180002c41  shl     rax, 20h
0x180002c45  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002c49  xor     rax, [rbp+arg_0]
0x180002c4d  and     rax, rcx
0x180002c50  mov     rcx, rax
0x180002c53  cmp     rax, rbx
0x180002c56  jnz     short loc_180002C65
0x180002c58  mov     rax, 2B992DDFA233h
0x180002c62  mov     rcx, rax
0x180002c65  mov     cs:__security_cookie, rcx
0x180002c6c  mov     rbx, [rsp+20h+arg_18]
0x180002c71  not     rax
0x180002c74  mov     cs:__security_cookie_complement, rax
0x180002c7b  add     rsp, 20h
0x180002c7f  pop     rbp
0x180002c80  retn
```
