# __security_init_cookie

- ea: `0x180043e28`
- end: `0x180043edd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180043630`

## callees

- `0x180043e28`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043e77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180043e77`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043e5d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043e5d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180043e87`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180043e87`

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
0x180043e28  mov     [rsp-8+arg_10], rbx
0x180043e2d  push    rbp
0x180043e2e  mov     rbp, rsp
0x180043e31  sub     rsp, 30h
0x180043e35  mov     rax, cs:__security_cookie
0x180043e3c  mov     rbx, 2B992DDFA232h
0x180043e46  cmp     rax, rbx
0x180043e49  jnz     short loc_180043EC8
0x180043e4b  xor     eax, eax
0x180043e4d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180043e51  mov     [rbp+var_10], rax
0x180043e55  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180043e59  mov     qword ptr [rbp+PerformanceCount], rax
0x180043e5d  call    cs:__imp_GetSystemTimeAsFileTime
0x180043e63  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180043e67  mov     [rbp+var_10], rax
0x180043e6b  call    cs:__imp_GetCurrentThreadId
0x180043e71  mov     eax, eax
0x180043e73  xor     [rbp+var_10], rax
0x180043e77  call    cs:__imp_GetCurrentProcessId
0x180043e7d  mov     eax, eax
0x180043e7f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180043e83  xor     [rbp+var_10], rax
0x180043e87  call    cs:__imp_QueryPerformanceCounter
0x180043e8d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180043e90  lea     rcx, [rbp+var_10]
0x180043e94  shl     rax, 20h
0x180043e98  xor     rax, qword ptr [rbp+PerformanceCount]
0x180043e9c  xor     rax, [rbp+var_10]
0x180043ea0  xor     rax, rcx
0x180043ea3  mov     rcx, 0FFFFFFFFFFFFh
0x180043ead  and     rax, rcx
0x180043eb0  mov     rcx, 2B992DDFA233h
0x180043eba  cmp     rax, rbx
0x180043ebd  cmovz   rax, rcx
0x180043ec1  mov     cs:__security_cookie, rax
0x180043ec8  mov     rbx, [rsp+30h+arg_10]
0x180043ecd  not     rax
0x180043ed0  mov     cs:__security_cookie_complement, rax
0x180043ed7  add     rsp, 30h
0x180043edb  pop     rbp
0x180043edc  retn
```
