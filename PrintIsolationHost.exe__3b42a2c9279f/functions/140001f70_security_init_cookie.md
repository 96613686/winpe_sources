# __security_init_cookie

- ea: `0x140001f70`
- end: `0x140002025`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001ca0`

## callees

- `0x140001f70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001fb3`
- `KERNEL32!GetCurrentThreadId` at `0x140001fb3`
- `KERNEL32!GetCurrentProcessId` at `0x140001fbf`
- `KERNEL32!GetCurrentProcessId` at `0x140001fbf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001fa5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001fa5`
- `KERNEL32!QueryPerformanceCounter` at `0x140001fcf`
- `KERNEL32!QueryPerformanceCounter` at `0x140001fcf`

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
0x140001f70  mov     [rsp-8+arg_10], rbx
0x140001f75  push    rbp
0x140001f76  mov     rbp, rsp
0x140001f79  sub     rsp, 30h
0x140001f7d  mov     rax, cs:__security_cookie
0x140001f84  mov     rbx, 2B992DDFA232h
0x140001f8e  cmp     rax, rbx
0x140001f91  jnz     short loc_140002010
0x140001f93  xor     eax, eax
0x140001f95  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001f99  mov     [rbp+var_10], rax
0x140001f9d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001fa1  mov     qword ptr [rbp+PerformanceCount], rax
0x140001fa5  call    cs:__imp_GetSystemTimeAsFileTime
0x140001fab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001faf  mov     [rbp+var_10], rax
0x140001fb3  call    cs:__imp_GetCurrentThreadId
0x140001fb9  mov     eax, eax
0x140001fbb  xor     [rbp+var_10], rax
0x140001fbf  call    cs:__imp_GetCurrentProcessId
0x140001fc5  mov     eax, eax
0x140001fc7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001fcb  xor     [rbp+var_10], rax
0x140001fcf  call    cs:__imp_QueryPerformanceCounter
0x140001fd5  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001fd8  lea     rcx, [rbp+var_10]
0x140001fdc  shl     rax, 20h
0x140001fe0  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001fe4  xor     rax, [rbp+var_10]
0x140001fe8  xor     rax, rcx
0x140001feb  mov     rcx, 0FFFFFFFFFFFFh
0x140001ff5  and     rax, rcx
0x140001ff8  mov     rcx, 2B992DDFA233h
0x140002002  cmp     rax, rbx
0x140002005  cmovz   rax, rcx
0x140002009  mov     cs:__security_cookie, rax
0x140002010  mov     rbx, [rsp+30h+arg_10]
0x140002015  not     rax
0x140002018  mov     cs:__security_cookie_complement, rax
0x14000201f  add     rsp, 30h
0x140002023  pop     rbp
0x140002024  retn
```
