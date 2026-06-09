# __security_init_cookie

- ea: `0x18000ef70`
- end: `0x18000f025`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000eb20`

## callees

- `0x18000ef70`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000efcf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000efcf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000efa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000efa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000efbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000efbf`

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
0x18000ef70  mov     [rsp-8+arg_10], rbx
0x18000ef75  push    rbp
0x18000ef76  mov     rbp, rsp
0x18000ef79  sub     rsp, 30h
0x18000ef7d  mov     rax, cs:__security_cookie
0x18000ef84  mov     rbx, 2B992DDFA232h
0x18000ef8e  cmp     rax, rbx
0x18000ef91  jnz     short loc_18000F010
0x18000ef93  xor     eax, eax
0x18000ef95  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ef99  mov     [rbp+var_10], rax
0x18000ef9d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000efa1  mov     qword ptr [rbp+PerformanceCount], rax
0x18000efa5  call    cs:__imp_GetSystemTimeAsFileTime
0x18000efab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000efaf  mov     [rbp+var_10], rax
0x18000efb3  call    cs:__imp_GetCurrentThreadId
0x18000efb9  mov     eax, eax
0x18000efbb  xor     [rbp+var_10], rax
0x18000efbf  call    cs:__imp_GetCurrentProcessId
0x18000efc5  mov     eax, eax
0x18000efc7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000efcb  xor     [rbp+var_10], rax
0x18000efcf  call    cs:__imp_QueryPerformanceCounter
0x18000efd5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000efd8  lea     rcx, [rbp+var_10]
0x18000efdc  shl     rax, 20h
0x18000efe0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000efe4  xor     rax, [rbp+var_10]
0x18000efe8  xor     rax, rcx
0x18000efeb  mov     rcx, 0FFFFFFFFFFFFh
0x18000eff5  and     rax, rcx
0x18000eff8  mov     rcx, 2B992DDFA233h
0x18000f002  cmp     rax, rbx
0x18000f005  cmovz   rax, rcx
0x18000f009  mov     cs:__security_cookie, rax
0x18000f010  mov     rbx, [rsp+30h+arg_10]
0x18000f015  not     rax
0x18000f018  mov     cs:__security_cookie_complement, rax
0x18000f01f  add     rsp, 30h
0x18000f023  pop     rbp
0x18000f024  retn
```
