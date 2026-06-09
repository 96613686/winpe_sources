# ImpersonateContext::ImpersonateContext(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x180085084`
- end: `0x180085166`
- name: `??0ImpersonateContext@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180059460`

## callees

- `0x1800593bc`
- `0x180085084`
- `0x18008a12c`
- `0x18008a400`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800850f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800850f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800850d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800850d4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800850ec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800850ec`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085132`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180085132`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ImpersonateContext::ImpersonateContext(__int64 a1, __int64 a2)
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
      (void *)0x1FC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
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
        (void *)0x201,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
        v6,
        v9);
  }
  if ( !ImpersonateLoggedOnUser(*(HANDLE *)(a2 + 8)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x203,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
      v7);
  return a1;
}

```

## disassembly

```asm
0x180085084  mov     [rsp+arg_8], rbx
0x180085089  mov     [rsp+arg_10], rsi
0x18008508e  mov     [rsp+arg_0], rcx
0x180085093  push    rdi; int
0x180085094  sub     rsp, 20h
0x180085098  mov     rdi, rdx
0x18008509b  mov     rbx, rcx
0x18008509e  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800850a5  mov     [rcx], rax
0x1800850a8  mov     qword ptr [rcx+8], 0
0x1800850b0  mov     rcx, [rsp+28h]; this
0x1800850b5  cmp     qword ptr [rdx+8], 0
0x1800850ba  jnz     short loc_1800850D4
0x1800850bc  mov     r9d, 80070057h; char *
0x1800850c2  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800850c9  mov     edx, 1FCh; void *
0x1800850ce  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800850d4  call    cs:__imp_GetCurrentThread
0x1800850da  lea     r9, [rbx+8]; TokenHandle
0x1800850de  mov     edx, 2000Eh; DesiredAccess
0x1800850e3  mov     r8d, 1; OpenAsSelf
0x1800850e9  mov     rcx, rax; ThreadHandle
0x1800850ec  call    cs:__imp_OpenThreadToken
0x1800850f2  test    eax, eax
0x1800850f4  jnz     short loc_18008512E
0x1800850f6  call    cs:__imp_GetLastError
0x1800850fc  test    eax, eax
0x1800850fe  jg      short loc_180085105
0x180085100  mov     r9d, eax
0x180085103  jmp     short loc_180085110
0x180085105  movzx   r9d, ax
0x180085109  or      r9d, 80070000h; char *
0x180085110  mov     rcx, [rsp+28h]; this
0x180085115  cmp     eax, 3F0h
0x18008511a  jz      short loc_18008512E
0x18008511c  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x180085123  mov     edx, 201h; void *
0x180085128  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18008512e  mov     rcx, [rdi+8]; hToken
0x180085132  call    cs:__imp_ImpersonateLoggedOnUser
0x180085138  mov     rcx, [rsp+28h]; this
0x18008513d  test    eax, eax
0x18008513f  jnz     short loc_180085153
0x180085141  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x180085148  mov     edx, 203h; void *
0x18008514d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180085153  mov     rax, rbx
0x180085156  mov     rbx, [rsp+28h+arg_8]
0x18008515b  mov     rsi, [rsp+28h+arg_10]
0x180085160  add     rsp, 20h
0x180085164  pop     rdi
0x180085165  retn
```
