# __security_init_cookie

- ea: `0x180002f54`
- end: `0x180003009`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002330`

## callees

- `0x180002f54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002fa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002fa3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002fb3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002fb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f89`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002f89`

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
0x180002f54  mov     [rsp-8+arg_10], rbx
0x180002f59  push    rbp
0x180002f5a  mov     rbp, rsp
0x180002f5d  sub     rsp, 30h
0x180002f61  mov     rax, cs:__security_cookie
0x180002f68  mov     rbx, 2B992DDFA232h
0x180002f72  cmp     rax, rbx
0x180002f75  jnz     short loc_180002FF4
0x180002f77  xor     eax, eax
0x180002f79  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002f7d  mov     [rbp+var_10], rax
0x180002f81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002f85  mov     qword ptr [rbp+PerformanceCount], rax
0x180002f89  call    cs:__imp_GetSystemTimeAsFileTime
0x180002f8f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002f93  mov     [rbp+var_10], rax
0x180002f97  call    cs:__imp_GetCurrentThreadId
0x180002f9d  mov     eax, eax
0x180002f9f  xor     [rbp+var_10], rax
0x180002fa3  call    cs:__imp_GetCurrentProcessId
0x180002fa9  mov     eax, eax
0x180002fab  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002faf  xor     [rbp+var_10], rax
0x180002fb3  call    cs:__imp_QueryPerformanceCounter
0x180002fb9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002fbc  lea     rcx, [rbp+var_10]
0x180002fc0  shl     rax, 20h
0x180002fc4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002fc8  xor     rax, [rbp+var_10]
0x180002fcc  xor     rax, rcx
0x180002fcf  mov     rcx, 0FFFFFFFFFFFFh
0x180002fd9  and     rax, rcx
0x180002fdc  mov     rcx, 2B992DDFA233h
0x180002fe6  cmp     rax, rbx
0x180002fe9  cmovz   rax, rcx
0x180002fed  mov     cs:__security_cookie, rax
0x180002ff4  mov     rbx, [rsp+30h+arg_10]
0x180002ff9  not     rax
0x180002ffc  mov     cs:__security_cookie_complement, rax
0x180003003  add     rsp, 30h
0x180003007  pop     rbp
0x180003008  retn
```
