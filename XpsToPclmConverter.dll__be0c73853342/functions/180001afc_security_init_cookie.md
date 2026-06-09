# __security_init_cookie

- ea: `0x180001afc`
- end: `0x180001bb1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015a0`

## callees

- `0x180001afc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001b3f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b5b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001b5b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b31`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b31`

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
0x180001afc  mov     [rsp-8+arg_10], rbx
0x180001b01  push    rbp
0x180001b02  mov     rbp, rsp
0x180001b05  sub     rsp, 30h
0x180001b09  mov     rax, cs:__security_cookie
0x180001b10  mov     rbx, 2B992DDFA232h
0x180001b1a  cmp     rax, rbx
0x180001b1d  jnz     short loc_180001B9C
0x180001b1f  xor     eax, eax
0x180001b21  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001b25  mov     [rbp+var_10], rax
0x180001b29  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001b2d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001b31  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b37  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001b3b  mov     [rbp+var_10], rax
0x180001b3f  call    cs:__imp_GetCurrentThreadId
0x180001b45  mov     eax, eax
0x180001b47  xor     [rbp+var_10], rax
0x180001b4b  call    cs:__imp_GetCurrentProcessId
0x180001b51  mov     eax, eax
0x180001b53  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001b57  xor     [rbp+var_10], rax
0x180001b5b  call    cs:__imp_QueryPerformanceCounter
0x180001b61  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001b64  lea     rcx, [rbp+var_10]
0x180001b68  shl     rax, 20h
0x180001b6c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b70  xor     rax, [rbp+var_10]
0x180001b74  xor     rax, rcx
0x180001b77  mov     rcx, 0FFFFFFFFFFFFh
0x180001b81  and     rax, rcx
0x180001b84  mov     rcx, 2B992DDFA233h
0x180001b8e  cmp     rax, rbx
0x180001b91  cmovz   rax, rcx
0x180001b95  mov     cs:__security_cookie, rax
0x180001b9c  mov     rbx, [rsp+30h+arg_10]
0x180001ba1  not     rax
0x180001ba4  mov     cs:__security_cookie_complement, rax
0x180001bab  add     rsp, 30h
0x180001baf  pop     rbp
0x180001bb0  retn
```
