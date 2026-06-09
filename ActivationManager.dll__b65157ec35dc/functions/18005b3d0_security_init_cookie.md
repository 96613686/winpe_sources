# __security_init_cookie

- ea: `0x18005b3d0`
- end: `0x18005b485`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ae40`

## callees

- `0x18005b3d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005b41f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005b41f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005b42f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005b42f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b405`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005b405`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18005b3d0  mov     [rsp-8+arg_10], rbx
0x18005b3d5  push    rbp
0x18005b3d6  mov     rbp, rsp
0x18005b3d9  sub     rsp, 30h
0x18005b3dd  mov     rax, cs:__security_cookie
0x18005b3e4  mov     rbx, 2B992DDFA232h
0x18005b3ee  cmp     rax, rbx
0x18005b3f1  jnz     short loc_18005B470
0x18005b3f3  xor     eax, eax
0x18005b3f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005b3f9  mov     [rbp+var_10], rax
0x18005b3fd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005b401  mov     qword ptr [rbp+PerformanceCount], rax
0x18005b405  call    cs:__imp_GetSystemTimeAsFileTime
0x18005b40b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005b40f  mov     [rbp+var_10], rax
0x18005b413  call    cs:__imp_GetCurrentThreadId
0x18005b419  mov     eax, eax
0x18005b41b  xor     [rbp+var_10], rax
0x18005b41f  call    cs:__imp_GetCurrentProcessId
0x18005b425  mov     eax, eax
0x18005b427  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005b42b  xor     [rbp+var_10], rax
0x18005b42f  call    cs:__imp_QueryPerformanceCounter
0x18005b435  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005b438  lea     rcx, [rbp+var_10]
0x18005b43c  shl     rax, 20h
0x18005b440  xor     rax, qword ptr [rbp+PerformanceCount]
0x18005b444  xor     rax, [rbp+var_10]
0x18005b448  xor     rax, rcx
0x18005b44b  mov     rcx, 0FFFFFFFFFFFFh
0x18005b455  and     rax, rcx
0x18005b458  mov     rcx, 2B992DDFA233h
0x18005b462  cmp     rax, rbx
0x18005b465  cmovz   rax, rcx
0x18005b469  mov     cs:__security_cookie, rax
0x18005b470  mov     rbx, [rsp+30h+arg_10]
0x18005b475  not     rax
0x18005b478  mov     cs:__security_cookie_complement, rax
0x18005b47f  add     rsp, 30h
0x18005b483  pop     rbp
0x18005b484  retn
```
