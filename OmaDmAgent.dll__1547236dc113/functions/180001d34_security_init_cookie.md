# __security_init_cookie

- ea: `0x180001d34`
- end: `0x180001e11`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001890`

## callees

- `0x180001d34`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180001d7b`
- `KERNEL32!GetCurrentProcessId` at `0x180001d7b`
- `KERNEL32!QueryPerformanceCounter` at `0x180001dbe`
- `KERNEL32!QueryPerformanceCounter` at `0x180001dbe`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d6d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d6d`
- `KERNEL32!GetTickCount` at `0x180001d93`
- `KERNEL32!GetTickCount` at `0x180001da3`
- `KERNEL32!GetTickCount` at `0x180001d93`
- `KERNEL32!GetTickCount` at `0x180001da3`
- `KERNEL32!GetCurrentThreadId` at `0x180001d87`
- `KERNEL32!GetCurrentThreadId` at `0x180001d87`

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
0x180001d34  mov     [rsp-8+arg_18], rbx
0x180001d39  push    rbp
0x180001d3a  mov     rbp, rsp
0x180001d3d  sub     rsp, 20h
0x180001d41  xor     eax, eax
0x180001d43  mov     rbx, 2B992DDFA232h
0x180001d4d  mov     [rbp+arg_0], rax
0x180001d51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d55  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d59  mov     rax, cs:__security_cookie
0x180001d60  cmp     rax, rbx
0x180001d63  jnz     loc_180001DFC
0x180001d69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d6d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d77  mov     [rbp+arg_0], rax
0x180001d7b  call    cs:__imp_GetCurrentProcessId
0x180001d81  mov     eax, eax
0x180001d83  xor     [rbp+arg_0], rax
0x180001d87  call    cs:__imp_GetCurrentThreadId
0x180001d8d  mov     eax, eax
0x180001d8f  xor     [rbp+arg_0], rax
0x180001d93  call    cs:__imp_GetTickCount
0x180001d99  mov     eax, eax
0x180001d9b  shl     rax, 18h
0x180001d9f  xor     [rbp+arg_0], rax
0x180001da3  call    cs:__imp_GetTickCount
0x180001da9  mov     eax, eax
0x180001dab  lea     rcx, [rbp+arg_0]
0x180001daf  xor     rax, [rbp+arg_0]
0x180001db3  xor     rax, rcx
0x180001db6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001dba  mov     [rbp+arg_0], rax
0x180001dbe  call    cs:__imp_QueryPerformanceCounter
0x180001dc4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001dc7  mov     rcx, 0FFFFFFFFFFFFh
0x180001dd1  shl     rax, 20h
0x180001dd5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001dd9  xor     rax, [rbp+arg_0]
0x180001ddd  and     rax, rcx
0x180001de0  mov     rcx, rax
0x180001de3  cmp     rax, rbx
0x180001de6  jnz     short loc_180001DF5
0x180001de8  mov     rax, 2B992DDFA233h
0x180001df2  mov     rcx, rax
0x180001df5  mov     cs:__security_cookie, rcx
0x180001dfc  mov     rbx, [rsp+20h+arg_18]
0x180001e01  not     rax
0x180001e04  mov     cs:__security_cookie_complement, rax
0x180001e0b  add     rsp, 20h
0x180001e0f  pop     rbp
0x180001e10  retn
```
