# __security_init_cookie

- ea: `0x140005274`
- end: `0x140005329`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140004840`

## callees

- `0x140005274`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400052b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400052b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400052c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400052c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400052d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400052d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400052a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400052a9`

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
0x140005274  mov     [rsp-8+arg_10], rbx
0x140005279  push    rbp
0x14000527a  mov     rbp, rsp
0x14000527d  sub     rsp, 30h
0x140005281  mov     rax, cs:__security_cookie
0x140005288  mov     rbx, 2B992DDFA232h
0x140005292  cmp     rax, rbx
0x140005295  jnz     short loc_140005314
0x140005297  xor     eax, eax
0x140005299  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000529d  mov     [rbp+var_10], rax
0x1400052a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400052a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400052a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1400052af  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400052b3  mov     [rbp+var_10], rax
0x1400052b7  call    cs:__imp_GetCurrentThreadId
0x1400052bd  mov     eax, eax
0x1400052bf  xor     [rbp+var_10], rax
0x1400052c3  call    cs:__imp_GetCurrentProcessId
0x1400052c9  mov     eax, eax
0x1400052cb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400052cf  xor     [rbp+var_10], rax
0x1400052d3  call    cs:__imp_QueryPerformanceCounter
0x1400052d9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400052dc  lea     rcx, [rbp+var_10]
0x1400052e0  shl     rax, 20h
0x1400052e4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400052e8  xor     rax, [rbp+var_10]
0x1400052ec  xor     rax, rcx
0x1400052ef  mov     rcx, 0FFFFFFFFFFFFh
0x1400052f9  and     rax, rcx
0x1400052fc  mov     rcx, 2B992DDFA233h
0x140005306  cmp     rax, rbx
0x140005309  cmovz   rax, rcx
0x14000530d  mov     cs:__security_cookie, rax
0x140005314  mov     rbx, [rsp+30h+arg_10]
0x140005319  not     rax
0x14000531c  mov     cs:__security_cookie_complement, rax
0x140005323  add     rsp, 30h
0x140005327  pop     rbp
0x140005328  retn
```
