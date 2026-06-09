# __security_init_cookie

- ea: `0x1800700c0`
- end: `0x18007019d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006fc70`

## callees

- `0x1800700c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180070107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180070107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070113`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180070113`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007014a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007014a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007011f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007012f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007011f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18007012f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800700f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800700f9`

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
0x1800700c0  mov     [rsp-8+arg_18], rbx
0x1800700c5  push    rbp
0x1800700c6  mov     rbp, rsp
0x1800700c9  sub     rsp, 20h
0x1800700cd  xor     eax, eax
0x1800700cf  mov     rbx, 2B992DDFA232h
0x1800700d9  mov     [rbp+arg_0], rax
0x1800700dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800700e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800700e5  mov     rax, cs:__security_cookie
0x1800700ec  cmp     rax, rbx
0x1800700ef  jnz     loc_180070188
0x1800700f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800700f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800700ff  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180070103  mov     [rbp+arg_0], rax
0x180070107  call    cs:__imp_GetCurrentProcessId
0x18007010d  mov     eax, eax
0x18007010f  xor     [rbp+arg_0], rax
0x180070113  call    cs:__imp_GetCurrentThreadId
0x180070119  mov     eax, eax
0x18007011b  xor     [rbp+arg_0], rax
0x18007011f  call    cs:__imp_GetTickCount
0x180070125  mov     eax, eax
0x180070127  shl     rax, 18h
0x18007012b  xor     [rbp+arg_0], rax
0x18007012f  call    cs:__imp_GetTickCount
0x180070135  mov     eax, eax
0x180070137  lea     rcx, [rbp+arg_0]
0x18007013b  xor     rax, [rbp+arg_0]
0x18007013f  xor     rax, rcx
0x180070142  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180070146  mov     [rbp+arg_0], rax
0x18007014a  call    cs:__imp_QueryPerformanceCounter
0x180070150  mov     eax, dword ptr [rbp+PerformanceCount]
0x180070153  mov     rcx, 0FFFFFFFFFFFFh
0x18007015d  shl     rax, 20h
0x180070161  xor     rax, qword ptr [rbp+PerformanceCount]
0x180070165  xor     rax, [rbp+arg_0]
0x180070169  and     rax, rcx
0x18007016c  mov     rcx, rax
0x18007016f  cmp     rax, rbx
0x180070172  jnz     short loc_180070181
0x180070174  mov     rax, 2B992DDFA233h
0x18007017e  mov     rcx, rax
0x180070181  mov     cs:__security_cookie, rcx
0x180070188  mov     rbx, [rsp+20h+arg_18]
0x18007018d  not     rax
0x180070190  mov     cs:__security_cookie_complement, rax
0x180070197  add     rsp, 20h
0x18007019b  pop     rbp
0x18007019c  retn
```
