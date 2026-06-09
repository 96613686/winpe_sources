# __security_init_cookie

- ea: `0x1800045ac`
- end: `0x180004661`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003c50`

## callees

- `0x1800045ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800045fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800045fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000460b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000460b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800045e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800045e1`

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
0x1800045ac  mov     [rsp-8+arg_10], rbx
0x1800045b1  push    rbp
0x1800045b2  mov     rbp, rsp
0x1800045b5  sub     rsp, 30h
0x1800045b9  mov     rax, cs:__security_cookie
0x1800045c0  mov     rbx, 2B992DDFA232h
0x1800045ca  cmp     rax, rbx
0x1800045cd  jnz     short loc_18000464C
0x1800045cf  xor     eax, eax
0x1800045d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800045d5  mov     [rbp+var_10], rax
0x1800045d9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800045dd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800045e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800045e7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800045eb  mov     [rbp+var_10], rax
0x1800045ef  call    cs:__imp_GetCurrentThreadId
0x1800045f5  mov     eax, eax
0x1800045f7  xor     [rbp+var_10], rax
0x1800045fb  call    cs:__imp_GetCurrentProcessId
0x180004601  mov     eax, eax
0x180004603  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004607  xor     [rbp+var_10], rax
0x18000460b  call    cs:__imp_QueryPerformanceCounter
0x180004611  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004614  lea     rcx, [rbp+var_10]
0x180004618  shl     rax, 20h
0x18000461c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004620  xor     rax, [rbp+var_10]
0x180004624  xor     rax, rcx
0x180004627  mov     rcx, 0FFFFFFFFFFFFh
0x180004631  and     rax, rcx
0x180004634  mov     rcx, 2B992DDFA233h
0x18000463e  cmp     rax, rbx
0x180004641  cmovz   rax, rcx
0x180004645  mov     cs:__security_cookie, rax
0x18000464c  mov     rbx, [rsp+30h+arg_10]
0x180004651  not     rax
0x180004654  mov     cs:__security_cookie_complement, rax
0x18000465b  add     rsp, 30h
0x18000465f  pop     rbp
0x180004660  retn
```
