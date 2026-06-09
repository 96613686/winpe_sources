# __security_init_cookie

- ea: `0x180045370`
- end: `0x180045425`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180044ee0`

## callees

- `0x180045370`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800453bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800453bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800453b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800453b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800453a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800453a5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800453cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800453cf`

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
0x180045370  mov     [rsp-8+arg_10], rbx
0x180045375  push    rbp
0x180045376  mov     rbp, rsp
0x180045379  sub     rsp, 30h
0x18004537d  mov     rax, cs:__security_cookie
0x180045384  mov     rbx, 2B992DDFA232h
0x18004538e  cmp     rax, rbx
0x180045391  jnz     short loc_180045410
0x180045393  xor     eax, eax
0x180045395  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180045399  mov     [rbp+var_10], rax
0x18004539d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800453a1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800453a5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800453ab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800453af  mov     [rbp+var_10], rax
0x1800453b3  call    cs:__imp_GetCurrentThreadId
0x1800453b9  mov     eax, eax
0x1800453bb  xor     [rbp+var_10], rax
0x1800453bf  call    cs:__imp_GetCurrentProcessId
0x1800453c5  mov     eax, eax
0x1800453c7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800453cb  xor     [rbp+var_10], rax
0x1800453cf  call    cs:__imp_QueryPerformanceCounter
0x1800453d5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800453d8  lea     rcx, [rbp+var_10]
0x1800453dc  shl     rax, 20h
0x1800453e0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800453e4  xor     rax, [rbp+var_10]
0x1800453e8  xor     rax, rcx
0x1800453eb  mov     rcx, 0FFFFFFFFFFFFh
0x1800453f5  and     rax, rcx
0x1800453f8  mov     rcx, 2B992DDFA233h
0x180045402  cmp     rax, rbx
0x180045405  cmovz   rax, rcx
0x180045409  mov     cs:__security_cookie, rax
0x180045410  mov     rbx, [rsp+30h+arg_10]
0x180045415  not     rax
0x180045418  mov     cs:__security_cookie_complement, rax
0x18004541f  add     rsp, 30h
0x180045423  pop     rbp
0x180045424  retn
```
