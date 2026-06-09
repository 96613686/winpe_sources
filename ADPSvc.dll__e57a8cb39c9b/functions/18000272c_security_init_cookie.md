# __security_init_cookie

- ea: `0x18000272c`
- end: `0x1800027e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002200`

## callees

- `0x18000272c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000277b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000277b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000276f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000276f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000278b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000278b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002761`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002761`

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
0x18000272c  mov     [rsp-8+arg_10], rbx
0x180002731  push    rbp
0x180002732  mov     rbp, rsp
0x180002735  sub     rsp, 30h
0x180002739  mov     rax, cs:__security_cookie
0x180002740  mov     rbx, 2B992DDFA232h
0x18000274a  cmp     rax, rbx
0x18000274d  jnz     short loc_1800027CC
0x18000274f  xor     eax, eax
0x180002751  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002755  mov     [rbp+var_10], rax
0x180002759  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000275d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002761  call    cs:__imp_GetSystemTimeAsFileTime
0x180002767  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000276b  mov     [rbp+var_10], rax
0x18000276f  call    cs:__imp_GetCurrentThreadId
0x180002775  mov     eax, eax
0x180002777  xor     [rbp+var_10], rax
0x18000277b  call    cs:__imp_GetCurrentProcessId
0x180002781  mov     eax, eax
0x180002783  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002787  xor     [rbp+var_10], rax
0x18000278b  call    cs:__imp_QueryPerformanceCounter
0x180002791  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002794  lea     rcx, [rbp+var_10]
0x180002798  shl     rax, 20h
0x18000279c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800027a0  xor     rax, [rbp+var_10]
0x1800027a4  xor     rax, rcx
0x1800027a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800027b1  and     rax, rcx
0x1800027b4  mov     rcx, 2B992DDFA233h
0x1800027be  cmp     rax, rbx
0x1800027c1  cmovz   rax, rcx
0x1800027c5  mov     cs:__security_cookie, rax
0x1800027cc  mov     rbx, [rsp+30h+arg_10]
0x1800027d1  not     rax
0x1800027d4  mov     cs:__security_cookie_complement, rax
0x1800027db  add     rsp, 30h
0x1800027df  pop     rbp
0x1800027e0  retn
```
