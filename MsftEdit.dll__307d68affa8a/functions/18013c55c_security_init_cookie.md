# __security_init_cookie

- ea: `0x18013c55c`
- end: `0x18013c611`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18013ba80`

## callees

- `0x18013c55c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013c59f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18013c59f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18013c5ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18013c5ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18013c591`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18013c591`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18013c5bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18013c5bb`

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
0x18013c55c  mov     [rsp-8+arg_10], rbx
0x18013c561  push    rbp
0x18013c562  mov     rbp, rsp
0x18013c565  sub     rsp, 30h
0x18013c569  mov     rax, cs:__security_cookie
0x18013c570  mov     rbx, 2B992DDFA232h
0x18013c57a  cmp     rax, rbx
0x18013c57d  jnz     short loc_18013C5FC
0x18013c57f  xor     eax, eax
0x18013c581  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18013c585  mov     [rbp+var_10], rax
0x18013c589  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18013c58d  mov     qword ptr [rbp+PerformanceCount], rax
0x18013c591  call    cs:__imp_GetSystemTimeAsFileTime
0x18013c597  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18013c59b  mov     [rbp+var_10], rax
0x18013c59f  call    cs:__imp_GetCurrentThreadId
0x18013c5a5  mov     eax, eax
0x18013c5a7  xor     [rbp+var_10], rax
0x18013c5ab  call    cs:__imp_GetCurrentProcessId
0x18013c5b1  mov     eax, eax
0x18013c5b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18013c5b7  xor     [rbp+var_10], rax
0x18013c5bb  call    cs:__imp_QueryPerformanceCounter
0x18013c5c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18013c5c4  lea     rcx, [rbp+var_10]
0x18013c5c8  shl     rax, 20h
0x18013c5cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18013c5d0  xor     rax, [rbp+var_10]
0x18013c5d4  xor     rax, rcx
0x18013c5d7  mov     rcx, 0FFFFFFFFFFFFh
0x18013c5e1  and     rax, rcx
0x18013c5e4  mov     rcx, 2B992DDFA233h
0x18013c5ee  cmp     rax, rbx
0x18013c5f1  cmovz   rax, rcx
0x18013c5f5  mov     cs:__security_cookie, rax
0x18013c5fc  mov     rbx, [rsp+30h+arg_10]
0x18013c601  not     rax
0x18013c604  mov     cs:__security_cookie_complement, rax
0x18013c60b  add     rsp, 30h
0x18013c60f  pop     rbp
0x18013c610  retn
```
