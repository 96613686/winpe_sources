# __security_init_cookie

- ea: `0x1800038a8`
- end: `0x18000395d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003560`

## callees

- `0x1800038a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800038f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800038f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800038eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800038eb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003907`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003907`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800038dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800038dd`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x1800038a8  mov     [rsp-8+arg_10], rbx
0x1800038ad  push    rbp
0x1800038ae  mov     rbp, rsp
0x1800038b1  sub     rsp, 30h
0x1800038b5  mov     rax, cs:__security_cookie
0x1800038bc  mov     rbx, 2B992DDFA232h
0x1800038c6  cmp     rax, rbx
0x1800038c9  jnz     short loc_180003948
0x1800038cb  xor     eax, eax
0x1800038cd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800038d1  mov     [rbp+var_10], rax
0x1800038d5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800038d9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800038dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800038e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800038e7  mov     [rbp+var_10], rax
0x1800038eb  call    cs:__imp_GetCurrentThreadId
0x1800038f1  mov     eax, eax
0x1800038f3  xor     [rbp+var_10], rax
0x1800038f7  call    cs:__imp_GetCurrentProcessId
0x1800038fd  mov     eax, eax
0x1800038ff  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003903  xor     [rbp+var_10], rax
0x180003907  call    cs:__imp_QueryPerformanceCounter
0x18000390d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003910  lea     rcx, [rbp+var_10]
0x180003914  shl     rax, 20h
0x180003918  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000391c  xor     rax, [rbp+var_10]
0x180003920  xor     rax, rcx
0x180003923  mov     rcx, 0FFFFFFFFFFFFh
0x18000392d  and     rax, rcx
0x180003930  mov     rcx, 2B992DDFA233h
0x18000393a  cmp     rax, rbx
0x18000393d  cmovz   rax, rcx
0x180003941  mov     cs:__security_cookie, rax
0x180003948  mov     rbx, [rsp+30h+arg_10]
0x18000394d  not     rax
0x180003950  mov     cs:__security_cookie_complement, rax
0x180003957  add     rsp, 30h
0x18000395b  pop     rbp
0x18000395c  retn
```
