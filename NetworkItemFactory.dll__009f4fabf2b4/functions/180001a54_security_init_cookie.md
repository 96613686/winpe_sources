# __security_init_cookie

- ea: `0x180001a54`
- end: `0x180001b31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001570`

## callees

- `0x180001a54`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180001a9b`
- `KERNEL32!GetCurrentProcessId` at `0x180001a9b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a8d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a8d`
- `KERNEL32!QueryPerformanceCounter` at `0x180001ade`
- `KERNEL32!QueryPerformanceCounter` at `0x180001ade`
- `KERNEL32!GetTickCount` at `0x180001ab3`
- `KERNEL32!GetTickCount` at `0x180001ac3`
- `KERNEL32!GetTickCount` at `0x180001ab3`
- `KERNEL32!GetTickCount` at `0x180001ac3`
- `KERNEL32!GetCurrentThreadId` at `0x180001aa7`
- `KERNEL32!GetCurrentThreadId` at `0x180001aa7`

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
0x180001a54  mov     [rsp-8+arg_18], rbx
0x180001a59  push    rbp
0x180001a5a  mov     rbp, rsp
0x180001a5d  sub     rsp, 20h
0x180001a61  xor     eax, eax
0x180001a63  mov     rbx, 2B992DDFA232h
0x180001a6d  mov     [rbp+arg_0], rax
0x180001a71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a75  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a79  mov     rax, cs:__security_cookie
0x180001a80  cmp     rax, rbx
0x180001a83  jnz     loc_180001B1C
0x180001a89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a8d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a97  mov     [rbp+arg_0], rax
0x180001a9b  call    cs:__imp_GetCurrentProcessId
0x180001aa1  mov     eax, eax
0x180001aa3  xor     [rbp+arg_0], rax
0x180001aa7  call    cs:__imp_GetCurrentThreadId
0x180001aad  mov     eax, eax
0x180001aaf  xor     [rbp+arg_0], rax
0x180001ab3  call    cs:__imp_GetTickCount
0x180001ab9  mov     eax, eax
0x180001abb  shl     rax, 18h
0x180001abf  xor     [rbp+arg_0], rax
0x180001ac3  call    cs:__imp_GetTickCount
0x180001ac9  mov     eax, eax
0x180001acb  lea     rcx, [rbp+arg_0]
0x180001acf  xor     rax, [rbp+arg_0]
0x180001ad3  xor     rax, rcx
0x180001ad6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001ada  mov     [rbp+arg_0], rax
0x180001ade  call    cs:__imp_QueryPerformanceCounter
0x180001ae4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ae7  mov     rcx, 0FFFFFFFFFFFFh
0x180001af1  shl     rax, 20h
0x180001af5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001af9  xor     rax, [rbp+arg_0]
0x180001afd  and     rax, rcx
0x180001b00  mov     rcx, rax
0x180001b03  cmp     rax, rbx
0x180001b06  jnz     short loc_180001B15
0x180001b08  mov     rax, 2B992DDFA233h
0x180001b12  mov     rcx, rax
0x180001b15  mov     cs:__security_cookie, rcx
0x180001b1c  mov     rbx, [rsp+20h+arg_18]
0x180001b21  not     rax
0x180001b24  mov     cs:__security_cookie_complement, rax
0x180001b2b  add     rsp, 20h
0x180001b2f  pop     rbp
0x180001b30  retn
```
