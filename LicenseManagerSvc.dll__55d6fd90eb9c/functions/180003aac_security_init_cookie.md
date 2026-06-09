# __security_init_cookie

- ea: `0x180003aac`
- end: `0x180003b61`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003380`

## callees

- `0x180003aac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003aef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003aef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003afb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180003afb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003b0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180003b0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003ae1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180003ae1`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180003aac  mov     [rsp-8+arg_10], rbx
0x180003ab1  push    rbp
0x180003ab2  mov     rbp, rsp
0x180003ab5  sub     rsp, 30h
0x180003ab9  mov     rax, cs:__security_cookie
0x180003ac0  mov     rbx, 2B992DDFA232h
0x180003aca  cmp     rax, rbx
0x180003acd  jnz     short loc_180003B4C
0x180003acf  xor     eax, eax
0x180003ad1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003ad5  mov     [rbp+var_10], rax
0x180003ad9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003add  mov     qword ptr [rbp+PerformanceCount], rax
0x180003ae1  call    cs:__imp_GetSystemTimeAsFileTime
0x180003ae7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003aeb  mov     [rbp+var_10], rax
0x180003aef  call    cs:__imp_GetCurrentThreadId
0x180003af5  mov     eax, eax
0x180003af7  xor     [rbp+var_10], rax
0x180003afb  call    cs:__imp_GetCurrentProcessId
0x180003b01  mov     eax, eax
0x180003b03  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003b07  xor     [rbp+var_10], rax
0x180003b0b  call    cs:__imp_QueryPerformanceCounter
0x180003b11  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003b14  lea     rcx, [rbp+var_10]
0x180003b18  shl     rax, 20h
0x180003b1c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003b20  xor     rax, [rbp+var_10]
0x180003b24  xor     rax, rcx
0x180003b27  mov     rcx, 0FFFFFFFFFFFFh
0x180003b31  and     rax, rcx
0x180003b34  mov     rcx, 2B992DDFA233h
0x180003b3e  cmp     rax, rbx
0x180003b41  cmovz   rax, rcx
0x180003b45  mov     cs:__security_cookie, rax
0x180003b4c  mov     rbx, [rsp+30h+arg_10]
0x180003b51  not     rax
0x180003b54  mov     cs:__security_cookie_complement, rax
0x180003b5b  add     rsp, 30h
0x180003b5f  pop     rbp
0x180003b60  retn
```
