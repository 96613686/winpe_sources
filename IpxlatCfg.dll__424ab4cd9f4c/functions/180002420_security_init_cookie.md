# __security_init_cookie

- ea: `0x180002420`
- end: `0x1800024d5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001cf0`

## callees

- `0x180002420`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002463`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000246f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000246f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000247f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000247f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002455`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002455`

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
0x180002420  mov     [rsp-8+arg_10], rbx
0x180002425  push    rbp
0x180002426  mov     rbp, rsp
0x180002429  sub     rsp, 30h
0x18000242d  mov     rax, cs:__security_cookie
0x180002434  mov     rbx, 2B992DDFA232h
0x18000243e  cmp     rax, rbx
0x180002441  jnz     short loc_1800024C0
0x180002443  xor     eax, eax
0x180002445  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002449  mov     [rbp+var_10], rax
0x18000244d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002451  mov     qword ptr [rbp+PerformanceCount], rax
0x180002455  call    cs:__imp_GetSystemTimeAsFileTime
0x18000245b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000245f  mov     [rbp+var_10], rax
0x180002463  call    cs:__imp_GetCurrentThreadId
0x180002469  mov     eax, eax
0x18000246b  xor     [rbp+var_10], rax
0x18000246f  call    cs:__imp_GetCurrentProcessId
0x180002475  mov     eax, eax
0x180002477  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000247b  xor     [rbp+var_10], rax
0x18000247f  call    cs:__imp_QueryPerformanceCounter
0x180002485  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002488  lea     rcx, [rbp+var_10]
0x18000248c  shl     rax, 20h
0x180002490  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002494  xor     rax, [rbp+var_10]
0x180002498  xor     rax, rcx
0x18000249b  mov     rcx, 0FFFFFFFFFFFFh
0x1800024a5  and     rax, rcx
0x1800024a8  mov     rcx, 2B992DDFA233h
0x1800024b2  cmp     rax, rbx
0x1800024b5  cmovz   rax, rcx
0x1800024b9  mov     cs:__security_cookie, rax
0x1800024c0  mov     rbx, [rsp+30h+arg_10]
0x1800024c5  not     rax
0x1800024c8  mov     cs:__security_cookie_complement, rax
0x1800024cf  add     rsp, 30h
0x1800024d3  pop     rbp
0x1800024d4  retn
```
