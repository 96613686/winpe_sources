# __security_init_cookie

- ea: `0x1800026f4`
- end: `0x1800027d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800020f0`

## callees

- `0x1800026f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000273b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000273b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002747`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000277e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000277e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002753`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002763`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002753`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002763`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000272d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000272d`

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
0x1800026f4  mov     [rsp-8+arg_18], rbx
0x1800026f9  push    rbp
0x1800026fa  mov     rbp, rsp
0x1800026fd  sub     rsp, 20h
0x180002701  xor     eax, eax
0x180002703  mov     rbx, 2B992DDFA232h
0x18000270d  mov     [rbp+arg_0], rax
0x180002711  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002715  mov     qword ptr [rbp+PerformanceCount], rax
0x180002719  mov     rax, cs:__security_cookie
0x180002720  cmp     rax, rbx
0x180002723  jnz     loc_1800027BC
0x180002729  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000272d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002733  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002737  mov     [rbp+arg_0], rax
0x18000273b  call    cs:__imp_GetCurrentProcessId
0x180002741  mov     eax, eax
0x180002743  xor     [rbp+arg_0], rax
0x180002747  call    cs:__imp_GetCurrentThreadId
0x18000274d  mov     eax, eax
0x18000274f  xor     [rbp+arg_0], rax
0x180002753  call    cs:__imp_GetTickCount
0x180002759  mov     eax, eax
0x18000275b  shl     rax, 18h
0x18000275f  xor     [rbp+arg_0], rax
0x180002763  call    cs:__imp_GetTickCount
0x180002769  mov     eax, eax
0x18000276b  lea     rcx, [rbp+arg_0]
0x18000276f  xor     rax, [rbp+arg_0]
0x180002773  xor     rax, rcx
0x180002776  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000277a  mov     [rbp+arg_0], rax
0x18000277e  call    cs:__imp_QueryPerformanceCounter
0x180002784  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002787  mov     rcx, 0FFFFFFFFFFFFh
0x180002791  shl     rax, 20h
0x180002795  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002799  xor     rax, [rbp+arg_0]
0x18000279d  and     rax, rcx
0x1800027a0  mov     rcx, rax
0x1800027a3  cmp     rax, rbx
0x1800027a6  jnz     short loc_1800027B5
0x1800027a8  mov     rax, 2B992DDFA233h
0x1800027b2  mov     rcx, rax
0x1800027b5  mov     cs:__security_cookie, rcx
0x1800027bc  mov     rbx, [rsp+20h+arg_18]
0x1800027c1  not     rax
0x1800027c4  mov     cs:__security_cookie_complement, rax
0x1800027cb  add     rsp, 20h
0x1800027cf  pop     rbp
0x1800027d0  retn
```
