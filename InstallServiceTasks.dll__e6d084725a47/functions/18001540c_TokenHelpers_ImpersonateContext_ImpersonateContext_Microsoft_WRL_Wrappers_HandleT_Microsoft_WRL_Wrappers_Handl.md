# TokenHelpers::ImpersonateContext::ImpersonateContext(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x18001540c`
- end: `0x1800154ec`
- name: `??0ImpersonateContext@TokenHelpers@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017b80`
- `0x18001913c`
- `0x180027178`
- `0x180034194`

## callees

- `0x180010150`
- `0x18001540c`
- `0x1800195c8`
- `0x180019624`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001547e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001547e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015474`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180015474`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001545c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001545c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800154ba`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800154ba`

## string_xrefs

- `0x18001544a`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`
- `0x1800154a4`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`
- `0x1800154c9`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall TokenHelpers::ImpersonateContext::ImpersonateContext(__int64 a1, __int64 a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  const char *v6; // r9
  const char *v7; // r9
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  if ( !*(_QWORD *)(a2 + 8) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
      (const char *)0x80070057LL,
      v9);
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, (PHANDLE)(a1 + 8)) )
  {
    LastError = GetLastError();
    v6 = LastError > 0
       ? (const char *)((unsigned __int16)LastError | 0x80070000)
       : (const char *)(unsigned int)LastError;
    if ( LastError != 1008 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16,
        (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
        v6,
        v9);
  }
  if ( !ImpersonateLoggedOnUser(*(HANDLE *)(a2 + 8)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
      v7);
  return a1;
}

```

## disassembly

```asm
0x18001540c  mov     [rsp+arg_8], rbx
0x180015411  mov     [rsp+arg_10], rsi
0x180015416  mov     [rsp+arg_0], rcx
0x18001541b  push    rdi; int
0x18001541c  sub     rsp, 20h
0x180015420  mov     rdi, rdx
0x180015423  mov     rbx, rcx
0x180015426  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18001542d  mov     [rcx], rax
0x180015430  mov     qword ptr [rcx+8], 0
0x180015438  mov     rcx, [rsp+28h]; this
0x18001543d  cmp     qword ptr [rdx+8], 0
0x180015442  jnz     short loc_18001545C
0x180015444  mov     r9d, 80070057h; char *
0x18001544a  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x180015451  mov     edx, 11h; void *
0x180015456  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18001545c  call    cs:__imp_GetCurrentThread
0x180015462  lea     r9, [rbx+8]; TokenHandle
0x180015466  mov     edx, 2000Eh; DesiredAccess
0x18001546b  mov     r8d, 1; OpenAsSelf
0x180015471  mov     rcx, rax; ThreadHandle
0x180015474  call    cs:__imp_OpenThreadToken
0x18001547a  test    eax, eax
0x18001547c  jnz     short loc_1800154B6
0x18001547e  call    cs:__imp_GetLastError
0x180015484  test    eax, eax
0x180015486  jg      short loc_18001548D
0x180015488  mov     r9d, eax
0x18001548b  jmp     short loc_180015498
0x18001548d  movzx   r9d, ax
0x180015491  or      r9d, 80070000h; char *
0x180015498  mov     rcx, [rsp+28h]; this
0x18001549d  cmp     eax, 3F0h
0x1800154a2  jz      short loc_1800154B6
0x1800154a4  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x1800154ab  mov     edx, 16h; void *
0x1800154b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800154b6  mov     rcx, [rdi+8]; hToken
0x1800154ba  call    cs:__imp_ImpersonateLoggedOnUser
0x1800154c0  mov     rcx, [rsp+28h]; this
0x1800154c5  test    eax, eax
0x1800154c7  jnz     short loc_1800154D9
0x1800154c9  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x1800154d0  lea     edx, [rax+18h]; void *
0x1800154d3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800154d9  mov     rax, rbx
0x1800154dc  mov     rbx, [rsp+28h+arg_8]
0x1800154e1  mov     rsi, [rsp+28h+arg_10]
0x1800154e6  add     rsp, 20h
0x1800154ea  pop     rdi
0x1800154eb  retn
```
