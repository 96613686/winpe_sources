# __security_init_cookie

- ea: `0x180022b2c`
- end: `0x180022be1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022550`

## callees

- `0x180022b2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022b6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022b6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022b7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180022b7b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022b8b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180022b8b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022b61`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022b61`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180022b2c  mov     [rsp-8+arg_10], rbx
0x180022b31  push    rbp
0x180022b32  mov     rbp, rsp
0x180022b35  sub     rsp, 30h
0x180022b39  mov     rax, cs:__security_cookie
0x180022b40  mov     rbx, 2B992DDFA232h
0x180022b4a  cmp     rax, rbx
0x180022b4d  jnz     short loc_180022BCC
0x180022b4f  xor     eax, eax
0x180022b51  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180022b55  mov     [rbp+var_10], rax
0x180022b59  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180022b5d  mov     qword ptr [rbp+PerformanceCount], rax
0x180022b61  call    cs:__imp_GetSystemTimeAsFileTime
0x180022b67  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180022b6b  mov     [rbp+var_10], rax
0x180022b6f  call    cs:__imp_GetCurrentThreadId
0x180022b75  mov     eax, eax
0x180022b77  xor     [rbp+var_10], rax
0x180022b7b  call    cs:__imp_GetCurrentProcessId
0x180022b81  mov     eax, eax
0x180022b83  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180022b87  xor     [rbp+var_10], rax
0x180022b8b  call    cs:__imp_QueryPerformanceCounter
0x180022b91  mov     eax, dword ptr [rbp+PerformanceCount]
0x180022b94  lea     rcx, [rbp+var_10]
0x180022b98  shl     rax, 20h
0x180022b9c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180022ba0  xor     rax, [rbp+var_10]
0x180022ba4  xor     rax, rcx
0x180022ba7  mov     rcx, 0FFFFFFFFFFFFh
0x180022bb1  and     rax, rcx
0x180022bb4  mov     rcx, 2B992DDFA233h
0x180022bbe  cmp     rax, rbx
0x180022bc1  cmovz   rax, rcx
0x180022bc5  mov     cs:__security_cookie, rax
0x180022bcc  mov     rbx, [rsp+30h+arg_10]
0x180022bd1  not     rax
0x180022bd4  mov     cs:__security_cookie_complement, rax
0x180022bdb  add     rsp, 30h
0x180022bdf  pop     rbp
0x180022be0  retn
```
