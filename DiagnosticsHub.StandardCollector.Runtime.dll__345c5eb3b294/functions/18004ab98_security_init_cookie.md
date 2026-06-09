# __security_init_cookie

- ea: `0x18004ab98`
- end: `0x18004ac47`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004a500`

## callees

- `0x18004ab98`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004abc7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004abc7`
- `KERNEL32!QueryPerformanceCounter` at `0x18004abf1`
- `KERNEL32!QueryPerformanceCounter` at `0x18004abf1`
- `KERNEL32!GetCurrentProcessId` at `0x18004abe1`
- `KERNEL32!GetCurrentProcessId` at `0x18004abe1`
- `KERNEL32!GetCurrentThreadId` at `0x18004abd5`
- `KERNEL32!GetCurrentThreadId` at `0x18004abd5`

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
0x18004ab98  mov     [rsp-8+arg_10], rbx
0x18004ab9d  push    rbp
0x18004ab9e  mov     rbp, rsp
0x18004aba1  sub     rsp, 30h
0x18004aba5  mov     rax, cs:__security_cookie
0x18004abac  mov     rbx, 2B992DDFA232h
0x18004abb6  cmp     rax, rbx
0x18004abb9  jnz     short loc_18004AC32
0x18004abbb  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004abbf  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004abc7  call    cs:__imp_GetSystemTimeAsFileTime
0x18004abcd  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004abd1  mov     [rbp+var_10], rax
0x18004abd5  call    cs:__imp_GetCurrentThreadId
0x18004abdb  mov     eax, eax
0x18004abdd  xor     [rbp+var_10], rax
0x18004abe1  call    cs:__imp_GetCurrentProcessId
0x18004abe7  mov     eax, eax
0x18004abe9  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004abed  xor     [rbp+var_10], rax
0x18004abf1  call    cs:__imp_QueryPerformanceCounter
0x18004abf7  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004abfa  lea     rcx, [rbp+var_10]
0x18004abfe  shl     rax, 20h
0x18004ac02  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004ac06  xor     rax, [rbp+var_10]
0x18004ac0a  xor     rax, rcx
0x18004ac0d  mov     rcx, 0FFFFFFFFFFFFh
0x18004ac17  and     rax, rcx
0x18004ac1a  mov     rcx, 2B992DDFA233h
0x18004ac24  cmp     rax, rbx
0x18004ac27  cmovz   rax, rcx
0x18004ac2b  mov     cs:__security_cookie, rax
0x18004ac32  mov     rbx, [rsp+30h+arg_10]
0x18004ac37  not     rax
0x18004ac3a  mov     cs:__security_cookie_complement, rax
0x18004ac41  add     rsp, 30h
0x18004ac45  pop     rbp
0x18004ac46  retn
```
