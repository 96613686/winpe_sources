# __security_init_cookie

- ea: `0x180001754`
- end: `0x180001831`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013e0`

## callees

- `0x180001754`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1800017b3`
- `KERNEL32!GetTickCount` at `0x1800017c3`
- `KERNEL32!GetTickCount` at `0x1800017b3`
- `KERNEL32!GetTickCount` at `0x1800017c3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000178d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000178d`
- `KERNEL32!GetCurrentThreadId` at `0x1800017a7`
- `KERNEL32!GetCurrentThreadId` at `0x1800017a7`
- `KERNEL32!GetCurrentProcessId` at `0x18000179b`
- `KERNEL32!GetCurrentProcessId` at `0x18000179b`
- `KERNEL32!QueryPerformanceCounter` at `0x1800017de`
- `KERNEL32!QueryPerformanceCounter` at `0x1800017de`

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
0x180001754  mov     [rsp-8+arg_18], rbx
0x180001759  push    rbp
0x18000175a  mov     rbp, rsp
0x18000175d  sub     rsp, 20h
0x180001761  xor     eax, eax
0x180001763  mov     rbx, 2B992DDFA232h
0x18000176d  mov     [rbp+arg_0], rax
0x180001771  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001775  mov     qword ptr [rbp+PerformanceCount], rax
0x180001779  mov     rax, cs:__security_cookie
0x180001780  cmp     rax, rbx
0x180001783  jnz     loc_18000181C
0x180001789  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000178d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001793  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001797  mov     [rbp+arg_0], rax
0x18000179b  call    cs:__imp_GetCurrentProcessId
0x1800017a1  mov     eax, eax
0x1800017a3  xor     [rbp+arg_0], rax
0x1800017a7  call    cs:__imp_GetCurrentThreadId
0x1800017ad  mov     eax, eax
0x1800017af  xor     [rbp+arg_0], rax
0x1800017b3  call    cs:__imp_GetTickCount
0x1800017b9  mov     eax, eax
0x1800017bb  shl     rax, 18h
0x1800017bf  xor     [rbp+arg_0], rax
0x1800017c3  call    cs:__imp_GetTickCount
0x1800017c9  mov     eax, eax
0x1800017cb  lea     rcx, [rbp+arg_0]
0x1800017cf  xor     rax, [rbp+arg_0]
0x1800017d3  xor     rax, rcx
0x1800017d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800017da  mov     [rbp+arg_0], rax
0x1800017de  call    cs:__imp_QueryPerformanceCounter
0x1800017e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800017e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800017f1  shl     rax, 20h
0x1800017f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800017f9  xor     rax, [rbp+arg_0]
0x1800017fd  and     rax, rcx
0x180001800  mov     rcx, rax
0x180001803  cmp     rax, rbx
0x180001806  jnz     short loc_180001815
0x180001808  mov     rax, 2B992DDFA233h
0x180001812  mov     rcx, rax
0x180001815  mov     cs:__security_cookie, rcx
0x18000181c  mov     rbx, [rsp+20h+arg_18]
0x180001821  not     rax
0x180001824  mov     cs:__security_cookie_complement, rax
0x18000182b  add     rsp, 20h
0x18000182f  pop     rbp
0x180001830  retn
```
