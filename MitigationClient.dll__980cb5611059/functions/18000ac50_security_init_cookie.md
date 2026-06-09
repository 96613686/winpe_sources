# __security_init_cookie

- ea: `0x18000ac50`
- end: `0x18000ad05`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a690`

## callees

- `0x18000ac50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ac9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ac9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ac93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ac85`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ac85`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000acaf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000acaf`

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
0x18000ac50  mov     [rsp-8+arg_10], rbx
0x18000ac55  push    rbp
0x18000ac56  mov     rbp, rsp
0x18000ac59  sub     rsp, 30h
0x18000ac5d  mov     rax, cs:__security_cookie
0x18000ac64  mov     rbx, 2B992DDFA232h
0x18000ac6e  cmp     rax, rbx
0x18000ac71  jnz     short loc_18000ACF0
0x18000ac73  xor     eax, eax
0x18000ac75  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ac79  mov     [rbp+var_10], rax
0x18000ac7d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000ac81  mov     qword ptr [rbp+PerformanceCount], rax
0x18000ac85  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ac8b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000ac8f  mov     [rbp+var_10], rax
0x18000ac93  call    cs:__imp_GetCurrentThreadId
0x18000ac99  mov     eax, eax
0x18000ac9b  xor     [rbp+var_10], rax
0x18000ac9f  call    cs:__imp_GetCurrentProcessId
0x18000aca5  mov     eax, eax
0x18000aca7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000acab  xor     [rbp+var_10], rax
0x18000acaf  call    cs:__imp_QueryPerformanceCounter
0x18000acb5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000acb8  lea     rcx, [rbp+var_10]
0x18000acbc  shl     rax, 20h
0x18000acc0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000acc4  xor     rax, [rbp+var_10]
0x18000acc8  xor     rax, rcx
0x18000accb  mov     rcx, 0FFFFFFFFFFFFh
0x18000acd5  and     rax, rcx
0x18000acd8  mov     rcx, 2B992DDFA233h
0x18000ace2  cmp     rax, rbx
0x18000ace5  cmovz   rax, rcx
0x18000ace9  mov     cs:__security_cookie, rax
0x18000acf0  mov     rbx, [rsp+30h+arg_10]
0x18000acf5  not     rax
0x18000acf8  mov     cs:__security_cookie_complement, rax
0x18000acff  add     rsp, 30h
0x18000ad03  pop     rbp
0x18000ad04  retn
```
