# __security_init_cookie

- ea: `0x1800bbd1c`
- end: `0x1800bbdd1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800bb430`

## callees

- `0x1800bbd1c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bbd6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800bbd6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bbd5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800bbd5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bbd51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800bbd51`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbd7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbd7b`

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
0x1800bbd1c  mov     [rsp-8+arg_10], rbx
0x1800bbd21  push    rbp
0x1800bbd22  mov     rbp, rsp
0x1800bbd25  sub     rsp, 30h
0x1800bbd29  mov     rax, cs:__security_cookie
0x1800bbd30  mov     rbx, 2B992DDFA232h
0x1800bbd3a  cmp     rax, rbx
0x1800bbd3d  jnz     short loc_1800BBDBC
0x1800bbd3f  xor     eax, eax
0x1800bbd41  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800bbd45  mov     [rbp+var_10], rax
0x1800bbd49  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800bbd4d  mov     qword ptr [rbp+PerformanceCount], rax
0x1800bbd51  call    cs:__imp_GetSystemTimeAsFileTime
0x1800bbd57  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800bbd5b  mov     [rbp+var_10], rax
0x1800bbd5f  call    cs:__imp_GetCurrentThreadId
0x1800bbd65  mov     eax, eax
0x1800bbd67  xor     [rbp+var_10], rax
0x1800bbd6b  call    cs:__imp_GetCurrentProcessId
0x1800bbd71  mov     eax, eax
0x1800bbd73  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800bbd77  xor     [rbp+var_10], rax
0x1800bbd7b  call    cs:__imp_QueryPerformanceCounter
0x1800bbd81  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800bbd84  lea     rcx, [rbp+var_10]
0x1800bbd88  shl     rax, 20h
0x1800bbd8c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800bbd90  xor     rax, [rbp+var_10]
0x1800bbd94  xor     rax, rcx
0x1800bbd97  mov     rcx, 0FFFFFFFFFFFFh
0x1800bbda1  and     rax, rcx
0x1800bbda4  mov     rcx, 2B992DDFA233h
0x1800bbdae  cmp     rax, rbx
0x1800bbdb1  cmovz   rax, rcx
0x1800bbdb5  mov     cs:__security_cookie, rax
0x1800bbdbc  mov     rbx, [rsp+30h+arg_10]
0x1800bbdc1  not     rax
0x1800bbdc4  mov     cs:__security_cookie_complement, rax
0x1800bbdcb  add     rsp, 30h
0x1800bbdcf  pop     rbp
0x1800bbdd0  retn
```
