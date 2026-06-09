# __security_init_cookie

- ea: `0x180039938`
- end: `0x180039a0c`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039ac8`

## callees

- `0x180039938`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180039984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039990`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039990`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003999c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800399ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003999c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800399ac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180039976`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180039976`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800399c7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800399c7`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (struct _FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180039938  mov     [rsp-8+arg_18], rbx
0x18003993d  push    rbp
0x18003993e  mov     rbp, rsp
0x180039941  sub     rsp, 20h
0x180039945  mov     rcx, cs:__security_cookie
0x18003994c  xor     eax, eax
0x18003994e  mov     [rbp+arg_0], rax
0x180039952  mov     rbx, 2B992DDFA232h
0x18003995c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180039960  mov     qword ptr [rbp+PerformanceCount], rax
0x180039964  test    rcx, rcx
0x180039967  jz      short loc_180039972
0x180039969  cmp     rcx, rbx
0x18003996c  jnz     loc_1800399F7
0x180039972  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180039976  call    cs:__imp_GetSystemTimeAsFileTime
0x18003997c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180039980  mov     [rbp+arg_0], rax
0x180039984  call    cs:__imp_GetCurrentProcessId
0x18003998a  mov     eax, eax
0x18003998c  xor     [rbp+arg_0], rax
0x180039990  call    cs:__imp_GetCurrentThreadId
0x180039996  mov     eax, eax
0x180039998  xor     [rbp+arg_0], rax
0x18003999c  call    cs:__imp_GetTickCount
0x1800399a2  mov     eax, eax
0x1800399a4  shl     rax, 18h
0x1800399a8  xor     [rbp+arg_0], rax
0x1800399ac  call    cs:__imp_GetTickCount
0x1800399b2  mov     eax, eax
0x1800399b4  lea     rcx, [rbp+arg_0]
0x1800399b8  xor     rax, [rbp+arg_0]
0x1800399bc  xor     rax, rcx
0x1800399bf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800399c3  mov     [rbp+arg_0], rax
0x1800399c7  call    cs:__imp_QueryPerformanceCounter
0x1800399cd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800399d0  mov     rcx, 0FFFFFFFFFFFFh
0x1800399da  shl     rax, 20h
0x1800399de  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800399e2  xor     rax, [rbp+arg_0]
0x1800399e6  and     rax, rcx
0x1800399e9  mov     rcx, rbx
0x1800399ec  cmovnz  rcx, rax
0x1800399f0  mov     cs:__security_cookie, rcx
0x1800399f7  mov     rbx, [rsp+20h+arg_18]
0x1800399fc  not     rcx
0x1800399ff  mov     cs:__security_cookie_complement, rcx
0x180039a06  add     rsp, 20h
0x180039a0a  pop     rbp
0x180039a0b  retn
```
