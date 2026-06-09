# __security_init_cookie

- ea: `0x140002d30`
- end: `0x140002de5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002900`

## callees

- `0x140002d30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002d7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002d7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002d65`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002d65`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002d8f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002d8f`

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
0x140002d30  mov     [rsp-8+arg_10], rbx
0x140002d35  push    rbp
0x140002d36  mov     rbp, rsp
0x140002d39  sub     rsp, 30h
0x140002d3d  mov     rax, cs:__security_cookie
0x140002d44  mov     rbx, 2B992DDFA232h
0x140002d4e  cmp     rax, rbx
0x140002d51  jnz     short loc_140002DD0
0x140002d53  xor     eax, eax
0x140002d55  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002d59  mov     [rbp+var_10], rax
0x140002d5d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002d61  mov     qword ptr [rbp+PerformanceCount], rax
0x140002d65  call    cs:__imp_GetSystemTimeAsFileTime
0x140002d6b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002d6f  mov     [rbp+var_10], rax
0x140002d73  call    cs:__imp_GetCurrentThreadId
0x140002d79  mov     eax, eax
0x140002d7b  xor     [rbp+var_10], rax
0x140002d7f  call    cs:__imp_GetCurrentProcessId
0x140002d85  mov     eax, eax
0x140002d87  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002d8b  xor     [rbp+var_10], rax
0x140002d8f  call    cs:__imp_QueryPerformanceCounter
0x140002d95  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002d98  lea     rcx, [rbp+var_10]
0x140002d9c  shl     rax, 20h
0x140002da0  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002da4  xor     rax, [rbp+var_10]
0x140002da8  xor     rax, rcx
0x140002dab  mov     rcx, 0FFFFFFFFFFFFh
0x140002db5  and     rax, rcx
0x140002db8  mov     rcx, 2B992DDFA233h
0x140002dc2  cmp     rax, rbx
0x140002dc5  cmovz   rax, rcx
0x140002dc9  mov     cs:__security_cookie, rax
0x140002dd0  mov     rbx, [rsp+30h+arg_10]
0x140002dd5  not     rax
0x140002dd8  mov     cs:__security_cookie_complement, rax
0x140002ddf  add     rsp, 30h
0x140002de3  pop     rbp
0x140002de4  retn
```
