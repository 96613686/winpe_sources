# GetCurrentUserToken(void * *)

- ea: `0x18000f5a0`
- end: `0x18000f685`
- name: `?GetCurrentUserToken@@YAJPEAPEAX@Z`
- size: `229`
- prototype: `__int64 __fastcall(PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800226b0`

## callees

- `0x18000f5a0`
- `0x1800202bc`
- `0x1800238d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f5b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000f5b7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f606`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000f606`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f5ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000f5ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000f5f5`

## string_xrefs

- `0x18000f622`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`
- `0x18000f642`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`
- `0x18000f66d`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`

## pseudocode

```c
__int64 __fastcall GetCurrentUserToken(PHANDLE TokenHandle)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v4; // edi
  HANDLE CurrentProcess; // rax
  const char *v6; // r9
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !TokenHandle )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
      (const char *)0x80070057LL,
      v8);
    return 2147942487LL;
  }
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 != -2147023888 && (v4 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
        (const char *)v4,
        v8);
      return v4;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x25,
               (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
               v6);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f5a0  push    rbx; int
0x18000f5a2  sub     rsp, 20h
0x18000f5a6  mov     rbx, rcx
0x18000f5a9  test    rcx, rcx
0x18000f5ac  jz      loc_18000F63D
0x18000f5b2  mov     [rsp+28h+arg_0], rdi
0x18000f5b7  call    cs:__imp_GetCurrentThread
0x18000f5bd  mov     r9, rbx; TokenHandle
0x18000f5c0  mov     edx, 8; DesiredAccess
0x18000f5c5  mov     rcx, rax; ThreadHandle
0x18000f5c8  mov     r8d, 1; OpenAsSelf
0x18000f5ce  call    cs:__imp_OpenThreadToken
0x18000f5d4  test    eax, eax
0x18000f5d6  jnz     short loc_18000F610
0x18000f5d8  call    cs:__imp_GetLastError
0x18000f5de  mov     edi, eax
0x18000f5e0  test    eax, eax
0x18000f5e2  jle     short loc_18000F5ED
0x18000f5e4  movzx   edi, ax
0x18000f5e7  or      edi, 80070000h
0x18000f5ed  cmp     edi, 800703F0h
0x18000f5f3  jnz     short loc_18000F664
0x18000f5f5  call    cs:__imp_GetCurrentProcess
0x18000f5fb  mov     r8, rbx; TokenHandle
0x18000f5fe  mov     edx, 8; DesiredAccess
0x18000f603  mov     rcx, rax; ProcessHandle
0x18000f606  call    cs:__imp_OpenProcessToken
0x18000f60c  test    eax, eax
0x18000f60e  jz      short loc_18000F61D
0x18000f610  xor     eax, eax
0x18000f612  mov     rdi, [rsp+28h+arg_0]
0x18000f617  add     rsp, 20h
0x18000f61b  pop     rbx
0x18000f61c  retn
0x18000f61d  mov     rcx, [rsp+28h]; this
0x18000f622  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000f629  mov     edx, 25h ; '%'; void *
0x18000f62e  mov     rdi, [rsp+28h+arg_0]
0x18000f633  add     rsp, 20h
0x18000f637  pop     rbx
0x18000f638  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f63d  mov     rcx, [rsp+28h]; this
0x18000f642  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000f649  mov     r9d, 80070057h; char *
0x18000f64f  mov     edx, 12h; void *
0x18000f654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f659  mov     eax, 80070057h
0x18000f65e  add     rsp, 20h
0x18000f662  pop     rbx
0x18000f663  retn
0x18000f664  test    edi, edi
0x18000f666  jns     short loc_18000F5F5
0x18000f668  mov     rcx, [rsp+28h]; this
0x18000f66d  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000f674  mov     r9d, edi; char *
0x18000f677  mov     edx, 1Fh; void *
0x18000f67c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f681  mov     eax, edi
0x18000f683  jmp     short loc_18000F612
```
