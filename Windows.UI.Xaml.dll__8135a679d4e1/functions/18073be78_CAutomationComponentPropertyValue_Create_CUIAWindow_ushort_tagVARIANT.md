# CAutomationComponentPropertyValue::Create(CUIAWindow *,ushort,tagVARIANT *)

- ea: `0x18073be78`
- end: `0x18073c251`
- name: `?Create@CAutomationComponentPropertyValue@@QEAAJPEAVCUIAWindow@@GPEAUtagVARIANT@@@Z`
- size: `985`
- prototype: `HRESULT __fastcall(CAutomationComponentPropertyValue *this, CUIAWindow *pUIAWindow, unsigned __int16 vtType, tagVARIANT *pRetValue)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1806b9104`

## callees

- `0x180004bc0`
- `0x180008428`
- `0x1801292ec`
- `0x18020a400`
- `0x180436cdc`
- `0x18043eb10`
- `0x180530610`
- `0x180580af8`
- `0x180688828`
- `0x180702c34`
- `0x18073be78`
- `0x18076e110`
- `0x1809fa818`
- `0x1809faca0`
- `0x1809fadc8`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073bf77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c0c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c17f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c1b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c1e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073bf77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c0c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c11f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c17f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c1b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18073c1e6`
- `OLEAUT32!__imp_VariantClear` at `0x18073beb2`
- `OLEAUT32!__imp_VariantClear` at `0x18073bf22`
- `OLEAUT32!__imp_VariantClear` at `0x18073beb2`
- `OLEAUT32!__imp_VariantClear` at `0x18073bf22`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18073c06b`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x18073c06b`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18073c043`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18073c043`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__int64 __fastcall CAutomationComponentPropertyValue::Create(
        CAutomationComponentPropertyValue *this,
        CUIAWindow *pUIAWindow,
        unsigned __int16 vtType,
        tagVARIANT *pRetValue)
{
  HRESULT Interface; // eax
  unsigned int v9; // ebx
  HRESULT ComponentSite; // eax
  HRESULT ElementId; // eax
  ComponentSiteAutomationProxy *ptr; // r14
  ComponentSiteAutomationProxy *v14; // rax
  HSTRING v15; // rbx
  CTextWithLinguisticAlternatives *v16; // rax
  HRESULT (__fastcall *QueryInterface)(IUnknown *, const _GUID *, void **); // rdi
  HRESULT v18; // eax
  unsigned int v19; // edi
  SAFEARRAY *Vector; // rax
  HRESULT v21; // ecx
  __int64 v22; // rdi
  int v23; // eax
  unsigned int v24; // r12d
  Microsoft::WRL::ComPtr<IRawElementProviderFragmentRoot> spFragment; // [rsp+20h] [rbp-60h] BYREF
  Microsoft::WRL::ComPtr<Windows::Foundation::Private::IComponentSite> spSite; // [rsp+28h] [rbp-58h] BYREF
  Microsoft::WRL::ComPtr<IUnknown> spUnk; // [rsp+30h] [rbp-50h] BYREF
  HSTRING safeArrayCount; // [rsp+38h] [rbp-48h] BYREF
  _GUID safeArray; // [rsp+40h] [rbp-40h] OVERLAPPED BYREF
  Microsoft::WRL::ComPtr<ComponentSiteAutomationProxy> spProxy; // [rsp+50h] [rbp-30h] BYREF
  _GUID componentSiteId; // [rsp+60h] [rbp-20h] BYREF

  VariantClear(pRetValue);
  if ( pUIAWindow )
    _InterlockedIncrement((volatile signed __int32 *)&pUIAWindow->m_cReferences);
  spFragment.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spFragment);
  Interface = CUIAWindow::QueryInterface(
                pUIAWindow,
                &GUID_620ce2a5_ab8f_40a9_86cb_de3c75599b58,
                (void **)&spFragment.ptr_);
  v9 = Interface;
  if ( Interface < 0 )
  {
    OnFailure_2990_(Interface);
    goto LABEL_43;
  }
  spSite.ptr_ = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spSite);
  ComponentSite = CAutomationComponentPropertyValue::GetComponentSite(this, &spSite.ptr_);
  v9 = ComponentSite;
  if ( ComponentSite < 0 )
    goto LABEL_40;
  if ( !spSite.ptr_ )
  {
    VariantClear(pRetValue);
LABEL_7:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spSite);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spFragment);
    if ( pUIAWindow )
      CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&pUIAWindow->CInterlockedReferenceCount);
    return 0;
  }
  componentSiteId = GUID_NULL;
  ComponentSite = spSite.ptr_->get_Id(spSite.ptr_, &componentSiteId);
  v9 = ComponentSite;
  if ( ComponentSite < 0 )
  {
LABEL_40:
    OnFailure_2990_(ComponentSite);
    goto LABEL_39;
  }
  WindowsDeleteString(0);
  safeArrayCount = 0;
  ElementId = CAutomationComponentPropertyValue::GetElementId(this, &safeArrayCount);
  v9 = ElementId;
  if ( ElementId < 0 )
  {
    OnFailure_2990_(ElementId);
    WindowsDeleteString(safeArrayCount);
LABEL_39:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spSite);
LABEL_43:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spFragment);
    if ( pUIAWindow )
      CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&pUIAWindow->CInterlockedReferenceCount);
    return v9;
  }
  ptr = 0;
  spProxy.ptr_ = 0;
  *(_QWORD *)&safeArray.Data1 = 0;
  v14 = (ComponentSiteAutomationProxy *)Microsoft::WRL::Details::MakeAllocator<ComponentSiteAutomationProxy>::Allocate((Microsoft::WRL::Details::MakeAllocator<Windows::UI::Xaml::Hosting::NavigationGotFocusEventArgs> *)&safeArray);
  v15 = safeArrayCount;
  if ( v14 )
  {
    safeArray = componentSiteId;
    ComponentSiteAutomationProxy::ComponentSiteAutomationProxy(v14, &safeArray, spFragment.ptr_, safeArrayCount);
    Microsoft::WRL::ComPtr<ComponentSiteAutomationProxy>::Attach(
      (Microsoft::WRL::ComPtr<CTextWithLinguisticAlternatives> *)&spProxy,
      v16);
    *(_QWORD *)&safeArray.Data1 = 0;
    ptr = spProxy.ptr_;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::System::IDispatcherQueueHandler::*)(void)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>,_lambda_d38cc70e2c5b9eeec78ab0432adf98fc_ &,-1,>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::System::IDispatcherQueueHandler::*)(void)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>,_lambda_d38cc70e2c5b9eeec78ab0432adf98fc_ &,-1,>>((Microsoft::WRL::Details::MakeAllocator<CIntegratedUIManager> *)&safeArray);
  spUnk.ptr_ = 0;
  QueryInterface = ptr->QueryInterface;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&spUnk);
  v18 = QueryInterface(ptr, &GUID_00000000_0000_0000_c000_000000000046, (void **)&spUnk.ptr_);
  v19 = v18;
  if ( v18 < 0 )
  {
    OnFailure_2990_(v18);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&spUnk);
    if ( ptr )
      ptr->Release(ptr);
    WindowsDeleteString(v15);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spSite);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spFragment);
    if ( pUIAWindow )
      CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&pUIAWindow->CInterlockedReferenceCount);
    return v19;
  }
  else
  {
    pRetValue->vt = vtType;
    if ( (vtType & 0x2000) == 0 )
    {
      *(Microsoft::WRL::ComPtr<IUnknown> *)&pRetValue->boolVal = spUnk;
      spUnk.ptr_ = 0;
      goto LABEL_30;
    }
    Vector = SafeArrayCreateVector(0xDu, 0, 1u);
    *(_QWORD *)&safeArray.Data1 = Vector;
    v22 = (__int64)Vector;
    if ( Vector )
    {
      LODWORD(safeArrayCount) = 0;
      v23 = SafeArrayPutElement(Vector, (LONG *)&safeArrayCount, spUnk.ptr_);
      v24 = v23;
      if ( v23 >= 0 )
      {
        *(_QWORD *)&safeArray.Data1 = 0;
        pRetValue->llVal = v22;
        wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (__cdecl*)(tagSAFEARRAY *),&SafeArrayDestroy,wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t> > *)&safeArray);
LABEL_30:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&spUnk);
        if ( ptr )
          ptr->Release(ptr);
        WindowsDeleteString(v15);
        goto LABEL_7;
      }
      OnFailure_2990_(v23);
      wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (__cdecl*)(tagSAFEARRAY *),&SafeArrayDestroy,wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t> > *)&safeArray);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&spUnk);
      if ( ptr )
        ptr->Release(ptr);
      WindowsDeleteString(v15);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spSite);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spFragment);
      if ( pUIAWindow )
        CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&pUIAWindow->CInterlockedReferenceCount);
      return v24;
    }
    else
    {
      OnNewFailure_1172_(v21);
      wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&long SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>((wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (__cdecl*)(tagSAFEARRAY *),&SafeArrayDestroy,wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t> > *)&safeArray);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((Microsoft::WRL::ComPtr<Windows::UI::Composition::ICompositionObjectStatics> *)&spUnk);
      if ( ptr )
        ptr->Release(ptr);
      WindowsDeleteString(v15);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spSite);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((Microsoft::WRL::ComPtr<Windows::System::Internal::IUserManagerStatics> *)&spFragment);
      if ( pUIAWindow )
        CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&pUIAWindow->CInterlockedReferenceCount);
      return 2147500035LL;
    }
  }
}

```

## disassembly

```asm
0x18073be78  mov     [rsp-28h+arg_8], rbx
0x18073be7d  mov     [rsp-28h+arg_10], rsi
0x18073be82  push    rbp
0x18073be83  push    rdi
0x18073be84  push    r12
0x18073be86  push    r14
0x18073be88  push    r15
0x18073be8a  mov     rbp, rsp
0x18073be8d  sub     rsp, 80h
0x18073be94  mov     rax, cs:__security_cookie
0x18073be9b  xor     rax, rsp
0x18073be9e  mov     [rbp+var_10], rax
0x18073bea2  mov     rdi, this
0x18073bea5  mov     r15, pRetValue
0x18073bea8  mov     this, pRetValue; pvarg
0x18073beab  movzx   r12d, vtType
0x18073beaf  mov     rsi, pUIAWindow
0x18073beb2  call    cs:__imp_VariantClear
0x18073beb8  test    rsi, rsi
0x18073bebb  jz      short loc_18073BEC1
0x18073bebd  lock inc dword ptr [rsi+30h]
0x18073bec1  lea     this, [rbp+spFragment]; this
0x18073bec5  mov     [rbp+spFragment.ptr_], 0
0x18073becd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073bed2  lea     r8, [rbp+spFragment]; ppInterface
0x18073bed6  mov     this, rsi; this
0x18073bed9  lea     pUIAWindow, _GUID_620ce2a5_ab8f_40a9_86cb_de3c75599b58; riid
0x18073bee0  call    ?QueryInterface@CUIAWindow@@UEAAJAEBU_GUID@@PEAPEAX@Z; CUIAWindow::QueryInterface(_GUID const &,void * *)
0x18073bee5  mov     ebx, eax
0x18073bee7  test    eax, eax
0x18073bee9  js      loc_18073C209
0x18073beef  lea     this, [rbp+spSite]; this
0x18073bef3  mov     [rbp+spSite.ptr_], 0
0x18073befb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073bf00  lea     pUIAWindow, [rbp+spSite]; ppSite
0x18073bf04  mov     this, rdi; this
0x18073bf07  call    ?GetComponentSite@CAutomationComponentPropertyValue@@AEAAJPEAPEAUIComponentSite@Private@Foundation@Windows@@@Z; CAutomationComponentPropertyValue::GetComponentSite(Windows::Foundation::Private::IComponentSite * *)
0x18073bf0c  mov     ebx, eax
0x18073bf0e  test    eax, eax
0x18073bf10  js      loc_18073C200
0x18073bf16  mov     this, [rbp+spSite.ptr_]
0x18073bf1a  test    this, this
0x18073bf1d  jnz     short loc_18073BF4F
0x18073bf1f  mov     this, r15; pvarg
0x18073bf22  call    cs:__imp_VariantClear
0x18073bf28  lea     this, [rbp+spSite]; this
0x18073bf2c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073bf31  lea     this, [rbp+spFragment]; this
0x18073bf35  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073bf3a  test    rsi, rsi
0x18073bf3d  jz      short loc_18073BF48
0x18073bf3f  lea     this, [rsi+28h]; this
0x18073bf43  call    ?Release@CInterlockedReferenceCount@@QEBAIXZ; CInterlockedReferenceCount::Release(void)
0x18073bf48  xor     eax, eax
0x18073bf4a  jmp     loc_18073C229
0x18073bf4f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18073bf56  lea     pUIAWindow, [rbp+componentSiteId]
0x18073bf5a  movdqu  xmmword ptr [rbp+componentSiteId.Data1], xmm0
0x18073bf5f  mov     rax, [this]
0x18073bf62  mov     rax, [rax+58h]
0x18073bf66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18073bf6b  mov     ebx, eax
0x18073bf6d  test    eax, eax
0x18073bf6f  js      loc_18073C1F7
0x18073bf75  xor     ecx, ecx; string
0x18073bf77  call    cs:__imp_WindowsDeleteString
0x18073bf7d  lea     pUIAWindow, [rbp+safeArrayCount]; pElementId
0x18073bf81  mov     [rbp+safeArrayCount], 0
0x18073bf89  mov     this, rdi; this
0x18073bf8c  call    ?GetElementId@CAutomationComponentPropertyValue@@AEAAJPEAPEAUHSTRING__@@@Z; CAutomationComponentPropertyValue::GetElementId(HSTRING__ * *)
0x18073bf91  mov     ebx, eax
0x18073bf93  test    eax, eax
0x18073bf95  js      loc_18073C1DB
0x18073bf9b  xor     r14d, r14d
0x18073bf9e  lea     this, [rbp+safeArray]; this
0x18073bfa2  mov     [rbp+spProxy.ptr_], r14
0x18073bfa6  mov     [rbp+safeArray.m_ptr], r14
0x18073bfaa  call    ?Allocate@?$MakeAllocator@VComponentSiteAutomationProxy@@@Details@WRL@Microsoft@@QEAAPEAXXZ; Microsoft::WRL::Details::MakeAllocator<ComponentSiteAutomationProxy>::Allocate(void)
0x18073bfaf  mov     rbx, [rbp+safeArrayCount]
0x18073bfb3  test    rax, rax
0x18073bfb6  jz      short loc_18073BFE8
0x18073bfb8  movaps  xmm0, xmmword ptr [rbp+componentSiteId.Data1]
0x18073bfbc  lea     pUIAWindow, [rbp+safeArray]
0x18073bfc0  mov     r8, [rbp+spFragment.ptr_]
0x18073bfc4  mov     pRetValue, rbx
0x18073bfc7  mov     this, rax
0x18073bfca  movdqa  xmmword ptr [rbp+safeArray.m_ptr], xmm0
0x18073bfcf  call    ??0ComponentSiteAutomationProxy@@QEAA@U_GUID@@PEAUIRawElementProviderFragmentRoot@@PEAUHSTRING__@@@Z; ComponentSiteAutomationProxy::ComponentSiteAutomationProxy(_GUID,IRawElementProviderFragmentRoot *,HSTRING__ *)
0x18073bfd4  mov     pUIAWindow, rax; other
0x18073bfd7  lea     this, [rbp+spProxy]; this
0x18073bfdb  call    ?Attach@?$ComPtr@VComponentSiteAutomationProxy@@@WRL@Microsoft@@QEAAXPEAVComponentSiteAutomationProxy@@@Z; Microsoft::WRL::ComPtr<ComponentSiteAutomationProxy>::Attach(ComponentSiteAutomationProxy *)
0x18073bfe0  mov     [rbp+safeArray.m_ptr], r14
0x18073bfe4  mov     r14, [rbp+spProxy.ptr_]
0x18073bfe8  lea     this, [rbp+safeArray]; this
0x18073bfec  call    ??1?$MakeAllocator@U?$DelegateInvokeHelper@U?$Implements@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDispatcherQueueHandler@System@Windows@@VFtmBase@23@@WRL@Microsoft@@AEAV_lambda_d38cc70e2c5b9eeec78ab0432adf98fc_@@$0?0$$V@?$DelegateArgTraits@P8IDispatcherQueueHandler@System@Windows@@EAAJXZ@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::System::IDispatcherQueueHandler::*)(void)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>,_lambda_d38cc70e2c5b9eeec78ab0432adf98fc_ &,-1,>>::~MakeAllocator<Microsoft::WRL::Details::DelegateArgTraits<long (Windows::System::IDispatcherQueueHandler::*)(void)>::DelegateInvokeHelper<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<2>,Windows::System::IDispatcherQueueHandler,Microsoft::WRL::FtmBase>,_lambda_d38cc70e2c5b9eeec78ab0432adf98fc_ &,-1,>>(void)
0x18073bff1  mov     [rbp+spUnk.ptr_], 0
0x18073bff9  lea     this, [rbp+spUnk]; this
0x18073bffd  mov     rax, [r14]
0x18073c000  mov     rdi, [rax]
0x18073c003  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18073c008  lea     r8, [rbp+spUnk]
0x18073c00c  mov     this, r14
0x18073c00f  lea     pUIAWindow, _GUID_00000000_0000_0000_c000_000000000046
0x18073c016  mov     rax, rdi
0x18073c019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18073c01e  mov     edi, eax
0x18073c020  test    eax, eax
0x18073c022  js      loc_18073C18A
0x18073c028  bt      r12w, 0Dh
0x18073c02e  mov     [r15], r12w
0x18073c032  jnb     loc_18073C14F
0x18073c038  mov     ecx, 0Dh; vt
0x18073c03d  xor     edx, edx; lLbound
0x18073c03f  lea     r8d, [this-0Ch]; cElements
0x18073c043  call    cs:__imp_SafeArrayCreateVector
0x18073c049  mov     [rbp+safeArray.m_ptr], rax
0x18073c04d  mov     rdi, rax
0x18073c050  test    rax, rax
0x18073c053  jz      loc_18073C0F1
0x18073c059  mov     r8, [rbp+spUnk.ptr_]; pv
0x18073c05d  lea     pUIAWindow, [rbp+safeArrayCount]; rgIndices
0x18073c061  mov     this, rax; psa
0x18073c064  mov     dword ptr [rbp+safeArrayCount], 0
0x18073c06b  call    cs:__imp_SafeArrayPutElement
0x18073c071  mov     r12d, eax
0x18073c074  test    eax, eax
0x18073c076  js      short loc_18073C092
0x18073c078  lea     this, [rbp+safeArray]; this
0x18073c07c  mov     [rbp+safeArray.m_ptr], 0
0x18073c084  mov     [r15+8], rdi
0x18073c088  call    ??1?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>(void)
0x18073c08d  jmp     loc_18073C15F
0x18073c092  mov     ecx, r12d; failedFrameHR
0x18073c095  call    OnFailure_2990_
0x18073c09a  lea     this, [rbp+safeArray]; this
0x18073c09e  call    ??1?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>(void)
0x18073c0a3  lea     this, [rbp+spUnk]; this
0x18073c0a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18073c0ac  test    r14, r14
0x18073c0af  jz      short loc_18073C0C0
0x18073c0b1  mov     rax, [r14]
0x18073c0b4  mov     this, r14
0x18073c0b7  mov     rax, [rax+10h]
0x18073c0bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18073c0c0  mov     this, rbx; string
0x18073c0c3  call    cs:__imp_WindowsDeleteString
0x18073c0c9  lea     this, [rbp+spSite]; this
0x18073c0cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073c0d2  lea     this, [rbp+spFragment]; this
0x18073c0d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073c0db  test    rsi, rsi
0x18073c0de  jz      short loc_18073C0E9
0x18073c0e0  lea     this, [rsi+28h]; this
0x18073c0e4  call    ?Release@CInterlockedReferenceCount@@QEBAIXZ; CInterlockedReferenceCount::Release(void)
0x18073c0e9  mov     eax, r12d
0x18073c0ec  jmp     loc_18073C229
0x18073c0f1  call    OnNewFailure_1172_
0x18073c0f6  lea     this, [rbp+safeArray]; this
0x18073c0fa  call    ??1?$unique_storage@U?$resource_policy@PEAUtagSAFEARRAY@@P6AJPEAU1@@Z$1?SafeArrayDestroy@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<tagSAFEARRAY *,long (*)(tagSAFEARRAY *),&SafeArrayDestroy(tagSAFEARRAY *),wistd::integral_constant<unsigned __int64,0>,tagSAFEARRAY *,tagSAFEARRAY *,0,std::nullptr_t>>(void)
0x18073c0ff  lea     this, [rbp+spUnk]; this
0x18073c103  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18073c108  test    r14, r14
0x18073c10b  jz      short loc_18073C11C
0x18073c10d  mov     rax, [r14]
0x18073c110  mov     this, r14
0x18073c113  mov     rax, [rax+10h]
0x18073c117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18073c11c  mov     this, rbx; string
0x18073c11f  call    cs:__imp_WindowsDeleteString
0x18073c125  lea     this, [rbp+spSite]; this
0x18073c129  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073c12e  lea     this, [rbp+spFragment]; this
0x18073c132  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073c137  test    rsi, rsi
0x18073c13a  jz      short loc_18073C145
0x18073c13c  lea     this, [rsi+28h]; this
0x18073c140  call    ?Release@CInterlockedReferenceCount@@QEBAIXZ; CInterlockedReferenceCount::Release(void)
0x18073c145  mov     eax, 80004003h
0x18073c14a  jmp     loc_18073C229
0x18073c14f  mov     rax, [rbp+spUnk.ptr_]
0x18073c153  mov     [r15+8], rax
0x18073c157  mov     [rbp+spUnk.ptr_], 0
0x18073c15f  lea     this, [rbp+spUnk]; this
0x18073c163  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18073c168  test    r14, r14
0x18073c16b  jz      short loc_18073C17C
0x18073c16d  mov     rax, [r14]
0x18073c170  mov     this, r14
0x18073c173  mov     rax, [rax+10h]
0x18073c177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18073c17c  mov     this, rbx; string
0x18073c17f  call    cs:__imp_WindowsDeleteString
0x18073c185  jmp     loc_18073BF28
0x18073c18a  mov     ecx, edi; failedFrameHR
0x18073c18c  call    OnFailure_2990_
0x18073c191  lea     this, [rbp+spUnk]; this
0x18073c195  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18073c19a  test    r14, r14
0x18073c19d  jz      short loc_18073C1AE
0x18073c19f  mov     rax, [r14]
0x18073c1a2  mov     this, r14
0x18073c1a5  mov     rax, [rax+10h]
0x18073c1a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18073c1ae  mov     this, rbx; string
0x18073c1b1  call    cs:__imp_WindowsDeleteString
0x18073c1b7  lea     this, [rbp+spSite]; this
0x18073c1bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073c1c0  lea     this, [rbp+spFragment]; this
0x18073c1c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073c1c9  test    rsi, rsi
0x18073c1cc  jz      short loc_18073C1D7
0x18073c1ce  lea     this, [rsi+28h]; this
0x18073c1d2  call    ?Release@CInterlockedReferenceCount@@QEBAIXZ; CInterlockedReferenceCount::Release(void)
0x18073c1d7  mov     eax, edi
0x18073c1d9  jmp     short loc_18073C229
0x18073c1db  mov     ecx, ebx; failedFrameHR
0x18073c1dd  call    OnFailure_2990_
0x18073c1e2  mov     this, [rbp+safeArrayCount]; string
0x18073c1e6  call    cs:__imp_WindowsDeleteString
0x18073c1ec  lea     this, [rbp+spSite]; this
0x18073c1f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073c1f5  jmp     short loc_18073C210
0x18073c1f7  mov     ecx, ebx; failedFrameHR
0x18073c1f9  call    OnFailure_2990_
0x18073c1fe  jmp     short loc_18073C1EC
0x18073c200  mov     ecx, ebx; failedFrameHR
0x18073c202  call    OnFailure_2990_
0x18073c207  jmp     short loc_18073C1EC
0x18073c209  mov     ecx, ebx; failedFrameHR
0x18073c20b  call    OnFailure_2990_
0x18073c210  lea     this, [rbp+spFragment]; this
0x18073c214  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18073c219  test    rsi, rsi
0x18073c21c  jz      short loc_18073C227
0x18073c21e  lea     this, [rsi+28h]; this
0x18073c222  call    ?Release@CInterlockedReferenceCount@@QEBAIXZ; CInterlockedReferenceCount::Release(void)
0x18073c227  mov     eax, ebx
0x18073c229  mov     this, [rbp+var_10]
0x18073c22d  xor     this, rsp; StackCookie
0x18073c230  call    __security_check_cookie
0x18073c235  lea     r11, [rsp+80h+var_s0]
0x18073c23d  mov     rbx, [r11+38h]
0x18073c241  mov     rsi, [r11+40h]
0x18073c245  mov     rsp, r11
0x18073c248  pop     r15
0x18073c24a  pop     r14
0x18073c24c  pop     r12
0x18073c24e  pop     rdi
0x18073c24f  pop     rbp
0x18073c250  retn
```
