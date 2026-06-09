# __security_init_cookie

- ea: `0x180001744`
- end: `0x180001821`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800012d0`

## callees

- `0x180001744`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000178b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000178b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800017ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800017ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800017b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000177d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000177d`

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
0x180001744  mov     [rsp-8+arg_18], rbx
0x180001749  push    rbp
0x18000174a  mov     rbp, rsp
0x18000174d  sub     rsp, 20h
0x180001751  xor     eax, eax
0x180001753  mov     rbx, 2B992DDFA232h
0x18000175d  mov     [rbp+arg_0], rax
0x180001761  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001765  mov     qword ptr [rbp+PerformanceCount], rax
0x180001769  mov     rax, cs:__security_cookie
0x180001770  cmp     rax, rbx
0x180001773  jnz     loc_18000180C
0x180001779  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000177d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001783  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001787  mov     [rbp+arg_0], rax
0x18000178b  call    cs:__imp_GetCurrentProcessId
0x180001791  mov     eax, eax
0x180001793  xor     [rbp+arg_0], rax
0x180001797  call    cs:__imp_GetCurrentThreadId
0x18000179d  mov     eax, eax
0x18000179f  xor     [rbp+arg_0], rax
0x1800017a3  call    cs:__imp_GetTickCount
0x1800017a9  mov     eax, eax
0x1800017ab  shl     rax, 18h
0x1800017af  xor     [rbp+arg_0], rax
0x1800017b3  call    cs:__imp_GetTickCount
0x1800017b9  mov     eax, eax
0x1800017bb  lea     rcx, [rbp+arg_0]
0x1800017bf  xor     rax, [rbp+arg_0]
0x1800017c3  xor     rax, rcx
0x1800017c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800017ca  mov     [rbp+arg_0], rax
0x1800017ce  call    cs:__imp_QueryPerformanceCounter
0x1800017d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800017d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800017e1  shl     rax, 20h
0x1800017e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800017e9  xor     rax, [rbp+arg_0]
0x1800017ed  and     rax, rcx
0x1800017f0  mov     rcx, rax
0x1800017f3  cmp     rax, rbx
0x1800017f6  jnz     short loc_180001805
0x1800017f8  mov     rax, 2B992DDFA233h
0x180001802  mov     rcx, rax
0x180001805  mov     cs:__security_cookie, rcx
0x18000180c  mov     rbx, [rsp+20h+arg_18]
0x180001811  not     rax
0x180001814  mov     cs:__security_cookie_complement, rax
0x18000181b  add     rsp, 20h
0x18000181f  pop     rbp
0x180001820  retn
```
