# __security_init_cookie

- ea: `0x180005f94`
- end: `0x180006071`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005df0`

## callees

- `0x180005f94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fe7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fe7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005fdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005fdb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000601e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000601e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005fcd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005fcd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005ff3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006003`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005ff3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006003`

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
0x180005f94  mov     [rsp-8+arg_18], rbx
0x180005f99  push    rbp
0x180005f9a  mov     rbp, rsp
0x180005f9d  sub     rsp, 20h
0x180005fa1  xor     eax, eax
0x180005fa3  mov     rbx, 2B992DDFA232h
0x180005fad  mov     [rbp+arg_0], rax
0x180005fb1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005fb5  mov     qword ptr [rbp+PerformanceCount], rax
0x180005fb9  mov     rax, cs:__security_cookie
0x180005fc0  cmp     rax, rbx
0x180005fc3  jnz     loc_18000605C
0x180005fc9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005fcd  call    cs:__imp_GetSystemTimeAsFileTime
0x180005fd3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005fd7  mov     [rbp+arg_0], rax
0x180005fdb  call    cs:__imp_GetCurrentProcessId
0x180005fe1  mov     eax, eax
0x180005fe3  xor     [rbp+arg_0], rax
0x180005fe7  call    cs:__imp_GetCurrentThreadId
0x180005fed  mov     eax, eax
0x180005fef  xor     [rbp+arg_0], rax
0x180005ff3  call    cs:__imp_GetTickCount
0x180005ff9  mov     eax, eax
0x180005ffb  shl     rax, 18h
0x180005fff  xor     [rbp+arg_0], rax
0x180006003  call    cs:__imp_GetTickCount
0x180006009  mov     eax, eax
0x18000600b  lea     rcx, [rbp+arg_0]
0x18000600f  xor     rax, [rbp+arg_0]
0x180006013  xor     rax, rcx
0x180006016  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000601a  mov     [rbp+arg_0], rax
0x18000601e  call    cs:__imp_QueryPerformanceCounter
0x180006024  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006027  mov     rcx, 0FFFFFFFFFFFFh
0x180006031  shl     rax, 20h
0x180006035  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006039  xor     rax, [rbp+arg_0]
0x18000603d  and     rax, rcx
0x180006040  mov     rcx, rax
0x180006043  cmp     rax, rbx
0x180006046  jnz     short loc_180006055
0x180006048  mov     rax, 2B992DDFA233h
0x180006052  mov     rcx, rax
0x180006055  mov     cs:__security_cookie, rcx
0x18000605c  mov     rbx, [rsp+20h+arg_18]
0x180006061  not     rax
0x180006064  mov     cs:__security_cookie_complement, rax
0x18000606b  add     rsp, 20h
0x18000606f  pop     rbp
0x180006070  retn
```
