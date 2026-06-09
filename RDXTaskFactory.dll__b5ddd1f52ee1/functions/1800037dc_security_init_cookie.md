# __security_init_cookie

- ea: `0x1800037dc`
- end: `0x180003891`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003340`

## callees

- `0x1800037dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000382b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000382b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000381f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000381f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000383b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000383b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003811`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003811`

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
0x1800037dc  mov     [rsp-8+arg_10], rbx
0x1800037e1  push    rbp
0x1800037e2  mov     rbp, rsp
0x1800037e5  sub     rsp, 30h
0x1800037e9  mov     rax, cs:__security_cookie
0x1800037f0  mov     rbx, 2B992DDFA232h
0x1800037fa  cmp     rax, rbx
0x1800037fd  jnz     short loc_18000387C
0x1800037ff  xor     eax, eax
0x180003801  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003805  mov     [rbp+var_10], rax
0x180003809  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000380d  mov     qword ptr [rbp+PerformanceCount], rax
0x180003811  call    cs:__imp_GetSystemTimeAsFileTime
0x180003817  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000381b  mov     [rbp+var_10], rax
0x18000381f  call    cs:__imp_GetCurrentThreadId
0x180003825  mov     eax, eax
0x180003827  xor     [rbp+var_10], rax
0x18000382b  call    cs:__imp_GetCurrentProcessId
0x180003831  mov     eax, eax
0x180003833  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003837  xor     [rbp+var_10], rax
0x18000383b  call    cs:__imp_QueryPerformanceCounter
0x180003841  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003844  lea     rcx, [rbp+var_10]
0x180003848  shl     rax, 20h
0x18000384c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003850  xor     rax, [rbp+var_10]
0x180003854  xor     rax, rcx
0x180003857  mov     rcx, 0FFFFFFFFFFFFh
0x180003861  and     rax, rcx
0x180003864  mov     rcx, 2B992DDFA233h
0x18000386e  cmp     rax, rbx
0x180003871  cmovz   rax, rcx
0x180003875  mov     cs:__security_cookie, rax
0x18000387c  mov     rbx, [rsp+30h+arg_10]
0x180003881  not     rax
0x180003884  mov     cs:__security_cookie_complement, rax
0x18000388b  add     rsp, 30h
0x18000388f  pop     rbp
0x180003890  retn
```
