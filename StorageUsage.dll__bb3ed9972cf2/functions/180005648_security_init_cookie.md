# __security_init_cookie

- ea: `0x180005648`
- end: `0x1800056fd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800050a0`

## callees

- `0x180005648`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000567d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000567d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000568b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000568b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005697`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800056a7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800056a7`

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
0x180005648  mov     [rsp-8+arg_10], rbx
0x18000564d  push    rbp
0x18000564e  mov     rbp, rsp
0x180005651  sub     rsp, 30h
0x180005655  mov     rax, cs:__security_cookie
0x18000565c  mov     rbx, 2B992DDFA232h
0x180005666  cmp     rax, rbx
0x180005669  jnz     short loc_1800056E8
0x18000566b  xor     eax, eax
0x18000566d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005671  mov     [rbp+var_10], rax
0x180005675  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005679  mov     qword ptr [rbp+PerformanceCount], rax
0x18000567d  call    cs:__imp_GetSystemTimeAsFileTime
0x180005683  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005687  mov     [rbp+var_10], rax
0x18000568b  call    cs:__imp_GetCurrentThreadId
0x180005691  mov     eax, eax
0x180005693  xor     [rbp+var_10], rax
0x180005697  call    cs:__imp_GetCurrentProcessId
0x18000569d  mov     eax, eax
0x18000569f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800056a3  xor     [rbp+var_10], rax
0x1800056a7  call    cs:__imp_QueryPerformanceCounter
0x1800056ad  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800056b0  lea     rcx, [rbp+var_10]
0x1800056b4  shl     rax, 20h
0x1800056b8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800056bc  xor     rax, [rbp+var_10]
0x1800056c0  xor     rax, rcx
0x1800056c3  mov     rcx, 0FFFFFFFFFFFFh
0x1800056cd  and     rax, rcx
0x1800056d0  mov     rcx, 2B992DDFA233h
0x1800056da  cmp     rax, rbx
0x1800056dd  cmovz   rax, rcx
0x1800056e1  mov     cs:__security_cookie, rax
0x1800056e8  mov     rbx, [rsp+30h+arg_10]
0x1800056ed  not     rax
0x1800056f0  mov     cs:__security_cookie_complement, rax
0x1800056f7  add     rsp, 30h
0x1800056fb  pop     rbp
0x1800056fc  retn
```
