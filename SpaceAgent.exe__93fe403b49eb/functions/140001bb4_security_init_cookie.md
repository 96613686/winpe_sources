# __security_init_cookie

- ea: `0x140001bb4`
- end: `0x140001c91`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001600`

## callees

- `0x140001bb4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x140001c3e`
- `KERNEL32!QueryPerformanceCounter` at `0x140001c3e`
- `KERNEL32!GetCurrentProcessId` at `0x140001bfb`
- `KERNEL32!GetCurrentProcessId` at `0x140001bfb`
- `KERNEL32!GetCurrentThreadId` at `0x140001c07`
- `KERNEL32!GetCurrentThreadId` at `0x140001c07`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001bed`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001bed`
- `KERNEL32!GetTickCount` at `0x140001c13`
- `KERNEL32!GetTickCount` at `0x140001c23`
- `KERNEL32!GetTickCount` at `0x140001c13`
- `KERNEL32!GetTickCount` at `0x140001c23`

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
0x140001bb4  mov     [rsp-8+arg_18], rbx
0x140001bb9  push    rbp
0x140001bba  mov     rbp, rsp
0x140001bbd  sub     rsp, 20h
0x140001bc1  xor     eax, eax
0x140001bc3  mov     rbx, 2B992DDFA232h
0x140001bcd  mov     [rbp+arg_0], rax
0x140001bd1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001bd5  mov     qword ptr [rbp+PerformanceCount], rax
0x140001bd9  mov     rax, cs:__security_cookie
0x140001be0  cmp     rax, rbx
0x140001be3  jnz     loc_140001C7C
0x140001be9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001bed  call    cs:__imp_GetSystemTimeAsFileTime
0x140001bf3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001bf7  mov     [rbp+arg_0], rax
0x140001bfb  call    cs:__imp_GetCurrentProcessId
0x140001c01  mov     eax, eax
0x140001c03  xor     [rbp+arg_0], rax
0x140001c07  call    cs:__imp_GetCurrentThreadId
0x140001c0d  mov     eax, eax
0x140001c0f  xor     [rbp+arg_0], rax
0x140001c13  call    cs:__imp_GetTickCount
0x140001c19  mov     eax, eax
0x140001c1b  shl     rax, 18h
0x140001c1f  xor     [rbp+arg_0], rax
0x140001c23  call    cs:__imp_GetTickCount
0x140001c29  mov     eax, eax
0x140001c2b  lea     rcx, [rbp+arg_0]
0x140001c2f  xor     rax, [rbp+arg_0]
0x140001c33  xor     rax, rcx
0x140001c36  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001c3a  mov     [rbp+arg_0], rax
0x140001c3e  call    cs:__imp_QueryPerformanceCounter
0x140001c44  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001c47  mov     rcx, 0FFFFFFFFFFFFh
0x140001c51  shl     rax, 20h
0x140001c55  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001c59  xor     rax, [rbp+arg_0]
0x140001c5d  and     rax, rcx
0x140001c60  mov     rcx, rax
0x140001c63  cmp     rax, rbx
0x140001c66  jnz     short loc_140001C75
0x140001c68  mov     rax, 2B992DDFA233h
0x140001c72  mov     rcx, rax
0x140001c75  mov     cs:__security_cookie, rcx
0x140001c7c  mov     rbx, [rsp+20h+arg_18]
0x140001c81  not     rax
0x140001c84  mov     cs:__security_cookie_complement, rax
0x140001c8b  add     rsp, 20h
0x140001c8f  pop     rbp
0x140001c90  retn
```
