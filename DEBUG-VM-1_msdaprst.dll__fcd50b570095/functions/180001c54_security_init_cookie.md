# __security_init_cookie

- ea: `0x180001c54`
- end: `0x180001d31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001370`

## callees

- `0x180001c54`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001cb3`
- `KERNEL32!GetTickCount` at `0x180001cc3`
- `KERNEL32!GetTickCount` at `0x180001cb3`
- `KERNEL32!GetTickCount` at `0x180001cc3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c8d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c8d`
- `KERNEL32!QueryPerformanceCounter` at `0x180001cde`
- `KERNEL32!QueryPerformanceCounter` at `0x180001cde`
- `KERNEL32!GetCurrentProcessId` at `0x180001c9b`
- `KERNEL32!GetCurrentProcessId` at `0x180001c9b`
- `KERNEL32!GetCurrentThreadId` at `0x180001ca7`
- `KERNEL32!GetCurrentThreadId` at `0x180001ca7`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001c54  mov     [rsp-8+arg_18], rbx
0x180001c59  push    rbp
0x180001c5a  mov     rbp, rsp
0x180001c5d  sub     rsp, 20h
0x180001c61  xor     eax, eax
0x180001c63  mov     rbx, 2B992DDFA232h
0x180001c6d  mov     [rbp+arg_0], rax
0x180001c71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001c75  mov     qword ptr [rbp+PerformanceCount], rax
0x180001c79  mov     rax, cs:__security_cookie
0x180001c80  cmp     rax, rbx
0x180001c83  jnz     loc_180001D1C
0x180001c89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001c8d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001c93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001c97  mov     [rbp+arg_0], rax
0x180001c9b  call    cs:__imp_GetCurrentProcessId
0x180001ca1  mov     eax, eax
0x180001ca3  xor     [rbp+arg_0], rax
0x180001ca7  call    cs:__imp_GetCurrentThreadId
0x180001cad  mov     eax, eax
0x180001caf  xor     [rbp+arg_0], rax
0x180001cb3  call    cs:__imp_GetTickCount
0x180001cb9  mov     eax, eax
0x180001cbb  shl     rax, 18h
0x180001cbf  xor     [rbp+arg_0], rax
0x180001cc3  call    cs:__imp_GetTickCount
0x180001cc9  mov     eax, eax
0x180001ccb  lea     rcx, [rbp+arg_0]
0x180001ccf  xor     rax, [rbp+arg_0]
0x180001cd3  xor     rax, rcx
0x180001cd6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001cda  mov     [rbp+arg_0], rax
0x180001cde  call    cs:__imp_QueryPerformanceCounter
0x180001ce4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ce7  mov     rcx, 0FFFFFFFFFFFFh
0x180001cf1  shl     rax, 20h
0x180001cf5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001cf9  xor     rax, [rbp+arg_0]
0x180001cfd  and     rax, rcx
0x180001d00  mov     rcx, rax
0x180001d03  cmp     rax, rbx
0x180001d06  jnz     short loc_180001D15
0x180001d08  mov     rax, 2B992DDFA233h
0x180001d12  mov     rcx, rax
0x180001d15  mov     cs:__security_cookie, rcx
0x180001d1c  mov     rbx, [rsp+20h+arg_18]
0x180001d21  not     rax
0x180001d24  mov     cs:__security_cookie_complement, rax
0x180001d2b  add     rsp, 20h
0x180001d2f  pop     rbp
0x180001d30  retn
```
