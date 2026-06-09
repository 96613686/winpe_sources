# __security_init_cookie

- ea: `0x18004d344`
- end: `0x18004d3f9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180041b94`
- `0x18004d2d0`

## callees

- `0x18004d344`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d387`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d387`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d393`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004d3a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004d3a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004d379`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004d379`

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
0x18004d344  mov     [rsp-8+arg_10], rbx
0x18004d349  push    rbp
0x18004d34a  mov     rbp, rsp
0x18004d34d  sub     rsp, 30h
0x18004d351  mov     rax, cs:__security_cookie
0x18004d358  mov     rbx, 2B992DDFA232h
0x18004d362  cmp     rax, rbx
0x18004d365  jnz     short loc_18004D3E4
0x18004d367  xor     eax, eax
0x18004d369  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004d36d  mov     [rbp+var_10], rax
0x18004d371  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004d375  mov     qword ptr [rbp+PerformanceCount], rax
0x18004d379  call    cs:__imp_GetSystemTimeAsFileTime
0x18004d37f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004d383  mov     [rbp+var_10], rax
0x18004d387  call    cs:__imp_GetCurrentThreadId
0x18004d38d  mov     eax, eax
0x18004d38f  xor     [rbp+var_10], rax
0x18004d393  call    cs:__imp_GetCurrentProcessId
0x18004d399  mov     eax, eax
0x18004d39b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004d39f  xor     [rbp+var_10], rax
0x18004d3a3  call    cs:__imp_QueryPerformanceCounter
0x18004d3a9  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004d3ac  lea     rcx, [rbp+var_10]
0x18004d3b0  shl     rax, 20h
0x18004d3b4  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004d3b8  xor     rax, [rbp+var_10]
0x18004d3bc  xor     rax, rcx
0x18004d3bf  mov     rcx, 0FFFFFFFFFFFFh
0x18004d3c9  and     rax, rcx
0x18004d3cc  mov     rcx, 2B992DDFA233h
0x18004d3d6  cmp     rax, rbx
0x18004d3d9  cmovz   rax, rcx
0x18004d3dd  mov     cs:__security_cookie, rax
0x18004d3e4  mov     rbx, [rsp+30h+arg_10]
0x18004d3e9  not     rax
0x18004d3ec  mov     cs:__security_cookie_complement, rax
0x18004d3f3  add     rsp, 30h
0x18004d3f7  pop     rbp
0x18004d3f8  retn
```
