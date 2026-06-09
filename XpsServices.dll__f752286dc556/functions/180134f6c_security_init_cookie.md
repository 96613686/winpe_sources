# __security_init_cookie

- ea: `0x180134f6c`
- end: `0x180135021`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180134b20`

## callees

- `0x180134f6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180134fbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180134fbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180134faf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180134faf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180134fcb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180134fcb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180134fa1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180134fa1`

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
0x180134f6c  mov     [rsp-8+arg_10], rbx
0x180134f71  push    rbp
0x180134f72  mov     rbp, rsp
0x180134f75  sub     rsp, 30h
0x180134f79  mov     rax, cs:__security_cookie
0x180134f80  mov     rbx, 2B992DDFA232h
0x180134f8a  cmp     rax, rbx
0x180134f8d  jnz     short loc_18013500C
0x180134f8f  xor     eax, eax
0x180134f91  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180134f95  mov     [rbp+var_10], rax
0x180134f99  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180134f9d  mov     qword ptr [rbp+PerformanceCount], rax
0x180134fa1  call    cs:__imp_GetSystemTimeAsFileTime
0x180134fa7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180134fab  mov     [rbp+var_10], rax
0x180134faf  call    cs:__imp_GetCurrentThreadId
0x180134fb5  mov     eax, eax
0x180134fb7  xor     [rbp+var_10], rax
0x180134fbb  call    cs:__imp_GetCurrentProcessId
0x180134fc1  mov     eax, eax
0x180134fc3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180134fc7  xor     [rbp+var_10], rax
0x180134fcb  call    cs:__imp_QueryPerformanceCounter
0x180134fd1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180134fd4  lea     rcx, [rbp+var_10]
0x180134fd8  shl     rax, 20h
0x180134fdc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180134fe0  xor     rax, [rbp+var_10]
0x180134fe4  xor     rax, rcx
0x180134fe7  mov     rcx, 0FFFFFFFFFFFFh
0x180134ff1  and     rax, rcx
0x180134ff4  mov     rcx, 2B992DDFA233h
0x180134ffe  cmp     rax, rbx
0x180135001  cmovz   rax, rcx
0x180135005  mov     cs:__security_cookie, rax
0x18013500c  mov     rbx, [rsp+30h+arg_10]
0x180135011  not     rax
0x180135014  mov     cs:__security_cookie_complement, rax
0x18013501b  add     rsp, 30h
0x18013501f  pop     rbp
0x180135020  retn
```
