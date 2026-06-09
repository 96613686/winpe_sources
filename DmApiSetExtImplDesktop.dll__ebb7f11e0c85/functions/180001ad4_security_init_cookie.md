# __security_init_cookie

- ea: `0x180001ad4`
- end: `0x180001bb1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001430`

## callees

- `0x180001ad4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b27`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001b33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001b43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001b33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001b43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b0d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b5e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b5e`

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
0x180001ad4  mov     [rsp-8+arg_18], rbx
0x180001ad9  push    rbp
0x180001ada  mov     rbp, rsp
0x180001add  sub     rsp, 20h
0x180001ae1  xor     eax, eax
0x180001ae3  mov     rbx, 2B992DDFA232h
0x180001aed  mov     [rbp+arg_0], rax
0x180001af1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001af5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001af9  mov     rax, cs:__security_cookie
0x180001b00  cmp     rax, rbx
0x180001b03  jnz     loc_180001B9C
0x180001b09  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001b0d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b13  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001b17  mov     [rbp+arg_0], rax
0x180001b1b  call    cs:__imp_GetCurrentProcessId
0x180001b21  mov     eax, eax
0x180001b23  xor     [rbp+arg_0], rax
0x180001b27  call    cs:__imp_GetCurrentThreadId
0x180001b2d  mov     eax, eax
0x180001b2f  xor     [rbp+arg_0], rax
0x180001b33  call    cs:__imp_GetTickCount
0x180001b39  mov     eax, eax
0x180001b3b  shl     rax, 18h
0x180001b3f  xor     [rbp+arg_0], rax
0x180001b43  call    cs:__imp_GetTickCount
0x180001b49  mov     eax, eax
0x180001b4b  lea     rcx, [rbp+arg_0]
0x180001b4f  xor     rax, [rbp+arg_0]
0x180001b53  xor     rax, rcx
0x180001b56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001b5a  mov     [rbp+arg_0], rax
0x180001b5e  call    cs:__imp_QueryPerformanceCounter
0x180001b64  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001b67  mov     rcx, 0FFFFFFFFFFFFh
0x180001b71  shl     rax, 20h
0x180001b75  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b79  xor     rax, [rbp+arg_0]
0x180001b7d  and     rax, rcx
0x180001b80  mov     rcx, rax
0x180001b83  cmp     rax, rbx
0x180001b86  jnz     short loc_180001B95
0x180001b88  mov     rax, 2B992DDFA233h
0x180001b92  mov     rcx, rax
0x180001b95  mov     cs:__security_cookie, rcx
0x180001b9c  mov     rbx, [rsp+20h+arg_18]
0x180001ba1  not     rax
0x180001ba4  mov     cs:__security_cookie_complement, rax
0x180001bab  add     rsp, 20h
0x180001baf  pop     rbp
0x180001bb0  retn
```
