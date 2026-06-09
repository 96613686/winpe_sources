# __security_init_cookie

- ea: `0x180003548`
- end: `0x1800035fd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a80`

## callees

- `0x180003548`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000358b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000358b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003597`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000357d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000357d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800035a7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800035a7`

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
0x180003548  mov     [rsp-8+arg_10], rbx
0x18000354d  push    rbp
0x18000354e  mov     rbp, rsp
0x180003551  sub     rsp, 30h
0x180003555  mov     rax, cs:__security_cookie
0x18000355c  mov     rbx, 2B992DDFA232h
0x180003566  cmp     rax, rbx
0x180003569  jnz     short loc_1800035E8
0x18000356b  xor     eax, eax
0x18000356d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003571  mov     [rbp+var_10], rax
0x180003575  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003579  mov     qword ptr [rbp+PerformanceCount], rax
0x18000357d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003583  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003587  mov     [rbp+var_10], rax
0x18000358b  call    cs:__imp_GetCurrentThreadId
0x180003591  mov     eax, eax
0x180003593  xor     [rbp+var_10], rax
0x180003597  call    cs:__imp_GetCurrentProcessId
0x18000359d  mov     eax, eax
0x18000359f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800035a3  xor     [rbp+var_10], rax
0x1800035a7  call    cs:__imp_QueryPerformanceCounter
0x1800035ad  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800035b0  lea     rcx, [rbp+var_10]
0x1800035b4  shl     rax, 20h
0x1800035b8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800035bc  xor     rax, [rbp+var_10]
0x1800035c0  xor     rax, rcx
0x1800035c3  mov     rcx, 0FFFFFFFFFFFFh
0x1800035cd  and     rax, rcx
0x1800035d0  mov     rcx, 2B992DDFA233h
0x1800035da  cmp     rax, rbx
0x1800035dd  cmovz   rax, rcx
0x1800035e1  mov     cs:__security_cookie, rax
0x1800035e8  mov     rbx, [rsp+30h+arg_10]
0x1800035ed  not     rax
0x1800035f0  mov     cs:__security_cookie_complement, rax
0x1800035f7  add     rsp, 30h
0x1800035fb  pop     rbp
0x1800035fc  retn
```
