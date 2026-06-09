# __security_init_cookie

- ea: `0x180050f7c`
- end: `0x180051031`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050b50`

## callees

- `0x180050f7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180050fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180050fcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050fbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180050fbf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050fdb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180050fdb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180050fb1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180050fb1`

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
0x180050f7c  mov     [rsp-8+arg_10], rbx
0x180050f81  push    rbp
0x180050f82  mov     rbp, rsp
0x180050f85  sub     rsp, 30h
0x180050f89  mov     rax, cs:__security_cookie
0x180050f90  mov     rbx, 2B992DDFA232h
0x180050f9a  cmp     rax, rbx
0x180050f9d  jnz     short loc_18005101C
0x180050f9f  xor     eax, eax
0x180050fa1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180050fa5  mov     [rbp+var_10], rax
0x180050fa9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180050fad  mov     qword ptr [rbp+PerformanceCount], rax
0x180050fb1  call    cs:__imp_GetSystemTimeAsFileTime
0x180050fb7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180050fbb  mov     [rbp+var_10], rax
0x180050fbf  call    cs:__imp_GetCurrentThreadId
0x180050fc5  mov     eax, eax
0x180050fc7  xor     [rbp+var_10], rax
0x180050fcb  call    cs:__imp_GetCurrentProcessId
0x180050fd1  mov     eax, eax
0x180050fd3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180050fd7  xor     [rbp+var_10], rax
0x180050fdb  call    cs:__imp_QueryPerformanceCounter
0x180050fe1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180050fe4  lea     rcx, [rbp+var_10]
0x180050fe8  shl     rax, 20h
0x180050fec  xor     rax, qword ptr [rbp+PerformanceCount]
0x180050ff0  xor     rax, [rbp+var_10]
0x180050ff4  xor     rax, rcx
0x180050ff7  mov     rcx, 0FFFFFFFFFFFFh
0x180051001  and     rax, rcx
0x180051004  mov     rcx, 2B992DDFA233h
0x18005100e  cmp     rax, rbx
0x180051011  cmovz   rax, rcx
0x180051015  mov     cs:__security_cookie, rax
0x18005101c  mov     rbx, [rsp+30h+arg_10]
0x180051021  not     rax
0x180051024  mov     cs:__security_cookie_complement, rax
0x18005102b  add     rsp, 30h
0x18005102f  pop     rbp
0x180051030  retn
```
