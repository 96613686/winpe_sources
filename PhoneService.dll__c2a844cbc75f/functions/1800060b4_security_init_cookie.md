# __security_init_cookie

- ea: `0x1800060b4`
- end: `0x180006191`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005930`

## callees

- `0x1800060b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800060fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800060fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800060ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800060ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006113`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006123`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006113`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006123`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000613e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000613e`

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
0x1800060b4  mov     [rsp-8+arg_18], rbx
0x1800060b9  push    rbp
0x1800060ba  mov     rbp, rsp
0x1800060bd  sub     rsp, 20h
0x1800060c1  xor     eax, eax
0x1800060c3  mov     rbx, 2B992DDFA232h
0x1800060cd  mov     [rbp+arg_0], rax
0x1800060d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800060d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800060d9  mov     rax, cs:__security_cookie
0x1800060e0  cmp     rax, rbx
0x1800060e3  jnz     loc_18000617C
0x1800060e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800060ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800060f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800060f7  mov     [rbp+arg_0], rax
0x1800060fb  call    cs:__imp_GetCurrentProcessId
0x180006101  mov     eax, eax
0x180006103  xor     [rbp+arg_0], rax
0x180006107  call    cs:__imp_GetCurrentThreadId
0x18000610d  mov     eax, eax
0x18000610f  xor     [rbp+arg_0], rax
0x180006113  call    cs:__imp_GetTickCount
0x180006119  mov     eax, eax
0x18000611b  shl     rax, 18h
0x18000611f  xor     [rbp+arg_0], rax
0x180006123  call    cs:__imp_GetTickCount
0x180006129  mov     eax, eax
0x18000612b  lea     rcx, [rbp+arg_0]
0x18000612f  xor     rax, [rbp+arg_0]
0x180006133  xor     rax, rcx
0x180006136  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000613a  mov     [rbp+arg_0], rax
0x18000613e  call    cs:__imp_QueryPerformanceCounter
0x180006144  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006147  mov     rcx, 0FFFFFFFFFFFFh
0x180006151  shl     rax, 20h
0x180006155  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006159  xor     rax, [rbp+arg_0]
0x18000615d  and     rax, rcx
0x180006160  mov     rcx, rax
0x180006163  cmp     rax, rbx
0x180006166  jnz     short loc_180006175
0x180006168  mov     rax, 2B992DDFA233h
0x180006172  mov     rcx, rax
0x180006175  mov     cs:__security_cookie, rcx
0x18000617c  mov     rbx, [rsp+20h+arg_18]
0x180006181  not     rax
0x180006184  mov     cs:__security_cookie_complement, rax
0x18000618b  add     rsp, 20h
0x18000618f  pop     rbp
0x180006190  retn
```
