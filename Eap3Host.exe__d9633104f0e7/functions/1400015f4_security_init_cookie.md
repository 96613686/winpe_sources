# __security_init_cookie

- ea: `0x1400015f4`
- end: `0x1400016a9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001300`

## callees

- `0x1400015f4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001653`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001653`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001643`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001629`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001629`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1400015f4  mov     [rsp-8+arg_10], rbx
0x1400015f9  push    rbp
0x1400015fa  mov     rbp, rsp
0x1400015fd  sub     rsp, 30h
0x140001601  mov     rax, cs:__security_cookie
0x140001608  mov     rbx, 2B992DDFA232h
0x140001612  cmp     rax, rbx
0x140001615  jnz     short loc_140001694
0x140001617  xor     eax, eax
0x140001619  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000161d  mov     [rbp+var_10], rax
0x140001621  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001625  mov     qword ptr [rbp+PerformanceCount], rax
0x140001629  call    cs:__imp_GetSystemTimeAsFileTime
0x14000162f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001633  mov     [rbp+var_10], rax
0x140001637  call    cs:__imp_GetCurrentThreadId
0x14000163d  mov     eax, eax
0x14000163f  xor     [rbp+var_10], rax
0x140001643  call    cs:__imp_GetCurrentProcessId
0x140001649  mov     eax, eax
0x14000164b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000164f  xor     [rbp+var_10], rax
0x140001653  call    cs:__imp_QueryPerformanceCounter
0x140001659  mov     eax, dword ptr [rbp+PerformanceCount]
0x14000165c  lea     rcx, [rbp+var_10]
0x140001660  shl     rax, 20h
0x140001664  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001668  xor     rax, [rbp+var_10]
0x14000166c  xor     rax, rcx
0x14000166f  mov     rcx, 0FFFFFFFFFFFFh
0x140001679  and     rax, rcx
0x14000167c  mov     rcx, 2B992DDFA233h
0x140001686  cmp     rax, rbx
0x140001689  cmovz   rax, rcx
0x14000168d  mov     cs:__security_cookie, rax
0x140001694  mov     rbx, [rsp+30h+arg_10]
0x140001699  not     rax
0x14000169c  mov     cs:__security_cookie_complement, rax
0x1400016a3  add     rsp, 30h
0x1400016a7  pop     rbp
0x1400016a8  retn
```
