# __security_init_cookie

- ea: `0x140003254`
- end: `0x140003331`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003020`

## callees

- `0x140003254`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400032a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400032a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000329b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000329b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400032de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400032de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000328d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000328d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400032b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400032c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400032b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400032c3`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x140003254  mov     [rsp-8+arg_18], rbx
0x140003259  push    rbp
0x14000325a  mov     rbp, rsp
0x14000325d  sub     rsp, 20h
0x140003261  xor     eax, eax
0x140003263  mov     rbx, 2B992DDFA232h
0x14000326d  mov     [rbp+arg_0], rax
0x140003271  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140003275  mov     qword ptr [rbp+PerformanceCount], rax
0x140003279  mov     rax, cs:__security_cookie
0x140003280  cmp     rax, rbx
0x140003283  jnz     loc_14000331C
0x140003289  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000328d  call    cs:__imp_GetSystemTimeAsFileTime
0x140003293  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140003297  mov     [rbp+arg_0], rax
0x14000329b  call    cs:__imp_GetCurrentProcessId
0x1400032a1  mov     eax, eax
0x1400032a3  xor     [rbp+arg_0], rax
0x1400032a7  call    cs:__imp_GetCurrentThreadId
0x1400032ad  mov     eax, eax
0x1400032af  xor     [rbp+arg_0], rax
0x1400032b3  call    cs:__imp_GetTickCount
0x1400032b9  mov     eax, eax
0x1400032bb  shl     rax, 18h
0x1400032bf  xor     [rbp+arg_0], rax
0x1400032c3  call    cs:__imp_GetTickCount
0x1400032c9  mov     eax, eax
0x1400032cb  lea     rcx, [rbp+arg_0]
0x1400032cf  xor     rax, [rbp+arg_0]
0x1400032d3  xor     rax, rcx
0x1400032d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400032da  mov     [rbp+arg_0], rax
0x1400032de  call    cs:__imp_QueryPerformanceCounter
0x1400032e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400032e7  mov     rcx, 0FFFFFFFFFFFFh
0x1400032f1  shl     rax, 20h
0x1400032f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400032f9  xor     rax, [rbp+arg_0]
0x1400032fd  and     rax, rcx
0x140003300  mov     rcx, rax
0x140003303  cmp     rax, rbx
0x140003306  jnz     short loc_140003315
0x140003308  mov     rax, 2B992DDFA233h
0x140003312  mov     rcx, rax
0x140003315  mov     cs:__security_cookie, rcx
0x14000331c  mov     rbx, [rsp+20h+arg_18]
0x140003321  not     rax
0x140003324  mov     cs:__security_cookie_complement, rax
0x14000332b  add     rsp, 20h
0x14000332f  pop     rbp
0x140003330  retn
```
