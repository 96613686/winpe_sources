# __security_init_cookie

- ea: `0x14000262c`
- end: `0x1400026e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002330`

## callees

- `0x14000262c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000267b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000267b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000266f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000266f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000268b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000268b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002661`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002661`

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
0x14000262c  mov     [rsp-8+arg_10], rbx
0x140002631  push    rbp
0x140002632  mov     rbp, rsp
0x140002635  sub     rsp, 30h
0x140002639  mov     rax, cs:__security_cookie
0x140002640  mov     rbx, 2B992DDFA232h
0x14000264a  cmp     rax, rbx
0x14000264d  jnz     short loc_1400026CC
0x14000264f  xor     eax, eax
0x140002651  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002655  mov     [rbp+var_10], rax
0x140002659  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000265d  mov     qword ptr [rbp+PerformanceCount], rax
0x140002661  call    cs:__imp_GetSystemTimeAsFileTime
0x140002667  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000266b  mov     [rbp+var_10], rax
0x14000266f  call    cs:__imp_GetCurrentThreadId
0x140002675  mov     eax, eax
0x140002677  xor     [rbp+var_10], rax
0x14000267b  call    cs:__imp_GetCurrentProcessId
0x140002681  mov     eax, eax
0x140002683  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002687  xor     [rbp+var_10], rax
0x14000268b  call    cs:__imp_QueryPerformanceCounter
0x140002691  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002694  lea     rcx, [rbp+var_10]
0x140002698  shl     rax, 20h
0x14000269c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400026a0  xor     rax, [rbp+var_10]
0x1400026a4  xor     rax, rcx
0x1400026a7  mov     rcx, 0FFFFFFFFFFFFh
0x1400026b1  and     rax, rcx
0x1400026b4  mov     rcx, 2B992DDFA233h
0x1400026be  cmp     rax, rbx
0x1400026c1  cmovz   rax, rcx
0x1400026c5  mov     cs:__security_cookie, rax
0x1400026cc  mov     rbx, [rsp+30h+arg_10]
0x1400026d1  not     rax
0x1400026d4  mov     cs:__security_cookie_complement, rax
0x1400026db  add     rsp, 30h
0x1400026df  pop     rbp
0x1400026e0  retn
```
