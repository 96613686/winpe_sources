# __security_init_cookie

- ea: `0x180019b84`
- end: `0x180019c39`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018fa0`

## callees

- `0x180019b84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019bc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019bd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019bd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019bb9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019bb9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019be3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019be3`

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
0x180019b84  mov     [rsp-8+arg_10], rbx
0x180019b89  push    rbp
0x180019b8a  mov     rbp, rsp
0x180019b8d  sub     rsp, 30h
0x180019b91  mov     rax, cs:__security_cookie
0x180019b98  mov     rbx, 2B992DDFA232h
0x180019ba2  cmp     rax, rbx
0x180019ba5  jnz     short loc_180019C24
0x180019ba7  xor     eax, eax
0x180019ba9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019bad  mov     [rbp+var_10], rax
0x180019bb1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180019bb5  mov     qword ptr [rbp+PerformanceCount], rax
0x180019bb9  call    cs:__imp_GetSystemTimeAsFileTime
0x180019bbf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180019bc3  mov     [rbp+var_10], rax
0x180019bc7  call    cs:__imp_GetCurrentThreadId
0x180019bcd  mov     eax, eax
0x180019bcf  xor     [rbp+var_10], rax
0x180019bd3  call    cs:__imp_GetCurrentProcessId
0x180019bd9  mov     eax, eax
0x180019bdb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180019bdf  xor     [rbp+var_10], rax
0x180019be3  call    cs:__imp_QueryPerformanceCounter
0x180019be9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180019bec  lea     rcx, [rbp+var_10]
0x180019bf0  shl     rax, 20h
0x180019bf4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180019bf8  xor     rax, [rbp+var_10]
0x180019bfc  xor     rax, rcx
0x180019bff  mov     rcx, 0FFFFFFFFFFFFh
0x180019c09  and     rax, rcx
0x180019c0c  mov     rcx, 2B992DDFA233h
0x180019c16  cmp     rax, rbx
0x180019c19  cmovz   rax, rcx
0x180019c1d  mov     cs:__security_cookie, rax
0x180019c24  mov     rbx, [rsp+30h+arg_10]
0x180019c29  not     rax
0x180019c2c  mov     cs:__security_cookie_complement, rax
0x180019c33  add     rsp, 30h
0x180019c37  pop     rbp
0x180019c38  retn
```
