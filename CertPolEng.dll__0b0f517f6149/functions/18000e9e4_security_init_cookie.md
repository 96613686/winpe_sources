# __security_init_cookie

- ea: `0x18000e9e4`
- end: `0x18000eac1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e2f0`

## callees

- `0x18000e9e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ea37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ea2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ea2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ea43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ea53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ea43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ea53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ea1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ea1d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ea6e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ea6e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x18000e9e4  mov     [rsp-8+arg_18], rbx
0x18000e9e9  push    rbp
0x18000e9ea  mov     rbp, rsp
0x18000e9ed  sub     rsp, 20h
0x18000e9f1  xor     eax, eax
0x18000e9f3  mov     rbx, 2B992DDFA232h
0x18000e9fd  mov     [rbp+arg_0], rax
0x18000ea01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000ea05  mov     qword ptr [rbp+PerformanceCount], rax
0x18000ea09  mov     rax, cs:__security_cookie
0x18000ea10  cmp     rax, rbx
0x18000ea13  jnz     loc_18000EAAC
0x18000ea19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ea1d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ea23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000ea27  mov     [rbp+arg_0], rax
0x18000ea2b  call    cs:__imp_GetCurrentProcessId
0x18000ea31  mov     eax, eax
0x18000ea33  xor     [rbp+arg_0], rax
0x18000ea37  call    cs:__imp_GetCurrentThreadId
0x18000ea3d  mov     eax, eax
0x18000ea3f  xor     [rbp+arg_0], rax
0x18000ea43  call    cs:__imp_GetTickCount
0x18000ea49  mov     eax, eax
0x18000ea4b  shl     rax, 18h
0x18000ea4f  xor     [rbp+arg_0], rax
0x18000ea53  call    cs:__imp_GetTickCount
0x18000ea59  mov     eax, eax
0x18000ea5b  lea     rcx, [rbp+arg_0]
0x18000ea5f  xor     rax, [rbp+arg_0]
0x18000ea63  xor     rax, rcx
0x18000ea66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000ea6a  mov     [rbp+arg_0], rax
0x18000ea6e  call    cs:__imp_QueryPerformanceCounter
0x18000ea74  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000ea77  mov     rcx, 0FFFFFFFFFFFFh
0x18000ea81  shl     rax, 20h
0x18000ea85  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000ea89  xor     rax, [rbp+arg_0]
0x18000ea8d  and     rax, rcx
0x18000ea90  mov     rcx, rax
0x18000ea93  cmp     rax, rbx
0x18000ea96  jnz     short loc_18000EAA5
0x18000ea98  mov     rax, 2B992DDFA233h
0x18000eaa2  mov     rcx, rax
0x18000eaa5  mov     cs:__security_cookie, rcx
0x18000eaac  mov     rbx, [rsp+20h+arg_18]
0x18000eab1  not     rax
0x18000eab4  mov     cs:__security_cookie_complement, rax
0x18000eabb  add     rsp, 20h
0x18000eabf  pop     rbp
0x18000eac0  retn
```
