# __security_init_cookie

- ea: `0x14000304c`
- end: `0x140003101`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002d00`

## callees

- `0x14000304c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000309b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000309b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000308f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000308f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400030ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400030ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003081`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003081`

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
0x14000304c  mov     [rsp-8+arg_10], rbx
0x140003051  push    rbp
0x140003052  mov     rbp, rsp
0x140003055  sub     rsp, 30h
0x140003059  mov     rax, cs:__security_cookie
0x140003060  mov     rbx, 2B992DDFA232h
0x14000306a  cmp     rax, rbx
0x14000306d  jnz     short loc_1400030EC
0x14000306f  xor     eax, eax
0x140003071  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003075  mov     [rbp+var_10], rax
0x140003079  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000307d  mov     qword ptr [rbp+PerformanceCount], rax
0x140003081  call    cs:__imp_GetSystemTimeAsFileTime
0x140003087  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000308b  mov     [rbp+var_10], rax
0x14000308f  call    cs:__imp_GetCurrentThreadId
0x140003095  mov     eax, eax
0x140003097  xor     [rbp+var_10], rax
0x14000309b  call    cs:__imp_GetCurrentProcessId
0x1400030a1  mov     eax, eax
0x1400030a3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400030a7  xor     [rbp+var_10], rax
0x1400030ab  call    cs:__imp_QueryPerformanceCounter
0x1400030b1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400030b4  lea     rcx, [rbp+var_10]
0x1400030b8  shl     rax, 20h
0x1400030bc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400030c0  xor     rax, [rbp+var_10]
0x1400030c4  xor     rax, rcx
0x1400030c7  mov     rcx, 0FFFFFFFFFFFFh
0x1400030d1  and     rax, rcx
0x1400030d4  mov     rcx, 2B992DDFA233h
0x1400030de  cmp     rax, rbx
0x1400030e1  cmovz   rax, rcx
0x1400030e5  mov     cs:__security_cookie, rax
0x1400030ec  mov     rbx, [rsp+30h+arg_10]
0x1400030f1  not     rax
0x1400030f4  mov     cs:__security_cookie_complement, rax
0x1400030fb  add     rsp, 30h
0x1400030ff  pop     rbp
0x140003100  retn
```
