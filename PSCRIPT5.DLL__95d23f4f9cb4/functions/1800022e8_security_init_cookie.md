# __security_init_cookie

- ea: `0x1800022e8`
- end: `0x18000239d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e90`

## callees

- `0x1800022e8`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000231d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000231d`
- `KERNEL32!QueryPerformanceCounter` at `0x180002347`
- `KERNEL32!QueryPerformanceCounter` at `0x180002347`
- `KERNEL32!GetCurrentProcessId` at `0x180002337`
- `KERNEL32!GetCurrentProcessId` at `0x180002337`
- `KERNEL32!GetCurrentThreadId` at `0x18000232b`
- `KERNEL32!GetCurrentThreadId` at `0x18000232b`

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
0x1800022e8  mov     [rsp-8+arg_10], rbx
0x1800022ed  push    rbp
0x1800022ee  mov     rbp, rsp
0x1800022f1  sub     rsp, 30h
0x1800022f5  mov     rax, cs:__security_cookie
0x1800022fc  mov     rbx, 2B992DDFA232h
0x180002306  cmp     rax, rbx
0x180002309  jnz     short loc_180002388
0x18000230b  xor     eax, eax
0x18000230d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002311  mov     [rbp+var_10], rax
0x180002315  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002319  mov     qword ptr [rbp+PerformanceCount], rax
0x18000231d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002323  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002327  mov     [rbp+var_10], rax
0x18000232b  call    cs:__imp_GetCurrentThreadId
0x180002331  mov     eax, eax
0x180002333  xor     [rbp+var_10], rax
0x180002337  call    cs:__imp_GetCurrentProcessId
0x18000233d  mov     eax, eax
0x18000233f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002343  xor     [rbp+var_10], rax
0x180002347  call    cs:__imp_QueryPerformanceCounter
0x18000234d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002350  lea     rcx, [rbp+var_10]
0x180002354  shl     rax, 20h
0x180002358  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000235c  xor     rax, [rbp+var_10]
0x180002360  xor     rax, rcx
0x180002363  mov     rcx, 0FFFFFFFFFFFFh
0x18000236d  and     rax, rcx
0x180002370  mov     rcx, 2B992DDFA233h
0x18000237a  cmp     rax, rbx
0x18000237d  cmovz   rax, rcx
0x180002381  mov     cs:__security_cookie, rax
0x180002388  mov     rbx, [rsp+30h+arg_10]
0x18000238d  not     rax
0x180002390  mov     cs:__security_cookie_complement, rax
0x180002397  add     rsp, 30h
0x18000239b  pop     rbp
0x18000239c  retn
```
