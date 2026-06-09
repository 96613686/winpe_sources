# __security_init_cookie

- ea: `0x140002bb0`
- end: `0x140002c65`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400028e0`

## callees

- `0x140002bb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002bff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002bff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002bf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002bf3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002c0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002c0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002be5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002be5`

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
0x140002bb0  mov     [rsp-8+arg_10], rbx
0x140002bb5  push    rbp
0x140002bb6  mov     rbp, rsp
0x140002bb9  sub     rsp, 30h
0x140002bbd  mov     rax, cs:__security_cookie
0x140002bc4  mov     rbx, 2B992DDFA232h
0x140002bce  cmp     rax, rbx
0x140002bd1  jnz     short loc_140002C50
0x140002bd3  xor     eax, eax
0x140002bd5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002bd9  mov     [rbp+var_10], rax
0x140002bdd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002be1  mov     qword ptr [rbp+PerformanceCount], rax
0x140002be5  call    cs:__imp_GetSystemTimeAsFileTime
0x140002beb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002bef  mov     [rbp+var_10], rax
0x140002bf3  call    cs:__imp_GetCurrentThreadId
0x140002bf9  mov     eax, eax
0x140002bfb  xor     [rbp+var_10], rax
0x140002bff  call    cs:__imp_GetCurrentProcessId
0x140002c05  mov     eax, eax
0x140002c07  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002c0b  xor     [rbp+var_10], rax
0x140002c0f  call    cs:__imp_QueryPerformanceCounter
0x140002c15  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002c18  lea     rcx, [rbp+var_10]
0x140002c1c  shl     rax, 20h
0x140002c20  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002c24  xor     rax, [rbp+var_10]
0x140002c28  xor     rax, rcx
0x140002c2b  mov     rcx, 0FFFFFFFFFFFFh
0x140002c35  and     rax, rcx
0x140002c38  mov     rcx, 2B992DDFA233h
0x140002c42  cmp     rax, rbx
0x140002c45  cmovz   rax, rcx
0x140002c49  mov     cs:__security_cookie, rax
0x140002c50  mov     rbx, [rsp+30h+arg_10]
0x140002c55  not     rax
0x140002c58  mov     cs:__security_cookie_complement, rax
0x140002c5f  add     rsp, 30h
0x140002c63  pop     rbp
0x140002c64  retn
```
