# __security_init_cookie

- ea: `0x140001f34`
- end: `0x140002011`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001c40`

## callees

- `0x140001f34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001f87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001f7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001fbe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001fbe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001f93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001fa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001f93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001fa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001f6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001f6d`

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
0x140001f34  mov     [rsp-8+arg_18], rbx
0x140001f39  push    rbp
0x140001f3a  mov     rbp, rsp
0x140001f3d  sub     rsp, 20h
0x140001f41  xor     eax, eax
0x140001f43  mov     rbx, 2B992DDFA232h
0x140001f4d  mov     [rbp+arg_0], rax
0x140001f51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001f55  mov     qword ptr [rbp+PerformanceCount], rax
0x140001f59  mov     rax, cs:__security_cookie
0x140001f60  cmp     rax, rbx
0x140001f63  jnz     loc_140001FFC
0x140001f69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001f6d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001f73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001f77  mov     [rbp+arg_0], rax
0x140001f7b  call    cs:__imp_GetCurrentProcessId
0x140001f81  mov     eax, eax
0x140001f83  xor     [rbp+arg_0], rax
0x140001f87  call    cs:__imp_GetCurrentThreadId
0x140001f8d  mov     eax, eax
0x140001f8f  xor     [rbp+arg_0], rax
0x140001f93  call    cs:__imp_GetTickCount
0x140001f99  mov     eax, eax
0x140001f9b  shl     rax, 18h
0x140001f9f  xor     [rbp+arg_0], rax
0x140001fa3  call    cs:__imp_GetTickCount
0x140001fa9  mov     eax, eax
0x140001fab  lea     rcx, [rbp+arg_0]
0x140001faf  xor     rax, [rbp+arg_0]
0x140001fb3  xor     rax, rcx
0x140001fb6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001fba  mov     [rbp+arg_0], rax
0x140001fbe  call    cs:__imp_QueryPerformanceCounter
0x140001fc4  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001fc7  mov     rcx, 0FFFFFFFFFFFFh
0x140001fd1  shl     rax, 20h
0x140001fd5  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001fd9  xor     rax, [rbp+arg_0]
0x140001fdd  and     rax, rcx
0x140001fe0  mov     rcx, rax
0x140001fe3  cmp     rax, rbx
0x140001fe6  jnz     short loc_140001FF5
0x140001fe8  mov     rax, 2B992DDFA233h
0x140001ff2  mov     rcx, rax
0x140001ff5  mov     cs:__security_cookie, rcx
0x140001ffc  mov     rbx, [rsp+20h+arg_18]
0x140002001  not     rax
0x140002004  mov     cs:__security_cookie_complement, rax
0x14000200b  add     rsp, 20h
0x14000200f  pop     rbp
0x140002010  retn
```
