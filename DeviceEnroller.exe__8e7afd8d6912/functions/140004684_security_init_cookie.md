# __security_init_cookie

- ea: `0x140004684`
- end: `0x140004739`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400042c0`

## callees

- `0x140004684`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400046d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400046d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400046c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400046c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400046b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400046b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400046e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400046e3`

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
0x140004684  mov     [rsp-8+arg_10], rbx
0x140004689  push    rbp
0x14000468a  mov     rbp, rsp
0x14000468d  sub     rsp, 30h
0x140004691  mov     rax, cs:__security_cookie
0x140004698  mov     rbx, 2B992DDFA232h
0x1400046a2  cmp     rax, rbx
0x1400046a5  jnz     short loc_140004724
0x1400046a7  xor     eax, eax
0x1400046a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400046ad  mov     [rbp+var_10], rax
0x1400046b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400046b5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400046b9  call    cs:__imp_GetSystemTimeAsFileTime
0x1400046bf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400046c3  mov     [rbp+var_10], rax
0x1400046c7  call    cs:__imp_GetCurrentThreadId
0x1400046cd  mov     eax, eax
0x1400046cf  xor     [rbp+var_10], rax
0x1400046d3  call    cs:__imp_GetCurrentProcessId
0x1400046d9  mov     eax, eax
0x1400046db  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400046df  xor     [rbp+var_10], rax
0x1400046e3  call    cs:__imp_QueryPerformanceCounter
0x1400046e9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400046ec  lea     rcx, [rbp+var_10]
0x1400046f0  shl     rax, 20h
0x1400046f4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400046f8  xor     rax, [rbp+var_10]
0x1400046fc  xor     rax, rcx
0x1400046ff  mov     rcx, 0FFFFFFFFFFFFh
0x140004709  and     rax, rcx
0x14000470c  mov     rcx, 2B992DDFA233h
0x140004716  cmp     rax, rbx
0x140004719  cmovz   rax, rcx
0x14000471d  mov     cs:__security_cookie, rax
0x140004724  mov     rbx, [rsp+30h+arg_10]
0x140004729  not     rax
0x14000472c  mov     cs:__security_cookie_complement, rax
0x140004733  add     rsp, 30h
0x140004737  pop     rbp
0x140004738  retn
```
