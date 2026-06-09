# TokenHelpers::DuplicateTokenWithRequiredPrivileges(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x180034194`
- end: `0x18003423a`
- name: `?DuplicateTokenWithRequiredPrivileges@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@AEBV2345@@Z`
- size: `166`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180034240`

## callees

- `0x18001540c`
- `0x18001584c`
- `0x180019624`
- `0x180034194`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800341fd`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800341fd`

## string_xrefs

- `0x180034207`: `onecoreuap\enduser\winstore\servicescommon\inc\TokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TokenHelpers::DuplicateTokenWithRequiredPrivileges(__int64 a1, __int64 a2)
{
  const char *v4; // r9
  _BYTE v6[32]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  TokenHelpers::ImpersonateContext::ImpersonateContext((__int64)v6, a2);
  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  if ( !DuplicateTokenEx(*(HANDLE *)(a2 + 8), 0x2000Eu, 0, SecurityImpersonation, TokenImpersonation, (PHANDLE)(a1 + 8)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\enduser\\winstore\\servicescommon\\inc\\TokenHelpers.h",
      v4);
  TokenHelpers::ImpersonateContext::~ImpersonateContext((TokenHelpers::ImpersonateContext *)v6);
  return a1;
}

```

## disassembly

```asm
0x180034194  mov     rax, rsp
0x180034197  mov     [rax+10h], rbx
0x18003419b  mov     [rax+18h], rsi
0x18003419f  mov     [rax+8], rcx
0x1800341a3  push    rdi
0x1800341a4  sub     rsp, 50h
0x1800341a8  mov     rbx, rdx
0x1800341ab  mov     rdi, rcx
0x1800341ae  mov     dword ptr [rax-28h], 0
0x1800341b5  lea     rcx, [rax-20h]
0x1800341b9  call    ??0ImpersonateContext@TokenHelpers@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; TokenHelpers::ImpersonateContext::ImpersonateContext(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x1800341be  nop
0x1800341bf  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800341c6  mov     [rdi], rax
0x1800341c9  lea     rax, [rdi+8]
0x1800341cd  mov     qword ptr [rax], 0
0x1800341d4  mov     [rsp+58h+var_28], 1
0x1800341dc  mov     rsi, [rsp+58h]
0x1800341e1  mov     [rsp+58h+phNewToken], rax; phNewToken
0x1800341e6  mov     r9d, 2; ImpersonationLevel
0x1800341ec  mov     [rsp+58h+TokenType], r9d; TokenType
0x1800341f1  xor     r8d, r8d; lpTokenAttributes
0x1800341f4  mov     edx, 2000Eh; dwDesiredAccess
0x1800341f9  mov     rcx, [rbx+8]; hExistingToken
0x1800341fd  call    cs:__imp_DuplicateTokenEx
0x180034203  test    eax, eax
0x180034205  jnz     short loc_18003421C
0x180034207  lea     r8, aOnecoreuapEndu_5; "onecoreuap\\enduser\\winstore\\services"...
0x18003420e  mov     edx, 98h; void *
0x180034213  mov     rcx, rsi; this
0x180034216  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003421c  lea     rcx, [rsp+58h+var_20]; this
0x180034221  call    ??1ImpersonateContext@TokenHelpers@@QEAA@XZ; TokenHelpers::ImpersonateContext::~ImpersonateContext(void)
0x180034226  mov     rax, rdi
0x180034229  mov     rbx, [rsp+58h+arg_8]
0x18003422e  mov     rsi, [rsp+58h+arg_10]
0x180034233  add     rsp, 50h
0x180034237  pop     rdi
0x180034238  retn
```
