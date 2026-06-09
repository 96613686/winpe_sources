# __security_init_cookie

- ea: `0x140002858`
- end: `0x14000290d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400021e0`

## callees

- `0x140002858`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400028a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400028a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000289b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000289b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400028b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400028b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000288d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000288d`

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
0x140002858  mov     [rsp-8+arg_10], rbx
0x14000285d  push    rbp
0x14000285e  mov     rbp, rsp
0x140002861  sub     rsp, 30h
0x140002865  mov     rax, cs:__security_cookie
0x14000286c  mov     rbx, 2B992DDFA232h
0x140002876  cmp     rax, rbx
0x140002879  jnz     short loc_1400028F8
0x14000287b  xor     eax, eax
0x14000287d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002881  mov     [rbp+var_10], rax
0x140002885  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002889  mov     qword ptr [rbp+PerformanceCount], rax
0x14000288d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002893  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002897  mov     [rbp+var_10], rax
0x14000289b  call    cs:__imp_GetCurrentThreadId
0x1400028a1  mov     eax, eax
0x1400028a3  xor     [rbp+var_10], rax
0x1400028a7  call    cs:__imp_GetCurrentProcessId
0x1400028ad  mov     eax, eax
0x1400028af  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400028b3  xor     [rbp+var_10], rax
0x1400028b7  call    cs:__imp_QueryPerformanceCounter
0x1400028bd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400028c0  lea     rcx, [rbp+var_10]
0x1400028c4  shl     rax, 20h
0x1400028c8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400028cc  xor     rax, [rbp+var_10]
0x1400028d0  xor     rax, rcx
0x1400028d3  mov     rcx, 0FFFFFFFFFFFFh
0x1400028dd  and     rax, rcx
0x1400028e0  mov     rcx, 2B992DDFA233h
0x1400028ea  cmp     rax, rbx
0x1400028ed  cmovz   rax, rcx
0x1400028f1  mov     cs:__security_cookie, rax
0x1400028f8  mov     rbx, [rsp+30h+arg_10]
0x1400028fd  not     rax
0x140002900  mov     cs:__security_cookie_complement, rax
0x140002907  add     rsp, 30h
0x14000290b  pop     rbp
0x14000290c  retn
```
