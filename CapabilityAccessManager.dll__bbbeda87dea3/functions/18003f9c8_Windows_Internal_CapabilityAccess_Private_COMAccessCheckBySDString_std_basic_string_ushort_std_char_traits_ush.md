# Windows::Internal::CapabilityAccess::Private::COMAccessCheckBySDString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003f9c8`
- end: `0x18003fb68`
- name: `?COMAccessCheckBySDString@Private@CapabilityAccess@Internal@Windows@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `416`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003fb70`
- `0x18003fbc8`
- `0x18003fc20`

## callees

- `0x1800094c0`
- `0x18002392c`
- `0x180029408`
- `0x18002f260`
- `0x180039e9c`
- `0x18003f3a0`
- `0x18003f4a0`
- `0x18003f9c8`
- `0x180040d7c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18003faef`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x18003faef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003fa5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003fa5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Windows::Internal::CapabilityAccess::Private::COMAccessCheckBySDString(__int64 a1)
{
  HANDLE v2; // rbx
  const WCHAR *v3; // rax
  const char *v4; // r9
  const char *v5; // r9
  int ObjectTypeList; // [rsp+20h] [rbp-49h]
  WINBOOL AccessStatus; // [rsp+60h] [rbp-9h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-5h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp-1h] BYREF
  DWORD PrivilegeSetLength; // [rsp+70h] [rbp+7h] BYREF
  HANDLE ClientToken; // [rsp+78h] [rbp+Fh] BYREF
  PSECURITY_DESCRIPTOR *p_pSecurityDescriptor; // [rsp+80h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp+1Fh] BYREF
  char v15; // [rsp+90h] [rbp+27h]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+98h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(&ClientToken);
  v2 = ClientToken;
  if ( (((unsigned __int64)ClientToken + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x748,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      (const char *)0x8000FFFFLL,
      ObjectTypeList);
  pSecurityDescriptor = 0;
  p_pSecurityDescriptor = &pSecurityDescriptor;
  SecurityDescriptor = 0;
  v15 = 1;
  v3 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v3, 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x750,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v4);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_pSecurityDescriptor);
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 20;
  if ( !AccessCheckByType(
          pSecurityDescriptor,
          0,
          v2,
          1u,
          0,
          0,
          (PGENERIC_MAPPING)&GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x76B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v5);
  if ( AccessStatus && (GrantedAccess & 1) != 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
    return 1;
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ClientToken);
    return 0;
  }
}

```

## disassembly

```asm
0x18003f9c8  mov     [rsp-8+arg_8], rbx
0x18003f9cd  mov     [rsp-8+arg_10], rdi
0x18003f9d2  push    rbp
0x18003f9d3  lea     rbp, [rsp-57h]
0x18003f9d8  sub     rsp, 0C0h
0x18003f9df  mov     rax, cs:__security_cookie
0x18003f9e6  xor     rax, rsp
0x18003f9e9  mov     [rbp+57h+var_10], rax
0x18003f9ed  mov     rdi, rcx
0x18003f9f0  lea     rcx, [rbp+57h+ClientToken]
0x18003f9f4  call    ?GetCallerTokenFromComCall@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(void)
0x18003f9f9  nop
0x18003f9fa  mov     rbx, [rbp+57h+ClientToken]
0x18003f9fe  lea     rax, [rbx+1]
0x18003fa02  test    rax, 0FFFFFFFFFFFFFFFEh
0x18003fa08  setz    al
0x18003fa0b  mov     rcx, [rbp+5Fh]; this
0x18003fa0f  test    al, al
0x18003fa11  jz      short loc_18003FA2B
0x18003fa13  mov     r9d, 8000FFFFh; char *
0x18003fa19  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18003fa20  mov     edx, 748h; void *
0x18003fa25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003fa2b  mov     [rbp+57h+pSecurityDescriptor], 0
0x18003fa33  lea     rax, [rbp+57h+pSecurityDescriptor]
0x18003fa37  mov     [rbp+57h+var_40], rax
0x18003fa3b  mov     [rbp+57h+SecurityDescriptor], 0
0x18003fa43  mov     [rbp+57h+var_30], 1
0x18003fa47  mov     rcx, rdi
0x18003fa4a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003fa4f  xor     r9d, r9d; SecurityDescriptorSize
0x18003fa52  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18003fa56  lea     edx, [r9+1]; StringSDRevision
0x18003fa5a  mov     rcx, rax; StringSecurityDescriptor
0x18003fa5d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003fa63  mov     rcx, [rbp+5Fh]; this
0x18003fa67  test    eax, eax
0x18003fa69  jnz     short loc_18003FA7D
0x18003fa6b  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18003fa72  mov     edx, 750h; void *
0x18003fa77  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003fa7d  lea     rcx, [rbp+57h+var_40]
0x18003fa81  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18003fa86  xorps   xmm0, xmm0
0x18003fa89  xor     eax, eax
0x18003fa8b  movups  xmmword ptr [rbp+57h+var_28.PrivilegeCount], xmm0
0x18003fa8f  mov     [rbp+57h+var_28.Privilege.Attributes], eax
0x18003fa92  mov     [rbp+57h+var_5C], eax
0x18003fa95  mov     [rbp+57h+var_60], eax
0x18003fa98  mov     [rbp+57h+var_50], 14h
0x18003fa9f  lea     rax, [rbp+57h+var_60]
0x18003faa3  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x18003faa8  lea     rax, [rbp+57h+var_5C]
0x18003faac  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x18003fab1  lea     rax, [rbp+57h+var_50]
0x18003fab5  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18003faba  lea     rax, [rbp+57h+var_28]
0x18003fabe  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x18003fac3  lea     rax, GenericMapping
0x18003faca  mov     [rsp+0C0h+GenericMapping], rax; GenericMapping
0x18003facf  mov     [rsp+0C0h+ObjectTypeListLength], 0; ObjectTypeListLength
0x18003fad7  mov     [rsp+0C0h+ObjectTypeList], 0; ObjectTypeList
0x18003fae0  mov     r9d, 1; DesiredAccess
0x18003fae6  mov     r8, rbx; ClientToken
0x18003fae9  xor     edx, edx; PrincipalSelfSid
0x18003faeb  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x18003faef  call    cs:__imp_AccessCheckByType
0x18003faf5  mov     rcx, [rbp+5Fh]; this
0x18003faf9  test    eax, eax
0x18003fafb  jnz     short loc_18003FB0F
0x18003fafd  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18003fb04  mov     edx, 76Bh; void *
0x18003fb09  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18003fb0f  cmp     [rbp+57h+var_60], 0
0x18003fb13  jz      short loc_18003FB32
0x18003fb15  test    byte ptr [rbp+57h+var_5C], 1
0x18003fb19  jz      short loc_18003FB32
0x18003fb1b  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x18003fb1f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fb24  nop
0x18003fb25  lea     rcx, [rbp+57h+ClientToken]
0x18003fb29  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003fb2e  mov     al, 1
0x18003fb30  jmp     short loc_18003FB47
0x18003fb32  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x18003fb36  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003fb3b  nop
0x18003fb3c  lea     rcx, [rbp+57h+ClientToken]
0x18003fb40  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18003fb45  xor     al, al
0x18003fb47  mov     rcx, [rbp+57h+var_10]
0x18003fb4b  xor     rcx, rsp; StackCookie
0x18003fb4e  call    __security_check_cookie
0x18003fb53  lea     r11, [rsp+0C0h+var_s0]
0x18003fb5b  mov     rbx, [r11+18h]
0x18003fb5f  mov     rdi, [r11+20h]
0x18003fb63  mov     rsp, r11
0x18003fb66  pop     rbp
0x18003fb67  retn
```
