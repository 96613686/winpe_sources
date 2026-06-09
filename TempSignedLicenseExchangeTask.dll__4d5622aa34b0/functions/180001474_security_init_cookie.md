# __security_init_cookie

- ea: `0x180001474`
- end: `0x180001529`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013b0`

## callees

- `0x180001474`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800014c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800014c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800014b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800014b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800014d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800014d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800014a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800014a9`

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
0x180001474  mov     [rsp-8+arg_10], rbx
0x180001479  push    rbp
0x18000147a  mov     rbp, rsp
0x18000147d  sub     rsp, 30h
0x180001481  mov     rax, cs:__security_cookie
0x180001488  mov     rbx, 2B992DDFA232h
0x180001492  cmp     rax, rbx
0x180001495  jnz     short loc_180001514
0x180001497  xor     eax, eax
0x180001499  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000149d  mov     [rbp+var_10], rax
0x1800014a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800014a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800014a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800014af  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800014b3  mov     [rbp+var_10], rax
0x1800014b7  call    cs:__imp_GetCurrentThreadId
0x1800014bd  mov     eax, eax
0x1800014bf  xor     [rbp+var_10], rax
0x1800014c3  call    cs:__imp_GetCurrentProcessId
0x1800014c9  mov     eax, eax
0x1800014cb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800014cf  xor     [rbp+var_10], rax
0x1800014d3  call    cs:__imp_QueryPerformanceCounter
0x1800014d9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800014dc  lea     rcx, [rbp+var_10]
0x1800014e0  shl     rax, 20h
0x1800014e4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800014e8  xor     rax, [rbp+var_10]
0x1800014ec  xor     rax, rcx
0x1800014ef  mov     rcx, 0FFFFFFFFFFFFh
0x1800014f9  and     rax, rcx
0x1800014fc  mov     rcx, 2B992DDFA233h
0x180001506  cmp     rax, rbx
0x180001509  cmovz   rax, rcx
0x18000150d  mov     cs:__security_cookie, rax
0x180001514  mov     rbx, [rsp+30h+arg_10]
0x180001519  not     rax
0x18000151c  mov     cs:__security_cookie_complement, rax
0x180001523  add     rsp, 30h
0x180001527  pop     rbp
0x180001528  retn
```
