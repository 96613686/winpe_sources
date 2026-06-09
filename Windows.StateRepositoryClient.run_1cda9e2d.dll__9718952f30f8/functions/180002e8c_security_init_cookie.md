# __security_init_cookie

- ea: `0x180002e8c`
- end: `0x180002f41`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002930`

## callees

- `0x180002e8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ecf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ecf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002eeb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002eeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002ec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002ec1`

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
0x180002e8c  mov     [rsp-8+arg_10], rbx
0x180002e91  push    rbp
0x180002e92  mov     rbp, rsp
0x180002e95  sub     rsp, 30h
0x180002e99  mov     rax, cs:__security_cookie
0x180002ea0  mov     rbx, 2B992DDFA232h
0x180002eaa  cmp     rax, rbx
0x180002ead  jnz     short loc_180002F2C
0x180002eaf  xor     eax, eax
0x180002eb1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002eb5  mov     [rbp+var_10], rax
0x180002eb9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002ebd  mov     qword ptr [rbp+PerformanceCount], rax
0x180002ec1  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ec7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002ecb  mov     [rbp+var_10], rax
0x180002ecf  call    cs:__imp_GetCurrentThreadId
0x180002ed5  mov     eax, eax
0x180002ed7  xor     [rbp+var_10], rax
0x180002edb  call    cs:__imp_GetCurrentProcessId
0x180002ee1  mov     eax, eax
0x180002ee3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002ee7  xor     [rbp+var_10], rax
0x180002eeb  call    cs:__imp_QueryPerformanceCounter
0x180002ef1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002ef4  lea     rcx, [rbp+var_10]
0x180002ef8  shl     rax, 20h
0x180002efc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002f00  xor     rax, [rbp+var_10]
0x180002f04  xor     rax, rcx
0x180002f07  mov     rcx, 0FFFFFFFFFFFFh
0x180002f11  and     rax, rcx
0x180002f14  mov     rcx, 2B992DDFA233h
0x180002f1e  cmp     rax, rbx
0x180002f21  cmovz   rax, rcx
0x180002f25  mov     cs:__security_cookie, rax
0x180002f2c  mov     rbx, [rsp+30h+arg_10]
0x180002f31  not     rax
0x180002f34  mov     cs:__security_cookie_complement, rax
0x180002f3b  add     rsp, 30h
0x180002f3f  pop     rbp
0x180002f40  retn
```
