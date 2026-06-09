# __security_init_cookie

- ea: `0x180002724`
- end: `0x180002801`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002120`

## callees

- `0x180002724`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000276b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000276b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002777`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002777`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800027ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800027ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002783`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002793`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002783`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002793`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000275d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000275d`

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
0x180002724  mov     [rsp-8+arg_18], rbx
0x180002729  push    rbp
0x18000272a  mov     rbp, rsp
0x18000272d  sub     rsp, 20h
0x180002731  xor     eax, eax
0x180002733  mov     rbx, 2B992DDFA232h
0x18000273d  mov     [rbp+arg_0], rax
0x180002741  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002745  mov     qword ptr [rbp+PerformanceCount], rax
0x180002749  mov     rax, cs:__security_cookie
0x180002750  cmp     rax, rbx
0x180002753  jnz     loc_1800027EC
0x180002759  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000275d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002763  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002767  mov     [rbp+arg_0], rax
0x18000276b  call    cs:__imp_GetCurrentProcessId
0x180002771  mov     eax, eax
0x180002773  xor     [rbp+arg_0], rax
0x180002777  call    cs:__imp_GetCurrentThreadId
0x18000277d  mov     eax, eax
0x18000277f  xor     [rbp+arg_0], rax
0x180002783  call    cs:__imp_GetTickCount
0x180002789  mov     eax, eax
0x18000278b  shl     rax, 18h
0x18000278f  xor     [rbp+arg_0], rax
0x180002793  call    cs:__imp_GetTickCount
0x180002799  mov     eax, eax
0x18000279b  lea     rcx, [rbp+arg_0]
0x18000279f  xor     rax, [rbp+arg_0]
0x1800027a3  xor     rax, rcx
0x1800027a6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800027aa  mov     [rbp+arg_0], rax
0x1800027ae  call    cs:__imp_QueryPerformanceCounter
0x1800027b4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800027b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800027c1  shl     rax, 20h
0x1800027c5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800027c9  xor     rax, [rbp+arg_0]
0x1800027cd  and     rax, rcx
0x1800027d0  mov     rcx, rax
0x1800027d3  cmp     rax, rbx
0x1800027d6  jnz     short loc_1800027E5
0x1800027d8  mov     rax, 2B992DDFA233h
0x1800027e2  mov     rcx, rax
0x1800027e5  mov     cs:__security_cookie, rcx
0x1800027ec  mov     rbx, [rsp+20h+arg_18]
0x1800027f1  not     rax
0x1800027f4  mov     cs:__security_cookie_complement, rax
0x1800027fb  add     rsp, 20h
0x1800027ff  pop     rbp
0x180002800  retn
```
