# __security_init_cookie

- ea: `0x180005164`
- end: `0x180005241`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800046f0`

## callees

- `0x180005164`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800051c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800051d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800051c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800051d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000519d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000519d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800051ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800051ee`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180005164  mov     [rsp-8+arg_18], rbx
0x180005169  push    rbp
0x18000516a  mov     rbp, rsp
0x18000516d  sub     rsp, 20h
0x180005171  xor     eax, eax
0x180005173  mov     rbx, 2B992DDFA232h
0x18000517d  mov     [rbp+arg_0], rax
0x180005181  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005185  mov     qword ptr [rbp+PerformanceCount], rax
0x180005189  mov     rax, cs:__security_cookie
0x180005190  cmp     rax, rbx
0x180005193  jnz     loc_18000522C
0x180005199  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000519d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800051a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800051a7  mov     [rbp+arg_0], rax
0x1800051ab  call    cs:__imp_GetCurrentProcessId
0x1800051b1  mov     eax, eax
0x1800051b3  xor     [rbp+arg_0], rax
0x1800051b7  call    cs:__imp_GetCurrentThreadId
0x1800051bd  mov     eax, eax
0x1800051bf  xor     [rbp+arg_0], rax
0x1800051c3  call    cs:__imp_GetTickCount
0x1800051c9  mov     eax, eax
0x1800051cb  shl     rax, 18h
0x1800051cf  xor     [rbp+arg_0], rax
0x1800051d3  call    cs:__imp_GetTickCount
0x1800051d9  mov     eax, eax
0x1800051db  lea     rcx, [rbp+arg_0]
0x1800051df  xor     rax, [rbp+arg_0]
0x1800051e3  xor     rax, rcx
0x1800051e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800051ea  mov     [rbp+arg_0], rax
0x1800051ee  call    cs:__imp_QueryPerformanceCounter
0x1800051f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800051f7  mov     rcx, 0FFFFFFFFFFFFh
0x180005201  shl     rax, 20h
0x180005205  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005209  xor     rax, [rbp+arg_0]
0x18000520d  and     rax, rcx
0x180005210  mov     rcx, rax
0x180005213  cmp     rax, rbx
0x180005216  jnz     short loc_180005225
0x180005218  mov     rax, 2B992DDFA233h
0x180005222  mov     rcx, rax
0x180005225  mov     cs:__security_cookie, rcx
0x18000522c  mov     rbx, [rsp+20h+arg_18]
0x180005231  not     rax
0x180005234  mov     cs:__security_cookie_complement, rax
0x18000523b  add     rsp, 20h
0x18000523f  pop     rbp
0x180005240  retn
```
