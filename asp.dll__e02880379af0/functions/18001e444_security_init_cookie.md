# __security_init_cookie

- ea: `0x18001e444`
- end: `0x18001e521`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001dca0`

## callees

- `0x18001e444`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18001e4ce`
- `KERNEL32!QueryPerformanceCounter` at `0x18001e4ce`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001e47d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001e47d`
- `KERNEL32!GetCurrentThreadId` at `0x18001e497`
- `KERNEL32!GetCurrentThreadId` at `0x18001e497`
- `KERNEL32!GetTickCount` at `0x18001e4a3`
- `KERNEL32!GetTickCount` at `0x18001e4b3`
- `KERNEL32!GetTickCount` at `0x18001e4a3`
- `KERNEL32!GetTickCount` at `0x18001e4b3`
- `KERNEL32!GetCurrentProcessId` at `0x18001e48b`
- `KERNEL32!GetCurrentProcessId` at `0x18001e48b`

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
0x18001e444  mov     [rsp-8+arg_18], rbx
0x18001e449  push    rbp
0x18001e44a  mov     rbp, rsp
0x18001e44d  sub     rsp, 20h
0x18001e451  xor     eax, eax
0x18001e453  mov     rbx, 2B992DDFA232h
0x18001e45d  mov     [rbp+arg_0], rax
0x18001e461  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001e465  mov     qword ptr [rbp+PerformanceCount], rax
0x18001e469  mov     rax, cs:__security_cookie
0x18001e470  cmp     rax, rbx
0x18001e473  jnz     loc_18001E50C
0x18001e479  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001e47d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001e483  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001e487  mov     [rbp+arg_0], rax
0x18001e48b  call    cs:__imp_GetCurrentProcessId
0x18001e491  mov     eax, eax
0x18001e493  xor     [rbp+arg_0], rax
0x18001e497  call    cs:__imp_GetCurrentThreadId
0x18001e49d  mov     eax, eax
0x18001e49f  xor     [rbp+arg_0], rax
0x18001e4a3  call    cs:__imp_GetTickCount
0x18001e4a9  mov     eax, eax
0x18001e4ab  shl     rax, 18h
0x18001e4af  xor     [rbp+arg_0], rax
0x18001e4b3  call    cs:__imp_GetTickCount
0x18001e4b9  mov     eax, eax
0x18001e4bb  lea     rcx, [rbp+arg_0]
0x18001e4bf  xor     rax, [rbp+arg_0]
0x18001e4c3  xor     rax, rcx
0x18001e4c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001e4ca  mov     [rbp+arg_0], rax
0x18001e4ce  call    cs:__imp_QueryPerformanceCounter
0x18001e4d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001e4d7  mov     rcx, 0FFFFFFFFFFFFh
0x18001e4e1  shl     rax, 20h
0x18001e4e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001e4e9  xor     rax, [rbp+arg_0]
0x18001e4ed  and     rax, rcx
0x18001e4f0  mov     rcx, rax
0x18001e4f3  cmp     rax, rbx
0x18001e4f6  jnz     short loc_18001E505
0x18001e4f8  mov     rax, 2B992DDFA233h
0x18001e502  mov     rcx, rax
0x18001e505  mov     cs:__security_cookie, rcx
0x18001e50c  mov     rbx, [rsp+20h+arg_18]
0x18001e511  not     rax
0x18001e514  mov     cs:__security_cookie_complement, rax
0x18001e51b  add     rsp, 20h
0x18001e51f  pop     rbp
0x18001e520  retn
```
