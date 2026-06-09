# __security_init_cookie

- ea: `0x18004410c`
- end: `0x1800441c1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180043be0`

## callees

- `0x18004410c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004414f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004414f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004415b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004415b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004416b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004416b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044141`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044141`

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
0x18004410c  mov     [rsp-8+arg_10], rbx
0x180044111  push    rbp
0x180044112  mov     rbp, rsp
0x180044115  sub     rsp, 30h
0x180044119  mov     rax, cs:__security_cookie
0x180044120  mov     rbx, 2B992DDFA232h
0x18004412a  cmp     rax, rbx
0x18004412d  jnz     short loc_1800441AC
0x18004412f  xor     eax, eax
0x180044131  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180044135  mov     [rbp+var_10], rax
0x180044139  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004413d  mov     qword ptr [rbp+PerformanceCount], rax
0x180044141  call    cs:__imp_GetSystemTimeAsFileTime
0x180044147  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004414b  mov     [rbp+var_10], rax
0x18004414f  call    cs:__imp_GetCurrentThreadId
0x180044155  mov     eax, eax
0x180044157  xor     [rbp+var_10], rax
0x18004415b  call    cs:__imp_GetCurrentProcessId
0x180044161  mov     eax, eax
0x180044163  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180044167  xor     [rbp+var_10], rax
0x18004416b  call    cs:__imp_QueryPerformanceCounter
0x180044171  mov     eax, dword ptr [rbp+PerformanceCount]
0x180044174  lea     rcx, [rbp+var_10]
0x180044178  shl     rax, 20h
0x18004417c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180044180  xor     rax, [rbp+var_10]
0x180044184  xor     rax, rcx
0x180044187  mov     rcx, 0FFFFFFFFFFFFh
0x180044191  and     rax, rcx
0x180044194  mov     rcx, 2B992DDFA233h
0x18004419e  cmp     rax, rbx
0x1800441a1  cmovz   rax, rcx
0x1800441a5  mov     cs:__security_cookie, rax
0x1800441ac  mov     rbx, [rsp+30h+arg_10]
0x1800441b1  not     rax
0x1800441b4  mov     cs:__security_cookie_complement, rax
0x1800441bb  add     rsp, 30h
0x1800441bf  pop     rbp
0x1800441c0  retn
```
