# __security_init_cookie

- ea: `0x1800270b0`
- end: `0x180027180`
- name: `__security_init_cookie`
- size: `208`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026b80`

## callees

- `0x1800270b0`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180027131`
- `KERNEL32!QueryPerformanceCounter` at `0x180027131`
- `KERNEL32!GetCurrentProcessId` at `0x1800270ee`
- `KERNEL32!GetCurrentProcessId` at `0x1800270ee`
- `KERNEL32!GetCurrentThreadId` at `0x1800270fa`
- `KERNEL32!GetCurrentThreadId` at `0x1800270fa`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800270e0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800270e0`
- `KERNEL32!GetTickCount` at `0x180027106`
- `KERNEL32!GetTickCount` at `0x180027116`
- `KERNEL32!GetTickCount` at `0x180027106`
- `KERNEL32!GetTickCount` at `0x180027116`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (struct _FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v1
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
0x1800270b0  mov     [rsp-8+arg_18], rbx
0x1800270b5  push    rbp
0x1800270b6  mov     rbp, rsp
0x1800270b9  sub     rsp, 20h
0x1800270bd  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800270c2  mov     rbx, 2B992DDFA232h
0x1800270cc  mov     rax, cs:__security_cookie
0x1800270d3  cmp     rax, rbx
0x1800270d6  jnz     loc_18002716B
0x1800270dc  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800270e0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800270e6  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800270ea  mov     [rbp+arg_0], rax
0x1800270ee  call    cs:__imp_GetCurrentProcessId
0x1800270f4  mov     eax, eax
0x1800270f6  xor     [rbp+arg_0], rax
0x1800270fa  call    cs:__imp_GetCurrentThreadId
0x180027100  mov     eax, eax
0x180027102  xor     [rbp+arg_0], rax
0x180027106  call    cs:__imp_GetTickCount
0x18002710c  mov     eax, eax
0x18002710e  shl     rax, 18h
0x180027112  xor     [rbp+arg_0], rax
0x180027116  call    cs:__imp_GetTickCount
0x18002711c  mov     eax, eax
0x18002711e  lea     rcx, [rbp+arg_0]
0x180027122  xor     rax, [rbp+arg_0]
0x180027126  xor     rax, rcx
0x180027129  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002712d  mov     [rbp+arg_0], rax
0x180027131  call    cs:__imp_QueryPerformanceCounter
0x180027137  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002713a  mov     rcx, 0FFFFFFFFFFFFh
0x180027144  shl     rax, 20h
0x180027148  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002714c  xor     rax, [rbp+arg_0]
0x180027150  and     rax, rcx
0x180027153  mov     rcx, 2B992DDFA233h
0x18002715d  cmp     rax, rbx
0x180027160  cmovz   rax, rcx
0x180027164  mov     cs:__security_cookie, rax
0x18002716b  mov     rbx, [rsp+20h+arg_18]
0x180027170  not     rax
0x180027173  mov     cs:__security_cookie_complement, rax
0x18002717a  add     rsp, 20h
0x18002717e  pop     rbp
0x18002717f  retn
```
