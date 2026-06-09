# __security_init_cookie

- ea: `0x140001cac`
- end: `0x140001d61`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001670`

## callees

- `0x140001cac`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001cef`
- `KERNEL32!GetCurrentThreadId` at `0x140001cef`
- `KERNEL32!GetCurrentProcessId` at `0x140001cfb`
- `KERNEL32!GetCurrentProcessId` at `0x140001cfb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001d0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001d0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001ce1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001ce1`

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
0x140001cac  mov     [rsp-8+arg_10], rbx
0x140001cb1  push    rbp
0x140001cb2  mov     rbp, rsp
0x140001cb5  sub     rsp, 30h
0x140001cb9  mov     rax, cs:__security_cookie
0x140001cc0  mov     rbx, 2B992DDFA232h
0x140001cca  cmp     rax, rbx
0x140001ccd  jnz     short loc_140001D4C
0x140001ccf  xor     eax, eax
0x140001cd1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001cd5  mov     [rbp+var_10], rax
0x140001cd9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001cdd  mov     qword ptr [rbp+PerformanceCount], rax
0x140001ce1  call    cs:__imp_GetSystemTimeAsFileTime
0x140001ce7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001ceb  mov     [rbp+var_10], rax
0x140001cef  call    cs:__imp_GetCurrentThreadId
0x140001cf5  mov     eax, eax
0x140001cf7  xor     [rbp+var_10], rax
0x140001cfb  call    cs:__imp_GetCurrentProcessId
0x140001d01  mov     eax, eax
0x140001d03  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001d07  xor     [rbp+var_10], rax
0x140001d0b  call    cs:__imp_QueryPerformanceCounter
0x140001d11  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001d14  lea     rcx, [rbp+var_10]
0x140001d18  shl     rax, 20h
0x140001d1c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001d20  xor     rax, [rbp+var_10]
0x140001d24  xor     rax, rcx
0x140001d27  mov     rcx, 0FFFFFFFFFFFFh
0x140001d31  and     rax, rcx
0x140001d34  mov     rcx, 2B992DDFA233h
0x140001d3e  cmp     rax, rbx
0x140001d41  cmovz   rax, rcx
0x140001d45  mov     cs:__security_cookie, rax
0x140001d4c  mov     rbx, [rsp+30h+arg_10]
0x140001d51  not     rax
0x140001d54  mov     cs:__security_cookie_complement, rax
0x140001d5b  add     rsp, 30h
0x140001d5f  pop     rbp
0x140001d60  retn
```
