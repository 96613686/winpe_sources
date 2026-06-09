# __security_init_cookie

- ea: `0x18000a274`
- end: `0x18000a351`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009df0`

## callees

- `0x18000a274`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a2bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a2bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a2fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a2fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a2ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a2ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a2d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a2e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a2d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a2e3`

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
0x18000a274  mov     [rsp-8+arg_18], rbx
0x18000a279  push    rbp
0x18000a27a  mov     rbp, rsp
0x18000a27d  sub     rsp, 20h
0x18000a281  xor     eax, eax
0x18000a283  mov     rbx, 2B992DDFA232h
0x18000a28d  mov     [rbp+arg_0], rax
0x18000a291  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000a295  mov     qword ptr [rbp+PerformanceCount], rax
0x18000a299  mov     rax, cs:__security_cookie
0x18000a2a0  cmp     rax, rbx
0x18000a2a3  jnz     loc_18000A33C
0x18000a2a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000a2ad  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a2b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000a2b7  mov     [rbp+arg_0], rax
0x18000a2bb  call    cs:__imp_GetCurrentProcessId
0x18000a2c1  mov     eax, eax
0x18000a2c3  xor     [rbp+arg_0], rax
0x18000a2c7  call    cs:__imp_GetCurrentThreadId
0x18000a2cd  mov     eax, eax
0x18000a2cf  xor     [rbp+arg_0], rax
0x18000a2d3  call    cs:__imp_GetTickCount
0x18000a2d9  mov     eax, eax
0x18000a2db  shl     rax, 18h
0x18000a2df  xor     [rbp+arg_0], rax
0x18000a2e3  call    cs:__imp_GetTickCount
0x18000a2e9  mov     eax, eax
0x18000a2eb  lea     rcx, [rbp+arg_0]
0x18000a2ef  xor     rax, [rbp+arg_0]
0x18000a2f3  xor     rax, rcx
0x18000a2f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000a2fa  mov     [rbp+arg_0], rax
0x18000a2fe  call    cs:__imp_QueryPerformanceCounter
0x18000a304  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000a307  mov     rcx, 0FFFFFFFFFFFFh
0x18000a311  shl     rax, 20h
0x18000a315  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000a319  xor     rax, [rbp+arg_0]
0x18000a31d  and     rax, rcx
0x18000a320  mov     rcx, rax
0x18000a323  cmp     rax, rbx
0x18000a326  jnz     short loc_18000A335
0x18000a328  mov     rax, 2B992DDFA233h
0x18000a332  mov     rcx, rax
0x18000a335  mov     cs:__security_cookie, rcx
0x18000a33c  mov     rbx, [rsp+20h+arg_18]
0x18000a341  not     rax
0x18000a344  mov     cs:__security_cookie_complement, rax
0x18000a34b  add     rsp, 20h
0x18000a34f  pop     rbp
0x18000a350  retn
```
