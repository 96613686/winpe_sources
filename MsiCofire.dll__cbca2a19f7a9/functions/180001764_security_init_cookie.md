# __security_init_cookie

- ea: `0x180001764`
- end: `0x180001841`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001400`

## callees

- `0x180001764`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800017ee`
- `KERNEL32!QueryPerformanceCounter` at `0x1800017ee`
- `KERNEL32!GetCurrentProcessId` at `0x1800017ab`
- `KERNEL32!GetCurrentProcessId` at `0x1800017ab`
- `KERNEL32!GetCurrentThreadId` at `0x1800017b7`
- `KERNEL32!GetCurrentThreadId` at `0x1800017b7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000179d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000179d`
- `KERNEL32!GetTickCount` at `0x1800017c3`
- `KERNEL32!GetTickCount` at `0x1800017d3`
- `KERNEL32!GetTickCount` at `0x1800017c3`
- `KERNEL32!GetTickCount` at `0x1800017d3`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180001764  mov     [rsp-8+arg_18], rbx
0x180001769  push    rbp
0x18000176a  mov     rbp, rsp
0x18000176d  sub     rsp, 20h
0x180001771  xor     eax, eax
0x180001773  mov     rbx, 2B992DDFA232h
0x18000177d  mov     [rbp+arg_0], rax
0x180001781  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001785  mov     qword ptr [rbp+PerformanceCount], rax
0x180001789  mov     rax, cs:__security_cookie
0x180001790  cmp     rax, rbx
0x180001793  jnz     loc_18000182C
0x180001799  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000179d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800017a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800017a7  mov     [rbp+arg_0], rax
0x1800017ab  call    cs:__imp_GetCurrentProcessId
0x1800017b1  mov     eax, eax
0x1800017b3  xor     [rbp+arg_0], rax
0x1800017b7  call    cs:__imp_GetCurrentThreadId
0x1800017bd  mov     eax, eax
0x1800017bf  xor     [rbp+arg_0], rax
0x1800017c3  call    cs:__imp_GetTickCount
0x1800017c9  mov     eax, eax
0x1800017cb  shl     rax, 18h
0x1800017cf  xor     [rbp+arg_0], rax
0x1800017d3  call    cs:__imp_GetTickCount
0x1800017d9  mov     eax, eax
0x1800017db  lea     rcx, [rbp+arg_0]
0x1800017df  xor     rax, [rbp+arg_0]
0x1800017e3  xor     rax, rcx
0x1800017e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800017ea  mov     [rbp+arg_0], rax
0x1800017ee  call    cs:__imp_QueryPerformanceCounter
0x1800017f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800017f7  mov     rcx, 0FFFFFFFFFFFFh
0x180001801  shl     rax, 20h
0x180001805  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001809  xor     rax, [rbp+arg_0]
0x18000180d  and     rax, rcx
0x180001810  mov     rcx, rax
0x180001813  cmp     rax, rbx
0x180001816  jnz     short loc_180001825
0x180001818  mov     rax, 2B992DDFA233h
0x180001822  mov     rcx, rax
0x180001825  mov     cs:__security_cookie, rcx
0x18000182c  mov     rbx, [rsp+20h+arg_18]
0x180001831  not     rax
0x180001834  mov     cs:__security_cookie_complement, rax
0x18000183b  add     rsp, 20h
0x18000183f  pop     rbp
0x180001840  retn
```
