# __security_init_cookie

- ea: `0x1800068b0`
- end: `0x180006965`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006050`

## callees

- `0x1800068b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800068ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800068ff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000690f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000690f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800068e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800068e5`

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
0x1800068b0  mov     [rsp-8+arg_10], rbx
0x1800068b5  push    rbp
0x1800068b6  mov     rbp, rsp
0x1800068b9  sub     rsp, 30h
0x1800068bd  mov     rax, cs:__security_cookie
0x1800068c4  mov     rbx, 2B992DDFA232h
0x1800068ce  cmp     rax, rbx
0x1800068d1  jnz     short loc_180006950
0x1800068d3  xor     eax, eax
0x1800068d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800068d9  mov     [rbp+var_10], rax
0x1800068dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800068e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800068e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800068eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800068ef  mov     [rbp+var_10], rax
0x1800068f3  call    cs:__imp_GetCurrentThreadId
0x1800068f9  mov     eax, eax
0x1800068fb  xor     [rbp+var_10], rax
0x1800068ff  call    cs:__imp_GetCurrentProcessId
0x180006905  mov     eax, eax
0x180006907  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000690b  xor     [rbp+var_10], rax
0x18000690f  call    cs:__imp_QueryPerformanceCounter
0x180006915  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006918  lea     rcx, [rbp+var_10]
0x18000691c  shl     rax, 20h
0x180006920  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006924  xor     rax, [rbp+var_10]
0x180006928  xor     rax, rcx
0x18000692b  mov     rcx, 0FFFFFFFFFFFFh
0x180006935  and     rax, rcx
0x180006938  mov     rcx, 2B992DDFA233h
0x180006942  cmp     rax, rbx
0x180006945  cmovz   rax, rcx
0x180006949  mov     cs:__security_cookie, rax
0x180006950  mov     rbx, [rsp+30h+arg_10]
0x180006955  not     rax
0x180006958  mov     cs:__security_cookie_complement, rax
0x18000695f  add     rsp, 30h
0x180006963  pop     rbp
0x180006964  retn
```
