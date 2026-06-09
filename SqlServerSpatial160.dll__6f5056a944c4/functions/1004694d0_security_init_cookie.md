# __security_init_cookie

- ea: `0x1004694d0`
- end: `0x10046957c`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100468eec`

## callees

- `0x1004694d0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x100469526`
- `KERNEL32!QueryPerformanceCounter` at `0x100469526`
- `KERNEL32!GetCurrentProcessId` at `0x100469516`
- `KERNEL32!GetCurrentProcessId` at `0x100469516`
- `KERNEL32!GetCurrentThreadId` at `0x10046950a`
- `KERNEL32!GetCurrentThreadId` at `0x10046950a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1004694fc`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1004694fc`

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
0x1004694d0  mov     [rsp-8+arg_18], rbx
0x1004694d5  push    rbp
0x1004694d6  mov     rbp, rsp
0x1004694d9  sub     rsp, 20h
0x1004694dd  mov     rax, cs:__security_cookie
0x1004694e4  mov     rbx, 2B992DDFA232h
0x1004694ee  cmp     rax, rbx
0x1004694f1  jnz     short loc_100469567
0x1004694f3  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1004694f8  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1004694fc  call    cs:__imp_GetSystemTimeAsFileTime
0x100469502  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x100469506  mov     [rbp+arg_0], rax
0x10046950a  call    cs:__imp_GetCurrentThreadId
0x100469510  mov     eax, eax
0x100469512  xor     [rbp+arg_0], rax
0x100469516  call    cs:__imp_GetCurrentProcessId
0x10046951c  mov     eax, eax
0x10046951e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x100469522  xor     [rbp+arg_0], rax
0x100469526  call    cs:__imp_QueryPerformanceCounter
0x10046952c  mov     eax, dword ptr [rbp+PerformanceCount]
0x10046952f  lea     rcx, [rbp+arg_0]
0x100469533  shl     rax, 20h
0x100469537  xor     rax, qword ptr [rbp+PerformanceCount]
0x10046953b  xor     rax, [rbp+arg_0]
0x10046953f  xor     rax, rcx
0x100469542  mov     rcx, 0FFFFFFFFFFFFh
0x10046954c  and     rax, rcx
0x10046954f  mov     rcx, 2B992DDFA233h
0x100469559  cmp     rax, rbx
0x10046955c  cmovz   rax, rcx
0x100469560  mov     cs:__security_cookie, rax
0x100469567  mov     rbx, [rsp+20h+arg_18]
0x10046956c  not     rax
0x10046956f  mov     cs:__security_cookie_complement, rax
0x100469576  add     rsp, 20h
0x10046957a  pop     rbp
0x10046957b  retn
```
