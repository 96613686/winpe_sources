# __security_init_cookie

- ea: `0x140001790`
- end: `0x140001845`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001450`

## callees

- `0x140001790`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400017df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400017df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400017d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400017d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017ef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017c5`

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
0x140001790  mov     [rsp-8+arg_10], rbx
0x140001795  push    rbp
0x140001796  mov     rbp, rsp
0x140001799  sub     rsp, 30h
0x14000179d  mov     rax, cs:__security_cookie
0x1400017a4  mov     rbx, 2B992DDFA232h
0x1400017ae  cmp     rax, rbx
0x1400017b1  jnz     short loc_140001830
0x1400017b3  xor     eax, eax
0x1400017b5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400017b9  mov     [rbp+var_10], rax
0x1400017bd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400017c1  mov     qword ptr [rbp+PerformanceCount], rax
0x1400017c5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400017cb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400017cf  mov     [rbp+var_10], rax
0x1400017d3  call    cs:__imp_GetCurrentThreadId
0x1400017d9  mov     eax, eax
0x1400017db  xor     [rbp+var_10], rax
0x1400017df  call    cs:__imp_GetCurrentProcessId
0x1400017e5  mov     eax, eax
0x1400017e7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400017eb  xor     [rbp+var_10], rax
0x1400017ef  call    cs:__imp_QueryPerformanceCounter
0x1400017f5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400017f8  lea     rcx, [rbp+var_10]
0x1400017fc  shl     rax, 20h
0x140001800  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001804  xor     rax, [rbp+var_10]
0x140001808  xor     rax, rcx
0x14000180b  mov     rcx, 0FFFFFFFFFFFFh
0x140001815  and     rax, rcx
0x140001818  mov     rcx, 2B992DDFA233h
0x140001822  cmp     rax, rbx
0x140001825  cmovz   rax, rcx
0x140001829  mov     cs:__security_cookie, rax
0x140001830  mov     rbx, [rsp+30h+arg_10]
0x140001835  not     rax
0x140001838  mov     cs:__security_cookie_complement, rax
0x14000183f  add     rsp, 30h
0x140001843  pop     rbp
0x140001844  retn
```
