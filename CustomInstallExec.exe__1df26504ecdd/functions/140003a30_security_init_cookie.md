# __security_init_cookie

- ea: `0x140003a30`
- end: `0x140003ae5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003380`

## callees

- `0x140003a30`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003a7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003a73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003a73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003a65`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003a65`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140003a8f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140003a8f`

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
0x140003a30  mov     [rsp-8+arg_10], rbx
0x140003a35  push    rbp
0x140003a36  mov     rbp, rsp
0x140003a39  sub     rsp, 30h
0x140003a3d  mov     rax, cs:__security_cookie
0x140003a44  mov     rbx, 2B992DDFA232h
0x140003a4e  cmp     rax, rbx
0x140003a51  jnz     short loc_140003AD0
0x140003a53  xor     eax, eax
0x140003a55  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003a59  mov     [rbp+var_10], rax
0x140003a5d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140003a61  mov     qword ptr [rbp+PerformanceCount], rax
0x140003a65  call    cs:__imp_GetSystemTimeAsFileTime
0x140003a6b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140003a6f  mov     [rbp+var_10], rax
0x140003a73  call    cs:__imp_GetCurrentThreadId
0x140003a79  mov     eax, eax
0x140003a7b  xor     [rbp+var_10], rax
0x140003a7f  call    cs:__imp_GetCurrentProcessId
0x140003a85  mov     eax, eax
0x140003a87  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140003a8b  xor     [rbp+var_10], rax
0x140003a8f  call    cs:__imp_QueryPerformanceCounter
0x140003a95  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003a98  lea     rcx, [rbp+var_10]
0x140003a9c  shl     rax, 20h
0x140003aa0  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003aa4  xor     rax, [rbp+var_10]
0x140003aa8  xor     rax, rcx
0x140003aab  mov     rcx, 0FFFFFFFFFFFFh
0x140003ab5  and     rax, rcx
0x140003ab8  mov     rcx, 2B992DDFA233h
0x140003ac2  cmp     rax, rbx
0x140003ac5  cmovz   rax, rcx
0x140003ac9  mov     cs:__security_cookie, rax
0x140003ad0  mov     rbx, [rsp+30h+arg_10]
0x140003ad5  not     rax
0x140003ad8  mov     cs:__security_cookie_complement, rax
0x140003adf  add     rsp, 30h
0x140003ae3  pop     rbp
0x140003ae4  retn
```
