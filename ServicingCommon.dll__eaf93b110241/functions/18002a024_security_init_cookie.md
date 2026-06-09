# __security_init_cookie

- ea: `0x18002a024`
- end: `0x18002a0d9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029350`

## callees

- `0x18002a024`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002a067`
- `KERNEL32!GetCurrentThreadId` at `0x18002a067`
- `KERNEL32!GetCurrentProcessId` at `0x18002a073`
- `KERNEL32!GetCurrentProcessId` at `0x18002a073`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002a059`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002a059`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a083`
- `KERNEL32!QueryPerformanceCounter` at `0x18002a083`

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
0x18002a024  mov     [rsp-8+arg_10], rbx
0x18002a029  push    rbp
0x18002a02a  mov     rbp, rsp
0x18002a02d  sub     rsp, 30h
0x18002a031  mov     rax, cs:__security_cookie
0x18002a038  mov     rbx, 2B992DDFA232h
0x18002a042  cmp     rax, rbx
0x18002a045  jnz     short loc_18002A0C4
0x18002a047  xor     eax, eax
0x18002a049  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002a04d  mov     [rbp+var_10], rax
0x18002a051  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002a055  mov     qword ptr [rbp+PerformanceCount], rax
0x18002a059  call    cs:__imp_GetSystemTimeAsFileTime
0x18002a05f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002a063  mov     [rbp+var_10], rax
0x18002a067  call    cs:__imp_GetCurrentThreadId
0x18002a06d  mov     eax, eax
0x18002a06f  xor     [rbp+var_10], rax
0x18002a073  call    cs:__imp_GetCurrentProcessId
0x18002a079  mov     eax, eax
0x18002a07b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002a07f  xor     [rbp+var_10], rax
0x18002a083  call    cs:__imp_QueryPerformanceCounter
0x18002a089  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002a08c  lea     rcx, [rbp+var_10]
0x18002a090  shl     rax, 20h
0x18002a094  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002a098  xor     rax, [rbp+var_10]
0x18002a09c  xor     rax, rcx
0x18002a09f  mov     rcx, 0FFFFFFFFFFFFh
0x18002a0a9  and     rax, rcx
0x18002a0ac  mov     rcx, 2B992DDFA233h
0x18002a0b6  cmp     rax, rbx
0x18002a0b9  cmovz   rax, rcx
0x18002a0bd  mov     cs:__security_cookie, rax
0x18002a0c4  mov     rbx, [rsp+30h+arg_10]
0x18002a0c9  not     rax
0x18002a0cc  mov     cs:__security_cookie_complement, rax
0x18002a0d3  add     rsp, 30h
0x18002a0d7  pop     rbp
0x18002a0d8  retn
```
