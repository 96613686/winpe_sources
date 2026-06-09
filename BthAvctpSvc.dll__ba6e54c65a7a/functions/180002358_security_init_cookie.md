# __security_init_cookie

- ea: `0x180002358`
- end: `0x18000240d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001d80`

## callees

- `0x180002358`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000239b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000239b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800023b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800023b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000238d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000238d`

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
0x180002358  mov     [rsp-8+arg_10], rbx
0x18000235d  push    rbp
0x18000235e  mov     rbp, rsp
0x180002361  sub     rsp, 30h
0x180002365  mov     rax, cs:__security_cookie
0x18000236c  mov     rbx, 2B992DDFA232h
0x180002376  cmp     rax, rbx
0x180002379  jnz     short loc_1800023F8
0x18000237b  xor     eax, eax
0x18000237d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002381  mov     [rbp+var_10], rax
0x180002385  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002389  mov     qword ptr [rbp+PerformanceCount], rax
0x18000238d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002393  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002397  mov     [rbp+var_10], rax
0x18000239b  call    cs:__imp_GetCurrentThreadId
0x1800023a1  mov     eax, eax
0x1800023a3  xor     [rbp+var_10], rax
0x1800023a7  call    cs:__imp_GetCurrentProcessId
0x1800023ad  mov     eax, eax
0x1800023af  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800023b3  xor     [rbp+var_10], rax
0x1800023b7  call    cs:__imp_QueryPerformanceCounter
0x1800023bd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800023c0  lea     rcx, [rbp+var_10]
0x1800023c4  shl     rax, 20h
0x1800023c8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800023cc  xor     rax, [rbp+var_10]
0x1800023d0  xor     rax, rcx
0x1800023d3  mov     rcx, 0FFFFFFFFFFFFh
0x1800023dd  and     rax, rcx
0x1800023e0  mov     rcx, 2B992DDFA233h
0x1800023ea  cmp     rax, rbx
0x1800023ed  cmovz   rax, rcx
0x1800023f1  mov     cs:__security_cookie, rax
0x1800023f8  mov     rbx, [rsp+30h+arg_10]
0x1800023fd  not     rax
0x180002400  mov     cs:__security_cookie_complement, rax
0x180002407  add     rsp, 30h
0x18000240b  pop     rbp
0x18000240c  retn
```
