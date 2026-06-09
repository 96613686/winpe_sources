# __security_init_cookie

- ea: `0x1800020a4`
- end: `0x180002181`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a50`

## callees

- `0x1800020a4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800020f7`
- `KERNEL32!GetCurrentThreadId` at `0x1800020f7`
- `KERNEL32!GetCurrentProcessId` at `0x1800020eb`
- `KERNEL32!GetCurrentProcessId` at `0x1800020eb`
- `KERNEL32!QueryPerformanceCounter` at `0x18000212e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000212e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800020dd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800020dd`
- `KERNEL32!GetTickCount` at `0x180002103`
- `KERNEL32!GetTickCount` at `0x180002113`
- `KERNEL32!GetTickCount` at `0x180002103`
- `KERNEL32!GetTickCount` at `0x180002113`

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
0x1800020a4  mov     [rsp-8+arg_18], rbx
0x1800020a9  push    rbp
0x1800020aa  mov     rbp, rsp
0x1800020ad  sub     rsp, 20h
0x1800020b1  xor     eax, eax
0x1800020b3  mov     rbx, 2B992DDFA232h
0x1800020bd  mov     [rbp+arg_0], rax
0x1800020c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800020c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800020c9  mov     rax, cs:__security_cookie
0x1800020d0  cmp     rax, rbx
0x1800020d3  jnz     loc_18000216C
0x1800020d9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800020dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800020e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800020e7  mov     [rbp+arg_0], rax
0x1800020eb  call    cs:__imp_GetCurrentProcessId
0x1800020f1  mov     eax, eax
0x1800020f3  xor     [rbp+arg_0], rax
0x1800020f7  call    cs:__imp_GetCurrentThreadId
0x1800020fd  mov     eax, eax
0x1800020ff  xor     [rbp+arg_0], rax
0x180002103  call    cs:__imp_GetTickCount
0x180002109  mov     eax, eax
0x18000210b  shl     rax, 18h
0x18000210f  xor     [rbp+arg_0], rax
0x180002113  call    cs:__imp_GetTickCount
0x180002119  mov     eax, eax
0x18000211b  lea     rcx, [rbp+arg_0]
0x18000211f  xor     rax, [rbp+arg_0]
0x180002123  xor     rax, rcx
0x180002126  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000212a  mov     [rbp+arg_0], rax
0x18000212e  call    cs:__imp_QueryPerformanceCounter
0x180002134  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002137  mov     rcx, 0FFFFFFFFFFFFh
0x180002141  shl     rax, 20h
0x180002145  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002149  xor     rax, [rbp+arg_0]
0x18000214d  and     rax, rcx
0x180002150  mov     rcx, rax
0x180002153  cmp     rax, rbx
0x180002156  jnz     short loc_180002165
0x180002158  mov     rax, 2B992DDFA233h
0x180002162  mov     rcx, rax
0x180002165  mov     cs:__security_cookie, rcx
0x18000216c  mov     rbx, [rsp+20h+arg_18]
0x180002171  not     rax
0x180002174  mov     cs:__security_cookie_complement, rax
0x18000217b  add     rsp, 20h
0x18000217f  pop     rbp
0x180002180  retn
```
