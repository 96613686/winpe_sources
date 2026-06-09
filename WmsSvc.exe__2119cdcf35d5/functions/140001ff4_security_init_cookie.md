# __security_init_cookie

- ea: `0x140001ff4`
- end: `0x1400020d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400019f0`

## callees

- `0x140001ff4`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000203b`
- `KERNEL32!GetCurrentProcessId` at `0x14000203b`
- `KERNEL32!GetCurrentThreadId` at `0x140002047`
- `KERNEL32!GetCurrentThreadId` at `0x140002047`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000202d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000202d`
- `KERNEL32!GetTickCount` at `0x140002053`
- `KERNEL32!GetTickCount` at `0x140002063`
- `KERNEL32!GetTickCount` at `0x140002053`
- `KERNEL32!GetTickCount` at `0x140002063`
- `KERNEL32!QueryPerformanceCounter` at `0x14000207e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000207e`

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
0x140001ff4  mov     [rsp-8+arg_18], rbx
0x140001ff9  push    rbp
0x140001ffa  mov     rbp, rsp
0x140001ffd  sub     rsp, 20h
0x140002001  xor     eax, eax
0x140002003  mov     rbx, 2B992DDFA232h
0x14000200d  mov     [rbp+arg_0], rax
0x140002011  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002015  mov     qword ptr [rbp+PerformanceCount], rax
0x140002019  mov     rax, cs:__security_cookie
0x140002020  cmp     rax, rbx
0x140002023  jnz     loc_1400020BC
0x140002029  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000202d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002033  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002037  mov     [rbp+arg_0], rax
0x14000203b  call    cs:__imp_GetCurrentProcessId
0x140002041  mov     eax, eax
0x140002043  xor     [rbp+arg_0], rax
0x140002047  call    cs:__imp_GetCurrentThreadId
0x14000204d  mov     eax, eax
0x14000204f  xor     [rbp+arg_0], rax
0x140002053  call    cs:__imp_GetTickCount
0x140002059  mov     eax, eax
0x14000205b  shl     rax, 18h
0x14000205f  xor     [rbp+arg_0], rax
0x140002063  call    cs:__imp_GetTickCount
0x140002069  mov     eax, eax
0x14000206b  lea     rcx, [rbp+arg_0]
0x14000206f  xor     rax, [rbp+arg_0]
0x140002073  xor     rax, rcx
0x140002076  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000207a  mov     [rbp+arg_0], rax
0x14000207e  call    cs:__imp_QueryPerformanceCounter
0x140002084  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002087  mov     rcx, 0FFFFFFFFFFFFh
0x140002091  shl     rax, 20h
0x140002095  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002099  xor     rax, [rbp+arg_0]
0x14000209d  and     rax, rcx
0x1400020a0  mov     rcx, rax
0x1400020a3  cmp     rax, rbx
0x1400020a6  jnz     short loc_1400020B5
0x1400020a8  mov     rax, 2B992DDFA233h
0x1400020b2  mov     rcx, rax
0x1400020b5  mov     cs:__security_cookie, rcx
0x1400020bc  mov     rbx, [rsp+20h+arg_18]
0x1400020c1  not     rax
0x1400020c4  mov     cs:__security_cookie_complement, rax
0x1400020cb  add     rsp, 20h
0x1400020cf  pop     rbp
0x1400020d0  retn
```
