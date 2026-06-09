# __security_init_cookie

- ea: `0x18001f1d4`
- end: `0x18001f2b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001ea80`

## callees

- `0x18001f1d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f227`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f21b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f21b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f20d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001f20d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f233`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f243`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f233`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001f243`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f25e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001f25e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x18001f1d4  mov     [rsp-8+arg_18], rbx
0x18001f1d9  push    rbp
0x18001f1da  mov     rbp, rsp
0x18001f1dd  sub     rsp, 20h
0x18001f1e1  xor     eax, eax
0x18001f1e3  mov     rbx, 2B992DDFA232h
0x18001f1ed  mov     [rbp+arg_0], rax
0x18001f1f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001f1f5  mov     qword ptr [rbp+PerformanceCount], rax
0x18001f1f9  mov     rax, cs:__security_cookie
0x18001f200  cmp     rax, rbx
0x18001f203  jnz     loc_18001F29C
0x18001f209  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001f20d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001f213  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001f217  mov     [rbp+arg_0], rax
0x18001f21b  call    cs:__imp_GetCurrentProcessId
0x18001f221  mov     eax, eax
0x18001f223  xor     [rbp+arg_0], rax
0x18001f227  call    cs:__imp_GetCurrentThreadId
0x18001f22d  mov     eax, eax
0x18001f22f  xor     [rbp+arg_0], rax
0x18001f233  call    cs:__imp_GetTickCount
0x18001f239  mov     eax, eax
0x18001f23b  shl     rax, 18h
0x18001f23f  xor     [rbp+arg_0], rax
0x18001f243  call    cs:__imp_GetTickCount
0x18001f249  mov     eax, eax
0x18001f24b  lea     rcx, [rbp+arg_0]
0x18001f24f  xor     rax, [rbp+arg_0]
0x18001f253  xor     rax, rcx
0x18001f256  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001f25a  mov     [rbp+arg_0], rax
0x18001f25e  call    cs:__imp_QueryPerformanceCounter
0x18001f264  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001f267  mov     rcx, 0FFFFFFFFFFFFh
0x18001f271  shl     rax, 20h
0x18001f275  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001f279  xor     rax, [rbp+arg_0]
0x18001f27d  and     rax, rcx
0x18001f280  mov     rcx, rax
0x18001f283  cmp     rax, rbx
0x18001f286  jnz     short loc_18001F295
0x18001f288  mov     rax, 2B992DDFA233h
0x18001f292  mov     rcx, rax
0x18001f295  mov     cs:__security_cookie, rcx
0x18001f29c  mov     rbx, [rsp+20h+arg_18]
0x18001f2a1  not     rax
0x18001f2a4  mov     cs:__security_cookie_complement, rax
0x18001f2ab  add     rsp, 20h
0x18001f2af  pop     rbp
0x18001f2b0  retn
```
