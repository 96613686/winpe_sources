# GetTokenSID(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x18000f07c`
- end: `0x18000f15c`
- name: `?GetTokenSID@@YA?AV?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@234@@Z`
- size: `224`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800107b0`
- `0x180011aa0`
- `0x180012984`
- `0x180026b60`
- `0x180045750`
- `0x180055e28`

## callees

- `0x18000f07c`
- `0x180076300`
- `0x180082410`
- `0x18008a400`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f0b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f0e7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f0b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f0e7`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000f116`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000f116`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetTokenSID(__int64 a1, __int64 a2)
{
  PSID *v4; // rsi
  const char *v5; // r9
  const struct std::nothrow_t *v6; // rdx
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF
  PSID *v11; // [rsp+70h] [rbp+18h]

  TokenInformationLength = 0;
  GetTokenInformation(*(HANDLE *)(a2 + 8), TokenUser, 0, 0, &TokenInformationLength);
  v4 = (PSID *)operator new[](TokenInformationLength);
  v11 = v4;
  if ( !GetTokenInformation(*(HANDLE *)(a2 + 8), TokenUser, v4, TokenInformationLength, &TokenInformationLength) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      v5);
  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  if ( !ConvertSidToStringSidW(*v4, (LPWSTR *)(a1 + 8)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\misc.cpp",
      v7);
  operator delete(v4, v6);
  return a1;
}

```

## disassembly

```asm
0x18000f07c  mov     rax, rsp
0x18000f07f  mov     [rax+8], rcx
0x18000f083  push    rbx
0x18000f084  push    rsi
0x18000f085  push    rdi
0x18000f086  sub     rsp, 40h
0x18000f08a  mov     rbx, rdx
0x18000f08d  mov     rdi, rcx
0x18000f090  mov     dword ptr [rax-28h], 0
0x18000f097  mov     dword ptr [rax+10h], 0
0x18000f09e  lea     rax, [rax+10h]
0x18000f0a2  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000f0a7  xor     r9d, r9d; TokenInformationLength
0x18000f0aa  xor     r8d, r8d; TokenInformation
0x18000f0ad  lea     edx, [r9+1]; TokenInformationClass
0x18000f0b1  mov     rcx, [rbx+8]; TokenHandle
0x18000f0b5  call    cs:__imp_GetTokenInformation
0x18000f0bb  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x18000f0bf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f0c4  mov     rsi, rax
0x18000f0c7  mov     [rsp+58h+arg_10], rax
0x18000f0cc  lea     rax, [rsp+58h+TokenInformationLength]
0x18000f0d1  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18000f0d6  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x18000f0db  mov     r8, rsi; TokenInformation
0x18000f0de  mov     edx, 1; TokenInformationClass
0x18000f0e3  mov     rcx, [rbx+8]; TokenHandle
0x18000f0e7  call    cs:__imp_GetTokenInformation
0x18000f0ed  mov     rcx, [rsp+58h]; this
0x18000f0f2  test    eax, eax
0x18000f0f4  jz      short loc_18000F138
0x18000f0f6  lea     rax, ??_7?$HandleT@ULocalAllocStringBufferTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<LocalAllocStringBufferTraits>::`vftable'
0x18000f0fd  mov     [rdi], rax
0x18000f100  lea     rdx, [rdi+8]; StringSid
0x18000f104  mov     qword ptr [rdx], 0
0x18000f10b  mov     [rsp+58h+var_28], 1
0x18000f113  mov     rcx, [rsi]; Sid
0x18000f116  call    cs:__imp_ConvertSidToStringSidW
0x18000f11c  mov     rcx, [rsp+58h]; this
0x18000f121  test    eax, eax
0x18000f123  jz      short loc_18000F14A
0x18000f125  mov     rcx, rsi; void *
0x18000f128  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f12d  mov     rax, rdi
0x18000f130  add     rsp, 40h
0x18000f134  pop     rdi
0x18000f135  pop     rsi
0x18000f136  pop     rbx
0x18000f137  retn
0x18000f138  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000f13f  mov     edx, 0A8h; void *
0x18000f144  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000f14a  lea     r8, aOnecoreuapEndu_29; "onecoreuap\\enduser\\winstore\\licensem"...
0x18000f151  mov     edx, 0ACh; void *
0x18000f156  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
