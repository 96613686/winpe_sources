# __security_init_cookie

- ea: `0x18005a37c`
- end: `0x18005a431`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800598d0`

## callees

- `0x18005a37c`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18005a3db`
- `KERNEL32!QueryPerformanceCounter` at `0x18005a3db`
- `KERNEL32!GetCurrentProcessId` at `0x18005a3cb`
- `KERNEL32!GetCurrentProcessId` at `0x18005a3cb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18005a3b1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18005a3b1`
- `KERNEL32!GetCurrentThreadId` at `0x18005a3bf`
- `KERNEL32!GetCurrentThreadId` at `0x18005a3bf`

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
0x18005a37c  mov     [rsp-8+arg_10], rbx
0x18005a381  push    rbp
0x18005a382  mov     rbp, rsp
0x18005a385  sub     rsp, 30h
0x18005a389  mov     rax, cs:__security_cookie
0x18005a390  mov     rbx, 2B992DDFA232h
0x18005a39a  cmp     rax, rbx
0x18005a39d  jnz     short loc_18005A41C
0x18005a39f  xor     eax, eax
0x18005a3a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005a3a5  mov     [rbp+var_10], rax
0x18005a3a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005a3ad  mov     qword ptr [rbp+PerformanceCount], rax
0x18005a3b1  call    cs:__imp_GetSystemTimeAsFileTime
0x18005a3b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005a3bb  mov     [rbp+var_10], rax
0x18005a3bf  call    cs:__imp_GetCurrentThreadId
0x18005a3c5  mov     eax, eax
0x18005a3c7  xor     [rbp+var_10], rax
0x18005a3cb  call    cs:__imp_GetCurrentProcessId
0x18005a3d1  mov     eax, eax
0x18005a3d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005a3d7  xor     [rbp+var_10], rax
0x18005a3db  call    cs:__imp_QueryPerformanceCounter
0x18005a3e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005a3e4  lea     rcx, [rbp+var_10]
0x18005a3e8  shl     rax, 20h
0x18005a3ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x18005a3f0  xor     rax, [rbp+var_10]
0x18005a3f4  xor     rax, rcx
0x18005a3f7  mov     rcx, 0FFFFFFFFFFFFh
0x18005a401  and     rax, rcx
0x18005a404  mov     rcx, 2B992DDFA233h
0x18005a40e  cmp     rax, rbx
0x18005a411  cmovz   rax, rcx
0x18005a415  mov     cs:__security_cookie, rax
0x18005a41c  mov     rbx, [rsp+30h+arg_10]
0x18005a421  not     rax
0x18005a424  mov     cs:__security_cookie_complement, rax
0x18005a42b  add     rsp, 30h
0x18005a42f  pop     rbp
0x18005a430  retn
```
