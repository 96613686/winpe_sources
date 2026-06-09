# __security_init_cookie

- ea: `0x18004f348`
- end: `0x18004f3fd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004ec80`

## callees

- `0x18004f348`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f38b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004f38b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004f397`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f37d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004f37d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004f3a7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004f3a7`

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
0x18004f348  mov     [rsp-8+arg_10], rbx
0x18004f34d  push    rbp
0x18004f34e  mov     rbp, rsp
0x18004f351  sub     rsp, 30h
0x18004f355  mov     rax, cs:__security_cookie
0x18004f35c  mov     rbx, 2B992DDFA232h
0x18004f366  cmp     rax, rbx
0x18004f369  jnz     short loc_18004F3E8
0x18004f36b  xor     eax, eax
0x18004f36d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004f371  mov     [rbp+var_10], rax
0x18004f375  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004f379  mov     qword ptr [rbp+PerformanceCount], rax
0x18004f37d  call    cs:__imp_GetSystemTimeAsFileTime
0x18004f383  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004f387  mov     [rbp+var_10], rax
0x18004f38b  call    cs:__imp_GetCurrentThreadId
0x18004f391  mov     eax, eax
0x18004f393  xor     [rbp+var_10], rax
0x18004f397  call    cs:__imp_GetCurrentProcessId
0x18004f39d  mov     eax, eax
0x18004f39f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004f3a3  xor     [rbp+var_10], rax
0x18004f3a7  call    cs:__imp_QueryPerformanceCounter
0x18004f3ad  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004f3b0  lea     rcx, [rbp+var_10]
0x18004f3b4  shl     rax, 20h
0x18004f3b8  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004f3bc  xor     rax, [rbp+var_10]
0x18004f3c0  xor     rax, rcx
0x18004f3c3  mov     rcx, 0FFFFFFFFFFFFh
0x18004f3cd  and     rax, rcx
0x18004f3d0  mov     rcx, 2B992DDFA233h
0x18004f3da  cmp     rax, rbx
0x18004f3dd  cmovz   rax, rcx
0x18004f3e1  mov     cs:__security_cookie, rax
0x18004f3e8  mov     rbx, [rsp+30h+arg_10]
0x18004f3ed  not     rax
0x18004f3f0  mov     cs:__security_cookie_complement, rax
0x18004f3f7  add     rsp, 30h
0x18004f3fb  pop     rbp
0x18004f3fc  retn
```
