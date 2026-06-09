# __security_init_cookie

- ea: `0x18006c4e8`
- end: `0x18006c59d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006bfb0`

## callees

- `0x18006c4e8`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18006c51d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18006c51d`
- `KERNEL32!QueryPerformanceCounter` at `0x18006c547`
- `KERNEL32!QueryPerformanceCounter` at `0x18006c547`
- `KERNEL32!GetCurrentProcessId` at `0x18006c537`
- `KERNEL32!GetCurrentProcessId` at `0x18006c537`
- `KERNEL32!GetCurrentThreadId` at `0x18006c52b`
- `KERNEL32!GetCurrentThreadId` at `0x18006c52b`

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
0x18006c4e8  mov     [rsp-8+arg_10], rbx
0x18006c4ed  push    rbp
0x18006c4ee  mov     rbp, rsp
0x18006c4f1  sub     rsp, 30h
0x18006c4f5  mov     rax, cs:__security_cookie
0x18006c4fc  mov     rbx, 2B992DDFA232h
0x18006c506  cmp     rax, rbx
0x18006c509  jnz     short loc_18006C588
0x18006c50b  xor     eax, eax
0x18006c50d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006c511  mov     [rbp+var_10], rax
0x18006c515  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18006c519  mov     qword ptr [rbp+PerformanceCount], rax
0x18006c51d  call    cs:__imp_GetSystemTimeAsFileTime
0x18006c523  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18006c527  mov     [rbp+var_10], rax
0x18006c52b  call    cs:__imp_GetCurrentThreadId
0x18006c531  mov     eax, eax
0x18006c533  xor     [rbp+var_10], rax
0x18006c537  call    cs:__imp_GetCurrentProcessId
0x18006c53d  mov     eax, eax
0x18006c53f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18006c543  xor     [rbp+var_10], rax
0x18006c547  call    cs:__imp_QueryPerformanceCounter
0x18006c54d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18006c550  lea     rcx, [rbp+var_10]
0x18006c554  shl     rax, 20h
0x18006c558  xor     rax, qword ptr [rbp+PerformanceCount]
0x18006c55c  xor     rax, [rbp+var_10]
0x18006c560  xor     rax, rcx
0x18006c563  mov     rcx, 0FFFFFFFFFFFFh
0x18006c56d  and     rax, rcx
0x18006c570  mov     rcx, 2B992DDFA233h
0x18006c57a  cmp     rax, rbx
0x18006c57d  cmovz   rax, rcx
0x18006c581  mov     cs:__security_cookie, rax
0x18006c588  mov     rbx, [rsp+30h+arg_10]
0x18006c58d  not     rax
0x18006c590  mov     cs:__security_cookie_complement, rax
0x18006c597  add     rsp, 30h
0x18006c59b  pop     rbp
0x18006c59c  retn
```
