# __security_init_cookie

- ea: `0x18001baf4`
- end: `0x18001bbcd`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b390`

## callees

- `0x18001baf4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bb37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001bb37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001bb43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bb4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bb5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bb4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001bb5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb29`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001bb29`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001bb7a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001bb7a`

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
0x18001baf4  mov     [rsp-8+arg_18], rbx
0x18001baf9  push    rbp
0x18001bafa  mov     rbp, rsp
0x18001bafd  sub     rsp, 20h
0x18001bb01  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18001bb06  mov     rbx, 2B992DDFA232h
0x18001bb10  and     qword ptr [rbp+PerformanceCount], 0
0x18001bb15  mov     rax, cs:__security_cookie
0x18001bb1c  cmp     rax, rbx
0x18001bb1f  jnz     loc_18001BBB8
0x18001bb25  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001bb29  call    cs:__imp_GetSystemTimeAsFileTime
0x18001bb2f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001bb33  mov     [rbp+arg_0], rax
0x18001bb37  call    cs:__imp_GetCurrentProcessId
0x18001bb3d  mov     eax, eax
0x18001bb3f  xor     [rbp+arg_0], rax
0x18001bb43  call    cs:__imp_GetCurrentThreadId
0x18001bb49  mov     eax, eax
0x18001bb4b  xor     [rbp+arg_0], rax
0x18001bb4f  call    cs:__imp_GetTickCount
0x18001bb55  mov     eax, eax
0x18001bb57  shl     rax, 18h
0x18001bb5b  xor     [rbp+arg_0], rax
0x18001bb5f  call    cs:__imp_GetTickCount
0x18001bb65  mov     eax, eax
0x18001bb67  lea     rcx, [rbp+arg_0]
0x18001bb6b  xor     rax, [rbp+arg_0]
0x18001bb6f  xor     rax, rcx
0x18001bb72  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001bb76  mov     [rbp+arg_0], rax
0x18001bb7a  call    cs:__imp_QueryPerformanceCounter
0x18001bb80  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001bb83  mov     rcx, 0FFFFFFFFFFFFh
0x18001bb8d  shl     rax, 20h
0x18001bb91  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001bb95  xor     rax, [rbp+arg_0]
0x18001bb99  and     rax, rcx
0x18001bb9c  mov     rcx, rax
0x18001bb9f  cmp     rax, rbx
0x18001bba2  jnz     short loc_18001BBB1
0x18001bba4  mov     rax, 2B992DDFA233h
0x18001bbae  mov     rcx, rax
0x18001bbb1  mov     cs:__security_cookie, rcx
0x18001bbb8  mov     rbx, [rsp+20h+arg_18]
0x18001bbbd  not     rax
0x18001bbc0  mov     cs:__security_cookie_complement, rax
0x18001bbc7  add     rsp, 20h
0x18001bbcb  pop     rbp
0x18001bbcc  retn
```
