# __security_init_cookie

- ea: `0x18001fa58`
- end: `0x18001fb0d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f600`

## callees

- `0x18001fa58`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001fa8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001fa8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001faa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001faa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fa9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001fa9b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001fab7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001fab7`

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
0x18001fa58  mov     [rsp-8+arg_10], rbx
0x18001fa5d  push    rbp
0x18001fa5e  mov     rbp, rsp
0x18001fa61  sub     rsp, 30h
0x18001fa65  mov     rax, cs:__security_cookie
0x18001fa6c  mov     rbx, 2B992DDFA232h
0x18001fa76  cmp     rax, rbx
0x18001fa79  jnz     short loc_18001FAF8
0x18001fa7b  xor     eax, eax
0x18001fa7d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001fa81  mov     [rbp+var_10], rax
0x18001fa85  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001fa89  mov     qword ptr [rbp+PerformanceCount], rax
0x18001fa8d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001fa93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001fa97  mov     [rbp+var_10], rax
0x18001fa9b  call    cs:__imp_GetCurrentThreadId
0x18001faa1  mov     eax, eax
0x18001faa3  xor     [rbp+var_10], rax
0x18001faa7  call    cs:__imp_GetCurrentProcessId
0x18001faad  mov     eax, eax
0x18001faaf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001fab3  xor     [rbp+var_10], rax
0x18001fab7  call    cs:__imp_QueryPerformanceCounter
0x18001fabd  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001fac0  lea     rcx, [rbp+var_10]
0x18001fac4  shl     rax, 20h
0x18001fac8  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001facc  xor     rax, [rbp+var_10]
0x18001fad0  xor     rax, rcx
0x18001fad3  mov     rcx, 0FFFFFFFFFFFFh
0x18001fadd  and     rax, rcx
0x18001fae0  mov     rcx, 2B992DDFA233h
0x18001faea  cmp     rax, rbx
0x18001faed  cmovz   rax, rcx
0x18001faf1  mov     cs:__security_cookie, rax
0x18001faf8  mov     rbx, [rsp+30h+arg_10]
0x18001fafd  not     rax
0x18001fb00  mov     cs:__security_cookie_complement, rax
0x18001fb07  add     rsp, 30h
0x18001fb0b  pop     rbp
0x18001fb0c  retn
```
