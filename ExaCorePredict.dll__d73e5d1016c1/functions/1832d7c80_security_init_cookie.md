# __security_init_cookie

- ea: `0x1832d7c80`
- end: `0x1832d7d2c`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1832cf6b0`

## callees

- `0x1832d7c80`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1832d7cba`
- `KERNEL32!GetCurrentThreadId` at `0x1832d7cba`
- `KERNEL32!QueryPerformanceCounter` at `0x1832d7cd6`
- `KERNEL32!QueryPerformanceCounter` at `0x1832d7cd6`
- `KERNEL32!GetCurrentProcessId` at `0x1832d7cc6`
- `KERNEL32!GetCurrentProcessId` at `0x1832d7cc6`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1832d7cac`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1832d7cac`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  SystemTimeAsFileTime = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
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
0x1832d7c80  mov     [rsp-8+arg_18], rbx
0x1832d7c85  push    rbp
0x1832d7c86  mov     rbp, rsp
0x1832d7c89  sub     rsp, 20h
0x1832d7c8d  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1832d7c92  mov     rbx, 2B992DDFA232h
0x1832d7c9c  mov     rax, cs:__security_cookie
0x1832d7ca3  cmp     rax, rbx
0x1832d7ca6  jnz     short loc_1832D7D17
0x1832d7ca8  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1832d7cac  call    cs:__imp_GetSystemTimeAsFileTime
0x1832d7cb2  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1832d7cb6  mov     [rbp+arg_0], rax
0x1832d7cba  call    cs:__imp_GetCurrentThreadId
0x1832d7cc0  mov     eax, eax
0x1832d7cc2  xor     [rbp+arg_0], rax
0x1832d7cc6  call    cs:__imp_GetCurrentProcessId
0x1832d7ccc  mov     eax, eax
0x1832d7cce  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1832d7cd2  xor     [rbp+arg_0], rax
0x1832d7cd6  call    cs:__imp_QueryPerformanceCounter
0x1832d7cdc  mov     eax, dword ptr [rbp+PerformanceCount]
0x1832d7cdf  lea     rcx, [rbp+arg_0]
0x1832d7ce3  shl     rax, 20h
0x1832d7ce7  xor     rax, qword ptr [rbp+PerformanceCount]
0x1832d7ceb  xor     rax, [rbp+arg_0]
0x1832d7cef  xor     rax, rcx
0x1832d7cf2  mov     rcx, 0FFFFFFFFFFFFh
0x1832d7cfc  and     rax, rcx
0x1832d7cff  mov     rcx, 2B992DDFA233h
0x1832d7d09  cmp     rax, rbx
0x1832d7d0c  cmovz   rax, rcx
0x1832d7d10  mov     cs:__security_cookie, rax
0x1832d7d17  mov     rbx, [rsp+20h+arg_18]
0x1832d7d1c  not     rax
0x1832d7d1f  mov     cs:__security_cookie_complement, rax
0x1832d7d26  add     rsp, 20h
0x1832d7d2a  pop     rbp
0x1832d7d2b  retn
```
