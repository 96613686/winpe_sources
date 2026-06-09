# NgcUtils::InvokeCredUIBrokerInternal

- ea: `0x18005d8fc`
- end: `0x18005dfc6`
- name: `NgcUtils::InvokeCredUIBrokerInternal`
- size: `1738`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, DWORD dwAuthError, int, __int64, char, __int64, __int64, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005d3e8`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x18000c6e8`
- `0x18000c740`
- `0x180016550`
- `0x180018194`
- `0x180022510`
- `0x18002c640`
- `0x18002d518`
- `0x18002dc54`
- `0x18004e650`
- `0x18005d128`
- `0x18005d17c`
- `0x18005d1b8`
- `0x18005d48c`
- `0x18005d4b4`
- `0x18005d8fc`
- `0x18005e098`
- `0x18005e178`
- `0x18005e424`
- `0x18005e4d0`
- `0x180080010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005dcc1`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18005dcc1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005dbaf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005dbaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dbe4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dae8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005dbe4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005dac9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005dac9`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x18005de74`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x18005de74`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall NgcUtils::InvokeCredUIBrokerInternal(
        void *a1,
        HWND a2,
        __int64 a3,
        __int64 a4,
        DWORD dwAuthError,
        ULONG a6,
        __int64 a7,
        unsigned __int8 a8,
        _QWORD *a9,
        _QWORD *a10,
        char a11,
        __int64 a12,
        _QWORD *a13,
        ULONG *a14)
{
  signed int CancellationEventName; // ebx
  __int64 v19; // rcx
  _BYTE *v20; // rdx
  BOOL v21; // ebx
  DWORD LastError; // eax
  __int64 v23; // rcx
  _BYTE *v24; // rdx
  const WCHAR *v25; // r9
  DWORD v26; // eax
  __int64 v27; // rcx
  _BYTE *v28; // rdx
  LPCWSTR *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rcx
  _BYTE *v32; // rdx
  const WCHAR *v33; // rax
  const WCHAR *v34; // rax
  __int64 v35; // rax
  int hbmBanner; // eax
  __int64 v37; // rcx
  __int64 v38; // rcx
  DWORD dwFlags; // ebx
  struct CREDUI_ADDITIONAL_INFO *v40; // rdx
  struct CREDUI_ADDITIONAL_INFO *v41; // rdx
  __int64 v42; // rcx
  _BYTE *v43; // rdx
  _BYTE *v44; // rax
  __int64 v45; // rcx
  _BYTE *v46; // rdx
  int v48; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v49; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE v50; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+68h] [rbp-98h] BYREF
  ULONG pulAuthPackage; // [rsp+70h] [rbp-90h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+74h] [rbp-8Ch] BYREF
  void *v54; // [rsp+78h] [rbp-88h] BYREF
  void **v55; // [rsp+80h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+88h] [rbp-78h] BYREF
  char v57; // [rsp+90h] [rbp-70h]
  int *v58; // [rsp+98h] [rbp-68h] BYREF
  __int16 v59; // [rsp+A0h] [rbp-60h]
  __int128 *v60; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-48h]
  _QWORD *v63; // [rsp+C0h] [rbp-40h]
  ULONG *v64; // [rsp+C8h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v66; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v67; // [rsp+100h] [rbp+0h]
  __int128 v68; // [rsp+110h] [rbp+10h]
  __int128 v69; // [rsp+120h] [rbp+20h]
  __int128 v70; // [rsp+130h] [rbp+30h]
  _CREDUI_INFOW pUiInfo; // [rsp+140h] [rbp+40h] BYREF
  __int64 v72; // [rsp+168h] [rbp+68h]
  __int64 v73; // [rsp+170h] [rbp+70h]
  __int64 v74; // [rsp+190h] [rbp+90h]
  LPCWSTR *v75; // [rsp+198h] [rbp+98h]
  NgcUtils *v76; // [rsp+1B8h] [rbp+B8h]
  NgcUtils *v77; // [rsp+1C0h] [rbp+C0h]
  LPCWSTR lpName[3]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v79; // [rsp+1E8h] [rbp+E8h]

  v62 = a7;
  v63 = a13;
  v64 = a14;
  v48 = 0;
  v58 = &v48;
  v59 = 256;
  *a13 = 0;
  if ( (unsigned __int8)IsCredUIPromptForWindowsCredentialsWPresent() )
  {
    pulAuthPackage = a6;
    memset_0(&pUiInfo, 0, 0x88u);
    pUiInfo.cbSize = 136;
    pUiInfo.hwndParent = a2;
    LODWORD(pUiInfo.hbmBanner) = 1;
    memset_0(&v66, 0, 0x50u);
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v69 = 0;
    v70 = 0;
    v49 = 0;
    pulOutAuthBufferSize = 0;
    std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)lpName);
    v51 = 0;
    if ( a12 )
    {
      CancellationEventName = NgcUtils::Detail::GetCancellationEventName(a12, lpName);
      v48 = CancellationEventName;
      if ( CancellationEventName < 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v51);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v20 = v49;
        v49 = 0;
        if ( v20 )
          wil::cotaskmem_secure_deleter::operator()<unsigned char>(v19, v20);
LABEL_78:
        NgcUtils::CredUIStrings::~CredUIStrings((NgcUtils::CredUIStrings *)&v66);
        goto LABEL_79;
      }
      v54 = 0;
      v55 = &v54;
      SecurityDescriptor = 0;
      v57 = 1;
      v21 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"O:SYD:(A;;0x001F0003;;;WD)(A;;0x001F0003;;;AC)",
              1u,
              &SecurityDescriptor,
              0);
      wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v55);
      if ( !v21 )
      {
        LastError = GetLastError();
        CancellationEventName = LastError;
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          LODWORD(v50) = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (unsigned __int8 *)byte_1800AE759,
            0,
            0,
            (__int64)&v50);
        }
        if ( CancellationEventName > 0 )
          CancellationEventName = (unsigned __int16)CancellationEventName | 0x80070000;
        v48 = CancellationEventName;
        wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          &v54,
          0);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v51);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v24 = v49;
        v49 = 0;
        if ( v24 )
          wil::cotaskmem_secure_deleter::operator()<unsigned char>(v23, v24);
        goto LABEL_78;
      }
      *(_QWORD *)&EventAttributes.nLength = 24;
      *(_QWORD *)&EventAttributes.bInheritHandle = 0;
      EventAttributes.lpSecurityDescriptor = v54;
      v25 = (const WCHAR *)lpName;
      if ( v79 > 7 )
        v25 = lpName[0];
      v50 = CreateEventW(&EventAttributes, 1, 0, v25);
      __4__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAAAEAV01___QEAV01__Z(
        &v51,
        &v50);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v50);
      if ( !v51 )
      {
        v26 = GetLastError();
        CancellationEventName = v26;
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          LODWORD(v50) = v26;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (unsigned __int8 *)byte_1800AE6E9,
            0,
            0,
            (__int64)&v50);
        }
        if ( CancellationEventName > 0 )
          CancellationEventName = (unsigned __int16)CancellationEventName | 0x80070000;
        v48 = CancellationEventName;
        wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
          &v54,
          0);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v51);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v28 = v49;
        v49 = 0;
        if ( v28 )
          wil::cotaskmem_secure_deleter::operator()<unsigned char>(v27, v28);
        goto LABEL_78;
      }
      v29 = lpName;
      if ( v79 > 7 )
        v29 = (LPCWSTR *)lpName[0];
      v75 = v29;
      wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
        &v54,
        0);
    }
    NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)&v50, a1);
    v60 = &v66;
    v61 = a4;
    v30 = *(_QWORD *)(a3 + 56);
    if ( !v30 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    CancellationEventName = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 **))(*(_QWORD *)v30 + 16LL))(
                              v30,
                              &v61,
                              &v60);
    v48 = CancellationEventName;
    if ( CancellationEventName >= 0 )
    {
      v33 = (const WCHAR *)v66;
      if ( *(_QWORD *)(v66 + 24) > 7u )
        v33 = *(const WCHAR **)v66;
      pUiInfo.pszCaptionText = v33;
      v34 = (const WCHAR *)v67;
      if ( *(_QWORD *)(v67 + 24) > 7u )
        v34 = *(const WCHAR **)v67;
      pUiInfo.pszMessageText = v34;
      v35 = v68;
      if ( *(_QWORD *)(v68 + 16) )
      {
        if ( *(_QWORD *)(v68 + 24) > 7u )
          v35 = *(_QWORD *)v68;
        v74 = v35;
        hbmBanner = LODWORD(pUiInfo.hbmBanner) | 0x800;
        LODWORD(pUiInfo.hbmBanner) |= 0x800u;
      }
      else
      {
        hbmBanner = (int)pUiInfo.hbmBanner;
      }
      v37 = v69;
      if ( *(_QWORD *)(v69 + 16) )
      {
        if ( *(_QWORD *)(v69 + 24) > 7u )
          v37 = *(_QWORD *)v69;
        v72 = v37;
        hbmBanner |= 0x100u;
        LODWORD(pUiInfo.hbmBanner) = hbmBanner;
      }
      v38 = v70;
      if ( *(_QWORD *)(v70 + 16) )
      {
        if ( *(_QWORD *)(v70 + 24) > 7u )
          v38 = *(_QWORD *)v70;
        v73 = v38;
        LODWORD(pUiInfo.hbmBanner) = hbmBanner | 0x200;
      }
      dwFlags = (a8 << 30) + 134218256;
      if ( *a9 != a9[1] )
        v76 = (NgcUtils *)lambda_3a2dbe4c6996697c9f7853101d3d01a2_::operator()();
      if ( *a10 != a10[1] )
        v77 = (NgcUtils *)lambda_3a2dbe4c6996697c9f7853101d3d01a2_::operator()();
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl)
        || *a9 != a9[1]
        || *a10 != a10[1] )
      {
        dwFlags |= 0x40u;
      }
      if ( a11 )
        LODWORD(pUiInfo.hbmBanner) |= 0x80000u;
      v55 = (void **)&v49;
      SecurityDescriptor = 0;
      v57 = 1;
      CancellationEventName = CredUIPromptForWindowsCredentialsW(
                                &pUiInfo,
                                dwAuthError,
                                &pulAuthPackage,
                                *(LPCVOID *)v62,
                                *(_DWORD *)(v62 + 8) - *(_DWORD *)v62,
                                &SecurityDescriptor,
                                &pulOutAuthBufferSize,
                                0,
                                dwFlags);
      wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>>::~out_param_ptr_t<void * *,wistd::unique_ptr<unsigned char,wil::cotaskmem_secure_deleter>>(&v55);
      NgcUtils::CaptureAndRelease(v76, v40);
      NgcUtils::CaptureAndRelease(v77, v41);
      NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)&v50);
      if ( CancellationEventName )
      {
        if ( CancellationEventName == 1223 )
          goto LABEL_69;
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          LODWORD(v50) = CancellationEventName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_1800BE0B8,
            (unsigned __int8 *)byte_1800AE6A9,
            0,
            0,
            (__int64)&v50);
        }
        if ( CancellationEventName > 0 )
LABEL_69:
          CancellationEventName = (unsigned __int16)CancellationEventName | 0x80070000;
        v48 = CancellationEventName;
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v51);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v43 = v49;
        v49 = 0;
        if ( v43 )
          wil::cotaskmem_secure_deleter::operator()<unsigned char>(v42, v43);
      }
      else
      {
        if ( pulAuthPackage == 212664322 )
        {
          CancellationEventName = -2146893778;
          v48 = -2146893778;
        }
        else
        {
          CancellationEventName = v48;
        }
        v44 = v49;
        v49 = 0;
        *v63 = v44;
        *v64 = pulOutAuthBufferSize;
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v51);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v46 = v49;
        v49 = 0;
        if ( v46 )
          wil::cotaskmem_secure_deleter::operator()<unsigned char>(v45, v46);
      }
    }
    else
    {
      NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)&v50);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v51);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
      v32 = v49;
      v49 = 0;
      if ( v32 )
        wil::cotaskmem_secure_deleter::operator()<unsigned char>(v31, v32);
    }
    goto LABEL_78;
  }
  v48 = -2147467263;
  if ( (unsigned int)dword_1800BE0B8 > 2 )
  {
    LODWORD(v50) = v48;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_1800BE0B8,
      (unsigned __int8 *)byte_1800AE713,
      0,
      0,
      (__int64)&v50);
  }
  CancellationEventName = v48;
LABEL_79:
  wil::details::ScopeExitFnGuard__lambda_b6c25e5114ea17ef54c09ac0751f509e___::operator()(&v58);
  return (unsigned int)CancellationEventName;
}

```

## disassembly

```asm
0x18005d8fc  push    rbp
0x18005d8fe  push    rbx
0x18005d8ff  push    rsi
0x18005d900  push    rdi
0x18005d901  push    r12
0x18005d903  push    r13
0x18005d905  push    r14
0x18005d907  push    r15
0x18005d909  lea     rbp, [rsp-108h]
0x18005d911  sub     rsp, 208h
0x18005d918  mov     rax, cs:__security_cookie
0x18005d91f  xor     rax, rsp
0x18005d922  mov     [rbp+140h+var_50], rax
0x18005d929  mov     r12, r9
0x18005d92c  mov     r13, r8
0x18005d92f  mov     r14, rdx
0x18005d932  mov     r15, rcx
0x18005d935  mov     rax, [rbp+140h+arg_30]
0x18005d93c  mov     [rbp+140h+var_188], rax
0x18005d940  mov     rdi, [rbp+140h+arg_48]
0x18005d947  mov     rsi, [rbp+140h+arg_40]
0x18005d94e  mov     rbx, [rbp+140h+arg_58]
0x18005d955  mov     rax, [rbp+140h+arg_60]
0x18005d95c  mov     [rbp+140h+var_180], rax
0x18005d960  mov     rcx, [rbp+140h+arg_68]
0x18005d967  mov     [rbp+140h+var_178], rcx
0x18005d96b  xor     edx, edx
0x18005d96d  mov     [rsp+240h+var_1F0], edx
0x18005d971  lea     rcx, [rsp+240h+var_1F0]
0x18005d976  mov     [rbp+140h+var_1A8], rcx
0x18005d97a  mov     [rbp+140h+var_1A0], 100h
0x18005d980  mov     [rax], rdx
0x18005d983  call    IsCredUIPromptForWindowsCredentialsWPresent
0x18005d988  test    al, al
0x18005d98a  jnz     short loc_18005D9D3
0x18005d98c  mov     [rsp+240h+var_1F0], 80004001h
0x18005d994  mov     eax, cs:dword_1800BE0B8
0x18005d99a  cmp     eax, 2
0x18005d99d  jbe     short loc_18005D9CA
0x18005d99f  mov     eax, [rsp+240h+var_1F0]
0x18005d9a3  mov     dword ptr [rsp+240h+var_1E0], eax
0x18005d9a7  lea     rax, [rsp+240h+var_1E0]
0x18005d9ac  mov     qword ptr [rsp+240h+ulInAuthBufferSize], rax
0x18005d9b1  xor     r9d, r9d
0x18005d9b4  xor     r8d, r8d
0x18005d9b7  lea     rdx, byte_1800AE713
0x18005d9be  lea     rcx, dword_1800BE0B8
0x18005d9c5  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005d9ca  mov     ebx, [rsp+240h+var_1F0]
0x18005d9ce  jmp     loc_18005DF97
0x18005d9d3  mov     eax, [rbp+140h+arg_28]
0x18005d9d9  mov     [rsp+240h+pulAuthPackage], eax
0x18005d9dd  xor     edx, edx; Val
0x18005d9df  mov     r8d, 88h; Size
0x18005d9e5  lea     rcx, [rbp+140h+pUiInfo]; void *
0x18005d9e9  call    memset_0
0x18005d9ee  mov     [rbp+140h+pUiInfo.cbSize], 88h
0x18005d9f5  mov     [rbp+140h+pUiInfo.hwndParent], r14
0x18005d9f9  mov     dword ptr [rbp+140h+pUiInfo.hbmBanner], 1
0x18005da00  xor     edx, edx; Val
0x18005da02  lea     r8d, [rdx+50h]; Size
0x18005da06  lea     rcx, [rbp+140h+var_150]; void *
0x18005da0a  call    memset_0
0x18005da0f  xorps   xmm0, xmm0
0x18005da12  movdqa  [rbp+140h+var_150], xmm0
0x18005da17  xorps   xmm1, xmm1
0x18005da1a  movdqa  [rbp+140h+var_140], xmm1
0x18005da1f  movdqa  [rbp+140h+var_130], xmm0
0x18005da24  movdqa  [rbp+140h+var_120], xmm1
0x18005da29  movdqa  [rbp+140h+var_110], xmm0
0x18005da2e  xor     r14d, r14d
0x18005da31  mov     [rsp+240h+var_1E8], r14
0x18005da36  mov     [rsp+240h+var_1CC], r14d
0x18005da3b  lea     rcx, [rbp+140h+lpName]
0x18005da42  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18005da47  nop
0x18005da48  mov     [rsp+240h+var_1D8], r14
0x18005da4d  test    rbx, rbx
0x18005da50  jz      loc_18005DC9E
0x18005da56  lea     rdx, [rbp+140h+lpName]
0x18005da5d  mov     rcx, rbx
0x18005da60  call    ?GetCancellationEventName@Detail@NgcUtils@@YAJAEBU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::Detail::GetCancellationEventName(_GUID const &,std::wstring *)
0x18005da65  mov     ebx, eax
0x18005da67  mov     [rsp+240h+var_1F0], eax
0x18005da6b  test    eax, eax
0x18005da6d  jns     short loc_18005DAA1
0x18005da6f  lea     rcx, [rsp+240h+var_1D8]
0x18005da74  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005da79  nop
0x18005da7a  lea     rcx, [rbp+140h+lpName]
0x18005da81  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005da86  nop
0x18005da87  mov     rdx, [rsp+240h+var_1E8]
0x18005da8c  mov     [rsp+240h+var_1E8], r14
0x18005da91  test    rdx, rdx
0x18005da94  jz      short loc_18005DA9C
0x18005da96  call    ??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z; wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)
0x18005da9b  nop
0x18005da9c  jmp     loc_18005DF8D
0x18005daa1  mov     [rsp+240h+var_1C8], r14
0x18005daa6  lea     rax, [rsp+240h+var_1C8]
0x18005daab  mov     [rbp+140h+var_1C0], rax
0x18005daaf  mov     [rbp+140h+SecurityDescriptor], r14
0x18005dab3  mov     [rbp+140h+var_1B0], 1
0x18005dab7  xor     r9d, r9d; SecurityDescriptorSize
0x18005daba  lea     r8, [rbp+140h+SecurityDescriptor]; SecurityDescriptor
0x18005dabe  lea     edx, [r9+1]; StringSDRevision
0x18005dac2  lea     rcx, aOSydA0x001f000; "O:SYD:(A;;0x001F0003;;;WD)(A;;0x001F000"...
0x18005dac9  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005dad0  nop     dword ptr [rax+rax+00h]
0x18005dad5  mov     ebx, eax
0x18005dad7  lea     rcx, [rbp+140h+var_1C0]
0x18005dadb  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x18005dae0  test    ebx, ebx
0x18005dae2  jnz     loc_18005DB78
0x18005dae8  call    cs:__imp_GetLastError
0x18005daef  nop     dword ptr [rax+rax+00h]
0x18005daf4  mov     ebx, eax
0x18005daf6  mov     ecx, cs:dword_1800BE0B8
0x18005dafc  cmp     ecx, 2
0x18005daff  jbe     short loc_18005DB28
0x18005db01  mov     dword ptr [rsp+240h+var_1E0], eax
0x18005db05  lea     rax, [rsp+240h+var_1E0]
0x18005db0a  mov     qword ptr [rsp+240h+ulInAuthBufferSize], rax
0x18005db0f  xor     r9d, r9d
0x18005db12  xor     r8d, r8d
0x18005db15  lea     rdx, byte_1800AE759
0x18005db1c  lea     rcx, dword_1800BE0B8
0x18005db23  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005db28  test    ebx, ebx
0x18005db2a  jle     short loc_18005DB35
0x18005db2c  movzx   ebx, bx
0x18005db2f  or      ebx, 80070000h
0x18005db35  mov     [rsp+240h+var_1F0], ebx
0x18005db39  xor     edx, edx
0x18005db3b  lea     rcx, [rsp+240h+var_1C8]
0x18005db40  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x18005db45  nop
0x18005db46  lea     rcx, [rsp+240h+var_1D8]
0x18005db4b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005db50  nop
0x18005db51  lea     rcx, [rbp+140h+lpName]
0x18005db58  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005db5d  nop
0x18005db5e  mov     rdx, [rsp+240h+var_1E8]
0x18005db63  mov     [rsp+240h+var_1E8], r14
0x18005db68  test    rdx, rdx
0x18005db6b  jz      short loc_18005DB73
0x18005db6d  call    ??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z; wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)
0x18005db72  nop
0x18005db73  jmp     loc_18005DF8D
0x18005db78  mov     qword ptr [rbp+140h+EventAttributes.nLength], 18h
0x18005db80  mov     qword ptr [rbp+140h+EventAttributes.bInheritHandle], r14
0x18005db84  mov     rax, [rsp+240h+var_1C8]
0x18005db89  mov     [rbp+140h+EventAttributes.lpSecurityDescriptor], rax
0x18005db8d  lea     r9, [rbp+140h+lpName]
0x18005db94  cmp     [rbp+140h+var_58], 7
0x18005db9c  cmova   r9, [rbp+140h+lpName]; lpName
0x18005dba4  xor     r8d, r8d; bInitialState
0x18005dba7  lea     edx, [r8+1]; bManualReset
0x18005dbab  lea     rcx, [rbp+140h+EventAttributes]; lpEventAttributes
0x18005dbaf  call    cs:__imp_CreateEventW
0x18005dbb6  nop     dword ptr [rax+rax+00h]
0x18005dbbb  mov     [rsp+240h+var_1E0], rax
0x18005dbc0  lea     rdx, [rsp+240h+var_1E0]
0x18005dbc5  lea     rcx, [rsp+240h+var_1D8]
0x18005dbca  call    ??4?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z
0x18005dbcf  lea     rcx, [rsp+240h+var_1E0]
0x18005dbd4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005dbd9  cmp     [rsp+240h+var_1D8], r14
0x18005dbde  jnz     loc_18005DC74
0x18005dbe4  call    cs:__imp_GetLastError
0x18005dbeb  nop     dword ptr [rax+rax+00h]
0x18005dbf0  mov     ebx, eax
0x18005dbf2  mov     ecx, cs:dword_1800BE0B8
0x18005dbf8  cmp     ecx, 2
0x18005dbfb  jbe     short loc_18005DC24
0x18005dbfd  mov     dword ptr [rsp+240h+var_1E0], eax
0x18005dc01  lea     rax, [rsp+240h+var_1E0]
0x18005dc06  mov     qword ptr [rsp+240h+ulInAuthBufferSize], rax
0x18005dc0b  xor     r9d, r9d
0x18005dc0e  xor     r8d, r8d
0x18005dc11  lea     rdx, byte_1800AE6E9
0x18005dc18  lea     rcx, dword_1800BE0B8
0x18005dc1f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005dc24  test    ebx, ebx
0x18005dc26  jle     short loc_18005DC31
0x18005dc28  movzx   ebx, bx
0x18005dc2b  or      ebx, 80070000h
0x18005dc31  mov     [rsp+240h+var_1F0], ebx
0x18005dc35  xor     edx, edx
0x18005dc37  lea     rcx, [rsp+240h+var_1C8]
0x18005dc3c  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x18005dc41  nop
0x18005dc42  lea     rcx, [rsp+240h+var_1D8]
0x18005dc47  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005dc4c  nop
0x18005dc4d  lea     rcx, [rbp+140h+lpName]
0x18005dc54  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005dc59  nop
0x18005dc5a  mov     rdx, [rsp+240h+var_1E8]
0x18005dc5f  mov     [rsp+240h+var_1E8], r14
0x18005dc64  test    rdx, rdx
0x18005dc67  jz      short loc_18005DC6F
0x18005dc69  call    ??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z; wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)
0x18005dc6e  nop
0x18005dc6f  jmp     loc_18005DF8D
0x18005dc74  lea     rax, [rbp+140h+lpName]
0x18005dc7b  cmp     [rbp+140h+var_58], 7
0x18005dc83  cmova   rax, [rbp+140h+lpName]
0x18005dc8b  mov     [rbp+140h+var_A8], rax
0x18005dc92  xor     edx, edx
0x18005dc94  lea     rcx, [rsp+240h+var_1C8]
0x18005dc99  call    ?reset@?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_SECURITY_DESCRIPTOR@@@Z; wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_SECURITY_DESCRIPTOR *)
0x18005dc9e  mov     rdx, r15; void *
0x18005dca1  lea     rcx, [rsp+240h+var_1E0]; this
0x18005dca6  call    ??0RpcCallerImpersonator@NgcUtils@@QEAA@QEAX@Z; NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator(void * const)
0x18005dcab  nop
0x18005dcac  lea     rax, [rbp+140h+var_150]
0x18005dcb0  mov     [rbp+140h+var_198], rax
0x18005dcb4  mov     [rbp+140h+var_190], r12
0x18005dcb8  mov     rcx, [r13+38h]
0x18005dcbc  test    rcx, rcx
0x18005dcbf  jnz     short loc_18005DCCE
0x18005dcc1  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18005dcc8  nop     dword ptr [rax+rax+00h]
0x18005dccd  int     3; Trap to Debugger
0x18005dcce  mov     rax, [rcx]
0x18005dcd1  lea     r8, [rbp+140h+var_198]
0x18005dcd5  lea     rdx, [rbp+140h+var_190]
0x18005dcd9  mov     rax, [rax+10h]
0x18005dcdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005dce2  mov     ebx, eax
0x18005dce4  mov     [rsp+240h+var_1F0], eax
0x18005dce8  test    eax, eax
0x18005dcea  jns     short loc_18005DD29
0x18005dcec  lea     rcx, [rsp+240h+var_1E0]; this
0x18005dcf1  call    ??1RpcCallerImpersonator@NgcUtils@@QEAA@XZ; NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator(void)
0x18005dcf6  nop
0x18005dcf7  lea     rcx, [rsp+240h+var_1D8]
0x18005dcfc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005dd01  nop
0x18005dd02  lea     rcx, [rbp+140h+lpName]
0x18005dd09  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18005dd0e  nop
0x18005dd0f  mov     rdx, [rsp+240h+var_1E8]
0x18005dd14  mov     [rsp+240h+var_1E8], r14
0x18005dd19  test    rdx, rdx
0x18005dd1c  jz      short loc_18005DD24
0x18005dd1e  call    ??$?RE@cotaskmem_secure_deleter@wil@@QEBAXPEAE@Z; wil::cotaskmem_secure_deleter::operator()<uchar>(uchar *)
0x18005dd23  nop
0x18005dd24  jmp     loc_18005DF8D
0x18005dd29  mov     rax, qword ptr [rbp+140h+var_150]
0x18005dd2d  cmp     qword ptr [rax+18h], 7
0x18005dd32  jbe     short loc_18005DD37
0x18005dd34  mov     rax, [rax]
0x18005dd37  mov     [rbp+140h+pUiInfo.pszCaptionText], rax
0x18005dd3b  mov     rax, qword ptr [rbp+140h+var_140]
0x18005dd3f  cmp     qword ptr [rax+18h], 7
0x18005dd44  jbe     short loc_18005DD49
0x18005dd46  mov     rax, [rax]
0x18005dd49  mov     [rbp+140h+pUiInfo.pszMessageText], rax
0x18005dd4d  mov     rax, qword ptr [rbp+140h+var_130]
0x18005dd51  cmp     [rax+10h], r14
0x18005dd55  jz      short loc_18005DD74
0x18005dd57  cmp     qword ptr [rax+18h], 7
0x18005dd5c  jbe     short loc_18005DD61
0x18005dd5e  mov     rax, [rax]
0x18005dd61  mov     [rbp+140h+var_B0], rax
0x18005dd68  mov     eax, dword ptr [rbp+140h+pUiInfo.hbmBanner]
0x18005dd6b  bts     eax, 0Bh
0x18005dd6f  mov     dword ptr [rbp+140h+pUiInfo.hbmBanner], eax
0x18005dd72  jmp     short loc_18005DD77
0x18005dd74  mov     eax, dword ptr [rbp+140h+pUiInfo.hbmBanner]
0x18005dd77  mov     rcx, qword ptr [rbp+140h+var_120]
0x18005dd7b  cmp     [rcx+10h], r14
0x18005dd7f  jz      short loc_18005DD96
0x18005dd81  cmp     qword ptr [rcx+18h], 7
0x18005dd86  jbe     short loc_18005DD8B
0x18005dd88  mov     rcx, [rcx]
0x18005dd8b  mov     [rbp+140h+var_D8], rcx
0x18005dd8f  bts     eax, 8
0x18005dd93  mov     dword ptr [rbp+140h+pUiInfo.hbmBanner], eax
0x18005dd96  mov     rcx, qword ptr [rbp+140h+var_110]
0x18005dd9a  cmp     [rcx+10h], r14
0x18005dd9e  jz      short loc_18005DDB5
0x18005dda0  cmp     qword ptr [rcx+18h], 7
0x18005dda5  jbe     short loc_18005DDAA
0x18005dda7  mov     rcx, [rcx]
0x18005ddaa  mov     [rbp+140h+var_D0], rcx
0x18005ddae  bts     eax, 9
0x18005ddb2  mov     dword ptr [rbp+140h+pUiInfo.hbmBanner], eax
0x18005ddb5  movzx   ebx, [rbp+140h+arg_38]
0x18005ddbc  shl     ebx, 1Eh
0x18005ddbf  add     ebx, 8000210h
0x18005ddc5  mov     rax, [rsi+8]
0x18005ddc9  cmp     [rsi], rax
0x18005ddcc  jz      short loc_18005DDDD
0x18005ddce  mov     rdx, rsi
0x18005ddd1  call    _lambda_3a2dbe4c6996697c9f7853101d3d01a2___operator__
  ... truncated ...
```
