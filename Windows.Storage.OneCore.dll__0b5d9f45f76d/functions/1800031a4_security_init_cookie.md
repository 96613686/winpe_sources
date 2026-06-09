# __security_init_cookie

- ea: `0x1800031a4`
- end: `0x180003259`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002b90`

## callees

- `0x1800031a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800031e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800031e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800031f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800031f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800031d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800031d9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003203`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003203`

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
0x1800031a4  mov     [rsp-8+arg_10], rbx
0x1800031a9  push    rbp
0x1800031aa  mov     rbp, rsp
0x1800031ad  sub     rsp, 30h
0x1800031b1  mov     rax, cs:__security_cookie
0x1800031b8  mov     rbx, 2B992DDFA232h
0x1800031c2  cmp     rax, rbx
0x1800031c5  jnz     short loc_180003244
0x1800031c7  xor     eax, eax
0x1800031c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800031cd  mov     [rbp+var_10], rax
0x1800031d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800031d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800031d9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800031df  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800031e3  mov     [rbp+var_10], rax
0x1800031e7  call    cs:__imp_GetCurrentThreadId
0x1800031ed  mov     eax, eax
0x1800031ef  xor     [rbp+var_10], rax
0x1800031f3  call    cs:__imp_GetCurrentProcessId
0x1800031f9  mov     eax, eax
0x1800031fb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800031ff  xor     [rbp+var_10], rax
0x180003203  call    cs:__imp_QueryPerformanceCounter
0x180003209  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000320c  lea     rcx, [rbp+var_10]
0x180003210  shl     rax, 20h
0x180003214  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003218  xor     rax, [rbp+var_10]
0x18000321c  xor     rax, rcx
0x18000321f  mov     rcx, 0FFFFFFFFFFFFh
0x180003229  and     rax, rcx
0x18000322c  mov     rcx, 2B992DDFA233h
0x180003236  cmp     rax, rbx
0x180003239  cmovz   rax, rcx
0x18000323d  mov     cs:__security_cookie, rax
0x180003244  mov     rbx, [rsp+30h+arg_10]
0x180003249  not     rax
0x18000324c  mov     cs:__security_cookie_complement, rax
0x180003253  add     rsp, 30h
0x180003257  pop     rbp
0x180003258  retn
```
