# __security_init_cookie

- ea: `0x1800e325c`
- end: `0x1800e3311`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e2f40`

## callees

- `0x1800e325c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e32bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e32bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e32ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e32ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e329f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e329f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e3291`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e3291`

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
0x1800e325c  mov     [rsp-8+arg_10], rbx
0x1800e3261  push    rbp
0x1800e3262  mov     rbp, rsp
0x1800e3265  sub     rsp, 30h
0x1800e3269  mov     rax, cs:__security_cookie
0x1800e3270  mov     rbx, 2B992DDFA232h
0x1800e327a  cmp     rax, rbx
0x1800e327d  jnz     short loc_1800E32FC
0x1800e327f  xor     eax, eax
0x1800e3281  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800e3285  mov     [rbp+var_10], rax
0x1800e3289  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800e328d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800e3291  call    cs:__imp_GetSystemTimeAsFileTime
0x1800e3297  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800e329b  mov     [rbp+var_10], rax
0x1800e329f  call    cs:__imp_GetCurrentThreadId
0x1800e32a5  mov     eax, eax
0x1800e32a7  xor     [rbp+var_10], rax
0x1800e32ab  call    cs:__imp_GetCurrentProcessId
0x1800e32b1  mov     eax, eax
0x1800e32b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800e32b7  xor     [rbp+var_10], rax
0x1800e32bb  call    cs:__imp_QueryPerformanceCounter
0x1800e32c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800e32c4  lea     rcx, [rbp+var_10]
0x1800e32c8  shl     rax, 20h
0x1800e32cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800e32d0  xor     rax, [rbp+var_10]
0x1800e32d4  xor     rax, rcx
0x1800e32d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800e32e1  and     rax, rcx
0x1800e32e4  mov     rcx, 2B992DDFA233h
0x1800e32ee  cmp     rax, rbx
0x1800e32f1  cmovz   rax, rcx
0x1800e32f5  mov     cs:__security_cookie, rax
0x1800e32fc  mov     rbx, [rsp+30h+arg_10]
0x1800e3301  not     rax
0x1800e3304  mov     cs:__security_cookie_complement, rax
0x1800e330b  add     rsp, 30h
0x1800e330f  pop     rbp
0x1800e3310  retn
```
