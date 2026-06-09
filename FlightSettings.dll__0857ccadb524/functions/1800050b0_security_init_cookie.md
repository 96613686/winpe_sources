# __security_init_cookie

- ea: `0x1800050b0`
- end: `0x180005165`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004b30`

## callees

- `0x1800050b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050ff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800050e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800050e5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000510f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000510f`

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
0x1800050b0  mov     [rsp-8+arg_10], rbx
0x1800050b5  push    rbp
0x1800050b6  mov     rbp, rsp
0x1800050b9  sub     rsp, 30h
0x1800050bd  mov     rax, cs:__security_cookie
0x1800050c4  mov     rbx, 2B992DDFA232h
0x1800050ce  cmp     rax, rbx
0x1800050d1  jnz     short loc_180005150
0x1800050d3  xor     eax, eax
0x1800050d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800050d9  mov     [rbp+var_10], rax
0x1800050dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800050e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800050e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800050eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800050ef  mov     [rbp+var_10], rax
0x1800050f3  call    cs:__imp_GetCurrentThreadId
0x1800050f9  mov     eax, eax
0x1800050fb  xor     [rbp+var_10], rax
0x1800050ff  call    cs:__imp_GetCurrentProcessId
0x180005105  mov     eax, eax
0x180005107  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000510b  xor     [rbp+var_10], rax
0x18000510f  call    cs:__imp_QueryPerformanceCounter
0x180005115  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005118  lea     rcx, [rbp+var_10]
0x18000511c  shl     rax, 20h
0x180005120  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005124  xor     rax, [rbp+var_10]
0x180005128  xor     rax, rcx
0x18000512b  mov     rcx, 0FFFFFFFFFFFFh
0x180005135  and     rax, rcx
0x180005138  mov     rcx, 2B992DDFA233h
0x180005142  cmp     rax, rbx
0x180005145  cmovz   rax, rcx
0x180005149  mov     cs:__security_cookie, rax
0x180005150  mov     rbx, [rsp+30h+arg_10]
0x180005155  not     rax
0x180005158  mov     cs:__security_cookie_complement, rax
0x18000515f  add     rsp, 30h
0x180005163  pop     rbp
0x180005164  retn
```
