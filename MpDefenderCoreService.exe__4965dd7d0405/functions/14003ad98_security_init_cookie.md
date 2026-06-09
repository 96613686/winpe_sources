# __security_init_cookie

- ea: `0x14003ad98`
- end: `0x14003ae47`
- name: `__security_init_cookie`
- size: `175`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a0e0`

## callees

- `0x14003ad98`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14003add5`
- `KERNEL32!GetCurrentThreadId` at `0x14003add5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14003adc7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14003adc7`
- `KERNEL32!GetCurrentProcessId` at `0x14003ade1`
- `KERNEL32!GetCurrentProcessId` at `0x14003ade1`
- `KERNEL32!QueryPerformanceCounter` at `0x14003adf1`
- `KERNEL32!QueryPerformanceCounter` at `0x14003adf1`

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
0x14003ad98  mov     [rsp-8+arg_10], rbx
0x14003ad9d  push    rbp
0x14003ad9e  mov     rbp, rsp
0x14003ada1  sub     rsp, 30h
0x14003ada5  mov     rax, cs:__security_cookie
0x14003adac  mov     rbx, 2B992DDFA232h
0x14003adb6  cmp     rax, rbx
0x14003adb9  jnz     short loc_14003AE32
0x14003adbb  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14003adbf  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x14003adc7  call    cs:__imp_GetSystemTimeAsFileTime
0x14003adcd  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14003add1  mov     [rbp+var_10], rax
0x14003add5  call    cs:__imp_GetCurrentThreadId
0x14003addb  mov     eax, eax
0x14003addd  xor     [rbp+var_10], rax
0x14003ade1  call    cs:__imp_GetCurrentProcessId
0x14003ade7  mov     eax, eax
0x14003ade9  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14003aded  xor     [rbp+var_10], rax
0x14003adf1  call    cs:__imp_QueryPerformanceCounter
0x14003adf7  mov     eax, dword ptr [rbp+PerformanceCount]
0x14003adfa  lea     rcx, [rbp+var_10]
0x14003adfe  shl     rax, 20h
0x14003ae02  xor     rax, qword ptr [rbp+PerformanceCount]
0x14003ae06  xor     rax, [rbp+var_10]
0x14003ae0a  xor     rax, rcx
0x14003ae0d  mov     rcx, 0FFFFFFFFFFFFh
0x14003ae17  and     rax, rcx
0x14003ae1a  mov     rcx, 2B992DDFA233h
0x14003ae24  cmp     rax, rbx
0x14003ae27  cmovz   rax, rcx
0x14003ae2b  mov     cs:__security_cookie, rax
0x14003ae32  mov     rbx, [rsp+30h+arg_10]
0x14003ae37  not     rax
0x14003ae3a  mov     cs:__security_cookie_complement, rax
0x14003ae41  add     rsp, 30h
0x14003ae45  pop     rbp
0x14003ae46  retn
```
