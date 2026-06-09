# __security_init_cookie

- ea: `0x1800030e4`
- end: `0x1800031c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002930`

## callees

- `0x1800030e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000312b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000312b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003143`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003153`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003143`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003153`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000311d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000311d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000316e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000316e`

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
0x1800030e4  mov     [rsp-8+arg_18], rbx
0x1800030e9  push    rbp
0x1800030ea  mov     rbp, rsp
0x1800030ed  sub     rsp, 20h
0x1800030f1  xor     eax, eax
0x1800030f3  mov     rbx, 2B992DDFA232h
0x1800030fd  mov     [rbp+arg_0], rax
0x180003101  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003105  mov     qword ptr [rbp+PerformanceCount], rax
0x180003109  mov     rax, cs:__security_cookie
0x180003110  cmp     rax, rbx
0x180003113  jnz     loc_1800031AC
0x180003119  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000311d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003123  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003127  mov     [rbp+arg_0], rax
0x18000312b  call    cs:__imp_GetCurrentProcessId
0x180003131  mov     eax, eax
0x180003133  xor     [rbp+arg_0], rax
0x180003137  call    cs:__imp_GetCurrentThreadId
0x18000313d  mov     eax, eax
0x18000313f  xor     [rbp+arg_0], rax
0x180003143  call    cs:__imp_GetTickCount
0x180003149  mov     eax, eax
0x18000314b  shl     rax, 18h
0x18000314f  xor     [rbp+arg_0], rax
0x180003153  call    cs:__imp_GetTickCount
0x180003159  mov     eax, eax
0x18000315b  lea     rcx, [rbp+arg_0]
0x18000315f  xor     rax, [rbp+arg_0]
0x180003163  xor     rax, rcx
0x180003166  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000316a  mov     [rbp+arg_0], rax
0x18000316e  call    cs:__imp_QueryPerformanceCounter
0x180003174  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003177  mov     rcx, 0FFFFFFFFFFFFh
0x180003181  shl     rax, 20h
0x180003185  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003189  xor     rax, [rbp+arg_0]
0x18000318d  and     rax, rcx
0x180003190  mov     rcx, rax
0x180003193  cmp     rax, rbx
0x180003196  jnz     short loc_1800031A5
0x180003198  mov     rax, 2B992DDFA233h
0x1800031a2  mov     rcx, rax
0x1800031a5  mov     cs:__security_cookie, rcx
0x1800031ac  mov     rbx, [rsp+20h+arg_18]
0x1800031b1  not     rax
0x1800031b4  mov     cs:__security_cookie_complement, rax
0x1800031bb  add     rsp, 20h
0x1800031bf  pop     rbp
0x1800031c0  retn
```
