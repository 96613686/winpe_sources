# __security_init_cookie

- ea: `0x180029a84`
- end: `0x180029b39`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029450`

## callees

- `0x180029a84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029ac7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029ac7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029ad3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180029ad3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029ab9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180029ab9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180029ae3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180029ae3`

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
0x180029a84  mov     [rsp-8+arg_10], rbx
0x180029a89  push    rbp
0x180029a8a  mov     rbp, rsp
0x180029a8d  sub     rsp, 30h
0x180029a91  mov     rax, cs:__security_cookie
0x180029a98  mov     rbx, 2B992DDFA232h
0x180029aa2  cmp     rax, rbx
0x180029aa5  jnz     short loc_180029B24
0x180029aa7  xor     eax, eax
0x180029aa9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180029aad  mov     [rbp+var_10], rax
0x180029ab1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180029ab5  mov     qword ptr [rbp+PerformanceCount], rax
0x180029ab9  call    cs:__imp_GetSystemTimeAsFileTime
0x180029abf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180029ac3  mov     [rbp+var_10], rax
0x180029ac7  call    cs:__imp_GetCurrentThreadId
0x180029acd  mov     eax, eax
0x180029acf  xor     [rbp+var_10], rax
0x180029ad3  call    cs:__imp_GetCurrentProcessId
0x180029ad9  mov     eax, eax
0x180029adb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180029adf  xor     [rbp+var_10], rax
0x180029ae3  call    cs:__imp_QueryPerformanceCounter
0x180029ae9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180029aec  lea     rcx, [rbp+var_10]
0x180029af0  shl     rax, 20h
0x180029af4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180029af8  xor     rax, [rbp+var_10]
0x180029afc  xor     rax, rcx
0x180029aff  mov     rcx, 0FFFFFFFFFFFFh
0x180029b09  and     rax, rcx
0x180029b0c  mov     rcx, 2B992DDFA233h
0x180029b16  cmp     rax, rbx
0x180029b19  cmovz   rax, rcx
0x180029b1d  mov     cs:__security_cookie, rax
0x180029b24  mov     rbx, [rsp+30h+arg_10]
0x180029b29  not     rax
0x180029b2c  mov     cs:__security_cookie_complement, rax
0x180029b33  add     rsp, 30h
0x180029b37  pop     rbp
0x180029b38  retn
```
