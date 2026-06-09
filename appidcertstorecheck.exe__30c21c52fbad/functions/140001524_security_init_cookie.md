# __security_init_cookie

- ea: `0x140001524`
- end: `0x140001601`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400012f0`

## callees

- `0x140001524`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000155d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000155d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001583`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001593`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001583`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001593`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400015ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400015ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001577`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000156b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000156b`

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
0x140001524  mov     [rsp-8+arg_18], rbx
0x140001529  push    rbp
0x14000152a  mov     rbp, rsp
0x14000152d  sub     rsp, 20h
0x140001531  xor     eax, eax
0x140001533  mov     rbx, 2B992DDFA232h
0x14000153d  mov     [rbp+arg_0], rax
0x140001541  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001545  mov     qword ptr [rbp+PerformanceCount], rax
0x140001549  mov     rax, cs:__security_cookie
0x140001550  cmp     rax, rbx
0x140001553  jnz     loc_1400015EC
0x140001559  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000155d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001563  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001567  mov     [rbp+arg_0], rax
0x14000156b  call    cs:__imp_GetCurrentProcessId
0x140001571  mov     eax, eax
0x140001573  xor     [rbp+arg_0], rax
0x140001577  call    cs:__imp_GetCurrentThreadId
0x14000157d  mov     eax, eax
0x14000157f  xor     [rbp+arg_0], rax
0x140001583  call    cs:__imp_GetTickCount
0x140001589  mov     eax, eax
0x14000158b  shl     rax, 18h
0x14000158f  xor     [rbp+arg_0], rax
0x140001593  call    cs:__imp_GetTickCount
0x140001599  mov     eax, eax
0x14000159b  lea     rcx, [rbp+arg_0]
0x14000159f  xor     rax, [rbp+arg_0]
0x1400015a3  xor     rax, rcx
0x1400015a6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400015aa  mov     [rbp+arg_0], rax
0x1400015ae  call    cs:__imp_QueryPerformanceCounter
0x1400015b4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400015b7  mov     rcx, 0FFFFFFFFFFFFh
0x1400015c1  shl     rax, 20h
0x1400015c5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400015c9  xor     rax, [rbp+arg_0]
0x1400015cd  and     rax, rcx
0x1400015d0  mov     rcx, rax
0x1400015d3  cmp     rax, rbx
0x1400015d6  jnz     short loc_1400015E5
0x1400015d8  mov     rax, 2B992DDFA233h
0x1400015e2  mov     rcx, rax
0x1400015e5  mov     cs:__security_cookie, rcx
0x1400015ec  mov     rbx, [rsp+20h+arg_18]
0x1400015f1  not     rax
0x1400015f4  mov     cs:__security_cookie_complement, rax
0x1400015fb  add     rsp, 20h
0x1400015ff  pop     rbp
0x140001600  retn
```
