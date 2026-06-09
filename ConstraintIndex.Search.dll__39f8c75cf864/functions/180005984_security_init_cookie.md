# __security_init_cookie

- ea: `0x180005984`
- end: `0x180005a39`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800055b0`

## callees

- `0x180005984`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800059b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800059b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800059e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800059e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800059d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800059d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059c7`

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
0x180005984  mov     [rsp-8+arg_10], rbx
0x180005989  push    rbp
0x18000598a  mov     rbp, rsp
0x18000598d  sub     rsp, 30h
0x180005991  mov     rax, cs:__security_cookie
0x180005998  mov     rbx, 2B992DDFA232h
0x1800059a2  cmp     rax, rbx
0x1800059a5  jnz     short loc_180005A24
0x1800059a7  xor     eax, eax
0x1800059a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800059ad  mov     [rbp+var_10], rax
0x1800059b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800059b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800059b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800059bf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800059c3  mov     [rbp+var_10], rax
0x1800059c7  call    cs:__imp_GetCurrentThreadId
0x1800059cd  mov     eax, eax
0x1800059cf  xor     [rbp+var_10], rax
0x1800059d3  call    cs:__imp_GetCurrentProcessId
0x1800059d9  mov     eax, eax
0x1800059db  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800059df  xor     [rbp+var_10], rax
0x1800059e3  call    cs:__imp_QueryPerformanceCounter
0x1800059e9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800059ec  lea     rcx, [rbp+var_10]
0x1800059f0  shl     rax, 20h
0x1800059f4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800059f8  xor     rax, [rbp+var_10]
0x1800059fc  xor     rax, rcx
0x1800059ff  mov     rcx, 0FFFFFFFFFFFFh
0x180005a09  and     rax, rcx
0x180005a0c  mov     rcx, 2B992DDFA233h
0x180005a16  cmp     rax, rbx
0x180005a19  cmovz   rax, rcx
0x180005a1d  mov     cs:__security_cookie, rax
0x180005a24  mov     rbx, [rsp+30h+arg_10]
0x180005a29  not     rax
0x180005a2c  mov     cs:__security_cookie_complement, rax
0x180005a33  add     rsp, 30h
0x180005a37  pop     rbp
0x180005a38  retn
```
