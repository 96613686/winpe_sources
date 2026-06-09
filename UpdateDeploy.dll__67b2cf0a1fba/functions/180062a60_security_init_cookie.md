# __security_init_cookie

- ea: `0x180062a60`
- end: `0x180062b17`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180062100`

## callees

- `0x180062a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180062ab1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062aa5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062aa5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062a97`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180062a97`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180062ac1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180062ac1`

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
0x180062a60  mov     [rsp-8+arg_10], rbx
0x180062a65  push    rbp
0x180062a66  mov     rbp, rsp
0x180062a69  sub     rsp, 30h
0x180062a6d  mov     rax, cs:__security_cookie
0x180062a74  mov     rbx, 2B992DDFA232h
0x180062a7e  cmp     rax, rbx
0x180062a81  jnz     short loc_180062B02
0x180062a83  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180062a87  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180062a8f  mov     qword ptr [rbp+PerformanceCount], 0
0x180062a97  call    cs:__imp_GetSystemTimeAsFileTime
0x180062a9d  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180062aa1  mov     [rbp+var_10], rax
0x180062aa5  call    cs:__imp_GetCurrentThreadId
0x180062aab  mov     eax, eax
0x180062aad  xor     [rbp+var_10], rax
0x180062ab1  call    cs:__imp_GetCurrentProcessId
0x180062ab7  mov     eax, eax
0x180062ab9  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180062abd  xor     [rbp+var_10], rax
0x180062ac1  call    cs:__imp_QueryPerformanceCounter
0x180062ac7  mov     eax, dword ptr [rbp+PerformanceCount]
0x180062aca  lea     rcx, [rbp+var_10]
0x180062ace  shl     rax, 20h
0x180062ad2  xor     rax, qword ptr [rbp+PerformanceCount]
0x180062ad6  xor     rax, [rbp+var_10]
0x180062ada  xor     rax, rcx
0x180062add  mov     rcx, 0FFFFFFFFFFFFh
0x180062ae7  and     rax, rcx
0x180062aea  mov     rcx, 2B992DDFA233h
0x180062af4  cmp     rax, rbx
0x180062af7  cmovz   rax, rcx
0x180062afb  mov     cs:__security_cookie, rax
0x180062b02  mov     rbx, [rsp+30h+arg_10]
0x180062b07  not     rax
0x180062b0a  mov     cs:__security_cookie_complement, rax
0x180062b11  add     rsp, 30h
0x180062b15  pop     rbp
0x180062b16  retn
```
