# __security_init_cookie

- ea: `0x140002dc0`
- end: `0x140002e75`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002990`

## callees

- `0x140002dc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002e03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002e03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002e0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002df5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002df5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002e1f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002e1f`

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
0x140002dc0  mov     [rsp-8+arg_10], rbx
0x140002dc5  push    rbp
0x140002dc6  mov     rbp, rsp
0x140002dc9  sub     rsp, 30h
0x140002dcd  mov     rax, cs:__security_cookie
0x140002dd4  mov     rbx, 2B992DDFA232h
0x140002dde  cmp     rax, rbx
0x140002de1  jnz     short loc_140002E60
0x140002de3  xor     eax, eax
0x140002de5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002de9  mov     [rbp+var_10], rax
0x140002ded  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002df1  mov     qword ptr [rbp+PerformanceCount], rax
0x140002df5  call    cs:__imp_GetSystemTimeAsFileTime
0x140002dfb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002dff  mov     [rbp+var_10], rax
0x140002e03  call    cs:__imp_GetCurrentThreadId
0x140002e09  mov     eax, eax
0x140002e0b  xor     [rbp+var_10], rax
0x140002e0f  call    cs:__imp_GetCurrentProcessId
0x140002e15  mov     eax, eax
0x140002e17  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002e1b  xor     [rbp+var_10], rax
0x140002e1f  call    cs:__imp_QueryPerformanceCounter
0x140002e25  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002e28  lea     rcx, [rbp+var_10]
0x140002e2c  shl     rax, 20h
0x140002e30  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002e34  xor     rax, [rbp+var_10]
0x140002e38  xor     rax, rcx
0x140002e3b  mov     rcx, 0FFFFFFFFFFFFh
0x140002e45  and     rax, rcx
0x140002e48  mov     rcx, 2B992DDFA233h
0x140002e52  cmp     rax, rbx
0x140002e55  cmovz   rax, rcx
0x140002e59  mov     cs:__security_cookie, rax
0x140002e60  mov     rbx, [rsp+30h+arg_10]
0x140002e65  not     rax
0x140002e68  mov     cs:__security_cookie_complement, rax
0x140002e6f  add     rsp, 30h
0x140002e73  pop     rbp
0x140002e74  retn
```
