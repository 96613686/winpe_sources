# __security_init_cookie

- ea: `0x140002680`
- end: `0x140002735`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400023b0`

## callees

- `0x140002680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400026cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400026cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400026c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400026c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400026b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400026b5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400026df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400026df`

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
0x140002680  mov     [rsp-8+arg_10], rbx
0x140002685  push    rbp
0x140002686  mov     rbp, rsp
0x140002689  sub     rsp, 30h
0x14000268d  mov     rax, cs:__security_cookie
0x140002694  mov     rbx, 2B992DDFA232h
0x14000269e  cmp     rax, rbx
0x1400026a1  jnz     short loc_140002720
0x1400026a3  xor     eax, eax
0x1400026a5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400026a9  mov     [rbp+var_10], rax
0x1400026ad  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400026b1  mov     qword ptr [rbp+PerformanceCount], rax
0x1400026b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400026bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400026bf  mov     [rbp+var_10], rax
0x1400026c3  call    cs:__imp_GetCurrentThreadId
0x1400026c9  mov     eax, eax
0x1400026cb  xor     [rbp+var_10], rax
0x1400026cf  call    cs:__imp_GetCurrentProcessId
0x1400026d5  mov     eax, eax
0x1400026d7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400026db  xor     [rbp+var_10], rax
0x1400026df  call    cs:__imp_QueryPerformanceCounter
0x1400026e5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400026e8  lea     rcx, [rbp+var_10]
0x1400026ec  shl     rax, 20h
0x1400026f0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400026f4  xor     rax, [rbp+var_10]
0x1400026f8  xor     rax, rcx
0x1400026fb  mov     rcx, 0FFFFFFFFFFFFh
0x140002705  and     rax, rcx
0x140002708  mov     rcx, 2B992DDFA233h
0x140002712  cmp     rax, rbx
0x140002715  cmovz   rax, rcx
0x140002719  mov     cs:__security_cookie, rax
0x140002720  mov     rbx, [rsp+30h+arg_10]
0x140002725  not     rax
0x140002728  mov     cs:__security_cookie_complement, rax
0x14000272f  add     rsp, 30h
0x140002733  pop     rbp
0x140002734  retn
```
