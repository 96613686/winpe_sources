# __security_init_cookie

- ea: `0x140001704`
- end: `0x1400017e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400014c0`

## callees

- `0x140001704`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x14000178e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000178e`
- `KERNEL32!GetCurrentProcessId` at `0x14000174b`
- `KERNEL32!GetCurrentProcessId` at `0x14000174b`
- `KERNEL32!GetCurrentThreadId` at `0x140001757`
- `KERNEL32!GetCurrentThreadId` at `0x140001757`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000173d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000173d`
- `KERNEL32!GetTickCount` at `0x140001763`
- `KERNEL32!GetTickCount` at `0x140001773`
- `KERNEL32!GetTickCount` at `0x140001763`
- `KERNEL32!GetTickCount` at `0x140001773`

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
0x140001704  mov     [rsp-8+arg_18], rbx
0x140001709  push    rbp
0x14000170a  mov     rbp, rsp
0x14000170d  sub     rsp, 20h
0x140001711  xor     eax, eax
0x140001713  mov     rbx, 2B992DDFA232h
0x14000171d  mov     [rbp+arg_0], rax
0x140001721  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001725  mov     qword ptr [rbp+PerformanceCount], rax
0x140001729  mov     rax, cs:__security_cookie
0x140001730  cmp     rax, rbx
0x140001733  jnz     loc_1400017CC
0x140001739  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000173d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001743  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001747  mov     [rbp+arg_0], rax
0x14000174b  call    cs:__imp_GetCurrentProcessId
0x140001751  mov     eax, eax
0x140001753  xor     [rbp+arg_0], rax
0x140001757  call    cs:__imp_GetCurrentThreadId
0x14000175d  mov     eax, eax
0x14000175f  xor     [rbp+arg_0], rax
0x140001763  call    cs:__imp_GetTickCount
0x140001769  mov     eax, eax
0x14000176b  shl     rax, 18h
0x14000176f  xor     [rbp+arg_0], rax
0x140001773  call    cs:__imp_GetTickCount
0x140001779  mov     eax, eax
0x14000177b  lea     rcx, [rbp+arg_0]
0x14000177f  xor     rax, [rbp+arg_0]
0x140001783  xor     rax, rcx
0x140001786  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000178a  mov     [rbp+arg_0], rax
0x14000178e  call    cs:__imp_QueryPerformanceCounter
0x140001794  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001797  mov     rcx, 0FFFFFFFFFFFFh
0x1400017a1  shl     rax, 20h
0x1400017a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400017a9  xor     rax, [rbp+arg_0]
0x1400017ad  and     rax, rcx
0x1400017b0  mov     rcx, rax
0x1400017b3  cmp     rax, rbx
0x1400017b6  jnz     short loc_1400017C5
0x1400017b8  mov     rax, 2B992DDFA233h
0x1400017c2  mov     rcx, rax
0x1400017c5  mov     cs:__security_cookie, rcx
0x1400017cc  mov     rbx, [rsp+20h+arg_18]
0x1400017d1  not     rax
0x1400017d4  mov     cs:__security_cookie_complement, rax
0x1400017db  add     rsp, 20h
0x1400017df  pop     rbp
0x1400017e0  retn
```
