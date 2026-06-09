# __security_init_cookie

- ea: `0x180008260`
- end: `0x18000833d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007e10`

## callees

- `0x180008260`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800082a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800082a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800082b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800082b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800082ea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800082ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008299`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180008299`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800082bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800082cf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800082bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800082cf`

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
0x180008260  mov     [rsp-8+arg_18], rbx
0x180008265  push    rbp
0x180008266  mov     rbp, rsp
0x180008269  sub     rsp, 20h
0x18000826d  xor     eax, eax
0x18000826f  mov     rbx, 2B992DDFA232h
0x180008279  mov     [rbp+cookie], rax
0x18000827d  mov     qword ptr [rbp+systime], rax
0x180008281  mov     qword ptr [rbp+perfctr], rax
0x180008285  mov     rax, cs:__security_cookie
0x18000828c  cmp     rax, rbx
0x18000828f  jnz     loc_180008328
0x180008295  lea     rcx, [rbp+systime]; lpSystemTimeAsFileTime
0x180008299  call    cs:__imp_GetSystemTimeAsFileTime
0x18000829f  mov     rax, qword ptr [rbp+systime]
0x1800082a3  mov     [rbp+cookie], rax
0x1800082a7  call    cs:__imp_GetCurrentProcessId
0x1800082ad  mov     eax, eax
0x1800082af  xor     [rbp+cookie], rax
0x1800082b3  call    cs:__imp_GetCurrentThreadId
0x1800082b9  mov     eax, eax
0x1800082bb  xor     [rbp+cookie], rax
0x1800082bf  call    cs:__imp_GetTickCount
0x1800082c5  mov     eax, eax
0x1800082c7  shl     rax, 18h
0x1800082cb  xor     [rbp+cookie], rax
0x1800082cf  call    cs:__imp_GetTickCount
0x1800082d5  mov     eax, eax
0x1800082d7  lea     rcx, [rbp+cookie]
0x1800082db  xor     rax, [rbp+cookie]
0x1800082df  xor     rax, rcx
0x1800082e2  lea     rcx, [rbp+perfctr]; lpPerformanceCount
0x1800082e6  mov     [rbp+cookie], rax
0x1800082ea  call    cs:__imp_QueryPerformanceCounter
0x1800082f0  mov     eax, dword ptr [rbp+perfctr]
0x1800082f3  mov     rcx, 0FFFFFFFFFFFFh
0x1800082fd  shl     rax, 20h
0x180008301  xor     rax, qword ptr [rbp+perfctr]
0x180008305  xor     rax, [rbp+cookie]
0x180008309  and     rax, rcx
0x18000830c  mov     rcx, rax
0x18000830f  cmp     rax, rbx
0x180008312  jnz     short loc_180008321
0x180008314  mov     rax, 2B992DDFA233h
0x18000831e  mov     rcx, rax
0x180008321  mov     cs:__security_cookie, rcx
0x180008328  mov     rbx, [rsp+20h+arg_18]
0x18000832d  not     rax
0x180008330  mov     cs:__security_cookie_complement, rax
0x180008337  add     rsp, 20h
0x18000833b  pop     rbp
0x18000833c  retn
```
