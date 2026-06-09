# __security_init_cookie

- ea: `0x180002a98`
- end: `0x180002b4d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022b0`

## callees

- `0x180002a98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002adb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002adb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002af7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002af7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002acd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002acd`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180002a98  mov     [rsp-8+arg_10], rbx
0x180002a9d  push    rbp
0x180002a9e  mov     rbp, rsp
0x180002aa1  sub     rsp, 30h
0x180002aa5  mov     rax, cs:__security_cookie
0x180002aac  mov     rbx, 2B992DDFA232h
0x180002ab6  cmp     rax, rbx
0x180002ab9  jnz     short loc_180002B38
0x180002abb  xor     eax, eax
0x180002abd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002ac1  mov     [rbp+var_10], rax
0x180002ac5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002ac9  mov     qword ptr [rbp+PerformanceCount], rax
0x180002acd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002ad3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002ad7  mov     [rbp+var_10], rax
0x180002adb  call    cs:__imp_GetCurrentThreadId
0x180002ae1  mov     eax, eax
0x180002ae3  xor     [rbp+var_10], rax
0x180002ae7  call    cs:__imp_GetCurrentProcessId
0x180002aed  mov     eax, eax
0x180002aef  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002af3  xor     [rbp+var_10], rax
0x180002af7  call    cs:__imp_QueryPerformanceCounter
0x180002afd  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002b00  lea     rcx, [rbp+var_10]
0x180002b04  shl     rax, 20h
0x180002b08  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002b0c  xor     rax, [rbp+var_10]
0x180002b10  xor     rax, rcx
0x180002b13  mov     rcx, 0FFFFFFFFFFFFh
0x180002b1d  and     rax, rcx
0x180002b20  mov     rcx, 2B992DDFA233h
0x180002b2a  cmp     rax, rbx
0x180002b2d  cmovz   rax, rcx
0x180002b31  mov     cs:__security_cookie, rax
0x180002b38  mov     rbx, [rsp+30h+arg_10]
0x180002b3d  not     rax
0x180002b40  mov     cs:__security_cookie_complement, rax
0x180002b47  add     rsp, 30h
0x180002b4b  pop     rbp
0x180002b4c  retn
```
