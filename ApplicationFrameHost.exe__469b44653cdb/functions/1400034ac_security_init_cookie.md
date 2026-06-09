# __security_init_cookie

- ea: `0x1400034ac`
- end: `0x140003561`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003180`

## callees

- `0x1400034ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400034fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400034fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400034ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000350b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000350b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400034e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400034e1`

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
0x1400034ac  mov     [rsp-8+arg_10], rbx
0x1400034b1  push    rbp
0x1400034b2  mov     rbp, rsp
0x1400034b5  sub     rsp, 30h
0x1400034b9  mov     rax, cs:__security_cookie
0x1400034c0  mov     rbx, 2B992DDFA232h
0x1400034ca  cmp     rax, rbx
0x1400034cd  jnz     short loc_14000354C
0x1400034cf  xor     eax, eax
0x1400034d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400034d5  mov     [rbp+var_10], rax
0x1400034d9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400034dd  mov     qword ptr [rbp+PerformanceCount], rax
0x1400034e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400034e7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400034eb  mov     [rbp+var_10], rax
0x1400034ef  call    cs:__imp_GetCurrentThreadId
0x1400034f5  mov     eax, eax
0x1400034f7  xor     [rbp+var_10], rax
0x1400034fb  call    cs:__imp_GetCurrentProcessId
0x140003501  mov     eax, eax
0x140003503  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140003507  xor     [rbp+var_10], rax
0x14000350b  call    cs:__imp_QueryPerformanceCounter
0x140003511  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003514  lea     rcx, [rbp+var_10]
0x140003518  shl     rax, 20h
0x14000351c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003520  xor     rax, [rbp+var_10]
0x140003524  xor     rax, rcx
0x140003527  mov     rcx, 0FFFFFFFFFFFFh
0x140003531  and     rax, rcx
0x140003534  mov     rcx, 2B992DDFA233h
0x14000353e  cmp     rax, rbx
0x140003541  cmovz   rax, rcx
0x140003545  mov     cs:__security_cookie, rax
0x14000354c  mov     rbx, [rsp+30h+arg_10]
0x140003551  not     rax
0x140003554  mov     cs:__security_cookie_complement, rax
0x14000355b  add     rsp, 30h
0x14000355f  pop     rbp
0x140003560  retn
```
