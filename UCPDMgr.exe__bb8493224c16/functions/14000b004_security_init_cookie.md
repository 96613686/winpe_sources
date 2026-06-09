# __security_init_cookie

- ea: `0x14000b004`
- end: `0x14000b0bb`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a8e0`

## callees

- `0x14000b004`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000b049`
- `KERNEL32!GetCurrentThreadId` at `0x14000b049`
- `KERNEL32!GetCurrentProcessId` at `0x14000b055`
- `KERNEL32!GetCurrentProcessId` at `0x14000b055`
- `KERNEL32!QueryPerformanceCounter` at `0x14000b065`
- `KERNEL32!QueryPerformanceCounter` at `0x14000b065`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000b03b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000b03b`

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
0x14000b004  mov     [rsp-8+arg_10], rbx
0x14000b009  push    rbp
0x14000b00a  mov     rbp, rsp
0x14000b00d  sub     rsp, 30h
0x14000b011  mov     rax, cs:__security_cookie
0x14000b018  mov     rbx, 2B992DDFA232h
0x14000b022  cmp     rax, rbx
0x14000b025  jnz     short loc_14000B0A6
0x14000b027  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000b02b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14000b033  mov     qword ptr [rbp+PerformanceCount], 0
0x14000b03b  call    cs:__imp_GetSystemTimeAsFileTime
0x14000b041  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000b045  mov     [rbp+var_10], rax
0x14000b049  call    cs:__imp_GetCurrentThreadId
0x14000b04f  mov     eax, eax
0x14000b051  xor     [rbp+var_10], rax
0x14000b055  call    cs:__imp_GetCurrentProcessId
0x14000b05b  mov     eax, eax
0x14000b05d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000b061  xor     [rbp+var_10], rax
0x14000b065  call    cs:__imp_QueryPerformanceCounter
0x14000b06b  mov     eax, dword ptr [rbp+PerformanceCount]
0x14000b06e  lea     rcx, [rbp+var_10]
0x14000b072  shl     rax, 20h
0x14000b076  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000b07a  xor     rax, [rbp+var_10]
0x14000b07e  xor     rax, rcx
0x14000b081  mov     rcx, 0FFFFFFFFFFFFh
0x14000b08b  and     rax, rcx
0x14000b08e  mov     rcx, 2B992DDFA233h
0x14000b098  cmp     rax, rbx
0x14000b09b  cmovz   rax, rcx
0x14000b09f  mov     cs:__security_cookie, rax
0x14000b0a6  mov     rbx, [rsp+30h+arg_10]
0x14000b0ab  not     rax
0x14000b0ae  mov     cs:__security_cookie_complement, rax
0x14000b0b5  add     rsp, 30h
0x14000b0b9  pop     rbp
0x14000b0ba  retn
```
