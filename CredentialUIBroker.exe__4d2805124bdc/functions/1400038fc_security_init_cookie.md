# __security_init_cookie

- ea: `0x1400038fc`
- end: `0x1400039b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400035f0`

## callees

- `0x1400038fc`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000393f`
- `KERNEL32!GetCurrentThreadId` at `0x14000393f`
- `KERNEL32!GetCurrentProcessId` at `0x14000394b`
- `KERNEL32!GetCurrentProcessId` at `0x14000394b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000395b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000395b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003931`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003931`

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
0x1400038fc  mov     [rsp-8+arg_10], rbx
0x140003901  push    rbp
0x140003902  mov     rbp, rsp
0x140003905  sub     rsp, 30h
0x140003909  mov     rax, cs:__security_cookie
0x140003910  mov     rbx, 2B992DDFA232h
0x14000391a  cmp     rax, rbx
0x14000391d  jnz     short loc_14000399C
0x14000391f  xor     eax, eax
0x140003921  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003925  mov     [rbp+var_10], rax
0x140003929  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000392d  mov     qword ptr [rbp+PerformanceCount], rax
0x140003931  call    cs:__imp_GetSystemTimeAsFileTime
0x140003937  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000393b  mov     [rbp+var_10], rax
0x14000393f  call    cs:__imp_GetCurrentThreadId
0x140003945  mov     eax, eax
0x140003947  xor     [rbp+var_10], rax
0x14000394b  call    cs:__imp_GetCurrentProcessId
0x140003951  mov     eax, eax
0x140003953  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140003957  xor     [rbp+var_10], rax
0x14000395b  call    cs:__imp_QueryPerformanceCounter
0x140003961  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003964  lea     rcx, [rbp+var_10]
0x140003968  shl     rax, 20h
0x14000396c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003970  xor     rax, [rbp+var_10]
0x140003974  xor     rax, rcx
0x140003977  mov     rcx, 0FFFFFFFFFFFFh
0x140003981  and     rax, rcx
0x140003984  mov     rcx, 2B992DDFA233h
0x14000398e  cmp     rax, rbx
0x140003991  cmovz   rax, rcx
0x140003995  mov     cs:__security_cookie, rax
0x14000399c  mov     rbx, [rsp+30h+arg_10]
0x1400039a1  not     rax
0x1400039a4  mov     cs:__security_cookie_complement, rax
0x1400039ab  add     rsp, 30h
0x1400039af  pop     rbp
0x1400039b0  retn
```
