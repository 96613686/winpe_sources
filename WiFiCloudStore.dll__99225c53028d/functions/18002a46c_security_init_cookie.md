# __security_init_cookie

- ea: `0x18002a46c`
- end: `0x18002a521`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029fe0`

## callees

- `0x18002a46c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a4bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a4bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a4af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a4af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a4cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002a4cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a4a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002a4a1`

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
0x18002a46c  mov     [rsp-8+arg_10], rbx
0x18002a471  push    rbp
0x18002a472  mov     rbp, rsp
0x18002a475  sub     rsp, 30h
0x18002a479  mov     rax, cs:__security_cookie
0x18002a480  mov     rbx, 2B992DDFA232h
0x18002a48a  cmp     rax, rbx
0x18002a48d  jnz     short loc_18002A50C
0x18002a48f  xor     eax, eax
0x18002a491  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002a495  mov     [rbp+var_10], rax
0x18002a499  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002a49d  mov     qword ptr [rbp+PerformanceCount], rax
0x18002a4a1  call    cs:__imp_GetSystemTimeAsFileTime
0x18002a4a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002a4ab  mov     [rbp+var_10], rax
0x18002a4af  call    cs:__imp_GetCurrentThreadId
0x18002a4b5  mov     eax, eax
0x18002a4b7  xor     [rbp+var_10], rax
0x18002a4bb  call    cs:__imp_GetCurrentProcessId
0x18002a4c1  mov     eax, eax
0x18002a4c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002a4c7  xor     [rbp+var_10], rax
0x18002a4cb  call    cs:__imp_QueryPerformanceCounter
0x18002a4d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002a4d4  lea     rcx, [rbp+var_10]
0x18002a4d8  shl     rax, 20h
0x18002a4dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002a4e0  xor     rax, [rbp+var_10]
0x18002a4e4  xor     rax, rcx
0x18002a4e7  mov     rcx, 0FFFFFFFFFFFFh
0x18002a4f1  and     rax, rcx
0x18002a4f4  mov     rcx, 2B992DDFA233h
0x18002a4fe  cmp     rax, rbx
0x18002a501  cmovz   rax, rcx
0x18002a505  mov     cs:__security_cookie, rax
0x18002a50c  mov     rbx, [rsp+30h+arg_10]
0x18002a511  not     rax
0x18002a514  mov     cs:__security_cookie_complement, rax
0x18002a51b  add     rsp, 30h
0x18002a51f  pop     rbp
0x18002a520  retn
```
