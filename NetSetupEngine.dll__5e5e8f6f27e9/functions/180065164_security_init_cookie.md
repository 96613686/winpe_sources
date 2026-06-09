# __security_init_cookie

- ea: `0x180065164`
- end: `0x180065241`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180064b10`

## callees

- `0x180065164`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800651b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800651b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800651ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800651ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800651ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800651ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800651c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800651d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800651c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800651d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006519d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006519d`

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
0x180065164  mov     [rsp-8+arg_18], rbx
0x180065169  push    rbp
0x18006516a  mov     rbp, rsp
0x18006516d  sub     rsp, 20h
0x180065171  xor     eax, eax
0x180065173  mov     rbx, 2B992DDFA232h
0x18006517d  mov     [rbp+arg_0], rax
0x180065181  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180065185  mov     qword ptr [rbp+PerformanceCount], rax
0x180065189  mov     rax, cs:__security_cookie
0x180065190  cmp     rax, rbx
0x180065193  jnz     loc_18006522C
0x180065199  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006519d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800651a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800651a7  mov     [rbp+arg_0], rax
0x1800651ab  call    cs:__imp_GetCurrentProcessId
0x1800651b1  mov     eax, eax
0x1800651b3  xor     [rbp+arg_0], rax
0x1800651b7  call    cs:__imp_GetCurrentThreadId
0x1800651bd  mov     eax, eax
0x1800651bf  xor     [rbp+arg_0], rax
0x1800651c3  call    cs:__imp_GetTickCount
0x1800651c9  mov     eax, eax
0x1800651cb  shl     rax, 18h
0x1800651cf  xor     [rbp+arg_0], rax
0x1800651d3  call    cs:__imp_GetTickCount
0x1800651d9  mov     eax, eax
0x1800651db  lea     rcx, [rbp+arg_0]
0x1800651df  xor     rax, [rbp+arg_0]
0x1800651e3  xor     rax, rcx
0x1800651e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800651ea  mov     [rbp+arg_0], rax
0x1800651ee  call    cs:__imp_QueryPerformanceCounter
0x1800651f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800651f7  mov     rcx, 0FFFFFFFFFFFFh
0x180065201  shl     rax, 20h
0x180065205  xor     rax, qword ptr [rbp+PerformanceCount]
0x180065209  xor     rax, [rbp+arg_0]
0x18006520d  and     rax, rcx
0x180065210  mov     rcx, rax
0x180065213  cmp     rax, rbx
0x180065216  jnz     short loc_180065225
0x180065218  mov     rax, 2B992DDFA233h
0x180065222  mov     rcx, rax
0x180065225  mov     cs:__security_cookie, rcx
0x18006522c  mov     rbx, [rsp+20h+arg_18]
0x180065231  not     rax
0x180065234  mov     cs:__security_cookie_complement, rax
0x18006523b  add     rsp, 20h
0x18006523f  pop     rbp
0x180065240  retn
```
