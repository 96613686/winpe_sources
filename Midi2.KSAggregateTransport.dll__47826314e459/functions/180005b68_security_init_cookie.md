# __security_init_cookie

- ea: `0x180005b68`
- end: `0x180005c1d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004fc0`

## callees

- `0x180005b68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005bab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005bb7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005bc7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005bc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005b9d`

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
0x180005b68  mov     [rsp-8+arg_10], rbx
0x180005b6d  push    rbp
0x180005b6e  mov     rbp, rsp
0x180005b71  sub     rsp, 30h
0x180005b75  mov     rax, cs:__security_cookie
0x180005b7c  mov     rbx, 2B992DDFA232h
0x180005b86  cmp     rax, rbx
0x180005b89  jnz     short loc_180005C08
0x180005b8b  xor     eax, eax
0x180005b8d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005b91  mov     [rbp+var_10], rax
0x180005b95  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005b99  mov     qword ptr [rbp+PerformanceCount], rax
0x180005b9d  call    cs:__imp_GetSystemTimeAsFileTime
0x180005ba3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005ba7  mov     [rbp+var_10], rax
0x180005bab  call    cs:__imp_GetCurrentThreadId
0x180005bb1  mov     eax, eax
0x180005bb3  xor     [rbp+var_10], rax
0x180005bb7  call    cs:__imp_GetCurrentProcessId
0x180005bbd  mov     eax, eax
0x180005bbf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005bc3  xor     [rbp+var_10], rax
0x180005bc7  call    cs:__imp_QueryPerformanceCounter
0x180005bcd  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005bd0  lea     rcx, [rbp+var_10]
0x180005bd4  shl     rax, 20h
0x180005bd8  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005bdc  xor     rax, [rbp+var_10]
0x180005be0  xor     rax, rcx
0x180005be3  mov     rcx, 0FFFFFFFFFFFFh
0x180005bed  and     rax, rcx
0x180005bf0  mov     rcx, 2B992DDFA233h
0x180005bfa  cmp     rax, rbx
0x180005bfd  cmovz   rax, rcx
0x180005c01  mov     cs:__security_cookie, rax
0x180005c08  mov     rbx, [rsp+30h+arg_10]
0x180005c0d  not     rax
0x180005c10  mov     cs:__security_cookie_complement, rax
0x180005c17  add     rsp, 30h
0x180005c1b  pop     rbp
0x180005c1c  retn
```
