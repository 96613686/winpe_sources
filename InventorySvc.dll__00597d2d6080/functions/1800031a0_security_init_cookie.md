# __security_init_cookie

- ea: `0x1800031a0`
- end: `0x180003255`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ba0`

## callees

- `0x1800031a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800031ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800031ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800031e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800031e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800031d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800031d5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800031ff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800031ff`

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
0x1800031a0  mov     [rsp-8+arg_10], rbx
0x1800031a5  push    rbp
0x1800031a6  mov     rbp, rsp
0x1800031a9  sub     rsp, 30h
0x1800031ad  mov     rax, cs:__security_cookie
0x1800031b4  mov     rbx, 2B992DDFA232h
0x1800031be  cmp     rax, rbx
0x1800031c1  jnz     short loc_180003240
0x1800031c3  xor     eax, eax
0x1800031c5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800031c9  mov     [rbp+var_10], rax
0x1800031cd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800031d1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800031d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800031db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800031df  mov     [rbp+var_10], rax
0x1800031e3  call    cs:__imp_GetCurrentThreadId
0x1800031e9  mov     eax, eax
0x1800031eb  xor     [rbp+var_10], rax
0x1800031ef  call    cs:__imp_GetCurrentProcessId
0x1800031f5  mov     eax, eax
0x1800031f7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800031fb  xor     [rbp+var_10], rax
0x1800031ff  call    cs:__imp_QueryPerformanceCounter
0x180003205  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003208  lea     rcx, [rbp+var_10]
0x18000320c  shl     rax, 20h
0x180003210  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003214  xor     rax, [rbp+var_10]
0x180003218  xor     rax, rcx
0x18000321b  mov     rcx, 0FFFFFFFFFFFFh
0x180003225  and     rax, rcx
0x180003228  mov     rcx, 2B992DDFA233h
0x180003232  cmp     rax, rbx
0x180003235  cmovz   rax, rcx
0x180003239  mov     cs:__security_cookie, rax
0x180003240  mov     rbx, [rsp+30h+arg_10]
0x180003245  not     rax
0x180003248  mov     cs:__security_cookie_complement, rax
0x18000324f  add     rsp, 30h
0x180003253  pop     rbp
0x180003254  retn
```
