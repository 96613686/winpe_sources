# __security_init_cookie

- ea: `0x180001704`
- end: `0x1800017b9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001650`

## callees

- `0x180001704`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001763`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001763`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001753`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001753`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001747`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001739`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001739`

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
0x180001704  mov     [rsp-8+arg_10], rbx
0x180001709  push    rbp
0x18000170a  mov     rbp, rsp
0x18000170d  sub     rsp, 30h
0x180001711  mov     rax, cs:__security_cookie
0x180001718  mov     rbx, 2B992DDFA232h
0x180001722  cmp     rax, rbx
0x180001725  jnz     short loc_1800017A4
0x180001727  xor     eax, eax
0x180001729  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000172d  mov     [rbp+var_10], rax
0x180001731  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001735  mov     qword ptr [rbp+PerformanceCount], rax
0x180001739  call    cs:__imp_GetSystemTimeAsFileTime
0x18000173f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001743  mov     [rbp+var_10], rax
0x180001747  call    cs:__imp_GetCurrentThreadId
0x18000174d  mov     eax, eax
0x18000174f  xor     [rbp+var_10], rax
0x180001753  call    cs:__imp_GetCurrentProcessId
0x180001759  mov     eax, eax
0x18000175b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000175f  xor     [rbp+var_10], rax
0x180001763  call    cs:__imp_QueryPerformanceCounter
0x180001769  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000176c  lea     rcx, [rbp+var_10]
0x180001770  shl     rax, 20h
0x180001774  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001778  xor     rax, [rbp+var_10]
0x18000177c  xor     rax, rcx
0x18000177f  mov     rcx, 0FFFFFFFFFFFFh
0x180001789  and     rax, rcx
0x18000178c  mov     rcx, 2B992DDFA233h
0x180001796  cmp     rax, rbx
0x180001799  cmovz   rax, rcx
0x18000179d  mov     cs:__security_cookie, rax
0x1800017a4  mov     rbx, [rsp+30h+arg_10]
0x1800017a9  not     rax
0x1800017ac  mov     cs:__security_cookie_complement, rax
0x1800017b3  add     rsp, 30h
0x1800017b7  pop     rbp
0x1800017b8  retn
```
