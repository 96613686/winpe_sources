# __security_init_cookie

- ea: `0x140002b84`
- end: `0x140002c61`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022d0`

## callees

- `0x140002b84`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140002be3`
- `KERNEL32!GetTickCount` at `0x140002bf3`
- `KERNEL32!GetTickCount` at `0x140002be3`
- `KERNEL32!GetTickCount` at `0x140002bf3`
- `KERNEL32!GetCurrentThreadId` at `0x140002bd7`
- `KERNEL32!GetCurrentThreadId` at `0x140002bd7`
- `KERNEL32!GetCurrentProcessId` at `0x140002bcb`
- `KERNEL32!GetCurrentProcessId` at `0x140002bcb`
- `KERNEL32!QueryPerformanceCounter` at `0x140002c0e`
- `KERNEL32!QueryPerformanceCounter` at `0x140002c0e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140002bbd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140002bbd`

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
0x140002b84  mov     [rsp-8+arg_18], rbx
0x140002b89  push    rbp
0x140002b8a  mov     rbp, rsp
0x140002b8d  sub     rsp, 20h
0x140002b91  xor     eax, eax
0x140002b93  mov     rbx, 2B992DDFA232h
0x140002b9d  mov     [rbp+arg_0], rax
0x140002ba1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002ba5  mov     qword ptr [rbp+PerformanceCount], rax
0x140002ba9  mov     rax, cs:__security_cookie
0x140002bb0  cmp     rax, rbx
0x140002bb3  jnz     loc_140002C4C
0x140002bb9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002bbd  call    cs:__imp_GetSystemTimeAsFileTime
0x140002bc3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002bc7  mov     [rbp+arg_0], rax
0x140002bcb  call    cs:__imp_GetCurrentProcessId
0x140002bd1  mov     eax, eax
0x140002bd3  xor     [rbp+arg_0], rax
0x140002bd7  call    cs:__imp_GetCurrentThreadId
0x140002bdd  mov     eax, eax
0x140002bdf  xor     [rbp+arg_0], rax
0x140002be3  call    cs:__imp_GetTickCount
0x140002be9  mov     eax, eax
0x140002beb  shl     rax, 18h
0x140002bef  xor     [rbp+arg_0], rax
0x140002bf3  call    cs:__imp_GetTickCount
0x140002bf9  mov     eax, eax
0x140002bfb  lea     rcx, [rbp+arg_0]
0x140002bff  xor     rax, [rbp+arg_0]
0x140002c03  xor     rax, rcx
0x140002c06  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002c0a  mov     [rbp+arg_0], rax
0x140002c0e  call    cs:__imp_QueryPerformanceCounter
0x140002c14  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002c17  mov     rcx, 0FFFFFFFFFFFFh
0x140002c21  shl     rax, 20h
0x140002c25  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002c29  xor     rax, [rbp+arg_0]
0x140002c2d  and     rax, rcx
0x140002c30  mov     rcx, rax
0x140002c33  cmp     rax, rbx
0x140002c36  jnz     short loc_140002C45
0x140002c38  mov     rax, 2B992DDFA233h
0x140002c42  mov     rcx, rax
0x140002c45  mov     cs:__security_cookie, rcx
0x140002c4c  mov     rbx, [rsp+20h+arg_18]
0x140002c51  not     rax
0x140002c54  mov     cs:__security_cookie_complement, rax
0x140002c5b  add     rsp, 20h
0x140002c5f  pop     rbp
0x140002c60  retn
```
