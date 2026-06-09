# __security_init_cookie

- ea: `0x180013ef0`
- end: `0x180013fcd`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013a90`

## callees

- `0x180013ef0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013f7a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013f7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013f37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013f37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013f43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013f43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013f29`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013f29`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013f4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013f5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013f4f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013f5f`

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
0x180013ef0  mov     [rsp-8+arg_18], rbx
0x180013ef5  push    rbp
0x180013ef6  mov     rbp, rsp
0x180013ef9  sub     rsp, 20h
0x180013efd  xor     eax, eax
0x180013eff  mov     rbx, 2B992DDFA232h
0x180013f09  mov     [rbp+arg_0], rax
0x180013f0d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180013f11  mov     qword ptr [rbp+PerformanceCount], rax
0x180013f15  mov     rax, cs:__security_cookie
0x180013f1c  cmp     rax, rbx
0x180013f1f  jnz     loc_180013FB8
0x180013f25  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013f29  call    cs:__imp_GetSystemTimeAsFileTime
0x180013f2f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180013f33  mov     [rbp+arg_0], rax
0x180013f37  call    cs:__imp_GetCurrentProcessId
0x180013f3d  mov     eax, eax
0x180013f3f  xor     [rbp+arg_0], rax
0x180013f43  call    cs:__imp_GetCurrentThreadId
0x180013f49  mov     eax, eax
0x180013f4b  xor     [rbp+arg_0], rax
0x180013f4f  call    cs:__imp_GetTickCount
0x180013f55  mov     eax, eax
0x180013f57  shl     rax, 18h
0x180013f5b  xor     [rbp+arg_0], rax
0x180013f5f  call    cs:__imp_GetTickCount
0x180013f65  mov     eax, eax
0x180013f67  lea     rcx, [rbp+arg_0]
0x180013f6b  xor     rax, [rbp+arg_0]
0x180013f6f  xor     rax, rcx
0x180013f72  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180013f76  mov     [rbp+arg_0], rax
0x180013f7a  call    cs:__imp_QueryPerformanceCounter
0x180013f80  mov     eax, dword ptr [rbp+PerformanceCount]
0x180013f83  mov     rcx, 0FFFFFFFFFFFFh
0x180013f8d  shl     rax, 20h
0x180013f91  xor     rax, qword ptr [rbp+PerformanceCount]
0x180013f95  xor     rax, [rbp+arg_0]
0x180013f99  and     rax, rcx
0x180013f9c  mov     rcx, rax
0x180013f9f  cmp     rax, rbx
0x180013fa2  jnz     short loc_180013FB1
0x180013fa4  mov     rax, 2B992DDFA233h
0x180013fae  mov     rcx, rax
0x180013fb1  mov     cs:__security_cookie, rcx
0x180013fb8  mov     rbx, [rsp+20h+arg_18]
0x180013fbd  not     rax
0x180013fc0  mov     cs:__security_cookie_complement, rax
0x180013fc7  add     rsp, 20h
0x180013fcb  pop     rbp
0x180013fcc  retn
```
