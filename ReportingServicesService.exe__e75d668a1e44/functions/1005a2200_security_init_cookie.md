# __security_init_cookie

- ea: `0x1005a2200`
- end: `0x1005a22ac`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1005a1910`

## callees

- `0x1005a2200`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1005a2256`
- `KERNEL32!QueryPerformanceCounter` at `0x1005a2256`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005a222c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005a222c`
- `KERNEL32!GetCurrentThreadId` at `0x1005a223a`
- `KERNEL32!GetCurrentThreadId` at `0x1005a223a`
- `KERNEL32!GetCurrentProcessId` at `0x1005a2246`
- `KERNEL32!GetCurrentProcessId` at `0x1005a2246`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
  qword_10066A008 = ~v0;
}

```

## disassembly

```asm
0x1005a2200  mov     [rsp-8+arg_18], rbx
0x1005a2205  push    rbp
0x1005a2206  mov     rbp, rsp
0x1005a2209  sub     rsp, 20h
0x1005a220d  mov     rax, cs:__security_cookie
0x1005a2214  mov     rbx, 2B992DDFA232h
0x1005a221e  cmp     rax, rbx
0x1005a2221  jnz     short loc_1005A2297
0x1005a2223  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1005a2228  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1005a222c  call    cs:GetSystemTimeAsFileTime
0x1005a2232  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1005a2236  mov     [rbp+arg_0], rax
0x1005a223a  call    cs:GetCurrentThreadId
0x1005a2240  mov     eax, eax
0x1005a2242  xor     [rbp+arg_0], rax
0x1005a2246  call    cs:GetCurrentProcessId
0x1005a224c  mov     eax, eax
0x1005a224e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1005a2252  xor     [rbp+arg_0], rax
0x1005a2256  call    cs:QueryPerformanceCounter
0x1005a225c  mov     eax, dword ptr [rbp+PerformanceCount]
0x1005a225f  lea     rcx, [rbp+arg_0]
0x1005a2263  shl     rax, 20h
0x1005a2267  xor     rax, qword ptr [rbp+PerformanceCount]
0x1005a226b  xor     rax, [rbp+arg_0]
0x1005a226f  xor     rax, rcx
0x1005a2272  mov     rcx, 0FFFFFFFFFFFFh
0x1005a227c  and     rax, rcx
0x1005a227f  mov     rcx, 2B992DDFA233h
0x1005a2289  cmp     rax, rbx
0x1005a228c  cmovz   rax, rcx
0x1005a2290  mov     cs:__security_cookie, rax
0x1005a2297  mov     rbx, [rsp+20h+arg_18]
0x1005a229c  not     rax
0x1005a229f  mov     cs:qword_10066A008, rax
0x1005a22a6  add     rsp, 20h
0x1005a22aa  pop     rbp
0x1005a22ab  retn
```
