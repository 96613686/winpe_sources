# __security_init_cookie

- ea: `0x180001aac`
- end: `0x180001b61`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001650`

## callees

- `0x180001aac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001aef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001aef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001afb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001afb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ae1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ae1`

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
0x180001aac  mov     [rsp-8+arg_10], rbx
0x180001ab1  push    rbp
0x180001ab2  mov     rbp, rsp
0x180001ab5  sub     rsp, 30h
0x180001ab9  mov     rax, cs:__security_cookie
0x180001ac0  mov     rbx, 2B992DDFA232h
0x180001aca  cmp     rax, rbx
0x180001acd  jnz     short loc_180001B4C
0x180001acf  xor     eax, eax
0x180001ad1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001ad5  mov     [rbp+var_10], rax
0x180001ad9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001add  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ae1  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ae7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001aeb  mov     [rbp+var_10], rax
0x180001aef  call    cs:__imp_GetCurrentThreadId
0x180001af5  mov     eax, eax
0x180001af7  xor     [rbp+var_10], rax
0x180001afb  call    cs:__imp_GetCurrentProcessId
0x180001b01  mov     eax, eax
0x180001b03  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001b07  xor     [rbp+var_10], rax
0x180001b0b  call    cs:__imp_QueryPerformanceCounter
0x180001b11  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001b14  lea     rcx, [rbp+var_10]
0x180001b18  shl     rax, 20h
0x180001b1c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b20  xor     rax, [rbp+var_10]
0x180001b24  xor     rax, rcx
0x180001b27  mov     rcx, 0FFFFFFFFFFFFh
0x180001b31  and     rax, rcx
0x180001b34  mov     rcx, 2B992DDFA233h
0x180001b3e  cmp     rax, rbx
0x180001b41  cmovz   rax, rcx
0x180001b45  mov     cs:__security_cookie, rax
0x180001b4c  mov     rbx, [rsp+30h+arg_10]
0x180001b51  not     rax
0x180001b54  mov     cs:__security_cookie_complement, rax
0x180001b5b  add     rsp, 30h
0x180001b5f  pop     rbp
0x180001b60  retn
```
