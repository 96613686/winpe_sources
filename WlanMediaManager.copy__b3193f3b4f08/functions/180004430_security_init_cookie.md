# __security_init_cookie

- ea: `0x180004430`
- end: `0x1800044e5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003e80`

## callees

- `0x180004430`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000447f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000447f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000448f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000448f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004465`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004465`

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
0x180004430  mov     [rsp-8+arg_10], rbx
0x180004435  push    rbp
0x180004436  mov     rbp, rsp
0x180004439  sub     rsp, 30h
0x18000443d  mov     rax, cs:__security_cookie
0x180004444  mov     rbx, 2B992DDFA232h
0x18000444e  cmp     rax, rbx
0x180004451  jnz     short loc_1800044D0
0x180004453  xor     eax, eax
0x180004455  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004459  mov     [rbp+var_10], rax
0x18000445d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004461  mov     qword ptr [rbp+PerformanceCount], rax
0x180004465  call    cs:__imp_GetSystemTimeAsFileTime
0x18000446b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000446f  mov     [rbp+var_10], rax
0x180004473  call    cs:__imp_GetCurrentThreadId
0x180004479  mov     eax, eax
0x18000447b  xor     [rbp+var_10], rax
0x18000447f  call    cs:__imp_GetCurrentProcessId
0x180004485  mov     eax, eax
0x180004487  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000448b  xor     [rbp+var_10], rax
0x18000448f  call    cs:__imp_QueryPerformanceCounter
0x180004495  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004498  lea     rcx, [rbp+var_10]
0x18000449c  shl     rax, 20h
0x1800044a0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800044a4  xor     rax, [rbp+var_10]
0x1800044a8  xor     rax, rcx
0x1800044ab  mov     rcx, 0FFFFFFFFFFFFh
0x1800044b5  and     rax, rcx
0x1800044b8  mov     rcx, 2B992DDFA233h
0x1800044c2  cmp     rax, rbx
0x1800044c5  cmovz   rax, rcx
0x1800044c9  mov     cs:__security_cookie, rax
0x1800044d0  mov     rbx, [rsp+30h+arg_10]
0x1800044d5  not     rax
0x1800044d8  mov     cs:__security_cookie_complement, rax
0x1800044df  add     rsp, 30h
0x1800044e3  pop     rbp
0x1800044e4  retn
```
