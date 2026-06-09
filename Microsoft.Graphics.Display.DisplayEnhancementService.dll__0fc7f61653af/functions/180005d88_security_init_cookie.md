# __security_init_cookie

- ea: `0x180005d88`
- end: `0x180005e3d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005810`

## callees

- `0x180005d88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005dcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005dcb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005de7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005de7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005dbd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005dbd`

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
0x180005d88  mov     [rsp-8+arg_10], rbx
0x180005d8d  push    rbp
0x180005d8e  mov     rbp, rsp
0x180005d91  sub     rsp, 30h
0x180005d95  mov     rax, cs:__security_cookie
0x180005d9c  mov     rbx, 2B992DDFA232h
0x180005da6  cmp     rax, rbx
0x180005da9  jnz     short loc_180005E28
0x180005dab  xor     eax, eax
0x180005dad  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005db1  mov     [rbp+var_10], rax
0x180005db5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005db9  mov     qword ptr [rbp+PerformanceCount], rax
0x180005dbd  call    cs:__imp_GetSystemTimeAsFileTime
0x180005dc3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005dc7  mov     [rbp+var_10], rax
0x180005dcb  call    cs:__imp_GetCurrentThreadId
0x180005dd1  mov     eax, eax
0x180005dd3  xor     [rbp+var_10], rax
0x180005dd7  call    cs:__imp_GetCurrentProcessId
0x180005ddd  mov     eax, eax
0x180005ddf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005de3  xor     [rbp+var_10], rax
0x180005de7  call    cs:__imp_QueryPerformanceCounter
0x180005ded  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005df0  lea     rcx, [rbp+var_10]
0x180005df4  shl     rax, 20h
0x180005df8  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005dfc  xor     rax, [rbp+var_10]
0x180005e00  xor     rax, rcx
0x180005e03  mov     rcx, 0FFFFFFFFFFFFh
0x180005e0d  and     rax, rcx
0x180005e10  mov     rcx, 2B992DDFA233h
0x180005e1a  cmp     rax, rbx
0x180005e1d  cmovz   rax, rcx
0x180005e21  mov     cs:__security_cookie, rax
0x180005e28  mov     rbx, [rsp+30h+arg_10]
0x180005e2d  not     rax
0x180005e30  mov     cs:__security_cookie_complement, rax
0x180005e37  add     rsp, 30h
0x180005e3b  pop     rbp
0x180005e3c  retn
```
