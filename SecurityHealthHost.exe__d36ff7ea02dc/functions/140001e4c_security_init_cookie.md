# __security_init_cookie

- ea: `0x140001e4c`
- end: `0x140001f01`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400015c0`

## callees

- `0x140001e4c`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x140001eab`
- `KERNEL32!QueryPerformanceCounter` at `0x140001eab`
- `KERNEL32!GetCurrentProcessId` at `0x140001e9b`
- `KERNEL32!GetCurrentProcessId` at `0x140001e9b`
- `KERNEL32!GetCurrentThreadId` at `0x140001e8f`
- `KERNEL32!GetCurrentThreadId` at `0x140001e8f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001e81`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001e81`

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
0x140001e4c  mov     [rsp-8+arg_10], rbx
0x140001e51  push    rbp
0x140001e52  mov     rbp, rsp
0x140001e55  sub     rsp, 30h
0x140001e59  mov     rax, cs:__security_cookie
0x140001e60  mov     rbx, 2B992DDFA232h
0x140001e6a  cmp     rax, rbx
0x140001e6d  jnz     short loc_140001EEC
0x140001e6f  xor     eax, eax
0x140001e71  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001e75  mov     [rbp+var_10], rax
0x140001e79  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001e7d  mov     qword ptr [rbp+PerformanceCount], rax
0x140001e81  call    cs:__imp_GetSystemTimeAsFileTime
0x140001e87  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001e8b  mov     [rbp+var_10], rax
0x140001e8f  call    cs:__imp_GetCurrentThreadId
0x140001e95  mov     eax, eax
0x140001e97  xor     [rbp+var_10], rax
0x140001e9b  call    cs:__imp_GetCurrentProcessId
0x140001ea1  mov     eax, eax
0x140001ea3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001ea7  xor     [rbp+var_10], rax
0x140001eab  call    cs:__imp_QueryPerformanceCounter
0x140001eb1  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001eb4  lea     rcx, [rbp+var_10]
0x140001eb8  shl     rax, 20h
0x140001ebc  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001ec0  xor     rax, [rbp+var_10]
0x140001ec4  xor     rax, rcx
0x140001ec7  mov     rcx, 0FFFFFFFFFFFFh
0x140001ed1  and     rax, rcx
0x140001ed4  mov     rcx, 2B992DDFA233h
0x140001ede  cmp     rax, rbx
0x140001ee1  cmovz   rax, rcx
0x140001ee5  mov     cs:__security_cookie, rax
0x140001eec  mov     rbx, [rsp+30h+arg_10]
0x140001ef1  not     rax
0x140001ef4  mov     cs:__security_cookie_complement, rax
0x140001efb  add     rsp, 30h
0x140001eff  pop     rbp
0x140001f00  retn
```
