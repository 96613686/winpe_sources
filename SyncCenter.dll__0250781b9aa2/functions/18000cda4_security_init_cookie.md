# __security_init_cookie

- ea: `0x18000cda4`
- end: `0x18000ce81`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c8b0`

## callees

- `0x18000cda4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cdeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000cdeb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cdf7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ce03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ce13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ce03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ce13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000cddd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000cddd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ce2e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ce2e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18000cda4  mov     [rsp-8+arg_18], rbx
0x18000cda9  push    rbp
0x18000cdaa  mov     rbp, rsp
0x18000cdad  sub     rsp, 20h
0x18000cdb1  xor     eax, eax
0x18000cdb3  mov     rbx, 2B992DDFA232h
0x18000cdbd  mov     [rbp+arg_0], rax
0x18000cdc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000cdc5  mov     qword ptr [rbp+PerformanceCount], rax
0x18000cdc9  mov     rax, cs:__security_cookie
0x18000cdd0  cmp     rax, rbx
0x18000cdd3  jnz     loc_18000CE6C
0x18000cdd9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000cddd  call    cs:__imp_GetSystemTimeAsFileTime
0x18000cde3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000cde7  mov     [rbp+arg_0], rax
0x18000cdeb  call    cs:__imp_GetCurrentProcessId
0x18000cdf1  mov     eax, eax
0x18000cdf3  xor     [rbp+arg_0], rax
0x18000cdf7  call    cs:__imp_GetCurrentThreadId
0x18000cdfd  mov     eax, eax
0x18000cdff  xor     [rbp+arg_0], rax
0x18000ce03  call    cs:__imp_GetTickCount
0x18000ce09  mov     eax, eax
0x18000ce0b  shl     rax, 18h
0x18000ce0f  xor     [rbp+arg_0], rax
0x18000ce13  call    cs:__imp_GetTickCount
0x18000ce19  mov     eax, eax
0x18000ce1b  lea     rcx, [rbp+arg_0]
0x18000ce1f  xor     rax, [rbp+arg_0]
0x18000ce23  xor     rax, rcx
0x18000ce26  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000ce2a  mov     [rbp+arg_0], rax
0x18000ce2e  call    cs:__imp_QueryPerformanceCounter
0x18000ce34  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000ce37  mov     rcx, 0FFFFFFFFFFFFh
0x18000ce41  shl     rax, 20h
0x18000ce45  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000ce49  xor     rax, [rbp+arg_0]
0x18000ce4d  and     rax, rcx
0x18000ce50  mov     rcx, rax
0x18000ce53  cmp     rax, rbx
0x18000ce56  jnz     short loc_18000CE65
0x18000ce58  mov     rax, 2B992DDFA233h
0x18000ce62  mov     rcx, rax
0x18000ce65  mov     cs:__security_cookie, rcx
0x18000ce6c  mov     rbx, [rsp+20h+arg_18]
0x18000ce71  not     rax
0x18000ce74  mov     cs:__security_cookie_complement, rax
0x18000ce7b  add     rsp, 20h
0x18000ce7f  pop     rbp
0x18000ce80  retn
```
