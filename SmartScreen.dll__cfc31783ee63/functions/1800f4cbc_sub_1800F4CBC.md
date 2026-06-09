# sub_1800F4CBC

- ea: `0x1800f4cbc`
- end: `0x1800f4d6b`
- name: `sub_1800F4CBC`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f45d0`

## callees

- `0x1800f4cbc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f4d05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f4d05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f4cf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f4cf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f4ceb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f4ceb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f4d15`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f4d15`

## pseudocode

```c
__int64 sub_1800F4CBC()
{
  uintptr_t v0; // rax
  __int64 result; // rax
  struct _FILETIME v2; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v2
        ^ *(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  result = ~v0;
  qword_1802190C0 = result;
  return result;
}

```

## disassembly

```asm
0x1800f4cbc  mov     [rsp-8+arg_10], rbx
0x1800f4cc1  push    rbp
0x1800f4cc2  mov     rbp, rsp
0x1800f4cc5  sub     rsp, 30h
0x1800f4cc9  mov     rax, cs:__security_cookie
0x1800f4cd0  mov     rbx, 2B992DDFA232h
0x1800f4cda  cmp     rax, rbx
0x1800f4cdd  jnz     short loc_1800F4D56
0x1800f4cdf  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800f4ce3  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800f4ceb  call    cs:GetSystemTimeAsFileTime
0x1800f4cf1  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800f4cf5  mov     [rbp+var_10], rax
0x1800f4cf9  call    cs:__imp_GetCurrentThreadId
0x1800f4cff  mov     eax, eax
0x1800f4d01  xor     [rbp+var_10], rax
0x1800f4d05  call    cs:GetCurrentProcessId
0x1800f4d0b  mov     eax, eax
0x1800f4d0d  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800f4d11  xor     [rbp+var_10], rax
0x1800f4d15  call    cs:QueryPerformanceCounter
0x1800f4d1b  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800f4d1e  lea     rcx, [rbp+var_10]
0x1800f4d22  shl     rax, 20h
0x1800f4d26  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800f4d2a  xor     rax, [rbp+var_10]
0x1800f4d2e  xor     rax, rcx
0x1800f4d31  mov     rcx, 0FFFFFFFFFFFFh
0x1800f4d3b  and     rax, rcx
0x1800f4d3e  mov     rcx, 2B992DDFA233h
0x1800f4d48  cmp     rax, rbx
0x1800f4d4b  cmovz   rax, rcx
0x1800f4d4f  mov     cs:__security_cookie, rax
0x1800f4d56  mov     rbx, [rsp+30h+arg_10]
0x1800f4d5b  not     rax
0x1800f4d5e  mov     cs:qword_1802190C0, rax
0x1800f4d65  add     rsp, 30h
0x1800f4d69  pop     rbp
0x1800f4d6a  retn
```
