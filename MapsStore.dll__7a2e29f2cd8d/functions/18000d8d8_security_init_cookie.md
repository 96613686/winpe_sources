# __security_init_cookie

- ea: `0x18000d8d8`
- end: `0x18000d98d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d040`

## callees

- `0x18000d8d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d91b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d91b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d927`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d927`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d937`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d937`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d90d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d90d`

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
0x18000d8d8  mov     [rsp-8+arg_10], rbx
0x18000d8dd  push    rbp
0x18000d8de  mov     rbp, rsp
0x18000d8e1  sub     rsp, 30h
0x18000d8e5  mov     rax, cs:__security_cookie
0x18000d8ec  mov     rbx, 2B992DDFA232h
0x18000d8f6  cmp     rax, rbx
0x18000d8f9  jnz     short loc_18000D978
0x18000d8fb  xor     eax, eax
0x18000d8fd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d901  mov     [rbp+var_10], rax
0x18000d905  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000d909  mov     qword ptr [rbp+PerformanceCount], rax
0x18000d90d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d913  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d917  mov     [rbp+var_10], rax
0x18000d91b  call    cs:__imp_GetCurrentThreadId
0x18000d921  mov     eax, eax
0x18000d923  xor     [rbp+var_10], rax
0x18000d927  call    cs:__imp_GetCurrentProcessId
0x18000d92d  mov     eax, eax
0x18000d92f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000d933  xor     [rbp+var_10], rax
0x18000d937  call    cs:__imp_QueryPerformanceCounter
0x18000d93d  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000d940  lea     rcx, [rbp+var_10]
0x18000d944  shl     rax, 20h
0x18000d948  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000d94c  xor     rax, [rbp+var_10]
0x18000d950  xor     rax, rcx
0x18000d953  mov     rcx, 0FFFFFFFFFFFFh
0x18000d95d  and     rax, rcx
0x18000d960  mov     rcx, 2B992DDFA233h
0x18000d96a  cmp     rax, rbx
0x18000d96d  cmovz   rax, rcx
0x18000d971  mov     cs:__security_cookie, rax
0x18000d978  mov     rbx, [rsp+30h+arg_10]
0x18000d97d  not     rax
0x18000d980  mov     cs:__security_cookie_complement, rax
0x18000d987  add     rsp, 30h
0x18000d98b  pop     rbp
0x18000d98c  retn
```
