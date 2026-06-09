# __security_init_cookie

- ea: `0x1400020d4`
- end: `0x1400021b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001ac0`

## callees

- `0x1400020d4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000210d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000210d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002133`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002143`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002133`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140002143`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000211b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000211b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002127`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002127`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000215e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000215e`

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
0x1400020d4  mov     [rsp-8+arg_18], rbx
0x1400020d9  push    rbp
0x1400020da  mov     rbp, rsp
0x1400020dd  sub     rsp, 20h
0x1400020e1  xor     eax, eax
0x1400020e3  mov     rbx, 2B992DDFA232h
0x1400020ed  mov     [rbp+arg_0], rax
0x1400020f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400020f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400020f9  mov     rax, cs:__security_cookie
0x140002100  cmp     rax, rbx
0x140002103  jnz     loc_14000219C
0x140002109  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000210d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002113  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002117  mov     [rbp+arg_0], rax
0x14000211b  call    cs:__imp_GetCurrentProcessId
0x140002121  mov     eax, eax
0x140002123  xor     [rbp+arg_0], rax
0x140002127  call    cs:__imp_GetCurrentThreadId
0x14000212d  mov     eax, eax
0x14000212f  xor     [rbp+arg_0], rax
0x140002133  call    cs:__imp_GetTickCount
0x140002139  mov     eax, eax
0x14000213b  shl     rax, 18h
0x14000213f  xor     [rbp+arg_0], rax
0x140002143  call    cs:__imp_GetTickCount
0x140002149  mov     eax, eax
0x14000214b  lea     rcx, [rbp+arg_0]
0x14000214f  xor     rax, [rbp+arg_0]
0x140002153  xor     rax, rcx
0x140002156  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000215a  mov     [rbp+arg_0], rax
0x14000215e  call    cs:__imp_QueryPerformanceCounter
0x140002164  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002167  mov     rcx, 0FFFFFFFFFFFFh
0x140002171  shl     rax, 20h
0x140002175  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002179  xor     rax, [rbp+arg_0]
0x14000217d  and     rax, rcx
0x140002180  mov     rcx, rax
0x140002183  cmp     rax, rbx
0x140002186  jnz     short loc_140002195
0x140002188  mov     rax, 2B992DDFA233h
0x140002192  mov     rcx, rax
0x140002195  mov     cs:__security_cookie, rcx
0x14000219c  mov     rbx, [rsp+20h+arg_18]
0x1400021a1  not     rax
0x1400021a4  mov     cs:__security_cookie_complement, rax
0x1400021ab  add     rsp, 20h
0x1400021af  pop     rbp
0x1400021b0  retn
```
