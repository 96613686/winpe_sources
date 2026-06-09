# __security_init_cookie

- ea: `0x1800081d0`
- end: `0x180008285`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007600`

## callees

- `0x1800081d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000821f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000821f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008213`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008213`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008205`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008205`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000822f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000822f`

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
0x1800081d0  mov     [rsp-8+arg_10], rbx
0x1800081d5  push    rbp
0x1800081d6  mov     rbp, rsp
0x1800081d9  sub     rsp, 30h
0x1800081dd  mov     rax, cs:__security_cookie
0x1800081e4  mov     rbx, 2B992DDFA232h
0x1800081ee  cmp     rax, rbx
0x1800081f1  jnz     short loc_180008270
0x1800081f3  xor     eax, eax
0x1800081f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800081f9  mov     [rbp+var_10], rax
0x1800081fd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008201  mov     qword ptr [rbp+PerformanceCount], rax
0x180008205  call    cs:__imp_GetSystemTimeAsFileTime
0x18000820b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000820f  mov     [rbp+var_10], rax
0x180008213  call    cs:__imp_GetCurrentThreadId
0x180008219  mov     eax, eax
0x18000821b  xor     [rbp+var_10], rax
0x18000821f  call    cs:__imp_GetCurrentProcessId
0x180008225  mov     eax, eax
0x180008227  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000822b  xor     [rbp+var_10], rax
0x18000822f  call    cs:__imp_QueryPerformanceCounter
0x180008235  mov     eax, dword ptr [rbp+PerformanceCount]
0x180008238  lea     rcx, [rbp+var_10]
0x18000823c  shl     rax, 20h
0x180008240  xor     rax, qword ptr [rbp+PerformanceCount]
0x180008244  xor     rax, [rbp+var_10]
0x180008248  xor     rax, rcx
0x18000824b  mov     rcx, 0FFFFFFFFFFFFh
0x180008255  and     rax, rcx
0x180008258  mov     rcx, 2B992DDFA233h
0x180008262  cmp     rax, rbx
0x180008265  cmovz   rax, rcx
0x180008269  mov     cs:__security_cookie, rax
0x180008270  mov     rbx, [rsp+30h+arg_10]
0x180008275  not     rax
0x180008278  mov     cs:__security_cookie_complement, rax
0x18000827f  add     rsp, 30h
0x180008283  pop     rbp
0x180008284  retn
```
