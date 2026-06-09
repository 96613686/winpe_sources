# __security_init_cookie

- ea: `0x1400025b0`
- end: `0x140002665`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400022e0`

## callees

- `0x1400025b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400025ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400025ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400025f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400025f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400025e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400025e5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000260f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000260f`

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
0x1400025b0  mov     [rsp-8+arg_10], rbx
0x1400025b5  push    rbp
0x1400025b6  mov     rbp, rsp
0x1400025b9  sub     rsp, 30h
0x1400025bd  mov     rax, cs:__security_cookie
0x1400025c4  mov     rbx, 2B992DDFA232h
0x1400025ce  cmp     rax, rbx
0x1400025d1  jnz     short loc_140002650
0x1400025d3  xor     eax, eax
0x1400025d5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400025d9  mov     [rbp+var_10], rax
0x1400025dd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400025e1  mov     qword ptr [rbp+PerformanceCount], rax
0x1400025e5  call    cs:__imp_GetSystemTimeAsFileTime
0x1400025eb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400025ef  mov     [rbp+var_10], rax
0x1400025f3  call    cs:__imp_GetCurrentThreadId
0x1400025f9  mov     eax, eax
0x1400025fb  xor     [rbp+var_10], rax
0x1400025ff  call    cs:__imp_GetCurrentProcessId
0x140002605  mov     eax, eax
0x140002607  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000260b  xor     [rbp+var_10], rax
0x14000260f  call    cs:__imp_QueryPerformanceCounter
0x140002615  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002618  lea     rcx, [rbp+var_10]
0x14000261c  shl     rax, 20h
0x140002620  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002624  xor     rax, [rbp+var_10]
0x140002628  xor     rax, rcx
0x14000262b  mov     rcx, 0FFFFFFFFFFFFh
0x140002635  and     rax, rcx
0x140002638  mov     rcx, 2B992DDFA233h
0x140002642  cmp     rax, rbx
0x140002645  cmovz   rax, rcx
0x140002649  mov     cs:__security_cookie, rax
0x140002650  mov     rbx, [rsp+30h+arg_10]
0x140002655  not     rax
0x140002658  mov     cs:__security_cookie_complement, rax
0x14000265f  add     rsp, 30h
0x140002663  pop     rbp
0x140002664  retn
```
