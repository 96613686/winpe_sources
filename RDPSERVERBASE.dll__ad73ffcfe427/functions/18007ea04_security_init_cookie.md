# __security_init_cookie

- ea: `0x18007ea04`
- end: `0x18007eab9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007e990`

## callees

- `0x18007ea04`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007ea63`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007ea63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007ea53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007ea53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007ea47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007ea47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007ea39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007ea39`

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
0x18007ea04  mov     [rsp-8+arg_10], rbx
0x18007ea09  push    rbp
0x18007ea0a  mov     rbp, rsp
0x18007ea0d  sub     rsp, 30h
0x18007ea11  mov     rax, cs:__security_cookie
0x18007ea18  mov     rbx, 2B992DDFA232h
0x18007ea22  cmp     rax, rbx
0x18007ea25  jnz     short loc_18007EAA4
0x18007ea27  xor     eax, eax
0x18007ea29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007ea2d  mov     [rbp+var_10], rax
0x18007ea31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18007ea35  mov     qword ptr [rbp+PerformanceCount], rax
0x18007ea39  call    cs:__imp_GetSystemTimeAsFileTime
0x18007ea3f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18007ea43  mov     [rbp+var_10], rax
0x18007ea47  call    cs:__imp_GetCurrentThreadId
0x18007ea4d  mov     eax, eax
0x18007ea4f  xor     [rbp+var_10], rax
0x18007ea53  call    cs:__imp_GetCurrentProcessId
0x18007ea59  mov     eax, eax
0x18007ea5b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18007ea5f  xor     [rbp+var_10], rax
0x18007ea63  call    cs:__imp_QueryPerformanceCounter
0x18007ea69  mov     eax, dword ptr [rbp+PerformanceCount]
0x18007ea6c  lea     rcx, [rbp+var_10]
0x18007ea70  shl     rax, 20h
0x18007ea74  xor     rax, qword ptr [rbp+PerformanceCount]
0x18007ea78  xor     rax, [rbp+var_10]
0x18007ea7c  xor     rax, rcx
0x18007ea7f  mov     rcx, 0FFFFFFFFFFFFh
0x18007ea89  and     rax, rcx
0x18007ea8c  mov     rcx, 2B992DDFA233h
0x18007ea96  cmp     rax, rbx
0x18007ea99  cmovz   rax, rcx
0x18007ea9d  mov     cs:__security_cookie, rax
0x18007eaa4  mov     rbx, [rsp+30h+arg_10]
0x18007eaa9  not     rax
0x18007eaac  mov     cs:__security_cookie_complement, rax
0x18007eab3  add     rsp, 30h
0x18007eab7  pop     rbp
0x18007eab8  retn
```
