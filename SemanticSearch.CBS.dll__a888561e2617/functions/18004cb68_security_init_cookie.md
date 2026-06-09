# __security_init_cookie

- ea: `0x18004cb68`
- end: `0x18004cc17`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c3f0`

## callees

- `0x18004cb68`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18004cba5`
- `KERNEL32!GetCurrentThreadId` at `0x18004cba5`
- `KERNEL32!GetCurrentProcessId` at `0x18004cbb1`
- `KERNEL32!GetCurrentProcessId` at `0x18004cbb1`
- `KERNEL32!QueryPerformanceCounter` at `0x18004cbc1`
- `KERNEL32!QueryPerformanceCounter` at `0x18004cbc1`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004cb97`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18004cb97`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x18004cb68  mov     [rsp-8+arg_10], rbx
0x18004cb6d  push    rbp
0x18004cb6e  mov     rbp, rsp
0x18004cb71  sub     rsp, 30h
0x18004cb75  mov     rax, cs:__security_cookie
0x18004cb7c  mov     rbx, 2B992DDFA232h
0x18004cb86  cmp     rax, rbx
0x18004cb89  jnz     short loc_18004CC02
0x18004cb8b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004cb8f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18004cb97  call    cs:__imp_GetSystemTimeAsFileTime
0x18004cb9d  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004cba1  mov     [rbp+var_10], rax
0x18004cba5  call    cs:__imp_GetCurrentThreadId
0x18004cbab  mov     eax, eax
0x18004cbad  xor     [rbp+var_10], rax
0x18004cbb1  call    cs:__imp_GetCurrentProcessId
0x18004cbb7  mov     eax, eax
0x18004cbb9  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004cbbd  xor     [rbp+var_10], rax
0x18004cbc1  call    cs:__imp_QueryPerformanceCounter
0x18004cbc7  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004cbca  lea     rcx, [rbp+var_10]
0x18004cbce  shl     rax, 20h
0x18004cbd2  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004cbd6  xor     rax, [rbp+var_10]
0x18004cbda  xor     rax, rcx
0x18004cbdd  mov     rcx, 0FFFFFFFFFFFFh
0x18004cbe7  and     rax, rcx
0x18004cbea  mov     rcx, 2B992DDFA233h
0x18004cbf4  cmp     rax, rbx
0x18004cbf7  cmovz   rax, rcx
0x18004cbfb  mov     cs:__security_cookie, rax
0x18004cc02  mov     rbx, [rsp+30h+arg_10]
0x18004cc07  not     rax
0x18004cc0a  mov     cs:__security_cookie_complement, rax
0x18004cc11  add     rsp, 30h
0x18004cc15  pop     rbp
0x18004cc16  retn
```
