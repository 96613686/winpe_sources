# __security_init_cookie

- ea: `0x180001a90`
- end: `0x180001b45`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x180001a90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ad3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ad3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001adf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001adf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ac5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001ac5`

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
0x180001a90  mov     [rsp-8+arg_10], rbx
0x180001a95  push    rbp
0x180001a96  mov     rbp, rsp
0x180001a99  sub     rsp, 30h
0x180001a9d  mov     rax, cs:__security_cookie
0x180001aa4  mov     rbx, 2B992DDFA232h
0x180001aae  cmp     rax, rbx
0x180001ab1  jnz     short loc_180001B30
0x180001ab3  xor     eax, eax
0x180001ab5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001ab9  mov     [rbp+var_10], rax
0x180001abd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ac1  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ac5  call    cs:__imp_GetSystemTimeAsFileTime
0x180001acb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001acf  mov     [rbp+var_10], rax
0x180001ad3  call    cs:__imp_GetCurrentThreadId
0x180001ad9  mov     eax, eax
0x180001adb  xor     [rbp+var_10], rax
0x180001adf  call    cs:__imp_GetCurrentProcessId
0x180001ae5  mov     eax, eax
0x180001ae7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001aeb  xor     [rbp+var_10], rax
0x180001aef  call    cs:__imp_QueryPerformanceCounter
0x180001af5  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001af8  lea     rcx, [rbp+var_10]
0x180001afc  shl     rax, 20h
0x180001b00  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b04  xor     rax, [rbp+var_10]
0x180001b08  xor     rax, rcx
0x180001b0b  mov     rcx, 0FFFFFFFFFFFFh
0x180001b15  and     rax, rcx
0x180001b18  mov     rcx, 2B992DDFA233h
0x180001b22  cmp     rax, rbx
0x180001b25  cmovz   rax, rcx
0x180001b29  mov     cs:__security_cookie, rax
0x180001b30  mov     rbx, [rsp+30h+arg_10]
0x180001b35  not     rax
0x180001b38  mov     cs:__security_cookie_complement, rax
0x180001b3f  add     rsp, 30h
0x180001b43  pop     rbp
0x180001b44  retn
```
