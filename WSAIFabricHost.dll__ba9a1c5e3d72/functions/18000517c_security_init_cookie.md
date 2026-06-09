# __security_init_cookie

- ea: `0x18000517c`
- end: `0x180005231`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004c50`

## callees

- `0x18000517c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800051cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800051db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800051db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800051b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800051b1`

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
0x18000517c  mov     [rsp-8+arg_10], rbx
0x180005181  push    rbp
0x180005182  mov     rbp, rsp
0x180005185  sub     rsp, 30h
0x180005189  mov     rax, cs:__security_cookie
0x180005190  mov     rbx, 2B992DDFA232h
0x18000519a  cmp     rax, rbx
0x18000519d  jnz     short loc_18000521C
0x18000519f  xor     eax, eax
0x1800051a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800051a5  mov     [rbp+var_10], rax
0x1800051a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800051ad  mov     qword ptr [rbp+PerformanceCount], rax
0x1800051b1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800051b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800051bb  mov     [rbp+var_10], rax
0x1800051bf  call    cs:__imp_GetCurrentThreadId
0x1800051c5  mov     eax, eax
0x1800051c7  xor     [rbp+var_10], rax
0x1800051cb  call    cs:__imp_GetCurrentProcessId
0x1800051d1  mov     eax, eax
0x1800051d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800051d7  xor     [rbp+var_10], rax
0x1800051db  call    cs:__imp_QueryPerformanceCounter
0x1800051e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800051e4  lea     rcx, [rbp+var_10]
0x1800051e8  shl     rax, 20h
0x1800051ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800051f0  xor     rax, [rbp+var_10]
0x1800051f4  xor     rax, rcx
0x1800051f7  mov     rcx, 0FFFFFFFFFFFFh
0x180005201  and     rax, rcx
0x180005204  mov     rcx, 2B992DDFA233h
0x18000520e  cmp     rax, rbx
0x180005211  cmovz   rax, rcx
0x180005215  mov     cs:__security_cookie, rax
0x18000521c  mov     rbx, [rsp+30h+arg_10]
0x180005221  not     rax
0x180005224  mov     cs:__security_cookie_complement, rax
0x18000522b  add     rsp, 30h
0x18000522f  pop     rbp
0x180005230  retn
```
