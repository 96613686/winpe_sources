# __security_init_cookie

- ea: `0x140005d90`
- end: `0x140005e3c`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005a80`

## callees

- `0x140005d90`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x140005dd6`
- `KERNEL32!GetCurrentProcessId` at `0x140005dd6`
- `KERNEL32!QueryPerformanceCounter` at `0x140005de6`
- `KERNEL32!QueryPerformanceCounter` at `0x140005de6`
- `KERNEL32!GetCurrentThreadId` at `0x140005dca`
- `KERNEL32!GetCurrentThreadId` at `0x140005dca`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140005dbc`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140005dbc`

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
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x140005d90  mov     [rsp-8+arg_18], rbx
0x140005d95  push    rbp
0x140005d96  mov     rbp, rsp
0x140005d99  sub     rsp, 20h
0x140005d9d  mov     rax, cs:__security_cookie
0x140005da4  mov     rbx, 2B992DDFA232h
0x140005dae  cmp     rax, rbx
0x140005db1  jnz     short loc_140005E27
0x140005db3  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x140005db8  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140005dbc  call    cs:__imp_GetSystemTimeAsFileTime
0x140005dc2  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140005dc6  mov     [rbp+arg_0], rax
0x140005dca  call    cs:__imp_GetCurrentThreadId
0x140005dd0  mov     eax, eax
0x140005dd2  xor     [rbp+arg_0], rax
0x140005dd6  call    cs:__imp_GetCurrentProcessId
0x140005ddc  mov     eax, eax
0x140005dde  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140005de2  xor     [rbp+arg_0], rax
0x140005de6  call    cs:__imp_QueryPerformanceCounter
0x140005dec  mov     eax, dword ptr [rbp+PerformanceCount]
0x140005def  lea     rcx, [rbp+arg_0]
0x140005df3  shl     rax, 20h
0x140005df7  xor     rax, qword ptr [rbp+PerformanceCount]
0x140005dfb  xor     rax, [rbp+arg_0]
0x140005dff  xor     rax, rcx
0x140005e02  mov     rcx, 0FFFFFFFFFFFFh
0x140005e0c  and     rax, rcx
0x140005e0f  mov     rcx, 2B992DDFA233h
0x140005e19  cmp     rax, rbx
0x140005e1c  cmovz   rax, rcx
0x140005e20  mov     cs:__security_cookie, rax
0x140005e27  mov     rbx, [rsp+20h+arg_18]
0x140005e2c  not     rax
0x140005e2f  mov     cs:__security_cookie_complement, rax
0x140005e36  add     rsp, 20h
0x140005e3a  pop     rbp
0x140005e3b  retn
```
