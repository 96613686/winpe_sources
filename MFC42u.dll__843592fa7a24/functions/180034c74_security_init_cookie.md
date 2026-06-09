# __security_init_cookie

- ea: `0x180034c74`
- end: `0x180034d51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034250`

## callees

- `0x180034c74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034cbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034cbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034cc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034cc7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180034cfe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180034cfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034cd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034ce3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034cd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180034ce3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034cad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180034cad`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180034c74  mov     [rsp-8+arg_18], rbx
0x180034c79  push    rbp
0x180034c7a  mov     rbp, rsp
0x180034c7d  sub     rsp, 20h
0x180034c81  xor     eax, eax
0x180034c83  mov     rbx, 2B992DDFA232h
0x180034c8d  mov     [rbp+arg_0], rax
0x180034c91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180034c95  mov     qword ptr [rbp+PerformanceCount], rax
0x180034c99  mov     rax, cs:__security_cookie
0x180034ca0  cmp     rax, rbx
0x180034ca3  jnz     loc_180034D3C
0x180034ca9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180034cad  call    cs:__imp_GetSystemTimeAsFileTime
0x180034cb3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180034cb7  mov     [rbp+arg_0], rax
0x180034cbb  call    cs:__imp_GetCurrentProcessId
0x180034cc1  mov     eax, eax
0x180034cc3  xor     [rbp+arg_0], rax
0x180034cc7  call    cs:__imp_GetCurrentThreadId
0x180034ccd  mov     eax, eax
0x180034ccf  xor     [rbp+arg_0], rax
0x180034cd3  call    cs:__imp_GetTickCount
0x180034cd9  mov     eax, eax
0x180034cdb  shl     rax, 18h
0x180034cdf  xor     [rbp+arg_0], rax
0x180034ce3  call    cs:__imp_GetTickCount
0x180034ce9  mov     eax, eax
0x180034ceb  lea     rcx, [rbp+arg_0]
0x180034cef  xor     rax, [rbp+arg_0]
0x180034cf3  xor     rax, rcx
0x180034cf6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180034cfa  mov     [rbp+arg_0], rax
0x180034cfe  call    cs:__imp_QueryPerformanceCounter
0x180034d04  mov     eax, dword ptr [rbp+PerformanceCount]
0x180034d07  mov     rcx, 0FFFFFFFFFFFFh
0x180034d11  shl     rax, 20h
0x180034d15  xor     rax, qword ptr [rbp+PerformanceCount]
0x180034d19  xor     rax, [rbp+arg_0]
0x180034d1d  and     rax, rcx
0x180034d20  mov     rcx, rax
0x180034d23  cmp     rax, rbx
0x180034d26  jnz     short loc_180034D35
0x180034d28  mov     rax, 2B992DDFA233h
0x180034d32  mov     rcx, rax
0x180034d35  mov     cs:__security_cookie, rcx
0x180034d3c  mov     rbx, [rsp+20h+arg_18]
0x180034d41  not     rax
0x180034d44  mov     cs:__security_cookie_complement, rax
0x180034d4b  add     rsp, 20h
0x180034d4f  pop     rbp
0x180034d50  retn
```
