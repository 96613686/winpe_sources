# __security_init_cookie

- ea: `0x18002aaf0`
- end: `0x18002aba5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002aa70`

## callees

- `0x18002aaf0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ab4f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ab4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ab33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002ab3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002ab3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ab25`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ab25`

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
0x18002aaf0  mov     [rsp-8+arg_10], rbx
0x18002aaf5  push    rbp
0x18002aaf6  mov     rbp, rsp
0x18002aaf9  sub     rsp, 30h
0x18002aafd  mov     rax, cs:__security_cookie
0x18002ab04  mov     rbx, 2B992DDFA232h
0x18002ab0e  cmp     rax, rbx
0x18002ab11  jnz     short loc_18002AB90
0x18002ab13  xor     eax, eax
0x18002ab15  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002ab19  mov     [rbp+var_10], rax
0x18002ab1d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002ab21  mov     qword ptr [rbp+PerformanceCount], rax
0x18002ab25  call    cs:__imp_GetSystemTimeAsFileTime
0x18002ab2b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002ab2f  mov     [rbp+var_10], rax
0x18002ab33  call    cs:__imp_GetCurrentThreadId
0x18002ab39  mov     eax, eax
0x18002ab3b  xor     [rbp+var_10], rax
0x18002ab3f  call    cs:__imp_GetCurrentProcessId
0x18002ab45  mov     eax, eax
0x18002ab47  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002ab4b  xor     [rbp+var_10], rax
0x18002ab4f  call    cs:__imp_QueryPerformanceCounter
0x18002ab55  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002ab58  lea     rcx, [rbp+var_10]
0x18002ab5c  shl     rax, 20h
0x18002ab60  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002ab64  xor     rax, [rbp+var_10]
0x18002ab68  xor     rax, rcx
0x18002ab6b  mov     rcx, 0FFFFFFFFFFFFh
0x18002ab75  and     rax, rcx
0x18002ab78  mov     rcx, 2B992DDFA233h
0x18002ab82  cmp     rax, rbx
0x18002ab85  cmovz   rax, rcx
0x18002ab89  mov     cs:__security_cookie, rax
0x18002ab90  mov     rbx, [rsp+30h+arg_10]
0x18002ab95  not     rax
0x18002ab98  mov     cs:__security_cookie_complement, rax
0x18002ab9f  add     rsp, 30h
0x18002aba3  pop     rbp
0x18002aba4  retn
```
