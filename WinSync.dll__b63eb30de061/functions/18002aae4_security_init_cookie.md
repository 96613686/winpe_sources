# __security_init_cookie

- ea: `0x18002aae4`
- end: `0x18002abc1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a7a0`

## callees

- `0x18002aae4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ab6e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ab6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002ab2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002ab2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab37`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ab43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ab53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ab43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002ab53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ab1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ab1d`

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
0x18002aae4  mov     [rsp-8+arg_18], rbx
0x18002aae9  push    rbp
0x18002aaea  mov     rbp, rsp
0x18002aaed  sub     rsp, 20h
0x18002aaf1  xor     eax, eax
0x18002aaf3  mov     rbx, 2B992DDFA232h
0x18002aafd  mov     [rbp+arg_0], rax
0x18002ab01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002ab05  mov     qword ptr [rbp+PerformanceCount], rax
0x18002ab09  mov     rax, cs:__security_cookie
0x18002ab10  cmp     rax, rbx
0x18002ab13  jnz     loc_18002ABAC
0x18002ab19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002ab1d  call    cs:__imp_GetSystemTimeAsFileTime
0x18002ab23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002ab27  mov     [rbp+arg_0], rax
0x18002ab2b  call    cs:__imp_GetCurrentProcessId
0x18002ab31  mov     eax, eax
0x18002ab33  xor     [rbp+arg_0], rax
0x18002ab37  call    cs:__imp_GetCurrentThreadId
0x18002ab3d  mov     eax, eax
0x18002ab3f  xor     [rbp+arg_0], rax
0x18002ab43  call    cs:__imp_GetTickCount
0x18002ab49  mov     eax, eax
0x18002ab4b  shl     rax, 18h
0x18002ab4f  xor     [rbp+arg_0], rax
0x18002ab53  call    cs:__imp_GetTickCount
0x18002ab59  mov     eax, eax
0x18002ab5b  lea     rcx, [rbp+arg_0]
0x18002ab5f  xor     rax, [rbp+arg_0]
0x18002ab63  xor     rax, rcx
0x18002ab66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002ab6a  mov     [rbp+arg_0], rax
0x18002ab6e  call    cs:__imp_QueryPerformanceCounter
0x18002ab74  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002ab77  mov     rcx, 0FFFFFFFFFFFFh
0x18002ab81  shl     rax, 20h
0x18002ab85  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002ab89  xor     rax, [rbp+arg_0]
0x18002ab8d  and     rax, rcx
0x18002ab90  mov     rcx, rax
0x18002ab93  cmp     rax, rbx
0x18002ab96  jnz     short loc_18002ABA5
0x18002ab98  mov     rax, 2B992DDFA233h
0x18002aba2  mov     rcx, rax
0x18002aba5  mov     cs:__security_cookie, rcx
0x18002abac  mov     rbx, [rsp+20h+arg_18]
0x18002abb1  not     rax
0x18002abb4  mov     cs:__security_cookie_complement, rax
0x18002abbb  add     rsp, 20h
0x18002abbf  pop     rbp
0x18002abc0  retn
```
