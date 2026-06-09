# __security_init_cookie

- ea: `0x180044bd4`
- end: `0x180044cb1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180044150`

## callees

- `0x180044bd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180044c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044c1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044c1b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180044c33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180044c43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180044c33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180044c43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044c0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180044c0d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180044c5e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180044c5e`

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
0x180044bd4  mov     [rsp-8+arg_18], rbx
0x180044bd9  push    rbp
0x180044bda  mov     rbp, rsp
0x180044bdd  sub     rsp, 20h
0x180044be1  xor     eax, eax
0x180044be3  mov     rbx, 2B992DDFA232h
0x180044bed  mov     [rbp+arg_0], rax
0x180044bf1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180044bf5  mov     qword ptr [rbp+PerformanceCount], rax
0x180044bf9  mov     rax, cs:__security_cookie
0x180044c00  cmp     rax, rbx
0x180044c03  jnz     loc_180044C9C
0x180044c09  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180044c0d  call    cs:__imp_GetSystemTimeAsFileTime
0x180044c13  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180044c17  mov     [rbp+arg_0], rax
0x180044c1b  call    cs:__imp_GetCurrentProcessId
0x180044c21  mov     eax, eax
0x180044c23  xor     [rbp+arg_0], rax
0x180044c27  call    cs:__imp_GetCurrentThreadId
0x180044c2d  mov     eax, eax
0x180044c2f  xor     [rbp+arg_0], rax
0x180044c33  call    cs:__imp_GetTickCount
0x180044c39  mov     eax, eax
0x180044c3b  shl     rax, 18h
0x180044c3f  xor     [rbp+arg_0], rax
0x180044c43  call    cs:__imp_GetTickCount
0x180044c49  mov     eax, eax
0x180044c4b  lea     rcx, [rbp+arg_0]
0x180044c4f  xor     rax, [rbp+arg_0]
0x180044c53  xor     rax, rcx
0x180044c56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180044c5a  mov     [rbp+arg_0], rax
0x180044c5e  call    cs:__imp_QueryPerformanceCounter
0x180044c64  mov     eax, dword ptr [rbp+PerformanceCount]
0x180044c67  mov     rcx, 0FFFFFFFFFFFFh
0x180044c71  shl     rax, 20h
0x180044c75  xor     rax, qword ptr [rbp+PerformanceCount]
0x180044c79  xor     rax, [rbp+arg_0]
0x180044c7d  and     rax, rcx
0x180044c80  mov     rcx, rax
0x180044c83  cmp     rax, rbx
0x180044c86  jnz     short loc_180044C95
0x180044c88  mov     rax, 2B992DDFA233h
0x180044c92  mov     rcx, rax
0x180044c95  mov     cs:__security_cookie, rcx
0x180044c9c  mov     rbx, [rsp+20h+arg_18]
0x180044ca1  not     rax
0x180044ca4  mov     cs:__security_cookie_complement, rax
0x180044cab  add     rsp, 20h
0x180044caf  pop     rbp
0x180044cb0  retn
```
