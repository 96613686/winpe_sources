# __security_init_cookie

- ea: `0x18001a97c`
- end: `0x18001aa31`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a4f0`

## callees

- `0x18001a97c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a9cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a9cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a9bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a9bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001a9db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001a9db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a9b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a9b1`

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
0x18001a97c  mov     [rsp-8+arg_10], rbx
0x18001a981  push    rbp
0x18001a982  mov     rbp, rsp
0x18001a985  sub     rsp, 30h
0x18001a989  mov     rax, cs:__security_cookie
0x18001a990  mov     rbx, 2B992DDFA232h
0x18001a99a  cmp     rax, rbx
0x18001a99d  jnz     short loc_18001AA1C
0x18001a99f  xor     eax, eax
0x18001a9a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a9a5  mov     [rbp+var_10], rax
0x18001a9a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001a9ad  mov     qword ptr [rbp+PerformanceCount], rax
0x18001a9b1  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a9b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001a9bb  mov     [rbp+var_10], rax
0x18001a9bf  call    cs:__imp_GetCurrentThreadId
0x18001a9c5  mov     eax, eax
0x18001a9c7  xor     [rbp+var_10], rax
0x18001a9cb  call    cs:__imp_GetCurrentProcessId
0x18001a9d1  mov     eax, eax
0x18001a9d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001a9d7  xor     [rbp+var_10], rax
0x18001a9db  call    cs:__imp_QueryPerformanceCounter
0x18001a9e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001a9e4  lea     rcx, [rbp+var_10]
0x18001a9e8  shl     rax, 20h
0x18001a9ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001a9f0  xor     rax, [rbp+var_10]
0x18001a9f4  xor     rax, rcx
0x18001a9f7  mov     rcx, 0FFFFFFFFFFFFh
0x18001aa01  and     rax, rcx
0x18001aa04  mov     rcx, 2B992DDFA233h
0x18001aa0e  cmp     rax, rbx
0x18001aa11  cmovz   rax, rcx
0x18001aa15  mov     cs:__security_cookie, rax
0x18001aa1c  mov     rbx, [rsp+30h+arg_10]
0x18001aa21  not     rax
0x18001aa24  mov     cs:__security_cookie_complement, rax
0x18001aa2b  add     rsp, 30h
0x18001aa2f  pop     rbp
0x18001aa30  retn
```
