# __security_init_cookie

- ea: `0x18000160c`
- end: `0x1800016c1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014d0`

## callees

- `0x18000160c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000166b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000166b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000165b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000165b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000164f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000164f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001641`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001641`

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
0x18000160c  mov     [rsp-8+arg_10], rbx
0x180001611  push    rbp
0x180001612  mov     rbp, rsp
0x180001615  sub     rsp, 30h
0x180001619  mov     rax, cs:__security_cookie
0x180001620  mov     rbx, 2B992DDFA232h
0x18000162a  cmp     rax, rbx
0x18000162d  jnz     short loc_1800016AC
0x18000162f  xor     eax, eax
0x180001631  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001635  mov     [rbp+var_10], rax
0x180001639  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000163d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001641  call    cs:__imp_GetSystemTimeAsFileTime
0x180001647  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000164b  mov     [rbp+var_10], rax
0x18000164f  call    cs:__imp_GetCurrentThreadId
0x180001655  mov     eax, eax
0x180001657  xor     [rbp+var_10], rax
0x18000165b  call    cs:__imp_GetCurrentProcessId
0x180001661  mov     eax, eax
0x180001663  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001667  xor     [rbp+var_10], rax
0x18000166b  call    cs:__imp_QueryPerformanceCounter
0x180001671  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001674  lea     rcx, [rbp+var_10]
0x180001678  shl     rax, 20h
0x18000167c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001680  xor     rax, [rbp+var_10]
0x180001684  xor     rax, rcx
0x180001687  mov     rcx, 0FFFFFFFFFFFFh
0x180001691  and     rax, rcx
0x180001694  mov     rcx, 2B992DDFA233h
0x18000169e  cmp     rax, rbx
0x1800016a1  cmovz   rax, rcx
0x1800016a5  mov     cs:__security_cookie, rax
0x1800016ac  mov     rbx, [rsp+30h+arg_10]
0x1800016b1  not     rax
0x1800016b4  mov     cs:__security_cookie_complement, rax
0x1800016bb  add     rsp, 30h
0x1800016bf  pop     rbp
0x1800016c0  retn
```
