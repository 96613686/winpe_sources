# __security_init_cookie

- ea: `0x180003010`
- end: `0x1800030c5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002a20`

## callees

- `0x180003010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000305f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000305f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003053`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003045`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003045`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000306f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000306f`

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
0x180003010  mov     [rsp-8+arg_10], rbx
0x180003015  push    rbp
0x180003016  mov     rbp, rsp
0x180003019  sub     rsp, 30h
0x18000301d  mov     rax, cs:__security_cookie
0x180003024  mov     rbx, 2B992DDFA232h
0x18000302e  cmp     rax, rbx
0x180003031  jnz     short loc_1800030B0
0x180003033  xor     eax, eax
0x180003035  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003039  mov     [rbp+var_10], rax
0x18000303d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003041  mov     qword ptr [rbp+PerformanceCount], rax
0x180003045  call    cs:__imp_GetSystemTimeAsFileTime
0x18000304b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000304f  mov     [rbp+var_10], rax
0x180003053  call    cs:__imp_GetCurrentThreadId
0x180003059  mov     eax, eax
0x18000305b  xor     [rbp+var_10], rax
0x18000305f  call    cs:__imp_GetCurrentProcessId
0x180003065  mov     eax, eax
0x180003067  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000306b  xor     [rbp+var_10], rax
0x18000306f  call    cs:__imp_QueryPerformanceCounter
0x180003075  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003078  lea     rcx, [rbp+var_10]
0x18000307c  shl     rax, 20h
0x180003080  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003084  xor     rax, [rbp+var_10]
0x180003088  xor     rax, rcx
0x18000308b  mov     rcx, 0FFFFFFFFFFFFh
0x180003095  and     rax, rcx
0x180003098  mov     rcx, 2B992DDFA233h
0x1800030a2  cmp     rax, rbx
0x1800030a5  cmovz   rax, rcx
0x1800030a9  mov     cs:__security_cookie, rax
0x1800030b0  mov     rbx, [rsp+30h+arg_10]
0x1800030b5  not     rax
0x1800030b8  mov     cs:__security_cookie_complement, rax
0x1800030bf  add     rsp, 30h
0x1800030c3  pop     rbp
0x1800030c4  retn
```
