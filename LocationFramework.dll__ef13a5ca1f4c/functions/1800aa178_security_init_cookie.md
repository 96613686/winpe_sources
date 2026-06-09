# __security_init_cookie

- ea: `0x1800aa178`
- end: `0x1800aa22d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a9860`

## callees

- `0x1800aa178`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aa1c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aa1c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa1bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa1bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aa1ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aa1ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aa1d7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aa1d7`

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
0x1800aa178  mov     [rsp-8+arg_10], rbx
0x1800aa17d  push    rbp
0x1800aa17e  mov     rbp, rsp
0x1800aa181  sub     rsp, 30h
0x1800aa185  mov     rax, cs:__security_cookie
0x1800aa18c  mov     rbx, 2B992DDFA232h
0x1800aa196  cmp     rax, rbx
0x1800aa199  jnz     short loc_1800AA218
0x1800aa19b  xor     eax, eax
0x1800aa19d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800aa1a1  mov     [rbp+var_10], rax
0x1800aa1a5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800aa1a9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800aa1ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800aa1b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800aa1b7  mov     [rbp+var_10], rax
0x1800aa1bb  call    cs:__imp_GetCurrentThreadId
0x1800aa1c1  mov     eax, eax
0x1800aa1c3  xor     [rbp+var_10], rax
0x1800aa1c7  call    cs:__imp_GetCurrentProcessId
0x1800aa1cd  mov     eax, eax
0x1800aa1cf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800aa1d3  xor     [rbp+var_10], rax
0x1800aa1d7  call    cs:__imp_QueryPerformanceCounter
0x1800aa1dd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800aa1e0  lea     rcx, [rbp+var_10]
0x1800aa1e4  shl     rax, 20h
0x1800aa1e8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800aa1ec  xor     rax, [rbp+var_10]
0x1800aa1f0  xor     rax, rcx
0x1800aa1f3  mov     rcx, 0FFFFFFFFFFFFh
0x1800aa1fd  and     rax, rcx
0x1800aa200  mov     rcx, 2B992DDFA233h
0x1800aa20a  cmp     rax, rbx
0x1800aa20d  cmovz   rax, rcx
0x1800aa211  mov     cs:__security_cookie, rax
0x1800aa218  mov     rbx, [rsp+30h+arg_10]
0x1800aa21d  not     rax
0x1800aa220  mov     cs:__security_cookie_complement, rax
0x1800aa227  add     rsp, 30h
0x1800aa22b  pop     rbp
0x1800aa22c  retn
```
