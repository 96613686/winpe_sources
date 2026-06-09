# __security_init_cookie

- ea: `0x180016270`
- end: `0x180016325`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015aa0`

## callees

- `0x180016270`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800162bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800162bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800162b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800162b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800162cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800162cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800162a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800162a5`

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
0x180016270  mov     [rsp-8+arg_10], rbx
0x180016275  push    rbp
0x180016276  mov     rbp, rsp
0x180016279  sub     rsp, 30h
0x18001627d  mov     rax, cs:__security_cookie
0x180016284  mov     rbx, 2B992DDFA232h
0x18001628e  cmp     rax, rbx
0x180016291  jnz     short loc_180016310
0x180016293  xor     eax, eax
0x180016295  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180016299  mov     [rbp+var_10], rax
0x18001629d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800162a1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800162a5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800162ab  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800162af  mov     [rbp+var_10], rax
0x1800162b3  call    cs:__imp_GetCurrentThreadId
0x1800162b9  mov     eax, eax
0x1800162bb  xor     [rbp+var_10], rax
0x1800162bf  call    cs:__imp_GetCurrentProcessId
0x1800162c5  mov     eax, eax
0x1800162c7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800162cb  xor     [rbp+var_10], rax
0x1800162cf  call    cs:__imp_QueryPerformanceCounter
0x1800162d5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800162d8  lea     rcx, [rbp+var_10]
0x1800162dc  shl     rax, 20h
0x1800162e0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800162e4  xor     rax, [rbp+var_10]
0x1800162e8  xor     rax, rcx
0x1800162eb  mov     rcx, 0FFFFFFFFFFFFh
0x1800162f5  and     rax, rcx
0x1800162f8  mov     rcx, 2B992DDFA233h
0x180016302  cmp     rax, rbx
0x180016305  cmovz   rax, rcx
0x180016309  mov     cs:__security_cookie, rax
0x180016310  mov     rbx, [rsp+30h+arg_10]
0x180016315  not     rax
0x180016318  mov     cs:__security_cookie_complement, rax
0x18001631f  add     rsp, 30h
0x180016323  pop     rbp
0x180016324  retn
```
