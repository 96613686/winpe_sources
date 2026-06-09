# __security_init_cookie

- ea: `0x18001c09c`
- end: `0x18001c151`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bb90`

## callees

- `0x18001c09c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c0df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c0df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c0eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c0eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c0d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c0d1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001c0fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001c0fb`

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
0x18001c09c  mov     [rsp-8+arg_10], rbx
0x18001c0a1  push    rbp
0x18001c0a2  mov     rbp, rsp
0x18001c0a5  sub     rsp, 30h
0x18001c0a9  mov     rax, cs:__security_cookie
0x18001c0b0  mov     rbx, 2B992DDFA232h
0x18001c0ba  cmp     rax, rbx
0x18001c0bd  jnz     short loc_18001C13C
0x18001c0bf  xor     eax, eax
0x18001c0c1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c0c5  mov     [rbp+var_10], rax
0x18001c0c9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001c0cd  mov     qword ptr [rbp+PerformanceCount], rax
0x18001c0d1  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c0d7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001c0db  mov     [rbp+var_10], rax
0x18001c0df  call    cs:__imp_GetCurrentThreadId
0x18001c0e5  mov     eax, eax
0x18001c0e7  xor     [rbp+var_10], rax
0x18001c0eb  call    cs:__imp_GetCurrentProcessId
0x18001c0f1  mov     eax, eax
0x18001c0f3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001c0f7  xor     [rbp+var_10], rax
0x18001c0fb  call    cs:__imp_QueryPerformanceCounter
0x18001c101  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001c104  lea     rcx, [rbp+var_10]
0x18001c108  shl     rax, 20h
0x18001c10c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001c110  xor     rax, [rbp+var_10]
0x18001c114  xor     rax, rcx
0x18001c117  mov     rcx, 0FFFFFFFFFFFFh
0x18001c121  and     rax, rcx
0x18001c124  mov     rcx, 2B992DDFA233h
0x18001c12e  cmp     rax, rbx
0x18001c131  cmovz   rax, rcx
0x18001c135  mov     cs:__security_cookie, rax
0x18001c13c  mov     rbx, [rsp+30h+arg_10]
0x18001c141  not     rax
0x18001c144  mov     cs:__security_cookie_complement, rax
0x18001c14b  add     rsp, 30h
0x18001c14f  pop     rbp
0x18001c150  retn
```
