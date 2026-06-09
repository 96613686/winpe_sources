# __security_init_cookie

- ea: `0x180001bbc`
- end: `0x180001c71`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001760`

## callees

- `0x180001bbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001c0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001c0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001bff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001bff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001bf1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001bf1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c1b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c1b`

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
0x180001bbc  mov     [rsp-8+arg_10], rbx
0x180001bc1  push    rbp
0x180001bc2  mov     rbp, rsp
0x180001bc5  sub     rsp, 30h
0x180001bc9  mov     rax, cs:__security_cookie
0x180001bd0  mov     rbx, 2B992DDFA232h
0x180001bda  cmp     rax, rbx
0x180001bdd  jnz     short loc_180001C5C
0x180001bdf  xor     eax, eax
0x180001be1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001be5  mov     [rbp+var_10], rax
0x180001be9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001bed  mov     qword ptr [rbp+PerformanceCount], rax
0x180001bf1  call    cs:__imp_GetSystemTimeAsFileTime
0x180001bf7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001bfb  mov     [rbp+var_10], rax
0x180001bff  call    cs:__imp_GetCurrentThreadId
0x180001c05  mov     eax, eax
0x180001c07  xor     [rbp+var_10], rax
0x180001c0b  call    cs:__imp_GetCurrentProcessId
0x180001c11  mov     eax, eax
0x180001c13  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c17  xor     [rbp+var_10], rax
0x180001c1b  call    cs:__imp_QueryPerformanceCounter
0x180001c21  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c24  lea     rcx, [rbp+var_10]
0x180001c28  shl     rax, 20h
0x180001c2c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001c30  xor     rax, [rbp+var_10]
0x180001c34  xor     rax, rcx
0x180001c37  mov     rcx, 0FFFFFFFFFFFFh
0x180001c41  and     rax, rcx
0x180001c44  mov     rcx, 2B992DDFA233h
0x180001c4e  cmp     rax, rbx
0x180001c51  cmovz   rax, rcx
0x180001c55  mov     cs:__security_cookie, rax
0x180001c5c  mov     rbx, [rsp+30h+arg_10]
0x180001c61  not     rax
0x180001c64  mov     cs:__security_cookie_complement, rax
0x180001c6b  add     rsp, 30h
0x180001c6f  pop     rbp
0x180001c70  retn
```
