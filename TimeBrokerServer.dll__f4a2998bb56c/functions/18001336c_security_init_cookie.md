# __security_init_cookie

- ea: `0x18001336c`
- end: `0x180013421`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012d80`

## callees

- `0x18001336c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800133a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800133a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800133bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800133bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800133af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800133af`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800133cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800133cb`

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
0x18001336c  mov     [rsp-8+arg_10], rbx
0x180013371  push    rbp
0x180013372  mov     rbp, rsp
0x180013375  sub     rsp, 30h
0x180013379  mov     rax, cs:__security_cookie
0x180013380  mov     rbx, 2B992DDFA232h
0x18001338a  cmp     rax, rbx
0x18001338d  jnz     short loc_18001340C
0x18001338f  xor     eax, eax
0x180013391  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013395  mov     [rbp+var_10], rax
0x180013399  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001339d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800133a1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800133a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800133ab  mov     [rbp+var_10], rax
0x1800133af  call    cs:__imp_GetCurrentThreadId
0x1800133b5  mov     eax, eax
0x1800133b7  xor     [rbp+var_10], rax
0x1800133bb  call    cs:__imp_GetCurrentProcessId
0x1800133c1  mov     eax, eax
0x1800133c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800133c7  xor     [rbp+var_10], rax
0x1800133cb  call    cs:__imp_QueryPerformanceCounter
0x1800133d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800133d4  lea     rcx, [rbp+var_10]
0x1800133d8  shl     rax, 20h
0x1800133dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800133e0  xor     rax, [rbp+var_10]
0x1800133e4  xor     rax, rcx
0x1800133e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800133f1  and     rax, rcx
0x1800133f4  mov     rcx, 2B992DDFA233h
0x1800133fe  cmp     rax, rbx
0x180013401  cmovz   rax, rcx
0x180013405  mov     cs:__security_cookie, rax
0x18001340c  mov     rbx, [rsp+30h+arg_10]
0x180013411  not     rax
0x180013414  mov     cs:__security_cookie_complement, rax
0x18001341b  add     rsp, 30h
0x18001341f  pop     rbp
0x180013420  retn
```
