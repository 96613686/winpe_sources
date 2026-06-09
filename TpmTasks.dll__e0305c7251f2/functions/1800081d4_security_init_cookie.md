# __security_init_cookie

- ea: `0x1800081d4`
- end: `0x180008289`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007850`

## callees

- `0x1800081d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180008223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008217`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008209`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008209`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008233`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180008233`

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
0x1800081d4  mov     [rsp-8+arg_10], rbx
0x1800081d9  push    rbp
0x1800081da  mov     rbp, rsp
0x1800081dd  sub     rsp, 30h
0x1800081e1  mov     rax, cs:__security_cookie
0x1800081e8  mov     rbx, 2B992DDFA232h
0x1800081f2  cmp     rax, rbx
0x1800081f5  jnz     short loc_180008274
0x1800081f7  xor     eax, eax
0x1800081f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800081fd  mov     [rbp+var_10], rax
0x180008201  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008205  mov     qword ptr [rbp+PerformanceCount], rax
0x180008209  call    cs:__imp_GetSystemTimeAsFileTime
0x18000820f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008213  mov     [rbp+var_10], rax
0x180008217  call    cs:__imp_GetCurrentThreadId
0x18000821d  mov     eax, eax
0x18000821f  xor     [rbp+var_10], rax
0x180008223  call    cs:__imp_GetCurrentProcessId
0x180008229  mov     eax, eax
0x18000822b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000822f  xor     [rbp+var_10], rax
0x180008233  call    cs:__imp_QueryPerformanceCounter
0x180008239  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000823c  lea     rcx, [rbp+var_10]
0x180008240  shl     rax, 20h
0x180008244  xor     rax, qword ptr [rbp+PerformanceCount]
0x180008248  xor     rax, [rbp+var_10]
0x18000824c  xor     rax, rcx
0x18000824f  mov     rcx, 0FFFFFFFFFFFFh
0x180008259  and     rax, rcx
0x18000825c  mov     rcx, 2B992DDFA233h
0x180008266  cmp     rax, rbx
0x180008269  cmovz   rax, rcx
0x18000826d  mov     cs:__security_cookie, rax
0x180008274  mov     rbx, [rsp+30h+arg_10]
0x180008279  not     rax
0x18000827c  mov     cs:__security_cookie_complement, rax
0x180008283  add     rsp, 30h
0x180008287  pop     rbp
0x180008288  retn
```
