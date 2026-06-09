# __security_init_cookie

- ea: `0x180007db4`
- end: `0x180007e91`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800076c0`

## callees

- `0x180007db4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007dfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007dfb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007e3e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007e3e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007ded`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007ded`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007e13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007e23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007e13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180007e23`

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
0x180007db4  mov     [rsp-8+arg_18], rbx
0x180007db9  push    rbp
0x180007dba  mov     rbp, rsp
0x180007dbd  sub     rsp, 20h
0x180007dc1  xor     eax, eax
0x180007dc3  mov     rbx, 2B992DDFA232h
0x180007dcd  mov     [rbp+arg_0], rax
0x180007dd1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180007dd5  mov     qword ptr [rbp+PerformanceCount], rax
0x180007dd9  mov     rax, cs:__security_cookie
0x180007de0  cmp     rax, rbx
0x180007de3  jnz     loc_180007E7C
0x180007de9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007ded  call    cs:__imp_GetSystemTimeAsFileTime
0x180007df3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180007df7  mov     [rbp+arg_0], rax
0x180007dfb  call    cs:__imp_GetCurrentProcessId
0x180007e01  mov     eax, eax
0x180007e03  xor     [rbp+arg_0], rax
0x180007e07  call    cs:__imp_GetCurrentThreadId
0x180007e0d  mov     eax, eax
0x180007e0f  xor     [rbp+arg_0], rax
0x180007e13  call    cs:__imp_GetTickCount
0x180007e19  mov     eax, eax
0x180007e1b  shl     rax, 18h
0x180007e1f  xor     [rbp+arg_0], rax
0x180007e23  call    cs:__imp_GetTickCount
0x180007e29  mov     eax, eax
0x180007e2b  lea     rcx, [rbp+arg_0]
0x180007e2f  xor     rax, [rbp+arg_0]
0x180007e33  xor     rax, rcx
0x180007e36  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180007e3a  mov     [rbp+arg_0], rax
0x180007e3e  call    cs:__imp_QueryPerformanceCounter
0x180007e44  mov     eax, dword ptr [rbp+PerformanceCount]
0x180007e47  mov     rcx, 0FFFFFFFFFFFFh
0x180007e51  shl     rax, 20h
0x180007e55  xor     rax, qword ptr [rbp+PerformanceCount]
0x180007e59  xor     rax, [rbp+arg_0]
0x180007e5d  and     rax, rcx
0x180007e60  mov     rcx, rax
0x180007e63  cmp     rax, rbx
0x180007e66  jnz     short loc_180007E75
0x180007e68  mov     rax, 2B992DDFA233h
0x180007e72  mov     rcx, rax
0x180007e75  mov     cs:__security_cookie, rcx
0x180007e7c  mov     rbx, [rsp+20h+arg_18]
0x180007e81  not     rax
0x180007e84  mov     cs:__security_cookie_complement, rax
0x180007e8b  add     rsp, 20h
0x180007e8f  pop     rbp
0x180007e90  retn
```
