# __security_init_cookie

- ea: `0x1800026b4`
- end: `0x180002791`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022a0`

## callees

- `0x1800026b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002707`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002707`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000273e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000273e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800026ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800026ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002713`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002723`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002713`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002723`

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
0x1800026b4  mov     [rsp-8+arg_18], rbx
0x1800026b9  push    rbp
0x1800026ba  mov     rbp, rsp
0x1800026bd  sub     rsp, 20h
0x1800026c1  xor     eax, eax
0x1800026c3  mov     rbx, 2B992DDFA232h
0x1800026cd  mov     [rbp+arg_0], rax
0x1800026d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800026d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800026d9  mov     rax, cs:__security_cookie
0x1800026e0  cmp     rax, rbx
0x1800026e3  jnz     loc_18000277C
0x1800026e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800026ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800026f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800026f7  mov     [rbp+arg_0], rax
0x1800026fb  call    cs:__imp_GetCurrentProcessId
0x180002701  mov     eax, eax
0x180002703  xor     [rbp+arg_0], rax
0x180002707  call    cs:__imp_GetCurrentThreadId
0x18000270d  mov     eax, eax
0x18000270f  xor     [rbp+arg_0], rax
0x180002713  call    cs:__imp_GetTickCount
0x180002719  mov     eax, eax
0x18000271b  shl     rax, 18h
0x18000271f  xor     [rbp+arg_0], rax
0x180002723  call    cs:__imp_GetTickCount
0x180002729  mov     eax, eax
0x18000272b  lea     rcx, [rbp+arg_0]
0x18000272f  xor     rax, [rbp+arg_0]
0x180002733  xor     rax, rcx
0x180002736  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000273a  mov     [rbp+arg_0], rax
0x18000273e  call    cs:__imp_QueryPerformanceCounter
0x180002744  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002747  mov     rcx, 0FFFFFFFFFFFFh
0x180002751  shl     rax, 20h
0x180002755  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002759  xor     rax, [rbp+arg_0]
0x18000275d  and     rax, rcx
0x180002760  mov     rcx, rax
0x180002763  cmp     rax, rbx
0x180002766  jnz     short loc_180002775
0x180002768  mov     rax, 2B992DDFA233h
0x180002772  mov     rcx, rax
0x180002775  mov     cs:__security_cookie, rcx
0x18000277c  mov     rbx, [rsp+20h+arg_18]
0x180002781  not     rax
0x180002784  mov     cs:__security_cookie_complement, rax
0x18000278b  add     rsp, 20h
0x18000278f  pop     rbp
0x180002790  retn
```
