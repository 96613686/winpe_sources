# __security_init_cookie

- ea: `0x18000a33c`
- end: `0x18000a3f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009ee0`

## callees

- `0x18000a33c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a37f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a37f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a38b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a38b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a39b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a39b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a371`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a371`

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
0x18000a33c  mov     [rsp-8+arg_10], rbx
0x18000a341  push    rbp
0x18000a342  mov     rbp, rsp
0x18000a345  sub     rsp, 30h
0x18000a349  mov     rax, cs:__security_cookie
0x18000a350  mov     rbx, 2B992DDFA232h
0x18000a35a  cmp     rax, rbx
0x18000a35d  jnz     short loc_18000A3DC
0x18000a35f  xor     eax, eax
0x18000a361  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000a365  mov     [rbp+var_10], rax
0x18000a369  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000a36d  mov     qword ptr [rbp+PerformanceCount], rax
0x18000a371  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a377  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000a37b  mov     [rbp+var_10], rax
0x18000a37f  call    cs:__imp_GetCurrentThreadId
0x18000a385  mov     eax, eax
0x18000a387  xor     [rbp+var_10], rax
0x18000a38b  call    cs:__imp_GetCurrentProcessId
0x18000a391  mov     eax, eax
0x18000a393  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000a397  xor     [rbp+var_10], rax
0x18000a39b  call    cs:__imp_QueryPerformanceCounter
0x18000a3a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000a3a4  lea     rcx, [rbp+var_10]
0x18000a3a8  shl     rax, 20h
0x18000a3ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000a3b0  xor     rax, [rbp+var_10]
0x18000a3b4  xor     rax, rcx
0x18000a3b7  mov     rcx, 0FFFFFFFFFFFFh
0x18000a3c1  and     rax, rcx
0x18000a3c4  mov     rcx, 2B992DDFA233h
0x18000a3ce  cmp     rax, rbx
0x18000a3d1  cmovz   rax, rcx
0x18000a3d5  mov     cs:__security_cookie, rax
0x18000a3dc  mov     rbx, [rsp+30h+arg_10]
0x18000a3e1  not     rax
0x18000a3e4  mov     cs:__security_cookie_complement, rax
0x18000a3eb  add     rsp, 30h
0x18000a3ef  pop     rbp
0x18000a3f0  retn
```
