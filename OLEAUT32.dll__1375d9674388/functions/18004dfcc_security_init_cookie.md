# __security_init_cookie

- ea: `0x18004dfcc`
- end: `0x18004e081`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004d8b0`

## callees

- `0x18004dfcc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e00f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e00f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e01b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e01b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004e001`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004e001`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004e02b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004e02b`

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
0x18004dfcc  mov     [rsp-8+arg_10], rbx
0x18004dfd1  push    rbp
0x18004dfd2  mov     rbp, rsp
0x18004dfd5  sub     rsp, 30h
0x18004dfd9  mov     rax, cs:__security_cookie
0x18004dfe0  mov     rbx, 2B992DDFA232h
0x18004dfea  cmp     rax, rbx
0x18004dfed  jnz     short loc_18004E06C
0x18004dfef  xor     eax, eax
0x18004dff1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004dff5  mov     [rbp+var_10], rax
0x18004dff9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004dffd  mov     qword ptr [rbp+PerformanceCount], rax
0x18004e001  call    cs:__imp_GetSystemTimeAsFileTime
0x18004e007  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004e00b  mov     [rbp+var_10], rax
0x18004e00f  call    cs:__imp_GetCurrentThreadId
0x18004e015  mov     eax, eax
0x18004e017  xor     [rbp+var_10], rax
0x18004e01b  call    cs:__imp_GetCurrentProcessId
0x18004e021  mov     eax, eax
0x18004e023  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004e027  xor     [rbp+var_10], rax
0x18004e02b  call    cs:__imp_QueryPerformanceCounter
0x18004e031  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004e034  lea     rcx, [rbp+var_10]
0x18004e038  shl     rax, 20h
0x18004e03c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004e040  xor     rax, [rbp+var_10]
0x18004e044  xor     rax, rcx
0x18004e047  mov     rcx, 0FFFFFFFFFFFFh
0x18004e051  and     rax, rcx
0x18004e054  mov     rcx, 2B992DDFA233h
0x18004e05e  cmp     rax, rbx
0x18004e061  cmovz   rax, rcx
0x18004e065  mov     cs:__security_cookie, rax
0x18004e06c  mov     rbx, [rsp+30h+arg_10]
0x18004e071  not     rax
0x18004e074  mov     cs:__security_cookie_complement, rax
0x18004e07b  add     rsp, 30h
0x18004e07f  pop     rbp
0x18004e080  retn
```
