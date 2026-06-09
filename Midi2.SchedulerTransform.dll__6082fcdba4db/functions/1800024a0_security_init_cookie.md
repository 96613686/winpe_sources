# __security_init_cookie

- ea: `0x1800024a0`
- end: `0x180002555`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001fa0`

## callees

- `0x1800024a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800024ff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800024ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024d5`

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
0x1800024a0  mov     [rsp-8+arg_10], rbx
0x1800024a5  push    rbp
0x1800024a6  mov     rbp, rsp
0x1800024a9  sub     rsp, 30h
0x1800024ad  mov     rax, cs:__security_cookie
0x1800024b4  mov     rbx, 2B992DDFA232h
0x1800024be  cmp     rax, rbx
0x1800024c1  jnz     short loc_180002540
0x1800024c3  xor     eax, eax
0x1800024c5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800024c9  mov     [rbp+var_10], rax
0x1800024cd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800024d1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800024d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800024db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800024df  mov     [rbp+var_10], rax
0x1800024e3  call    cs:__imp_GetCurrentThreadId
0x1800024e9  mov     eax, eax
0x1800024eb  xor     [rbp+var_10], rax
0x1800024ef  call    cs:__imp_GetCurrentProcessId
0x1800024f5  mov     eax, eax
0x1800024f7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800024fb  xor     [rbp+var_10], rax
0x1800024ff  call    cs:__imp_QueryPerformanceCounter
0x180002505  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002508  lea     rcx, [rbp+var_10]
0x18000250c  shl     rax, 20h
0x180002510  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002514  xor     rax, [rbp+var_10]
0x180002518  xor     rax, rcx
0x18000251b  mov     rcx, 0FFFFFFFFFFFFh
0x180002525  and     rax, rcx
0x180002528  mov     rcx, 2B992DDFA233h
0x180002532  cmp     rax, rbx
0x180002535  cmovz   rax, rcx
0x180002539  mov     cs:__security_cookie, rax
0x180002540  mov     rbx, [rsp+30h+arg_10]
0x180002545  not     rax
0x180002548  mov     cs:__security_cookie_complement, rax
0x18000254f  add     rsp, 30h
0x180002553  pop     rbp
0x180002554  retn
```
