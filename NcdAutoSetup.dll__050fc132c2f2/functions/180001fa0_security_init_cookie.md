# __security_init_cookie

- ea: `0x180001fa0`
- end: `0x18000207d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001b40`

## callees

- `0x180001fa0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ff3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ff3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001fe7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001fe7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001fff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000200f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001fff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000200f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001fd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001fd9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000202a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000202a`

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
0x180001fa0  mov     [rsp-8+arg_18], rbx
0x180001fa5  push    rbp
0x180001fa6  mov     rbp, rsp
0x180001fa9  sub     rsp, 20h
0x180001fad  xor     eax, eax
0x180001faf  mov     rbx, 2B992DDFA232h
0x180001fb9  mov     [rbp+arg_0], rax
0x180001fbd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001fc1  mov     qword ptr [rbp+PerformanceCount], rax
0x180001fc5  mov     rax, cs:__security_cookie
0x180001fcc  cmp     rax, rbx
0x180001fcf  jnz     loc_180002068
0x180001fd5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001fd9  call    cs:__imp_GetSystemTimeAsFileTime
0x180001fdf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001fe3  mov     [rbp+arg_0], rax
0x180001fe7  call    cs:__imp_GetCurrentProcessId
0x180001fed  mov     eax, eax
0x180001fef  xor     [rbp+arg_0], rax
0x180001ff3  call    cs:__imp_GetCurrentThreadId
0x180001ff9  mov     eax, eax
0x180001ffb  xor     [rbp+arg_0], rax
0x180001fff  call    cs:__imp_GetTickCount
0x180002005  mov     eax, eax
0x180002007  shl     rax, 18h
0x18000200b  xor     [rbp+arg_0], rax
0x18000200f  call    cs:__imp_GetTickCount
0x180002015  mov     eax, eax
0x180002017  lea     rcx, [rbp+arg_0]
0x18000201b  xor     rax, [rbp+arg_0]
0x18000201f  xor     rax, rcx
0x180002022  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002026  mov     [rbp+arg_0], rax
0x18000202a  call    cs:__imp_QueryPerformanceCounter
0x180002030  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002033  mov     rcx, 0FFFFFFFFFFFFh
0x18000203d  shl     rax, 20h
0x180002041  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002045  xor     rax, [rbp+arg_0]
0x180002049  and     rax, rcx
0x18000204c  mov     rcx, rax
0x18000204f  cmp     rax, rbx
0x180002052  jnz     short loc_180002061
0x180002054  mov     rax, 2B992DDFA233h
0x18000205e  mov     rcx, rax
0x180002061  mov     cs:__security_cookie, rcx
0x180002068  mov     rbx, [rsp+20h+arg_18]
0x18000206d  not     rax
0x180002070  mov     cs:__security_cookie_complement, rax
0x180002077  add     rsp, 20h
0x18000207b  pop     rbp
0x18000207c  retn
```
