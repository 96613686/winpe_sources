# __security_init_cookie

- ea: `0x18003e63c`
- end: `0x18003e6f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e1c0`

## callees

- `0x18003e63c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003e68b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003e68b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e67f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e67f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003e69b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003e69b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e671`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003e671`

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
0x18003e63c  mov     [rsp-8+arg_10], rbx
0x18003e641  push    rbp
0x18003e642  mov     rbp, rsp
0x18003e645  sub     rsp, 30h
0x18003e649  mov     rax, cs:__security_cookie
0x18003e650  mov     rbx, 2B992DDFA232h
0x18003e65a  cmp     rax, rbx
0x18003e65d  jnz     short loc_18003E6DC
0x18003e65f  xor     eax, eax
0x18003e661  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003e665  mov     [rbp+var_10], rax
0x18003e669  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003e66d  mov     qword ptr [rbp+PerformanceCount], rax
0x18003e671  call    cs:__imp_GetSystemTimeAsFileTime
0x18003e677  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003e67b  mov     [rbp+var_10], rax
0x18003e67f  call    cs:__imp_GetCurrentThreadId
0x18003e685  mov     eax, eax
0x18003e687  xor     [rbp+var_10], rax
0x18003e68b  call    cs:__imp_GetCurrentProcessId
0x18003e691  mov     eax, eax
0x18003e693  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003e697  xor     [rbp+var_10], rax
0x18003e69b  call    cs:__imp_QueryPerformanceCounter
0x18003e6a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003e6a4  lea     rcx, [rbp+var_10]
0x18003e6a8  shl     rax, 20h
0x18003e6ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003e6b0  xor     rax, [rbp+var_10]
0x18003e6b4  xor     rax, rcx
0x18003e6b7  mov     rcx, 0FFFFFFFFFFFFh
0x18003e6c1  and     rax, rcx
0x18003e6c4  mov     rcx, 2B992DDFA233h
0x18003e6ce  cmp     rax, rbx
0x18003e6d1  cmovz   rax, rcx
0x18003e6d5  mov     cs:__security_cookie, rax
0x18003e6dc  mov     rbx, [rsp+30h+arg_10]
0x18003e6e1  not     rax
0x18003e6e4  mov     cs:__security_cookie_complement, rax
0x18003e6eb  add     rsp, 30h
0x18003e6ef  pop     rbp
0x18003e6f0  retn
```
