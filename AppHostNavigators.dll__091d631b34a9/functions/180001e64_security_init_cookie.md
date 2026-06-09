# __security_init_cookie

- ea: `0x180001e64`
- end: `0x180001f41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001460`

## callees

- `0x180001e64`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001eee`
- `KERNEL32!QueryPerformanceCounter` at `0x180001eee`
- `KERNEL32!GetCurrentProcessId` at `0x180001eab`
- `KERNEL32!GetCurrentProcessId` at `0x180001eab`
- `KERNEL32!GetCurrentThreadId` at `0x180001eb7`
- `KERNEL32!GetCurrentThreadId` at `0x180001eb7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e9d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e9d`
- `KERNEL32!GetTickCount` at `0x180001ec3`
- `KERNEL32!GetTickCount` at `0x180001ed3`
- `KERNEL32!GetTickCount` at `0x180001ec3`
- `KERNEL32!GetTickCount` at `0x180001ed3`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001e64  mov     [rsp-8+arg_18], rbx
0x180001e69  push    rbp
0x180001e6a  mov     rbp, rsp
0x180001e6d  sub     rsp, 20h
0x180001e71  xor     eax, eax
0x180001e73  mov     rbx, 2B992DDFA232h
0x180001e7d  mov     [rbp+arg_0], rax
0x180001e81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001e85  mov     qword ptr [rbp+PerformanceCount], rax
0x180001e89  mov     rax, cs:__security_cookie
0x180001e90  cmp     rax, rbx
0x180001e93  jnz     loc_180001F2C
0x180001e99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001e9d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ea3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ea7  mov     [rbp+arg_0], rax
0x180001eab  call    cs:__imp_GetCurrentProcessId
0x180001eb1  mov     eax, eax
0x180001eb3  xor     [rbp+arg_0], rax
0x180001eb7  call    cs:__imp_GetCurrentThreadId
0x180001ebd  mov     eax, eax
0x180001ebf  xor     [rbp+arg_0], rax
0x180001ec3  call    cs:__imp_GetTickCount
0x180001ec9  mov     eax, eax
0x180001ecb  shl     rax, 18h
0x180001ecf  xor     [rbp+arg_0], rax
0x180001ed3  call    cs:__imp_GetTickCount
0x180001ed9  mov     eax, eax
0x180001edb  lea     rcx, [rbp+arg_0]
0x180001edf  xor     rax, [rbp+arg_0]
0x180001ee3  xor     rax, rcx
0x180001ee6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001eea  mov     [rbp+arg_0], rax
0x180001eee  call    cs:__imp_QueryPerformanceCounter
0x180001ef4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ef7  mov     rcx, 0FFFFFFFFFFFFh
0x180001f01  shl     rax, 20h
0x180001f05  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f09  xor     rax, [rbp+arg_0]
0x180001f0d  and     rax, rcx
0x180001f10  mov     rcx, rax
0x180001f13  cmp     rax, rbx
0x180001f16  jnz     short loc_180001F25
0x180001f18  mov     rax, 2B992DDFA233h
0x180001f22  mov     rcx, rax
0x180001f25  mov     cs:__security_cookie, rcx
0x180001f2c  mov     rbx, [rsp+20h+arg_18]
0x180001f31  not     rax
0x180001f34  mov     cs:__security_cookie_complement, rax
0x180001f3b  add     rsp, 20h
0x180001f3f  pop     rbp
0x180001f40  retn
```
