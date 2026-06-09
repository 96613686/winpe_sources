# __security_init_cookie

- ea: `0x1400018c0`
- end: `0x140001975`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400015a0`

## callees

- `0x1400018c0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x14000191f`
- `KERNEL32!QueryPerformanceCounter` at `0x14000191f`
- `KERNEL32!GetCurrentProcessId` at `0x14000190f`
- `KERNEL32!GetCurrentProcessId` at `0x14000190f`
- `KERNEL32!GetCurrentThreadId` at `0x140001903`
- `KERNEL32!GetCurrentThreadId` at `0x140001903`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400018f5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400018f5`

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
0x1400018c0  mov     [rsp-8+arg_10], rbx
0x1400018c5  push    rbp
0x1400018c6  mov     rbp, rsp
0x1400018c9  sub     rsp, 30h
0x1400018cd  mov     rax, cs:__security_cookie
0x1400018d4  mov     rbx, 2B992DDFA232h
0x1400018de  cmp     rax, rbx
0x1400018e1  jnz     short loc_140001960
0x1400018e3  xor     eax, eax
0x1400018e5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400018e9  mov     [rbp+var_10], rax
0x1400018ed  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400018f1  mov     qword ptr [rbp+PerformanceCount], rax
0x1400018f5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400018fb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400018ff  mov     [rbp+var_10], rax
0x140001903  call    cs:__imp_GetCurrentThreadId
0x140001909  mov     eax, eax
0x14000190b  xor     [rbp+var_10], rax
0x14000190f  call    cs:__imp_GetCurrentProcessId
0x140001915  mov     eax, eax
0x140001917  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000191b  xor     [rbp+var_10], rax
0x14000191f  call    cs:__imp_QueryPerformanceCounter
0x140001925  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001928  lea     rcx, [rbp+var_10]
0x14000192c  shl     rax, 20h
0x140001930  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001934  xor     rax, [rbp+var_10]
0x140001938  xor     rax, rcx
0x14000193b  mov     rcx, 0FFFFFFFFFFFFh
0x140001945  and     rax, rcx
0x140001948  mov     rcx, 2B992DDFA233h
0x140001952  cmp     rax, rbx
0x140001955  cmovz   rax, rcx
0x140001959  mov     cs:__security_cookie, rax
0x140001960  mov     rbx, [rsp+30h+arg_10]
0x140001965  not     rax
0x140001968  mov     cs:__security_cookie_complement, rax
0x14000196f  add     rsp, 30h
0x140001973  pop     rbp
0x140001974  retn
```
