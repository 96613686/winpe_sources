# __security_init_cookie

- ea: `0x180001aa4`
- end: `0x180001b59`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a30`

## callees

- `0x180001aa4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001af3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001af3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ae7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ad9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ad9`

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
0x180001aa4  mov     [rsp-8+arg_10], rbx
0x180001aa9  push    rbp
0x180001aaa  mov     rbp, rsp
0x180001aad  sub     rsp, 30h
0x180001ab1  mov     rax, cs:__security_cookie
0x180001ab8  mov     rbx, 2B992DDFA232h
0x180001ac2  cmp     rax, rbx
0x180001ac5  jnz     short loc_180001B44
0x180001ac7  xor     eax, eax
0x180001ac9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001acd  mov     [rbp+var_10], rax
0x180001ad1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ad5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ad9  call    cs:__imp_GetSystemTimeAsFileTime
0x180001adf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ae3  mov     [rbp+var_10], rax
0x180001ae7  call    cs:__imp_GetCurrentThreadId
0x180001aed  mov     eax, eax
0x180001aef  xor     [rbp+var_10], rax
0x180001af3  call    cs:__imp_GetCurrentProcessId
0x180001af9  mov     eax, eax
0x180001afb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001aff  xor     [rbp+var_10], rax
0x180001b03  call    cs:__imp_QueryPerformanceCounter
0x180001b09  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001b0c  lea     rcx, [rbp+var_10]
0x180001b10  shl     rax, 20h
0x180001b14  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b18  xor     rax, [rbp+var_10]
0x180001b1c  xor     rax, rcx
0x180001b1f  mov     rcx, 0FFFFFFFFFFFFh
0x180001b29  and     rax, rcx
0x180001b2c  mov     rcx, 2B992DDFA233h
0x180001b36  cmp     rax, rbx
0x180001b39  cmovz   rax, rcx
0x180001b3d  mov     cs:__security_cookie, rax
0x180001b44  mov     rbx, [rsp+30h+arg_10]
0x180001b49  not     rax
0x180001b4c  mov     cs:__security_cookie_complement, rax
0x180001b53  add     rsp, 30h
0x180001b57  pop     rbp
0x180001b58  retn
```
