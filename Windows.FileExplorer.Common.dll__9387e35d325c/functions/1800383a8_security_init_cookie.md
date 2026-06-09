# __security_init_cookie

- ea: `0x1800383a8`
- end: `0x18003845d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180037730`

## callees

- `0x1800383a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800383f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800383f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800383dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800383dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038407`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180038407`

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
0x1800383a8  mov     [rsp-8+arg_10], rbx
0x1800383ad  push    rbp
0x1800383ae  mov     rbp, rsp
0x1800383b1  sub     rsp, 30h
0x1800383b5  mov     rax, cs:__security_cookie
0x1800383bc  mov     rbx, 2B992DDFA232h
0x1800383c6  cmp     rax, rbx
0x1800383c9  jnz     short loc_180038448
0x1800383cb  xor     eax, eax
0x1800383cd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800383d1  mov     [rbp+var_10], rax
0x1800383d5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800383d9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800383dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800383e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800383e7  mov     [rbp+var_10], rax
0x1800383eb  call    cs:__imp_GetCurrentThreadId
0x1800383f1  mov     eax, eax
0x1800383f3  xor     [rbp+var_10], rax
0x1800383f7  call    cs:__imp_GetCurrentProcessId
0x1800383fd  mov     eax, eax
0x1800383ff  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180038403  xor     [rbp+var_10], rax
0x180038407  call    cs:__imp_QueryPerformanceCounter
0x18003840d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180038410  lea     rcx, [rbp+var_10]
0x180038414  shl     rax, 20h
0x180038418  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003841c  xor     rax, [rbp+var_10]
0x180038420  xor     rax, rcx
0x180038423  mov     rcx, 0FFFFFFFFFFFFh
0x18003842d  and     rax, rcx
0x180038430  mov     rcx, 2B992DDFA233h
0x18003843a  cmp     rax, rbx
0x18003843d  cmovz   rax, rcx
0x180038441  mov     cs:__security_cookie, rax
0x180038448  mov     rbx, [rsp+30h+arg_10]
0x18003844d  not     rax
0x180038450  mov     cs:__security_cookie_complement, rax
0x180038457  add     rsp, 30h
0x18003845b  pop     rbp
0x18003845c  retn
```
