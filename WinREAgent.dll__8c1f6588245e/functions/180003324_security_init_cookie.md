# __security_init_cookie

- ea: `0x180003324`
- end: `0x180003401`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002df0`

## callees

- `0x180003324`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800033ae`
- `KERNEL32!QueryPerformanceCounter` at `0x1800033ae`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000335d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000335d`
- `KERNEL32!GetTickCount` at `0x180003383`
- `KERNEL32!GetTickCount` at `0x180003393`
- `KERNEL32!GetTickCount` at `0x180003383`
- `KERNEL32!GetTickCount` at `0x180003393`
- `KERNEL32!GetCurrentProcessId` at `0x18000336b`
- `KERNEL32!GetCurrentProcessId` at `0x18000336b`
- `KERNEL32!GetCurrentThreadId` at `0x180003377`
- `KERNEL32!GetCurrentThreadId` at `0x180003377`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180003324  mov     [rsp-8+arg_18], rbx
0x180003329  push    rbp
0x18000332a  mov     rbp, rsp
0x18000332d  sub     rsp, 20h
0x180003331  xor     eax, eax
0x180003333  mov     rbx, 2B992DDFA232h
0x18000333d  mov     [rbp+arg_0], rax
0x180003341  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003345  mov     qword ptr [rbp+PerformanceCount], rax
0x180003349  mov     rax, cs:__security_cookie
0x180003350  cmp     rax, rbx
0x180003353  jnz     loc_1800033EC
0x180003359  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000335d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003363  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003367  mov     [rbp+arg_0], rax
0x18000336b  call    cs:__imp_GetCurrentProcessId
0x180003371  mov     eax, eax
0x180003373  xor     [rbp+arg_0], rax
0x180003377  call    cs:__imp_GetCurrentThreadId
0x18000337d  mov     eax, eax
0x18000337f  xor     [rbp+arg_0], rax
0x180003383  call    cs:__imp_GetTickCount
0x180003389  mov     eax, eax
0x18000338b  shl     rax, 18h
0x18000338f  xor     [rbp+arg_0], rax
0x180003393  call    cs:__imp_GetTickCount
0x180003399  mov     eax, eax
0x18000339b  lea     rcx, [rbp+arg_0]
0x18000339f  xor     rax, [rbp+arg_0]
0x1800033a3  xor     rax, rcx
0x1800033a6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800033aa  mov     [rbp+arg_0], rax
0x1800033ae  call    cs:__imp_QueryPerformanceCounter
0x1800033b4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800033b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800033c1  shl     rax, 20h
0x1800033c5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800033c9  xor     rax, [rbp+arg_0]
0x1800033cd  and     rax, rcx
0x1800033d0  mov     rcx, rax
0x1800033d3  cmp     rax, rbx
0x1800033d6  jnz     short loc_1800033E5
0x1800033d8  mov     rax, 2B992DDFA233h
0x1800033e2  mov     rcx, rax
0x1800033e5  mov     cs:__security_cookie, rcx
0x1800033ec  mov     rbx, [rsp+20h+arg_18]
0x1800033f1  not     rax
0x1800033f4  mov     cs:__security_cookie_complement, rax
0x1800033fb  add     rsp, 20h
0x1800033ff  pop     rbp
0x180003400  retn
```
