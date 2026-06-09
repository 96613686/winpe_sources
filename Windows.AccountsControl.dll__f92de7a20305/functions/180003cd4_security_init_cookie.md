# __security_init_cookie

- ea: `0x180003cd4`
- end: `0x180003db1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800035c0`

## callees

- `0x180003cd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003d1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003d5e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003d5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003d33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003d43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003d33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003d43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003d0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003d0d`

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
0x180003cd4  mov     [rsp-8+arg_18], rbx
0x180003cd9  push    rbp
0x180003cda  mov     rbp, rsp
0x180003cdd  sub     rsp, 20h
0x180003ce1  xor     eax, eax
0x180003ce3  mov     rbx, 2B992DDFA232h
0x180003ced  mov     [rbp+arg_0], rax
0x180003cf1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003cf5  mov     qword ptr [rbp+PerformanceCount], rax
0x180003cf9  mov     rax, cs:__security_cookie
0x180003d00  cmp     rax, rbx
0x180003d03  jnz     loc_180003D9C
0x180003d09  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003d0d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003d13  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003d17  mov     [rbp+arg_0], rax
0x180003d1b  call    cs:__imp_GetCurrentProcessId
0x180003d21  mov     eax, eax
0x180003d23  xor     [rbp+arg_0], rax
0x180003d27  call    cs:__imp_GetCurrentThreadId
0x180003d2d  mov     eax, eax
0x180003d2f  xor     [rbp+arg_0], rax
0x180003d33  call    cs:__imp_GetTickCount
0x180003d39  mov     eax, eax
0x180003d3b  shl     rax, 18h
0x180003d3f  xor     [rbp+arg_0], rax
0x180003d43  call    cs:__imp_GetTickCount
0x180003d49  mov     eax, eax
0x180003d4b  lea     rcx, [rbp+arg_0]
0x180003d4f  xor     rax, [rbp+arg_0]
0x180003d53  xor     rax, rcx
0x180003d56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003d5a  mov     [rbp+arg_0], rax
0x180003d5e  call    cs:__imp_QueryPerformanceCounter
0x180003d64  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003d67  mov     rcx, 0FFFFFFFFFFFFh
0x180003d71  shl     rax, 20h
0x180003d75  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003d79  xor     rax, [rbp+arg_0]
0x180003d7d  and     rax, rcx
0x180003d80  mov     rcx, rax
0x180003d83  cmp     rax, rbx
0x180003d86  jnz     short loc_180003D95
0x180003d88  mov     rax, 2B992DDFA233h
0x180003d92  mov     rcx, rax
0x180003d95  mov     cs:__security_cookie, rcx
0x180003d9c  mov     rbx, [rsp+20h+arg_18]
0x180003da1  not     rax
0x180003da4  mov     cs:__security_cookie_complement, rax
0x180003dab  add     rsp, 20h
0x180003daf  pop     rbp
0x180003db0  retn
```
