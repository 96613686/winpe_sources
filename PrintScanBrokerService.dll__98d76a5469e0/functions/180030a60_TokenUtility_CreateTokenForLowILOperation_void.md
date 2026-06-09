# TokenUtility::CreateTokenForLowILOperation(void *)

- ea: `0x180030a60`
- end: `0x180030ca8`
- name: `?CreateTokenForLowILOperation@TokenUtility@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX@Z`
- size: `584`
- prototype: `void *__fastcall(__int64, void *, void *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ad90`

## callees

- `0x180002d40`
- `0x180007a28`
- `0x18000876c`
- `0x18000f8a8`
- `0x18001255c`
- `0x18001cf40`
- `0x18001d0a0`
- `0x180023264`
- `0x180030a38`
- `0x180030a60`
- `0x180031f84`
- `0x1800320a4`
- `0x1800321f8`
- `0x180032588`
- `0x1800327ec`
- `0x18003286c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180030ad2`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180030b5a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180030ad2`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180030b5a`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180030c12`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180030c12`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180030afd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180030b8c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180030afd`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180030b8c`

## string_xrefs

- `0x180030b1c`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180030bab`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180030c2b`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x180030c1c`: `DuplicateTokenEx failed!`
- `0x180030b0c`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed!`
- `0x180030b9b`: `ConvertStringSecurityDescriptorToSecurityDescriptor failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void *__fastcall TokenUtility::CreateTokenForLowILOperation(__int64 a1, void *a2, void *a3)
{
  __int64 v4; // rcx
  BOOL v5; // eax
  const WCHAR *v6; // rcx
  BOOL v7; // eax
  unsigned int v8; // eax
  TokenUtility *v9; // rcx
  TokenUtility *v10; // rcx
  TokenUtility *v11; // rcx
  __int64 v12; // rcx
  const char *phNewToken; // [rsp+28h] [rbp-31h]
  const char *phNewTokena; // [rsp+28h] [rbp-31h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-29h] BYREF
  void *v17; // [rsp+38h] [rbp-21h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+40h] [rbp-19h] BYREF
  PSECURITY_DESCRIPTOR v19; // [rsp+48h] [rbp-11h]
  HANDLE hExistingToken; // [rsp+50h] [rbp-9h] BYREF
  struct _SECURITY_ATTRIBUTES TokenAttributes; // [rsp+68h] [rbp+Fh] BYREF
  LPCWSTR StringSecurityDescriptor[4]; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v19 = a2;
  TokenUtility::_DuplicateHandle(a1, &hExistingToken, a3, 1);
  SecurityDescriptorSize = 0;
  SecurityDescriptor = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    TokenUtility::_CreateAllAccessDaclForUserAndWorker(v4, StringSecurityDescriptor, hExistingToken);
    SecurityDescriptor = 0;
    v6 = (const WCHAR *)StringSecurityDescriptor;
    if ( StringSecurityDescriptor[3] > (LPCWSTR)7 )
      v6 = StringSecurityDescriptor[0];
    v7 = ConvertStringSecurityDescriptorToSecurityDescriptorW(v6, 1u, &SecurityDescriptor, &SecurityDescriptorSize);
    wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
      (const char *)v7,
      (bool)"ConvertStringSecurityDescriptorToSecurityDescriptor failed!",
      phNewToken);
    std::wstring::_Tidy_deallocate(StringSecurityDescriptor);
  }
  else
  {
    SecurityDescriptor = 0;
    v5 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"D:(A;OICI;KA;;;S-1-5-99-216390572-1995538116-3857911515-2404958512-2623887229)(A;OICI;KA;;;SY)",
           1u,
           &SecurityDescriptor,
           &SecurityDescriptorSize);
    wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
      (const char *)v5,
      (bool)"ConvertStringSecurityDescriptorToSecurityDescriptor failed!",
      phNewToken);
  }
  *(_QWORD *)&TokenAttributes.nLength = 24;
  *(_QWORD *)&TokenAttributes.bInheritHandle = 1;
  TokenAttributes.lpSecurityDescriptor = SecurityDescriptor;
  v17 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v17,
    0);
  v8 = DuplicateTokenEx(hExistingToken, 0x8Eu, &TokenAttributes, SecurityImpersonation, TokenImpersonation, &v17);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x59,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v8,
    (int)"DuplicateTokenEx failed!",
    phNewTokena);
  TokenUtility::_SetTokenAsEnterpriseExemptIfNeeded(v9, v17);
  TokenUtility::_ElevateTokenToMedium(v10, v17);
  TokenUtility::_RemoveAttributesForLowILToken(v11, v17);
  TokenUtility::_DuplicateHandle(v12, (HANDLE *)a2, v17, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&SecurityDescriptor);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
  return a2;
}

```

## disassembly

```asm
0x180030a60  mov     [rsp-8+arg_0], rbx
0x180030a65  mov     [rsp-8+arg_18], rdi
0x180030a6a  push    rbp
0x180030a6b  lea     rbp, [rsp-57h]
0x180030a70  sub     rsp, 0B0h
0x180030a77  mov     rax, cs:__security_cookie
0x180030a7e  xor     rax, rsp
0x180030a81  mov     [rbp+57h+var_10], rax
0x180030a85  mov     rdi, rdx
0x180030a88  mov     [rbp+57h+var_68], rdx
0x180030a8c  mov     r9b, 1
0x180030a8f  lea     rdx, [rbp+57h+hExistingToken]
0x180030a93  call    ?_DuplicateHandle@TokenUtility@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N@Z; TokenUtility::_DuplicateHandle(void *,bool)
0x180030a98  nop
0x180030a99  mov     [rbp+57h+SecurityDescriptorSize], 0
0x180030aa0  mov     [rbp+57h+SecurityDescriptor], 0
0x180030aa8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180030aaf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180030ab4  test    al, al
0x180030ab6  jnz     short loc_180030B32
0x180030ab8  mov     rbx, [rbp+57h+SecurityDescriptor]
0x180030abc  test    rbx, rbx
0x180030abf  jz      short loc_180030AE1
0x180030ac1  lea     rcx, [rbp+57h+var_68]; this
0x180030ac5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180030aca  mov     [rbp+57h+ObjectDescriptor], rbx
0x180030ace  lea     rcx, [rbp+57h+ObjectDescriptor]; ObjectDescriptor
0x180030ad2  call    cs:__imp_DestroyPrivateObjectSecurity
0x180030ad8  lea     rcx, [rbp+57h+var_68]; this
0x180030adc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180030ae1  mov     [rbp+57h+SecurityDescriptor], 0
0x180030ae9  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180030aed  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180030af1  mov     edx, 1; StringSDRevision
0x180030af6  lea     rcx, StringSecurityDescriptor; "D:(A;OICI;KA;;;S-1-5-99-216390572-19955"...
0x180030afd  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180030b03  test    eax, eax
0x180030b05  setnz   al
0x180030b08  mov     rcx, [rbp+5Fh]; this
0x180030b0c  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x180030b13  mov     qword ptr [rsp+0B0h+TokenType], rdx; bool
0x180030b18  movzx   r9d, al; char *
0x180030b1c  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180030b23  mov     edx, 4Bh ; 'K'; void *
0x180030b28  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180030b2d  jmp     loc_180030BC6
0x180030b32  mov     r8, [rbp+57h+hExistingToken]
0x180030b36  lea     rdx, [rbp+57h+StringSecurityDescriptor]
0x180030b3a  call    ?_CreateAllAccessDaclForUserAndWorker@TokenUtility@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; TokenUtility::_CreateAllAccessDaclForUserAndWorker(void *)
0x180030b3f  nop
0x180030b40  mov     rbx, [rbp+57h+SecurityDescriptor]
0x180030b44  test    rbx, rbx
0x180030b47  jz      short loc_180030B69
0x180030b49  lea     rcx, [rbp+57h+ObjectDescriptor]; this
0x180030b4d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180030b52  mov     [rbp+57h+var_68], rbx
0x180030b56  lea     rcx, [rbp+57h+var_68]; ObjectDescriptor
0x180030b5a  call    cs:__imp_DestroyPrivateObjectSecurity
0x180030b60  lea     rcx, [rbp+57h+ObjectDescriptor]; this
0x180030b64  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180030b69  mov     [rbp+57h+SecurityDescriptor], 0
0x180030b71  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x180030b75  cmp     [rbp+57h+var_18], 7
0x180030b7a  cmova   rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180030b7f  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180030b83  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180030b87  mov     edx, 1; StringSDRevision
0x180030b8c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180030b92  test    eax, eax
0x180030b94  setnz   al
0x180030b97  mov     rcx, [rbp+5Fh]; this
0x180030b9b  lea     rdx, aConvertstrings; "ConvertStringSecurityDescriptorToSecuri"...
0x180030ba2  mov     qword ptr [rsp+0B0h+TokenType], rdx; bool
0x180030ba7  movzx   r9d, al; char *
0x180030bab  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180030bb2  mov     edx, 46h ; 'F'; void *
0x180030bb7  call    ?Throw_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x180030bbc  nop
0x180030bbd  lea     rcx, [rbp+57h+StringSecurityDescriptor]
0x180030bc1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180030bc6  mov     qword ptr [rbp+57h+TokenAttributes.nLength], 18h
0x180030bce  mov     qword ptr [rbp+57h+TokenAttributes.bInheritHandle], 1
0x180030bd6  mov     rax, [rbp+57h+SecurityDescriptor]
0x180030bda  mov     [rbp+57h+TokenAttributes.lpSecurityDescriptor], rax
0x180030bde  mov     [rbp+57h+var_78], 0
0x180030be6  xor     edx, edx
0x180030be8  lea     rcx, [rbp+57h+var_78]
0x180030bec  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180030bf1  lea     rax, [rbp+57h+var_78]
0x180030bf5  mov     [rsp+0B0h+phNewToken], rax; char *
0x180030bfa  mov     r9d, 2; ImpersonationLevel
0x180030c00  mov     [rsp+0B0h+TokenType], r9d; TokenType
0x180030c05  lea     r8, [rbp+57h+TokenAttributes]; lpTokenAttributes
0x180030c09  mov     edx, 8Eh; dwDesiredAccess
0x180030c0e  mov     rcx, [rbp+57h+hExistingToken]; hExistingToken
0x180030c12  call    cs:__imp_DuplicateTokenEx
0x180030c18  mov     rcx, [rbp+5Fh]; this
0x180030c1c  lea     rdx, aDuplicatetoken; "DuplicateTokenEx failed!"
0x180030c23  mov     qword ptr [rsp+0B0h+TokenType], rdx; int
0x180030c28  mov     r9d, eax; char *
0x180030c2b  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180030c32  mov     edx, 59h ; 'Y'; void *
0x180030c37  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180030c3c  mov     rdx, [rbp+57h+var_78]; void *
0x180030c40  call    ?_SetTokenAsEnterpriseExemptIfNeeded@TokenUtility@@AEAAXPEAX@Z; TokenUtility::_SetTokenAsEnterpriseExemptIfNeeded(void *)
0x180030c45  mov     rdx, [rbp+57h+var_78]; void *
0x180030c49  call    ?_ElevateTokenToMedium@TokenUtility@@AEAAXPEAX@Z; TokenUtility::_ElevateTokenToMedium(void *)
0x180030c4e  mov     rdx, [rbp+57h+var_78]; void *
0x180030c52  call    ?_RemoveAttributesForLowILToken@TokenUtility@@AEAAXPEAX@Z; TokenUtility::_RemoveAttributesForLowILToken(void *)
0x180030c57  xor     r9d, r9d
0x180030c5a  mov     r8, [rbp+57h+var_78]
0x180030c5e  mov     rdx, rdi
0x180030c61  call    ?_DuplicateHandle@TokenUtility@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX_N@Z; TokenUtility::_DuplicateHandle(void *,bool)
0x180030c66  nop
0x180030c67  lea     rcx, [rbp+57h+var_78]
0x180030c6b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030c70  nop
0x180030c71  lea     rcx, [rbp+57h+SecurityDescriptor]
0x180030c75  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180030c7a  nop
0x180030c7b  lea     rcx, [rbp+57h+hExistingToken]
0x180030c7f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030c84  mov     rax, rdi
0x180030c87  mov     rcx, [rbp+57h+var_10]
0x180030c8b  xor     rcx, rsp; StackCookie
0x180030c8e  call    __security_check_cookie
0x180030c93  lea     r11, [rsp+0B0h+var_s0]
0x180030c9b  mov     rbx, [r11+10h]
0x180030c9f  mov     rdi, [r11+28h]
0x180030ca3  mov     rsp, r11
0x180030ca6  pop     rbp
0x180030ca7  retn
```
