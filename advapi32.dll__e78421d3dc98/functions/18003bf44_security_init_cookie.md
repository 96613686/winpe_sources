# __security_init_cookie

- ea: `0x18003bf44`
- end: `0x18003c021`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c6f0`
- `0x18003bc08`

## callees

- `0x18003bf44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bf97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bf97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003bf8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003bf8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003bfa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003bfb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003bfa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003bfb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003bf7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003bf7d`
- `KERNEL32!QueryPerformanceCounter` at `0x18003bfce`
- `KERNEL32!QueryPerformanceCounter` at `0x18003bfce`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x18003bf44  mov     [rsp-8+arg_18], rbx
0x18003bf49  push    rbp
0x18003bf4a  mov     rbp, rsp
0x18003bf4d  sub     rsp, 20h
0x18003bf51  xor     eax, eax
0x18003bf53  mov     rbx, 2B992DDFA232h
0x18003bf5d  mov     [rbp+arg_0], rax
0x18003bf61  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003bf65  mov     qword ptr [rbp+PerformanceCount], rax
0x18003bf69  mov     rax, cs:__security_cookie
0x18003bf70  cmp     rax, rbx
0x18003bf73  jnz     loc_18003C00C
0x18003bf79  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003bf7d  call    cs:__imp_GetSystemTimeAsFileTime
0x18003bf83  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003bf87  mov     [rbp+arg_0], rax
0x18003bf8b  call    cs:__imp_GetCurrentProcessId
0x18003bf91  mov     eax, eax
0x18003bf93  xor     [rbp+arg_0], rax
0x18003bf97  call    cs:__imp_GetCurrentThreadId
0x18003bf9d  mov     eax, eax
0x18003bf9f  xor     [rbp+arg_0], rax
0x18003bfa3  call    cs:__imp_GetTickCount
0x18003bfa9  mov     eax, eax
0x18003bfab  shl     rax, 18h
0x18003bfaf  xor     [rbp+arg_0], rax
0x18003bfb3  call    cs:__imp_GetTickCount
0x18003bfb9  mov     eax, eax
0x18003bfbb  lea     rcx, [rbp+arg_0]
0x18003bfbf  xor     rax, [rbp+arg_0]
0x18003bfc3  xor     rax, rcx
0x18003bfc6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003bfca  mov     [rbp+arg_0], rax
0x18003bfce  call    cs:__imp_QueryPerformanceCounter
0x18003bfd4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003bfd7  mov     rcx, 0FFFFFFFFFFFFh
0x18003bfe1  shl     rax, 20h
0x18003bfe5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003bfe9  xor     rax, [rbp+arg_0]
0x18003bfed  and     rax, rcx
0x18003bff0  mov     rcx, rax
0x18003bff3  cmp     rax, rbx
0x18003bff6  jnz     short loc_18003C005
0x18003bff8  mov     rax, 2B992DDFA233h
0x18003c002  mov     rcx, rax
0x18003c005  mov     cs:__security_cookie, rcx
0x18003c00c  mov     rbx, [rsp+20h+arg_18]
0x18003c011  not     rax
0x18003c014  mov     cs:__security_cookie_complement, rax
0x18003c01b  add     rsp, 20h
0x18003c01f  pop     rbp
0x18003c020  retn
```
