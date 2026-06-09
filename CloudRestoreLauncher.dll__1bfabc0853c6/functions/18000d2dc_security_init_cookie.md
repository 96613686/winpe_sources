# __security_init_cookie

- ea: `0x18000d2dc`
- end: `0x18000d391`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c690`

## callees

- `0x18000d2dc`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000d311`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000d311`
- `KERNEL32!QueryPerformanceCounter` at `0x18000d33b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000d33b`
- `KERNEL32!GetCurrentProcessId` at `0x18000d32b`
- `KERNEL32!GetCurrentProcessId` at `0x18000d32b`
- `KERNEL32!GetCurrentThreadId` at `0x18000d31f`
- `KERNEL32!GetCurrentThreadId` at `0x18000d31f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
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
0x18000d2dc  mov     [rsp-8+arg_10], rbx
0x18000d2e1  push    rbp
0x18000d2e2  mov     rbp, rsp
0x18000d2e5  sub     rsp, 30h
0x18000d2e9  mov     rax, cs:__security_cookie
0x18000d2f0  mov     rbx, 2B992DDFA232h
0x18000d2fa  cmp     rax, rbx
0x18000d2fd  jnz     short loc_18000D37C
0x18000d2ff  xor     eax, eax
0x18000d301  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d305  mov     [rbp+var_10], rax
0x18000d309  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000d30d  mov     qword ptr [rbp+PerformanceCount], rax
0x18000d311  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d317  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d31b  mov     [rbp+var_10], rax
0x18000d31f  call    cs:__imp_GetCurrentThreadId
0x18000d325  mov     eax, eax
0x18000d327  xor     [rbp+var_10], rax
0x18000d32b  call    cs:__imp_GetCurrentProcessId
0x18000d331  mov     eax, eax
0x18000d333  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000d337  xor     [rbp+var_10], rax
0x18000d33b  call    cs:__imp_QueryPerformanceCounter
0x18000d341  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000d344  lea     rcx, [rbp+var_10]
0x18000d348  shl     rax, 20h
0x18000d34c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000d350  xor     rax, [rbp+var_10]
0x18000d354  xor     rax, rcx
0x18000d357  mov     rcx, 0FFFFFFFFFFFFh
0x18000d361  and     rax, rcx
0x18000d364  mov     rcx, 2B992DDFA233h
0x18000d36e  cmp     rax, rbx
0x18000d371  cmovz   rax, rcx
0x18000d375  mov     cs:__security_cookie, rax
0x18000d37c  mov     rbx, [rsp+30h+arg_10]
0x18000d381  not     rax
0x18000d384  mov     cs:__security_cookie_complement, rax
0x18000d38b  add     rsp, 30h
0x18000d38f  pop     rbp
0x18000d390  retn
```
