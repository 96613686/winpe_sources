# __security_init_cookie

- ea: `0x18001bec4`
- end: `0x18001bf9d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b760`

## callees

- `0x18001bec4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bf13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bf07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bf07`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bef9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bef9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bf1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bf2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bf1f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bf2f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001bf4a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001bf4a`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x18001bec4  mov     [rsp-8+arg_18], rbx
0x18001bec9  push    rbp
0x18001beca  mov     rbp, rsp
0x18001becd  sub     rsp, 20h
0x18001bed1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001bed6  mov     rbx, 2B992DDFA232h
0x18001bee0  and     qword ptr [rbp+PerformanceCount], 0
0x18001bee5  mov     rax, cs:__security_cookie
0x18001beec  cmp     rax, rbx
0x18001beef  jnz     loc_18001BF88
0x18001bef5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001bef9  call    cs:__imp_GetSystemTimeAsFileTime
0x18001beff  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001bf03  mov     [rbp+arg_0], rax
0x18001bf07  call    cs:__imp_GetCurrentProcessId
0x18001bf0d  mov     eax, eax
0x18001bf0f  xor     [rbp+arg_0], rax
0x18001bf13  call    cs:__imp_GetCurrentThreadId
0x18001bf19  mov     eax, eax
0x18001bf1b  xor     [rbp+arg_0], rax
0x18001bf1f  call    cs:__imp_GetTickCount
0x18001bf25  mov     eax, eax
0x18001bf27  shl     rax, 18h
0x18001bf2b  xor     [rbp+arg_0], rax
0x18001bf2f  call    cs:__imp_GetTickCount
0x18001bf35  mov     eax, eax
0x18001bf37  lea     rcx, [rbp+arg_0]
0x18001bf3b  xor     rax, [rbp+arg_0]
0x18001bf3f  xor     rax, rcx
0x18001bf42  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001bf46  mov     [rbp+arg_0], rax
0x18001bf4a  call    cs:__imp_QueryPerformanceCounter
0x18001bf50  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001bf53  mov     rcx, 0FFFFFFFFFFFFh
0x18001bf5d  shl     rax, 20h
0x18001bf61  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001bf65  xor     rax, [rbp+arg_0]
0x18001bf69  and     rax, rcx
0x18001bf6c  mov     rcx, rax
0x18001bf6f  cmp     rax, rbx
0x18001bf72  jnz     short loc_18001BF81
0x18001bf74  mov     rax, 2B992DDFA233h
0x18001bf7e  mov     rcx, rax
0x18001bf81  mov     cs:__security_cookie, rcx
0x18001bf88  mov     rbx, [rsp+20h+arg_18]
0x18001bf8d  not     rax
0x18001bf90  mov     cs:__security_cookie_complement, rax
0x18001bf97  add     rsp, 20h
0x18001bf9b  pop     rbp
0x18001bf9c  retn
```
