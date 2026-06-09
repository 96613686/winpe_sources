# __security_init_cookie

- ea: `0x180078054`
- end: `0x180078109`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078010`

## callees

- `0x180078054`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800780b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800780b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800780a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800780a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180078097`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180078097`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180078089`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180078089`

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
0x180078054  mov     [rsp-8+arg_10], rbx
0x180078059  push    rbp
0x18007805a  mov     rbp, rsp
0x18007805d  sub     rsp, 30h
0x180078061  mov     rax, cs:__security_cookie
0x180078068  mov     rbx, 2B992DDFA232h
0x180078072  cmp     rax, rbx
0x180078075  jnz     short loc_1800780F4
0x180078077  xor     eax, eax
0x180078079  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007807d  mov     [rbp+var_10], rax
0x180078081  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180078085  mov     qword ptr [rbp+PerformanceCount], rax
0x180078089  call    cs:__imp_GetSystemTimeAsFileTime
0x18007808f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180078093  mov     [rbp+var_10], rax
0x180078097  call    cs:__imp_GetCurrentThreadId
0x18007809d  mov     eax, eax
0x18007809f  xor     [rbp+var_10], rax
0x1800780a3  call    cs:__imp_GetCurrentProcessId
0x1800780a9  mov     eax, eax
0x1800780ab  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800780af  xor     [rbp+var_10], rax
0x1800780b3  call    cs:__imp_QueryPerformanceCounter
0x1800780b9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800780bc  lea     rcx, [rbp+var_10]
0x1800780c0  shl     rax, 20h
0x1800780c4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800780c8  xor     rax, [rbp+var_10]
0x1800780cc  xor     rax, rcx
0x1800780cf  mov     rcx, 0FFFFFFFFFFFFh
0x1800780d9  and     rax, rcx
0x1800780dc  mov     rcx, 2B992DDFA233h
0x1800780e6  cmp     rax, rbx
0x1800780e9  cmovz   rax, rcx
0x1800780ed  mov     cs:__security_cookie, rax
0x1800780f4  mov     rbx, [rsp+30h+arg_10]
0x1800780f9  not     rax
0x1800780fc  mov     cs:__security_cookie_complement, rax
0x180078103  add     rsp, 30h
0x180078107  pop     rbp
0x180078108  retn
```
