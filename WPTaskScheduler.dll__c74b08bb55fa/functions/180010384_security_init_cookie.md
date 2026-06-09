# __security_init_cookie

- ea: `0x180010384`
- end: `0x180010461`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fe30`

## callees

- `0x180010384`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800103cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800103cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800103bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800103bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800103e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800103f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800103e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800103f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001040e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001040e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180010384  mov     [rsp-8+arg_18], rbx
0x180010389  push    rbp
0x18001038a  mov     rbp, rsp
0x18001038d  sub     rsp, 20h
0x180010391  xor     eax, eax
0x180010393  mov     rbx, 2B992DDFA232h
0x18001039d  mov     [rbp+arg_0], rax
0x1800103a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800103a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800103a9  mov     rax, cs:__security_cookie
0x1800103b0  cmp     rax, rbx
0x1800103b3  jnz     loc_18001044C
0x1800103b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800103bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800103c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800103c7  mov     [rbp+arg_0], rax
0x1800103cb  call    cs:__imp_GetCurrentProcessId
0x1800103d1  mov     eax, eax
0x1800103d3  xor     [rbp+arg_0], rax
0x1800103d7  call    cs:__imp_GetCurrentThreadId
0x1800103dd  mov     eax, eax
0x1800103df  xor     [rbp+arg_0], rax
0x1800103e3  call    cs:__imp_GetTickCount
0x1800103e9  mov     eax, eax
0x1800103eb  shl     rax, 18h
0x1800103ef  xor     [rbp+arg_0], rax
0x1800103f3  call    cs:__imp_GetTickCount
0x1800103f9  mov     eax, eax
0x1800103fb  lea     rcx, [rbp+arg_0]
0x1800103ff  xor     rax, [rbp+arg_0]
0x180010403  xor     rax, rcx
0x180010406  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001040a  mov     [rbp+arg_0], rax
0x18001040e  call    cs:__imp_QueryPerformanceCounter
0x180010414  mov     eax, dword ptr [rbp+PerformanceCount]
0x180010417  mov     rcx, 0FFFFFFFFFFFFh
0x180010421  shl     rax, 20h
0x180010425  xor     rax, qword ptr [rbp+PerformanceCount]
0x180010429  xor     rax, [rbp+arg_0]
0x18001042d  and     rax, rcx
0x180010430  mov     rcx, rax
0x180010433  cmp     rax, rbx
0x180010436  jnz     short loc_180010445
0x180010438  mov     rax, 2B992DDFA233h
0x180010442  mov     rcx, rax
0x180010445  mov     cs:__security_cookie, rcx
0x18001044c  mov     rbx, [rsp+20h+arg_18]
0x180010451  not     rax
0x180010454  mov     cs:__security_cookie_complement, rax
0x18001045b  add     rsp, 20h
0x18001045f  pop     rbp
0x180010460  retn
```
