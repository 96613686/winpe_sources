# __security_init_cookie

- ea: `0x180002a74`
- end: `0x180002b51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002550`

## callees

- `0x180002a74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ac7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ac7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002abb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002abb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002afe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002afe`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002ad3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002ae3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002ad3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002ae3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002aad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002aad`

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
0x180002a74  mov     [rsp-8+arg_18], rbx
0x180002a79  push    rbp
0x180002a7a  mov     rbp, rsp
0x180002a7d  sub     rsp, 20h
0x180002a81  xor     eax, eax
0x180002a83  mov     rbx, 2B992DDFA232h
0x180002a8d  mov     [rbp+arg_0], rax
0x180002a91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002a95  mov     qword ptr [rbp+PerformanceCount], rax
0x180002a99  mov     rax, cs:__security_cookie
0x180002aa0  cmp     rax, rbx
0x180002aa3  jnz     loc_180002B3C
0x180002aa9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002aad  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ab3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002ab7  mov     [rbp+arg_0], rax
0x180002abb  call    cs:__imp_GetCurrentProcessId
0x180002ac1  mov     eax, eax
0x180002ac3  xor     [rbp+arg_0], rax
0x180002ac7  call    cs:__imp_GetCurrentThreadId
0x180002acd  mov     eax, eax
0x180002acf  xor     [rbp+arg_0], rax
0x180002ad3  call    cs:__imp_GetTickCount
0x180002ad9  mov     eax, eax
0x180002adb  shl     rax, 18h
0x180002adf  xor     [rbp+arg_0], rax
0x180002ae3  call    cs:__imp_GetTickCount
0x180002ae9  mov     eax, eax
0x180002aeb  lea     rcx, [rbp+arg_0]
0x180002aef  xor     rax, [rbp+arg_0]
0x180002af3  xor     rax, rcx
0x180002af6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002afa  mov     [rbp+arg_0], rax
0x180002afe  call    cs:__imp_QueryPerformanceCounter
0x180002b04  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002b07  mov     rcx, 0FFFFFFFFFFFFh
0x180002b11  shl     rax, 20h
0x180002b15  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002b19  xor     rax, [rbp+arg_0]
0x180002b1d  and     rax, rcx
0x180002b20  mov     rcx, rax
0x180002b23  cmp     rax, rbx
0x180002b26  jnz     short loc_180002B35
0x180002b28  mov     rax, 2B992DDFA233h
0x180002b32  mov     rcx, rax
0x180002b35  mov     cs:__security_cookie, rcx
0x180002b3c  mov     rbx, [rsp+20h+arg_18]
0x180002b41  not     rax
0x180002b44  mov     cs:__security_cookie_complement, rax
0x180002b4b  add     rsp, 20h
0x180002b4f  pop     rbp
0x180002b50  retn
```
