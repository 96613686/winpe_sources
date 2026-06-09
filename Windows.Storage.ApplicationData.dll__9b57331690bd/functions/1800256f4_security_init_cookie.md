# __security_init_cookie

- ea: `0x1800256f4`
- end: `0x1800257d1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025290`

## callees

- `0x1800256f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002573b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002573b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025747`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025747`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002577e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002577e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002572d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002572d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025753`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025763`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025753`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180025763`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  unsigned __int64 cookie; // [rsp+30h] [rbp+10h] BYREF
  _LARGE_INTEGER perfctr; // [rsp+38h] [rbp+18h] BYREF
  FT systime; // [rsp+40h] [rbp+20h] BYREF

  cookie = 0;
  systime.ft_scalar = 0;
  perfctr.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime((LPFILETIME)&systime);
    cookie = systime.ft_scalar;
    cookie ^= GetCurrentProcessId();
    cookie ^= GetCurrentThreadId();
    cookie ^= (unsigned __int64)GetTickCount() << 24;
    cookie ^= (unsigned __int64)&cookie ^ GetTickCount();
    QueryPerformanceCounter(&perfctr);
    v0 = (cookie ^ perfctr.QuadPart ^ ((unsigned __int64)perfctr.LowPart << 32)) & 0xFFFFFFFFFFFFLL;
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
0x1800256f4  mov     [rsp-8+arg_18], rbx
0x1800256f9  push    rbp
0x1800256fa  mov     rbp, rsp
0x1800256fd  sub     rsp, 20h
0x180025701  xor     eax, eax
0x180025703  mov     rbx, 2B992DDFA232h
0x18002570d  mov     [rbp+cookie], rax
0x180025711  mov     qword ptr [rbp+systime], rax
0x180025715  mov     qword ptr [rbp+perfctr], rax
0x180025719  mov     rax, cs:__security_cookie
0x180025720  cmp     rax, rbx
0x180025723  jnz     loc_1800257BC
0x180025729  lea     rcx, [rbp+systime]; lpSystemTimeAsFileTime
0x18002572d  call    cs:__imp_GetSystemTimeAsFileTime
0x180025733  mov     rax, qword ptr [rbp+systime]
0x180025737  mov     [rbp+cookie], rax
0x18002573b  call    cs:__imp_GetCurrentProcessId
0x180025741  mov     eax, eax
0x180025743  xor     [rbp+cookie], rax
0x180025747  call    cs:__imp_GetCurrentThreadId
0x18002574d  mov     eax, eax
0x18002574f  xor     [rbp+cookie], rax
0x180025753  call    cs:__imp_GetTickCount
0x180025759  mov     eax, eax
0x18002575b  shl     rax, 18h
0x18002575f  xor     [rbp+cookie], rax
0x180025763  call    cs:__imp_GetTickCount
0x180025769  mov     eax, eax
0x18002576b  lea     rcx, [rbp+cookie]
0x18002576f  xor     rax, [rbp+cookie]
0x180025773  xor     rax, rcx
0x180025776  lea     rcx, [rbp+perfctr]; lpPerformanceCount
0x18002577a  mov     [rbp+cookie], rax
0x18002577e  call    cs:__imp_QueryPerformanceCounter
0x180025784  mov     eax, dword ptr [rbp+perfctr]
0x180025787  mov     rcx, 0FFFFFFFFFFFFh
0x180025791  shl     rax, 20h
0x180025795  xor     rax, qword ptr [rbp+perfctr]
0x180025799  xor     rax, [rbp+cookie]
0x18002579d  and     rax, rcx
0x1800257a0  mov     rcx, rax
0x1800257a3  cmp     rax, rbx
0x1800257a6  jnz     short loc_1800257B5
0x1800257a8  mov     rax, 2B992DDFA233h
0x1800257b2  mov     rcx, rax
0x1800257b5  mov     cs:__security_cookie, rcx
0x1800257bc  mov     rbx, [rsp+20h+arg_18]
0x1800257c1  not     rax
0x1800257c4  mov     cs:__security_cookie_complement, rax
0x1800257cb  add     rsp, 20h
0x1800257cf  pop     rbp
0x1800257d0  retn
```
