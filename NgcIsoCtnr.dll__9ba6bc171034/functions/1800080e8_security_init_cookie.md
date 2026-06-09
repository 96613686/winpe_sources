# __security_init_cookie

- ea: `0x1800080e8`
- end: `0x18000819d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007620`

## callees

- `0x1800080e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000812b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000812b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008137`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000811d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000811d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008147`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008147`

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
0x1800080e8  mov     [rsp-8+arg_10], rbx
0x1800080ed  push    rbp
0x1800080ee  mov     rbp, rsp
0x1800080f1  sub     rsp, 30h
0x1800080f5  mov     rax, cs:__security_cookie
0x1800080fc  mov     rbx, 2B992DDFA232h
0x180008106  cmp     rax, rbx
0x180008109  jnz     short loc_180008188
0x18000810b  xor     eax, eax
0x18000810d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008111  mov     [rbp+var_10], rax
0x180008115  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008119  mov     qword ptr [rbp+PerformanceCount], rax
0x18000811d  call    cs:__imp_GetSystemTimeAsFileTime
0x180008123  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008127  mov     [rbp+var_10], rax
0x18000812b  call    cs:__imp_GetCurrentThreadId
0x180008131  mov     eax, eax
0x180008133  xor     [rbp+var_10], rax
0x180008137  call    cs:__imp_GetCurrentProcessId
0x18000813d  mov     eax, eax
0x18000813f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180008143  xor     [rbp+var_10], rax
0x180008147  call    cs:__imp_QueryPerformanceCounter
0x18000814d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008150  lea     rcx, [rbp+var_10]
0x180008154  shl     rax, 20h
0x180008158  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000815c  xor     rax, [rbp+var_10]
0x180008160  xor     rax, rcx
0x180008163  mov     rcx, 0FFFFFFFFFFFFh
0x18000816d  and     rax, rcx
0x180008170  mov     rcx, 2B992DDFA233h
0x18000817a  cmp     rax, rbx
0x18000817d  cmovz   rax, rcx
0x180008181  mov     cs:__security_cookie, rax
0x180008188  mov     rbx, [rsp+30h+arg_10]
0x18000818d  not     rax
0x180008190  mov     cs:__security_cookie_complement, rax
0x180008197  add     rsp, 30h
0x18000819b  pop     rbp
0x18000819c  retn
```
