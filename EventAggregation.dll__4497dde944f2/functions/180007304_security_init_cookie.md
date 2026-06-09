# __security_init_cookie

- ea: `0x180007304`
- end: `0x1800073b9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007290`

## callees

- `0x180007304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007347`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007347`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007353`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007353`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007363`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007363`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007339`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180007339`

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
0x180007304  mov     [rsp-8+arg_10], rbx
0x180007309  push    rbp
0x18000730a  mov     rbp, rsp
0x18000730d  sub     rsp, 30h
0x180007311  mov     rax, cs:__security_cookie
0x180007318  mov     rbx, 2B992DDFA232h
0x180007322  cmp     rax, rbx
0x180007325  jnz     short loc_1800073A4
0x180007327  xor     eax, eax
0x180007329  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000732d  mov     [rbp+var_10], rax
0x180007331  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180007335  mov     qword ptr [rbp+PerformanceCount], rax
0x180007339  call    cs:__imp_GetSystemTimeAsFileTime
0x18000733f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180007343  mov     [rbp+var_10], rax
0x180007347  call    cs:__imp_GetCurrentThreadId
0x18000734d  mov     eax, eax
0x18000734f  xor     [rbp+var_10], rax
0x180007353  call    cs:__imp_GetCurrentProcessId
0x180007359  mov     eax, eax
0x18000735b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000735f  xor     [rbp+var_10], rax
0x180007363  call    cs:__imp_QueryPerformanceCounter
0x180007369  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000736c  lea     rcx, [rbp+var_10]
0x180007370  shl     rax, 20h
0x180007374  xor     rax, qword ptr [rbp+PerformanceCount]
0x180007378  xor     rax, [rbp+var_10]
0x18000737c  xor     rax, rcx
0x18000737f  mov     rcx, 0FFFFFFFFFFFFh
0x180007389  and     rax, rcx
0x18000738c  mov     rcx, 2B992DDFA233h
0x180007396  cmp     rax, rbx
0x180007399  cmovz   rax, rcx
0x18000739d  mov     cs:__security_cookie, rax
0x1800073a4  mov     rbx, [rsp+30h+arg_10]
0x1800073a9  not     rax
0x1800073ac  mov     cs:__security_cookie_complement, rax
0x1800073b3  add     rsp, 30h
0x1800073b7  pop     rbp
0x1800073b8  retn
```
