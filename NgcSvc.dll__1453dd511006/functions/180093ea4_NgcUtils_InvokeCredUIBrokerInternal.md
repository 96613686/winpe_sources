# NgcUtils::InvokeCredUIBrokerInternal

- ea: `0x180093ea4`
- end: `0x180094567`
- name: `NgcUtils::InvokeCredUIBrokerInternal`
- size: `1731`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, DWORD dwAuthError, int, __int64, char, __int64, __int64, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180093940`

## callees

- `0x18000948c`
- `0x18000e960`
- `0x180028d18`
- `0x18002c9d8`
- `0x1800320a0`
- `0x180045d60`
- `0x18004884c`
- `0x18005cee0`
- `0x18005dd44`
- `0x18005f5c8`
- `0x18006caa4`
- `0x1800811ac`
- `0x180081408`
- `0x1800936c8`
- `0x1800939e4`
- `0x180093a8c`
- `0x180093ea4`
- `0x180094a6c`
- `0x180097364`
- `0x1800cd010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180094266`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180094266`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180094165`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180094165`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009409b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009409b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094186`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800940f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800941e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009423b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800940f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800941e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009423b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180094081`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180094081`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x180094416`
- `ext-ms-win-security-credui-l1-1-0!CredUIPromptForWindowsCredentialsW` at `0x180094416`

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
  signed int CancellationEventName; // edi
  wil::details *v19; // rbx
  __int64 v20; // rcx
  _BYTE *v21; // rdx
  BOOL v22; // ebx
  DWORD LastError; // eax
  signed int v24; // ebx
  HLOCAL v25; // rcx
  __int64 v26; // rcx
  _BYTE *v27; // rdx
  const WCHAR *v28; // r9
  HANDLE v29; // rax
  DWORD v30; // eax
  HLOCAL v31; // rcx
  __int64 v32; // rcx
  _BYTE *v33; // rdx
  LPCWSTR *v34; // rax
  HLOCAL v35; // rcx
  __int64 v36; // rcx
  void *v37; // rdx
  __int64 v38; // rcx
  _BYTE *v39; // rdx
  const WCHAR *v40; // rax
  const WCHAR *v41; // rax
  __int64 v42; // rax
  int hbmBanner; // eax
  __int64 v44; // rcx
  __int64 v45; // rcx
  DWORD dwFlags; // edi
  struct CREDUI_ADDITIONAL_INFO *v47; // rdx
  struct CREDUI_ADDITIONAL_INFO *v48; // rdx
  void *v49; // rdx
  __int64 v50; // rcx
  _BYTE *v51; // rdx
  _BYTE *v52; // rax
  __int64 v53; // rcx
  _BYTE *v54; // rdx
  int v56; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v57; // [rsp+58h] [rbp-A8h] BYREF
  wil::details *v58; // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  ULONG pulAuthPackage; // [rsp+70h] [rbp-90h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+74h] [rbp-8Ch] BYREF
  HLOCAL *p_hMem; // [rsp+78h] [rbp-88h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp-80h] BYREF
  char v64; // [rsp+88h] [rbp-78h]
  char v65[8]; // [rsp+90h] [rbp-70h] BYREF
  int *v66; // [rsp+98h] [rbp-68h] BYREF
  __int16 v67; // [rsp+A0h] [rbp-60h]
  __int128 *v68; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v69; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-48h]
  _QWORD *v71; // [rsp+C0h] [rbp-40h]
  ULONG *v72; // [rsp+C8h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v74; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v75; // [rsp+100h] [rbp+0h]
  __int128 v76; // [rsp+110h] [rbp+10h]
  __int128 v77; // [rsp+120h] [rbp+20h]
  __int128 v78; // [rsp+130h] [rbp+30h]
  _CREDUI_INFOW pUiInfo; // [rsp+140h] [rbp+40h] BYREF
  __int64 v80; // [rsp+168h] [rbp+68h]
  __int64 v81; // [rsp+170h] [rbp+70h]
  __int64 v82; // [rsp+190h] [rbp+90h]
  LPCWSTR *v83; // [rsp+198h] [rbp+98h]
  NgcUtils *v84; // [rsp+1B8h] [rbp+B8h]
  NgcUtils *v85; // [rsp+1C0h] [rbp+C0h]
  LPCWSTR lpName[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  __m128i si128; // [rsp+1E0h] [rbp+E0h]

  v70 = a7;
  v71 = a13;
  v72 = a14;
  v56 = 0;
  v66 = &v56;
  v67 = 256;
  *a13 = 0;
  if ( (unsigned __int8)IsCredUIPromptForWindowsCredentialsWPresent() )
  {
    pulAuthPackage = a6;
    memset_0(&pUiInfo, 0, 0x88u);
    pUiInfo.cbSize = 136;
    pUiInfo.hwndParent = a2;
    LODWORD(pUiInfo.hbmBanner) = 1;
    memset_0(&v74, 0, 0x50u);
    v74 = 0;
    v75 = 0;
    v76 = 0;
    v77 = 0;
    v78 = 0;
    v57 = 0;
    pulOutAuthBufferSize = 0;
    *(_OWORD *)lpName = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(lpName[0]) = 0;
    v19 = 0;
    v58 = 0;
    if ( a12 )
    {
      CancellationEventName = NgcUtils::Detail::GetCancellationEventName(a12, lpName);
      v56 = CancellationEventName;
      if ( CancellationEventName < 0 )
      {
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v21 = v57;
        v57 = 0;
        if ( v21 )
          wil::cotaskmem_secure_deleter::operator()<unsigned short>(v20, v21);
LABEL_89:
        NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)&v74);
        goto LABEL_90;
      }
      hMem = 0;
      p_hMem = &hMem;
      SecurityDescriptor = 0;
      v64 = 1;
      v22 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"O:SYD:(A;;0x001F0003;;;WD)(A;;0x001F0003;;;AC)",
              1u,
              &SecurityDescriptor,
              0);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>((__int64)&p_hMem);
      if ( !v22 )
      {
        LastError = GetLastError();
        v24 = LastError;
        if ( (unsigned int)dword_180122070 > 2 )
        {
          LODWORD(v58) = LastError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)&dword_180107EFC,
            0,
            0,
            (__int64)&v58);
        }
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        v56 = v24;
        v25 = hMem;
        hMem = 0;
        if ( v25 )
          LocalFree(v25);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v27 = v57;
        v57 = 0;
        if ( v27 )
          wil::cotaskmem_secure_deleter::operator()<unsigned short>(v26, v27);
LABEL_19:
        NgcKspServer::CredUIStringsContext::~CredUIStringsContext((NgcKspServer::CredUIStringsContext *)&v74);
        CancellationEventName = v24;
        goto LABEL_90;
      }
      *(_QWORD *)&EventAttributes.nLength = 24;
      *(_QWORD *)&EventAttributes.bInheritHandle = 0;
      EventAttributes.lpSecurityDescriptor = hMem;
      v28 = (const WCHAR *)lpName;
      if ( si128.m128i_i64[1] > 7uLL )
        v28 = lpName[0];
      v29 = CreateEventW(&EventAttributes, 1, 0, v28);
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        &v58,
        v29);
      v19 = v58;
      if ( !v58 )
      {
        v30 = GetLastError();
        v24 = v30;
        if ( (unsigned int)dword_180122070 > 2 )
        {
          LODWORD(v58) = v30;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)word_180107ED2,
            0,
            0,
            (__int64)&v58);
        }
        if ( v24 > 0 )
          v24 = (unsigned __int16)v24 | 0x80070000;
        v56 = v24;
        v31 = hMem;
        hMem = 0;
        if ( v31 )
          LocalFree(v31);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v33 = v57;
        v57 = 0;
        if ( v33 )
          wil::cotaskmem_secure_deleter::operator()<unsigned short>(v32, v33);
        goto LABEL_19;
      }
      v34 = lpName;
      if ( si128.m128i_i64[1] > 7uLL )
        v34 = (LPCWSTR *)lpName[0];
      v83 = v34;
      v35 = hMem;
      hMem = 0;
      if ( v35 )
        LocalFree(v35);
    }
    NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)v65, a1);
    v68 = &v74;
    v69 = a4;
    v36 = *(_QWORD *)(a3 + 56);
    if ( !v36 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    CancellationEventName = (*(__int64 (__fastcall **)(__int64, __int64 *, __int128 **))(*(_QWORD *)v36 + 16LL))(
                              v36,
                              &v69,
                              &v68);
    v56 = CancellationEventName;
    if ( CancellationEventName >= 0 )
    {
      v40 = (const WCHAR *)v74;
      if ( *(_QWORD *)(v74 + 24) > 7u )
        v40 = *(const WCHAR **)v74;
      pUiInfo.pszCaptionText = v40;
      v41 = (const WCHAR *)v75;
      if ( *(_QWORD *)(v75 + 24) > 7u )
        v41 = *(const WCHAR **)v75;
      pUiInfo.pszMessageText = v41;
      v42 = v76;
      if ( *(_QWORD *)(v76 + 16) )
      {
        if ( *(_QWORD *)(v76 + 24) > 7u )
          v42 = *(_QWORD *)v76;
        v82 = v42;
        hbmBanner = LODWORD(pUiInfo.hbmBanner) | 0x800;
        LODWORD(pUiInfo.hbmBanner) |= 0x800u;
      }
      else
      {
        hbmBanner = (int)pUiInfo.hbmBanner;
      }
      v44 = v77;
      if ( *(_QWORD *)(v77 + 16) )
      {
        if ( *(_QWORD *)(v77 + 24) > 7u )
          v44 = *(_QWORD *)v77;
        v80 = v44;
        hbmBanner |= 0x100u;
        LODWORD(pUiInfo.hbmBanner) = hbmBanner;
      }
      v45 = v78;
      if ( *(_QWORD *)(v78 + 16) )
      {
        if ( *(_QWORD *)(v78 + 24) > 7u )
          v45 = *(_QWORD *)v78;
        v81 = v45;
        LODWORD(pUiInfo.hbmBanner) = hbmBanner | 0x200;
      }
      dwFlags = (a8 << 30) + 134218256;
      if ( *a9 != a9[1] )
        v84 = (NgcUtils *)lambda_3a2dbe4c6996697c9f7853101d3d01a2_::operator()(v45, a9);
      if ( *a10 != a10[1] )
        v85 = (NgcUtils *)lambda_3a2dbe4c6996697c9f7853101d3d01a2_::operator()(v45, a10);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PasskeyPluginAuthenticators>::GetImpl'::`2'::impl)
        || *a9 != a9[1]
        || *a10 != a10[1] )
      {
        dwFlags |= 0x40u;
      }
      if ( a11 )
        LODWORD(pUiInfo.hbmBanner) |= 0x80000u;
      p_hMem = (HLOCAL *)&v57;
      SecurityDescriptor = 0;
      v64 = 1;
      CancellationEventName = CredUIPromptForWindowsCredentialsW(
                                &pUiInfo,
                                dwAuthError,
                                &pulAuthPackage,
                                *(LPCVOID *)v70,
                                *(_DWORD *)(v70 + 8) - *(_DWORD *)v70,
                                &SecurityDescriptor,
                                &pulOutAuthBufferSize,
                                0,
                                dwFlags);
      wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::cotaskmem_secure_deleter>>((__int64)&p_hMem);
      NgcUtils::CaptureAndRelease(v84, v47);
      NgcUtils::CaptureAndRelease(v85, v48);
      NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)v65);
      if ( CancellationEventName )
      {
        if ( CancellationEventName == 1223 )
          goto LABEL_76;
        if ( (unsigned int)dword_180122070 > 2 )
        {
          LODWORD(v58) = CancellationEventName;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (__int64)&dword_180122070,
            (unsigned __int8 *)word_180107E92,
            0,
            0,
            (__int64)&v58);
        }
        if ( CancellationEventName > 0 )
LABEL_76:
          CancellationEventName = (unsigned __int16)CancellationEventName | 0x80070000;
        v56 = CancellationEventName;
        if ( v19 )
          wil::details::CloseHandle(v19, v49);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v51 = v57;
        v57 = 0;
        if ( v51 )
          wil::cotaskmem_secure_deleter::operator()<unsigned short>(v50, v51);
      }
      else
      {
        if ( pulAuthPackage == 212664322 )
        {
          CancellationEventName = -2146893778;
          v56 = -2146893778;
        }
        else
        {
          CancellationEventName = v56;
        }
        v52 = v57;
        v57 = 0;
        *v71 = v52;
        *v72 = pulOutAuthBufferSize;
        if ( v19 )
          wil::details::CloseHandle(v19, v49);
        std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
        v54 = v57;
        v57 = 0;
        if ( v54 )
          wil::cotaskmem_secure_deleter::operator()<unsigned short>(v53, v54);
      }
    }
    else
    {
      NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)v65);
      if ( v19 )
        wil::details::CloseHandle(v19, v37);
      std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpName);
      v39 = v57;
      v57 = 0;
      if ( v39 )
        wil::cotaskmem_secure_deleter::operator()<unsigned short>(v38, v39);
    }
    goto LABEL_89;
  }
  v56 = -2147467263;
  if ( (unsigned int)dword_180122070 > 2 )
  {
    LODWORD(v58) = v56;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (__int64)&dword_180122070,
      (unsigned __int8 *)&word_180107F4E,
      0,
      0,
      (__int64)&v58);
  }
  CancellationEventName = v56;
LABEL_90:
  wil::details::ScopeExitFnGuard__lambda_b6c25e5114ea17ef54c09ac0751f509e___::operator()(&v66);
  return (unsigned int)CancellationEventName;
}

```

## disassembly

```asm
0x180093ea4  push    rbp
0x180093ea6  push    rbx
0x180093ea7  push    rsi
0x180093ea8  push    rdi
0x180093ea9  push    r12
0x180093eab  push    r13
0x180093ead  push    r14
0x180093eaf  push    r15
0x180093eb1  lea     rbp, [rsp-108h]
0x180093eb9  sub     rsp, 208h
0x180093ec0  mov     rax, cs:__security_cookie
0x180093ec7  xor     rax, rsp
0x180093eca  mov     [rbp+140h+var_50], rax
0x180093ed1  mov     r12, r9
0x180093ed4  mov     r13, r8
0x180093ed7  mov     rbx, rdx
0x180093eda  mov     r15, rcx
0x180093edd  mov     rax, [rbp+140h+arg_30]
0x180093ee4  mov     [rbp+140h+var_188], rax
0x180093ee8  mov     rsi, [rbp+140h+arg_48]
0x180093eef  mov     r14, [rbp+140h+arg_40]
0x180093ef6  mov     rdi, [rbp+140h+arg_58]
0x180093efd  mov     rax, [rbp+140h+arg_60]
0x180093f04  mov     [rbp+140h+var_180], rax
0x180093f08  mov     rcx, [rbp+140h+arg_68]
0x180093f0f  mov     [rbp+140h+var_178], rcx
0x180093f13  xor     edx, edx
0x180093f15  mov     [rsp+240h+var_1F0], edx
0x180093f19  lea     rcx, [rsp+240h+var_1F0]
0x180093f1e  mov     [rbp+140h+var_1A8], rcx
0x180093f22  mov     [rbp+140h+var_1A0], 100h
0x180093f28  mov     [rax], rdx
0x180093f2b  call    IsCredUIPromptForWindowsCredentialsWPresent
0x180093f30  test    al, al
0x180093f32  jnz     short loc_180093F7B
0x180093f34  mov     [rsp+240h+var_1F0], 80004001h
0x180093f3c  mov     eax, cs:dword_180122070
0x180093f42  cmp     eax, 2
0x180093f45  jbe     short loc_180093F72
0x180093f47  mov     eax, [rsp+240h+var_1F0]
0x180093f4b  mov     dword ptr [rsp+240h+var_1E0], eax
0x180093f4f  lea     rax, [rsp+240h+var_1E0]
0x180093f54  mov     qword ptr [rsp+240h+ulInAuthBufferSize], rax
0x180093f59  xor     r9d, r9d
0x180093f5c  xor     r8d, r8d
0x180093f5f  lea     rdx, word_180107F4E
0x180093f66  lea     rcx, dword_180122070
0x180093f6d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180093f72  mov     edi, [rsp+240h+var_1F0]
0x180093f76  jmp     loc_180094539
0x180093f7b  mov     eax, [rbp+140h+arg_28]
0x180093f81  mov     [rsp+240h+pulAuthPackage], eax
0x180093f85  xor     edx, edx; Val
0x180093f87  mov     r8d, 88h; Size
0x180093f8d  lea     rcx, [rbp+140h+pUiInfo]; void *
0x180093f91  call    memset_0
0x180093f96  mov     [rbp+140h+pUiInfo.cbSize], 88h
0x180093f9d  mov     [rbp+140h+pUiInfo.hwndParent], rbx
0x180093fa1  mov     dword ptr [rbp+140h+pUiInfo.hbmBanner], 1
0x180093fa8  xor     edx, edx; Val
0x180093faa  lea     r8d, [rdx+50h]; Size
0x180093fae  lea     rcx, [rbp+140h+var_150]; void *
0x180093fb2  call    memset_0
0x180093fb7  xorps   xmm0, xmm0
0x180093fba  movdqa  [rbp+140h+var_150], xmm0
0x180093fbf  xorps   xmm1, xmm1
0x180093fc2  movdqa  [rbp+140h+var_140], xmm1
0x180093fc7  movdqa  [rbp+140h+var_130], xmm0
0x180093fcc  movdqa  [rbp+140h+var_120], xmm1
0x180093fd1  movdqa  [rbp+140h+var_110], xmm0
0x180093fd6  mov     [rsp+240h+var_1E8], 0
0x180093fdf  mov     [rsp+240h+var_1CC], 0
0x180093fe7  movups  xmmword ptr [rbp+140h+lpName], xmm0
0x180093fee  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180093ff6  movdqu  [rbp+140h+var_60], xmm1
0x180093ffe  xor     eax, eax
0x180094000  mov     word ptr [rbp+140h+lpName], ax
0x180094007  xor     ebx, ebx
0x180094009  mov     [rsp+240h+var_1E0], rbx
0x18009400e  test    rdi, rdi
0x180094011  jz      loc_180094241
0x180094017  lea     rdx, [rbp+140h+lpName]
0x18009401e  mov     rcx, rdi
0x180094021  call    ?GetCancellationEventName@Detail@NgcUtils@@YAJAEBU_GUID@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; NgcUtils::Detail::GetCancellationEventName(_GUID const &,std::wstring *)
0x180094026  mov     edi, eax
0x180094028  mov     [rsp+240h+var_1F0], eax
0x18009402c  test    eax, eax
0x18009402e  jns     short loc_180094057
0x180094030  lea     rcx, [rbp+140h+lpName]
0x180094037  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18009403c  nop
0x18009403d  mov     rdx, [rsp+240h+var_1E8]
0x180094042  mov     [rsp+240h+var_1E8], rbx
0x180094047  test    rdx, rdx
0x18009404a  jz      short loc_180094052
0x18009404c  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180094051  nop
0x180094052  jmp     loc_18009452F
0x180094057  xor     edi, edi
0x180094059  mov     [rsp+240h+hMem], rdi
0x18009405e  lea     rax, [rsp+240h+hMem]
0x180094063  mov     [rsp+240h+var_1C8], rax
0x180094068  mov     [rbp+140h+SecurityDescriptor], rdi
0x18009406c  mov     [rbp+140h+var_1B8], 1
0x180094070  xor     r9d, r9d; SecurityDescriptorSize
0x180094073  lea     r8, [rbp+140h+SecurityDescriptor]; SecurityDescriptor
0x180094077  lea     edx, [rdi+1]; StringSDRevision
0x18009407a  lea     rcx, aOSydA0x001f000; "O:SYD:(A;;0x001F0003;;;WD)(A;;0x001F000"...
0x180094081  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180094087  mov     ebx, eax
0x180094089  lea     rcx, [rsp+240h+var_1C8]
0x18009408e  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180094093  test    ebx, ebx
0x180094095  jnz     loc_18009412E
0x18009409b  call    cs:__imp_GetLastError
0x1800940a1  mov     ebx, eax
0x1800940a3  mov     ecx, cs:dword_180122070
0x1800940a9  cmp     ecx, 2
0x1800940ac  jbe     short loc_1800940D5
0x1800940ae  mov     dword ptr [rsp+240h+var_1E0], eax
0x1800940b2  lea     rax, [rsp+240h+var_1E0]
0x1800940b7  mov     qword ptr [rsp+240h+ulInAuthBufferSize], rax
0x1800940bc  xor     r9d, r9d
0x1800940bf  xor     r8d, r8d
0x1800940c2  lea     rdx, dword_180107EFC
0x1800940c9  lea     rcx, dword_180122070
0x1800940d0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800940d5  test    ebx, ebx
0x1800940d7  jle     short loc_1800940E2
0x1800940d9  movzx   ebx, bx
0x1800940dc  or      ebx, 80070000h
0x1800940e2  mov     [rsp+240h+var_1F0], ebx
0x1800940e6  mov     rcx, [rsp+240h+hMem]; hMem
0x1800940eb  mov     [rsp+240h+hMem], rdi
0x1800940f0  test    rcx, rcx
0x1800940f3  jz      short loc_1800940FC
0x1800940f5  call    cs:__imp_LocalFree
0x1800940fb  nop
0x1800940fc  lea     rcx, [rbp+140h+lpName]
0x180094103  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x180094108  nop
0x180094109  mov     rdx, [rsp+240h+var_1E8]
0x18009410e  mov     [rsp+240h+var_1E8], rdi
0x180094113  test    rdx, rdx
0x180094116  jz      short loc_18009411E
0x180094118  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x18009411d  nop
0x18009411e  lea     rcx, [rbp+140h+var_150]; this
0x180094122  call    ??1CredUIStringsContext@NgcKspServer@@QEAA@XZ; NgcKspServer::CredUIStringsContext::~CredUIStringsContext(void)
0x180094127  mov     edi, ebx
0x180094129  jmp     loc_180094539
0x18009412e  mov     qword ptr [rbp+140h+EventAttributes.nLength], 18h
0x180094136  mov     qword ptr [rbp+140h+EventAttributes.bInheritHandle], rdi
0x18009413a  mov     rax, [rsp+240h+hMem]
0x18009413f  mov     [rbp+140h+EventAttributes.lpSecurityDescriptor], rax
0x180094143  lea     r9, [rbp+140h+lpName]
0x18009414a  cmp     qword ptr [rbp+140h+var_60+8], 7
0x180094152  cmova   r9, [rbp+140h+lpName]; lpName
0x18009415a  xor     r8d, r8d; bInitialState
0x18009415d  lea     edx, [r8+1]; bManualReset
0x180094161  lea     rcx, [rbp+140h+EventAttributes]; lpEventAttributes
0x180094165  call    cs:__imp_CreateEventW
0x18009416b  mov     rdx, rax
0x18009416e  lea     rcx, [rsp+240h+var_1E0]
0x180094173  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180094178  mov     rbx, [rsp+240h+var_1E0]
0x18009417d  test    rbx, rbx
0x180094180  jnz     loc_18009420E
0x180094186  call    cs:__imp_GetLastError
0x18009418c  mov     ebx, eax
0x18009418e  mov     ecx, cs:dword_180122070
0x180094194  cmp     ecx, 2
0x180094197  jbe     short loc_1800941C0
0x180094199  mov     dword ptr [rsp+240h+var_1E0], eax
0x18009419d  lea     rax, [rsp+240h+var_1E0]
0x1800941a2  mov     qword ptr [rsp+240h+ulInAuthBufferSize], rax
0x1800941a7  xor     r9d, r9d
0x1800941aa  xor     r8d, r8d
0x1800941ad  lea     rdx, word_180107ED2
0x1800941b4  lea     rcx, dword_180122070
0x1800941bb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800941c0  test    ebx, ebx
0x1800941c2  jle     short loc_1800941CD
0x1800941c4  movzx   ebx, bx
0x1800941c7  or      ebx, 80070000h
0x1800941cd  mov     [rsp+240h+var_1F0], ebx
0x1800941d1  mov     rcx, [rsp+240h+hMem]; hMem
0x1800941d6  mov     [rsp+240h+hMem], rdi
0x1800941db  test    rcx, rcx
0x1800941de  jz      short loc_1800941E7
0x1800941e0  call    cs:__imp_LocalFree
0x1800941e6  nop
0x1800941e7  lea     rcx, [rbp+140h+lpName]
0x1800941ee  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800941f3  nop
0x1800941f4  mov     rdx, [rsp+240h+var_1E8]
0x1800941f9  mov     [rsp+240h+var_1E8], rdi
0x1800941fe  test    rdx, rdx
0x180094201  jz      short loc_180094209
0x180094203  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x180094208  nop
0x180094209  jmp     loc_18009411E
0x18009420e  lea     rax, [rbp+140h+lpName]
0x180094215  cmp     qword ptr [rbp+140h+var_60+8], 7
0x18009421d  cmova   rax, [rbp+140h+lpName]
0x180094225  mov     [rbp+140h+var_A8], rax
0x18009422c  mov     rcx, [rsp+240h+hMem]; hMem
0x180094231  mov     [rsp+240h+hMem], rdi
0x180094236  test    rcx, rcx
0x180094239  jz      short loc_180094241
0x18009423b  call    cs:__imp_LocalFree
0x180094241  mov     rdx, r15; void *
0x180094244  lea     rcx, [rbp+140h+var_1B0]; this
0x180094248  call    ??0RpcCallerImpersonator@NgcUtils@@QEAA@QEAX@Z; NgcUtils::RpcCallerImpersonator::RpcCallerImpersonator(void * const)
0x18009424d  nop
0x18009424e  lea     rax, [rbp+140h+var_150]
0x180094252  mov     [rbp+140h+var_198], rax
0x180094256  mov     [rbp+140h+var_190], r12
0x18009425a  mov     rcx, [r13+38h]
0x18009425e  xor     r15d, r15d
0x180094261  test    rcx, rcx
0x180094264  jnz     short loc_18009426D
0x180094266  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18009426c  int     3; Trap to Debugger
0x18009426d  mov     rax, [rcx]
0x180094270  lea     r8, [rbp+140h+var_198]
0x180094274  lea     rdx, [rbp+140h+var_190]
0x180094278  mov     rax, [rax+10h]
0x18009427c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094281  mov     edi, eax
0x180094283  mov     [rsp+240h+var_1F0], eax
0x180094287  test    eax, eax
0x180094289  jns     short loc_1800942CA
0x18009428b  lea     rcx, [rbp+140h+var_1B0]; this
0x18009428f  call    ??1RpcCallerImpersonator@NgcUtils@@QEAA@XZ; NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator(void)
0x180094294  nop
0x180094295  test    rbx, rbx
0x180094298  jz      short loc_1800942A3
0x18009429a  mov     rcx, rbx; this
0x18009429d  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1800942a2  nop
0x1800942a3  lea     rcx, [rbp+140h+lpName]
0x1800942aa  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x1800942af  nop
0x1800942b0  mov     rdx, [rsp+240h+var_1E8]
0x1800942b5  mov     [rsp+240h+var_1E8], r15
0x1800942ba  test    rdx, rdx
0x1800942bd  jz      short loc_1800942C5
0x1800942bf  call    ??$?RG@cotaskmem_secure_deleter@wil@@QEBAXPEAG@Z; wil::cotaskmem_secure_deleter::operator()<ushort>(ushort *)
0x1800942c4  nop
0x1800942c5  jmp     loc_18009452F
0x1800942ca  mov     rax, qword ptr [rbp+140h+var_150]
0x1800942ce  cmp     qword ptr [rax+18h], 7
0x1800942d3  jbe     short loc_1800942D8
0x1800942d5  mov     rax, [rax]
0x1800942d8  mov     [rbp+140h+pUiInfo.pszCaptionText], rax
0x1800942dc  mov     rax, qword ptr [rbp+140h+var_140]
0x1800942e0  cmp     qword ptr [rax+18h], 7
0x1800942e5  jbe     short loc_1800942EA
0x1800942e7  mov     rax, [rax]
0x1800942ea  mov     [rbp+140h+pUiInfo.pszMessageText], rax
0x1800942ee  mov     rax, qword ptr [rbp+140h+var_130]
0x1800942f2  cmp     [rax+10h], r15
0x1800942f6  jz      short loc_180094315
0x1800942f8  cmp     qword ptr [rax+18h], 7
0x1800942fd  jbe     short loc_180094302
0x1800942ff  mov     rax, [rax]
0x180094302  mov     [rbp+140h+var_B0], rax
0x180094309  mov     eax, dword ptr [rbp+140h+pUiInfo.hbmBanner]
0x18009430c  bts     eax, 0Bh
0x180094310  mov     dword ptr [rbp+140h+pUiInfo.hbmBanner], eax
0x180094313  jmp     short loc_180094318
0x180094315  mov     eax, dword ptr [rbp+140h+pUiInfo.hbmBanner]
0x180094318  mov     rcx, qword ptr [rbp+140h+var_120]
0x18009431c  cmp     [rcx+10h], r15
0x180094320  jz      short loc_180094337
0x180094322  cmp     qword ptr [rcx+18h], 7
0x180094327  jbe     short loc_18009432C
0x180094329  mov     rcx, [rcx]
0x18009432c  mov     [rbp+140h+var_D8], rcx
0x180094330  bts     eax, 8
0x180094334  mov     dword ptr [rbp+140h+pUiInfo.hbmBanner], eax
0x180094337  mov     rcx, qword ptr [rbp+140h+var_110]
0x18009433b  cmp     [rcx+10h], r15
0x18009433f  jz      short loc_180094356
0x180094341  cmp     qword ptr [rcx+18h], 7
0x180094346  jbe     short loc_18009434B
0x180094348  mov     rcx, [rcx]
0x18009434b  mov     [rbp+140h+var_D0], rcx
0x18009434f  bts     eax, 9
0x180094353  mov     dword ptr [rbp+140h+pUiInfo.hbmBanner], eax
0x180094356  movzx   edi, [rbp+140h+arg_38]
0x18009435d  shl     edi, 1Eh
0x180094360  add     edi, 8000210h
0x180094366  mov     rax, [r14+8]
0x18009436a  cmp     [r14], rax
0x18009436d  jz      short loc_18009437E
0x18009436f  mov     rdx, r14
0x180094372  call    _lambda_3a2dbe4c6996697c9f7853101d3d01a2___operator__
0x180094377  mov     [rbp+140h+var_88], rax
  ... truncated ...
```
