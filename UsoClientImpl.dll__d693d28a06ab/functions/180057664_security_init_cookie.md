# __security_init_cookie

- ea: `0x180057664`
- end: `0x18005771b`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057030`

## callees

- `0x180057664`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800576a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800576a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800576b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800576b5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800576c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800576c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005769b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005769b`

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
0x180057664  mov     [rsp-8+arg_10], rbx
0x180057669  push    rbp
0x18005766a  mov     rbp, rsp
0x18005766d  sub     rsp, 30h
0x180057671  mov     rax, cs:__security_cookie
0x180057678  mov     rbx, 2B992DDFA232h
0x180057682  cmp     rax, rbx
0x180057685  jnz     short loc_180057706
0x180057687  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005768b  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180057693  mov     qword ptr [rbp+PerformanceCount], 0
0x18005769b  call    cs:__imp_GetSystemTimeAsFileTime
0x1800576a1  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800576a5  mov     [rbp+var_10], rax
0x1800576a9  call    cs:__imp_GetCurrentThreadId
0x1800576af  mov     eax, eax
0x1800576b1  xor     [rbp+var_10], rax
0x1800576b5  call    cs:__imp_GetCurrentProcessId
0x1800576bb  mov     eax, eax
0x1800576bd  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800576c1  xor     [rbp+var_10], rax
0x1800576c5  call    cs:__imp_QueryPerformanceCounter
0x1800576cb  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800576ce  lea     rcx, [rbp+var_10]
0x1800576d2  shl     rax, 20h
0x1800576d6  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800576da  xor     rax, [rbp+var_10]
0x1800576de  xor     rax, rcx
0x1800576e1  mov     rcx, 0FFFFFFFFFFFFh
0x1800576eb  and     rax, rcx
0x1800576ee  mov     rcx, 2B992DDFA233h
0x1800576f8  cmp     rax, rbx
0x1800576fb  cmovz   rax, rcx
0x1800576ff  mov     cs:__security_cookie, rax
0x180057706  mov     rbx, [rsp+30h+arg_10]
0x18005770b  not     rax
0x18005770e  mov     cs:__security_cookie_complement, rax
0x180057715  add     rsp, 30h
0x180057719  pop     rbp
0x18005771a  retn
```
