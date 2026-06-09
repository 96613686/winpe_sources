# __security_init_cookie

- ea: `0x1800055bc`
- end: `0x180005671`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005050`

## callees

- `0x1800055bc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000560b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000560b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000561b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000561b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800055f1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800055f1`

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
0x1800055bc  mov     [rsp-8+arg_10], rbx
0x1800055c1  push    rbp
0x1800055c2  mov     rbp, rsp
0x1800055c5  sub     rsp, 30h
0x1800055c9  mov     rax, cs:__security_cookie
0x1800055d0  mov     rbx, 2B992DDFA232h
0x1800055da  cmp     rax, rbx
0x1800055dd  jnz     short loc_18000565C
0x1800055df  xor     eax, eax
0x1800055e1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800055e5  mov     [rbp+var_10], rax
0x1800055e9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800055ed  mov     qword ptr [rbp+PerformanceCount], rax
0x1800055f1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800055f7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800055fb  mov     [rbp+var_10], rax
0x1800055ff  call    cs:__imp_GetCurrentThreadId
0x180005605  mov     eax, eax
0x180005607  xor     [rbp+var_10], rax
0x18000560b  call    cs:__imp_GetCurrentProcessId
0x180005611  mov     eax, eax
0x180005613  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005617  xor     [rbp+var_10], rax
0x18000561b  call    cs:__imp_QueryPerformanceCounter
0x180005621  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005624  lea     rcx, [rbp+var_10]
0x180005628  shl     rax, 20h
0x18000562c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005630  xor     rax, [rbp+var_10]
0x180005634  xor     rax, rcx
0x180005637  mov     rcx, 0FFFFFFFFFFFFh
0x180005641  and     rax, rcx
0x180005644  mov     rcx, 2B992DDFA233h
0x18000564e  cmp     rax, rbx
0x180005651  cmovz   rax, rcx
0x180005655  mov     cs:__security_cookie, rax
0x18000565c  mov     rbx, [rsp+30h+arg_10]
0x180005661  not     rax
0x180005664  mov     cs:__security_cookie_complement, rax
0x18000566b  add     rsp, 30h
0x18000566f  pop     rbp
0x180005670  retn
```
