# __security_init_cookie

- ea: `0x180056364`
- end: `0x180056441`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055d70`

## callees

- `0x180056364`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800563b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800563b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800563ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800563ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800563ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800563ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800563c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800563d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800563c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800563d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005639d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005639d`

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
0x180056364  mov     [rsp-8+arg_18], rbx
0x180056369  push    rbp
0x18005636a  mov     rbp, rsp
0x18005636d  sub     rsp, 20h
0x180056371  xor     eax, eax
0x180056373  mov     rbx, 2B992DDFA232h
0x18005637d  mov     [rbp+arg_0], rax
0x180056381  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180056385  mov     qword ptr [rbp+PerformanceCount], rax
0x180056389  mov     rax, cs:__security_cookie
0x180056390  cmp     rax, rbx
0x180056393  jnz     loc_18005642C
0x180056399  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005639d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800563a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800563a7  mov     [rbp+arg_0], rax
0x1800563ab  call    cs:__imp_GetCurrentProcessId
0x1800563b1  mov     eax, eax
0x1800563b3  xor     [rbp+arg_0], rax
0x1800563b7  call    cs:__imp_GetCurrentThreadId
0x1800563bd  mov     eax, eax
0x1800563bf  xor     [rbp+arg_0], rax
0x1800563c3  call    cs:__imp_GetTickCount
0x1800563c9  mov     eax, eax
0x1800563cb  shl     rax, 18h
0x1800563cf  xor     [rbp+arg_0], rax
0x1800563d3  call    cs:__imp_GetTickCount
0x1800563d9  mov     eax, eax
0x1800563db  lea     rcx, [rbp+arg_0]
0x1800563df  xor     rax, [rbp+arg_0]
0x1800563e3  xor     rax, rcx
0x1800563e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800563ea  mov     [rbp+arg_0], rax
0x1800563ee  call    cs:__imp_QueryPerformanceCounter
0x1800563f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800563f7  mov     rcx, 0FFFFFFFFFFFFh
0x180056401  shl     rax, 20h
0x180056405  xor     rax, qword ptr [rbp+PerformanceCount]
0x180056409  xor     rax, [rbp+arg_0]
0x18005640d  and     rax, rcx
0x180056410  mov     rcx, rax
0x180056413  cmp     rax, rbx
0x180056416  jnz     short loc_180056425
0x180056418  mov     rax, 2B992DDFA233h
0x180056422  mov     rcx, rax
0x180056425  mov     cs:__security_cookie, rcx
0x18005642c  mov     rbx, [rsp+20h+arg_18]
0x180056431  not     rax
0x180056434  mov     cs:__security_cookie_complement, rax
0x18005643b  add     rsp, 20h
0x18005643f  pop     rbp
0x180056440  retn
```
