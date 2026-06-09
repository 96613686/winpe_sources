# __security_init_cookie

- ea: `0x18003ee94`
- end: `0x18003ef71`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e410`

## callees

- `0x18003ee94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003eedb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003eedb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003eee7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003eee7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ef1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003ef1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003eecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003eecd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003eef3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ef03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003eef3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003ef03`

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
0x18003ee94  mov     [rsp-8+arg_18], rbx
0x18003ee99  push    rbp
0x18003ee9a  mov     rbp, rsp
0x18003ee9d  sub     rsp, 20h
0x18003eea1  xor     eax, eax
0x18003eea3  mov     rbx, 2B992DDFA232h
0x18003eead  mov     [rbp+arg_0], rax
0x18003eeb1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003eeb5  mov     qword ptr [rbp+PerformanceCount], rax
0x18003eeb9  mov     rax, cs:__security_cookie
0x18003eec0  cmp     rax, rbx
0x18003eec3  jnz     loc_18003EF5C
0x18003eec9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003eecd  call    cs:__imp_GetSystemTimeAsFileTime
0x18003eed3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003eed7  mov     [rbp+arg_0], rax
0x18003eedb  call    cs:__imp_GetCurrentProcessId
0x18003eee1  mov     eax, eax
0x18003eee3  xor     [rbp+arg_0], rax
0x18003eee7  call    cs:__imp_GetCurrentThreadId
0x18003eeed  mov     eax, eax
0x18003eeef  xor     [rbp+arg_0], rax
0x18003eef3  call    cs:__imp_GetTickCount
0x18003eef9  mov     eax, eax
0x18003eefb  shl     rax, 18h
0x18003eeff  xor     [rbp+arg_0], rax
0x18003ef03  call    cs:__imp_GetTickCount
0x18003ef09  mov     eax, eax
0x18003ef0b  lea     rcx, [rbp+arg_0]
0x18003ef0f  xor     rax, [rbp+arg_0]
0x18003ef13  xor     rax, rcx
0x18003ef16  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003ef1a  mov     [rbp+arg_0], rax
0x18003ef1e  call    cs:__imp_QueryPerformanceCounter
0x18003ef24  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003ef27  mov     rcx, 0FFFFFFFFFFFFh
0x18003ef31  shl     rax, 20h
0x18003ef35  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003ef39  xor     rax, [rbp+arg_0]
0x18003ef3d  and     rax, rcx
0x18003ef40  mov     rcx, rax
0x18003ef43  cmp     rax, rbx
0x18003ef46  jnz     short loc_18003EF55
0x18003ef48  mov     rax, 2B992DDFA233h
0x18003ef52  mov     rcx, rax
0x18003ef55  mov     cs:__security_cookie, rcx
0x18003ef5c  mov     rbx, [rsp+20h+arg_18]
0x18003ef61  not     rax
0x18003ef64  mov     cs:__security_cookie_complement, rax
0x18003ef6b  add     rsp, 20h
0x18003ef6f  pop     rbp
0x18003ef70  retn
```
