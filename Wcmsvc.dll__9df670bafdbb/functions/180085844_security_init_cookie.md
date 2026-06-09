# __security_init_cookie

- ea: `0x180085844`
- end: `0x1800858f9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180084ef0`

## callees

- `0x180085844`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180085887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180085893`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180085893`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180085879`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180085879`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800858a3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800858a3`

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
0x180085844  mov     [rsp-8+arg_10], rbx
0x180085849  push    rbp
0x18008584a  mov     rbp, rsp
0x18008584d  sub     rsp, 30h
0x180085851  mov     rax, cs:__security_cookie
0x180085858  mov     rbx, 2B992DDFA232h
0x180085862  cmp     rax, rbx
0x180085865  jnz     short loc_1800858E4
0x180085867  xor     eax, eax
0x180085869  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18008586d  mov     [rbp+var_10], rax
0x180085871  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180085875  mov     qword ptr [rbp+PerformanceCount], rax
0x180085879  call    cs:__imp_GetSystemTimeAsFileTime
0x18008587f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180085883  mov     [rbp+var_10], rax
0x180085887  call    cs:__imp_GetCurrentThreadId
0x18008588d  mov     eax, eax
0x18008588f  xor     [rbp+var_10], rax
0x180085893  call    cs:__imp_GetCurrentProcessId
0x180085899  mov     eax, eax
0x18008589b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18008589f  xor     [rbp+var_10], rax
0x1800858a3  call    cs:__imp_QueryPerformanceCounter
0x1800858a9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800858ac  lea     rcx, [rbp+var_10]
0x1800858b0  shl     rax, 20h
0x1800858b4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800858b8  xor     rax, [rbp+var_10]
0x1800858bc  xor     rax, rcx
0x1800858bf  mov     rcx, 0FFFFFFFFFFFFh
0x1800858c9  and     rax, rcx
0x1800858cc  mov     rcx, 2B992DDFA233h
0x1800858d6  cmp     rax, rbx
0x1800858d9  cmovz   rax, rcx
0x1800858dd  mov     cs:__security_cookie, rax
0x1800858e4  mov     rbx, [rsp+30h+arg_10]
0x1800858e9  not     rax
0x1800858ec  mov     cs:__security_cookie_complement, rax
0x1800858f3  add     rsp, 30h
0x1800858f7  pop     rbp
0x1800858f8  retn
```
