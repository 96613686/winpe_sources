# __security_init_cookie

- ea: `0x180001874`
- end: `0x180001951`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001300`

## callees

- `0x180001874`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800018c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800018c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800018bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800018bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800018e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800018ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800018ad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800018fe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800018fe`

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
0x180001874  mov     [rsp-8+arg_18], rbx
0x180001879  push    rbp
0x18000187a  mov     rbp, rsp
0x18000187d  sub     rsp, 20h
0x180001881  xor     eax, eax
0x180001883  mov     rbx, 2B992DDFA232h
0x18000188d  mov     [rbp+arg_0], rax
0x180001891  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001895  mov     qword ptr [rbp+PerformanceCount], rax
0x180001899  mov     rax, cs:__security_cookie
0x1800018a0  cmp     rax, rbx
0x1800018a3  jnz     loc_18000193C
0x1800018a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800018ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1800018b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800018b7  mov     [rbp+arg_0], rax
0x1800018bb  call    cs:__imp_GetCurrentProcessId
0x1800018c1  mov     eax, eax
0x1800018c3  xor     [rbp+arg_0], rax
0x1800018c7  call    cs:__imp_GetCurrentThreadId
0x1800018cd  mov     eax, eax
0x1800018cf  xor     [rbp+arg_0], rax
0x1800018d3  call    cs:__imp_GetTickCount
0x1800018d9  mov     eax, eax
0x1800018db  shl     rax, 18h
0x1800018df  xor     [rbp+arg_0], rax
0x1800018e3  call    cs:__imp_GetTickCount
0x1800018e9  mov     eax, eax
0x1800018eb  lea     rcx, [rbp+arg_0]
0x1800018ef  xor     rax, [rbp+arg_0]
0x1800018f3  xor     rax, rcx
0x1800018f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800018fa  mov     [rbp+arg_0], rax
0x1800018fe  call    cs:__imp_QueryPerformanceCounter
0x180001904  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001907  mov     rcx, 0FFFFFFFFFFFFh
0x180001911  shl     rax, 20h
0x180001915  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001919  xor     rax, [rbp+arg_0]
0x18000191d  and     rax, rcx
0x180001920  mov     rcx, rax
0x180001923  cmp     rax, rbx
0x180001926  jnz     short loc_180001935
0x180001928  mov     rax, 2B992DDFA233h
0x180001932  mov     rcx, rax
0x180001935  mov     cs:__security_cookie, rcx
0x18000193c  mov     rbx, [rsp+20h+arg_18]
0x180001941  not     rax
0x180001944  mov     cs:__security_cookie_complement, rax
0x18000194b  add     rsp, 20h
0x18000194f  pop     rbp
0x180001950  retn
```
