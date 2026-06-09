# __security_init_cookie

- ea: `0x18009da7c`
- end: `0x18009db31`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009d620`

## callees

- `0x18009da7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009dabf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009dabf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009dacb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18009dacb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009dadb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18009dadb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009dab1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18009dab1`

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
0x18009da7c  mov     [rsp-8+arg_10], rbx
0x18009da81  push    rbp
0x18009da82  mov     rbp, rsp
0x18009da85  sub     rsp, 30h
0x18009da89  mov     rax, cs:__security_cookie
0x18009da90  mov     rbx, 2B992DDFA232h
0x18009da9a  cmp     rax, rbx
0x18009da9d  jnz     short loc_18009DB1C
0x18009da9f  xor     eax, eax
0x18009daa1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18009daa5  mov     [rbp+var_10], rax
0x18009daa9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18009daad  mov     qword ptr [rbp+PerformanceCount], rax
0x18009dab1  call    cs:__imp_GetSystemTimeAsFileTime
0x18009dab7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18009dabb  mov     [rbp+var_10], rax
0x18009dabf  call    cs:__imp_GetCurrentThreadId
0x18009dac5  mov     eax, eax
0x18009dac7  xor     [rbp+var_10], rax
0x18009dacb  call    cs:__imp_GetCurrentProcessId
0x18009dad1  mov     eax, eax
0x18009dad3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18009dad7  xor     [rbp+var_10], rax
0x18009dadb  call    cs:__imp_QueryPerformanceCounter
0x18009dae1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18009dae4  lea     rcx, [rbp+var_10]
0x18009dae8  shl     rax, 20h
0x18009daec  xor     rax, qword ptr [rbp+PerformanceCount]
0x18009daf0  xor     rax, [rbp+var_10]
0x18009daf4  xor     rax, rcx
0x18009daf7  mov     rcx, 0FFFFFFFFFFFFh
0x18009db01  and     rax, rcx
0x18009db04  mov     rcx, 2B992DDFA233h
0x18009db0e  cmp     rax, rbx
0x18009db11  cmovz   rax, rcx
0x18009db15  mov     cs:__security_cookie, rax
0x18009db1c  mov     rbx, [rsp+30h+arg_10]
0x18009db21  not     rax
0x18009db24  mov     cs:__security_cookie_complement, rax
0x18009db2b  add     rsp, 30h
0x18009db2f  pop     rbp
0x18009db30  retn
```
