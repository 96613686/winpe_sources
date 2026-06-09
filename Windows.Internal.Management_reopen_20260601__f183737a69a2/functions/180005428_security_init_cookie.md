# __security_init_cookie

- ea: `0x180005428`
- end: `0x1800054dd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004e50`

## callees

- `0x180005428`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005477`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000546b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000546b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005487`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005487`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000545d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000545d`

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
0x180005428  mov     [rsp-8+arg_10], rbx
0x18000542d  push    rbp
0x18000542e  mov     rbp, rsp
0x180005431  sub     rsp, 30h
0x180005435  mov     rax, cs:__security_cookie
0x18000543c  mov     rbx, 2B992DDFA232h
0x180005446  cmp     rax, rbx
0x180005449  jnz     short loc_1800054C8
0x18000544b  xor     eax, eax
0x18000544d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005451  mov     [rbp+var_10], rax
0x180005455  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005459  mov     qword ptr [rbp+PerformanceCount], rax
0x18000545d  call    cs:__imp_GetSystemTimeAsFileTime
0x180005463  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005467  mov     [rbp+var_10], rax
0x18000546b  call    cs:__imp_GetCurrentThreadId
0x180005471  mov     eax, eax
0x180005473  xor     [rbp+var_10], rax
0x180005477  call    cs:__imp_GetCurrentProcessId
0x18000547d  mov     eax, eax
0x18000547f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005483  xor     [rbp+var_10], rax
0x180005487  call    cs:__imp_QueryPerformanceCounter
0x18000548d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005490  lea     rcx, [rbp+var_10]
0x180005494  shl     rax, 20h
0x180005498  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000549c  xor     rax, [rbp+var_10]
0x1800054a0  xor     rax, rcx
0x1800054a3  mov     rcx, 0FFFFFFFFFFFFh
0x1800054ad  and     rax, rcx
0x1800054b0  mov     rcx, 2B992DDFA233h
0x1800054ba  cmp     rax, rbx
0x1800054bd  cmovz   rax, rcx
0x1800054c1  mov     cs:__security_cookie, rax
0x1800054c8  mov     rbx, [rsp+30h+arg_10]
0x1800054cd  not     rax
0x1800054d0  mov     cs:__security_cookie_complement, rax
0x1800054d7  add     rsp, 30h
0x1800054db  pop     rbp
0x1800054dc  retn
```
