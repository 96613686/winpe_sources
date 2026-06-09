# __security_init_cookie

- ea: `0x180026e3c`
- end: `0x180026ef1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800268d0`

## callees

- `0x180026e3c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026e8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026e8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026e7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026e7f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026e9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026e9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026e71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026e71`

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
0x180026e3c  mov     [rsp-8+arg_10], rbx
0x180026e41  push    rbp
0x180026e42  mov     rbp, rsp
0x180026e45  sub     rsp, 30h
0x180026e49  mov     rax, cs:__security_cookie
0x180026e50  mov     rbx, 2B992DDFA232h
0x180026e5a  cmp     rax, rbx
0x180026e5d  jnz     short loc_180026EDC
0x180026e5f  xor     eax, eax
0x180026e61  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180026e65  mov     [rbp+var_10], rax
0x180026e69  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180026e6d  mov     qword ptr [rbp+PerformanceCount], rax
0x180026e71  call    cs:__imp_GetSystemTimeAsFileTime
0x180026e77  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180026e7b  mov     [rbp+var_10], rax
0x180026e7f  call    cs:__imp_GetCurrentThreadId
0x180026e85  mov     eax, eax
0x180026e87  xor     [rbp+var_10], rax
0x180026e8b  call    cs:__imp_GetCurrentProcessId
0x180026e91  mov     eax, eax
0x180026e93  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180026e97  xor     [rbp+var_10], rax
0x180026e9b  call    cs:__imp_QueryPerformanceCounter
0x180026ea1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180026ea4  lea     rcx, [rbp+var_10]
0x180026ea8  shl     rax, 20h
0x180026eac  xor     rax, qword ptr [rbp+PerformanceCount]
0x180026eb0  xor     rax, [rbp+var_10]
0x180026eb4  xor     rax, rcx
0x180026eb7  mov     rcx, 0FFFFFFFFFFFFh
0x180026ec1  and     rax, rcx
0x180026ec4  mov     rcx, 2B992DDFA233h
0x180026ece  cmp     rax, rbx
0x180026ed1  cmovz   rax, rcx
0x180026ed5  mov     cs:__security_cookie, rax
0x180026edc  mov     rbx, [rsp+30h+arg_10]
0x180026ee1  not     rax
0x180026ee4  mov     cs:__security_cookie_complement, rax
0x180026eeb  add     rsp, 30h
0x180026eef  pop     rbp
0x180026ef0  retn
```
