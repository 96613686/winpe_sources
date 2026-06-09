# __security_init_cookie

- ea: `0x180120688`
- end: `0x18012073d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180120150`

## callees

- `0x180120688`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801206cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801206cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801206d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801206d7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801206e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801206e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801206bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801206bd`

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
0x180120688  mov     [rsp-8+arg_10], rbx
0x18012068d  push    rbp
0x18012068e  mov     rbp, rsp
0x180120691  sub     rsp, 30h
0x180120695  mov     rax, cs:__security_cookie
0x18012069c  mov     rbx, 2B992DDFA232h
0x1801206a6  cmp     rax, rbx
0x1801206a9  jnz     short loc_180120728
0x1801206ab  xor     eax, eax
0x1801206ad  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801206b1  mov     [rbp+var_10], rax
0x1801206b5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1801206b9  mov     qword ptr [rbp+PerformanceCount], rax
0x1801206bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1801206c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1801206c7  mov     [rbp+var_10], rax
0x1801206cb  call    cs:__imp_GetCurrentThreadId
0x1801206d1  mov     eax, eax
0x1801206d3  xor     [rbp+var_10], rax
0x1801206d7  call    cs:__imp_GetCurrentProcessId
0x1801206dd  mov     eax, eax
0x1801206df  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1801206e3  xor     [rbp+var_10], rax
0x1801206e7  call    cs:__imp_QueryPerformanceCounter
0x1801206ed  mov     eax, dword ptr [rbp+PerformanceCount]
0x1801206f0  lea     rcx, [rbp+var_10]
0x1801206f4  shl     rax, 20h
0x1801206f8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801206fc  xor     rax, [rbp+var_10]
0x180120700  xor     rax, rcx
0x180120703  mov     rcx, 0FFFFFFFFFFFFh
0x18012070d  and     rax, rcx
0x180120710  mov     rcx, 2B992DDFA233h
0x18012071a  cmp     rax, rbx
0x18012071d  cmovz   rax, rcx
0x180120721  mov     cs:__security_cookie, rax
0x180120728  mov     rbx, [rsp+30h+arg_10]
0x18012072d  not     rax
0x180120730  mov     cs:__security_cookie_complement, rax
0x180120737  add     rsp, 30h
0x18012073b  pop     rbp
0x18012073c  retn
```
