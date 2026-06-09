# __security_init_cookie

- ea: `0x18000736c`
- end: `0x180007421`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006e00`

## callees

- `0x18000736c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800073bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800073bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800073af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800073af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800073cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800073cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800073a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800073a1`

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
0x18000736c  mov     [rsp-8+arg_10], rbx
0x180007371  push    rbp
0x180007372  mov     rbp, rsp
0x180007375  sub     rsp, 30h
0x180007379  mov     rax, cs:__security_cookie
0x180007380  mov     rbx, 2B992DDFA232h
0x18000738a  cmp     rax, rbx
0x18000738d  jnz     short loc_18000740C
0x18000738f  xor     eax, eax
0x180007391  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180007395  mov     [rbp+var_10], rax
0x180007399  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000739d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800073a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800073a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800073ab  mov     [rbp+var_10], rax
0x1800073af  call    cs:__imp_GetCurrentThreadId
0x1800073b5  mov     eax, eax
0x1800073b7  xor     [rbp+var_10], rax
0x1800073bb  call    cs:__imp_GetCurrentProcessId
0x1800073c1  mov     eax, eax
0x1800073c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800073c7  xor     [rbp+var_10], rax
0x1800073cb  call    cs:__imp_QueryPerformanceCounter
0x1800073d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800073d4  lea     rcx, [rbp+var_10]
0x1800073d8  shl     rax, 20h
0x1800073dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800073e0  xor     rax, [rbp+var_10]
0x1800073e4  xor     rax, rcx
0x1800073e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800073f1  and     rax, rcx
0x1800073f4  mov     rcx, 2B992DDFA233h
0x1800073fe  cmp     rax, rbx
0x180007401  cmovz   rax, rcx
0x180007405  mov     cs:__security_cookie, rax
0x18000740c  mov     rbx, [rsp+30h+arg_10]
0x180007411  not     rax
0x180007414  mov     cs:__security_cookie_complement, rax
0x18000741b  add     rsp, 30h
0x18000741f  pop     rbp
0x180007420  retn
```
