# __security_init_cookie

- ea: `0x140002434`
- end: `0x140002511`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002040`

## callees

- `0x140002434`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000247b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000247b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002487`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002487`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400024be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400024be`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002493`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400024a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002493`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400024a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000246d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000246d`

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
0x140002434  mov     [rsp-8+arg_18], rbx
0x140002439  push    rbp
0x14000243a  mov     rbp, rsp
0x14000243d  sub     rsp, 20h
0x140002441  xor     eax, eax
0x140002443  mov     rbx, 2B992DDFA232h
0x14000244d  mov     [rbp+arg_0], rax
0x140002451  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002455  mov     qword ptr [rbp+PerformanceCount], rax
0x140002459  mov     rax, cs:__security_cookie
0x140002460  cmp     rax, rbx
0x140002463  jnz     loc_1400024FC
0x140002469  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000246d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002473  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002477  mov     [rbp+arg_0], rax
0x14000247b  call    cs:__imp_GetCurrentProcessId
0x140002481  mov     eax, eax
0x140002483  xor     [rbp+arg_0], rax
0x140002487  call    cs:__imp_GetCurrentThreadId
0x14000248d  mov     eax, eax
0x14000248f  xor     [rbp+arg_0], rax
0x140002493  call    cs:__imp_GetTickCount
0x140002499  mov     eax, eax
0x14000249b  shl     rax, 18h
0x14000249f  xor     [rbp+arg_0], rax
0x1400024a3  call    cs:__imp_GetTickCount
0x1400024a9  mov     eax, eax
0x1400024ab  lea     rcx, [rbp+arg_0]
0x1400024af  xor     rax, [rbp+arg_0]
0x1400024b3  xor     rax, rcx
0x1400024b6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400024ba  mov     [rbp+arg_0], rax
0x1400024be  call    cs:__imp_QueryPerformanceCounter
0x1400024c4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400024c7  mov     rcx, 0FFFFFFFFFFFFh
0x1400024d1  shl     rax, 20h
0x1400024d5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400024d9  xor     rax, [rbp+arg_0]
0x1400024dd  and     rax, rcx
0x1400024e0  mov     rcx, rax
0x1400024e3  cmp     rax, rbx
0x1400024e6  jnz     short loc_1400024F5
0x1400024e8  mov     rax, 2B992DDFA233h
0x1400024f2  mov     rcx, rax
0x1400024f5  mov     cs:__security_cookie, rcx
0x1400024fc  mov     rbx, [rsp+20h+arg_18]
0x140002501  not     rax
0x140002504  mov     cs:__security_cookie_complement, rax
0x14000250b  add     rsp, 20h
0x14000250f  pop     rbp
0x140002510  retn
```
