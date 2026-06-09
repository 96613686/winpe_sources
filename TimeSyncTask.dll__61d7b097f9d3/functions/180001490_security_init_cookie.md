# __security_init_cookie

- ea: `0x180001490`
- end: `0x180001545`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001410`

## callees

- `0x180001490`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800014d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800014d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800014df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800014df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800014ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800014ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800014c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800014c5`

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
0x180001490  mov     [rsp-8+arg_10], rbx
0x180001495  push    rbp
0x180001496  mov     rbp, rsp
0x180001499  sub     rsp, 30h
0x18000149d  mov     rax, cs:__security_cookie
0x1800014a4  mov     rbx, 2B992DDFA232h
0x1800014ae  cmp     rax, rbx
0x1800014b1  jnz     short loc_180001530
0x1800014b3  xor     eax, eax
0x1800014b5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800014b9  mov     [rbp+var_10], rax
0x1800014bd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800014c1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800014c5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800014cb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800014cf  mov     [rbp+var_10], rax
0x1800014d3  call    cs:__imp_GetCurrentThreadId
0x1800014d9  mov     eax, eax
0x1800014db  xor     [rbp+var_10], rax
0x1800014df  call    cs:__imp_GetCurrentProcessId
0x1800014e5  mov     eax, eax
0x1800014e7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800014eb  xor     [rbp+var_10], rax
0x1800014ef  call    cs:__imp_QueryPerformanceCounter
0x1800014f5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800014f8  lea     rcx, [rbp+var_10]
0x1800014fc  shl     rax, 20h
0x180001500  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001504  xor     rax, [rbp+var_10]
0x180001508  xor     rax, rcx
0x18000150b  mov     rcx, 0FFFFFFFFFFFFh
0x180001515  and     rax, rcx
0x180001518  mov     rcx, 2B992DDFA233h
0x180001522  cmp     rax, rbx
0x180001525  cmovz   rax, rcx
0x180001529  mov     cs:__security_cookie, rax
0x180001530  mov     rbx, [rsp+30h+arg_10]
0x180001535  not     rax
0x180001538  mov     cs:__security_cookie_complement, rax
0x18000153f  add     rsp, 30h
0x180001543  pop     rbp
0x180001544  retn
```
