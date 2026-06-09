# __security_init_cookie

- ea: `0x180001d6c`
- end: `0x180001e21`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001810`

## callees

- `0x180001d6c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001dcb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001dcb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001daf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001daf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001dbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001dbb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001da1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001da1`

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
0x180001d6c  mov     [rsp-8+arg_10], rbx
0x180001d71  push    rbp
0x180001d72  mov     rbp, rsp
0x180001d75  sub     rsp, 30h
0x180001d79  mov     rax, cs:__security_cookie
0x180001d80  mov     rbx, 2B992DDFA232h
0x180001d8a  cmp     rax, rbx
0x180001d8d  jnz     short loc_180001E0C
0x180001d8f  xor     eax, eax
0x180001d91  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d95  mov     [rbp+var_10], rax
0x180001d99  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d9d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001da1  call    cs:__imp_GetSystemTimeAsFileTime
0x180001da7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001dab  mov     [rbp+var_10], rax
0x180001daf  call    cs:__imp_GetCurrentThreadId
0x180001db5  mov     eax, eax
0x180001db7  xor     [rbp+var_10], rax
0x180001dbb  call    cs:__imp_GetCurrentProcessId
0x180001dc1  mov     eax, eax
0x180001dc3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001dc7  xor     [rbp+var_10], rax
0x180001dcb  call    cs:__imp_QueryPerformanceCounter
0x180001dd1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001dd4  lea     rcx, [rbp+var_10]
0x180001dd8  shl     rax, 20h
0x180001ddc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001de0  xor     rax, [rbp+var_10]
0x180001de4  xor     rax, rcx
0x180001de7  mov     rcx, 0FFFFFFFFFFFFh
0x180001df1  and     rax, rcx
0x180001df4  mov     rcx, 2B992DDFA233h
0x180001dfe  cmp     rax, rbx
0x180001e01  cmovz   rax, rcx
0x180001e05  mov     cs:__security_cookie, rax
0x180001e0c  mov     rbx, [rsp+30h+arg_10]
0x180001e11  not     rax
0x180001e14  mov     cs:__security_cookie_complement, rax
0x180001e1b  add     rsp, 30h
0x180001e1f  pop     rbp
0x180001e20  retn
```
