# __security_init_cookie

- ea: `0x180008e8c`
- end: `0x180008f41`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008a30`

## callees

- `0x180008e8c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ecf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ecf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008edb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008eeb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008eeb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008ec1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008ec1`

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
0x180008e8c  mov     [rsp-8+arg_10], rbx
0x180008e91  push    rbp
0x180008e92  mov     rbp, rsp
0x180008e95  sub     rsp, 30h
0x180008e99  mov     rax, cs:__security_cookie
0x180008ea0  mov     rbx, 2B992DDFA232h
0x180008eaa  cmp     rax, rbx
0x180008ead  jnz     short loc_180008F2C
0x180008eaf  xor     eax, eax
0x180008eb1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008eb5  mov     [rbp+var_10], rax
0x180008eb9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008ebd  mov     qword ptr [rbp+PerformanceCount], rax
0x180008ec1  call    cs:__imp_GetSystemTimeAsFileTime
0x180008ec7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008ecb  mov     [rbp+var_10], rax
0x180008ecf  call    cs:__imp_GetCurrentThreadId
0x180008ed5  mov     eax, eax
0x180008ed7  xor     [rbp+var_10], rax
0x180008edb  call    cs:__imp_GetCurrentProcessId
0x180008ee1  mov     eax, eax
0x180008ee3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180008ee7  xor     [rbp+var_10], rax
0x180008eeb  call    cs:__imp_QueryPerformanceCounter
0x180008ef1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008ef4  lea     rcx, [rbp+var_10]
0x180008ef8  shl     rax, 20h
0x180008efc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180008f00  xor     rax, [rbp+var_10]
0x180008f04  xor     rax, rcx
0x180008f07  mov     rcx, 0FFFFFFFFFFFFh
0x180008f11  and     rax, rcx
0x180008f14  mov     rcx, 2B992DDFA233h
0x180008f1e  cmp     rax, rbx
0x180008f21  cmovz   rax, rcx
0x180008f25  mov     cs:__security_cookie, rax
0x180008f2c  mov     rbx, [rsp+30h+arg_10]
0x180008f31  not     rax
0x180008f34  mov     cs:__security_cookie_complement, rax
0x180008f3b  add     rsp, 30h
0x180008f3f  pop     rbp
0x180008f40  retn
```
