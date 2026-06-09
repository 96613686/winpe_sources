# __security_init_cookie

- ea: `0x180002930`
- end: `0x1800029df`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057000`

## callees

- `0x180002930`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000296d`
- `KERNEL32!GetCurrentThreadId` at `0x18000296d`
- `KERNEL32!GetCurrentProcessId` at `0x180002979`
- `KERNEL32!GetCurrentProcessId` at `0x180002979`
- `KERNEL32!QueryPerformanceCounter` at `0x180002989`
- `KERNEL32!QueryPerformanceCounter` at `0x180002989`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000295f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000295f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x180002930  mov     [rsp-8+arg_10], rbx
0x180002935  push    rbp
0x180002936  mov     rbp, rsp
0x180002939  sub     rsp, 30h
0x18000293d  mov     rax, cs:__security_cookie
0x180002944  mov     rbx, 2B992DDFA232h
0x18000294e  cmp     rax, rbx
0x180002951  jnz     short loc_1800029CA
0x180002953  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002957  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000295f  call    cs:__imp_GetSystemTimeAsFileTime
0x180002965  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002969  mov     [rbp+var_10], rax
0x18000296d  call    cs:__imp_GetCurrentThreadId
0x180002973  mov     eax, eax
0x180002975  xor     [rbp+var_10], rax
0x180002979  call    cs:__imp_GetCurrentProcessId
0x18000297f  mov     eax, eax
0x180002981  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002985  xor     [rbp+var_10], rax
0x180002989  call    cs:__imp_QueryPerformanceCounter
0x18000298f  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002992  lea     rcx, [rbp+var_10]
0x180002996  shl     rax, 20h
0x18000299a  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000299e  xor     rax, [rbp+var_10]
0x1800029a2  xor     rax, rcx
0x1800029a5  mov     rcx, 0FFFFFFFFFFFFh
0x1800029af  and     rax, rcx
0x1800029b2  mov     rcx, 2B992DDFA233h
0x1800029bc  cmp     rax, rbx
0x1800029bf  cmovz   rax, rcx
0x1800029c3  mov     cs:__security_cookie, rax
0x1800029ca  mov     rbx, [rsp+30h+arg_10]
0x1800029cf  not     rax
0x1800029d2  mov     cs:__security_cookie_complement, rax
0x1800029d9  add     rsp, 30h
0x1800029dd  pop     rbp
0x1800029de  retn
```
