# __security_init_cookie

- ea: `0x180001bf0`
- end: `0x180001ca5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001430`

## callees

- `0x180001bf0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c25`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c25`
- `KERNEL32!GetCurrentThreadId` at `0x180001c33`
- `KERNEL32!GetCurrentThreadId` at `0x180001c33`
- `KERNEL32!GetCurrentProcessId` at `0x180001c3f`
- `KERNEL32!GetCurrentProcessId` at `0x180001c3f`
- `KERNEL32!QueryPerformanceCounter` at `0x180001c4f`
- `KERNEL32!QueryPerformanceCounter` at `0x180001c4f`

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
0x180001bf0  mov     [rsp-8+arg_10], rbx
0x180001bf5  push    rbp
0x180001bf6  mov     rbp, rsp
0x180001bf9  sub     rsp, 30h
0x180001bfd  mov     rax, cs:__security_cookie
0x180001c04  mov     rbx, 2B992DDFA232h
0x180001c0e  cmp     rax, rbx
0x180001c11  jnz     short loc_180001C90
0x180001c13  xor     eax, eax
0x180001c15  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001c19  mov     [rbp+var_10], rax
0x180001c1d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001c21  mov     qword ptr [rbp+PerformanceCount], rax
0x180001c25  call    cs:__imp_GetSystemTimeAsFileTime
0x180001c2b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001c2f  mov     [rbp+var_10], rax
0x180001c33  call    cs:__imp_GetCurrentThreadId
0x180001c39  mov     eax, eax
0x180001c3b  xor     [rbp+var_10], rax
0x180001c3f  call    cs:__imp_GetCurrentProcessId
0x180001c45  mov     eax, eax
0x180001c47  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c4b  xor     [rbp+var_10], rax
0x180001c4f  call    cs:__imp_QueryPerformanceCounter
0x180001c55  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c58  lea     rcx, [rbp+var_10]
0x180001c5c  shl     rax, 20h
0x180001c60  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001c64  xor     rax, [rbp+var_10]
0x180001c68  xor     rax, rcx
0x180001c6b  mov     rcx, 0FFFFFFFFFFFFh
0x180001c75  and     rax, rcx
0x180001c78  mov     rcx, 2B992DDFA233h
0x180001c82  cmp     rax, rbx
0x180001c85  cmovz   rax, rcx
0x180001c89  mov     cs:__security_cookie, rax
0x180001c90  mov     rbx, [rsp+30h+arg_10]
0x180001c95  not     rax
0x180001c98  mov     cs:__security_cookie_complement, rax
0x180001c9f  add     rsp, 30h
0x180001ca3  pop     rbp
0x180001ca4  retn
```
