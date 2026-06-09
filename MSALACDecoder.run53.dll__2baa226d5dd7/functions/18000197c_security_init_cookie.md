# __security_init_cookie

- ea: `0x18000197c`
- end: `0x180001a31`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001500`

## callees

- `0x18000197c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800019db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019b1`

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
0x18000197c  mov     [rsp-8+arg_10], rbx
0x180001981  push    rbp
0x180001982  mov     rbp, rsp
0x180001985  sub     rsp, 30h
0x180001989  mov     rax, cs:__security_cookie
0x180001990  mov     rbx, 2B992DDFA232h
0x18000199a  cmp     rax, rbx
0x18000199d  jnz     short loc_180001A1C
0x18000199f  xor     eax, eax
0x1800019a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019a5  mov     [rbp+var_10], rax
0x1800019a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019ad  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019b1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019bb  mov     [rbp+var_10], rax
0x1800019bf  call    cs:__imp_GetCurrentThreadId
0x1800019c5  mov     eax, eax
0x1800019c7  xor     [rbp+var_10], rax
0x1800019cb  call    cs:__imp_GetCurrentProcessId
0x1800019d1  mov     eax, eax
0x1800019d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800019d7  xor     [rbp+var_10], rax
0x1800019db  call    cs:__imp_QueryPerformanceCounter
0x1800019e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800019e4  lea     rcx, [rbp+var_10]
0x1800019e8  shl     rax, 20h
0x1800019ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800019f0  xor     rax, [rbp+var_10]
0x1800019f4  xor     rax, rcx
0x1800019f7  mov     rcx, 0FFFFFFFFFFFFh
0x180001a01  and     rax, rcx
0x180001a04  mov     rcx, 2B992DDFA233h
0x180001a0e  cmp     rax, rbx
0x180001a11  cmovz   rax, rcx
0x180001a15  mov     cs:__security_cookie, rax
0x180001a1c  mov     rbx, [rsp+30h+arg_10]
0x180001a21  not     rax
0x180001a24  mov     cs:__security_cookie_complement, rax
0x180001a2b  add     rsp, 30h
0x180001a2f  pop     rbp
0x180001a30  retn
```
