# __security_init_cookie

- ea: `0x1800aaddc`
- end: `0x1800aae91`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800aa600`

## callees

- `0x1800aaddc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aae1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aae1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aae2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800aae2b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aae3b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800aae3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aae11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800aae11`

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
0x1800aaddc  mov     [rsp-8+arg_10], rbx
0x1800aade1  push    rbp
0x1800aade2  mov     rbp, rsp
0x1800aade5  sub     rsp, 30h
0x1800aade9  mov     rax, cs:__security_cookie
0x1800aadf0  mov     rbx, 2B992DDFA232h
0x1800aadfa  cmp     rax, rbx
0x1800aadfd  jnz     short loc_1800AAE7C
0x1800aadff  xor     eax, eax
0x1800aae01  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800aae05  mov     [rbp+var_10], rax
0x1800aae09  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800aae0d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800aae11  call    cs:__imp_GetSystemTimeAsFileTime
0x1800aae17  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800aae1b  mov     [rbp+var_10], rax
0x1800aae1f  call    cs:__imp_GetCurrentThreadId
0x1800aae25  mov     eax, eax
0x1800aae27  xor     [rbp+var_10], rax
0x1800aae2b  call    cs:__imp_GetCurrentProcessId
0x1800aae31  mov     eax, eax
0x1800aae33  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800aae37  xor     [rbp+var_10], rax
0x1800aae3b  call    cs:__imp_QueryPerformanceCounter
0x1800aae41  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800aae44  lea     rcx, [rbp+var_10]
0x1800aae48  shl     rax, 20h
0x1800aae4c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800aae50  xor     rax, [rbp+var_10]
0x1800aae54  xor     rax, rcx
0x1800aae57  mov     rcx, 0FFFFFFFFFFFFh
0x1800aae61  and     rax, rcx
0x1800aae64  mov     rcx, 2B992DDFA233h
0x1800aae6e  cmp     rax, rbx
0x1800aae71  cmovz   rax, rcx
0x1800aae75  mov     cs:__security_cookie, rax
0x1800aae7c  mov     rbx, [rsp+30h+arg_10]
0x1800aae81  not     rax
0x1800aae84  mov     cs:__security_cookie_complement, rax
0x1800aae8b  add     rsp, 30h
0x1800aae8f  pop     rbp
0x1800aae90  retn
```
