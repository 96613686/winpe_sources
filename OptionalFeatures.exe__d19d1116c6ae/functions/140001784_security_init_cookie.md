# __security_init_cookie

- ea: `0x140001784`
- end: `0x140001861`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001490`

## callees

- `0x140001784`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400017d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400017d7`
- `KERNEL32!GetCurrentProcessId` at `0x1400017cb`
- `KERNEL32!GetCurrentProcessId` at `0x1400017cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000180e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000180e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400017e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400017f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400017e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400017f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017bd`

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
0x140001784  mov     [rsp-8+arg_18], rbx
0x140001789  push    rbp
0x14000178a  mov     rbp, rsp
0x14000178d  sub     rsp, 20h
0x140001791  xor     eax, eax
0x140001793  mov     rbx, 2B992DDFA232h
0x14000179d  mov     [rbp+arg_0], rax
0x1400017a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400017a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400017a9  mov     rax, cs:__security_cookie
0x1400017b0  cmp     rax, rbx
0x1400017b3  jnz     loc_14000184C
0x1400017b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400017bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400017c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400017c7  mov     [rbp+arg_0], rax
0x1400017cb  call    cs:__imp_GetCurrentProcessId
0x1400017d1  mov     eax, eax
0x1400017d3  xor     [rbp+arg_0], rax
0x1400017d7  call    cs:__imp_GetCurrentThreadId
0x1400017dd  mov     eax, eax
0x1400017df  xor     [rbp+arg_0], rax
0x1400017e3  call    cs:__imp_GetTickCount
0x1400017e9  mov     eax, eax
0x1400017eb  shl     rax, 18h
0x1400017ef  xor     [rbp+arg_0], rax
0x1400017f3  call    cs:__imp_GetTickCount
0x1400017f9  mov     eax, eax
0x1400017fb  lea     rcx, [rbp+arg_0]
0x1400017ff  xor     rax, [rbp+arg_0]
0x140001803  xor     rax, rcx
0x140001806  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000180a  mov     [rbp+arg_0], rax
0x14000180e  call    cs:__imp_QueryPerformanceCounter
0x140001814  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001817  mov     rcx, 0FFFFFFFFFFFFh
0x140001821  shl     rax, 20h
0x140001825  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001829  xor     rax, [rbp+arg_0]
0x14000182d  and     rax, rcx
0x140001830  mov     rcx, rax
0x140001833  cmp     rax, rbx
0x140001836  jnz     short loc_140001845
0x140001838  mov     rax, 2B992DDFA233h
0x140001842  mov     rcx, rax
0x140001845  mov     cs:__security_cookie, rcx
0x14000184c  mov     rbx, [rsp+20h+arg_18]
0x140001851  not     rax
0x140001854  mov     cs:__security_cookie_complement, rax
0x14000185b  add     rsp, 20h
0x14000185f  pop     rbp
0x140001860  retn
```
