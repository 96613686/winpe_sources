# __security_init_cookie

- ea: `0x140001754`
- end: `0x140001831`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001500`

## callees

- `0x140001754`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000178d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000178d`
- `KERNEL32!QueryPerformanceCounter` at `0x1400017de`
- `KERNEL32!QueryPerformanceCounter` at `0x1400017de`
- `KERNEL32!GetCurrentProcessId` at `0x14000179b`
- `KERNEL32!GetCurrentProcessId` at `0x14000179b`
- `KERNEL32!GetCurrentThreadId` at `0x1400017a7`
- `KERNEL32!GetCurrentThreadId` at `0x1400017a7`
- `KERNEL32!GetTickCount` at `0x1400017b3`
- `KERNEL32!GetTickCount` at `0x1400017c3`
- `KERNEL32!GetTickCount` at `0x1400017b3`
- `KERNEL32!GetTickCount` at `0x1400017c3`

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
0x140001754  mov     [rsp-8+arg_18], rbx
0x140001759  push    rbp
0x14000175a  mov     rbp, rsp
0x14000175d  sub     rsp, 20h
0x140001761  xor     eax, eax
0x140001763  mov     rbx, 2B992DDFA232h
0x14000176d  mov     [rbp+arg_0], rax
0x140001771  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001775  mov     qword ptr [rbp+PerformanceCount], rax
0x140001779  mov     rax, cs:__security_cookie
0x140001780  cmp     rax, rbx
0x140001783  jnz     loc_14000181C
0x140001789  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000178d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001793  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001797  mov     [rbp+arg_0], rax
0x14000179b  call    cs:__imp_GetCurrentProcessId
0x1400017a1  mov     eax, eax
0x1400017a3  xor     [rbp+arg_0], rax
0x1400017a7  call    cs:__imp_GetCurrentThreadId
0x1400017ad  mov     eax, eax
0x1400017af  xor     [rbp+arg_0], rax
0x1400017b3  call    cs:__imp_GetTickCount
0x1400017b9  mov     eax, eax
0x1400017bb  shl     rax, 18h
0x1400017bf  xor     [rbp+arg_0], rax
0x1400017c3  call    cs:__imp_GetTickCount
0x1400017c9  mov     eax, eax
0x1400017cb  lea     rcx, [rbp+arg_0]
0x1400017cf  xor     rax, [rbp+arg_0]
0x1400017d3  xor     rax, rcx
0x1400017d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400017da  mov     [rbp+arg_0], rax
0x1400017de  call    cs:__imp_QueryPerformanceCounter
0x1400017e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400017e7  mov     rcx, 0FFFFFFFFFFFFh
0x1400017f1  shl     rax, 20h
0x1400017f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400017f9  xor     rax, [rbp+arg_0]
0x1400017fd  and     rax, rcx
0x140001800  mov     rcx, rax
0x140001803  cmp     rax, rbx
0x140001806  jnz     short loc_140001815
0x140001808  mov     rax, 2B992DDFA233h
0x140001812  mov     rcx, rax
0x140001815  mov     cs:__security_cookie, rcx
0x14000181c  mov     rbx, [rsp+20h+arg_18]
0x140001821  not     rax
0x140001824  mov     cs:__security_cookie_complement, rax
0x14000182b  add     rsp, 20h
0x14000182f  pop     rbp
0x140001830  retn
```
