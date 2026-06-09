# __security_init_cookie

- ea: `0x1800049c4`
- end: `0x180004aa1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800049c4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004a4e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004a4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004a0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004a0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a17`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800049fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800049fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004a23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004a33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004a23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004a33`

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
0x1800049c4  mov     [rsp-8+arg_18], rbx
0x1800049c9  push    rbp
0x1800049ca  mov     rbp, rsp
0x1800049cd  sub     rsp, 20h
0x1800049d1  xor     eax, eax
0x1800049d3  mov     rbx, 2B992DDFA232h
0x1800049dd  mov     [rbp+arg_0], rax
0x1800049e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800049e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800049e9  mov     rax, cs:__security_cookie
0x1800049f0  cmp     rax, rbx
0x1800049f3  jnz     loc_180004A8C
0x1800049f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800049fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180004a03  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004a07  mov     [rbp+arg_0], rax
0x180004a0b  call    cs:__imp_GetCurrentProcessId
0x180004a11  mov     eax, eax
0x180004a13  xor     [rbp+arg_0], rax
0x180004a17  call    cs:__imp_GetCurrentThreadId
0x180004a1d  mov     eax, eax
0x180004a1f  xor     [rbp+arg_0], rax
0x180004a23  call    cs:__imp_GetTickCount
0x180004a29  mov     eax, eax
0x180004a2b  shl     rax, 18h
0x180004a2f  xor     [rbp+arg_0], rax
0x180004a33  call    cs:__imp_GetTickCount
0x180004a39  mov     eax, eax
0x180004a3b  lea     rcx, [rbp+arg_0]
0x180004a3f  xor     rax, [rbp+arg_0]
0x180004a43  xor     rax, rcx
0x180004a46  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004a4a  mov     [rbp+arg_0], rax
0x180004a4e  call    cs:__imp_QueryPerformanceCounter
0x180004a54  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004a57  mov     rcx, 0FFFFFFFFFFFFh
0x180004a61  shl     rax, 20h
0x180004a65  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004a69  xor     rax, [rbp+arg_0]
0x180004a6d  and     rax, rcx
0x180004a70  mov     rcx, rax
0x180004a73  cmp     rax, rbx
0x180004a76  jnz     short loc_180004A85
0x180004a78  mov     rax, 2B992DDFA233h
0x180004a82  mov     rcx, rax
0x180004a85  mov     cs:__security_cookie, rcx
0x180004a8c  mov     rbx, [rsp+20h+arg_18]
0x180004a91  not     rax
0x180004a94  mov     cs:__security_cookie_complement, rax
0x180004a9b  add     rsp, 20h
0x180004a9f  pop     rbp
0x180004aa0  retn
```
