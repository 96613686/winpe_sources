# __security_init_cookie

- ea: `0x18000d958`
- end: `0x18000da0d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cfe0`

## callees

- `0x18000d958`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d9a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d9a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d98d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d98d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d9b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d9b7`

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
0x18000d958  mov     [rsp-8+arg_10], rbx
0x18000d95d  push    rbp
0x18000d95e  mov     rbp, rsp
0x18000d961  sub     rsp, 30h
0x18000d965  mov     rax, cs:__security_cookie
0x18000d96c  mov     rbx, 2B992DDFA232h
0x18000d976  cmp     rax, rbx
0x18000d979  jnz     short loc_18000D9F8
0x18000d97b  xor     eax, eax
0x18000d97d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d981  mov     [rbp+var_10], rax
0x18000d985  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000d989  mov     qword ptr [rbp+PerformanceCount], rax
0x18000d98d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d993  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d997  mov     [rbp+var_10], rax
0x18000d99b  call    cs:__imp_GetCurrentThreadId
0x18000d9a1  mov     eax, eax
0x18000d9a3  xor     [rbp+var_10], rax
0x18000d9a7  call    cs:__imp_GetCurrentProcessId
0x18000d9ad  mov     eax, eax
0x18000d9af  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000d9b3  xor     [rbp+var_10], rax
0x18000d9b7  call    cs:__imp_QueryPerformanceCounter
0x18000d9bd  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000d9c0  lea     rcx, [rbp+var_10]
0x18000d9c4  shl     rax, 20h
0x18000d9c8  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000d9cc  xor     rax, [rbp+var_10]
0x18000d9d0  xor     rax, rcx
0x18000d9d3  mov     rcx, 0FFFFFFFFFFFFh
0x18000d9dd  and     rax, rcx
0x18000d9e0  mov     rcx, 2B992DDFA233h
0x18000d9ea  cmp     rax, rbx
0x18000d9ed  cmovz   rax, rcx
0x18000d9f1  mov     cs:__security_cookie, rax
0x18000d9f8  mov     rbx, [rsp+30h+arg_10]
0x18000d9fd  not     rax
0x18000da00  mov     cs:__security_cookie_complement, rax
0x18000da07  add     rsp, 30h
0x18000da0b  pop     rbp
0x18000da0c  retn
```
