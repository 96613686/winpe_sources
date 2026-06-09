# __security_init_cookie

- ea: `0x140002014`
- end: `0x1400020f3`
- name: `__security_init_cookie`
- size: `223`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001730`

## callees

- `0x140002014`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x14000205d`
- `KERNEL32!GetCurrentProcessId` at `0x14000205d`
- `KERNEL32!GetTickCount` at `0x140002075`
- `KERNEL32!GetTickCount` at `0x140002085`
- `KERNEL32!GetTickCount` at `0x140002075`
- `KERNEL32!GetTickCount` at `0x140002085`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000204f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000204f`
- `KERNEL32!QueryPerformanceCounter` at `0x1400020a0`
- `KERNEL32!QueryPerformanceCounter` at `0x1400020a0`
- `KERNEL32!GetCurrentThreadId` at `0x140002069`
- `KERNEL32!GetCurrentThreadId` at `0x140002069`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
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
0x140002014  mov     [rsp-8+arg_18], rbx
0x140002019  push    rbp
0x14000201a  mov     rbp, rsp
0x14000201d  sub     rsp, 20h
0x140002021  mov     rax, cs:__security_cookie
0x140002028  mov     rbx, 2B992DDFA232h
0x140002032  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14000203a  mov     qword ptr [rbp+PerformanceCount], 0
0x140002042  cmp     rax, rbx
0x140002045  jnz     loc_1400020DE
0x14000204b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000204f  call    cs:__imp_GetSystemTimeAsFileTime
0x140002055  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002059  mov     [rbp+arg_0], rax
0x14000205d  call    cs:__imp_GetCurrentProcessId
0x140002063  mov     eax, eax
0x140002065  xor     [rbp+arg_0], rax
0x140002069  call    cs:__imp_GetCurrentThreadId
0x14000206f  mov     eax, eax
0x140002071  xor     [rbp+arg_0], rax
0x140002075  call    cs:__imp_GetTickCount
0x14000207b  mov     eax, eax
0x14000207d  shl     rax, 18h
0x140002081  xor     [rbp+arg_0], rax
0x140002085  call    cs:__imp_GetTickCount
0x14000208b  mov     eax, eax
0x14000208d  lea     rcx, [rbp+arg_0]
0x140002091  xor     rax, [rbp+arg_0]
0x140002095  xor     rax, rcx
0x140002098  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000209c  mov     [rbp+arg_0], rax
0x1400020a0  call    cs:__imp_QueryPerformanceCounter
0x1400020a6  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400020a9  mov     rcx, 0FFFFFFFFFFFFh
0x1400020b3  shl     rax, 20h
0x1400020b7  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400020bb  xor     rax, [rbp+arg_0]
0x1400020bf  and     rax, rcx
0x1400020c2  mov     rcx, rax
0x1400020c5  cmp     rax, rbx
0x1400020c8  jnz     short loc_1400020D7
0x1400020ca  mov     rax, 2B992DDFA233h
0x1400020d4  mov     rcx, rax
0x1400020d7  mov     cs:__security_cookie, rcx
0x1400020de  mov     rbx, [rsp+20h+arg_18]
0x1400020e3  not     rax
0x1400020e6  mov     cs:__security_cookie_complement, rax
0x1400020ed  add     rsp, 20h
0x1400020f1  pop     rbp
0x1400020f2  retn
```
