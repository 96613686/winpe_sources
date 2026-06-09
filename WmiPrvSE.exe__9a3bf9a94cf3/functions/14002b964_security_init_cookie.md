# __security_init_cookie

- ea: `0x14002b964`
- end: `0x14002ba41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002b020`

## callees

- `0x14002b964`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002b9b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002b9b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002b9ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14002b9ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002b99d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14002b99d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002b9c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002b9d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002b9c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002b9d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14002b9ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14002b9ee`

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
0x14002b964  mov     [rsp-8+arg_18], rbx
0x14002b969  push    rbp
0x14002b96a  mov     rbp, rsp
0x14002b96d  sub     rsp, 20h
0x14002b971  xor     eax, eax
0x14002b973  mov     rbx, 2B992DDFA232h
0x14002b97d  mov     [rbp+arg_0], rax
0x14002b981  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14002b985  mov     qword ptr [rbp+PerformanceCount], rax
0x14002b989  mov     rax, cs:__security_cookie
0x14002b990  cmp     rax, rbx
0x14002b993  jnz     loc_14002BA2C
0x14002b999  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14002b99d  call    cs:__imp_GetSystemTimeAsFileTime
0x14002b9a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14002b9a7  mov     [rbp+arg_0], rax
0x14002b9ab  call    cs:__imp_GetCurrentProcessId
0x14002b9b1  mov     eax, eax
0x14002b9b3  xor     [rbp+arg_0], rax
0x14002b9b7  call    cs:__imp_GetCurrentThreadId
0x14002b9bd  mov     eax, eax
0x14002b9bf  xor     [rbp+arg_0], rax
0x14002b9c3  call    cs:__imp_GetTickCount
0x14002b9c9  mov     eax, eax
0x14002b9cb  shl     rax, 18h
0x14002b9cf  xor     [rbp+arg_0], rax
0x14002b9d3  call    cs:__imp_GetTickCount
0x14002b9d9  mov     eax, eax
0x14002b9db  lea     rcx, [rbp+arg_0]
0x14002b9df  xor     rax, [rbp+arg_0]
0x14002b9e3  xor     rax, rcx
0x14002b9e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14002b9ea  mov     [rbp+arg_0], rax
0x14002b9ee  call    cs:__imp_QueryPerformanceCounter
0x14002b9f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x14002b9f7  mov     rcx, 0FFFFFFFFFFFFh
0x14002ba01  shl     rax, 20h
0x14002ba05  xor     rax, qword ptr [rbp+PerformanceCount]
0x14002ba09  xor     rax, [rbp+arg_0]
0x14002ba0d  and     rax, rcx
0x14002ba10  mov     rcx, rax
0x14002ba13  cmp     rax, rbx
0x14002ba16  jnz     short loc_14002BA25
0x14002ba18  mov     rax, 2B992DDFA233h
0x14002ba22  mov     rcx, rax
0x14002ba25  mov     cs:__security_cookie, rcx
0x14002ba2c  mov     rbx, [rsp+20h+arg_18]
0x14002ba31  not     rax
0x14002ba34  mov     cs:__security_cookie_complement, rax
0x14002ba3b  add     rsp, 20h
0x14002ba3f  pop     rbp
0x14002ba40  retn
```
