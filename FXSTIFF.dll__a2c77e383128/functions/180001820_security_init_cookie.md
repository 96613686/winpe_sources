# __security_init_cookie

- ea: `0x180001820`
- end: `0x1800018fd`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014c0`

## callees

- `0x180001820`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001859`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001859`
- `KERNEL32!GetTickCount` at `0x18000187f`
- `KERNEL32!GetTickCount` at `0x18000188f`
- `KERNEL32!GetTickCount` at `0x18000187f`
- `KERNEL32!GetTickCount` at `0x18000188f`
- `KERNEL32!GetCurrentProcessId` at `0x180001867`
- `KERNEL32!GetCurrentProcessId` at `0x180001867`
- `KERNEL32!GetCurrentThreadId` at `0x180001873`
- `KERNEL32!GetCurrentThreadId` at `0x180001873`
- `KERNEL32!QueryPerformanceCounter` at `0x1800018aa`
- `KERNEL32!QueryPerformanceCounter` at `0x1800018aa`

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
0x180001820  mov     [rsp-8+arg_18], rbx
0x180001825  push    rbp
0x180001826  mov     rbp, rsp
0x180001829  sub     rsp, 20h
0x18000182d  xor     eax, eax
0x18000182f  mov     rbx, 2B992DDFA232h
0x180001839  mov     [rbp+arg_0], rax
0x18000183d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001841  mov     qword ptr [rbp+PerformanceCount], rax
0x180001845  mov     rax, cs:__security_cookie
0x18000184c  cmp     rax, rbx
0x18000184f  jnz     loc_1800018E8
0x180001855  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001859  call    cs:__imp_GetSystemTimeAsFileTime
0x18000185f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001863  mov     [rbp+arg_0], rax
0x180001867  call    cs:__imp_GetCurrentProcessId
0x18000186d  mov     eax, eax
0x18000186f  xor     [rbp+arg_0], rax
0x180001873  call    cs:__imp_GetCurrentThreadId
0x180001879  mov     eax, eax
0x18000187b  xor     [rbp+arg_0], rax
0x18000187f  call    cs:__imp_GetTickCount
0x180001885  mov     eax, eax
0x180001887  shl     rax, 18h
0x18000188b  xor     [rbp+arg_0], rax
0x18000188f  call    cs:__imp_GetTickCount
0x180001895  mov     eax, eax
0x180001897  lea     rcx, [rbp+arg_0]
0x18000189b  xor     rax, [rbp+arg_0]
0x18000189f  xor     rax, rcx
0x1800018a2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800018a6  mov     [rbp+arg_0], rax
0x1800018aa  call    cs:__imp_QueryPerformanceCounter
0x1800018b0  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800018b3  mov     rcx, 0FFFFFFFFFFFFh
0x1800018bd  shl     rax, 20h
0x1800018c1  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800018c5  xor     rax, [rbp+arg_0]
0x1800018c9  and     rax, rcx
0x1800018cc  mov     rcx, rax
0x1800018cf  cmp     rax, rbx
0x1800018d2  jnz     short loc_1800018E1
0x1800018d4  mov     rax, 2B992DDFA233h
0x1800018de  mov     rcx, rax
0x1800018e1  mov     cs:__security_cookie, rcx
0x1800018e8  mov     rbx, [rsp+20h+arg_18]
0x1800018ed  not     rax
0x1800018f0  mov     cs:__security_cookie_complement, rax
0x1800018f7  add     rsp, 20h
0x1800018fb  pop     rbp
0x1800018fc  retn
```
