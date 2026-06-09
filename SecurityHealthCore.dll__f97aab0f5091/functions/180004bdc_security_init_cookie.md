# __security_init_cookie

- ea: `0x180004bdc`
- end: `0x180004c91`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800046c0`

## callees

- `0x180004bdc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004c1f`
- `KERNEL32!GetCurrentThreadId` at `0x180004c1f`
- `KERNEL32!GetCurrentProcessId` at `0x180004c2b`
- `KERNEL32!GetCurrentProcessId` at `0x180004c2b`
- `KERNEL32!QueryPerformanceCounter` at `0x180004c3b`
- `KERNEL32!QueryPerformanceCounter` at `0x180004c3b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004c11`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004c11`

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
0x180004bdc  mov     [rsp-8+arg_10], rbx
0x180004be1  push    rbp
0x180004be2  mov     rbp, rsp
0x180004be5  sub     rsp, 30h
0x180004be9  mov     rax, cs:__security_cookie
0x180004bf0  mov     rbx, 2B992DDFA232h
0x180004bfa  cmp     rax, rbx
0x180004bfd  jnz     short loc_180004C7C
0x180004bff  xor     eax, eax
0x180004c01  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004c05  mov     [rbp+var_10], rax
0x180004c09  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004c0d  mov     qword ptr [rbp+PerformanceCount], rax
0x180004c11  call    cs:__imp_GetSystemTimeAsFileTime
0x180004c17  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004c1b  mov     [rbp+var_10], rax
0x180004c1f  call    cs:__imp_GetCurrentThreadId
0x180004c25  mov     eax, eax
0x180004c27  xor     [rbp+var_10], rax
0x180004c2b  call    cs:__imp_GetCurrentProcessId
0x180004c31  mov     eax, eax
0x180004c33  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004c37  xor     [rbp+var_10], rax
0x180004c3b  call    cs:__imp_QueryPerformanceCounter
0x180004c41  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004c44  lea     rcx, [rbp+var_10]
0x180004c48  shl     rax, 20h
0x180004c4c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004c50  xor     rax, [rbp+var_10]
0x180004c54  xor     rax, rcx
0x180004c57  mov     rcx, 0FFFFFFFFFFFFh
0x180004c61  and     rax, rcx
0x180004c64  mov     rcx, 2B992DDFA233h
0x180004c6e  cmp     rax, rbx
0x180004c71  cmovz   rax, rcx
0x180004c75  mov     cs:__security_cookie, rax
0x180004c7c  mov     rbx, [rsp+30h+arg_10]
0x180004c81  not     rax
0x180004c84  mov     cs:__security_cookie_complement, rax
0x180004c8b  add     rsp, 30h
0x180004c8f  pop     rbp
0x180004c90  retn
```
