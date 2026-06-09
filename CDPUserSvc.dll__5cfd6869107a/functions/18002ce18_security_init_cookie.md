# __security_init_cookie

- ea: `0x18002ce18`
- end: `0x18002cecd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002c520`

## callees

- `0x18002ce18`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ce5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002ce5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002ce67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002ce67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ce4d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002ce4d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ce77`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002ce77`

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
0x18002ce18  mov     [rsp-8+arg_10], rbx
0x18002ce1d  push    rbp
0x18002ce1e  mov     rbp, rsp
0x18002ce21  sub     rsp, 30h
0x18002ce25  mov     rax, cs:__security_cookie
0x18002ce2c  mov     rbx, 2B992DDFA232h
0x18002ce36  cmp     rax, rbx
0x18002ce39  jnz     short loc_18002CEB8
0x18002ce3b  xor     eax, eax
0x18002ce3d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002ce41  mov     [rbp+var_10], rax
0x18002ce45  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002ce49  mov     qword ptr [rbp+PerformanceCount], rax
0x18002ce4d  call    cs:__imp_GetSystemTimeAsFileTime
0x18002ce53  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002ce57  mov     [rbp+var_10], rax
0x18002ce5b  call    cs:__imp_GetCurrentThreadId
0x18002ce61  mov     eax, eax
0x18002ce63  xor     [rbp+var_10], rax
0x18002ce67  call    cs:__imp_GetCurrentProcessId
0x18002ce6d  mov     eax, eax
0x18002ce6f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002ce73  xor     [rbp+var_10], rax
0x18002ce77  call    cs:__imp_QueryPerformanceCounter
0x18002ce7d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002ce80  lea     rcx, [rbp+var_10]
0x18002ce84  shl     rax, 20h
0x18002ce88  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002ce8c  xor     rax, [rbp+var_10]
0x18002ce90  xor     rax, rcx
0x18002ce93  mov     rcx, 0FFFFFFFFFFFFh
0x18002ce9d  and     rax, rcx
0x18002cea0  mov     rcx, 2B992DDFA233h
0x18002ceaa  cmp     rax, rbx
0x18002cead  cmovz   rax, rcx
0x18002ceb1  mov     cs:__security_cookie, rax
0x18002ceb8  mov     rbx, [rsp+30h+arg_10]
0x18002cebd  not     rax
0x18002cec0  mov     cs:__security_cookie_complement, rax
0x18002cec7  add     rsp, 30h
0x18002cecb  pop     rbp
0x18002cecc  retn
```
