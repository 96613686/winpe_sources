# __security_init_cookie

- ea: `0x140001a74`
- end: `0x140001b51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001520`

## callees

- `0x140001a74`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x140001afe`
- `KERNEL32!QueryPerformanceCounter` at `0x140001afe`
- `KERNEL32!GetCurrentProcessId` at `0x140001abb`
- `KERNEL32!GetCurrentProcessId` at `0x140001abb`
- `KERNEL32!GetCurrentThreadId` at `0x140001ac7`
- `KERNEL32!GetCurrentThreadId` at `0x140001ac7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001aad`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001aad`
- `KERNEL32!GetTickCount` at `0x140001ad3`
- `KERNEL32!GetTickCount` at `0x140001ae3`
- `KERNEL32!GetTickCount` at `0x140001ad3`
- `KERNEL32!GetTickCount` at `0x140001ae3`

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
0x140001a74  mov     [rsp-8+arg_18], rbx
0x140001a79  push    rbp
0x140001a7a  mov     rbp, rsp
0x140001a7d  sub     rsp, 20h
0x140001a81  xor     eax, eax
0x140001a83  mov     rbx, 2B992DDFA232h
0x140001a8d  mov     [rbp+arg_0], rax
0x140001a91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001a95  mov     qword ptr [rbp+PerformanceCount], rax
0x140001a99  mov     rax, cs:__security_cookie
0x140001aa0  cmp     rax, rbx
0x140001aa3  jnz     loc_140001B3C
0x140001aa9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001aad  call    cs:__imp_GetSystemTimeAsFileTime
0x140001ab3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001ab7  mov     [rbp+arg_0], rax
0x140001abb  call    cs:__imp_GetCurrentProcessId
0x140001ac1  mov     eax, eax
0x140001ac3  xor     [rbp+arg_0], rax
0x140001ac7  call    cs:__imp_GetCurrentThreadId
0x140001acd  mov     eax, eax
0x140001acf  xor     [rbp+arg_0], rax
0x140001ad3  call    cs:__imp_GetTickCount
0x140001ad9  mov     eax, eax
0x140001adb  shl     rax, 18h
0x140001adf  xor     [rbp+arg_0], rax
0x140001ae3  call    cs:__imp_GetTickCount
0x140001ae9  mov     eax, eax
0x140001aeb  lea     rcx, [rbp+arg_0]
0x140001aef  xor     rax, [rbp+arg_0]
0x140001af3  xor     rax, rcx
0x140001af6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001afa  mov     [rbp+arg_0], rax
0x140001afe  call    cs:__imp_QueryPerformanceCounter
0x140001b04  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001b07  mov     rcx, 0FFFFFFFFFFFFh
0x140001b11  shl     rax, 20h
0x140001b15  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001b19  xor     rax, [rbp+arg_0]
0x140001b1d  and     rax, rcx
0x140001b20  mov     rcx, rax
0x140001b23  cmp     rax, rbx
0x140001b26  jnz     short loc_140001B35
0x140001b28  mov     rax, 2B992DDFA233h
0x140001b32  mov     rcx, rax
0x140001b35  mov     cs:__security_cookie, rcx
0x140001b3c  mov     rbx, [rsp+20h+arg_18]
0x140001b41  not     rax
0x140001b44  mov     cs:__security_cookie_complement, rax
0x140001b4b  add     rsp, 20h
0x140001b4f  pop     rbp
0x140001b50  retn
```
