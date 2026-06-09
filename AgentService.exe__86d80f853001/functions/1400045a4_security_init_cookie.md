# __security_init_cookie

- ea: `0x1400045a4`
- end: `0x140004659`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003e20`

## callees

- `0x1400045a4`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1400045f3`
- `KERNEL32!GetCurrentProcessId` at `0x1400045f3`
- `KERNEL32!QueryPerformanceCounter` at `0x140004603`
- `KERNEL32!QueryPerformanceCounter` at `0x140004603`
- `KERNEL32!GetCurrentThreadId` at `0x1400045e7`
- `KERNEL32!GetCurrentThreadId` at `0x1400045e7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400045d9`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400045d9`

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
0x1400045a4  mov     [rsp-8+arg_10], rbx
0x1400045a9  push    rbp
0x1400045aa  mov     rbp, rsp
0x1400045ad  sub     rsp, 30h
0x1400045b1  mov     rax, cs:__security_cookie
0x1400045b8  mov     rbx, 2B992DDFA232h
0x1400045c2  cmp     rax, rbx
0x1400045c5  jnz     short loc_140004644
0x1400045c7  xor     eax, eax
0x1400045c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400045cd  mov     [rbp+var_10], rax
0x1400045d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400045d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400045d9  call    cs:__imp_GetSystemTimeAsFileTime
0x1400045df  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400045e3  mov     [rbp+var_10], rax
0x1400045e7  call    cs:__imp_GetCurrentThreadId
0x1400045ed  mov     eax, eax
0x1400045ef  xor     [rbp+var_10], rax
0x1400045f3  call    cs:__imp_GetCurrentProcessId
0x1400045f9  mov     eax, eax
0x1400045fb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400045ff  xor     [rbp+var_10], rax
0x140004603  call    cs:__imp_QueryPerformanceCounter
0x140004609  mov     eax, dword ptr [rbp+PerformanceCount]
0x14000460c  lea     rcx, [rbp+var_10]
0x140004610  shl     rax, 20h
0x140004614  xor     rax, qword ptr [rbp+PerformanceCount]
0x140004618  xor     rax, [rbp+var_10]
0x14000461c  xor     rax, rcx
0x14000461f  mov     rcx, 0FFFFFFFFFFFFh
0x140004629  and     rax, rcx
0x14000462c  mov     rcx, 2B992DDFA233h
0x140004636  cmp     rax, rbx
0x140004639  cmovz   rax, rcx
0x14000463d  mov     cs:__security_cookie, rax
0x140004644  mov     rbx, [rsp+30h+arg_10]
0x140004649  not     rax
0x14000464c  mov     cs:__security_cookie_complement, rax
0x140004653  add     rsp, 30h
0x140004657  pop     rbp
0x140004658  retn
```
