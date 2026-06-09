# __security_init_cookie

- ea: `0x140002088`
- end: `0x140002137`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001a60`

## callees

- `0x140002088`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400020c5`
- `KERNEL32!GetCurrentThreadId` at `0x1400020c5`
- `KERNEL32!QueryPerformanceCounter` at `0x1400020e1`
- `KERNEL32!QueryPerformanceCounter` at `0x1400020e1`
- `KERNEL32!GetCurrentProcessId` at `0x1400020d1`
- `KERNEL32!GetCurrentProcessId` at `0x1400020d1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400020b7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400020b7`

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
0x140002088  mov     [rsp-8+arg_10], rbx
0x14000208d  push    rbp
0x14000208e  mov     rbp, rsp
0x140002091  sub     rsp, 30h
0x140002095  mov     rax, cs:__security_cookie
0x14000209c  mov     rbx, 2B992DDFA232h
0x1400020a6  cmp     rax, rbx
0x1400020a9  jnz     short loc_140002122
0x1400020ab  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400020af  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1400020b7  call    cs:__imp_GetSystemTimeAsFileTime
0x1400020bd  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400020c1  mov     [rbp+var_10], rax
0x1400020c5  call    cs:__imp_GetCurrentThreadId
0x1400020cb  mov     eax, eax
0x1400020cd  xor     [rbp+var_10], rax
0x1400020d1  call    cs:__imp_GetCurrentProcessId
0x1400020d7  mov     eax, eax
0x1400020d9  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400020dd  xor     [rbp+var_10], rax
0x1400020e1  call    cs:__imp_QueryPerformanceCounter
0x1400020e7  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400020ea  lea     rcx, [rbp+var_10]
0x1400020ee  shl     rax, 20h
0x1400020f2  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400020f6  xor     rax, [rbp+var_10]
0x1400020fa  xor     rax, rcx
0x1400020fd  mov     rcx, 0FFFFFFFFFFFFh
0x140002107  and     rax, rcx
0x14000210a  mov     rcx, 2B992DDFA233h
0x140002114  cmp     rax, rbx
0x140002117  cmovz   rax, rcx
0x14000211b  mov     cs:__security_cookie, rax
0x140002122  mov     rbx, [rsp+30h+arg_10]
0x140002127  not     rax
0x14000212a  mov     cs:__security_cookie_complement, rax
0x140002131  add     rsp, 30h
0x140002135  pop     rbp
0x140002136  retn
```
