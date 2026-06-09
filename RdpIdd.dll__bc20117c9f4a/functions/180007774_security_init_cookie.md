# __security_init_cookie

- ea: `0x180007774`
- end: `0x180007829`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006f10`

## callees

- `0x180007774`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800077c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800077c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800077d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800077d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800077a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800077a9`

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
0x180007774  mov     [rsp-8+arg_10], rbx
0x180007779  push    rbp
0x18000777a  mov     rbp, rsp
0x18000777d  sub     rsp, 30h
0x180007781  mov     rax, cs:__security_cookie
0x180007788  mov     rbx, 2B992DDFA232h
0x180007792  cmp     rax, rbx
0x180007795  jnz     short loc_180007814
0x180007797  xor     eax, eax
0x180007799  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000779d  mov     [rbp+var_10], rax
0x1800077a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800077a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800077a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800077af  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800077b3  mov     [rbp+var_10], rax
0x1800077b7  call    cs:__imp_GetCurrentThreadId
0x1800077bd  mov     eax, eax
0x1800077bf  xor     [rbp+var_10], rax
0x1800077c3  call    cs:__imp_GetCurrentProcessId
0x1800077c9  mov     eax, eax
0x1800077cb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800077cf  xor     [rbp+var_10], rax
0x1800077d3  call    cs:__imp_QueryPerformanceCounter
0x1800077d9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800077dc  lea     rcx, [rbp+var_10]
0x1800077e0  shl     rax, 20h
0x1800077e4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800077e8  xor     rax, [rbp+var_10]
0x1800077ec  xor     rax, rcx
0x1800077ef  mov     rcx, 0FFFFFFFFFFFFh
0x1800077f9  and     rax, rcx
0x1800077fc  mov     rcx, 2B992DDFA233h
0x180007806  cmp     rax, rbx
0x180007809  cmovz   rax, rcx
0x18000780d  mov     cs:__security_cookie, rax
0x180007814  mov     rbx, [rsp+30h+arg_10]
0x180007819  not     rax
0x18000781c  mov     cs:__security_cookie_complement, rax
0x180007823  add     rsp, 30h
0x180007827  pop     rbp
0x180007828  retn
```
