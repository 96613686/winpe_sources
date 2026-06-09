# __security_init_cookie

- ea: `0x180002484`
- end: `0x180002561`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c60`

## callees

- `0x180002484`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800024bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800024e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800024f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800024e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800024f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000250e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000250e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800024cb`

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
0x180002484  mov     [rsp-8+arg_18], rbx
0x180002489  push    rbp
0x18000248a  mov     rbp, rsp
0x18000248d  sub     rsp, 20h
0x180002491  xor     eax, eax
0x180002493  mov     rbx, 2B992DDFA232h
0x18000249d  mov     [rbp+arg_0], rax
0x1800024a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800024a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800024a9  mov     rax, cs:__security_cookie
0x1800024b0  cmp     rax, rbx
0x1800024b3  jnz     loc_18000254C
0x1800024b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800024bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800024c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800024c7  mov     [rbp+arg_0], rax
0x1800024cb  call    cs:__imp_GetCurrentProcessId
0x1800024d1  mov     eax, eax
0x1800024d3  xor     [rbp+arg_0], rax
0x1800024d7  call    cs:__imp_GetCurrentThreadId
0x1800024dd  mov     eax, eax
0x1800024df  xor     [rbp+arg_0], rax
0x1800024e3  call    cs:__imp_GetTickCount
0x1800024e9  mov     eax, eax
0x1800024eb  shl     rax, 18h
0x1800024ef  xor     [rbp+arg_0], rax
0x1800024f3  call    cs:__imp_GetTickCount
0x1800024f9  mov     eax, eax
0x1800024fb  lea     rcx, [rbp+arg_0]
0x1800024ff  xor     rax, [rbp+arg_0]
0x180002503  xor     rax, rcx
0x180002506  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000250a  mov     [rbp+arg_0], rax
0x18000250e  call    cs:__imp_QueryPerformanceCounter
0x180002514  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002517  mov     rcx, 0FFFFFFFFFFFFh
0x180002521  shl     rax, 20h
0x180002525  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002529  xor     rax, [rbp+arg_0]
0x18000252d  and     rax, rcx
0x180002530  mov     rcx, rax
0x180002533  cmp     rax, rbx
0x180002536  jnz     short loc_180002545
0x180002538  mov     rax, 2B992DDFA233h
0x180002542  mov     rcx, rax
0x180002545  mov     cs:__security_cookie, rcx
0x18000254c  mov     rbx, [rsp+20h+arg_18]
0x180002551  not     rax
0x180002554  mov     cs:__security_cookie_complement, rax
0x18000255b  add     rsp, 20h
0x18000255f  pop     rbp
0x180002560  retn
```
