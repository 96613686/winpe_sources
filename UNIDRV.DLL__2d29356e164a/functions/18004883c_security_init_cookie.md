# __security_init_cookie

- ea: `0x18004883c`
- end: `0x1800488f1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180048790`

## callees

- `0x18004883c`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180048871`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180048871`
- `KERNEL32!GetCurrentThreadId` at `0x18004887f`
- `KERNEL32!GetCurrentThreadId` at `0x18004887f`
- `KERNEL32!GetCurrentProcessId` at `0x18004888b`
- `KERNEL32!GetCurrentProcessId` at `0x18004888b`
- `KERNEL32!QueryPerformanceCounter` at `0x18004889b`
- `KERNEL32!QueryPerformanceCounter` at `0x18004889b`

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
0x18004883c  mov     [rsp-8+arg_10], rbx
0x180048841  push    rbp
0x180048842  mov     rbp, rsp
0x180048845  sub     rsp, 30h
0x180048849  mov     rax, cs:__security_cookie
0x180048850  mov     rbx, 2B992DDFA232h
0x18004885a  cmp     rax, rbx
0x18004885d  jnz     short loc_1800488DC
0x18004885f  xor     eax, eax
0x180048861  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180048865  mov     [rbp+var_10], rax
0x180048869  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004886d  mov     qword ptr [rbp+PerformanceCount], rax
0x180048871  call    cs:__imp_GetSystemTimeAsFileTime
0x180048877  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004887b  mov     [rbp+var_10], rax
0x18004887f  call    cs:__imp_GetCurrentThreadId
0x180048885  mov     eax, eax
0x180048887  xor     [rbp+var_10], rax
0x18004888b  call    cs:__imp_GetCurrentProcessId
0x180048891  mov     eax, eax
0x180048893  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180048897  xor     [rbp+var_10], rax
0x18004889b  call    cs:__imp_QueryPerformanceCounter
0x1800488a1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800488a4  lea     rcx, [rbp+var_10]
0x1800488a8  shl     rax, 20h
0x1800488ac  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800488b0  xor     rax, [rbp+var_10]
0x1800488b4  xor     rax, rcx
0x1800488b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800488c1  and     rax, rcx
0x1800488c4  mov     rcx, 2B992DDFA233h
0x1800488ce  cmp     rax, rbx
0x1800488d1  cmovz   rax, rcx
0x1800488d5  mov     cs:__security_cookie, rax
0x1800488dc  mov     rbx, [rsp+30h+arg_10]
0x1800488e1  not     rax
0x1800488e4  mov     cs:__security_cookie_complement, rax
0x1800488eb  add     rsp, 30h
0x1800488ef  pop     rbp
0x1800488f0  retn
```
