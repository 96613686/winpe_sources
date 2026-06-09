# __security_init_cookie

- ea: `0x180016448`
- end: `0x1800164fd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015fd0`

## callees

- `0x180016448`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800164a7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800164a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180016497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001648b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001648b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001647d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001647d`

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
0x180016448  mov     [rsp-8+arg_10], rbx
0x18001644d  push    rbp
0x18001644e  mov     rbp, rsp
0x180016451  sub     rsp, 30h
0x180016455  mov     rax, cs:__security_cookie
0x18001645c  mov     rbx, 2B992DDFA232h
0x180016466  cmp     rax, rbx
0x180016469  jnz     short loc_1800164E8
0x18001646b  xor     eax, eax
0x18001646d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180016471  mov     [rbp+var_10], rax
0x180016475  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180016479  mov     qword ptr [rbp+PerformanceCount], rax
0x18001647d  call    cs:__imp_GetSystemTimeAsFileTime
0x180016483  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180016487  mov     [rbp+var_10], rax
0x18001648b  call    cs:__imp_GetCurrentThreadId
0x180016491  mov     eax, eax
0x180016493  xor     [rbp+var_10], rax
0x180016497  call    cs:__imp_GetCurrentProcessId
0x18001649d  mov     eax, eax
0x18001649f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800164a3  xor     [rbp+var_10], rax
0x1800164a7  call    cs:__imp_QueryPerformanceCounter
0x1800164ad  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800164b0  lea     rcx, [rbp+var_10]
0x1800164b4  shl     rax, 20h
0x1800164b8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800164bc  xor     rax, [rbp+var_10]
0x1800164c0  xor     rax, rcx
0x1800164c3  mov     rcx, 0FFFFFFFFFFFFh
0x1800164cd  and     rax, rcx
0x1800164d0  mov     rcx, 2B992DDFA233h
0x1800164da  cmp     rax, rbx
0x1800164dd  cmovz   rax, rcx
0x1800164e1  mov     cs:__security_cookie, rax
0x1800164e8  mov     rbx, [rsp+30h+arg_10]
0x1800164ed  not     rax
0x1800164f0  mov     cs:__security_cookie_complement, rax
0x1800164f7  add     rsp, 30h
0x1800164fb  pop     rbp
0x1800164fc  retn
```
