# __security_init_cookie

- ea: `0x18000be68`
- end: `0x18000bf1d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b8a0`

## callees

- `0x18000be68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000beab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000beab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000beb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000beb7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000bec7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000bec7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000be9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000be9d`

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
0x18000be68  mov     [rsp-8+arg_10], rbx
0x18000be6d  push    rbp
0x18000be6e  mov     rbp, rsp
0x18000be71  sub     rsp, 30h
0x18000be75  mov     rax, cs:__security_cookie
0x18000be7c  mov     rbx, 2B992DDFA232h
0x18000be86  cmp     rax, rbx
0x18000be89  jnz     short loc_18000BF08
0x18000be8b  xor     eax, eax
0x18000be8d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000be91  mov     [rbp+var_10], rax
0x18000be95  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000be99  mov     qword ptr [rbp+PerformanceCount], rax
0x18000be9d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000bea3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000bea7  mov     [rbp+var_10], rax
0x18000beab  call    cs:__imp_GetCurrentThreadId
0x18000beb1  mov     eax, eax
0x18000beb3  xor     [rbp+var_10], rax
0x18000beb7  call    cs:__imp_GetCurrentProcessId
0x18000bebd  mov     eax, eax
0x18000bebf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000bec3  xor     [rbp+var_10], rax
0x18000bec7  call    cs:__imp_QueryPerformanceCounter
0x18000becd  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000bed0  lea     rcx, [rbp+var_10]
0x18000bed4  shl     rax, 20h
0x18000bed8  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000bedc  xor     rax, [rbp+var_10]
0x18000bee0  xor     rax, rcx
0x18000bee3  mov     rcx, 0FFFFFFFFFFFFh
0x18000beed  and     rax, rcx
0x18000bef0  mov     rcx, 2B992DDFA233h
0x18000befa  cmp     rax, rbx
0x18000befd  cmovz   rax, rcx
0x18000bf01  mov     cs:__security_cookie, rax
0x18000bf08  mov     rbx, [rsp+30h+arg_10]
0x18000bf0d  not     rax
0x18000bf10  mov     cs:__security_cookie_complement, rax
0x18000bf17  add     rsp, 30h
0x18000bf1b  pop     rbp
0x18000bf1c  retn
```
