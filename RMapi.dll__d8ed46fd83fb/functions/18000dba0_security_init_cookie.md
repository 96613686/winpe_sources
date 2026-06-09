# __security_init_cookie

- ea: `0x18000dba0`
- end: `0x18000dc55`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d250`

## callees

- `0x18000dba0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dbe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dbe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dbef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000dbef`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000dbd5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000dbd5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000dbff`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000dbff`

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
0x18000dba0  mov     [rsp-8+arg_10], rbx
0x18000dba5  push    rbp
0x18000dba6  mov     rbp, rsp
0x18000dba9  sub     rsp, 30h
0x18000dbad  mov     rax, cs:__security_cookie
0x18000dbb4  mov     rbx, 2B992DDFA232h
0x18000dbbe  cmp     rax, rbx
0x18000dbc1  jnz     short loc_18000DC40
0x18000dbc3  xor     eax, eax
0x18000dbc5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000dbc9  mov     [rbp+var_10], rax
0x18000dbcd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000dbd1  mov     qword ptr [rbp+PerformanceCount], rax
0x18000dbd5  call    cs:__imp_GetSystemTimeAsFileTime
0x18000dbdb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000dbdf  mov     [rbp+var_10], rax
0x18000dbe3  call    cs:__imp_GetCurrentThreadId
0x18000dbe9  mov     eax, eax
0x18000dbeb  xor     [rbp+var_10], rax
0x18000dbef  call    cs:__imp_GetCurrentProcessId
0x18000dbf5  mov     eax, eax
0x18000dbf7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000dbfb  xor     [rbp+var_10], rax
0x18000dbff  call    cs:__imp_QueryPerformanceCounter
0x18000dc05  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000dc08  lea     rcx, [rbp+var_10]
0x18000dc0c  shl     rax, 20h
0x18000dc10  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000dc14  xor     rax, [rbp+var_10]
0x18000dc18  xor     rax, rcx
0x18000dc1b  mov     rcx, 0FFFFFFFFFFFFh
0x18000dc25  and     rax, rcx
0x18000dc28  mov     rcx, 2B992DDFA233h
0x18000dc32  cmp     rax, rbx
0x18000dc35  cmovz   rax, rcx
0x18000dc39  mov     cs:__security_cookie, rax
0x18000dc40  mov     rbx, [rsp+30h+arg_10]
0x18000dc45  not     rax
0x18000dc48  mov     cs:__security_cookie_complement, rax
0x18000dc4f  add     rsp, 30h
0x18000dc53  pop     rbp
0x18000dc54  retn
```
