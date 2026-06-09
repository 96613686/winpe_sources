# __security_init_cookie

- ea: `0x180022c44`
- end: `0x180022d21`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012b64`
- `0x180022930`

## callees

- `0x180022c44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022c97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022c97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022c8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022c8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022ca3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022cb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022ca3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180022cb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022c7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022c7d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022cce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022cce`

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
0x180022c44  mov     [rsp-8+arg_18], rbx
0x180022c49  push    rbp
0x180022c4a  mov     rbp, rsp
0x180022c4d  sub     rsp, 20h
0x180022c51  xor     eax, eax
0x180022c53  mov     rbx, 2B992DDFA232h
0x180022c5d  mov     [rbp+arg_0], rax
0x180022c61  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180022c65  mov     qword ptr [rbp+PerformanceCount], rax
0x180022c69  mov     rax, cs:__security_cookie
0x180022c70  cmp     rax, rbx
0x180022c73  jnz     loc_180022D0C
0x180022c79  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180022c7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180022c83  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180022c87  mov     [rbp+arg_0], rax
0x180022c8b  call    cs:__imp_GetCurrentProcessId
0x180022c91  mov     eax, eax
0x180022c93  xor     [rbp+arg_0], rax
0x180022c97  call    cs:__imp_GetCurrentThreadId
0x180022c9d  mov     eax, eax
0x180022c9f  xor     [rbp+arg_0], rax
0x180022ca3  call    cs:__imp_GetTickCount
0x180022ca9  mov     eax, eax
0x180022cab  shl     rax, 18h
0x180022caf  xor     [rbp+arg_0], rax
0x180022cb3  call    cs:__imp_GetTickCount
0x180022cb9  mov     eax, eax
0x180022cbb  lea     rcx, [rbp+arg_0]
0x180022cbf  xor     rax, [rbp+arg_0]
0x180022cc3  xor     rax, rcx
0x180022cc6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180022cca  mov     [rbp+arg_0], rax
0x180022cce  call    cs:__imp_QueryPerformanceCounter
0x180022cd4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180022cd7  mov     rcx, 0FFFFFFFFFFFFh
0x180022ce1  shl     rax, 20h
0x180022ce5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180022ce9  xor     rax, [rbp+arg_0]
0x180022ced  and     rax, rcx
0x180022cf0  mov     rcx, rax
0x180022cf3  cmp     rax, rbx
0x180022cf6  jnz     short loc_180022D05
0x180022cf8  mov     rax, 2B992DDFA233h
0x180022d02  mov     rcx, rax
0x180022d05  mov     cs:__security_cookie, rcx
0x180022d0c  mov     rbx, [rsp+20h+arg_18]
0x180022d11  not     rax
0x180022d14  mov     cs:__security_cookie_complement, rax
0x180022d1b  add     rsp, 20h
0x180022d1f  pop     rbp
0x180022d20  retn
```
