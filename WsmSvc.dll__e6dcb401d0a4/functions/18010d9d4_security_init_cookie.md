# __security_init_cookie

- ea: `0x18010d9d4`
- end: `0x18010dab1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18010d100`

## callees

- `0x18010d9d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010da27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18010da27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18010da1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18010da1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010da5e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010da5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18010da0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18010da0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010da33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010da43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010da33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18010da43`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x18010d9d4  mov     [rsp-8+arg_18], rbx
0x18010d9d9  push    rbp
0x18010d9da  mov     rbp, rsp
0x18010d9dd  sub     rsp, 20h
0x18010d9e1  xor     eax, eax
0x18010d9e3  mov     rbx, 2B992DDFA232h
0x18010d9ed  mov     [rbp+arg_0], rax
0x18010d9f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18010d9f5  mov     qword ptr [rbp+PerformanceCount], rax
0x18010d9f9  mov     rax, cs:__security_cookie
0x18010da00  cmp     rax, rbx
0x18010da03  jnz     loc_18010DA9C
0x18010da09  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18010da0d  call    cs:__imp_GetSystemTimeAsFileTime
0x18010da13  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18010da17  mov     [rbp+arg_0], rax
0x18010da1b  call    cs:__imp_GetCurrentProcessId
0x18010da21  mov     eax, eax
0x18010da23  xor     [rbp+arg_0], rax
0x18010da27  call    cs:__imp_GetCurrentThreadId
0x18010da2d  mov     eax, eax
0x18010da2f  xor     [rbp+arg_0], rax
0x18010da33  call    cs:__imp_GetTickCount
0x18010da39  mov     eax, eax
0x18010da3b  shl     rax, 18h
0x18010da3f  xor     [rbp+arg_0], rax
0x18010da43  call    cs:__imp_GetTickCount
0x18010da49  mov     eax, eax
0x18010da4b  lea     rcx, [rbp+arg_0]
0x18010da4f  xor     rax, [rbp+arg_0]
0x18010da53  xor     rax, rcx
0x18010da56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18010da5a  mov     [rbp+arg_0], rax
0x18010da5e  call    cs:__imp_QueryPerformanceCounter
0x18010da64  mov     eax, dword ptr [rbp+PerformanceCount]
0x18010da67  mov     rcx, 0FFFFFFFFFFFFh
0x18010da71  shl     rax, 20h
0x18010da75  xor     rax, qword ptr [rbp+PerformanceCount]
0x18010da79  xor     rax, [rbp+arg_0]
0x18010da7d  and     rax, rcx
0x18010da80  mov     rcx, rax
0x18010da83  cmp     rax, rbx
0x18010da86  jnz     short loc_18010DA95
0x18010da88  mov     rax, 2B992DDFA233h
0x18010da92  mov     rcx, rax
0x18010da95  mov     cs:__security_cookie, rcx
0x18010da9c  mov     rbx, [rsp+20h+arg_18]
0x18010daa1  not     rax
0x18010daa4  mov     cs:__security_cookie_complement, rax
0x18010daab  add     rsp, 20h
0x18010daaf  pop     rbp
0x18010dab0  retn
```
