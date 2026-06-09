# __security_init_cookie

- ea: `0x18004c634`
- end: `0x18004c711`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004bf00`

## callees

- `0x18004c634`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18004c6be`
- `KERNEL32!QueryPerformanceCounter` at `0x18004c6be`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004c66d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004c66d`
- `KERNEL32!GetTickCount` at `0x18004c693`
- `KERNEL32!GetTickCount` at `0x18004c6a3`
- `KERNEL32!GetTickCount` at `0x18004c693`
- `KERNEL32!GetTickCount` at `0x18004c6a3`
- `KERNEL32!GetCurrentThreadId` at `0x18004c687`
- `KERNEL32!GetCurrentThreadId` at `0x18004c687`
- `KERNEL32!GetCurrentProcessId` at `0x18004c67b`
- `KERNEL32!GetCurrentProcessId` at `0x18004c67b`

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
0x18004c634  mov     [rsp-8+arg_18], rbx
0x18004c639  push    rbp
0x18004c63a  mov     rbp, rsp
0x18004c63d  sub     rsp, 20h
0x18004c641  xor     eax, eax
0x18004c643  mov     rbx, 2B992DDFA232h
0x18004c64d  mov     [rbp+arg_0], rax
0x18004c651  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004c655  mov     qword ptr [rbp+PerformanceCount], rax
0x18004c659  mov     rax, cs:__security_cookie
0x18004c660  cmp     rax, rbx
0x18004c663  jnz     loc_18004C6FC
0x18004c669  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004c66d  call    cs:__imp_GetSystemTimeAsFileTime
0x18004c673  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004c677  mov     [rbp+arg_0], rax
0x18004c67b  call    cs:__imp_GetCurrentProcessId
0x18004c681  mov     eax, eax
0x18004c683  xor     [rbp+arg_0], rax
0x18004c687  call    cs:__imp_GetCurrentThreadId
0x18004c68d  mov     eax, eax
0x18004c68f  xor     [rbp+arg_0], rax
0x18004c693  call    cs:__imp_GetTickCount
0x18004c699  mov     eax, eax
0x18004c69b  shl     rax, 18h
0x18004c69f  xor     [rbp+arg_0], rax
0x18004c6a3  call    cs:__imp_GetTickCount
0x18004c6a9  mov     eax, eax
0x18004c6ab  lea     rcx, [rbp+arg_0]
0x18004c6af  xor     rax, [rbp+arg_0]
0x18004c6b3  xor     rax, rcx
0x18004c6b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004c6ba  mov     [rbp+arg_0], rax
0x18004c6be  call    cs:__imp_QueryPerformanceCounter
0x18004c6c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004c6c7  mov     rcx, 0FFFFFFFFFFFFh
0x18004c6d1  shl     rax, 20h
0x18004c6d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004c6d9  xor     rax, [rbp+arg_0]
0x18004c6dd  and     rax, rcx
0x18004c6e0  mov     rcx, rax
0x18004c6e3  cmp     rax, rbx
0x18004c6e6  jnz     short loc_18004C6F5
0x18004c6e8  mov     rax, 2B992DDFA233h
0x18004c6f2  mov     rcx, rax
0x18004c6f5  mov     cs:__security_cookie, rcx
0x18004c6fc  mov     rbx, [rsp+20h+arg_18]
0x18004c701  not     rax
0x18004c704  mov     cs:__security_cookie_complement, rax
0x18004c70b  add     rsp, 20h
0x18004c70f  pop     rbp
0x18004c710  retn
```
