# __security_init_cookie

- ea: `0x180026660`
- end: `0x180026715`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800261b0`

## callees

- `0x180026660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800266af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800266af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800266a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800266a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800266bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800266bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026695`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026695`

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
0x180026660  mov     [rsp-8+arg_10], rbx
0x180026665  push    rbp
0x180026666  mov     rbp, rsp
0x180026669  sub     rsp, 30h
0x18002666d  mov     rax, cs:__security_cookie
0x180026674  mov     rbx, 2B992DDFA232h
0x18002667e  cmp     rax, rbx
0x180026681  jnz     short loc_180026700
0x180026683  xor     eax, eax
0x180026685  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180026689  mov     [rbp+var_10], rax
0x18002668d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180026691  mov     qword ptr [rbp+PerformanceCount], rax
0x180026695  call    cs:__imp_GetSystemTimeAsFileTime
0x18002669b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002669f  mov     [rbp+var_10], rax
0x1800266a3  call    cs:__imp_GetCurrentThreadId
0x1800266a9  mov     eax, eax
0x1800266ab  xor     [rbp+var_10], rax
0x1800266af  call    cs:__imp_GetCurrentProcessId
0x1800266b5  mov     eax, eax
0x1800266b7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800266bb  xor     [rbp+var_10], rax
0x1800266bf  call    cs:__imp_QueryPerformanceCounter
0x1800266c5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800266c8  lea     rcx, [rbp+var_10]
0x1800266cc  shl     rax, 20h
0x1800266d0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800266d4  xor     rax, [rbp+var_10]
0x1800266d8  xor     rax, rcx
0x1800266db  mov     rcx, 0FFFFFFFFFFFFh
0x1800266e5  and     rax, rcx
0x1800266e8  mov     rcx, 2B992DDFA233h
0x1800266f2  cmp     rax, rbx
0x1800266f5  cmovz   rax, rcx
0x1800266f9  mov     cs:__security_cookie, rax
0x180026700  mov     rbx, [rsp+30h+arg_10]
0x180026705  not     rax
0x180026708  mov     cs:__security_cookie_complement, rax
0x18002670f  add     rsp, 30h
0x180026713  pop     rbp
0x180026714  retn
```
