# __security_init_cookie

- ea: `0x1800015e4`
- end: `0x1800016c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001290`

## callees

- `0x1800015e4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001643`
- `KERNEL32!GetTickCount` at `0x180001653`
- `KERNEL32!GetTickCount` at `0x180001643`
- `KERNEL32!GetTickCount` at `0x180001653`
- `KERNEL32!QueryPerformanceCounter` at `0x18000166e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000166e`
- `KERNEL32!GetCurrentProcessId` at `0x18000162b`
- `KERNEL32!GetCurrentProcessId` at `0x18000162b`
- `KERNEL32!GetCurrentThreadId` at `0x180001637`
- `KERNEL32!GetCurrentThreadId` at `0x180001637`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000161d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000161d`

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
0x1800015e4  mov     [rsp-8+arg_18], rbx
0x1800015e9  push    rbp
0x1800015ea  mov     rbp, rsp
0x1800015ed  sub     rsp, 20h
0x1800015f1  xor     eax, eax
0x1800015f3  mov     rbx, 2B992DDFA232h
0x1800015fd  mov     [rbp+arg_0], rax
0x180001601  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001605  mov     qword ptr [rbp+PerformanceCount], rax
0x180001609  mov     rax, cs:__security_cookie
0x180001610  cmp     rax, rbx
0x180001613  jnz     loc_1800016AC
0x180001619  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000161d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001623  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001627  mov     [rbp+arg_0], rax
0x18000162b  call    cs:__imp_GetCurrentProcessId
0x180001631  mov     eax, eax
0x180001633  xor     [rbp+arg_0], rax
0x180001637  call    cs:__imp_GetCurrentThreadId
0x18000163d  mov     eax, eax
0x18000163f  xor     [rbp+arg_0], rax
0x180001643  call    cs:__imp_GetTickCount
0x180001649  mov     eax, eax
0x18000164b  shl     rax, 18h
0x18000164f  xor     [rbp+arg_0], rax
0x180001653  call    cs:__imp_GetTickCount
0x180001659  mov     eax, eax
0x18000165b  lea     rcx, [rbp+arg_0]
0x18000165f  xor     rax, [rbp+arg_0]
0x180001663  xor     rax, rcx
0x180001666  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000166a  mov     [rbp+arg_0], rax
0x18000166e  call    cs:__imp_QueryPerformanceCounter
0x180001674  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001677  mov     rcx, 0FFFFFFFFFFFFh
0x180001681  shl     rax, 20h
0x180001685  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001689  xor     rax, [rbp+arg_0]
0x18000168d  and     rax, rcx
0x180001690  mov     rcx, rax
0x180001693  cmp     rax, rbx
0x180001696  jnz     short loc_1800016A5
0x180001698  mov     rax, 2B992DDFA233h
0x1800016a2  mov     rcx, rax
0x1800016a5  mov     cs:__security_cookie, rcx
0x1800016ac  mov     rbx, [rsp+20h+arg_18]
0x1800016b1  not     rax
0x1800016b4  mov     cs:__security_cookie_complement, rax
0x1800016bb  add     rsp, 20h
0x1800016bf  pop     rbp
0x1800016c0  retn
```
