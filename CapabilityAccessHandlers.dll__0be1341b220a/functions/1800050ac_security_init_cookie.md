# __security_init_cookie

- ea: `0x1800050ac`
- end: `0x180005161`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004c20`

## callees

- `0x1800050ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800050fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800050ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000510b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000510b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800050e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800050e1`

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
0x1800050ac  mov     [rsp-8+arg_10], rbx
0x1800050b1  push    rbp
0x1800050b2  mov     rbp, rsp
0x1800050b5  sub     rsp, 30h
0x1800050b9  mov     rax, cs:__security_cookie
0x1800050c0  mov     rbx, 2B992DDFA232h
0x1800050ca  cmp     rax, rbx
0x1800050cd  jnz     short loc_18000514C
0x1800050cf  xor     eax, eax
0x1800050d1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800050d5  mov     [rbp+var_10], rax
0x1800050d9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800050dd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800050e1  call    cs:__imp_GetSystemTimeAsFileTime
0x1800050e7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800050eb  mov     [rbp+var_10], rax
0x1800050ef  call    cs:__imp_GetCurrentThreadId
0x1800050f5  mov     eax, eax
0x1800050f7  xor     [rbp+var_10], rax
0x1800050fb  call    cs:__imp_GetCurrentProcessId
0x180005101  mov     eax, eax
0x180005103  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005107  xor     [rbp+var_10], rax
0x18000510b  call    cs:__imp_QueryPerformanceCounter
0x180005111  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005114  lea     rcx, [rbp+var_10]
0x180005118  shl     rax, 20h
0x18000511c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005120  xor     rax, [rbp+var_10]
0x180005124  xor     rax, rcx
0x180005127  mov     rcx, 0FFFFFFFFFFFFh
0x180005131  and     rax, rcx
0x180005134  mov     rcx, 2B992DDFA233h
0x18000513e  cmp     rax, rbx
0x180005141  cmovz   rax, rcx
0x180005145  mov     cs:__security_cookie, rax
0x18000514c  mov     rbx, [rsp+30h+arg_10]
0x180005151  not     rax
0x180005154  mov     cs:__security_cookie_complement, rax
0x18000515b  add     rsp, 30h
0x18000515f  pop     rbp
0x180005160  retn
```
