# __security_init_cookie

- ea: `0x180009c04`
- end: `0x180009cb9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009780`

## callees

- `0x180009c04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009c53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009c53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009c39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009c39`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009c63`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009c63`

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
0x180009c04  mov     [rsp-8+arg_10], rbx
0x180009c09  push    rbp
0x180009c0a  mov     rbp, rsp
0x180009c0d  sub     rsp, 30h
0x180009c11  mov     rax, cs:__security_cookie
0x180009c18  mov     rbx, 2B992DDFA232h
0x180009c22  cmp     rax, rbx
0x180009c25  jnz     short loc_180009CA4
0x180009c27  xor     eax, eax
0x180009c29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180009c2d  mov     [rbp+var_10], rax
0x180009c31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180009c35  mov     qword ptr [rbp+PerformanceCount], rax
0x180009c39  call    cs:__imp_GetSystemTimeAsFileTime
0x180009c3f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180009c43  mov     [rbp+var_10], rax
0x180009c47  call    cs:__imp_GetCurrentThreadId
0x180009c4d  mov     eax, eax
0x180009c4f  xor     [rbp+var_10], rax
0x180009c53  call    cs:__imp_GetCurrentProcessId
0x180009c59  mov     eax, eax
0x180009c5b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180009c5f  xor     [rbp+var_10], rax
0x180009c63  call    cs:__imp_QueryPerformanceCounter
0x180009c69  mov     eax, dword ptr [rbp+PerformanceCount]
0x180009c6c  lea     rcx, [rbp+var_10]
0x180009c70  shl     rax, 20h
0x180009c74  xor     rax, qword ptr [rbp+PerformanceCount]
0x180009c78  xor     rax, [rbp+var_10]
0x180009c7c  xor     rax, rcx
0x180009c7f  mov     rcx, 0FFFFFFFFFFFFh
0x180009c89  and     rax, rcx
0x180009c8c  mov     rcx, 2B992DDFA233h
0x180009c96  cmp     rax, rbx
0x180009c99  cmovz   rax, rcx
0x180009c9d  mov     cs:__security_cookie, rax
0x180009ca4  mov     rbx, [rsp+30h+arg_10]
0x180009ca9  not     rax
0x180009cac  mov     cs:__security_cookie_complement, rax
0x180009cb3  add     rsp, 30h
0x180009cb7  pop     rbp
0x180009cb8  retn
```
