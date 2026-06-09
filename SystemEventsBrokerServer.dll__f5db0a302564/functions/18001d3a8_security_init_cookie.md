# __security_init_cookie

- ea: `0x18001d3a8`
- end: `0x18001d45d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001cf00`

## callees

- `0x18001d3a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d3f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001d3f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d3dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001d3dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d407`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001d407`

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
0x18001d3a8  mov     [rsp-8+arg_10], rbx
0x18001d3ad  push    rbp
0x18001d3ae  mov     rbp, rsp
0x18001d3b1  sub     rsp, 30h
0x18001d3b5  mov     rax, cs:__security_cookie
0x18001d3bc  mov     rbx, 2B992DDFA232h
0x18001d3c6  cmp     rax, rbx
0x18001d3c9  jnz     short loc_18001D448
0x18001d3cb  xor     eax, eax
0x18001d3cd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001d3d1  mov     [rbp+var_10], rax
0x18001d3d5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001d3d9  mov     qword ptr [rbp+PerformanceCount], rax
0x18001d3dd  call    cs:__imp_GetSystemTimeAsFileTime
0x18001d3e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001d3e7  mov     [rbp+var_10], rax
0x18001d3eb  call    cs:__imp_GetCurrentThreadId
0x18001d3f1  mov     eax, eax
0x18001d3f3  xor     [rbp+var_10], rax
0x18001d3f7  call    cs:__imp_GetCurrentProcessId
0x18001d3fd  mov     eax, eax
0x18001d3ff  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001d403  xor     [rbp+var_10], rax
0x18001d407  call    cs:__imp_QueryPerformanceCounter
0x18001d40d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001d410  lea     rcx, [rbp+var_10]
0x18001d414  shl     rax, 20h
0x18001d418  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001d41c  xor     rax, [rbp+var_10]
0x18001d420  xor     rax, rcx
0x18001d423  mov     rcx, 0FFFFFFFFFFFFh
0x18001d42d  and     rax, rcx
0x18001d430  mov     rcx, 2B992DDFA233h
0x18001d43a  cmp     rax, rbx
0x18001d43d  cmovz   rax, rcx
0x18001d441  mov     cs:__security_cookie, rax
0x18001d448  mov     rbx, [rsp+30h+arg_10]
0x18001d44d  not     rax
0x18001d450  mov     cs:__security_cookie_complement, rax
0x18001d457  add     rsp, 30h
0x18001d45b  pop     rbp
0x18001d45c  retn
```
