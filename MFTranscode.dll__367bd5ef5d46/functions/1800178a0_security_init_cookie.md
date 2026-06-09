# __security_init_cookie

- ea: `0x1800178a0`
- end: `0x180017955`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180017470`

## callees

- `0x1800178a0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800178ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800178ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800178e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800178e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800178ff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800178ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800178d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800178d5`

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
0x1800178a0  mov     [rsp-8+arg_10], rbx
0x1800178a5  push    rbp
0x1800178a6  mov     rbp, rsp
0x1800178a9  sub     rsp, 30h
0x1800178ad  mov     rax, cs:__security_cookie
0x1800178b4  mov     rbx, 2B992DDFA232h
0x1800178be  cmp     rax, rbx
0x1800178c1  jnz     short loc_180017940
0x1800178c3  xor     eax, eax
0x1800178c5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800178c9  mov     [rbp+var_10], rax
0x1800178cd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800178d1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800178d5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800178db  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800178df  mov     [rbp+var_10], rax
0x1800178e3  call    cs:__imp_GetCurrentThreadId
0x1800178e9  mov     eax, eax
0x1800178eb  xor     [rbp+var_10], rax
0x1800178ef  call    cs:__imp_GetCurrentProcessId
0x1800178f5  mov     eax, eax
0x1800178f7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800178fb  xor     [rbp+var_10], rax
0x1800178ff  call    cs:__imp_QueryPerformanceCounter
0x180017905  mov     eax, dword ptr [rbp+PerformanceCount]
0x180017908  lea     rcx, [rbp+var_10]
0x18001790c  shl     rax, 20h
0x180017910  xor     rax, qword ptr [rbp+PerformanceCount]
0x180017914  xor     rax, [rbp+var_10]
0x180017918  xor     rax, rcx
0x18001791b  mov     rcx, 0FFFFFFFFFFFFh
0x180017925  and     rax, rcx
0x180017928  mov     rcx, 2B992DDFA233h
0x180017932  cmp     rax, rbx
0x180017935  cmovz   rax, rcx
0x180017939  mov     cs:__security_cookie, rax
0x180017940  mov     rbx, [rsp+30h+arg_10]
0x180017945  not     rax
0x180017948  mov     cs:__security_cookie_complement, rax
0x18001794f  add     rsp, 30h
0x180017953  pop     rbp
0x180017954  retn
```
