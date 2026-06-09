# __security_init_cookie

- ea: `0x180058f7c`
- end: `0x180059031`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180058ae0`

## callees

- `0x180058f7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180058fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180058fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058fbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058fbf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180058fdb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180058fdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180058fb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180058fb1`

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
0x180058f7c  mov     [rsp-8+arg_10], rbx
0x180058f81  push    rbp
0x180058f82  mov     rbp, rsp
0x180058f85  sub     rsp, 30h
0x180058f89  mov     rax, cs:__security_cookie
0x180058f90  mov     rbx, 2B992DDFA232h
0x180058f9a  cmp     rax, rbx
0x180058f9d  jnz     short loc_18005901C
0x180058f9f  xor     eax, eax
0x180058fa1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180058fa5  mov     [rbp+var_10], rax
0x180058fa9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180058fad  mov     qword ptr [rbp+PerformanceCount], rax
0x180058fb1  call    cs:__imp_GetSystemTimeAsFileTime
0x180058fb7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180058fbb  mov     [rbp+var_10], rax
0x180058fbf  call    cs:__imp_GetCurrentThreadId
0x180058fc5  mov     eax, eax
0x180058fc7  xor     [rbp+var_10], rax
0x180058fcb  call    cs:__imp_GetCurrentProcessId
0x180058fd1  mov     eax, eax
0x180058fd3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180058fd7  xor     [rbp+var_10], rax
0x180058fdb  call    cs:__imp_QueryPerformanceCounter
0x180058fe1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180058fe4  lea     rcx, [rbp+var_10]
0x180058fe8  shl     rax, 20h
0x180058fec  xor     rax, qword ptr [rbp+PerformanceCount]
0x180058ff0  xor     rax, [rbp+var_10]
0x180058ff4  xor     rax, rcx
0x180058ff7  mov     rcx, 0FFFFFFFFFFFFh
0x180059001  and     rax, rcx
0x180059004  mov     rcx, 2B992DDFA233h
0x18005900e  cmp     rax, rbx
0x180059011  cmovz   rax, rcx
0x180059015  mov     cs:__security_cookie, rax
0x18005901c  mov     rbx, [rsp+30h+arg_10]
0x180059021  not     rax
0x180059024  mov     cs:__security_cookie_complement, rax
0x18005902b  add     rsp, 30h
0x18005902f  pop     rbp
0x180059030  retn
```
