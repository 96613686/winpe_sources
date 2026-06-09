# __security_init_cookie

- ea: `0x180061fa8`
- end: `0x18006205d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800612c0`

## callees

- `0x180061fa8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061feb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061feb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061ff7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180061ff7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180061fdd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180061fdd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180062007`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180062007`

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
0x180061fa8  mov     [rsp-8+arg_10], rbx
0x180061fad  push    rbp
0x180061fae  mov     rbp, rsp
0x180061fb1  sub     rsp, 30h
0x180061fb5  mov     rax, cs:__security_cookie
0x180061fbc  mov     rbx, 2B992DDFA232h
0x180061fc6  cmp     rax, rbx
0x180061fc9  jnz     short loc_180062048
0x180061fcb  xor     eax, eax
0x180061fcd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180061fd1  mov     [rbp+var_10], rax
0x180061fd5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180061fd9  mov     qword ptr [rbp+PerformanceCount], rax
0x180061fdd  call    cs:__imp_GetSystemTimeAsFileTime
0x180061fe3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180061fe7  mov     [rbp+var_10], rax
0x180061feb  call    cs:__imp_GetCurrentThreadId
0x180061ff1  mov     eax, eax
0x180061ff3  xor     [rbp+var_10], rax
0x180061ff7  call    cs:__imp_GetCurrentProcessId
0x180061ffd  mov     eax, eax
0x180061fff  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180062003  xor     [rbp+var_10], rax
0x180062007  call    cs:__imp_QueryPerformanceCounter
0x18006200d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180062010  lea     rcx, [rbp+var_10]
0x180062014  shl     rax, 20h
0x180062018  xor     rax, qword ptr [rbp+PerformanceCount]
0x18006201c  xor     rax, [rbp+var_10]
0x180062020  xor     rax, rcx
0x180062023  mov     rcx, 0FFFFFFFFFFFFh
0x18006202d  and     rax, rcx
0x180062030  mov     rcx, 2B992DDFA233h
0x18006203a  cmp     rax, rbx
0x18006203d  cmovz   rax, rcx
0x180062041  mov     cs:__security_cookie, rax
0x180062048  mov     rbx, [rsp+30h+arg_10]
0x18006204d  not     rax
0x180062050  mov     cs:__security_cookie_complement, rax
0x180062057  add     rsp, 30h
0x18006205b  pop     rbp
0x18006205c  retn
```
