# __security_init_cookie

- ea: `0x140002b54`
- end: `0x140002c31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022b0`

## callees

- `0x140002b54`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140002bb3`
- `KERNEL32!GetTickCount` at `0x140002bc3`
- `KERNEL32!GetTickCount` at `0x140002bb3`
- `KERNEL32!GetTickCount` at `0x140002bc3`
- `KERNEL32!GetCurrentThreadId` at `0x140002ba7`
- `KERNEL32!GetCurrentThreadId` at `0x140002ba7`
- `KERNEL32!GetCurrentProcessId` at `0x140002b9b`
- `KERNEL32!GetCurrentProcessId` at `0x140002b9b`
- `KERNEL32!QueryPerformanceCounter` at `0x140002bde`
- `KERNEL32!QueryPerformanceCounter` at `0x140002bde`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140002b8d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140002b8d`

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
0x140002b54  mov     [rsp-8+arg_18], rbx
0x140002b59  push    rbp
0x140002b5a  mov     rbp, rsp
0x140002b5d  sub     rsp, 20h
0x140002b61  xor     eax, eax
0x140002b63  mov     rbx, 2B992DDFA232h
0x140002b6d  mov     [rbp+arg_0], rax
0x140002b71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002b75  mov     qword ptr [rbp+PerformanceCount], rax
0x140002b79  mov     rax, cs:__security_cookie
0x140002b80  cmp     rax, rbx
0x140002b83  jnz     loc_140002C1C
0x140002b89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002b8d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002b93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002b97  mov     [rbp+arg_0], rax
0x140002b9b  call    cs:__imp_GetCurrentProcessId
0x140002ba1  mov     eax, eax
0x140002ba3  xor     [rbp+arg_0], rax
0x140002ba7  call    cs:__imp_GetCurrentThreadId
0x140002bad  mov     eax, eax
0x140002baf  xor     [rbp+arg_0], rax
0x140002bb3  call    cs:__imp_GetTickCount
0x140002bb9  mov     eax, eax
0x140002bbb  shl     rax, 18h
0x140002bbf  xor     [rbp+arg_0], rax
0x140002bc3  call    cs:__imp_GetTickCount
0x140002bc9  mov     eax, eax
0x140002bcb  lea     rcx, [rbp+arg_0]
0x140002bcf  xor     rax, [rbp+arg_0]
0x140002bd3  xor     rax, rcx
0x140002bd6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002bda  mov     [rbp+arg_0], rax
0x140002bde  call    cs:__imp_QueryPerformanceCounter
0x140002be4  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002be7  mov     rcx, 0FFFFFFFFFFFFh
0x140002bf1  shl     rax, 20h
0x140002bf5  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002bf9  xor     rax, [rbp+arg_0]
0x140002bfd  and     rax, rcx
0x140002c00  mov     rcx, rax
0x140002c03  cmp     rax, rbx
0x140002c06  jnz     short loc_140002C15
0x140002c08  mov     rax, 2B992DDFA233h
0x140002c12  mov     rcx, rax
0x140002c15  mov     cs:__security_cookie, rcx
0x140002c1c  mov     rbx, [rsp+20h+arg_18]
0x140002c21  not     rax
0x140002c24  mov     cs:__security_cookie_complement, rax
0x140002c2b  add     rsp, 20h
0x140002c2f  pop     rbp
0x140002c30  retn
```
