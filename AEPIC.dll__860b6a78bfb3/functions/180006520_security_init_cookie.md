# __security_init_cookie

- ea: `0x180006520`
- end: `0x1800065d5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005840`

## callees

- `0x180006520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006563`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006563`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000656f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000656f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006555`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006555`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000657f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000657f`

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
0x180006520  mov     [rsp-8+arg_10], rbx
0x180006525  push    rbp
0x180006526  mov     rbp, rsp
0x180006529  sub     rsp, 30h
0x18000652d  mov     rax, cs:__security_cookie
0x180006534  mov     rbx, 2B992DDFA232h
0x18000653e  cmp     rax, rbx
0x180006541  jnz     short loc_1800065C0
0x180006543  xor     eax, eax
0x180006545  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006549  mov     [rbp+var_10], rax
0x18000654d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006551  mov     qword ptr [rbp+PerformanceCount], rax
0x180006555  call    cs:__imp_GetSystemTimeAsFileTime
0x18000655b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000655f  mov     [rbp+var_10], rax
0x180006563  call    cs:__imp_GetCurrentThreadId
0x180006569  mov     eax, eax
0x18000656b  xor     [rbp+var_10], rax
0x18000656f  call    cs:__imp_GetCurrentProcessId
0x180006575  mov     eax, eax
0x180006577  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000657b  xor     [rbp+var_10], rax
0x18000657f  call    cs:__imp_QueryPerformanceCounter
0x180006585  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006588  lea     rcx, [rbp+var_10]
0x18000658c  shl     rax, 20h
0x180006590  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006594  xor     rax, [rbp+var_10]
0x180006598  xor     rax, rcx
0x18000659b  mov     rcx, 0FFFFFFFFFFFFh
0x1800065a5  and     rax, rcx
0x1800065a8  mov     rcx, 2B992DDFA233h
0x1800065b2  cmp     rax, rbx
0x1800065b5  cmovz   rax, rcx
0x1800065b9  mov     cs:__security_cookie, rax
0x1800065c0  mov     rbx, [rsp+30h+arg_10]
0x1800065c5  not     rax
0x1800065c8  mov     cs:__security_cookie_complement, rax
0x1800065cf  add     rsp, 30h
0x1800065d3  pop     rbp
0x1800065d4  retn
```
