# __security_init_cookie

- ea: `0x140002864`
- end: `0x140002941`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002470`

## callees

- `0x140002864`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400028b7`
- `KERNEL32!GetCurrentThreadId` at `0x1400028b7`
- `KERNEL32!GetCurrentProcessId` at `0x1400028ab`
- `KERNEL32!GetCurrentProcessId` at `0x1400028ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400028ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400028ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400028c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400028d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400028c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400028d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000289d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000289d`

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
0x140002864  mov     [rsp-8+arg_18], rbx
0x140002869  push    rbp
0x14000286a  mov     rbp, rsp
0x14000286d  sub     rsp, 20h
0x140002871  xor     eax, eax
0x140002873  mov     rbx, 2B992DDFA232h
0x14000287d  mov     [rbp+arg_0], rax
0x140002881  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002885  mov     qword ptr [rbp+PerformanceCount], rax
0x140002889  mov     rax, cs:__security_cookie
0x140002890  cmp     rax, rbx
0x140002893  jnz     loc_14000292C
0x140002899  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000289d  call    cs:__imp_GetSystemTimeAsFileTime
0x1400028a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400028a7  mov     [rbp+arg_0], rax
0x1400028ab  call    cs:__imp_GetCurrentProcessId
0x1400028b1  mov     eax, eax
0x1400028b3  xor     [rbp+arg_0], rax
0x1400028b7  call    cs:__imp_GetCurrentThreadId
0x1400028bd  mov     eax, eax
0x1400028bf  xor     [rbp+arg_0], rax
0x1400028c3  call    cs:__imp_GetTickCount
0x1400028c9  mov     eax, eax
0x1400028cb  shl     rax, 18h
0x1400028cf  xor     [rbp+arg_0], rax
0x1400028d3  call    cs:__imp_GetTickCount
0x1400028d9  mov     eax, eax
0x1400028db  lea     rcx, [rbp+arg_0]
0x1400028df  xor     rax, [rbp+arg_0]
0x1400028e3  xor     rax, rcx
0x1400028e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400028ea  mov     [rbp+arg_0], rax
0x1400028ee  call    cs:__imp_QueryPerformanceCounter
0x1400028f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400028f7  mov     rcx, 0FFFFFFFFFFFFh
0x140002901  shl     rax, 20h
0x140002905  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002909  xor     rax, [rbp+arg_0]
0x14000290d  and     rax, rcx
0x140002910  mov     rcx, rax
0x140002913  cmp     rax, rbx
0x140002916  jnz     short loc_140002925
0x140002918  mov     rax, 2B992DDFA233h
0x140002922  mov     rcx, rax
0x140002925  mov     cs:__security_cookie, rcx
0x14000292c  mov     rbx, [rsp+20h+arg_18]
0x140002931  not     rax
0x140002934  mov     cs:__security_cookie_complement, rax
0x14000293b  add     rsp, 20h
0x14000293f  pop     rbp
0x140002940  retn
```
