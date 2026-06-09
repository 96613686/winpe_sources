# __security_init_cookie

- ea: `0x180032498`
- end: `0x18003254d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180031910`

## callees

- `0x180032498`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800324db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800324db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800324e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800324e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800324cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800324cd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800324f7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800324f7`

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
0x180032498  mov     [rsp-8+arg_10], rbx
0x18003249d  push    rbp
0x18003249e  mov     rbp, rsp
0x1800324a1  sub     rsp, 30h
0x1800324a5  mov     rax, cs:__security_cookie
0x1800324ac  mov     rbx, 2B992DDFA232h
0x1800324b6  cmp     rax, rbx
0x1800324b9  jnz     short loc_180032538
0x1800324bb  xor     eax, eax
0x1800324bd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800324c1  mov     [rbp+var_10], rax
0x1800324c5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800324c9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800324cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800324d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800324d7  mov     [rbp+var_10], rax
0x1800324db  call    cs:__imp_GetCurrentThreadId
0x1800324e1  mov     eax, eax
0x1800324e3  xor     [rbp+var_10], rax
0x1800324e7  call    cs:__imp_GetCurrentProcessId
0x1800324ed  mov     eax, eax
0x1800324ef  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800324f3  xor     [rbp+var_10], rax
0x1800324f7  call    cs:__imp_QueryPerformanceCounter
0x1800324fd  mov     eax, dword ptr [rbp+PerformanceCount]
0x180032500  lea     rcx, [rbp+var_10]
0x180032504  shl     rax, 20h
0x180032508  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003250c  xor     rax, [rbp+var_10]
0x180032510  xor     rax, rcx
0x180032513  mov     rcx, 0FFFFFFFFFFFFh
0x18003251d  and     rax, rcx
0x180032520  mov     rcx, 2B992DDFA233h
0x18003252a  cmp     rax, rbx
0x18003252d  cmovz   rax, rcx
0x180032531  mov     cs:__security_cookie, rax
0x180032538  mov     rbx, [rsp+30h+arg_10]
0x18003253d  not     rax
0x180032540  mov     cs:__security_cookie_complement, rax
0x180032547  add     rsp, 30h
0x18003254b  pop     rbp
0x18003254c  retn
```
