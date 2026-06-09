# __security_init_cookie

- ea: `0x18000df44`
- end: `0x18000dff0`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000da50`

## callees

- `0x18000df44`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000df8a`
- `KERNEL32!GetCurrentProcessId` at `0x18000df8a`
- `KERNEL32!GetCurrentThreadId` at `0x18000df7e`
- `KERNEL32!GetCurrentThreadId` at `0x18000df7e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000df9a`
- `KERNEL32!QueryPerformanceCounter` at `0x18000df9a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000df70`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000df70`

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
0x18000df44  mov     [rsp-8+arg_18], rbx
0x18000df49  push    rbp
0x18000df4a  mov     rbp, rsp
0x18000df4d  sub     rsp, 20h
0x18000df51  mov     rax, cs:__security_cookie
0x18000df58  mov     rbx, 2B992DDFA232h
0x18000df62  cmp     rax, rbx
0x18000df65  jnz     short loc_18000DFDB
0x18000df67  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000df6c  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000df70  call    cs:__imp_GetSystemTimeAsFileTime
0x18000df76  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000df7a  mov     [rbp+arg_0], rax
0x18000df7e  call    cs:__imp_GetCurrentThreadId
0x18000df84  mov     eax, eax
0x18000df86  xor     [rbp+arg_0], rax
0x18000df8a  call    cs:__imp_GetCurrentProcessId
0x18000df90  mov     eax, eax
0x18000df92  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000df96  xor     [rbp+arg_0], rax
0x18000df9a  call    cs:__imp_QueryPerformanceCounter
0x18000dfa0  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000dfa3  lea     rcx, [rbp+arg_0]
0x18000dfa7  shl     rax, 20h
0x18000dfab  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000dfaf  xor     rax, [rbp+arg_0]
0x18000dfb3  xor     rax, rcx
0x18000dfb6  mov     rcx, 0FFFFFFFFFFFFh
0x18000dfc0  and     rax, rcx
0x18000dfc3  mov     rcx, 2B992DDFA233h
0x18000dfcd  cmp     rax, rbx
0x18000dfd0  cmovz   rax, rcx
0x18000dfd4  mov     cs:__security_cookie, rax
0x18000dfdb  mov     rbx, [rsp+20h+arg_18]
0x18000dfe0  not     rax
0x18000dfe3  mov     cs:__security_cookie_complement, rax
0x18000dfea  add     rsp, 20h
0x18000dfee  pop     rbp
0x18000dfef  retn
```
