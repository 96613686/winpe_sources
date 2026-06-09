# __security_init_cookie

- ea: `0x18001a6a4`
- end: `0x18001a759`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001a230`

## callees

- `0x18001a6a4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001a703`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001a703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a6f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001a6f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a6e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a6e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a6d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001a6d9`

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
0x18001a6a4  mov     [rsp-8+arg_10], rbx
0x18001a6a9  push    rbp
0x18001a6aa  mov     rbp, rsp
0x18001a6ad  sub     rsp, 30h
0x18001a6b1  mov     rax, cs:__security_cookie
0x18001a6b8  mov     rbx, 2B992DDFA232h
0x18001a6c2  cmp     rax, rbx
0x18001a6c5  jnz     short loc_18001A744
0x18001a6c7  xor     eax, eax
0x18001a6c9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001a6cd  mov     [rbp+var_10], rax
0x18001a6d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001a6d5  mov     qword ptr [rbp+PerformanceCount], rax
0x18001a6d9  call    cs:__imp_GetSystemTimeAsFileTime
0x18001a6df  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001a6e3  mov     [rbp+var_10], rax
0x18001a6e7  call    cs:__imp_GetCurrentThreadId
0x18001a6ed  mov     eax, eax
0x18001a6ef  xor     [rbp+var_10], rax
0x18001a6f3  call    cs:__imp_GetCurrentProcessId
0x18001a6f9  mov     eax, eax
0x18001a6fb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001a6ff  xor     [rbp+var_10], rax
0x18001a703  call    cs:__imp_QueryPerformanceCounter
0x18001a709  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001a70c  lea     rcx, [rbp+var_10]
0x18001a710  shl     rax, 20h
0x18001a714  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001a718  xor     rax, [rbp+var_10]
0x18001a71c  xor     rax, rcx
0x18001a71f  mov     rcx, 0FFFFFFFFFFFFh
0x18001a729  and     rax, rcx
0x18001a72c  mov     rcx, 2B992DDFA233h
0x18001a736  cmp     rax, rbx
0x18001a739  cmovz   rax, rcx
0x18001a73d  mov     cs:__security_cookie, rax
0x18001a744  mov     rbx, [rsp+30h+arg_10]
0x18001a749  not     rax
0x18001a74c  mov     cs:__security_cookie_complement, rax
0x18001a753  add     rsp, 30h
0x18001a757  pop     rbp
0x18001a758  retn
```
