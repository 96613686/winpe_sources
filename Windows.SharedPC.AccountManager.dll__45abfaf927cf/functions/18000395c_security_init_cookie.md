# __security_init_cookie

- ea: `0x18000395c`
- end: `0x180003a11`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800034e0`

## callees

- `0x18000395c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800039ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800039ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000399f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000399f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800039bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800039bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003991`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003991`

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
0x18000395c  mov     [rsp-8+arg_10], rbx
0x180003961  push    rbp
0x180003962  mov     rbp, rsp
0x180003965  sub     rsp, 30h
0x180003969  mov     rax, cs:__security_cookie
0x180003970  mov     rbx, 2B992DDFA232h
0x18000397a  cmp     rax, rbx
0x18000397d  jnz     short loc_1800039FC
0x18000397f  xor     eax, eax
0x180003981  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003985  mov     [rbp+var_10], rax
0x180003989  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000398d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003991  call    cs:__imp_GetSystemTimeAsFileTime
0x180003997  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000399b  mov     [rbp+var_10], rax
0x18000399f  call    cs:__imp_GetCurrentThreadId
0x1800039a5  mov     eax, eax
0x1800039a7  xor     [rbp+var_10], rax
0x1800039ab  call    cs:__imp_GetCurrentProcessId
0x1800039b1  mov     eax, eax
0x1800039b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800039b7  xor     [rbp+var_10], rax
0x1800039bb  call    cs:__imp_QueryPerformanceCounter
0x1800039c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800039c4  lea     rcx, [rbp+var_10]
0x1800039c8  shl     rax, 20h
0x1800039cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800039d0  xor     rax, [rbp+var_10]
0x1800039d4  xor     rax, rcx
0x1800039d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800039e1  and     rax, rcx
0x1800039e4  mov     rcx, 2B992DDFA233h
0x1800039ee  cmp     rax, rbx
0x1800039f1  cmovz   rax, rcx
0x1800039f5  mov     cs:__security_cookie, rax
0x1800039fc  mov     rbx, [rsp+30h+arg_10]
0x180003a01  not     rax
0x180003a04  mov     cs:__security_cookie_complement, rax
0x180003a0b  add     rsp, 30h
0x180003a0f  pop     rbp
0x180003a10  retn
```
