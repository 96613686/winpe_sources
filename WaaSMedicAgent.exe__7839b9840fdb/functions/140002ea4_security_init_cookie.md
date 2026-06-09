# __security_init_cookie

- ea: `0x140002ea4`
- end: `0x140002f59`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002a00`

## callees

- `0x140002ea4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002ef3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002ef3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002ee7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002ee7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002f03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002f03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002ed9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002ed9`

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
0x140002ea4  mov     [rsp-8+arg_10], rbx
0x140002ea9  push    rbp
0x140002eaa  mov     rbp, rsp
0x140002ead  sub     rsp, 30h
0x140002eb1  mov     rax, cs:__security_cookie
0x140002eb8  mov     rbx, 2B992DDFA232h
0x140002ec2  cmp     rax, rbx
0x140002ec5  jnz     short loc_140002F44
0x140002ec7  xor     eax, eax
0x140002ec9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002ecd  mov     [rbp+var_10], rax
0x140002ed1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002ed5  mov     qword ptr [rbp+PerformanceCount], rax
0x140002ed9  call    cs:__imp_GetSystemTimeAsFileTime
0x140002edf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002ee3  mov     [rbp+var_10], rax
0x140002ee7  call    cs:__imp_GetCurrentThreadId
0x140002eed  mov     eax, eax
0x140002eef  xor     [rbp+var_10], rax
0x140002ef3  call    cs:__imp_GetCurrentProcessId
0x140002ef9  mov     eax, eax
0x140002efb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002eff  xor     [rbp+var_10], rax
0x140002f03  call    cs:__imp_QueryPerformanceCounter
0x140002f09  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002f0c  lea     rcx, [rbp+var_10]
0x140002f10  shl     rax, 20h
0x140002f14  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002f18  xor     rax, [rbp+var_10]
0x140002f1c  xor     rax, rcx
0x140002f1f  mov     rcx, 0FFFFFFFFFFFFh
0x140002f29  and     rax, rcx
0x140002f2c  mov     rcx, 2B992DDFA233h
0x140002f36  cmp     rax, rbx
0x140002f39  cmovz   rax, rcx
0x140002f3d  mov     cs:__security_cookie, rax
0x140002f44  mov     rbx, [rsp+30h+arg_10]
0x140002f49  not     rax
0x140002f4c  mov     cs:__security_cookie_complement, rax
0x140002f53  add     rsp, 30h
0x140002f57  pop     rbp
0x140002f58  retn
```
