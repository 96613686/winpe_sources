# __security_init_cookie

- ea: `0x1800067bc`
- end: `0x180006871`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006250`

## callees

- `0x1800067bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000680b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000680b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000681b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000681b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800067f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800067f1`

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
0x1800067bc  mov     [rsp-8+arg_10], rbx
0x1800067c1  push    rbp
0x1800067c2  mov     rbp, rsp
0x1800067c5  sub     rsp, 30h
0x1800067c9  mov     rax, cs:__security_cookie
0x1800067d0  mov     rbx, 2B992DDFA232h
0x1800067da  cmp     rax, rbx
0x1800067dd  jnz     short loc_18000685C
0x1800067df  xor     eax, eax
0x1800067e1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800067e5  mov     [rbp+var_10], rax
0x1800067e9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800067ed  mov     qword ptr [rbp+PerformanceCount], rax
0x1800067f1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800067f7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800067fb  mov     [rbp+var_10], rax
0x1800067ff  call    cs:__imp_GetCurrentThreadId
0x180006805  mov     eax, eax
0x180006807  xor     [rbp+var_10], rax
0x18000680b  call    cs:__imp_GetCurrentProcessId
0x180006811  mov     eax, eax
0x180006813  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180006817  xor     [rbp+var_10], rax
0x18000681b  call    cs:__imp_QueryPerformanceCounter
0x180006821  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006824  lea     rcx, [rbp+var_10]
0x180006828  shl     rax, 20h
0x18000682c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006830  xor     rax, [rbp+var_10]
0x180006834  xor     rax, rcx
0x180006837  mov     rcx, 0FFFFFFFFFFFFh
0x180006841  and     rax, rcx
0x180006844  mov     rcx, 2B992DDFA233h
0x18000684e  cmp     rax, rbx
0x180006851  cmovz   rax, rcx
0x180006855  mov     cs:__security_cookie, rax
0x18000685c  mov     rbx, [rsp+30h+arg_10]
0x180006861  not     rax
0x180006864  mov     cs:__security_cookie_complement, rax
0x18000686b  add     rsp, 30h
0x18000686f  pop     rbp
0x180006870  retn
```
