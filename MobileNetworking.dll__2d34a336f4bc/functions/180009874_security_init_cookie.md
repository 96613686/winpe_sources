# __security_init_cookie

- ea: `0x180009874`
- end: `0x180009929`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009800`

## callees

- `0x180009874`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800098d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800098d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800098c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800098c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800098b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800098b7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800098a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800098a9`

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
0x180009874  mov     [rsp-8+arg_10], rbx
0x180009879  push    rbp
0x18000987a  mov     rbp, rsp
0x18000987d  sub     rsp, 30h
0x180009881  mov     rax, cs:__security_cookie
0x180009888  mov     rbx, 2B992DDFA232h
0x180009892  cmp     rax, rbx
0x180009895  jnz     short loc_180009914
0x180009897  xor     eax, eax
0x180009899  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000989d  mov     [rbp+var_10], rax
0x1800098a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800098a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800098a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800098af  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800098b3  mov     [rbp+var_10], rax
0x1800098b7  call    cs:__imp_GetCurrentThreadId
0x1800098bd  mov     eax, eax
0x1800098bf  xor     [rbp+var_10], rax
0x1800098c3  call    cs:__imp_GetCurrentProcessId
0x1800098c9  mov     eax, eax
0x1800098cb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800098cf  xor     [rbp+var_10], rax
0x1800098d3  call    cs:__imp_QueryPerformanceCounter
0x1800098d9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800098dc  lea     rcx, [rbp+var_10]
0x1800098e0  shl     rax, 20h
0x1800098e4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800098e8  xor     rax, [rbp+var_10]
0x1800098ec  xor     rax, rcx
0x1800098ef  mov     rcx, 0FFFFFFFFFFFFh
0x1800098f9  and     rax, rcx
0x1800098fc  mov     rcx, 2B992DDFA233h
0x180009906  cmp     rax, rbx
0x180009909  cmovz   rax, rcx
0x18000990d  mov     cs:__security_cookie, rax
0x180009914  mov     rbx, [rsp+30h+arg_10]
0x180009919  not     rax
0x18000991c  mov     cs:__security_cookie_complement, rax
0x180009923  add     rsp, 30h
0x180009927  pop     rbp
0x180009928  retn
```
