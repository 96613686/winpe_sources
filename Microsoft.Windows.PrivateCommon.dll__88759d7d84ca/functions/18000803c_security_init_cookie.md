# __security_init_cookie

- ea: `0x18000803c`
- end: `0x1800080eb`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800079c0`

## callees

- `0x18000803c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180008079`
- `KERNEL32!GetCurrentThreadId` at `0x180008079`
- `KERNEL32!GetCurrentProcessId` at `0x180008085`
- `KERNEL32!GetCurrentProcessId` at `0x180008085`
- `KERNEL32!QueryPerformanceCounter` at `0x180008095`
- `KERNEL32!QueryPerformanceCounter` at `0x180008095`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000806b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000806b`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x18000803c  mov     [rsp-8+arg_10], rbx
0x180008041  push    rbp
0x180008042  mov     rbp, rsp
0x180008045  sub     rsp, 30h
0x180008049  mov     rax, cs:__security_cookie
0x180008050  mov     rbx, 2B992DDFA232h
0x18000805a  cmp     rax, rbx
0x18000805d  jnz     short loc_1800080D6
0x18000805f  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008063  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000806b  call    cs:__imp_GetSystemTimeAsFileTime
0x180008071  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180008075  mov     [rbp+var_10], rax
0x180008079  call    cs:__imp_GetCurrentThreadId
0x18000807f  mov     eax, eax
0x180008081  xor     [rbp+var_10], rax
0x180008085  call    cs:__imp_GetCurrentProcessId
0x18000808b  mov     eax, eax
0x18000808d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180008091  xor     [rbp+var_10], rax
0x180008095  call    cs:__imp_QueryPerformanceCounter
0x18000809b  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000809e  lea     rcx, [rbp+var_10]
0x1800080a2  shl     rax, 20h
0x1800080a6  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800080aa  xor     rax, [rbp+var_10]
0x1800080ae  xor     rax, rcx
0x1800080b1  mov     rcx, 0FFFFFFFFFFFFh
0x1800080bb  and     rax, rcx
0x1800080be  mov     rcx, 2B992DDFA233h
0x1800080c8  cmp     rax, rbx
0x1800080cb  cmovz   rax, rcx
0x1800080cf  mov     cs:__security_cookie, rax
0x1800080d6  mov     rbx, [rsp+30h+arg_10]
0x1800080db  not     rax
0x1800080de  mov     cs:__security_cookie_complement, rax
0x1800080e5  add     rsp, 30h
0x1800080e9  pop     rbp
0x1800080ea  retn
```
