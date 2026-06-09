# __security_init_cookie

- ea: `0x180001a20`
- end: `0x180001afd`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001360`

## callees

- `0x180001a20`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001a7f`
- `KERNEL32!GetTickCount` at `0x180001a8f`
- `KERNEL32!GetTickCount` at `0x180001a7f`
- `KERNEL32!GetTickCount` at `0x180001a8f`
- `KERNEL32!QueryPerformanceCounter` at `0x180001aaa`
- `KERNEL32!QueryPerformanceCounter` at `0x180001aaa`
- `KERNEL32!GetCurrentProcessId` at `0x180001a67`
- `KERNEL32!GetCurrentProcessId` at `0x180001a67`
- `KERNEL32!GetCurrentThreadId` at `0x180001a73`
- `KERNEL32!GetCurrentThreadId` at `0x180001a73`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a59`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a59`

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
0x180001a20  mov     [rsp-8+arg_18], rbx
0x180001a25  push    rbp
0x180001a26  mov     rbp, rsp
0x180001a29  sub     rsp, 20h
0x180001a2d  xor     eax, eax
0x180001a2f  mov     rbx, 2B992DDFA232h
0x180001a39  mov     [rbp+arg_0], rax
0x180001a3d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a41  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a45  mov     rax, cs:__security_cookie
0x180001a4c  cmp     rax, rbx
0x180001a4f  jnz     loc_180001AE8
0x180001a55  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a59  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a5f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a63  mov     [rbp+arg_0], rax
0x180001a67  call    cs:__imp_GetCurrentProcessId
0x180001a6d  mov     eax, eax
0x180001a6f  xor     [rbp+arg_0], rax
0x180001a73  call    cs:__imp_GetCurrentThreadId
0x180001a79  mov     eax, eax
0x180001a7b  xor     [rbp+arg_0], rax
0x180001a7f  call    cs:__imp_GetTickCount
0x180001a85  mov     eax, eax
0x180001a87  shl     rax, 18h
0x180001a8b  xor     [rbp+arg_0], rax
0x180001a8f  call    cs:__imp_GetTickCount
0x180001a95  mov     eax, eax
0x180001a97  lea     rcx, [rbp+arg_0]
0x180001a9b  xor     rax, [rbp+arg_0]
0x180001a9f  xor     rax, rcx
0x180001aa2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001aa6  mov     [rbp+arg_0], rax
0x180001aaa  call    cs:__imp_QueryPerformanceCounter
0x180001ab0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ab3  mov     rcx, 0FFFFFFFFFFFFh
0x180001abd  shl     rax, 20h
0x180001ac1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ac5  xor     rax, [rbp+arg_0]
0x180001ac9  and     rax, rcx
0x180001acc  mov     rcx, rax
0x180001acf  cmp     rax, rbx
0x180001ad2  jnz     short loc_180001AE1
0x180001ad4  mov     rax, 2B992DDFA233h
0x180001ade  mov     rcx, rax
0x180001ae1  mov     cs:__security_cookie, rcx
0x180001ae8  mov     rbx, [rsp+20h+arg_18]
0x180001aed  not     rax
0x180001af0  mov     cs:__security_cookie_complement, rax
0x180001af7  add     rsp, 20h
0x180001afb  pop     rbp
0x180001afc  retn
```
