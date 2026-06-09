# __security_init_cookie

- ea: `0x180012d24`
- end: `0x180012dfd`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012250`

## callees

- `0x180012d24`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012d59`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012d59`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012d7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012d8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012d7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180012d8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012d73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012d67`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012daa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012daa`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x180012d24  mov     [rsp-8+arg_18], rbx
0x180012d29  push    rbp
0x180012d2a  mov     rbp, rsp
0x180012d2d  sub     rsp, 20h
0x180012d31  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180012d36  mov     rbx, 2B992DDFA232h
0x180012d40  and     qword ptr [rbp+PerformanceCount], 0
0x180012d45  mov     rax, cs:__security_cookie
0x180012d4c  cmp     rax, rbx
0x180012d4f  jnz     loc_180012DE8
0x180012d55  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012d59  call    cs:__imp_GetSystemTimeAsFileTime
0x180012d5f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180012d63  mov     [rbp+arg_0], rax
0x180012d67  call    cs:__imp_GetCurrentProcessId
0x180012d6d  mov     eax, eax
0x180012d6f  xor     [rbp+arg_0], rax
0x180012d73  call    cs:__imp_GetCurrentThreadId
0x180012d79  mov     eax, eax
0x180012d7b  xor     [rbp+arg_0], rax
0x180012d7f  call    cs:__imp_GetTickCount
0x180012d85  mov     eax, eax
0x180012d87  shl     rax, 18h
0x180012d8b  xor     [rbp+arg_0], rax
0x180012d8f  call    cs:__imp_GetTickCount
0x180012d95  mov     eax, eax
0x180012d97  lea     rcx, [rbp+arg_0]
0x180012d9b  xor     rax, [rbp+arg_0]
0x180012d9f  xor     rax, rcx
0x180012da2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180012da6  mov     [rbp+arg_0], rax
0x180012daa  call    cs:__imp_QueryPerformanceCounter
0x180012db0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180012db3  mov     rcx, 0FFFFFFFFFFFFh
0x180012dbd  shl     rax, 20h
0x180012dc1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180012dc5  xor     rax, [rbp+arg_0]
0x180012dc9  and     rax, rcx
0x180012dcc  mov     rcx, rax
0x180012dcf  cmp     rax, rbx
0x180012dd2  jnz     short loc_180012DE1
0x180012dd4  mov     rax, 2B992DDFA233h
0x180012dde  mov     rcx, rax
0x180012de1  mov     cs:__security_cookie, rcx
0x180012de8  mov     rbx, [rsp+20h+arg_18]
0x180012ded  not     rax
0x180012df0  mov     cs:__security_cookie_complement, rax
0x180012df7  add     rsp, 20h
0x180012dfb  pop     rbp
0x180012dfc  retn
```
