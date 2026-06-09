# __security_init_cookie

- ea: `0x18000fb88`
- end: `0x18000fc3f`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f510`

## callees

- `0x18000fb88`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fbcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fbcd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fbd9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000fbd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fbbf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fbbf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000fbe9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000fbe9`

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
0x18000fb88  mov     [rsp-8+arg_10], rbx
0x18000fb8d  push    rbp
0x18000fb8e  mov     rbp, rsp
0x18000fb91  sub     rsp, 30h
0x18000fb95  mov     rax, cs:__security_cookie
0x18000fb9c  mov     rbx, 2B992DDFA232h
0x18000fba6  cmp     rax, rbx
0x18000fba9  jnz     short loc_18000FC2A
0x18000fbab  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fbaf  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000fbb7  mov     qword ptr [rbp+PerformanceCount], 0
0x18000fbbf  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fbc5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000fbc9  mov     [rbp+var_10], rax
0x18000fbcd  call    cs:__imp_GetCurrentThreadId
0x18000fbd3  mov     eax, eax
0x18000fbd5  xor     [rbp+var_10], rax
0x18000fbd9  call    cs:__imp_GetCurrentProcessId
0x18000fbdf  mov     eax, eax
0x18000fbe1  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000fbe5  xor     [rbp+var_10], rax
0x18000fbe9  call    cs:__imp_QueryPerformanceCounter
0x18000fbef  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000fbf2  lea     rcx, [rbp+var_10]
0x18000fbf6  shl     rax, 20h
0x18000fbfa  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000fbfe  xor     rax, [rbp+var_10]
0x18000fc02  xor     rax, rcx
0x18000fc05  mov     rcx, 0FFFFFFFFFFFFh
0x18000fc0f  and     rax, rcx
0x18000fc12  mov     rcx, 2B992DDFA233h
0x18000fc1c  cmp     rax, rbx
0x18000fc1f  cmovz   rax, rcx
0x18000fc23  mov     cs:__security_cookie, rax
0x18000fc2a  mov     rbx, [rsp+30h+arg_10]
0x18000fc2f  not     rax
0x18000fc32  mov     cs:__security_cookie_complement, rax
0x18000fc39  add     rsp, 30h
0x18000fc3d  pop     rbp
0x18000fc3e  retn
```
