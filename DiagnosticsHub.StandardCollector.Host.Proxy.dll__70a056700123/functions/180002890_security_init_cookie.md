# __security_init_cookie

- ea: `0x180002890`
- end: `0x18000293f`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800027e0`

## callees

- `0x180002890`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800028e9`
- `KERNEL32!QueryPerformanceCounter` at `0x1800028e9`
- `KERNEL32!GetCurrentProcessId` at `0x1800028d9`
- `KERNEL32!GetCurrentProcessId` at `0x1800028d9`
- `KERNEL32!GetCurrentThreadId` at `0x1800028cd`
- `KERNEL32!GetCurrentThreadId` at `0x1800028cd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800028bf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800028bf`

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
0x180002890  mov     [rsp-8+arg_10], rbx
0x180002895  push    rbp
0x180002896  mov     rbp, rsp
0x180002899  sub     rsp, 30h
0x18000289d  mov     rax, cs:__security_cookie
0x1800028a4  mov     rbx, 2B992DDFA232h
0x1800028ae  cmp     rax, rbx
0x1800028b1  jnz     short loc_18000292A
0x1800028b3  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800028b7  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800028bf  call    cs:__imp_GetSystemTimeAsFileTime
0x1800028c5  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800028c9  mov     [rbp+var_10], rax
0x1800028cd  call    cs:__imp_GetCurrentThreadId
0x1800028d3  mov     eax, eax
0x1800028d5  xor     [rbp+var_10], rax
0x1800028d9  call    cs:__imp_GetCurrentProcessId
0x1800028df  mov     eax, eax
0x1800028e1  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800028e5  xor     [rbp+var_10], rax
0x1800028e9  call    cs:__imp_QueryPerformanceCounter
0x1800028ef  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800028f2  lea     rcx, [rbp+var_10]
0x1800028f6  shl     rax, 20h
0x1800028fa  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800028fe  xor     rax, [rbp+var_10]
0x180002902  xor     rax, rcx
0x180002905  mov     rcx, 0FFFFFFFFFFFFh
0x18000290f  and     rax, rcx
0x180002912  mov     rcx, 2B992DDFA233h
0x18000291c  cmp     rax, rbx
0x18000291f  cmovz   rax, rcx
0x180002923  mov     cs:__security_cookie, rax
0x18000292a  mov     rbx, [rsp+30h+arg_10]
0x18000292f  not     rax
0x180002932  mov     cs:__security_cookie_complement, rax
0x180002939  add     rsp, 30h
0x18000293d  pop     rbp
0x18000293e  retn
```
