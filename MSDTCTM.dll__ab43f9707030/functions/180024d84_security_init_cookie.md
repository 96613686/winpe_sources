# __security_init_cookie

- ea: `0x180024d84`
- end: `0x180024e61`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024390`

## callees

- `0x180024d84`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024de3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024df3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024de3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180024df3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024dbd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024dbd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024dcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180024dcb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180024e0e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180024e0e`

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
0x180024d84  mov     [rsp-8+arg_18], rbx
0x180024d89  push    rbp
0x180024d8a  mov     rbp, rsp
0x180024d8d  sub     rsp, 20h
0x180024d91  xor     eax, eax
0x180024d93  mov     rbx, 2B992DDFA232h
0x180024d9d  mov     [rbp+arg_0], rax
0x180024da1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180024da5  mov     qword ptr [rbp+PerformanceCount], rax
0x180024da9  mov     rax, cs:__security_cookie
0x180024db0  cmp     rax, rbx
0x180024db3  jnz     loc_180024E4C
0x180024db9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024dbd  call    cs:__imp_GetSystemTimeAsFileTime
0x180024dc3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180024dc7  mov     [rbp+arg_0], rax
0x180024dcb  call    cs:__imp_GetCurrentProcessId
0x180024dd1  mov     eax, eax
0x180024dd3  xor     [rbp+arg_0], rax
0x180024dd7  call    cs:__imp_GetCurrentThreadId
0x180024ddd  mov     eax, eax
0x180024ddf  xor     [rbp+arg_0], rax
0x180024de3  call    cs:__imp_GetTickCount
0x180024de9  mov     eax, eax
0x180024deb  shl     rax, 18h
0x180024def  xor     [rbp+arg_0], rax
0x180024df3  call    cs:__imp_GetTickCount
0x180024df9  mov     eax, eax
0x180024dfb  lea     rcx, [rbp+arg_0]
0x180024dff  xor     rax, [rbp+arg_0]
0x180024e03  xor     rax, rcx
0x180024e06  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180024e0a  mov     [rbp+arg_0], rax
0x180024e0e  call    cs:__imp_QueryPerformanceCounter
0x180024e14  mov     eax, dword ptr [rbp+PerformanceCount]
0x180024e17  mov     rcx, 0FFFFFFFFFFFFh
0x180024e21  shl     rax, 20h
0x180024e25  xor     rax, qword ptr [rbp+PerformanceCount]
0x180024e29  xor     rax, [rbp+arg_0]
0x180024e2d  and     rax, rcx
0x180024e30  mov     rcx, rax
0x180024e33  cmp     rax, rbx
0x180024e36  jnz     short loc_180024E45
0x180024e38  mov     rax, 2B992DDFA233h
0x180024e42  mov     rcx, rax
0x180024e45  mov     cs:__security_cookie, rcx
0x180024e4c  mov     rbx, [rsp+20h+arg_18]
0x180024e51  not     rax
0x180024e54  mov     cs:__security_cookie_complement, rax
0x180024e5b  add     rsp, 20h
0x180024e5f  pop     rbp
0x180024e60  retn
```
