# __security_init_cookie

- ea: `0x1800133d4`
- end: `0x1800134b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012e90`

## callees

- `0x1800133d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013427`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013427`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001341b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001341b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013433`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013443`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013433`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013443`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001340d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001340d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001345e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001345e`

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
0x1800133d4  mov     [rsp-8+arg_18], rbx
0x1800133d9  push    rbp
0x1800133da  mov     rbp, rsp
0x1800133dd  sub     rsp, 20h
0x1800133e1  xor     eax, eax
0x1800133e3  mov     rbx, 2B992DDFA232h
0x1800133ed  mov     [rbp+arg_0], rax
0x1800133f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800133f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800133f9  mov     rax, cs:__security_cookie
0x180013400  cmp     rax, rbx
0x180013403  jnz     loc_18001349C
0x180013409  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001340d  call    cs:__imp_GetSystemTimeAsFileTime
0x180013413  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180013417  mov     [rbp+arg_0], rax
0x18001341b  call    cs:__imp_GetCurrentProcessId
0x180013421  mov     eax, eax
0x180013423  xor     [rbp+arg_0], rax
0x180013427  call    cs:__imp_GetCurrentThreadId
0x18001342d  mov     eax, eax
0x18001342f  xor     [rbp+arg_0], rax
0x180013433  call    cs:__imp_GetTickCount
0x180013439  mov     eax, eax
0x18001343b  shl     rax, 18h
0x18001343f  xor     [rbp+arg_0], rax
0x180013443  call    cs:__imp_GetTickCount
0x180013449  mov     eax, eax
0x18001344b  lea     rcx, [rbp+arg_0]
0x18001344f  xor     rax, [rbp+arg_0]
0x180013453  xor     rax, rcx
0x180013456  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001345a  mov     [rbp+arg_0], rax
0x18001345e  call    cs:__imp_QueryPerformanceCounter
0x180013464  mov     eax, dword ptr [rbp+PerformanceCount]
0x180013467  mov     rcx, 0FFFFFFFFFFFFh
0x180013471  shl     rax, 20h
0x180013475  xor     rax, qword ptr [rbp+PerformanceCount]
0x180013479  xor     rax, [rbp+arg_0]
0x18001347d  and     rax, rcx
0x180013480  mov     rcx, rax
0x180013483  cmp     rax, rbx
0x180013486  jnz     short loc_180013495
0x180013488  mov     rax, 2B992DDFA233h
0x180013492  mov     rcx, rax
0x180013495  mov     cs:__security_cookie, rcx
0x18001349c  mov     rbx, [rsp+20h+arg_18]
0x1800134a1  not     rax
0x1800134a4  mov     cs:__security_cookie_complement, rax
0x1800134ab  add     rsp, 20h
0x1800134af  pop     rbp
0x1800134b0  retn
```
