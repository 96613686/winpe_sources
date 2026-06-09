# __security_init_cookie

- ea: `0x1400017c4`
- end: `0x1400018a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400015a0`

## callees

- `0x1400017c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000180b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000180b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000184e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000184e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001833`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001833`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017fd`

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
0x1400017c4  mov     [rsp-8+arg_18], rbx
0x1400017c9  push    rbp
0x1400017ca  mov     rbp, rsp
0x1400017cd  sub     rsp, 20h
0x1400017d1  xor     eax, eax
0x1400017d3  mov     rbx, 2B992DDFA232h
0x1400017dd  mov     [rbp+arg_0], rax
0x1400017e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400017e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400017e9  mov     rax, cs:__security_cookie
0x1400017f0  cmp     rax, rbx
0x1400017f3  jnz     loc_14000188C
0x1400017f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400017fd  call    cs:__imp_GetSystemTimeAsFileTime
0x140001803  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001807  mov     [rbp+arg_0], rax
0x14000180b  call    cs:__imp_GetCurrentProcessId
0x140001811  mov     eax, eax
0x140001813  xor     [rbp+arg_0], rax
0x140001817  call    cs:__imp_GetCurrentThreadId
0x14000181d  mov     eax, eax
0x14000181f  xor     [rbp+arg_0], rax
0x140001823  call    cs:__imp_GetTickCount
0x140001829  mov     eax, eax
0x14000182b  shl     rax, 18h
0x14000182f  xor     [rbp+arg_0], rax
0x140001833  call    cs:__imp_GetTickCount
0x140001839  mov     eax, eax
0x14000183b  lea     rcx, [rbp+arg_0]
0x14000183f  xor     rax, [rbp+arg_0]
0x140001843  xor     rax, rcx
0x140001846  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000184a  mov     [rbp+arg_0], rax
0x14000184e  call    cs:__imp_QueryPerformanceCounter
0x140001854  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001857  mov     rcx, 0FFFFFFFFFFFFh
0x140001861  shl     rax, 20h
0x140001865  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001869  xor     rax, [rbp+arg_0]
0x14000186d  and     rax, rcx
0x140001870  mov     rcx, rax
0x140001873  cmp     rax, rbx
0x140001876  jnz     short loc_140001885
0x140001878  mov     rax, 2B992DDFA233h
0x140001882  mov     rcx, rax
0x140001885  mov     cs:__security_cookie, rcx
0x14000188c  mov     rbx, [rsp+20h+arg_18]
0x140001891  not     rax
0x140001894  mov     cs:__security_cookie_complement, rax
0x14000189b  add     rsp, 20h
0x14000189f  pop     rbp
0x1400018a0  retn
```
