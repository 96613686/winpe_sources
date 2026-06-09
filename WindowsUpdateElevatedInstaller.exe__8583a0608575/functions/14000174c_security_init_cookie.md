# __security_init_cookie

- ea: `0x14000174c`
- end: `0x140001801`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001450`

## callees

- `0x14000174c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000178f`
- `KERNEL32!GetCurrentThreadId` at `0x14000178f`
- `KERNEL32!GetCurrentProcessId` at `0x14000179b`
- `KERNEL32!GetCurrentProcessId` at `0x14000179b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001781`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001781`

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
0x14000174c  mov     [rsp-8+arg_10], rbx
0x140001751  push    rbp
0x140001752  mov     rbp, rsp
0x140001755  sub     rsp, 30h
0x140001759  mov     rax, cs:__security_cookie
0x140001760  mov     rbx, 2B992DDFA232h
0x14000176a  cmp     rax, rbx
0x14000176d  jnz     short loc_1400017EC
0x14000176f  xor     eax, eax
0x140001771  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001775  mov     [rbp+var_10], rax
0x140001779  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000177d  mov     qword ptr [rbp+PerformanceCount], rax
0x140001781  call    cs:__imp_GetSystemTimeAsFileTime
0x140001787  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000178b  mov     [rbp+var_10], rax
0x14000178f  call    cs:__imp_GetCurrentThreadId
0x140001795  mov     eax, eax
0x140001797  xor     [rbp+var_10], rax
0x14000179b  call    cs:__imp_GetCurrentProcessId
0x1400017a1  mov     eax, eax
0x1400017a3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400017a7  xor     [rbp+var_10], rax
0x1400017ab  call    cs:__imp_QueryPerformanceCounter
0x1400017b1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400017b4  lea     rcx, [rbp+var_10]
0x1400017b8  shl     rax, 20h
0x1400017bc  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400017c0  xor     rax, [rbp+var_10]
0x1400017c4  xor     rax, rcx
0x1400017c7  mov     rcx, 0FFFFFFFFFFFFh
0x1400017d1  and     rax, rcx
0x1400017d4  mov     rcx, 2B992DDFA233h
0x1400017de  cmp     rax, rbx
0x1400017e1  cmovz   rax, rcx
0x1400017e5  mov     cs:__security_cookie, rax
0x1400017ec  mov     rbx, [rsp+30h+arg_10]
0x1400017f1  not     rax
0x1400017f4  mov     cs:__security_cookie_complement, rax
0x1400017fb  add     rsp, 30h
0x1400017ff  pop     rbp
0x140001800  retn
```
