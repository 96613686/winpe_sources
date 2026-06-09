# __security_init_cookie

- ea: `0x14000179c`
- end: `0x140001851`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001430`

## callees

- `0x14000179c`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400017d1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400017d1`
- `KERNEL32!QueryPerformanceCounter` at `0x1400017fb`
- `KERNEL32!QueryPerformanceCounter` at `0x1400017fb`
- `KERNEL32!GetCurrentProcessId` at `0x1400017eb`
- `KERNEL32!GetCurrentProcessId` at `0x1400017eb`
- `KERNEL32!GetCurrentThreadId` at `0x1400017df`
- `KERNEL32!GetCurrentThreadId` at `0x1400017df`

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
0x14000179c  mov     [rsp-8+arg_10], rbx
0x1400017a1  push    rbp
0x1400017a2  mov     rbp, rsp
0x1400017a5  sub     rsp, 30h
0x1400017a9  mov     rax, cs:__security_cookie
0x1400017b0  mov     rbx, 2B992DDFA232h
0x1400017ba  cmp     rax, rbx
0x1400017bd  jnz     short loc_14000183C
0x1400017bf  xor     eax, eax
0x1400017c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400017c5  mov     [rbp+var_10], rax
0x1400017c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400017cd  mov     qword ptr [rbp+PerformanceCount], rax
0x1400017d1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400017d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400017db  mov     [rbp+var_10], rax
0x1400017df  call    cs:__imp_GetCurrentThreadId
0x1400017e5  mov     eax, eax
0x1400017e7  xor     [rbp+var_10], rax
0x1400017eb  call    cs:__imp_GetCurrentProcessId
0x1400017f1  mov     eax, eax
0x1400017f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400017f7  xor     [rbp+var_10], rax
0x1400017fb  call    cs:__imp_QueryPerformanceCounter
0x140001801  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001804  lea     rcx, [rbp+var_10]
0x140001808  shl     rax, 20h
0x14000180c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001810  xor     rax, [rbp+var_10]
0x140001814  xor     rax, rcx
0x140001817  mov     rcx, 0FFFFFFFFFFFFh
0x140001821  and     rax, rcx
0x140001824  mov     rcx, 2B992DDFA233h
0x14000182e  cmp     rax, rbx
0x140001831  cmovz   rax, rcx
0x140001835  mov     cs:__security_cookie, rax
0x14000183c  mov     rbx, [rsp+30h+arg_10]
0x140001841  not     rax
0x140001844  mov     cs:__security_cookie_complement, rax
0x14000184b  add     rsp, 30h
0x14000184f  pop     rbp
0x140001850  retn
```
