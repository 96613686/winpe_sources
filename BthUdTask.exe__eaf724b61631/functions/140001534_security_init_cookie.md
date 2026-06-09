# __security_init_cookie

- ea: `0x140001534`
- end: `0x140001611`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400012f0`

## callees

- `0x140001534`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140001593`
- `KERNEL32!GetTickCount` at `0x1400015a3`
- `KERNEL32!GetTickCount` at `0x140001593`
- `KERNEL32!GetTickCount` at `0x1400015a3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000156d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000156d`
- `KERNEL32!GetCurrentProcessId` at `0x14000157b`
- `KERNEL32!GetCurrentProcessId` at `0x14000157b`
- `KERNEL32!QueryPerformanceCounter` at `0x1400015be`
- `KERNEL32!QueryPerformanceCounter` at `0x1400015be`
- `KERNEL32!GetCurrentThreadId` at `0x140001587`
- `KERNEL32!GetCurrentThreadId` at `0x140001587`

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
0x140001534  mov     [rsp-8+arg_18], rbx
0x140001539  push    rbp
0x14000153a  mov     rbp, rsp
0x14000153d  sub     rsp, 20h
0x140001541  xor     eax, eax
0x140001543  mov     rbx, 2B992DDFA232h
0x14000154d  mov     [rbp+arg_0], rax
0x140001551  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001555  mov     qword ptr [rbp+PerformanceCount], rax
0x140001559  mov     rax, cs:__security_cookie
0x140001560  cmp     rax, rbx
0x140001563  jnz     loc_1400015FC
0x140001569  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000156d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001573  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001577  mov     [rbp+arg_0], rax
0x14000157b  call    cs:__imp_GetCurrentProcessId
0x140001581  mov     eax, eax
0x140001583  xor     [rbp+arg_0], rax
0x140001587  call    cs:__imp_GetCurrentThreadId
0x14000158d  mov     eax, eax
0x14000158f  xor     [rbp+arg_0], rax
0x140001593  call    cs:__imp_GetTickCount
0x140001599  mov     eax, eax
0x14000159b  shl     rax, 18h
0x14000159f  xor     [rbp+arg_0], rax
0x1400015a3  call    cs:__imp_GetTickCount
0x1400015a9  mov     eax, eax
0x1400015ab  lea     rcx, [rbp+arg_0]
0x1400015af  xor     rax, [rbp+arg_0]
0x1400015b3  xor     rax, rcx
0x1400015b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400015ba  mov     [rbp+arg_0], rax
0x1400015be  call    cs:__imp_QueryPerformanceCounter
0x1400015c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400015c7  mov     rcx, 0FFFFFFFFFFFFh
0x1400015d1  shl     rax, 20h
0x1400015d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400015d9  xor     rax, [rbp+arg_0]
0x1400015dd  and     rax, rcx
0x1400015e0  mov     rcx, rax
0x1400015e3  cmp     rax, rbx
0x1400015e6  jnz     short loc_1400015F5
0x1400015e8  mov     rax, 2B992DDFA233h
0x1400015f2  mov     rcx, rax
0x1400015f5  mov     cs:__security_cookie, rcx
0x1400015fc  mov     rbx, [rsp+20h+arg_18]
0x140001601  not     rax
0x140001604  mov     cs:__security_cookie_complement, rax
0x14000160b  add     rsp, 20h
0x14000160f  pop     rbp
0x140001610  retn
```
