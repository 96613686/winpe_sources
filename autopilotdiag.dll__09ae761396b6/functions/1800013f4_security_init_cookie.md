# __security_init_cookie

- ea: `0x1800013f4`
- end: `0x1800014a9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013b0`

## callees

- `0x1800013f4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001453`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001453`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001443`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001443`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001437`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001429`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001429`

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
0x1800013f4  mov     [rsp-8+arg_10], rbx
0x1800013f9  push    rbp
0x1800013fa  mov     rbp, rsp
0x1800013fd  sub     rsp, 30h
0x180001401  mov     rax, cs:__security_cookie
0x180001408  mov     rbx, 2B992DDFA232h
0x180001412  cmp     rax, rbx
0x180001415  jnz     short loc_180001494
0x180001417  xor     eax, eax
0x180001419  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000141d  mov     [rbp+var_10], rax
0x180001421  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001425  mov     qword ptr [rbp+PerformanceCount], rax
0x180001429  call    cs:__imp_GetSystemTimeAsFileTime
0x18000142f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001433  mov     [rbp+var_10], rax
0x180001437  call    cs:__imp_GetCurrentThreadId
0x18000143d  mov     eax, eax
0x18000143f  xor     [rbp+var_10], rax
0x180001443  call    cs:__imp_GetCurrentProcessId
0x180001449  mov     eax, eax
0x18000144b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000144f  xor     [rbp+var_10], rax
0x180001453  call    cs:__imp_QueryPerformanceCounter
0x180001459  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000145c  lea     rcx, [rbp+var_10]
0x180001460  shl     rax, 20h
0x180001464  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001468  xor     rax, [rbp+var_10]
0x18000146c  xor     rax, rcx
0x18000146f  mov     rcx, 0FFFFFFFFFFFFh
0x180001479  and     rax, rcx
0x18000147c  mov     rcx, 2B992DDFA233h
0x180001486  cmp     rax, rbx
0x180001489  cmovz   rax, rcx
0x18000148d  mov     cs:__security_cookie, rax
0x180001494  mov     rbx, [rsp+30h+arg_10]
0x180001499  not     rax
0x18000149c  mov     cs:__security_cookie_complement, rax
0x1800014a3  add     rsp, 30h
0x1800014a7  pop     rbp
0x1800014a8  retn
```
