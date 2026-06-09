# Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800b805c`
- end: `0x1800b81a8`
- name: `?AccessCheckByString@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `332`
- prototype: `__int64 __fastcall(HANDLE ClientToken)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800b81b0`

## callees

- `0x1800094c0`
- `0x180029408`
- `0x18002f260`
- `0x180039e9c`
- `0x18003f3a0`
- `0x1800b805c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x1800b8135`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x1800b8135`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b80b1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b80b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckByString(
        HANDLE ClientToken,
        __int64 a2)
{
  const WCHAR *v3; // rax
  const char *v4; // r9
  const char *v5; // r9
  WINBOOL AccessStatus; // [rsp+60h] [rbp+7h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp+Bh] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp+Fh] BYREF
  DWORD PrivilegeSetLength; // [rsp+70h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR *p_pSecurityDescriptor; // [rsp+78h] [rbp+1Fh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+27h] BYREF
  char v13; // [rsp+88h] [rbp+2Fh]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+90h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  pSecurityDescriptor = 0;
  p_pSecurityDescriptor = &pSecurityDescriptor;
  SecurityDescriptor = 0;
  v13 = 1;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v3, 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x6B,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\callervalidation\\callervalidation.cpp",
      v4);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pSecurityDescriptor);
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 20;
  if ( !AccessCheckByType(
          pSecurityDescriptor,
          0,
          ClientToken,
          1u,
          0,
          0,
          (PGENERIC_MAPPING)&stru_180147FB8,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x85,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\callervalidation\\callervalidation.cpp",
      v5);
  if ( AccessStatus && (GrantedAccess & 1) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
    return 1;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
    return 0;
  }
}

```

## disassembly

```asm
0x1800b805c  mov     [rsp-8+arg_10], rbx
0x1800b8061  push    rbp
0x1800b8062  lea     rbp, [rsp-57h]
0x1800b8067  sub     rsp, 0B0h
0x1800b806e  mov     rax, cs:__security_cookie
0x1800b8075  xor     rax, rsp
0x1800b8078  mov     [rbp+57h+var_8], rax
0x1800b807c  mov     rbx, rcx
0x1800b807f  mov     [rbp+57h+pSecurityDescriptor], 0
0x1800b8087  lea     rax, [rbp+57h+pSecurityDescriptor]
0x1800b808b  mov     [rbp+57h+var_38], rax
0x1800b808f  mov     [rbp+57h+SecurityDescriptor], 0
0x1800b8097  mov     [rbp+57h+var_28], 1
0x1800b809b  mov     rcx, rdx
0x1800b809e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800b80a3  xor     r9d, r9d; SecurityDescriptorSize
0x1800b80a6  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800b80aa  lea     edx, [r9+1]; StringSDRevision
0x1800b80ae  mov     rcx, rax; StringSecurityDescriptor
0x1800b80b1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b80b7  mov     rcx, [rbp+5Fh]; this
0x1800b80bb  test    eax, eax
0x1800b80bd  jz      loc_1800B8196
0x1800b80c3  lea     rcx, [rbp+57h+var_38]
0x1800b80c7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x1800b80cc  xorps   xmm0, xmm0
0x1800b80cf  xor     eax, eax
0x1800b80d1  movups  xmmword ptr [rbp+57h+var_20.PrivilegeCount], xmm0
0x1800b80d5  mov     [rbp+57h+var_20.Privilege.Attributes], eax
0x1800b80d8  mov     [rbp+57h+var_4C], eax
0x1800b80db  mov     [rbp+57h+var_50], eax
0x1800b80de  mov     [rbp+57h+var_40], 14h
0x1800b80e5  lea     rax, [rbp+57h+var_50]
0x1800b80e9  mov     [rsp+0B0h+AccessStatus], rax; AccessStatus
0x1800b80ee  lea     rax, [rbp+57h+var_4C]
0x1800b80f2  mov     [rsp+0B0h+GrantedAccess], rax; GrantedAccess
0x1800b80f7  lea     rax, [rbp+57h+var_40]
0x1800b80fb  mov     [rsp+0B0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800b8100  lea     rax, [rbp+57h+var_20]
0x1800b8104  mov     [rsp+0B0h+PrivilegeSet], rax; PrivilegeSet
0x1800b8109  lea     rax, stru_180147FB8
0x1800b8110  mov     [rsp+0B0h+GenericMapping], rax; GenericMapping
0x1800b8115  mov     [rsp+0B0h+ObjectTypeListLength], 0; ObjectTypeListLength
0x1800b811d  mov     [rsp+0B0h+ObjectTypeList], 0; ObjectTypeList
0x1800b8126  mov     r9d, 1; DesiredAccess
0x1800b812c  mov     r8, rbx; ClientToken
0x1800b812f  xor     edx, edx; PrincipalSelfSid
0x1800b8131  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800b8135  call    cs:__imp_AccessCheckByType
0x1800b813b  mov     rcx, [rbp+5Fh]; this
0x1800b813f  test    eax, eax
0x1800b8141  jz      short loc_1800B8184
0x1800b8143  cmp     [rbp+57h+var_50], 0
0x1800b8147  jz      short loc_1800B815C
0x1800b8149  test    byte ptr [rbp+57h+var_4C], 1
0x1800b814d  jz      short loc_1800B815C
0x1800b814f  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x1800b8153  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b8158  mov     al, 1
0x1800b815a  jmp     short loc_1800B8167
0x1800b815c  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x1800b8160  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800b8165  xor     al, al
0x1800b8167  mov     rcx, [rbp+57h+var_8]
0x1800b816b  xor     rcx, rsp; StackCookie
0x1800b816e  call    __security_check_cookie
0x1800b8173  mov     rbx, [rsp+0B0h+arg_10]
0x1800b817b  add     rsp, 0B0h
0x1800b8182  pop     rbp
0x1800b8183  retn
0x1800b8184  lea     r8, aOnecoreBaseDev_51; "onecore\\base\\devices\\cam\\winrt\\cal"...
0x1800b818b  mov     edx, 85h; void *
0x1800b8190  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800b8196  lea     r8, aOnecoreBaseDev_51; "onecore\\base\\devices\\cam\\winrt\\cal"...
0x1800b819d  mov     edx, 6Bh ; 'k'; void *
0x1800b81a2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
