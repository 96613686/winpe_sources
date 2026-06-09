# __security_init_cookie

- ea: `0x180001884`
- end: `0x180001961`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001460`

## callees

- `0x180001884`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000190e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000190e`
- `KERNEL32!GetCurrentThreadId` at `0x1800018d7`
- `KERNEL32!GetCurrentThreadId` at `0x1800018d7`
- `KERNEL32!GetCurrentProcessId` at `0x1800018cb`
- `KERNEL32!GetCurrentProcessId` at `0x1800018cb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800018bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800018bd`
- `KERNEL32!GetTickCount` at `0x1800018e3`
- `KERNEL32!GetTickCount` at `0x1800018f3`
- `KERNEL32!GetTickCount` at `0x1800018e3`
- `KERNEL32!GetTickCount` at `0x1800018f3`

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
0x180001884  mov     [rsp-8+arg_18], rbx
0x180001889  push    rbp
0x18000188a  mov     rbp, rsp
0x18000188d  sub     rsp, 20h
0x180001891  xor     eax, eax
0x180001893  mov     rbx, 2B992DDFA232h
0x18000189d  mov     [rbp+arg_0], rax
0x1800018a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800018a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800018a9  mov     rax, cs:__security_cookie
0x1800018b0  cmp     rax, rbx
0x1800018b3  jnz     loc_18000194C
0x1800018b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800018bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800018c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800018c7  mov     [rbp+arg_0], rax
0x1800018cb  call    cs:__imp_GetCurrentProcessId
0x1800018d1  mov     eax, eax
0x1800018d3  xor     [rbp+arg_0], rax
0x1800018d7  call    cs:__imp_GetCurrentThreadId
0x1800018dd  mov     eax, eax
0x1800018df  xor     [rbp+arg_0], rax
0x1800018e3  call    cs:__imp_GetTickCount
0x1800018e9  mov     eax, eax
0x1800018eb  shl     rax, 18h
0x1800018ef  xor     [rbp+arg_0], rax
0x1800018f3  call    cs:__imp_GetTickCount
0x1800018f9  mov     eax, eax
0x1800018fb  lea     rcx, [rbp+arg_0]
0x1800018ff  xor     rax, [rbp+arg_0]
0x180001903  xor     rax, rcx
0x180001906  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000190a  mov     [rbp+arg_0], rax
0x18000190e  call    cs:__imp_QueryPerformanceCounter
0x180001914  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001917  mov     rcx, 0FFFFFFFFFFFFh
0x180001921  shl     rax, 20h
0x180001925  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001929  xor     rax, [rbp+arg_0]
0x18000192d  and     rax, rcx
0x180001930  mov     rcx, rax
0x180001933  cmp     rax, rbx
0x180001936  jnz     short loc_180001945
0x180001938  mov     rax, 2B992DDFA233h
0x180001942  mov     rcx, rax
0x180001945  mov     cs:__security_cookie, rcx
0x18000194c  mov     rbx, [rsp+20h+arg_18]
0x180001951  not     rax
0x180001954  mov     cs:__security_cookie_complement, rax
0x18000195b  add     rsp, 20h
0x18000195f  pop     rbp
0x180001960  retn
```
