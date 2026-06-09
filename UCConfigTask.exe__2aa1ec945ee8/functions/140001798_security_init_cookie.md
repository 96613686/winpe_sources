# __security_init_cookie

- ea: `0x140001798`
- end: `0x14000184d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001490`

## callees

- `0x140001798`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400017db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400017db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400017e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400017e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017f7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017cd`

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
0x140001798  mov     [rsp-8+arg_10], rbx
0x14000179d  push    rbp
0x14000179e  mov     rbp, rsp
0x1400017a1  sub     rsp, 30h
0x1400017a5  mov     rax, cs:__security_cookie
0x1400017ac  mov     rbx, 2B992DDFA232h
0x1400017b6  cmp     rax, rbx
0x1400017b9  jnz     short loc_140001838
0x1400017bb  xor     eax, eax
0x1400017bd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400017c1  mov     [rbp+var_10], rax
0x1400017c5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400017c9  mov     qword ptr [rbp+PerformanceCount], rax
0x1400017cd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400017d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400017d7  mov     [rbp+var_10], rax
0x1400017db  call    cs:__imp_GetCurrentThreadId
0x1400017e1  mov     eax, eax
0x1400017e3  xor     [rbp+var_10], rax
0x1400017e7  call    cs:__imp_GetCurrentProcessId
0x1400017ed  mov     eax, eax
0x1400017ef  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400017f3  xor     [rbp+var_10], rax
0x1400017f7  call    cs:__imp_QueryPerformanceCounter
0x1400017fd  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001800  lea     rcx, [rbp+var_10]
0x140001804  shl     rax, 20h
0x140001808  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000180c  xor     rax, [rbp+var_10]
0x140001810  xor     rax, rcx
0x140001813  mov     rcx, 0FFFFFFFFFFFFh
0x14000181d  and     rax, rcx
0x140001820  mov     rcx, 2B992DDFA233h
0x14000182a  cmp     rax, rbx
0x14000182d  cmovz   rax, rcx
0x140001831  mov     cs:__security_cookie, rax
0x140001838  mov     rbx, [rsp+30h+arg_10]
0x14000183d  not     rax
0x140001840  mov     cs:__security_cookie_complement, rax
0x140001847  add     rsp, 30h
0x14000184b  pop     rbp
0x14000184c  retn
```
