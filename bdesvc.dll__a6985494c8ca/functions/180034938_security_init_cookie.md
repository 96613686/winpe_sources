# __security_init_cookie

- ea: `0x180034938`
- end: `0x1800349ed`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180034020`

## callees

- `0x180034938`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003497b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003497b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034987`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180034987`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003496d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003496d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180034997`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180034997`

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
0x180034938  mov     [rsp-8+arg_10], rbx
0x18003493d  push    rbp
0x18003493e  mov     rbp, rsp
0x180034941  sub     rsp, 30h
0x180034945  mov     rax, cs:__security_cookie
0x18003494c  mov     rbx, 2B992DDFA232h
0x180034956  cmp     rax, rbx
0x180034959  jnz     short loc_1800349D8
0x18003495b  xor     eax, eax
0x18003495d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180034961  mov     [rbp+var_10], rax
0x180034965  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180034969  mov     qword ptr [rbp+PerformanceCount], rax
0x18003496d  call    cs:__imp_GetSystemTimeAsFileTime
0x180034973  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180034977  mov     [rbp+var_10], rax
0x18003497b  call    cs:__imp_GetCurrentThreadId
0x180034981  mov     eax, eax
0x180034983  xor     [rbp+var_10], rax
0x180034987  call    cs:__imp_GetCurrentProcessId
0x18003498d  mov     eax, eax
0x18003498f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180034993  xor     [rbp+var_10], rax
0x180034997  call    cs:__imp_QueryPerformanceCounter
0x18003499d  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800349a0  lea     rcx, [rbp+var_10]
0x1800349a4  shl     rax, 20h
0x1800349a8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800349ac  xor     rax, [rbp+var_10]
0x1800349b0  xor     rax, rcx
0x1800349b3  mov     rcx, 0FFFFFFFFFFFFh
0x1800349bd  and     rax, rcx
0x1800349c0  mov     rcx, 2B992DDFA233h
0x1800349ca  cmp     rax, rbx
0x1800349cd  cmovz   rax, rcx
0x1800349d1  mov     cs:__security_cookie, rax
0x1800349d8  mov     rbx, [rsp+30h+arg_10]
0x1800349dd  not     rax
0x1800349e0  mov     cs:__security_cookie_complement, rax
0x1800349e7  add     rsp, 30h
0x1800349eb  pop     rbp
0x1800349ec  retn
```
