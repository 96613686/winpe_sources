# __security_init_cookie

- ea: `0x180001e94`
- end: `0x180001f49`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001740`

## callees

- `0x180001e94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001ee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001ee3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ed7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ed7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ec9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ec9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001ef3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001ef3`

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
0x180001e94  mov     [rsp-8+arg_10], rbx
0x180001e99  push    rbp
0x180001e9a  mov     rbp, rsp
0x180001e9d  sub     rsp, 30h
0x180001ea1  mov     rax, cs:__security_cookie
0x180001ea8  mov     rbx, 2B992DDFA232h
0x180001eb2  cmp     rax, rbx
0x180001eb5  jnz     short loc_180001F34
0x180001eb7  xor     eax, eax
0x180001eb9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001ebd  mov     [rbp+var_10], rax
0x180001ec1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ec5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ec9  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ecf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ed3  mov     [rbp+var_10], rax
0x180001ed7  call    cs:__imp_GetCurrentThreadId
0x180001edd  mov     eax, eax
0x180001edf  xor     [rbp+var_10], rax
0x180001ee3  call    cs:__imp_GetCurrentProcessId
0x180001ee9  mov     eax, eax
0x180001eeb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001eef  xor     [rbp+var_10], rax
0x180001ef3  call    cs:__imp_QueryPerformanceCounter
0x180001ef9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001efc  lea     rcx, [rbp+var_10]
0x180001f00  shl     rax, 20h
0x180001f04  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f08  xor     rax, [rbp+var_10]
0x180001f0c  xor     rax, rcx
0x180001f0f  mov     rcx, 0FFFFFFFFFFFFh
0x180001f19  and     rax, rcx
0x180001f1c  mov     rcx, 2B992DDFA233h
0x180001f26  cmp     rax, rbx
0x180001f29  cmovz   rax, rcx
0x180001f2d  mov     cs:__security_cookie, rax
0x180001f34  mov     rbx, [rsp+30h+arg_10]
0x180001f39  not     rax
0x180001f3c  mov     cs:__security_cookie_complement, rax
0x180001f43  add     rsp, 30h
0x180001f47  pop     rbp
0x180001f48  retn
```
