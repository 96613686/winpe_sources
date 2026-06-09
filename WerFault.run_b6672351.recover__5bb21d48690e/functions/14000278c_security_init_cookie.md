# __security_init_cookie

- ea: `0x14000278c`
- end: `0x140002841`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002460`

## callees

- `0x14000278c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400027db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400027db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400027cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400027cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400027eb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400027eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400027c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400027c1`

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
0x14000278c  mov     [rsp-8+arg_10], rbx
0x140002791  push    rbp
0x140002792  mov     rbp, rsp
0x140002795  sub     rsp, 30h
0x140002799  mov     rax, cs:__security_cookie
0x1400027a0  mov     rbx, 2B992DDFA232h
0x1400027aa  cmp     rax, rbx
0x1400027ad  jnz     short loc_14000282C
0x1400027af  xor     eax, eax
0x1400027b1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400027b5  mov     [rbp+var_10], rax
0x1400027b9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400027bd  mov     qword ptr [rbp+PerformanceCount], rax
0x1400027c1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400027c7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400027cb  mov     [rbp+var_10], rax
0x1400027cf  call    cs:__imp_GetCurrentThreadId
0x1400027d5  mov     eax, eax
0x1400027d7  xor     [rbp+var_10], rax
0x1400027db  call    cs:__imp_GetCurrentProcessId
0x1400027e1  mov     eax, eax
0x1400027e3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400027e7  xor     [rbp+var_10], rax
0x1400027eb  call    cs:__imp_QueryPerformanceCounter
0x1400027f1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400027f4  lea     rcx, [rbp+var_10]
0x1400027f8  shl     rax, 20h
0x1400027fc  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002800  xor     rax, [rbp+var_10]
0x140002804  xor     rax, rcx
0x140002807  mov     rcx, 0FFFFFFFFFFFFh
0x140002811  and     rax, rcx
0x140002814  mov     rcx, 2B992DDFA233h
0x14000281e  cmp     rax, rbx
0x140002821  cmovz   rax, rcx
0x140002825  mov     cs:__security_cookie, rax
0x14000282c  mov     rbx, [rsp+30h+arg_10]
0x140002831  not     rax
0x140002834  mov     cs:__security_cookie_complement, rax
0x14000283b  add     rsp, 30h
0x14000283f  pop     rbp
0x140002840  retn
```
