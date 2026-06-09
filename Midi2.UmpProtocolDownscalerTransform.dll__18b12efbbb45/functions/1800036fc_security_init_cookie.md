# __security_init_cookie

- ea: `0x1800036fc`
- end: `0x1800037b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002e10`

## callees

- `0x1800036fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000374b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000374b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000373f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000373f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000375b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000375b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003731`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003731`

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
0x1800036fc  mov     [rsp-8+arg_10], rbx
0x180003701  push    rbp
0x180003702  mov     rbp, rsp
0x180003705  sub     rsp, 30h
0x180003709  mov     rax, cs:__security_cookie
0x180003710  mov     rbx, 2B992DDFA232h
0x18000371a  cmp     rax, rbx
0x18000371d  jnz     short loc_18000379C
0x18000371f  xor     eax, eax
0x180003721  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003725  mov     [rbp+var_10], rax
0x180003729  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000372d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003731  call    cs:__imp_GetSystemTimeAsFileTime
0x180003737  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000373b  mov     [rbp+var_10], rax
0x18000373f  call    cs:__imp_GetCurrentThreadId
0x180003745  mov     eax, eax
0x180003747  xor     [rbp+var_10], rax
0x18000374b  call    cs:__imp_GetCurrentProcessId
0x180003751  mov     eax, eax
0x180003753  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003757  xor     [rbp+var_10], rax
0x18000375b  call    cs:__imp_QueryPerformanceCounter
0x180003761  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003764  lea     rcx, [rbp+var_10]
0x180003768  shl     rax, 20h
0x18000376c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003770  xor     rax, [rbp+var_10]
0x180003774  xor     rax, rcx
0x180003777  mov     rcx, 0FFFFFFFFFFFFh
0x180003781  and     rax, rcx
0x180003784  mov     rcx, 2B992DDFA233h
0x18000378e  cmp     rax, rbx
0x180003791  cmovz   rax, rcx
0x180003795  mov     cs:__security_cookie, rax
0x18000379c  mov     rbx, [rsp+30h+arg_10]
0x1800037a1  not     rax
0x1800037a4  mov     cs:__security_cookie_complement, rax
0x1800037ab  add     rsp, 30h
0x1800037af  pop     rbp
0x1800037b0  retn
```
