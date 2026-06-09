# __security_init_cookie

- ea: `0x18002d17c`
- end: `0x18002d231`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c5f0`

## callees

- `0x18002d17c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d1bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d1cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d1cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d1b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d1b1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002d1db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002d1db`

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
0x18002d17c  mov     [rsp-8+arg_10], rbx
0x18002d181  push    rbp
0x18002d182  mov     rbp, rsp
0x18002d185  sub     rsp, 30h
0x18002d189  mov     rax, cs:__security_cookie
0x18002d190  mov     rbx, 2B992DDFA232h
0x18002d19a  cmp     rax, rbx
0x18002d19d  jnz     short loc_18002D21C
0x18002d19f  xor     eax, eax
0x18002d1a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002d1a5  mov     [rbp+var_10], rax
0x18002d1a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002d1ad  mov     qword ptr [rbp+PerformanceCount], rax
0x18002d1b1  call    cs:__imp_GetSystemTimeAsFileTime
0x18002d1b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002d1bb  mov     [rbp+var_10], rax
0x18002d1bf  call    cs:__imp_GetCurrentThreadId
0x18002d1c5  mov     eax, eax
0x18002d1c7  xor     [rbp+var_10], rax
0x18002d1cb  call    cs:__imp_GetCurrentProcessId
0x18002d1d1  mov     eax, eax
0x18002d1d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002d1d7  xor     [rbp+var_10], rax
0x18002d1db  call    cs:__imp_QueryPerformanceCounter
0x18002d1e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002d1e4  lea     rcx, [rbp+var_10]
0x18002d1e8  shl     rax, 20h
0x18002d1ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002d1f0  xor     rax, [rbp+var_10]
0x18002d1f4  xor     rax, rcx
0x18002d1f7  mov     rcx, 0FFFFFFFFFFFFh
0x18002d201  and     rax, rcx
0x18002d204  mov     rcx, 2B992DDFA233h
0x18002d20e  cmp     rax, rbx
0x18002d211  cmovz   rax, rcx
0x18002d215  mov     cs:__security_cookie, rax
0x18002d21c  mov     rbx, [rsp+30h+arg_10]
0x18002d221  not     rax
0x18002d224  mov     cs:__security_cookie_complement, rax
0x18002d22b  add     rsp, 30h
0x18002d22f  pop     rbp
0x18002d230  retn
```
