# __security_init_cookie

- ea: `0x1800039dc`
- end: `0x180003a91`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003930`

## callees

- `0x1800039dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003a1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003a2b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003a3b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003a3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003a11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003a11`

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
0x1800039dc  mov     [rsp-8+arg_10], rbx
0x1800039e1  push    rbp
0x1800039e2  mov     rbp, rsp
0x1800039e5  sub     rsp, 30h
0x1800039e9  mov     rax, cs:__security_cookie
0x1800039f0  mov     rbx, 2B992DDFA232h
0x1800039fa  cmp     rax, rbx
0x1800039fd  jnz     short loc_180003A7C
0x1800039ff  xor     eax, eax
0x180003a01  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003a05  mov     [rbp+var_10], rax
0x180003a09  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003a0d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003a11  call    cs:__imp_GetSystemTimeAsFileTime
0x180003a17  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003a1b  mov     [rbp+var_10], rax
0x180003a1f  call    cs:__imp_GetCurrentThreadId
0x180003a25  mov     eax, eax
0x180003a27  xor     [rbp+var_10], rax
0x180003a2b  call    cs:__imp_GetCurrentProcessId
0x180003a31  mov     eax, eax
0x180003a33  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003a37  xor     [rbp+var_10], rax
0x180003a3b  call    cs:__imp_QueryPerformanceCounter
0x180003a41  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003a44  lea     rcx, [rbp+var_10]
0x180003a48  shl     rax, 20h
0x180003a4c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003a50  xor     rax, [rbp+var_10]
0x180003a54  xor     rax, rcx
0x180003a57  mov     rcx, 0FFFFFFFFFFFFh
0x180003a61  and     rax, rcx
0x180003a64  mov     rcx, 2B992DDFA233h
0x180003a6e  cmp     rax, rbx
0x180003a71  cmovz   rax, rcx
0x180003a75  mov     cs:__security_cookie, rax
0x180003a7c  mov     rbx, [rsp+30h+arg_10]
0x180003a81  not     rax
0x180003a84  mov     cs:__security_cookie_complement, rax
0x180003a8b  add     rsp, 30h
0x180003a8f  pop     rbp
0x180003a90  retn
```
