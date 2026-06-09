# __security_init_cookie

- ea: `0x18000397c`
- end: `0x180003a28`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800035b0`

## callees

- `0x18000397c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800039b6`
- `KERNEL32!GetCurrentThreadId` at `0x1800039b6`
- `KERNEL32!GetCurrentProcessId` at `0x1800039c2`
- `KERNEL32!GetCurrentProcessId` at `0x1800039c2`
- `KERNEL32!QueryPerformanceCounter` at `0x1800039d2`
- `KERNEL32!QueryPerformanceCounter` at `0x1800039d2`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800039a8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800039a8`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x18000397c  mov     [rsp-8+arg_18], rbx
0x180003981  push    rbp
0x180003982  mov     rbp, rsp
0x180003985  sub     rsp, 20h
0x180003989  mov     rax, cs:__security_cookie
0x180003990  mov     rbx, 2B992DDFA232h
0x18000399a  cmp     rax, rbx
0x18000399d  jnz     short loc_180003A13
0x18000399f  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800039a4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800039a8  call    cs:__imp_GetSystemTimeAsFileTime
0x1800039ae  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800039b2  mov     [rbp+arg_0], rax
0x1800039b6  call    cs:__imp_GetCurrentThreadId
0x1800039bc  mov     eax, eax
0x1800039be  xor     [rbp+arg_0], rax
0x1800039c2  call    cs:__imp_GetCurrentProcessId
0x1800039c8  mov     eax, eax
0x1800039ca  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800039ce  xor     [rbp+arg_0], rax
0x1800039d2  call    cs:__imp_QueryPerformanceCounter
0x1800039d8  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800039db  lea     rcx, [rbp+arg_0]
0x1800039df  shl     rax, 20h
0x1800039e3  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800039e7  xor     rax, [rbp+arg_0]
0x1800039eb  xor     rax, rcx
0x1800039ee  mov     rcx, 0FFFFFFFFFFFFh
0x1800039f8  and     rax, rcx
0x1800039fb  mov     rcx, 2B992DDFA233h
0x180003a05  cmp     rax, rbx
0x180003a08  cmovz   rax, rcx
0x180003a0c  mov     cs:__security_cookie, rax
0x180003a13  mov     rbx, [rsp+20h+arg_18]
0x180003a18  not     rax
0x180003a1b  mov     cs:__security_cookie_complement, rax
0x180003a22  add     rsp, 20h
0x180003a26  pop     rbp
0x180003a27  retn
```
