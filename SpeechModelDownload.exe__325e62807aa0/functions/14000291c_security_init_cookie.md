# __security_init_cookie

- ea: `0x14000291c`
- end: `0x1400029d1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400025d0`

## callees

- `0x14000291c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000295f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000295f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000296b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000296b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000297b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000297b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002951`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002951`

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
0x14000291c  mov     [rsp-8+arg_10], rbx
0x140002921  push    rbp
0x140002922  mov     rbp, rsp
0x140002925  sub     rsp, 30h
0x140002929  mov     rax, cs:__security_cookie
0x140002930  mov     rbx, 2B992DDFA232h
0x14000293a  cmp     rax, rbx
0x14000293d  jnz     short loc_1400029BC
0x14000293f  xor     eax, eax
0x140002941  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002945  mov     [rbp+var_10], rax
0x140002949  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000294d  mov     qword ptr [rbp+PerformanceCount], rax
0x140002951  call    cs:__imp_GetSystemTimeAsFileTime
0x140002957  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000295b  mov     [rbp+var_10], rax
0x14000295f  call    cs:__imp_GetCurrentThreadId
0x140002965  mov     eax, eax
0x140002967  xor     [rbp+var_10], rax
0x14000296b  call    cs:__imp_GetCurrentProcessId
0x140002971  mov     eax, eax
0x140002973  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002977  xor     [rbp+var_10], rax
0x14000297b  call    cs:__imp_QueryPerformanceCounter
0x140002981  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002984  lea     rcx, [rbp+var_10]
0x140002988  shl     rax, 20h
0x14000298c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002990  xor     rax, [rbp+var_10]
0x140002994  xor     rax, rcx
0x140002997  mov     rcx, 0FFFFFFFFFFFFh
0x1400029a1  and     rax, rcx
0x1400029a4  mov     rcx, 2B992DDFA233h
0x1400029ae  cmp     rax, rbx
0x1400029b1  cmovz   rax, rcx
0x1400029b5  mov     cs:__security_cookie, rax
0x1400029bc  mov     rbx, [rsp+30h+arg_10]
0x1400029c1  not     rax
0x1400029c4  mov     cs:__security_cookie_complement, rax
0x1400029cb  add     rsp, 30h
0x1400029cf  pop     rbp
0x1400029d0  retn
```
