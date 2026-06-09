# __security_init_cookie

- ea: `0x180027340`
- end: `0x1800273ef`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800266a0`

## callees

- `0x180027340`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180027389`
- `KERNEL32!GetCurrentProcessId` at `0x180027389`
- `KERNEL32!GetCurrentThreadId` at `0x18002737d`
- `KERNEL32!GetCurrentThreadId` at `0x18002737d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002736f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002736f`
- `KERNEL32!QueryPerformanceCounter` at `0x180027399`
- `KERNEL32!QueryPerformanceCounter` at `0x180027399`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

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
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180027340  mov     [rsp-8+arg_10], rbx
0x180027345  push    rbp
0x180027346  mov     rbp, rsp
0x180027349  sub     rsp, 30h
0x18002734d  mov     rax, cs:__security_cookie
0x180027354  mov     rbx, 2B992DDFA232h
0x18002735e  cmp     rax, rbx
0x180027361  jnz     short loc_1800273DA
0x180027363  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180027367  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18002736f  call    cs:__imp_GetSystemTimeAsFileTime
0x180027375  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180027379  mov     [rbp+var_10], rax
0x18002737d  call    cs:__imp_GetCurrentThreadId
0x180027383  mov     eax, eax
0x180027385  xor     [rbp+var_10], rax
0x180027389  call    cs:__imp_GetCurrentProcessId
0x18002738f  mov     eax, eax
0x180027391  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180027395  xor     [rbp+var_10], rax
0x180027399  call    cs:__imp_QueryPerformanceCounter
0x18002739f  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800273a2  lea     rcx, [rbp+var_10]
0x1800273a6  shl     rax, 20h
0x1800273aa  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800273ae  xor     rax, [rbp+var_10]
0x1800273b2  xor     rax, rcx
0x1800273b5  mov     rcx, 0FFFFFFFFFFFFh
0x1800273bf  and     rax, rcx
0x1800273c2  mov     rcx, 2B992DDFA233h
0x1800273cc  cmp     rax, rbx
0x1800273cf  cmovz   rax, rcx
0x1800273d3  mov     cs:__security_cookie, rax
0x1800273da  mov     rbx, [rsp+30h+arg_10]
0x1800273df  not     rax
0x1800273e2  mov     cs:__security_cookie_complement, rax
0x1800273e9  add     rsp, 30h
0x1800273ed  pop     rbp
0x1800273ee  retn
```
