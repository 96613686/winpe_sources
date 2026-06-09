# __security_init_cookie

- ea: `0x1800037e8`
- end: `0x18000389d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002e10`

## callees

- `0x1800037e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000382b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000382b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003847`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003847`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000381d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000381d`

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
0x1800037e8  mov     [rsp-8+arg_10], rbx
0x1800037ed  push    rbp
0x1800037ee  mov     rbp, rsp
0x1800037f1  sub     rsp, 30h
0x1800037f5  mov     rax, cs:__security_cookie
0x1800037fc  mov     rbx, 2B992DDFA232h
0x180003806  cmp     rax, rbx
0x180003809  jnz     short loc_180003888
0x18000380b  xor     eax, eax
0x18000380d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003811  mov     [rbp+var_10], rax
0x180003815  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003819  mov     qword ptr [rbp+PerformanceCount], rax
0x18000381d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003823  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003827  mov     [rbp+var_10], rax
0x18000382b  call    cs:__imp_GetCurrentThreadId
0x180003831  mov     eax, eax
0x180003833  xor     [rbp+var_10], rax
0x180003837  call    cs:__imp_GetCurrentProcessId
0x18000383d  mov     eax, eax
0x18000383f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003843  xor     [rbp+var_10], rax
0x180003847  call    cs:__imp_QueryPerformanceCounter
0x18000384d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003850  lea     rcx, [rbp+var_10]
0x180003854  shl     rax, 20h
0x180003858  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000385c  xor     rax, [rbp+var_10]
0x180003860  xor     rax, rcx
0x180003863  mov     rcx, 0FFFFFFFFFFFFh
0x18000386d  and     rax, rcx
0x180003870  mov     rcx, 2B992DDFA233h
0x18000387a  cmp     rax, rbx
0x18000387d  cmovz   rax, rcx
0x180003881  mov     cs:__security_cookie, rax
0x180003888  mov     rbx, [rsp+30h+arg_10]
0x18000388d  not     rax
0x180003890  mov     cs:__security_cookie_complement, rax
0x180003897  add     rsp, 30h
0x18000389b  pop     rbp
0x18000389c  retn
```
