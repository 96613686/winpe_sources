# __security_init_cookie

- ea: `0x140006214`
- end: `0x1400062c3`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140005bf0`

## callees

- `0x140006214`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x140006243`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140006243`
- `KERNEL32!GetCurrentProcessId` at `0x14000625d`
- `KERNEL32!GetCurrentProcessId` at `0x14000625d`
- `KERNEL32!QueryPerformanceCounter` at `0x14000626d`
- `KERNEL32!QueryPerformanceCounter` at `0x14000626d`
- `KERNEL32!GetCurrentThreadId` at `0x140006251`
- `KERNEL32!GetCurrentThreadId` at `0x140006251`

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
0x140006214  mov     [rsp-8+arg_10], rbx
0x140006219  push    rbp
0x14000621a  mov     rbp, rsp
0x14000621d  sub     rsp, 30h
0x140006221  mov     rax, cs:__security_cookie
0x140006228  mov     rbx, 2B992DDFA232h
0x140006232  cmp     rax, rbx
0x140006235  jnz     short loc_1400062AE
0x140006237  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000623b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x140006243  call    cs:__imp_GetSystemTimeAsFileTime
0x140006249  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000624d  mov     [rbp+var_10], rax
0x140006251  call    cs:__imp_GetCurrentThreadId
0x140006257  mov     eax, eax
0x140006259  xor     [rbp+var_10], rax
0x14000625d  call    cs:__imp_GetCurrentProcessId
0x140006263  mov     eax, eax
0x140006265  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140006269  xor     [rbp+var_10], rax
0x14000626d  call    cs:__imp_QueryPerformanceCounter
0x140006273  mov     eax, dword ptr [rbp+PerformanceCount]
0x140006276  lea     rcx, [rbp+var_10]
0x14000627a  shl     rax, 20h
0x14000627e  xor     rax, qword ptr [rbp+PerformanceCount]
0x140006282  xor     rax, [rbp+var_10]
0x140006286  xor     rax, rcx
0x140006289  mov     rcx, 0FFFFFFFFFFFFh
0x140006293  and     rax, rcx
0x140006296  mov     rcx, 2B992DDFA233h
0x1400062a0  cmp     rax, rbx
0x1400062a3  cmovz   rax, rcx
0x1400062a7  mov     cs:__security_cookie, rax
0x1400062ae  mov     rbx, [rsp+30h+arg_10]
0x1400062b3  not     rax
0x1400062b6  mov     cs:__security_cookie_complement, rax
0x1400062bd  add     rsp, 30h
0x1400062c1  pop     rbp
0x1400062c2  retn
```
