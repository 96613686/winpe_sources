# __security_init_cookie

- ea: `0x18000ee84`
- end: `0x18000ef61`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e950`

## callees

- `0x18000ee84`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000eed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000eecb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000eecb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000eee3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000eef3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000eee3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000eef3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000eebd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000eebd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ef0e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ef0e`

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
0x18000ee84  mov     [rsp-8+arg_18], rbx
0x18000ee89  push    rbp
0x18000ee8a  mov     rbp, rsp
0x18000ee8d  sub     rsp, 20h
0x18000ee91  xor     eax, eax
0x18000ee93  mov     rbx, 2B992DDFA232h
0x18000ee9d  mov     [rbp+arg_0], rax
0x18000eea1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000eea5  mov     qword ptr [rbp+PerformanceCount], rax
0x18000eea9  mov     rax, cs:__security_cookie
0x18000eeb0  cmp     rax, rbx
0x18000eeb3  jnz     loc_18000EF4C
0x18000eeb9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000eebd  call    cs:__imp_GetSystemTimeAsFileTime
0x18000eec3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000eec7  mov     [rbp+arg_0], rax
0x18000eecb  call    cs:__imp_GetCurrentProcessId
0x18000eed1  mov     eax, eax
0x18000eed3  xor     [rbp+arg_0], rax
0x18000eed7  call    cs:__imp_GetCurrentThreadId
0x18000eedd  mov     eax, eax
0x18000eedf  xor     [rbp+arg_0], rax
0x18000eee3  call    cs:__imp_GetTickCount
0x18000eee9  mov     eax, eax
0x18000eeeb  shl     rax, 18h
0x18000eeef  xor     [rbp+arg_0], rax
0x18000eef3  call    cs:__imp_GetTickCount
0x18000eef9  mov     eax, eax
0x18000eefb  lea     rcx, [rbp+arg_0]
0x18000eeff  xor     rax, [rbp+arg_0]
0x18000ef03  xor     rax, rcx
0x18000ef06  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000ef0a  mov     [rbp+arg_0], rax
0x18000ef0e  call    cs:__imp_QueryPerformanceCounter
0x18000ef14  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000ef17  mov     rcx, 0FFFFFFFFFFFFh
0x18000ef21  shl     rax, 20h
0x18000ef25  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000ef29  xor     rax, [rbp+arg_0]
0x18000ef2d  and     rax, rcx
0x18000ef30  mov     rcx, rax
0x18000ef33  cmp     rax, rbx
0x18000ef36  jnz     short loc_18000EF45
0x18000ef38  mov     rax, 2B992DDFA233h
0x18000ef42  mov     rcx, rax
0x18000ef45  mov     cs:__security_cookie, rcx
0x18000ef4c  mov     rbx, [rsp+20h+arg_18]
0x18000ef51  not     rax
0x18000ef54  mov     cs:__security_cookie_complement, rax
0x18000ef5b  add     rsp, 20h
0x18000ef5f  pop     rbp
0x18000ef60  retn
```
