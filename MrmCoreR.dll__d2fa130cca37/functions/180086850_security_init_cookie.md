# __security_init_cookie

- ea: `0x180086850`
- end: `0x180086905`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800862a0`

## callees

- `0x180086850`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008689f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18008689f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180086893`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180086893`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180086885`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180086885`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800868af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800868af`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180086850  mov     [rsp-8+arg_10], rbx
0x180086855  push    rbp
0x180086856  mov     rbp, rsp
0x180086859  sub     rsp, 30h
0x18008685d  mov     rax, cs:__security_cookie
0x180086864  mov     rbx, 2B992DDFA232h
0x18008686e  cmp     rax, rbx
0x180086871  jnz     short loc_1800868F0
0x180086873  xor     eax, eax
0x180086875  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180086879  mov     [rbp+var_10], rax
0x18008687d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180086881  mov     qword ptr [rbp+PerformanceCount], rax
0x180086885  call    cs:__imp_GetSystemTimeAsFileTime
0x18008688b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18008688f  mov     [rbp+var_10], rax
0x180086893  call    cs:__imp_GetCurrentThreadId
0x180086899  mov     eax, eax
0x18008689b  xor     [rbp+var_10], rax
0x18008689f  call    cs:__imp_GetCurrentProcessId
0x1800868a5  mov     eax, eax
0x1800868a7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800868ab  xor     [rbp+var_10], rax
0x1800868af  call    cs:__imp_QueryPerformanceCounter
0x1800868b5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800868b8  lea     rcx, [rbp+var_10]
0x1800868bc  shl     rax, 20h
0x1800868c0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800868c4  xor     rax, [rbp+var_10]
0x1800868c8  xor     rax, rcx
0x1800868cb  mov     rcx, 0FFFFFFFFFFFFh
0x1800868d5  and     rax, rcx
0x1800868d8  mov     rcx, 2B992DDFA233h
0x1800868e2  cmp     rax, rbx
0x1800868e5  cmovz   rax, rcx
0x1800868e9  mov     cs:__security_cookie, rax
0x1800868f0  mov     rbx, [rsp+30h+arg_10]
0x1800868f5  not     rax
0x1800868f8  mov     cs:__security_cookie_complement, rax
0x1800868ff  add     rsp, 30h
0x180086903  pop     rbp
0x180086904  retn
```
