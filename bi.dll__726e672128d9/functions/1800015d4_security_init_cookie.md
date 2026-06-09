# __security_init_cookie

- ea: `0x1800015d4`
- end: `0x1800016b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001280`

## callees

- `0x1800015d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000161b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000161b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000165e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000165e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000160d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000160d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001633`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001643`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001633`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001643`

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
0x1800015d4  mov     [rsp-8+arg_18], rbx
0x1800015d9  push    rbp
0x1800015da  mov     rbp, rsp
0x1800015dd  sub     rsp, 20h
0x1800015e1  xor     eax, eax
0x1800015e3  mov     rbx, 2B992DDFA232h
0x1800015ed  mov     [rbp+arg_0], rax
0x1800015f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800015f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800015f9  mov     rax, cs:__security_cookie
0x180001600  cmp     rax, rbx
0x180001603  jnz     loc_18000169C
0x180001609  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000160d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001613  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001617  mov     [rbp+arg_0], rax
0x18000161b  call    cs:__imp_GetCurrentProcessId
0x180001621  mov     eax, eax
0x180001623  xor     [rbp+arg_0], rax
0x180001627  call    cs:__imp_GetCurrentThreadId
0x18000162d  mov     eax, eax
0x18000162f  xor     [rbp+arg_0], rax
0x180001633  call    cs:__imp_GetTickCount
0x180001639  mov     eax, eax
0x18000163b  shl     rax, 18h
0x18000163f  xor     [rbp+arg_0], rax
0x180001643  call    cs:__imp_GetTickCount
0x180001649  mov     eax, eax
0x18000164b  lea     rcx, [rbp+arg_0]
0x18000164f  xor     rax, [rbp+arg_0]
0x180001653  xor     rax, rcx
0x180001656  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000165a  mov     [rbp+arg_0], rax
0x18000165e  call    cs:__imp_QueryPerformanceCounter
0x180001664  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001667  mov     rcx, 0FFFFFFFFFFFFh
0x180001671  shl     rax, 20h
0x180001675  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001679  xor     rax, [rbp+arg_0]
0x18000167d  and     rax, rcx
0x180001680  mov     rcx, rax
0x180001683  cmp     rax, rbx
0x180001686  jnz     short loc_180001695
0x180001688  mov     rax, 2B992DDFA233h
0x180001692  mov     rcx, rax
0x180001695  mov     cs:__security_cookie, rcx
0x18000169c  mov     rbx, [rsp+20h+arg_18]
0x1800016a1  not     rax
0x1800016a4  mov     cs:__security_cookie_complement, rax
0x1800016ab  add     rsp, 20h
0x1800016af  pop     rbp
0x1800016b0  retn
```
