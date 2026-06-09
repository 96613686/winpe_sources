# __security_init_cookie

- ea: `0x180026a34`
- end: `0x180026b11`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026390`

## callees

- `0x180026a34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026a7b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180026a93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180026aa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180026a93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180026aa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026a6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026a6d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026abe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026abe`

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
0x180026a34  mov     [rsp-8+arg_18], rbx
0x180026a39  push    rbp
0x180026a3a  mov     rbp, rsp
0x180026a3d  sub     rsp, 20h
0x180026a41  xor     eax, eax
0x180026a43  mov     rbx, 2B992DDFA232h
0x180026a4d  mov     [rbp+arg_0], rax
0x180026a51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180026a55  mov     qword ptr [rbp+PerformanceCount], rax
0x180026a59  mov     rax, cs:__security_cookie
0x180026a60  cmp     rax, rbx
0x180026a63  jnz     loc_180026AFC
0x180026a69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180026a6d  call    cs:__imp_GetSystemTimeAsFileTime
0x180026a73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180026a77  mov     [rbp+arg_0], rax
0x180026a7b  call    cs:__imp_GetCurrentProcessId
0x180026a81  mov     eax, eax
0x180026a83  xor     [rbp+arg_0], rax
0x180026a87  call    cs:__imp_GetCurrentThreadId
0x180026a8d  mov     eax, eax
0x180026a8f  xor     [rbp+arg_0], rax
0x180026a93  call    cs:__imp_GetTickCount
0x180026a99  mov     eax, eax
0x180026a9b  shl     rax, 18h
0x180026a9f  xor     [rbp+arg_0], rax
0x180026aa3  call    cs:__imp_GetTickCount
0x180026aa9  mov     eax, eax
0x180026aab  lea     rcx, [rbp+arg_0]
0x180026aaf  xor     rax, [rbp+arg_0]
0x180026ab3  xor     rax, rcx
0x180026ab6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180026aba  mov     [rbp+arg_0], rax
0x180026abe  call    cs:__imp_QueryPerformanceCounter
0x180026ac4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180026ac7  mov     rcx, 0FFFFFFFFFFFFh
0x180026ad1  shl     rax, 20h
0x180026ad5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180026ad9  xor     rax, [rbp+arg_0]
0x180026add  and     rax, rcx
0x180026ae0  mov     rcx, rax
0x180026ae3  cmp     rax, rbx
0x180026ae6  jnz     short loc_180026AF5
0x180026ae8  mov     rax, 2B992DDFA233h
0x180026af2  mov     rcx, rax
0x180026af5  mov     cs:__security_cookie, rcx
0x180026afc  mov     rbx, [rsp+20h+arg_18]
0x180026b01  not     rax
0x180026b04  mov     cs:__security_cookie_complement, rax
0x180026b0b  add     rsp, 20h
0x180026b0f  pop     rbp
0x180026b10  retn
```
