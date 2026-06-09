# __security_init_cookie

- ea: `0x140001894`
- end: `0x140001949`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400015d0`

## callees

- `0x140001894`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400018e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400018e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400018d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400018d7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400018f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400018f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400018c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400018c9`

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
0x140001894  mov     [rsp-8+arg_10], rbx
0x140001899  push    rbp
0x14000189a  mov     rbp, rsp
0x14000189d  sub     rsp, 30h
0x1400018a1  mov     rax, cs:__security_cookie
0x1400018a8  mov     rbx, 2B992DDFA232h
0x1400018b2  cmp     rax, rbx
0x1400018b5  jnz     short loc_140001934
0x1400018b7  xor     eax, eax
0x1400018b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400018bd  mov     [rbp+var_10], rax
0x1400018c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400018c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400018c9  call    cs:__imp_GetSystemTimeAsFileTime
0x1400018cf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400018d3  mov     [rbp+var_10], rax
0x1400018d7  call    cs:__imp_GetCurrentThreadId
0x1400018dd  mov     eax, eax
0x1400018df  xor     [rbp+var_10], rax
0x1400018e3  call    cs:__imp_GetCurrentProcessId
0x1400018e9  mov     eax, eax
0x1400018eb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400018ef  xor     [rbp+var_10], rax
0x1400018f3  call    cs:__imp_QueryPerformanceCounter
0x1400018f9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400018fc  lea     rcx, [rbp+var_10]
0x140001900  shl     rax, 20h
0x140001904  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001908  xor     rax, [rbp+var_10]
0x14000190c  xor     rax, rcx
0x14000190f  mov     rcx, 0FFFFFFFFFFFFh
0x140001919  and     rax, rcx
0x14000191c  mov     rcx, 2B992DDFA233h
0x140001926  cmp     rax, rbx
0x140001929  cmovz   rax, rcx
0x14000192d  mov     cs:__security_cookie, rax
0x140001934  mov     rbx, [rsp+30h+arg_10]
0x140001939  not     rax
0x14000193c  mov     cs:__security_cookie_complement, rax
0x140001943  add     rsp, 30h
0x140001947  pop     rbp
0x140001948  retn
```
