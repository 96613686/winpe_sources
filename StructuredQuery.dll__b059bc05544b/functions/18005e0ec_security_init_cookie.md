# __security_init_cookie

- ea: `0x18005e0ec`
- end: `0x18005e1a1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005daa0`

## callees

- `0x18005e0ec`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e12f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e12f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005e13b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005e13b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005e121`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005e121`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005e14b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005e14b`

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
0x18005e0ec  mov     [rsp-8+arg_10], rbx
0x18005e0f1  push    rbp
0x18005e0f2  mov     rbp, rsp
0x18005e0f5  sub     rsp, 30h
0x18005e0f9  mov     rax, cs:__security_cookie
0x18005e100  mov     rbx, 2B992DDFA232h
0x18005e10a  cmp     rax, rbx
0x18005e10d  jnz     short loc_18005E18C
0x18005e10f  xor     eax, eax
0x18005e111  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005e115  mov     [rbp+var_10], rax
0x18005e119  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005e11d  mov     qword ptr [rbp+PerformanceCount], rax
0x18005e121  call    cs:__imp_GetSystemTimeAsFileTime
0x18005e127  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005e12b  mov     [rbp+var_10], rax
0x18005e12f  call    cs:__imp_GetCurrentThreadId
0x18005e135  mov     eax, eax
0x18005e137  xor     [rbp+var_10], rax
0x18005e13b  call    cs:__imp_GetCurrentProcessId
0x18005e141  mov     eax, eax
0x18005e143  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005e147  xor     [rbp+var_10], rax
0x18005e14b  call    cs:__imp_QueryPerformanceCounter
0x18005e151  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005e154  lea     rcx, [rbp+var_10]
0x18005e158  shl     rax, 20h
0x18005e15c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18005e160  xor     rax, [rbp+var_10]
0x18005e164  xor     rax, rcx
0x18005e167  mov     rcx, 0FFFFFFFFFFFFh
0x18005e171  and     rax, rcx
0x18005e174  mov     rcx, 2B992DDFA233h
0x18005e17e  cmp     rax, rbx
0x18005e181  cmovz   rax, rcx
0x18005e185  mov     cs:__security_cookie, rax
0x18005e18c  mov     rbx, [rsp+30h+arg_10]
0x18005e191  not     rax
0x18005e194  mov     cs:__security_cookie_complement, rax
0x18005e19b  add     rsp, 30h
0x18005e19f  pop     rbp
0x18005e1a0  retn
```
