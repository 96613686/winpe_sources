# __security_init_cookie

- ea: `0x1800cd4d4`
- end: `0x1800cd5b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cd0e0`

## callees

- `0x1800cd4d4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800cd55e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800cd55e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cd51b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cd51b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd527`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cd533`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cd543`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cd533`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cd543`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cd50d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cd50d`

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
0x1800cd4d4  mov     [rsp-8+arg_18], rbx
0x1800cd4d9  push    rbp
0x1800cd4da  mov     rbp, rsp
0x1800cd4dd  sub     rsp, 20h
0x1800cd4e1  xor     eax, eax
0x1800cd4e3  mov     rbx, 2B992DDFA232h
0x1800cd4ed  mov     [rbp+arg_0], rax
0x1800cd4f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800cd4f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800cd4f9  mov     rax, cs:__security_cookie
0x1800cd500  cmp     rax, rbx
0x1800cd503  jnz     loc_1800CD59C
0x1800cd509  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800cd50d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800cd513  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800cd517  mov     [rbp+arg_0], rax
0x1800cd51b  call    cs:__imp_GetCurrentProcessId
0x1800cd521  mov     eax, eax
0x1800cd523  xor     [rbp+arg_0], rax
0x1800cd527  call    cs:__imp_GetCurrentThreadId
0x1800cd52d  mov     eax, eax
0x1800cd52f  xor     [rbp+arg_0], rax
0x1800cd533  call    cs:__imp_GetTickCount
0x1800cd539  mov     eax, eax
0x1800cd53b  shl     rax, 18h
0x1800cd53f  xor     [rbp+arg_0], rax
0x1800cd543  call    cs:__imp_GetTickCount
0x1800cd549  mov     eax, eax
0x1800cd54b  lea     rcx, [rbp+arg_0]
0x1800cd54f  xor     rax, [rbp+arg_0]
0x1800cd553  xor     rax, rcx
0x1800cd556  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800cd55a  mov     [rbp+arg_0], rax
0x1800cd55e  call    cs:__imp_QueryPerformanceCounter
0x1800cd564  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800cd567  mov     rcx, 0FFFFFFFFFFFFh
0x1800cd571  shl     rax, 20h
0x1800cd575  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800cd579  xor     rax, [rbp+arg_0]
0x1800cd57d  and     rax, rcx
0x1800cd580  mov     rcx, rax
0x1800cd583  cmp     rax, rbx
0x1800cd586  jnz     short loc_1800CD595
0x1800cd588  mov     rax, 2B992DDFA233h
0x1800cd592  mov     rcx, rax
0x1800cd595  mov     cs:__security_cookie, rcx
0x1800cd59c  mov     rbx, [rsp+20h+arg_18]
0x1800cd5a1  not     rax
0x1800cd5a4  mov     cs:__security_cookie_complement, rax
0x1800cd5ab  add     rsp, 20h
0x1800cd5af  pop     rbp
0x1800cd5b0  retn
```
