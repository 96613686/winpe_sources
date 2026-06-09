# __security_init_cookie

- ea: `0x180035fd4`
- end: `0x180036083`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180035820`

## callees

- `0x180035fd4`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18003601d`
- `KERNEL32!GetCurrentProcessId` at `0x18003601d`
- `KERNEL32!GetCurrentThreadId` at `0x180036011`
- `KERNEL32!GetCurrentThreadId` at `0x180036011`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180036003`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180036003`
- `KERNEL32!QueryPerformanceCounter` at `0x18003602d`
- `KERNEL32!QueryPerformanceCounter` at `0x18003602d`

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
0x180035fd4  mov     [rsp-8+arg_10], rbx
0x180035fd9  push    rbp
0x180035fda  mov     rbp, rsp
0x180035fdd  sub     rsp, 30h
0x180035fe1  mov     rax, cs:__security_cookie
0x180035fe8  mov     rbx, 2B992DDFA232h
0x180035ff2  cmp     rax, rbx
0x180035ff5  jnz     short loc_18003606E
0x180035ff7  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180035ffb  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180036003  call    cs:__imp_GetSystemTimeAsFileTime
0x180036009  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003600d  mov     [rbp+var_10], rax
0x180036011  call    cs:__imp_GetCurrentThreadId
0x180036017  mov     eax, eax
0x180036019  xor     [rbp+var_10], rax
0x18003601d  call    cs:__imp_GetCurrentProcessId
0x180036023  mov     eax, eax
0x180036025  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180036029  xor     [rbp+var_10], rax
0x18003602d  call    cs:__imp_QueryPerformanceCounter
0x180036033  mov     eax, dword ptr [rbp+PerformanceCount]
0x180036036  lea     rcx, [rbp+var_10]
0x18003603a  shl     rax, 20h
0x18003603e  xor     rax, qword ptr [rbp+PerformanceCount]
0x180036042  xor     rax, [rbp+var_10]
0x180036046  xor     rax, rcx
0x180036049  mov     rcx, 0FFFFFFFFFFFFh
0x180036053  and     rax, rcx
0x180036056  mov     rcx, 2B992DDFA233h
0x180036060  cmp     rax, rbx
0x180036063  cmovz   rax, rcx
0x180036067  mov     cs:__security_cookie, rax
0x18003606e  mov     rbx, [rsp+30h+arg_10]
0x180036073  not     rax
0x180036076  mov     cs:__security_cookie_complement, rax
0x18003607d  add     rsp, 30h
0x180036081  pop     rbp
0x180036082  retn
```
