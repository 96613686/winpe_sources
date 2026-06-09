# __security_init_cookie

- ea: `0x18002db64`
- end: `0x18002dc41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d420`

## callees

- `0x18002db64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002dbab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002dbab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dbb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002dbb7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002db9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002db9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002dbc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002dbd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002dbc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002dbd3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002dbee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002dbee`

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
0x18002db64  mov     [rsp-8+arg_18], rbx
0x18002db69  push    rbp
0x18002db6a  mov     rbp, rsp
0x18002db6d  sub     rsp, 20h
0x18002db71  xor     eax, eax
0x18002db73  mov     rbx, 2B992DDFA232h
0x18002db7d  mov     [rbp+arg_0], rax
0x18002db81  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002db85  mov     qword ptr [rbp+PerformanceCount], rax
0x18002db89  mov     rax, cs:__security_cookie
0x18002db90  cmp     rax, rbx
0x18002db93  jnz     loc_18002DC2C
0x18002db99  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002db9d  call    cs:__imp_GetSystemTimeAsFileTime
0x18002dba3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002dba7  mov     [rbp+arg_0], rax
0x18002dbab  call    cs:__imp_GetCurrentProcessId
0x18002dbb1  mov     eax, eax
0x18002dbb3  xor     [rbp+arg_0], rax
0x18002dbb7  call    cs:__imp_GetCurrentThreadId
0x18002dbbd  mov     eax, eax
0x18002dbbf  xor     [rbp+arg_0], rax
0x18002dbc3  call    cs:__imp_GetTickCount
0x18002dbc9  mov     eax, eax
0x18002dbcb  shl     rax, 18h
0x18002dbcf  xor     [rbp+arg_0], rax
0x18002dbd3  call    cs:__imp_GetTickCount
0x18002dbd9  mov     eax, eax
0x18002dbdb  lea     rcx, [rbp+arg_0]
0x18002dbdf  xor     rax, [rbp+arg_0]
0x18002dbe3  xor     rax, rcx
0x18002dbe6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002dbea  mov     [rbp+arg_0], rax
0x18002dbee  call    cs:__imp_QueryPerformanceCounter
0x18002dbf4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002dbf7  mov     rcx, 0FFFFFFFFFFFFh
0x18002dc01  shl     rax, 20h
0x18002dc05  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002dc09  xor     rax, [rbp+arg_0]
0x18002dc0d  and     rax, rcx
0x18002dc10  mov     rcx, rax
0x18002dc13  cmp     rax, rbx
0x18002dc16  jnz     short loc_18002DC25
0x18002dc18  mov     rax, 2B992DDFA233h
0x18002dc22  mov     rcx, rax
0x18002dc25  mov     cs:__security_cookie, rcx
0x18002dc2c  mov     rbx, [rsp+20h+arg_18]
0x18002dc31  not     rax
0x18002dc34  mov     cs:__security_cookie_complement, rax
0x18002dc3b  add     rsp, 20h
0x18002dc3f  pop     rbp
0x18002dc40  retn
```
