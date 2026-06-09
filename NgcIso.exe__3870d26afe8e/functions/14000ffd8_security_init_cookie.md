# __security_init_cookie

- ea: `0x14000ffd8`
- end: `0x14001008d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f670`

## callees

- `0x14000ffd8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001001b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001001b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010027`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010027`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140010037`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140010037`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001000d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001000d`

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
0x14000ffd8  mov     [rsp-8+arg_10], rbx
0x14000ffdd  push    rbp
0x14000ffde  mov     rbp, rsp
0x14000ffe1  sub     rsp, 30h
0x14000ffe5  mov     rax, cs:__security_cookie
0x14000ffec  mov     rbx, 2B992DDFA232h
0x14000fff6  cmp     rax, rbx
0x14000fff9  jnz     short loc_140010078
0x14000fffb  xor     eax, eax
0x14000fffd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140010001  mov     [rbp+var_10], rax
0x140010005  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140010009  mov     qword ptr [rbp+PerformanceCount], rax
0x14001000d  call    cs:__imp_GetSystemTimeAsFileTime
0x140010013  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140010017  mov     [rbp+var_10], rax
0x14001001b  call    cs:__imp_GetCurrentThreadId
0x140010021  mov     eax, eax
0x140010023  xor     [rbp+var_10], rax
0x140010027  call    cs:__imp_GetCurrentProcessId
0x14001002d  mov     eax, eax
0x14001002f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140010033  xor     [rbp+var_10], rax
0x140010037  call    cs:__imp_QueryPerformanceCounter
0x14001003d  mov     eax, dword ptr [rbp+PerformanceCount]
0x140010040  lea     rcx, [rbp+var_10]
0x140010044  shl     rax, 20h
0x140010048  xor     rax, qword ptr [rbp+PerformanceCount]
0x14001004c  xor     rax, [rbp+var_10]
0x140010050  xor     rax, rcx
0x140010053  mov     rcx, 0FFFFFFFFFFFFh
0x14001005d  and     rax, rcx
0x140010060  mov     rcx, 2B992DDFA233h
0x14001006a  cmp     rax, rbx
0x14001006d  cmovz   rax, rcx
0x140010071  mov     cs:__security_cookie, rax
0x140010078  mov     rbx, [rsp+30h+arg_10]
0x14001007d  not     rax
0x140010080  mov     cs:__security_cookie_complement, rax
0x140010087  add     rsp, 30h
0x14001008b  pop     rbp
0x14001008c  retn
```
