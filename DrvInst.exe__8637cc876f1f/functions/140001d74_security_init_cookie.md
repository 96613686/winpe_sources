# __security_init_cookie

- ea: `0x140001d74`
- end: `0x140001e51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001740`

## callees

- `0x140001d74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001dbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001dbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001dc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001dc7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001dfe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001dfe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001dad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001dad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001dd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001de3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001dd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140001de3`

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
0x140001d74  mov     [rsp-8+arg_18], rbx
0x140001d79  push    rbp
0x140001d7a  mov     rbp, rsp
0x140001d7d  sub     rsp, 20h
0x140001d81  xor     eax, eax
0x140001d83  mov     rbx, 2B992DDFA232h
0x140001d8d  mov     [rbp+arg_0], rax
0x140001d91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001d95  mov     qword ptr [rbp+PerformanceCount], rax
0x140001d99  mov     rax, cs:__security_cookie
0x140001da0  cmp     rax, rbx
0x140001da3  jnz     loc_140001E3C
0x140001da9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001dad  call    cs:__imp_GetSystemTimeAsFileTime
0x140001db3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001db7  mov     [rbp+arg_0], rax
0x140001dbb  call    cs:__imp_GetCurrentProcessId
0x140001dc1  mov     eax, eax
0x140001dc3  xor     [rbp+arg_0], rax
0x140001dc7  call    cs:__imp_GetCurrentThreadId
0x140001dcd  mov     eax, eax
0x140001dcf  xor     [rbp+arg_0], rax
0x140001dd3  call    cs:__imp_GetTickCount
0x140001dd9  mov     eax, eax
0x140001ddb  shl     rax, 18h
0x140001ddf  xor     [rbp+arg_0], rax
0x140001de3  call    cs:__imp_GetTickCount
0x140001de9  mov     eax, eax
0x140001deb  lea     rcx, [rbp+arg_0]
0x140001def  xor     rax, [rbp+arg_0]
0x140001df3  xor     rax, rcx
0x140001df6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001dfa  mov     [rbp+arg_0], rax
0x140001dfe  call    cs:__imp_QueryPerformanceCounter
0x140001e04  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001e07  mov     rcx, 0FFFFFFFFFFFFh
0x140001e11  shl     rax, 20h
0x140001e15  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001e19  xor     rax, [rbp+arg_0]
0x140001e1d  and     rax, rcx
0x140001e20  mov     rcx, rax
0x140001e23  cmp     rax, rbx
0x140001e26  jnz     short loc_140001E35
0x140001e28  mov     rax, 2B992DDFA233h
0x140001e32  mov     rcx, rax
0x140001e35  mov     cs:__security_cookie, rcx
0x140001e3c  mov     rbx, [rsp+20h+arg_18]
0x140001e41  not     rax
0x140001e44  mov     cs:__security_cookie_complement, rax
0x140001e4b  add     rsp, 20h
0x140001e4f  pop     rbp
0x140001e50  retn
```
