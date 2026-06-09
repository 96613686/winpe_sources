# __security_init_cookie

- ea: `0x180005ab8`
- end: `0x180005b6d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004f50`

## callees

- `0x180005ab8`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005b17`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005b17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005b07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005afb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005afb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005aed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005aed`

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
0x180005ab8  mov     [rsp-8+arg_10], rbx
0x180005abd  push    rbp
0x180005abe  mov     rbp, rsp
0x180005ac1  sub     rsp, 30h
0x180005ac5  mov     rax, cs:__security_cookie
0x180005acc  mov     rbx, 2B992DDFA232h
0x180005ad6  cmp     rax, rbx
0x180005ad9  jnz     short loc_180005B58
0x180005adb  xor     eax, eax
0x180005add  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005ae1  mov     [rbp+var_10], rax
0x180005ae5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005ae9  mov     qword ptr [rbp+PerformanceCount], rax
0x180005aed  call    cs:__imp_GetSystemTimeAsFileTime
0x180005af3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005af7  mov     [rbp+var_10], rax
0x180005afb  call    cs:__imp_GetCurrentThreadId
0x180005b01  mov     eax, eax
0x180005b03  xor     [rbp+var_10], rax
0x180005b07  call    cs:__imp_GetCurrentProcessId
0x180005b0d  mov     eax, eax
0x180005b0f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005b13  xor     [rbp+var_10], rax
0x180005b17  call    cs:__imp_QueryPerformanceCounter
0x180005b1d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005b20  lea     rcx, [rbp+var_10]
0x180005b24  shl     rax, 20h
0x180005b28  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005b2c  xor     rax, [rbp+var_10]
0x180005b30  xor     rax, rcx
0x180005b33  mov     rcx, 0FFFFFFFFFFFFh
0x180005b3d  and     rax, rcx
0x180005b40  mov     rcx, 2B992DDFA233h
0x180005b4a  cmp     rax, rbx
0x180005b4d  cmovz   rax, rcx
0x180005b51  mov     cs:__security_cookie, rax
0x180005b58  mov     rbx, [rsp+30h+arg_10]
0x180005b5d  not     rax
0x180005b60  mov     cs:__security_cookie_complement, rax
0x180005b67  add     rsp, 30h
0x180005b6b  pop     rbp
0x180005b6c  retn
```
