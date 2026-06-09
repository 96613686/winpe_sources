# __security_init_cookie

- ea: `0x18005aeac`
- end: `0x18005af61`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005aa10`

## callees

- `0x18005aeac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005aefb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005aefb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005aeef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005aeef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005af0b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18005af0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005aee1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005aee1`

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
0x18005aeac  mov     [rsp-8+arg_10], rbx
0x18005aeb1  push    rbp
0x18005aeb2  mov     rbp, rsp
0x18005aeb5  sub     rsp, 30h
0x18005aeb9  mov     rax, cs:__security_cookie
0x18005aec0  mov     rbx, 2B992DDFA232h
0x18005aeca  cmp     rax, rbx
0x18005aecd  jnz     short loc_18005AF4C
0x18005aecf  xor     eax, eax
0x18005aed1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005aed5  mov     [rbp+var_10], rax
0x18005aed9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18005aedd  mov     qword ptr [rbp+PerformanceCount], rax
0x18005aee1  call    cs:__imp_GetSystemTimeAsFileTime
0x18005aee7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18005aeeb  mov     [rbp+var_10], rax
0x18005aeef  call    cs:__imp_GetCurrentThreadId
0x18005aef5  mov     eax, eax
0x18005aef7  xor     [rbp+var_10], rax
0x18005aefb  call    cs:__imp_GetCurrentProcessId
0x18005af01  mov     eax, eax
0x18005af03  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005af07  xor     [rbp+var_10], rax
0x18005af0b  call    cs:__imp_QueryPerformanceCounter
0x18005af11  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005af14  lea     rcx, [rbp+var_10]
0x18005af18  shl     rax, 20h
0x18005af1c  xor     rax, qword ptr [rbp+PerformanceCount]
0x18005af20  xor     rax, [rbp+var_10]
0x18005af24  xor     rax, rcx
0x18005af27  mov     rcx, 0FFFFFFFFFFFFh
0x18005af31  and     rax, rcx
0x18005af34  mov     rcx, 2B992DDFA233h
0x18005af3e  cmp     rax, rbx
0x18005af41  cmovz   rax, rcx
0x18005af45  mov     cs:__security_cookie, rax
0x18005af4c  mov     rbx, [rsp+30h+arg_10]
0x18005af51  not     rax
0x18005af54  mov     cs:__security_cookie_complement, rax
0x18005af5b  add     rsp, 30h
0x18005af5f  pop     rbp
0x18005af60  retn
```
