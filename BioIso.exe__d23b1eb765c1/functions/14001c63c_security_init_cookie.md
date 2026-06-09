# __security_init_cookie

- ea: `0x14001c63c`
- end: `0x14001c6f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001bd10`

## callees

- `0x14001c63c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c67f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001c67f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001c68b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14001c68b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14001c69b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14001c69b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001c671`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14001c671`

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
0x14001c63c  mov     [rsp-8+arg_10], rbx
0x14001c641  push    rbp
0x14001c642  mov     rbp, rsp
0x14001c645  sub     rsp, 30h
0x14001c649  mov     rax, cs:__security_cookie
0x14001c650  mov     rbx, 2B992DDFA232h
0x14001c65a  cmp     rax, rbx
0x14001c65d  jnz     short loc_14001C6DC
0x14001c65f  xor     eax, eax
0x14001c661  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14001c665  mov     [rbp+var_10], rax
0x14001c669  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14001c66d  mov     qword ptr [rbp+PerformanceCount], rax
0x14001c671  call    cs:__imp_GetSystemTimeAsFileTime
0x14001c677  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14001c67b  mov     [rbp+var_10], rax
0x14001c67f  call    cs:__imp_GetCurrentThreadId
0x14001c685  mov     eax, eax
0x14001c687  xor     [rbp+var_10], rax
0x14001c68b  call    cs:__imp_GetCurrentProcessId
0x14001c691  mov     eax, eax
0x14001c693  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14001c697  xor     [rbp+var_10], rax
0x14001c69b  call    cs:__imp_QueryPerformanceCounter
0x14001c6a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x14001c6a4  lea     rcx, [rbp+var_10]
0x14001c6a8  shl     rax, 20h
0x14001c6ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x14001c6b0  xor     rax, [rbp+var_10]
0x14001c6b4  xor     rax, rcx
0x14001c6b7  mov     rcx, 0FFFFFFFFFFFFh
0x14001c6c1  and     rax, rcx
0x14001c6c4  mov     rcx, 2B992DDFA233h
0x14001c6ce  cmp     rax, rbx
0x14001c6d1  cmovz   rax, rcx
0x14001c6d5  mov     cs:__security_cookie, rax
0x14001c6dc  mov     rbx, [rsp+30h+arg_10]
0x14001c6e1  not     rax
0x14001c6e4  mov     cs:__security_cookie_complement, rax
0x14001c6eb  add     rsp, 30h
0x14001c6ef  pop     rbp
0x14001c6f0  retn
```
