# __security_init_cookie

- ea: `0x1800045e4`
- end: `0x180004699`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003a00`

## callees

- `0x1800045e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004633`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004633`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004619`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004619`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004643`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004643`

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
0x1800045e4  mov     [rsp-8+arg_10], rbx
0x1800045e9  push    rbp
0x1800045ea  mov     rbp, rsp
0x1800045ed  sub     rsp, 30h
0x1800045f1  mov     rax, cs:__security_cookie
0x1800045f8  mov     rbx, 2B992DDFA232h
0x180004602  cmp     rax, rbx
0x180004605  jnz     short loc_180004684
0x180004607  xor     eax, eax
0x180004609  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000460d  mov     [rbp+var_10], rax
0x180004611  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004615  mov     qword ptr [rbp+PerformanceCount], rax
0x180004619  call    cs:__imp_GetSystemTimeAsFileTime
0x18000461f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004623  mov     [rbp+var_10], rax
0x180004627  call    cs:__imp_GetCurrentThreadId
0x18000462d  mov     eax, eax
0x18000462f  xor     [rbp+var_10], rax
0x180004633  call    cs:__imp_GetCurrentProcessId
0x180004639  mov     eax, eax
0x18000463b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000463f  xor     [rbp+var_10], rax
0x180004643  call    cs:__imp_QueryPerformanceCounter
0x180004649  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000464c  lea     rcx, [rbp+var_10]
0x180004650  shl     rax, 20h
0x180004654  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004658  xor     rax, [rbp+var_10]
0x18000465c  xor     rax, rcx
0x18000465f  mov     rcx, 0FFFFFFFFFFFFh
0x180004669  and     rax, rcx
0x18000466c  mov     rcx, 2B992DDFA233h
0x180004676  cmp     rax, rbx
0x180004679  cmovz   rax, rcx
0x18000467d  mov     cs:__security_cookie, rax
0x180004684  mov     rbx, [rsp+30h+arg_10]
0x180004689  not     rax
0x18000468c  mov     cs:__security_cookie_complement, rax
0x180004693  add     rsp, 30h
0x180004697  pop     rbp
0x180004698  retn
```
