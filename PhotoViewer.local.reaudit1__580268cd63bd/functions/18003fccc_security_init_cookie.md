# __security_init_cookie

- ea: `0x18003fccc`
- end: `0x18003fd81`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f7b0`

## callees

- `0x18003fccc`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003fd01`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18003fd01`
- `KERNEL32!GetCurrentProcessId` at `0x18003fd1b`
- `KERNEL32!GetCurrentProcessId` at `0x18003fd1b`
- `KERNEL32!QueryPerformanceCounter` at `0x18003fd2b`
- `KERNEL32!QueryPerformanceCounter` at `0x18003fd2b`
- `KERNEL32!GetCurrentThreadId` at `0x18003fd0f`
- `KERNEL32!GetCurrentThreadId` at `0x18003fd0f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
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
0x18003fccc  mov     [rsp-8+arg_10], rbx
0x18003fcd1  push    rbp
0x18003fcd2  mov     rbp, rsp
0x18003fcd5  sub     rsp, 30h
0x18003fcd9  mov     rax, cs:__security_cookie
0x18003fce0  mov     rbx, 2B992DDFA232h
0x18003fcea  cmp     rax, rbx
0x18003fced  jnz     short loc_18003FD6C
0x18003fcef  xor     eax, eax
0x18003fcf1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003fcf5  mov     [rbp+var_10], rax
0x18003fcf9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003fcfd  mov     qword ptr [rbp+PerformanceCount], rax
0x18003fd01  call    cs:__imp_GetSystemTimeAsFileTime
0x18003fd07  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003fd0b  mov     [rbp+var_10], rax
0x18003fd0f  call    cs:__imp_GetCurrentThreadId
0x18003fd15  mov     eax, eax
0x18003fd17  xor     [rbp+var_10], rax
0x18003fd1b  call    cs:__imp_GetCurrentProcessId
0x18003fd21  mov     eax, eax
0x18003fd23  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003fd27  xor     [rbp+var_10], rax
0x18003fd2b  call    cs:__imp_QueryPerformanceCounter
0x18003fd31  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003fd34  lea     rcx, [rbp+var_10]
0x18003fd38  shl     rax, 20h
0x18003fd3c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003fd40  xor     rax, [rbp+var_10]
0x18003fd44  xor     rax, rcx
0x18003fd47  mov     rcx, 0FFFFFFFFFFFFh
0x18003fd51  and     rax, rcx
0x18003fd54  mov     rcx, 2B992DDFA233h
0x18003fd5e  cmp     rax, rbx
0x18003fd61  cmovz   rax, rcx
0x18003fd65  mov     cs:__security_cookie, rax
0x18003fd6c  mov     rbx, [rsp+30h+arg_10]
0x18003fd71  not     rax
0x18003fd74  mov     cs:__security_cookie_complement, rax
0x18003fd7b  add     rsp, 30h
0x18003fd7f  pop     rbp
0x18003fd80  retn
```
