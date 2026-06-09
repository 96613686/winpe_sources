# __security_init_cookie

- ea: `0x180002694`
- end: `0x180002771`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002150`

## callees

- `0x180002694`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002703`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800026f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002703`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800026cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800026cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800026e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000271e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000271e`

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
0x180002694  mov     [rsp-8+arg_18], rbx
0x180002699  push    rbp
0x18000269a  mov     rbp, rsp
0x18000269d  sub     rsp, 20h
0x1800026a1  xor     eax, eax
0x1800026a3  mov     rbx, 2B992DDFA232h
0x1800026ad  mov     [rbp+arg_0], rax
0x1800026b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800026b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800026b9  mov     rax, cs:__security_cookie
0x1800026c0  cmp     rax, rbx
0x1800026c3  jnz     loc_18000275C
0x1800026c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800026cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800026d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800026d7  mov     [rbp+arg_0], rax
0x1800026db  call    cs:__imp_GetCurrentProcessId
0x1800026e1  mov     eax, eax
0x1800026e3  xor     [rbp+arg_0], rax
0x1800026e7  call    cs:__imp_GetCurrentThreadId
0x1800026ed  mov     eax, eax
0x1800026ef  xor     [rbp+arg_0], rax
0x1800026f3  call    cs:__imp_GetTickCount
0x1800026f9  mov     eax, eax
0x1800026fb  shl     rax, 18h
0x1800026ff  xor     [rbp+arg_0], rax
0x180002703  call    cs:__imp_GetTickCount
0x180002709  mov     eax, eax
0x18000270b  lea     rcx, [rbp+arg_0]
0x18000270f  xor     rax, [rbp+arg_0]
0x180002713  xor     rax, rcx
0x180002716  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000271a  mov     [rbp+arg_0], rax
0x18000271e  call    cs:__imp_QueryPerformanceCounter
0x180002724  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002727  mov     rcx, 0FFFFFFFFFFFFh
0x180002731  shl     rax, 20h
0x180002735  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002739  xor     rax, [rbp+arg_0]
0x18000273d  and     rax, rcx
0x180002740  mov     rcx, rax
0x180002743  cmp     rax, rbx
0x180002746  jnz     short loc_180002755
0x180002748  mov     rax, 2B992DDFA233h
0x180002752  mov     rcx, rax
0x180002755  mov     cs:__security_cookie, rcx
0x18000275c  mov     rbx, [rsp+20h+arg_18]
0x180002761  not     rax
0x180002764  mov     cs:__security_cookie_complement, rax
0x18000276b  add     rsp, 20h
0x18000276f  pop     rbp
0x180002770  retn
```
