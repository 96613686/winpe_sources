# __security_init_cookie

- ea: `0x1800f86d8`
- end: `0x1800f878d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f8694`

## callees

- `0x1800f86d8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f871b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f871b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f8727`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f8727`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f870d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f870d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f8737`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f8737`

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
0x1800f86d8  mov     [rsp-8+arg_10], rbx
0x1800f86dd  push    rbp
0x1800f86de  mov     rbp, rsp
0x1800f86e1  sub     rsp, 30h
0x1800f86e5  mov     rax, cs:__security_cookie
0x1800f86ec  mov     rbx, 2B992DDFA232h
0x1800f86f6  cmp     rax, rbx
0x1800f86f9  jnz     short loc_1800F8778
0x1800f86fb  xor     eax, eax
0x1800f86fd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800f8701  mov     [rbp+var_10], rax
0x1800f8705  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800f8709  mov     qword ptr [rbp+PerformanceCount], rax
0x1800f870d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800f8713  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800f8717  mov     [rbp+var_10], rax
0x1800f871b  call    cs:__imp_GetCurrentThreadId
0x1800f8721  mov     eax, eax
0x1800f8723  xor     [rbp+var_10], rax
0x1800f8727  call    cs:__imp_GetCurrentProcessId
0x1800f872d  mov     eax, eax
0x1800f872f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800f8733  xor     [rbp+var_10], rax
0x1800f8737  call    cs:__imp_QueryPerformanceCounter
0x1800f873d  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800f8740  lea     rcx, [rbp+var_10]
0x1800f8744  shl     rax, 20h
0x1800f8748  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800f874c  xor     rax, [rbp+var_10]
0x1800f8750  xor     rax, rcx
0x1800f8753  mov     rcx, 0FFFFFFFFFFFFh
0x1800f875d  and     rax, rcx
0x1800f8760  mov     rcx, 2B992DDFA233h
0x1800f876a  cmp     rax, rbx
0x1800f876d  cmovz   rax, rcx
0x1800f8771  mov     cs:__security_cookie, rax
0x1800f8778  mov     rbx, [rsp+30h+arg_10]
0x1800f877d  not     rax
0x1800f8780  mov     cs:__security_cookie_complement, rax
0x1800f8787  add     rsp, 30h
0x1800f878b  pop     rbp
0x1800f878c  retn
```
