# __security_init_cookie

- ea: `0x180015010`
- end: `0x1800150c5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014f70`

## callees

- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001505f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001505f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015053`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001506f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001506f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015045`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015045`

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
0x180015010  mov     [rsp-8+arg_10], rbx
0x180015015  push    rbp
0x180015016  mov     rbp, rsp
0x180015019  sub     rsp, 30h
0x18001501d  mov     rax, cs:__security_cookie
0x180015024  mov     rbx, 2B992DDFA232h
0x18001502e  cmp     rax, rbx
0x180015031  jnz     short loc_1800150B0
0x180015033  xor     eax, eax
0x180015035  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015039  mov     [rbp+var_10], rax
0x18001503d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180015041  mov     qword ptr [rbp+PerformanceCount], rax
0x180015045  call    cs:__imp_GetSystemTimeAsFileTime
0x18001504b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001504f  mov     [rbp+var_10], rax
0x180015053  call    cs:__imp_GetCurrentThreadId
0x180015059  mov     eax, eax
0x18001505b  xor     [rbp+var_10], rax
0x18001505f  call    cs:__imp_GetCurrentProcessId
0x180015065  mov     eax, eax
0x180015067  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001506b  xor     [rbp+var_10], rax
0x18001506f  call    cs:__imp_QueryPerformanceCounter
0x180015075  mov     eax, dword ptr [rbp+PerformanceCount]
0x180015078  lea     rcx, [rbp+var_10]
0x18001507c  shl     rax, 20h
0x180015080  xor     rax, qword ptr [rbp+PerformanceCount]
0x180015084  xor     rax, [rbp+var_10]
0x180015088  xor     rax, rcx
0x18001508b  mov     rcx, 0FFFFFFFFFFFFh
0x180015095  and     rax, rcx
0x180015098  mov     rcx, 2B992DDFA233h
0x1800150a2  cmp     rax, rbx
0x1800150a5  cmovz   rax, rcx
0x1800150a9  mov     cs:__security_cookie, rax
0x1800150b0  mov     rbx, [rsp+30h+arg_10]
0x1800150b5  not     rax
0x1800150b8  mov     cs:__security_cookie_complement, rax
0x1800150bf  add     rsp, 30h
0x1800150c3  pop     rbp
0x1800150c4  retn
```
