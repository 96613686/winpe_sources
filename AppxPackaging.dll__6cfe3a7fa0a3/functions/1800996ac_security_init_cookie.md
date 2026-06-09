# __security_init_cookie

- ea: `0x1800996ac`
- end: `0x180099761`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180099250`

## callees

- `0x1800996ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800996fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800996fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800996ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800996ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009970b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009970b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800996e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800996e1`

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
0x1800996ac  mov     [rsp-8+arg_10], rbx
0x1800996b1  push    rbp
0x1800996b2  mov     rbp, rsp
0x1800996b5  sub     rsp, 30h
0x1800996b9  mov     rax, cs:__security_cookie
0x1800996c0  mov     rbx, 2B992DDFA232h
0x1800996ca  cmp     rax, rbx
0x1800996cd  jnz     short loc_18009974C
0x1800996cf  xor     eax, eax
0x1800996d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800996d5  mov     [rbp+var_10], rax
0x1800996d9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800996dd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800996e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800996e7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800996eb  mov     [rbp+var_10], rax
0x1800996ef  call    cs:__imp_GetCurrentThreadId
0x1800996f5  mov     eax, eax
0x1800996f7  xor     [rbp+var_10], rax
0x1800996fb  call    cs:__imp_GetCurrentProcessId
0x180099701  mov     eax, eax
0x180099703  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180099707  xor     [rbp+var_10], rax
0x18009970b  call    cs:__imp_QueryPerformanceCounter
0x180099711  mov     eax, dword ptr [rbp+PerformanceCount]
0x180099714  lea     rcx, [rbp+var_10]
0x180099718  shl     rax, 20h
0x18009971c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180099720  xor     rax, [rbp+var_10]
0x180099724  xor     rax, rcx
0x180099727  mov     rcx, 0FFFFFFFFFFFFh
0x180099731  and     rax, rcx
0x180099734  mov     rcx, 2B992DDFA233h
0x18009973e  cmp     rax, rbx
0x180099741  cmovz   rax, rcx
0x180099745  mov     cs:__security_cookie, rax
0x18009974c  mov     rbx, [rsp+30h+arg_10]
0x180099751  not     rax
0x180099754  mov     cs:__security_cookie_complement, rax
0x18009975b  add     rsp, 30h
0x18009975f  pop     rbp
0x180099760  retn
```
