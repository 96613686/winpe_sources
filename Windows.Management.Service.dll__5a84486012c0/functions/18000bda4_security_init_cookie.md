# __security_init_cookie

- ea: `0x18000bda4`
- end: `0x18000be59`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b7d0`

## callees

- `0x18000bda4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bde7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bde7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bdf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bdf3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000be03`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000be03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bdd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bdd9`

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
0x18000bda4  mov     [rsp-8+arg_10], rbx
0x18000bda9  push    rbp
0x18000bdaa  mov     rbp, rsp
0x18000bdad  sub     rsp, 30h
0x18000bdb1  mov     rax, cs:__security_cookie
0x18000bdb8  mov     rbx, 2B992DDFA232h
0x18000bdc2  cmp     rax, rbx
0x18000bdc5  jnz     short loc_18000BE44
0x18000bdc7  xor     eax, eax
0x18000bdc9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000bdcd  mov     [rbp+var_10], rax
0x18000bdd1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000bdd5  mov     qword ptr [rbp+PerformanceCount], rax
0x18000bdd9  call    cs:__imp_GetSystemTimeAsFileTime
0x18000bddf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000bde3  mov     [rbp+var_10], rax
0x18000bde7  call    cs:__imp_GetCurrentThreadId
0x18000bded  mov     eax, eax
0x18000bdef  xor     [rbp+var_10], rax
0x18000bdf3  call    cs:__imp_GetCurrentProcessId
0x18000bdf9  mov     eax, eax
0x18000bdfb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000bdff  xor     [rbp+var_10], rax
0x18000be03  call    cs:__imp_QueryPerformanceCounter
0x18000be09  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000be0c  lea     rcx, [rbp+var_10]
0x18000be10  shl     rax, 20h
0x18000be14  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000be18  xor     rax, [rbp+var_10]
0x18000be1c  xor     rax, rcx
0x18000be1f  mov     rcx, 0FFFFFFFFFFFFh
0x18000be29  and     rax, rcx
0x18000be2c  mov     rcx, 2B992DDFA233h
0x18000be36  cmp     rax, rbx
0x18000be39  cmovz   rax, rcx
0x18000be3d  mov     cs:__security_cookie, rax
0x18000be44  mov     rbx, [rsp+30h+arg_10]
0x18000be49  not     rax
0x18000be4c  mov     cs:__security_cookie_complement, rax
0x18000be53  add     rsp, 30h
0x18000be57  pop     rbp
0x18000be58  retn
```
