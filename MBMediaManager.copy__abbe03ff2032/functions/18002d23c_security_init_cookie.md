# __security_init_cookie

- ea: `0x18002d23c`
- end: `0x18002d2f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002ccd0`

## callees

- `0x18002d23c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d27f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d27f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d28b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002d28b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002d29b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002d29b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d271`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002d271`

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
0x18002d23c  mov     [rsp-8+arg_10], rbx
0x18002d241  push    rbp
0x18002d242  mov     rbp, rsp
0x18002d245  sub     rsp, 30h
0x18002d249  mov     rax, cs:__security_cookie
0x18002d250  mov     rbx, 2B992DDFA232h
0x18002d25a  cmp     rax, rbx
0x18002d25d  jnz     short loc_18002D2DC
0x18002d25f  xor     eax, eax
0x18002d261  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002d265  mov     [rbp+var_10], rax
0x18002d269  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002d26d  mov     qword ptr [rbp+PerformanceCount], rax
0x18002d271  call    cs:__imp_GetSystemTimeAsFileTime
0x18002d277  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002d27b  mov     [rbp+var_10], rax
0x18002d27f  call    cs:__imp_GetCurrentThreadId
0x18002d285  mov     eax, eax
0x18002d287  xor     [rbp+var_10], rax
0x18002d28b  call    cs:__imp_GetCurrentProcessId
0x18002d291  mov     eax, eax
0x18002d293  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002d297  xor     [rbp+var_10], rax
0x18002d29b  call    cs:__imp_QueryPerformanceCounter
0x18002d2a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002d2a4  lea     rcx, [rbp+var_10]
0x18002d2a8  shl     rax, 20h
0x18002d2ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002d2b0  xor     rax, [rbp+var_10]
0x18002d2b4  xor     rax, rcx
0x18002d2b7  mov     rcx, 0FFFFFFFFFFFFh
0x18002d2c1  and     rax, rcx
0x18002d2c4  mov     rcx, 2B992DDFA233h
0x18002d2ce  cmp     rax, rbx
0x18002d2d1  cmovz   rax, rcx
0x18002d2d5  mov     cs:__security_cookie, rax
0x18002d2dc  mov     rbx, [rsp+30h+arg_10]
0x18002d2e1  not     rax
0x18002d2e4  mov     cs:__security_cookie_complement, rax
0x18002d2eb  add     rsp, 30h
0x18002d2ef  pop     rbp
0x18002d2f0  retn
```
