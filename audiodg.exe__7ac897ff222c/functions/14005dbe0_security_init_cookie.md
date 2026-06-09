# __security_init_cookie

- ea: `0x14005dbe0`
- end: `0x14005dc95`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005d0b0`

## callees

- `0x14005dbe0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005dc23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14005dc23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005dc2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14005dc2f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14005dc3f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14005dc3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14005dc15`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14005dc15`

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
0x14005dbe0  mov     [rsp-8+arg_10], rbx
0x14005dbe5  push    rbp
0x14005dbe6  mov     rbp, rsp
0x14005dbe9  sub     rsp, 30h
0x14005dbed  mov     rax, cs:__security_cookie
0x14005dbf4  mov     rbx, 2B992DDFA232h
0x14005dbfe  cmp     rax, rbx
0x14005dc01  jnz     short loc_14005DC80
0x14005dc03  xor     eax, eax
0x14005dc05  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14005dc09  mov     [rbp+var_10], rax
0x14005dc0d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14005dc11  mov     qword ptr [rbp+PerformanceCount], rax
0x14005dc15  call    cs:__imp_GetSystemTimeAsFileTime
0x14005dc1b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14005dc1f  mov     [rbp+var_10], rax
0x14005dc23  call    cs:__imp_GetCurrentThreadId
0x14005dc29  mov     eax, eax
0x14005dc2b  xor     [rbp+var_10], rax
0x14005dc2f  call    cs:__imp_GetCurrentProcessId
0x14005dc35  mov     eax, eax
0x14005dc37  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14005dc3b  xor     [rbp+var_10], rax
0x14005dc3f  call    cs:__imp_QueryPerformanceCounter
0x14005dc45  mov     eax, dword ptr [rbp+PerformanceCount]
0x14005dc48  lea     rcx, [rbp+var_10]
0x14005dc4c  shl     rax, 20h
0x14005dc50  xor     rax, qword ptr [rbp+PerformanceCount]
0x14005dc54  xor     rax, [rbp+var_10]
0x14005dc58  xor     rax, rcx
0x14005dc5b  mov     rcx, 0FFFFFFFFFFFFh
0x14005dc65  and     rax, rcx
0x14005dc68  mov     rcx, 2B992DDFA233h
0x14005dc72  cmp     rax, rbx
0x14005dc75  cmovz   rax, rcx
0x14005dc79  mov     cs:__security_cookie, rax
0x14005dc80  mov     rbx, [rsp+30h+arg_10]
0x14005dc85  not     rax
0x14005dc88  mov     cs:__security_cookie_complement, rax
0x14005dc8f  add     rsp, 30h
0x14005dc93  pop     rbp
0x14005dc94  retn
```
