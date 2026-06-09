# __security_init_cookie

- ea: `0x18000d288`
- end: `0x18000d33d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ca40`

## callees

- `0x18000d288`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d2cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d2cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d2d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d2d7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d2e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d2e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d2bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d2bd`

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
0x18000d288  mov     [rsp-8+arg_10], rbx
0x18000d28d  push    rbp
0x18000d28e  mov     rbp, rsp
0x18000d291  sub     rsp, 30h
0x18000d295  mov     rax, cs:__security_cookie
0x18000d29c  mov     rbx, 2B992DDFA232h
0x18000d2a6  cmp     rax, rbx
0x18000d2a9  jnz     short loc_18000D328
0x18000d2ab  xor     eax, eax
0x18000d2ad  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d2b1  mov     [rbp+var_10], rax
0x18000d2b5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000d2b9  mov     qword ptr [rbp+PerformanceCount], rax
0x18000d2bd  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d2c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d2c7  mov     [rbp+var_10], rax
0x18000d2cb  call    cs:__imp_GetCurrentThreadId
0x18000d2d1  mov     eax, eax
0x18000d2d3  xor     [rbp+var_10], rax
0x18000d2d7  call    cs:__imp_GetCurrentProcessId
0x18000d2dd  mov     eax, eax
0x18000d2df  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000d2e3  xor     [rbp+var_10], rax
0x18000d2e7  call    cs:__imp_QueryPerformanceCounter
0x18000d2ed  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000d2f0  lea     rcx, [rbp+var_10]
0x18000d2f4  shl     rax, 20h
0x18000d2f8  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000d2fc  xor     rax, [rbp+var_10]
0x18000d300  xor     rax, rcx
0x18000d303  mov     rcx, 0FFFFFFFFFFFFh
0x18000d30d  and     rax, rcx
0x18000d310  mov     rcx, 2B992DDFA233h
0x18000d31a  cmp     rax, rbx
0x18000d31d  cmovz   rax, rcx
0x18000d321  mov     cs:__security_cookie, rax
0x18000d328  mov     rbx, [rsp+30h+arg_10]
0x18000d32d  not     rax
0x18000d330  mov     cs:__security_cookie_complement, rax
0x18000d337  add     rsp, 30h
0x18000d33b  pop     rbp
0x18000d33c  retn
```
