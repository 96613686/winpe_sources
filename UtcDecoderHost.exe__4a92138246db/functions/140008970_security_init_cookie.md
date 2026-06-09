# __security_init_cookie

- ea: `0x140008970`
- end: `0x140008a25`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008630`

## callees

- `0x140008970`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400089bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400089bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400089b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400089b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400089a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400089a5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400089cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400089cf`

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
0x140008970  mov     [rsp-8+arg_10], rbx
0x140008975  push    rbp
0x140008976  mov     rbp, rsp
0x140008979  sub     rsp, 30h
0x14000897d  mov     rax, cs:__security_cookie
0x140008984  mov     rbx, 2B992DDFA232h
0x14000898e  cmp     rax, rbx
0x140008991  jnz     short loc_140008A10
0x140008993  xor     eax, eax
0x140008995  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140008999  mov     [rbp+var_10], rax
0x14000899d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400089a1  mov     qword ptr [rbp+PerformanceCount], rax
0x1400089a5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400089ab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400089af  mov     [rbp+var_10], rax
0x1400089b3  call    cs:__imp_GetCurrentThreadId
0x1400089b9  mov     eax, eax
0x1400089bb  xor     [rbp+var_10], rax
0x1400089bf  call    cs:__imp_GetCurrentProcessId
0x1400089c5  mov     eax, eax
0x1400089c7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400089cb  xor     [rbp+var_10], rax
0x1400089cf  call    cs:__imp_QueryPerformanceCounter
0x1400089d5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400089d8  lea     rcx, [rbp+var_10]
0x1400089dc  shl     rax, 20h
0x1400089e0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400089e4  xor     rax, [rbp+var_10]
0x1400089e8  xor     rax, rcx
0x1400089eb  mov     rcx, 0FFFFFFFFFFFFh
0x1400089f5  and     rax, rcx
0x1400089f8  mov     rcx, 2B992DDFA233h
0x140008a02  cmp     rax, rbx
0x140008a05  cmovz   rax, rcx
0x140008a09  mov     cs:__security_cookie, rax
0x140008a10  mov     rbx, [rsp+30h+arg_10]
0x140008a15  not     rax
0x140008a18  mov     cs:__security_cookie_complement, rax
0x140008a1f  add     rsp, 30h
0x140008a23  pop     rbp
0x140008a24  retn
```
