# __security_init_cookie

- ea: `0x180002334`
- end: `0x180002411`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c30`

## callees

- `0x180002334`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800023be`
- `KERNEL32!QueryPerformanceCounter` at `0x1800023be`
- `KERNEL32!GetCurrentProcessId` at `0x18000237b`
- `KERNEL32!GetCurrentProcessId` at `0x18000237b`
- `KERNEL32!GetCurrentThreadId` at `0x180002387`
- `KERNEL32!GetCurrentThreadId` at `0x180002387`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000236d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000236d`
- `KERNEL32!GetTickCount` at `0x180002393`
- `KERNEL32!GetTickCount` at `0x1800023a3`
- `KERNEL32!GetTickCount` at `0x180002393`
- `KERNEL32!GetTickCount` at `0x1800023a3`

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
0x180002334  mov     [rsp-8+arg_18], rbx
0x180002339  push    rbp
0x18000233a  mov     rbp, rsp
0x18000233d  sub     rsp, 20h
0x180002341  xor     eax, eax
0x180002343  mov     rbx, 2B992DDFA232h
0x18000234d  mov     [rbp+arg_0], rax
0x180002351  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002355  mov     qword ptr [rbp+PerformanceCount], rax
0x180002359  mov     rax, cs:__security_cookie
0x180002360  cmp     rax, rbx
0x180002363  jnz     loc_1800023FC
0x180002369  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000236d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002373  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002377  mov     [rbp+arg_0], rax
0x18000237b  call    cs:__imp_GetCurrentProcessId
0x180002381  mov     eax, eax
0x180002383  xor     [rbp+arg_0], rax
0x180002387  call    cs:__imp_GetCurrentThreadId
0x18000238d  mov     eax, eax
0x18000238f  xor     [rbp+arg_0], rax
0x180002393  call    cs:__imp_GetTickCount
0x180002399  mov     eax, eax
0x18000239b  shl     rax, 18h
0x18000239f  xor     [rbp+arg_0], rax
0x1800023a3  call    cs:__imp_GetTickCount
0x1800023a9  mov     eax, eax
0x1800023ab  lea     rcx, [rbp+arg_0]
0x1800023af  xor     rax, [rbp+arg_0]
0x1800023b3  xor     rax, rcx
0x1800023b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800023ba  mov     [rbp+arg_0], rax
0x1800023be  call    cs:__imp_QueryPerformanceCounter
0x1800023c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800023c7  mov     rcx, 0FFFFFFFFFFFFh
0x1800023d1  shl     rax, 20h
0x1800023d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800023d9  xor     rax, [rbp+arg_0]
0x1800023dd  and     rax, rcx
0x1800023e0  mov     rcx, rax
0x1800023e3  cmp     rax, rbx
0x1800023e6  jnz     short loc_1800023F5
0x1800023e8  mov     rax, 2B992DDFA233h
0x1800023f2  mov     rcx, rax
0x1800023f5  mov     cs:__security_cookie, rcx
0x1800023fc  mov     rbx, [rsp+20h+arg_18]
0x180002401  not     rax
0x180002404  mov     cs:__security_cookie_complement, rax
0x18000240b  add     rsp, 20h
0x18000240f  pop     rbp
0x180002410  retn
```
