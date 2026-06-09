# __security_init_cookie

- ea: `0x18002df34`
- end: `0x18002dfe9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002d260`

## callees

- `0x18002df34`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18002df77`
- `KERNEL32!GetCurrentThreadId` at `0x18002df77`
- `KERNEL32!GetCurrentProcessId` at `0x18002df83`
- `KERNEL32!GetCurrentProcessId` at `0x18002df83`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002df69`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002df69`
- `KERNEL32!QueryPerformanceCounter` at `0x18002df93`
- `KERNEL32!QueryPerformanceCounter` at `0x18002df93`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x18002df34  mov     [rsp-8+arg_10], rbx
0x18002df39  push    rbp
0x18002df3a  mov     rbp, rsp
0x18002df3d  sub     rsp, 30h
0x18002df41  mov     rax, cs:__security_cookie
0x18002df48  mov     rbx, 2B992DDFA232h
0x18002df52  cmp     rax, rbx
0x18002df55  jnz     short loc_18002DFD4
0x18002df57  xor     eax, eax
0x18002df59  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002df5d  mov     [rbp+var_10], rax
0x18002df61  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002df65  mov     qword ptr [rbp+PerformanceCount], rax
0x18002df69  call    cs:__imp_GetSystemTimeAsFileTime
0x18002df6f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002df73  mov     [rbp+var_10], rax
0x18002df77  call    cs:__imp_GetCurrentThreadId
0x18002df7d  mov     eax, eax
0x18002df7f  xor     [rbp+var_10], rax
0x18002df83  call    cs:__imp_GetCurrentProcessId
0x18002df89  mov     eax, eax
0x18002df8b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002df8f  xor     [rbp+var_10], rax
0x18002df93  call    cs:__imp_QueryPerformanceCounter
0x18002df99  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002df9c  lea     rcx, [rbp+var_10]
0x18002dfa0  shl     rax, 20h
0x18002dfa4  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002dfa8  xor     rax, [rbp+var_10]
0x18002dfac  xor     rax, rcx
0x18002dfaf  mov     rcx, 0FFFFFFFFFFFFh
0x18002dfb9  and     rax, rcx
0x18002dfbc  mov     rcx, 2B992DDFA233h
0x18002dfc6  cmp     rax, rbx
0x18002dfc9  cmovz   rax, rcx
0x18002dfcd  mov     cs:__security_cookie, rax
0x18002dfd4  mov     rbx, [rsp+30h+arg_10]
0x18002dfd9  not     rax
0x18002dfdc  mov     cs:__security_cookie_complement, rax
0x18002dfe3  add     rsp, 30h
0x18002dfe7  pop     rbp
0x18002dfe8  retn
```
