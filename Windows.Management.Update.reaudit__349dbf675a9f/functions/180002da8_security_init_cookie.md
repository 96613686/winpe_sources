# __security_init_cookie

- ea: `0x180002da8`
- end: `0x180002e59`
- name: `__security_init_cookie`
- size: `177`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002830`

## callees

- `0x180002da8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002df3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002df3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002de7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002de7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002e03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002e03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002dd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002dd9`

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
0x180002da8  mov     [rsp-8+arg_10], rbx
0x180002dad  push    rbp
0x180002dae  mov     rbp, rsp
0x180002db1  sub     rsp, 30h
0x180002db5  mov     rax, cs:__security_cookie
0x180002dbc  mov     rbx, 2B992DDFA232h
0x180002dc6  cmp     rax, rbx
0x180002dc9  jnz     short loc_180002E44
0x180002dcb  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002dd0  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002dd4  and     qword ptr [rbp+PerformanceCount], 0
0x180002dd9  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ddf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002de3  mov     [rbp+var_10], rax
0x180002de7  call    cs:__imp_GetCurrentThreadId
0x180002ded  mov     eax, eax
0x180002def  xor     [rbp+var_10], rax
0x180002df3  call    cs:__imp_GetCurrentProcessId
0x180002df9  mov     eax, eax
0x180002dfb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002dff  xor     [rbp+var_10], rax
0x180002e03  call    cs:__imp_QueryPerformanceCounter
0x180002e09  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002e0c  lea     rcx, [rbp+var_10]
0x180002e10  shl     rax, 20h
0x180002e14  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002e18  xor     rax, [rbp+var_10]
0x180002e1c  xor     rax, rcx
0x180002e1f  mov     rcx, 0FFFFFFFFFFFFh
0x180002e29  and     rax, rcx
0x180002e2c  mov     rcx, 2B992DDFA233h
0x180002e36  cmp     rax, rbx
0x180002e39  cmovz   rax, rcx
0x180002e3d  mov     cs:__security_cookie, rax
0x180002e44  mov     rbx, [rsp+30h+arg_10]
0x180002e49  not     rax
0x180002e4c  mov     cs:__security_cookie_complement, rax
0x180002e53  add     rsp, 30h
0x180002e57  pop     rbp
0x180002e58  retn
```
