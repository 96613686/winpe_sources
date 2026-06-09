# __security_init_cookie

- ea: `0x18000362c`
- end: `0x1800036e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002d70`

## callees

- `0x18000362c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000366f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000366f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000367b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000367b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000368b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000368b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003661`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003661`

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
0x18000362c  mov     [rsp-8+arg_10], rbx
0x180003631  push    rbp
0x180003632  mov     rbp, rsp
0x180003635  sub     rsp, 30h
0x180003639  mov     rax, cs:__security_cookie
0x180003640  mov     rbx, 2B992DDFA232h
0x18000364a  cmp     rax, rbx
0x18000364d  jnz     short loc_1800036CC
0x18000364f  xor     eax, eax
0x180003651  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003655  mov     [rbp+var_10], rax
0x180003659  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000365d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003661  call    cs:__imp_GetSystemTimeAsFileTime
0x180003667  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000366b  mov     [rbp+var_10], rax
0x18000366f  call    cs:__imp_GetCurrentThreadId
0x180003675  mov     eax, eax
0x180003677  xor     [rbp+var_10], rax
0x18000367b  call    cs:__imp_GetCurrentProcessId
0x180003681  mov     eax, eax
0x180003683  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003687  xor     [rbp+var_10], rax
0x18000368b  call    cs:__imp_QueryPerformanceCounter
0x180003691  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003694  lea     rcx, [rbp+var_10]
0x180003698  shl     rax, 20h
0x18000369c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800036a0  xor     rax, [rbp+var_10]
0x1800036a4  xor     rax, rcx
0x1800036a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800036b1  and     rax, rcx
0x1800036b4  mov     rcx, 2B992DDFA233h
0x1800036be  cmp     rax, rbx
0x1800036c1  cmovz   rax, rcx
0x1800036c5  mov     cs:__security_cookie, rax
0x1800036cc  mov     rbx, [rsp+30h+arg_10]
0x1800036d1  not     rax
0x1800036d4  mov     cs:__security_cookie_complement, rax
0x1800036db  add     rsp, 30h
0x1800036df  pop     rbp
0x1800036e0  retn
```
