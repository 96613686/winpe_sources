# __security_init_cookie

- ea: `0x18001cdc4`
- end: `0x18001cea1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c5f0`

## callees

- `0x18001cdc4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ce0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ce0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ce17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ce17`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ce4e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ce4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cdfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001cdfd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ce23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ce33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ce23`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001ce33`

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
0x18001cdc4  mov     [rsp-8+arg_18], rbx
0x18001cdc9  push    rbp
0x18001cdca  mov     rbp, rsp
0x18001cdcd  sub     rsp, 20h
0x18001cdd1  xor     eax, eax
0x18001cdd3  mov     rbx, 2B992DDFA232h
0x18001cddd  mov     [rbp+arg_0], rax
0x18001cde1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001cde5  mov     qword ptr [rbp+PerformanceCount], rax
0x18001cde9  mov     rax, cs:__security_cookie
0x18001cdf0  cmp     rax, rbx
0x18001cdf3  jnz     loc_18001CE8C
0x18001cdf9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001cdfd  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ce03  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001ce07  mov     [rbp+arg_0], rax
0x18001ce0b  call    cs:__imp_GetCurrentProcessId
0x18001ce11  mov     eax, eax
0x18001ce13  xor     [rbp+arg_0], rax
0x18001ce17  call    cs:__imp_GetCurrentThreadId
0x18001ce1d  mov     eax, eax
0x18001ce1f  xor     [rbp+arg_0], rax
0x18001ce23  call    cs:__imp_GetTickCount
0x18001ce29  mov     eax, eax
0x18001ce2b  shl     rax, 18h
0x18001ce2f  xor     [rbp+arg_0], rax
0x18001ce33  call    cs:__imp_GetTickCount
0x18001ce39  mov     eax, eax
0x18001ce3b  lea     rcx, [rbp+arg_0]
0x18001ce3f  xor     rax, [rbp+arg_0]
0x18001ce43  xor     rax, rcx
0x18001ce46  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001ce4a  mov     [rbp+arg_0], rax
0x18001ce4e  call    cs:__imp_QueryPerformanceCounter
0x18001ce54  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001ce57  mov     rcx, 0FFFFFFFFFFFFh
0x18001ce61  shl     rax, 20h
0x18001ce65  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001ce69  xor     rax, [rbp+arg_0]
0x18001ce6d  and     rax, rcx
0x18001ce70  mov     rcx, rax
0x18001ce73  cmp     rax, rbx
0x18001ce76  jnz     short loc_18001CE85
0x18001ce78  mov     rax, 2B992DDFA233h
0x18001ce82  mov     rcx, rax
0x18001ce85  mov     cs:__security_cookie, rcx
0x18001ce8c  mov     rbx, [rsp+20h+arg_18]
0x18001ce91  not     rax
0x18001ce94  mov     cs:__security_cookie_complement, rax
0x18001ce9b  add     rsp, 20h
0x18001ce9f  pop     rbp
0x18001cea0  retn
```
