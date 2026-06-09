# __security_init_cookie

- ea: `0x180009138`
- end: `0x1800091ed`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008570`

## callees

- `0x180009138`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009187`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180009187`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000917b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000917b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000916d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000916d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009197`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180009197`

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
0x180009138  mov     [rsp-8+arg_10], rbx
0x18000913d  push    rbp
0x18000913e  mov     rbp, rsp
0x180009141  sub     rsp, 30h
0x180009145  mov     rax, cs:__security_cookie
0x18000914c  mov     rbx, 2B992DDFA232h
0x180009156  cmp     rax, rbx
0x180009159  jnz     short loc_1800091D8
0x18000915b  xor     eax, eax
0x18000915d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180009161  mov     [rbp+var_10], rax
0x180009165  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180009169  mov     qword ptr [rbp+PerformanceCount], rax
0x18000916d  call    cs:__imp_GetSystemTimeAsFileTime
0x180009173  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180009177  mov     [rbp+var_10], rax
0x18000917b  call    cs:__imp_GetCurrentThreadId
0x180009181  mov     eax, eax
0x180009183  xor     [rbp+var_10], rax
0x180009187  call    cs:__imp_GetCurrentProcessId
0x18000918d  mov     eax, eax
0x18000918f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180009193  xor     [rbp+var_10], rax
0x180009197  call    cs:__imp_QueryPerformanceCounter
0x18000919d  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800091a0  lea     rcx, [rbp+var_10]
0x1800091a4  shl     rax, 20h
0x1800091a8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800091ac  xor     rax, [rbp+var_10]
0x1800091b0  xor     rax, rcx
0x1800091b3  mov     rcx, 0FFFFFFFFFFFFh
0x1800091bd  and     rax, rcx
0x1800091c0  mov     rcx, 2B992DDFA233h
0x1800091ca  cmp     rax, rbx
0x1800091cd  cmovz   rax, rcx
0x1800091d1  mov     cs:__security_cookie, rax
0x1800091d8  mov     rbx, [rsp+30h+arg_10]
0x1800091dd  not     rax
0x1800091e0  mov     cs:__security_cookie_complement, rax
0x1800091e7  add     rsp, 30h
0x1800091eb  pop     rbp
0x1800091ec  retn
```
