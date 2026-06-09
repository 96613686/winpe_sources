# __security_init_cookie

- ea: `0x1800047c4`
- end: `0x180004870`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800042d0`

## callees

- `0x1800047c4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000481a`
- `KERNEL32!QueryPerformanceCounter` at `0x18000481a`
- `KERNEL32!GetCurrentProcessId` at `0x18000480a`
- `KERNEL32!GetCurrentProcessId` at `0x18000480a`
- `KERNEL32!GetCurrentThreadId` at `0x1800047fe`
- `KERNEL32!GetCurrentThreadId` at `0x1800047fe`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800047f0`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800047f0`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
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
0x1800047c4  mov     [rsp-8+arg_18], rbx
0x1800047c9  push    rbp
0x1800047ca  mov     rbp, rsp
0x1800047cd  sub     rsp, 20h
0x1800047d1  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800047d6  mov     rbx, 2B992DDFA232h
0x1800047e0  mov     rax, cs:__security_cookie
0x1800047e7  cmp     rax, rbx
0x1800047ea  jnz     short loc_18000485B
0x1800047ec  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800047f0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800047f6  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800047fa  mov     [rbp+arg_0], rax
0x1800047fe  call    cs:__imp_GetCurrentThreadId
0x180004804  mov     eax, eax
0x180004806  xor     [rbp+arg_0], rax
0x18000480a  call    cs:__imp_GetCurrentProcessId
0x180004810  mov     eax, eax
0x180004812  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004816  xor     [rbp+arg_0], rax
0x18000481a  call    cs:__imp_QueryPerformanceCounter
0x180004820  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004823  lea     rcx, [rbp+arg_0]
0x180004827  shl     rax, 20h
0x18000482b  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000482f  xor     rax, [rbp+arg_0]
0x180004833  xor     rax, rcx
0x180004836  mov     rcx, 0FFFFFFFFFFFFh
0x180004840  and     rax, rcx
0x180004843  mov     rcx, 2B992DDFA233h
0x18000484d  cmp     rax, rbx
0x180004850  cmovz   rax, rcx
0x180004854  mov     cs:__security_cookie, rax
0x18000485b  mov     rbx, [rsp+20h+arg_18]
0x180004860  not     rax
0x180004863  mov     cs:__security_cookie_complement, rax
0x18000486a  add     rsp, 20h
0x18000486e  pop     rbp
0x18000486f  retn
```
