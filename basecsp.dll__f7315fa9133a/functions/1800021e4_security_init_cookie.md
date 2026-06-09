# __security_init_cookie

- ea: `0x1800021e4`
- end: `0x1800022c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800018a0`

## callees

- `0x1800021e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002237`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002237`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000222b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000222b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000226e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000226e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000221d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000221d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002243`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002253`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002243`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002253`

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
0x1800021e4  mov     [rsp-8+arg_18], rbx
0x1800021e9  push    rbp
0x1800021ea  mov     rbp, rsp
0x1800021ed  sub     rsp, 20h
0x1800021f1  xor     eax, eax
0x1800021f3  mov     rbx, 2B992DDFA232h
0x1800021fd  mov     [rbp+arg_0], rax
0x180002201  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002205  mov     qword ptr [rbp+PerformanceCount], rax
0x180002209  mov     rax, cs:__security_cookie
0x180002210  cmp     rax, rbx
0x180002213  jnz     loc_1800022AC
0x180002219  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000221d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002223  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002227  mov     [rbp+arg_0], rax
0x18000222b  call    cs:__imp_GetCurrentProcessId
0x180002231  mov     eax, eax
0x180002233  xor     [rbp+arg_0], rax
0x180002237  call    cs:__imp_GetCurrentThreadId
0x18000223d  mov     eax, eax
0x18000223f  xor     [rbp+arg_0], rax
0x180002243  call    cs:__imp_GetTickCount
0x180002249  mov     eax, eax
0x18000224b  shl     rax, 18h
0x18000224f  xor     [rbp+arg_0], rax
0x180002253  call    cs:__imp_GetTickCount
0x180002259  mov     eax, eax
0x18000225b  lea     rcx, [rbp+arg_0]
0x18000225f  xor     rax, [rbp+arg_0]
0x180002263  xor     rax, rcx
0x180002266  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000226a  mov     [rbp+arg_0], rax
0x18000226e  call    cs:__imp_QueryPerformanceCounter
0x180002274  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002277  mov     rcx, 0FFFFFFFFFFFFh
0x180002281  shl     rax, 20h
0x180002285  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002289  xor     rax, [rbp+arg_0]
0x18000228d  and     rax, rcx
0x180002290  mov     rcx, rax
0x180002293  cmp     rax, rbx
0x180002296  jnz     short loc_1800022A5
0x180002298  mov     rax, 2B992DDFA233h
0x1800022a2  mov     rcx, rax
0x1800022a5  mov     cs:__security_cookie, rcx
0x1800022ac  mov     rbx, [rsp+20h+arg_18]
0x1800022b1  not     rax
0x1800022b4  mov     cs:__security_cookie_complement, rax
0x1800022bb  add     rsp, 20h
0x1800022bf  pop     rbp
0x1800022c0  retn
```
