# __security_init_cookie

- ea: `0x140004728`
- end: `0x1400047dd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400044a0`

## callees

- `0x140004728`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140004787`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140004787`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140004777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000476b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000476b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000475d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000475d`

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
0x140004728  mov     [rsp-8+arg_10], rbx
0x14000472d  push    rbp
0x14000472e  mov     rbp, rsp
0x140004731  sub     rsp, 30h
0x140004735  mov     rax, cs:__security_cookie
0x14000473c  mov     rbx, 2B992DDFA232h
0x140004746  cmp     rax, rbx
0x140004749  jnz     short loc_1400047C8
0x14000474b  xor     eax, eax
0x14000474d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140004751  mov     [rbp+var_10], rax
0x140004755  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140004759  mov     qword ptr [rbp+PerformanceCount], rax
0x14000475d  call    cs:__imp_GetSystemTimeAsFileTime
0x140004763  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140004767  mov     [rbp+var_10], rax
0x14000476b  call    cs:__imp_GetCurrentThreadId
0x140004771  mov     eax, eax
0x140004773  xor     [rbp+var_10], rax
0x140004777  call    cs:__imp_GetCurrentProcessId
0x14000477d  mov     eax, eax
0x14000477f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140004783  xor     [rbp+var_10], rax
0x140004787  call    cs:__imp_QueryPerformanceCounter
0x14000478d  mov     eax, dword ptr [rbp+PerformanceCount]
0x140004790  lea     rcx, [rbp+var_10]
0x140004794  shl     rax, 20h
0x140004798  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000479c  xor     rax, [rbp+var_10]
0x1400047a0  xor     rax, rcx
0x1400047a3  mov     rcx, 0FFFFFFFFFFFFh
0x1400047ad  and     rax, rcx
0x1400047b0  mov     rcx, 2B992DDFA233h
0x1400047ba  cmp     rax, rbx
0x1400047bd  cmovz   rax, rcx
0x1400047c1  mov     cs:__security_cookie, rax
0x1400047c8  mov     rbx, [rsp+30h+arg_10]
0x1400047cd  not     rax
0x1400047d0  mov     cs:__security_cookie_complement, rax
0x1400047d7  add     rsp, 30h
0x1400047db  pop     rbp
0x1400047dc  retn
```
