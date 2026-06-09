# __security_init_cookie

- ea: `0x1400017fc`
- end: `0x1400018b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001500`

## callees

- `0x1400017fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000183f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000183f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000184b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000184b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000185b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000185b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001831`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001831`

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
0x1400017fc  mov     [rsp-8+arg_10], rbx
0x140001801  push    rbp
0x140001802  mov     rbp, rsp
0x140001805  sub     rsp, 30h
0x140001809  mov     rax, cs:__security_cookie
0x140001810  mov     rbx, 2B992DDFA232h
0x14000181a  cmp     rax, rbx
0x14000181d  jnz     short loc_14000189C
0x14000181f  xor     eax, eax
0x140001821  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001825  mov     [rbp+var_10], rax
0x140001829  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000182d  mov     qword ptr [rbp+PerformanceCount], rax
0x140001831  call    cs:__imp_GetSystemTimeAsFileTime
0x140001837  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000183b  mov     [rbp+var_10], rax
0x14000183f  call    cs:__imp_GetCurrentThreadId
0x140001845  mov     eax, eax
0x140001847  xor     [rbp+var_10], rax
0x14000184b  call    cs:__imp_GetCurrentProcessId
0x140001851  mov     eax, eax
0x140001853  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001857  xor     [rbp+var_10], rax
0x14000185b  call    cs:__imp_QueryPerformanceCounter
0x140001861  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001864  lea     rcx, [rbp+var_10]
0x140001868  shl     rax, 20h
0x14000186c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001870  xor     rax, [rbp+var_10]
0x140001874  xor     rax, rcx
0x140001877  mov     rcx, 0FFFFFFFFFFFFh
0x140001881  and     rax, rcx
0x140001884  mov     rcx, 2B992DDFA233h
0x14000188e  cmp     rax, rbx
0x140001891  cmovz   rax, rcx
0x140001895  mov     cs:__security_cookie, rax
0x14000189c  mov     rbx, [rsp+30h+arg_10]
0x1400018a1  not     rax
0x1400018a4  mov     cs:__security_cookie_complement, rax
0x1400018ab  add     rsp, 30h
0x1400018af  pop     rbp
0x1400018b0  retn
```
