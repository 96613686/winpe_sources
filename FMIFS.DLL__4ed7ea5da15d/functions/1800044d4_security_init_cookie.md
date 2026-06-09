# __security_init_cookie

- ea: `0x1800044d4`
- end: `0x1800045b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004180`

## callees

- `0x1800044d4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000455e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000455e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000451b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000451b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004527`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004533`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004543`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004533`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004543`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000450d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000450d`

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
0x1800044d4  mov     [rsp-8+arg_18], rbx
0x1800044d9  push    rbp
0x1800044da  mov     rbp, rsp
0x1800044dd  sub     rsp, 20h
0x1800044e1  xor     eax, eax
0x1800044e3  mov     rbx, 2B992DDFA232h
0x1800044ed  mov     [rbp+arg_0], rax
0x1800044f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800044f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800044f9  mov     rax, cs:__security_cookie
0x180004500  cmp     rax, rbx
0x180004503  jnz     loc_18000459C
0x180004509  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000450d  call    cs:__imp_GetSystemTimeAsFileTime
0x180004513  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004517  mov     [rbp+arg_0], rax
0x18000451b  call    cs:__imp_GetCurrentProcessId
0x180004521  mov     eax, eax
0x180004523  xor     [rbp+arg_0], rax
0x180004527  call    cs:__imp_GetCurrentThreadId
0x18000452d  mov     eax, eax
0x18000452f  xor     [rbp+arg_0], rax
0x180004533  call    cs:__imp_GetTickCount
0x180004539  mov     eax, eax
0x18000453b  shl     rax, 18h
0x18000453f  xor     [rbp+arg_0], rax
0x180004543  call    cs:__imp_GetTickCount
0x180004549  mov     eax, eax
0x18000454b  lea     rcx, [rbp+arg_0]
0x18000454f  xor     rax, [rbp+arg_0]
0x180004553  xor     rax, rcx
0x180004556  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000455a  mov     [rbp+arg_0], rax
0x18000455e  call    cs:__imp_QueryPerformanceCounter
0x180004564  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004567  mov     rcx, 0FFFFFFFFFFFFh
0x180004571  shl     rax, 20h
0x180004575  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004579  xor     rax, [rbp+arg_0]
0x18000457d  and     rax, rcx
0x180004580  mov     rcx, rax
0x180004583  cmp     rax, rbx
0x180004586  jnz     short loc_180004595
0x180004588  mov     rax, 2B992DDFA233h
0x180004592  mov     rcx, rax
0x180004595  mov     cs:__security_cookie, rcx
0x18000459c  mov     rbx, [rsp+20h+arg_18]
0x1800045a1  not     rax
0x1800045a4  mov     cs:__security_cookie_complement, rax
0x1800045ab  add     rsp, 20h
0x1800045af  pop     rbp
0x1800045b0  retn
```
