# _lambda_6783ced7c14576789a35b4d19aaf680c_::operator()

- ea: `0x18009b8ec`
- end: `0x18009ba9b`
- name: `_lambda_6783ced7c14576789a35b4d19aaf680c_::operator()`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023a24`

## callees

- `0x18000e5f4`
- `0x180021d30`
- `0x180022028`
- `0x180024844`
- `0x1800254f8`
- `0x18003b6b8`
- `0x1800894b0`
- `0x18009b8ec`
- `0x18009baa4`
- `0x1800b99f0`
- `0x1800badf0`
- `0x1800c40c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009ba29`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009ba29`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009ba11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009ba11`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009b949`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009ba3e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009b949`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009ba3e`

## string_xrefs

- `0x18009b929`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x18009ba0a`: `Windows.Security.Authorization.AppCapabilityAccess.AppCapability`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall lambda_6783ced7c14576789a35b4d19aaf680c_::operator()(CtaManager **a1, __int64 a2)
{
  int ActivationFactory; // eax
  unsigned int AgileReference; // eax
  __int64 *v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  void *v8; // rdx
  __int64 v9; // [rsp+20h] [rbp-58h] BYREF
  __int64 v10; // [rsp+28h] [rbp-50h] BYREF
  struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *v11; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_40670583>::GetImpl'::`2'::impl,
    a2);
  v10 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&string,
    L"Windows.Internal.CapabilityAccess.CapabilityAccess",
    0x33u,
    0x32u);
  ActivationFactory = RoGetActivationFactory(
                        *(_QWORD *)&hstringHeader.Reserved.Reserved2[16],
                        &GUID_518f3880_4e5c_4524_ab03_cd01336b2178,
                        &v10);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\ctamanager.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v9);
  v9 = 0;
  if ( v10 )
  {
    LODWORD(string) = 0;
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0;
    AgileReference = WINRT_IMPL_RoGetAgileReference(
                       0,
                       winrt::impl::guid_v<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>,
                       v10,
                       &v9);
    winrt::check_hresult(v12, AgileReference, &string);
  }
  v5 = (__int64 *)((char *)*a1 + 192);
  if ( v5 != &v9 )
  {
    if ( *v5 )
      winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref((char *)*a1 + 192);
    v6 = v9;
    v9 = 0;
    *v5 = v6;
  }
  if ( v9 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v9);
  if ( v10 )
    winrt::com_ptr<ThreadPool>::unconditional_release_ref(&v10);
  CtaManager::PopulateAppCapabilitiesMap(*a1);
  v11 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Security.Authorization.AppCapabilityAccess.AppCapability",
         0x40u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v7 = RoGetActivationFactory(string, &GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22, &v11);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\ctamanager.cpp",
      (const char *)(unsigned int)v7,
      v9);
  CtaManager::InitializeCapabilityListeners(*a1, v11);
  wil::details::SetEvent(*((wil::details **)*a1 + 1), v8);
  if ( v11 )
    winrt::com_ptr<ThreadPool>::unconditional_release_ref(&v11);
}

```

## disassembly

```asm
0x18009b8ec  push    rbp
0x18009b8ee  push    rbx
0x18009b8ef  push    rsi
0x18009b8f0  push    rdi
0x18009b8f1  mov     rbp, rsp
0x18009b8f4  sub     rsp, 78h
0x18009b8f8  mov     rax, cs:__security_cookie
0x18009b8ff  xor     rax, rsp
0x18009b902  mov     [rbp+var_18], rax
0x18009b906  mov     rdi, rcx
0x18009b909  xor     esi, esi
0x18009b90b  mov     dl, 1
0x18009b90d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_40670583@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_40670583@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583> `wil::Feature<__WilFeatureTraits_Feature_40670583>::GetImpl(void)'::`2'::impl
0x18009b914  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_40670583@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_40670583>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18009b919  mov     [rbp+var_50], rsi
0x18009b91d  mov     qword ptr [rbp+hstringHeader.Reserved+10h], rsi
0x18009b921  lea     r9d, [rsi+32h]; unsigned int
0x18009b925  lea     r8d, [rsi+33h]; unsigned int
0x18009b929  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18009b930  lea     rcx, [rbp+string]; hstringHeader
0x18009b934  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18009b939  nop
0x18009b93a  lea     r8, [rbp+var_50]
0x18009b93e  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x18009b945  mov     rcx, qword ptr [rbp+hstringHeader.Reserved+10h]
0x18009b949  call    cs:__imp_RoGetActivationFactory
0x18009b94f  mov     rcx, [rbp+20h]; this
0x18009b953  test    eax, eax
0x18009b955  jns     short loc_18009B96A
0x18009b957  mov     r9d, eax; char *
0x18009b95a  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009b961  lea     edx, [rsi+37h]; void *
0x18009b964  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b96a  mov     [rbp+var_58], rsi
0x18009b96e  cmp     [rbp+var_50], rsi
0x18009b972  jz      short loc_18009B9A5
0x18009b974  mov     dword ptr [rbp+string], esi
0x18009b977  xorps   xmm0, xmm0
0x18009b97a  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x18009b97f  lea     r9, [rbp+var_58]
0x18009b983  mov     r8, [rbp+var_50]
0x18009b987  lea     rdx, ??$guid_v@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>
0x18009b98e  xor     ecx, ecx
0x18009b990  call    WINRT_IMPL_RoGetAgileReference
0x18009b995  mov     edx, eax
0x18009b997  lea     r8, [rbp+string]
0x18009b99b  lea     rcx, [rbp+var_40]
0x18009b99f  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18009b9a4  nop
0x18009b9a5  mov     rbx, [rdi]
0x18009b9a8  add     rbx, 0C0h
0x18009b9af  lea     rax, [rbp+var_58]
0x18009b9b3  cmp     rbx, rax
0x18009b9b6  jz      short loc_18009B9D0
0x18009b9b8  cmp     [rbx], rsi
0x18009b9bb  jz      short loc_18009B9C5
0x18009b9bd  mov     rcx, rbx
0x18009b9c0  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18009b9c5  mov     rax, [rbp+var_58]
0x18009b9c9  mov     [rbp+var_58], rsi
0x18009b9cd  mov     [rbx], rax
0x18009b9d0  cmp     [rbp+var_58], rsi
0x18009b9d4  jz      short loc_18009B9E0
0x18009b9d6  lea     rcx, [rbp+var_58]
0x18009b9da  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18009b9df  nop
0x18009b9e0  cmp     [rbp+var_50], rsi
0x18009b9e4  jz      short loc_18009B9EF
0x18009b9e6  lea     rcx, [rbp+var_50]
0x18009b9ea  call    ?unconditional_release_ref@?$com_ptr@VThreadPool@@@winrt@@AEAAXXZ; winrt::com_ptr<ThreadPool>::unconditional_release_ref(void)
0x18009b9ef  mov     rcx, [rdi]; this
0x18009b9f2  call    ?PopulateAppCapabilitiesMap@CtaManager@@AEAAXXZ; CtaManager::PopulateAppCapabilitiesMap(void)
0x18009b9f7  mov     [rbp+var_48], rsi
0x18009b9fb  lea     r9, [rbp+string]; string
0x18009b9ff  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18009ba03  mov     ebx, 40h ; '@'
0x18009ba08  mov     edx, ebx; length
0x18009ba0a  lea     rcx, ?RuntimeClass_Windows_Security_Authorization_AppCapabilityAccess_AppCapability@@3QBGB; "Windows.Security.Authorization.AppCapab"...
0x18009ba11  call    cs:__imp_WindowsCreateStringReference
0x18009ba17  test    eax, eax
0x18009ba19  jns     short loc_18009BA2F
0x18009ba1b  xor     r9d, r9d; lpArguments
0x18009ba1e  xor     r8d, r8d; nNumberOfArguments
0x18009ba21  lea     edx, [rbx-3Fh]; dwExceptionFlags
0x18009ba24  mov     ecx, 0C000000Dh; dwExceptionCode
0x18009ba29  call    cs:__imp_RaiseException
0x18009ba2f  lea     r8, [rbp+var_48]
0x18009ba33  lea     rdx, _GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22
0x18009ba3a  mov     rcx, [rbp+string]
0x18009ba3e  call    cs:__imp_RoGetActivationFactory
0x18009ba44  mov     rcx, [rbp+20h]; this
0x18009ba48  test    eax, eax
0x18009ba4a  jns     short loc_18009BA5E
0x18009ba4c  mov     r9d, eax; char *
0x18009ba4f  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18009ba56  mov     edx, ebx; void *
0x18009ba58  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009ba5e  mov     rdx, [rbp+var_48]; struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *
0x18009ba62  mov     rcx, [rdi]; this
0x18009ba65  call    ?InitializeCapabilityListeners@CtaManager@@AEAAXPEAUIAppCapabilityStatics@AppCapabilityAccess@Authorization@Security@Windows@@@Z; CtaManager::InitializeCapabilityListeners(Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *)
0x18009ba6a  mov     rcx, [rdi]
0x18009ba6d  mov     rcx, [rcx+8]; this
0x18009ba71  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18009ba76  nop
0x18009ba77  cmp     [rbp+var_48], rsi
0x18009ba7b  jz      short loc_18009BA86
0x18009ba7d  lea     rcx, [rbp+var_48]
0x18009ba81  call    ?unconditional_release_ref@?$com_ptr@VThreadPool@@@winrt@@AEAAXXZ; winrt::com_ptr<ThreadPool>::unconditional_release_ref(void)
0x18009ba86  mov     rcx, [rbp+var_18]
0x18009ba8a  xor     rcx, rsp; StackCookie
0x18009ba8d  call    __security_check_cookie
0x18009ba92  add     rsp, 78h
0x18009ba96  pop     rdi
0x18009ba97  pop     rsi
0x18009ba98  pop     rbx
0x18009ba99  pop     rbp
0x18009ba9a  retn
```
