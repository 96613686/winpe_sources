# __security_init_cookie

- ea: `0x1801f849c`
- end: `0x1801f854b`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801f7a70`

## callees

- `0x1801f849c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1801f84d9`
- `KERNEL32!GetCurrentThreadId` at `0x1801f84d9`
- `KERNEL32!GetCurrentProcessId` at `0x1801f84e5`
- `KERNEL32!GetCurrentProcessId` at `0x1801f84e5`
- `KERNEL32!QueryPerformanceCounter` at `0x1801f84f5`
- `KERNEL32!QueryPerformanceCounter` at `0x1801f84f5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801f84cb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801f84cb`

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
0x1801f849c  mov     [rsp-8+arg_10], rbx
0x1801f84a1  push    rbp
0x1801f84a2  mov     rbp, rsp
0x1801f84a5  sub     rsp, 30h
0x1801f84a9  mov     rax, cs:__security_cookie
0x1801f84b0  mov     rbx, 2B992DDFA232h
0x1801f84ba  cmp     rax, rbx
0x1801f84bd  jnz     short loc_1801F8536
0x1801f84bf  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801f84c3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801f84cb  call    cs:__imp_GetSystemTimeAsFileTime
0x1801f84d1  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1801f84d5  mov     [rbp+var_10], rax
0x1801f84d9  call    cs:__imp_GetCurrentThreadId
0x1801f84df  mov     eax, eax
0x1801f84e1  xor     [rbp+var_10], rax
0x1801f84e5  call    cs:__imp_GetCurrentProcessId
0x1801f84eb  mov     eax, eax
0x1801f84ed  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1801f84f1  xor     [rbp+var_10], rax
0x1801f84f5  call    cs:__imp_QueryPerformanceCounter
0x1801f84fb  mov     eax, dword ptr [rbp+PerformanceCount]
0x1801f84fe  lea     rcx, [rbp+var_10]
0x1801f8502  shl     rax, 20h
0x1801f8506  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801f850a  xor     rax, [rbp+var_10]
0x1801f850e  xor     rax, rcx
0x1801f8511  mov     rcx, 0FFFFFFFFFFFFh
0x1801f851b  and     rax, rcx
0x1801f851e  mov     rcx, 2B992DDFA233h
0x1801f8528  cmp     rax, rbx
0x1801f852b  cmovz   rax, rcx
0x1801f852f  mov     cs:__security_cookie, rax
0x1801f8536  mov     rbx, [rsp+30h+arg_10]
0x1801f853b  not     rax
0x1801f853e  mov     cs:__security_cookie_complement, rax
0x1801f8545  add     rsp, 30h
0x1801f8549  pop     rbp
0x1801f854a  retn
```
