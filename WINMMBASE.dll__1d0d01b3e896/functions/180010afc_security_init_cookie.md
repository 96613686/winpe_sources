# __security_init_cookie

- ea: `0x180010afc`
- end: `0x180010bb1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180010670`

## callees

- `0x180010afc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180010b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010b3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010b31`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010b31`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010b5b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180010b5b`

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
0x180010afc  mov     [rsp-8+arg_10], rbx
0x180010b01  push    rbp
0x180010b02  mov     rbp, rsp
0x180010b05  sub     rsp, 30h
0x180010b09  mov     rax, cs:__security_cookie
0x180010b10  mov     rbx, 2B992DDFA232h
0x180010b1a  cmp     rax, rbx
0x180010b1d  jnz     short loc_180010B9C
0x180010b1f  xor     eax, eax
0x180010b21  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010b25  mov     [rbp+var_10], rax
0x180010b29  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180010b2d  mov     qword ptr [rbp+PerformanceCount], rax
0x180010b31  call    cs:__imp_GetSystemTimeAsFileTime
0x180010b37  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180010b3b  mov     [rbp+var_10], rax
0x180010b3f  call    cs:__imp_GetCurrentThreadId
0x180010b45  mov     eax, eax
0x180010b47  xor     [rbp+var_10], rax
0x180010b4b  call    cs:__imp_GetCurrentProcessId
0x180010b51  mov     eax, eax
0x180010b53  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180010b57  xor     [rbp+var_10], rax
0x180010b5b  call    cs:__imp_QueryPerformanceCounter
0x180010b61  mov     eax, dword ptr [rbp+PerformanceCount]
0x180010b64  lea     rcx, [rbp+var_10]
0x180010b68  shl     rax, 20h
0x180010b6c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180010b70  xor     rax, [rbp+var_10]
0x180010b74  xor     rax, rcx
0x180010b77  mov     rcx, 0FFFFFFFFFFFFh
0x180010b81  and     rax, rcx
0x180010b84  mov     rcx, 2B992DDFA233h
0x180010b8e  cmp     rax, rbx
0x180010b91  cmovz   rax, rcx
0x180010b95  mov     cs:__security_cookie, rax
0x180010b9c  mov     rbx, [rsp+30h+arg_10]
0x180010ba1  not     rax
0x180010ba4  mov     cs:__security_cookie_complement, rax
0x180010bab  add     rsp, 30h
0x180010baf  pop     rbp
0x180010bb0  retn
```
