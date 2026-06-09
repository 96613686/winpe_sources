# __security_init_cookie

- ea: `0x1800021c8`
- end: `0x18000227d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ce0`

## callees

- `0x1800021c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000220b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000220b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002217`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002227`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002227`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800021fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800021fd`

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
0x1800021c8  mov     [rsp-8+arg_10], rbx
0x1800021cd  push    rbp
0x1800021ce  mov     rbp, rsp
0x1800021d1  sub     rsp, 30h
0x1800021d5  mov     rax, cs:__security_cookie
0x1800021dc  mov     rbx, 2B992DDFA232h
0x1800021e6  cmp     rax, rbx
0x1800021e9  jnz     short loc_180002268
0x1800021eb  xor     eax, eax
0x1800021ed  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800021f1  mov     [rbp+var_10], rax
0x1800021f5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800021f9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800021fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002203  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002207  mov     [rbp+var_10], rax
0x18000220b  call    cs:__imp_GetCurrentThreadId
0x180002211  mov     eax, eax
0x180002213  xor     [rbp+var_10], rax
0x180002217  call    cs:__imp_GetCurrentProcessId
0x18000221d  mov     eax, eax
0x18000221f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002223  xor     [rbp+var_10], rax
0x180002227  call    cs:__imp_QueryPerformanceCounter
0x18000222d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002230  lea     rcx, [rbp+var_10]
0x180002234  shl     rax, 20h
0x180002238  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000223c  xor     rax, [rbp+var_10]
0x180002240  xor     rax, rcx
0x180002243  mov     rcx, 0FFFFFFFFFFFFh
0x18000224d  and     rax, rcx
0x180002250  mov     rcx, 2B992DDFA233h
0x18000225a  cmp     rax, rbx
0x18000225d  cmovz   rax, rcx
0x180002261  mov     cs:__security_cookie, rax
0x180002268  mov     rbx, [rsp+30h+arg_10]
0x18000226d  not     rax
0x180002270  mov     cs:__security_cookie_complement, rax
0x180002277  add     rsp, 30h
0x18000227b  pop     rbp
0x18000227c  retn
```
