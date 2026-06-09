# __security_init_cookie

- ea: `0x1800729cc`
- end: `0x180072a81`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180071d70`

## callees

- `0x1800729cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180072a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180072a1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180072a0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180072a0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180072a2b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180072a2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072a01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180072a01`

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
0x1800729cc  mov     [rsp-8+arg_10], rbx
0x1800729d1  push    rbp
0x1800729d2  mov     rbp, rsp
0x1800729d5  sub     rsp, 30h
0x1800729d9  mov     rax, cs:__security_cookie
0x1800729e0  mov     rbx, 2B992DDFA232h
0x1800729ea  cmp     rax, rbx
0x1800729ed  jnz     short loc_180072A6C
0x1800729ef  xor     eax, eax
0x1800729f1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800729f5  mov     [rbp+var_10], rax
0x1800729f9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800729fd  mov     qword ptr [rbp+PerformanceCount], rax
0x180072a01  call    cs:__imp_GetSystemTimeAsFileTime
0x180072a07  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180072a0b  mov     [rbp+var_10], rax
0x180072a0f  call    cs:__imp_GetCurrentThreadId
0x180072a15  mov     eax, eax
0x180072a17  xor     [rbp+var_10], rax
0x180072a1b  call    cs:__imp_GetCurrentProcessId
0x180072a21  mov     eax, eax
0x180072a23  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180072a27  xor     [rbp+var_10], rax
0x180072a2b  call    cs:__imp_QueryPerformanceCounter
0x180072a31  mov     eax, dword ptr [rbp+PerformanceCount]
0x180072a34  lea     rcx, [rbp+var_10]
0x180072a38  shl     rax, 20h
0x180072a3c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180072a40  xor     rax, [rbp+var_10]
0x180072a44  xor     rax, rcx
0x180072a47  mov     rcx, 0FFFFFFFFFFFFh
0x180072a51  and     rax, rcx
0x180072a54  mov     rcx, 2B992DDFA233h
0x180072a5e  cmp     rax, rbx
0x180072a61  cmovz   rax, rcx
0x180072a65  mov     cs:__security_cookie, rax
0x180072a6c  mov     rbx, [rsp+30h+arg_10]
0x180072a71  not     rax
0x180072a74  mov     cs:__security_cookie_complement, rax
0x180072a7b  add     rsp, 30h
0x180072a7f  pop     rbp
0x180072a80  retn
```
