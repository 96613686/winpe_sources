# __security_init_cookie

- ea: `0x18000356c`
- end: `0x180003621`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003100`

## callees

- `0x18000356c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800035bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800035bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800035cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800035cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800035a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800035a1`

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
0x18000356c  mov     [rsp-8+arg_10], rbx
0x180003571  push    rbp
0x180003572  mov     rbp, rsp
0x180003575  sub     rsp, 30h
0x180003579  mov     rax, cs:__security_cookie
0x180003580  mov     rbx, 2B992DDFA232h
0x18000358a  cmp     rax, rbx
0x18000358d  jnz     short loc_18000360C
0x18000358f  xor     eax, eax
0x180003591  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003595  mov     [rbp+var_10], rax
0x180003599  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000359d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800035a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800035a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800035ab  mov     [rbp+var_10], rax
0x1800035af  call    cs:__imp_GetCurrentThreadId
0x1800035b5  mov     eax, eax
0x1800035b7  xor     [rbp+var_10], rax
0x1800035bb  call    cs:__imp_GetCurrentProcessId
0x1800035c1  mov     eax, eax
0x1800035c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800035c7  xor     [rbp+var_10], rax
0x1800035cb  call    cs:__imp_QueryPerformanceCounter
0x1800035d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800035d4  lea     rcx, [rbp+var_10]
0x1800035d8  shl     rax, 20h
0x1800035dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800035e0  xor     rax, [rbp+var_10]
0x1800035e4  xor     rax, rcx
0x1800035e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800035f1  and     rax, rcx
0x1800035f4  mov     rcx, 2B992DDFA233h
0x1800035fe  cmp     rax, rbx
0x180003601  cmovz   rax, rcx
0x180003605  mov     cs:__security_cookie, rax
0x18000360c  mov     rbx, [rsp+30h+arg_10]
0x180003611  not     rax
0x180003614  mov     cs:__security_cookie_complement, rax
0x18000361b  add     rsp, 30h
0x18000361f  pop     rbp
0x180003620  retn
```
