# __security_init_cookie

- ea: `0x180008fc8`
- end: `0x18000907d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800087e0`

## callees

- `0x180008fc8`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180008ffd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180008ffd`
- `KERNEL32!QueryPerformanceCounter` at `0x180009027`
- `KERNEL32!QueryPerformanceCounter` at `0x180009027`
- `KERNEL32!GetCurrentProcessId` at `0x180009017`
- `KERNEL32!GetCurrentProcessId` at `0x180009017`
- `KERNEL32!GetCurrentThreadId` at `0x18000900b`
- `KERNEL32!GetCurrentThreadId` at `0x18000900b`

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
0x180008fc8  mov     [rsp-8+arg_10], rbx
0x180008fcd  push    rbp
0x180008fce  mov     rbp, rsp
0x180008fd1  sub     rsp, 30h
0x180008fd5  mov     rax, cs:__security_cookie
0x180008fdc  mov     rbx, 2B992DDFA232h
0x180008fe6  cmp     rax, rbx
0x180008fe9  jnz     short loc_180009068
0x180008feb  xor     eax, eax
0x180008fed  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180008ff1  mov     [rbp+var_10], rax
0x180008ff5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180008ff9  mov     qword ptr [rbp+PerformanceCount], rax
0x180008ffd  call    cs:__imp_GetSystemTimeAsFileTime
0x180009003  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180009007  mov     [rbp+var_10], rax
0x18000900b  call    cs:__imp_GetCurrentThreadId
0x180009011  mov     eax, eax
0x180009013  xor     [rbp+var_10], rax
0x180009017  call    cs:__imp_GetCurrentProcessId
0x18000901d  mov     eax, eax
0x18000901f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180009023  xor     [rbp+var_10], rax
0x180009027  call    cs:__imp_QueryPerformanceCounter
0x18000902d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180009030  lea     rcx, [rbp+var_10]
0x180009034  shl     rax, 20h
0x180009038  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000903c  xor     rax, [rbp+var_10]
0x180009040  xor     rax, rcx
0x180009043  mov     rcx, 0FFFFFFFFFFFFh
0x18000904d  and     rax, rcx
0x180009050  mov     rcx, 2B992DDFA233h
0x18000905a  cmp     rax, rbx
0x18000905d  cmovz   rax, rcx
0x180009061  mov     cs:__security_cookie, rax
0x180009068  mov     rbx, [rsp+30h+arg_10]
0x18000906d  not     rax
0x180009070  mov     cs:__security_cookie_complement, rax
0x180009077  add     rsp, 30h
0x18000907b  pop     rbp
0x18000907c  retn
```
