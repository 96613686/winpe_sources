# __security_init_cookie

- ea: `0x1800054f8`
- end: `0x1800055ad`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004940`

## callees

- `0x1800054f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000553b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000553b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005547`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005547`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005557`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005557`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000552d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000552d`

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
0x1800054f8  mov     [rsp-8+arg_10], rbx
0x1800054fd  push    rbp
0x1800054fe  mov     rbp, rsp
0x180005501  sub     rsp, 30h
0x180005505  mov     rax, cs:__security_cookie
0x18000550c  mov     rbx, 2B992DDFA232h
0x180005516  cmp     rax, rbx
0x180005519  jnz     short loc_180005598
0x18000551b  xor     eax, eax
0x18000551d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005521  mov     [rbp+var_10], rax
0x180005525  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005529  mov     qword ptr [rbp+PerformanceCount], rax
0x18000552d  call    cs:__imp_GetSystemTimeAsFileTime
0x180005533  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005537  mov     [rbp+var_10], rax
0x18000553b  call    cs:__imp_GetCurrentThreadId
0x180005541  mov     eax, eax
0x180005543  xor     [rbp+var_10], rax
0x180005547  call    cs:__imp_GetCurrentProcessId
0x18000554d  mov     eax, eax
0x18000554f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005553  xor     [rbp+var_10], rax
0x180005557  call    cs:__imp_QueryPerformanceCounter
0x18000555d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005560  lea     rcx, [rbp+var_10]
0x180005564  shl     rax, 20h
0x180005568  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000556c  xor     rax, [rbp+var_10]
0x180005570  xor     rax, rcx
0x180005573  mov     rcx, 0FFFFFFFFFFFFh
0x18000557d  and     rax, rcx
0x180005580  mov     rcx, 2B992DDFA233h
0x18000558a  cmp     rax, rbx
0x18000558d  cmovz   rax, rcx
0x180005591  mov     cs:__security_cookie, rax
0x180005598  mov     rbx, [rsp+30h+arg_10]
0x18000559d  not     rax
0x1800055a0  mov     cs:__security_cookie_complement, rax
0x1800055a7  add     rsp, 30h
0x1800055ab  pop     rbp
0x1800055ac  retn
```
