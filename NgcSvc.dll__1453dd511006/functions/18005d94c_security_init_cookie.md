# __security_init_cookie

- ea: `0x18005d94c`
- end: `0x18005da01`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005ce90`

## callees

- `0x18005d94c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005d99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005d99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d98f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d98f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005d981`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005d981`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005d9ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005d9ab`

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
0x18005d94c  mov     [rsp-8+arg_10], rbx
0x18005d951  push    rbp
0x18005d952  mov     rbp, rsp
0x18005d955  sub     rsp, 30h
0x18005d959  mov     rax, cs:__security_cookie
0x18005d960  mov     rbx, 2B992DDFA232h
0x18005d96a  cmp     rax, rbx
0x18005d96d  jnz     short loc_18005D9EC
0x18005d96f  xor     eax, eax
0x18005d971  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005d975  mov     [rbp+var_10], rax
0x18005d979  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005d97d  mov     qword ptr [rbp+PerformanceCount], rax
0x18005d981  call    cs:__imp_GetSystemTimeAsFileTime
0x18005d987  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005d98b  mov     [rbp+var_10], rax
0x18005d98f  call    cs:__imp_GetCurrentThreadId
0x18005d995  mov     eax, eax
0x18005d997  xor     [rbp+var_10], rax
0x18005d99b  call    cs:__imp_GetCurrentProcessId
0x18005d9a1  mov     eax, eax
0x18005d9a3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005d9a7  xor     [rbp+var_10], rax
0x18005d9ab  call    cs:__imp_QueryPerformanceCounter
0x18005d9b1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005d9b4  lea     rcx, [rbp+var_10]
0x18005d9b8  shl     rax, 20h
0x18005d9bc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18005d9c0  xor     rax, [rbp+var_10]
0x18005d9c4  xor     rax, rcx
0x18005d9c7  mov     rcx, 0FFFFFFFFFFFFh
0x18005d9d1  and     rax, rcx
0x18005d9d4  mov     rcx, 2B992DDFA233h
0x18005d9de  cmp     rax, rbx
0x18005d9e1  cmovz   rax, rcx
0x18005d9e5  mov     cs:__security_cookie, rax
0x18005d9ec  mov     rbx, [rsp+30h+arg_10]
0x18005d9f1  not     rax
0x18005d9f4  mov     cs:__security_cookie_complement, rax
0x18005d9fb  add     rsp, 30h
0x18005d9ff  pop     rbp
0x18005da00  retn
```
