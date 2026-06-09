# __security_init_cookie

- ea: `0x180001470`
- end: `0x180001525`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013f0`

## callees

- `0x180001470`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800014cf`
- `KERNEL32!QueryPerformanceCounter` at `0x1800014cf`
- `KERNEL32!GetCurrentThreadId` at `0x1800014b3`
- `KERNEL32!GetCurrentThreadId` at `0x1800014b3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800014a5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800014a5`
- `KERNEL32!GetCurrentProcessId` at `0x1800014bf`
- `KERNEL32!GetCurrentProcessId` at `0x1800014bf`

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
0x180001470  mov     [rsp-8+arg_10], rbx
0x180001475  push    rbp
0x180001476  mov     rbp, rsp
0x180001479  sub     rsp, 30h
0x18000147d  mov     rax, cs:__security_cookie
0x180001484  mov     rbx, 2B992DDFA232h
0x18000148e  cmp     rax, rbx
0x180001491  jnz     short loc_180001510
0x180001493  xor     eax, eax
0x180001495  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001499  mov     [rbp+var_10], rax
0x18000149d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800014a1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800014a5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800014ab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800014af  mov     [rbp+var_10], rax
0x1800014b3  call    cs:__imp_GetCurrentThreadId
0x1800014b9  mov     eax, eax
0x1800014bb  xor     [rbp+var_10], rax
0x1800014bf  call    cs:__imp_GetCurrentProcessId
0x1800014c5  mov     eax, eax
0x1800014c7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800014cb  xor     [rbp+var_10], rax
0x1800014cf  call    cs:__imp_QueryPerformanceCounter
0x1800014d5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800014d8  lea     rcx, [rbp+var_10]
0x1800014dc  shl     rax, 20h
0x1800014e0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800014e4  xor     rax, [rbp+var_10]
0x1800014e8  xor     rax, rcx
0x1800014eb  mov     rcx, 0FFFFFFFFFFFFh
0x1800014f5  and     rax, rcx
0x1800014f8  mov     rcx, 2B992DDFA233h
0x180001502  cmp     rax, rbx
0x180001505  cmovz   rax, rcx
0x180001509  mov     cs:__security_cookie, rax
0x180001510  mov     rbx, [rsp+30h+arg_10]
0x180001515  not     rax
0x180001518  mov     cs:__security_cookie_complement, rax
0x18000151f  add     rsp, 30h
0x180001523  pop     rbp
0x180001524  retn
```
