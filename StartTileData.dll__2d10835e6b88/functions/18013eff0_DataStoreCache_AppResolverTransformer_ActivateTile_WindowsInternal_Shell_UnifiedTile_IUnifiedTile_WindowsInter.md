# DataStoreCache::AppResolverTransformer::ActivateTile(WindowsInternal::Shell::UnifiedTile::IUnifiedTile *,WindowsInternal::Shell::UnifiedTile::ITileActivationContext *)

- ea: `0x18013eff0`
- end: `0x18013f4f1`
- name: `?ActivateTile@AppResolverTransformer@DataStoreCache@@UEAAJPEAUIUnifiedTile@UnifiedTile@Shell@WindowsInternal@@PEAUITileActivationContext@456@@Z`
- size: `1281`
- prototype: `__int64 __fastcall(DataStoreCache::AppResolverTransformer *__hidden this, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1800240ac`
- `0x18002ca10`
- `0x18002edec`
- `0x18004ffc0`
- `0x18008272c`
- `0x1800c06e8`
- `0x1800cd850`
- `0x18012b50c`
- `0x18013eff0`
- `0x180141224`
- `0x1801413dc`
- `0x180195080`
- `0x1801a27f4`
- `0x1801a4a64`
- `0x180201e50`
- `0x1802046d4`
- `0x1802fd900`
- `0x18031c30c`
- `0x18031d340`
- `0x18031d3a0`
- `0x1803201b4`
- `0x1803208b0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013f2b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013f2f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013f494`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013f2b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013f2f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013f494`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013f44b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18013f44b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013f331`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18013f331`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18013f374`
- `ext-ms-win-com-ole32-l1-1-1!CoAllowSetForegroundWindow` at `0x18013f374`

## string_xrefs

- `0x18013f05a`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f16e`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f240`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f284`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f2df`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f347`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`
- `0x18013f3c8`: `shellcommon\shell\datastorecache\transformers\appresolvertransformer\lib\appresolvertransformer.cpp`

## pseudocode

```c
__int64 __fastcall DataStoreCache::AppResolverTransformer::ActivateTile(
        DataStoreCache::AppResolverTransformer *this,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *a2,
        struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *a3)
{
  CallerIdentity *v6; // rcx
  int IsShellExperience; // eax
  unsigned int v8; // ebx
  __int64 Default; // rax
  __int64 v10; // rax
  __int128 v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *, __int64 *); // rbx
  __int64 (__fastcall *v15)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  HRESULT Instance; // eax
  IUnknown *v22; // rdi
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rsi
  __int64 (__fastcall *v28)(__int64, PCWSTR, __int64); // rdi
  __int64 v29; // rbx
  PCWSTR StringRawBuffer; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  __int64 v34; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v36; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *pUnk; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+58h] [rbp-A8h] BYREF
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v41[8]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v42[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v43[8]; // [rsp+78h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-80h] BYREF
  __int64 v45; // [rsp+98h] [rbp-68h]
  _QWORD v46[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  wil::ActivityBase<DataStoreTransformerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v46);
  v46[0] = &DataStoreTransformerTelemetry::AppResolverTransformerActivateTile::`vftable';
  DataStoreTransformerTelemetry::AppResolverTransformerActivateTile::StartActivity((DataStoreTransformerTelemetry::AppResolverTransformerActivateTile *)v46);
  IsShellExperience = CallerIdentity::EnsureCallingProcessIsShellExperience(v6);
  v8 = IsShellExperience;
  if ( IsShellExperience >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseDirectLaunchForActivatingWin32Tiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseDirectLaunchForActivatingWin32Tiles>::GetImpl'::`2'::impl) )
    {
      wil::convert_from_abi<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTile>(v42, a2);
      Default = winrt::impl::consume_WindowsUdk_UI_StartScreen_Implementation_IStartMenuSettingsStatics<winrt::WindowsUdk::UI::StartScreen::Implementation::IStartMenuSettingsStatics>::GetDefault(
                  v42,
                  &hstringHeader);
      v10 = winrt::Windows::Foundation::IUnknown::as<winrt::WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(
              Default,
              v43);
      winrt::impl::consume_WindowsUdk_UI_StartScreen_IWin32ShortcutProperties<winrt::WindowsUdk::UI::StartScreen::IWin32ShortcutProperties>::TargetPath(
        v10,
        v41);
      winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics((winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics *)v43);
      winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics((winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics *)&hstringHeader);
      *(_QWORD *)&v11 = winrt::hstring::c_str((winrt::hstring *)v41);
      *((_QWORD *)&v11 + 1) = -1;
      do
        ++*((_QWORD *)&v11 + 1);
      while ( *(_WORD *)(v11 + 2LL * *((_QWORD *)&v11 + 1)) );
      *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v11;
      if ( (unsigned __int8)DirectLaunchHelper::TryActivateUsingDirectLaunch((char *)this + 312, &hstringHeader) )
      {
        DataStoreTransformerTelemetry::AppResolverTransformer_LaunchedUsingDirectLaunch();
        winrt::handle_type<winrt::impl::hstring_traits>::close(v41);
        winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics((winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics *)v42);
LABEL_49:
        v8 = 0;
        goto LABEL_50;
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(v41);
      winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics((winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics *)v42);
    }
    v40 = 0;
    v34 = 0;
    if ( !a3 )
      goto LABEL_17;
    v12 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *, int *))(*(_QWORD *)a3 + 56LL))(
            a3,
            &v40);
    v8 = v12;
    if ( v12 < 0 )
    {
      v13 = 252;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
        (const char *)(unsigned int)v12,
        ppv);
      goto LABEL_13;
    }
    v14 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *, __int64 *))(*(_QWORD *)a3 + 128LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v12 = v14(a3, &v34);
    v8 = v12;
    if ( v12 < 0 )
    {
      v13 = 253;
      goto LABEL_12;
    }
    hstringHeader.Reserved.Reserved1 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader);
    if ( !v34 )
    {
LABEL_17:
      v45 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Foundation.Collections.ValueSet",
        0x28u,
        0x27u);
      v12 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
              v45,
              &v34);
      v8 = v12;
      if ( v12 < 0 )
      {
        v13 = 264;
        goto LABEL_12;
      }
    }
    v36 = 0;
    v15 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *, __int64 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
    v16 = v15(a2, &v36);
    v8 = v16;
    if ( v16 >= 0 )
    {
      v38 = 0;
      v17 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(
              &v36,
              &v38);
      v8 = v17;
      if ( v17 >= 0 )
      {
        string = 0;
        v18 = v38;
        v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 48LL);
        WindowsDeleteString(0);
        string = 0;
        v20 = v19(v18, &string);
        v8 = v20;
        if ( v20 >= 0 )
        {
          pUnk = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
          Instance = CoCreateInstance(
                       &GUID_228826af_02e1_4226_a9e0_99a855e455a6,
                       0,
                       0x404u,
                       &GUID_9767060c_9476_42e2_8f7b_2f10fd13765c,
                       (LPVOID *)&pUnk);
          v8 = Instance;
          if ( Instance >= 0 )
          {
            if ( (unsigned __int8)IsCoAllowSetForegroundWindowPresent() )
              CoAllowSetForegroundWindow(pUnk, 0);
            v39 = 0;
            v22 = pUnk;
            QueryInterface = pUnk->lpVtbl[4].QueryInterface;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
            v24 = ((__int64 (__fastcall *)(IUnknown *, GUID *, GUID *, __int64 *))QueryInterface)(
                    v22,
                    &GUID_c735d7d4_b88a_41f2_b35d_da0141e7348a,
                    &GUID_1a91faba_b93c_456b_a10d_0036d2a68be6,
                    &v39);
            v8 = v24;
            if ( v24 >= 0 )
            {
              v26 = 2;
              if ( (v40 & 1) == 0 )
              {
                if ( (v40 & 2) != 0 )
                {
                  v26 = 3;
                }
                else
                {
                  v26 = 4;
                  if ( (v40 & 4) != 0 )
                  {
                    v26 = 1;
                  }
                  else if ( (v40 & 0x10) == 0 )
                  {
                    v26 = 0;
                    if ( (v40 & 0x20) != 0 )
                      v26 = 5;
                  }
                }
              }
              v24 = AppActivationPropertySetHelpers::RequestActivationType(v34, v26);
              v8 = v24;
              if ( v24 >= 0 )
              {
                v27 = v39;
                v28 = *(__int64 (__fastcall **)(__int64, PCWSTR, __int64))(*(_QWORD *)v39 + 24LL);
                v29 = v34;
                StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                v24 = v28(v27, StringRawBuffer, v29);
                v8 = v24;
                if ( v24 >= 0 )
                {
                  wil::ActivityBase<DataStoreTransformerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v46);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
                  WindowsDeleteString(string);
                  string = 0;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
                  goto LABEL_49;
                }
                v25 = 319;
              }
              else
              {
                v25 = 312;
              }
            }
            else
            {
              v25 = 287;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v25,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
              (const char *)(unsigned int)v24,
              ppva);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x116,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
              (const char *)(unsigned int)Instance,
              ppva);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pUnk);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x112,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
            (const char *)(unsigned int)v20,
            ppv);
        }
        WindowsDeleteString(string);
        string = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
          (const char *)(unsigned int)v17,
          ppv);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
        (const char *)(unsigned int)v16,
        ppv);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
LABEL_13:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    goto LABEL_50;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE8,
    (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\appresolvertransformer\\lib\\appresolvertransformer.cpp",
    (const char *)(unsigned int)IsShellExperience,
    ppv);
LABEL_50:
  DataStoreTransformerTelemetry::AppResolverTransformerActivateTile::~AppResolverTransformerActivateTile((DataStoreTransformerTelemetry::AppResolverTransformerActivateTile *)v46);
  return v8;
}

```

## disassembly

```asm
0x18013eff0  mov     [rsp-8+arg_18], rbx
0x18013eff5  push    rbp
0x18013eff6  push    rsi
0x18013eff7  push    rdi
0x18013eff8  push    r14
0x18013effa  push    r15
0x18013effc  lea     rbp, [rsp-100h]
0x18013f004  sub     rsp, 200h
0x18013f00b  mov     rax, cs:__security_cookie
0x18013f012  xor     rax, rsp
0x18013f015  mov     [rbp+120h+var_30], rax
0x18013f01c  mov     rdi, r8
0x18013f01f  mov     rsi, rdx
0x18013f022  mov     r14, rcx
0x18013f025  lea     rcx, [rbp+120h+var_180]; struct wil::details::IFailureCallback *
0x18013f029  call    ??0?$ActivityBase@VDataStoreTransformerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DataStoreTransformerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18013f02e  lea     rax, ??_7AppResolverTransformerActivateTile@DataStoreTransformerTelemetry@@6B@; const DataStoreTransformerTelemetry::AppResolverTransformerActivateTile::`vftable'
0x18013f035  mov     [rbp+120h+var_180], rax
0x18013f039  lea     rcx, [rbp+120h+var_180]; this
0x18013f03d  call    ?StartActivity@AppResolverTransformerActivateTile@DataStoreTransformerTelemetry@@QEAAXXZ; DataStoreTransformerTelemetry::AppResolverTransformerActivateTile::StartActivity(void)
0x18013f042  call    ?EnsureCallingProcessIsShellExperience@CallerIdentity@@YAJXZ; CallerIdentity::EnsureCallingProcessIsShellExperience(void)
0x18013f047  mov     ebx, eax
0x18013f049  xor     r15d, r15d
0x18013f04c  test    eax, eax
0x18013f04e  jns     short loc_18013F070
0x18013f050  mov     rcx, [rbp+128h]; this
0x18013f057  mov     r9d, eax; char *
0x18013f05a  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f061  mov     edx, 0E8h; void *
0x18013f066  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f06b  jmp     loc_18013F4C0
0x18013f070  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseDirectLaunchForActivatingWin32Tiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseDirectLaunchForActivatingWin32Tiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseDirectLaunchForActivatingWin32Tiles> `wil::Feature<__WilFeatureTraits_Feature_UseDirectLaunchForActivatingWin32Tiles>::GetImpl(void)'::`2'::impl
0x18013f077  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseDirectLaunchForActivatingWin32Tiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseDirectLaunchForActivatingWin32Tiles>::__private_IsEnabled(void)
0x18013f07c  test    al, al
0x18013f07e  jz      loc_18013F132
0x18013f084  mov     rdx, rsi
0x18013f087  lea     rcx, [rsp+220h+var_1B0]
0x18013f08c  call    ??$convert_from_abi@UIUnifiedTile@UnifiedTile@Shell@WindowsInternal@winrt@@@wil@@YA?AUIUnifiedTile@UnifiedTile@Shell@WindowsInternal@winrt@@PEAUIUnknown@@@Z; wil::convert_from_abi<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTile>(IUnknown *)
0x18013f091  lea     rdx, [rbp+120h+hstringHeader]
0x18013f095  lea     rcx, [rsp+220h+var_1B0]
0x18013f09a  call    ?GetDefault@?$consume_WindowsUdk_UI_StartScreen_Implementation_IStartMenuSettingsStatics@UIStartMenuSettingsStatics@Implementation@StartScreen@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_StartScreen_Implementation_IStartMenuSettingsStatics<winrt::WindowsUdk::UI::StartScreen::Implementation::IStartMenuSettingsStatics>::GetDefault(void)
0x18013f09f  lea     rdx, [rsp+220h+var_1A8]
0x18013f0a4  mov     rcx, rax
0x18013f0a7  call    ??$as@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18013f0ac  lea     rdx, [rsp+220h+var_1B8]
0x18013f0b1  mov     rcx, rax
0x18013f0b4  call    ?TargetPath@?$consume_WindowsUdk_UI_StartScreen_IWin32ShortcutProperties@UIWin32ShortcutProperties@StartScreen@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsUdk_UI_StartScreen_IWin32ShortcutProperties<winrt::WindowsUdk::UI::StartScreen::IWin32ShortcutProperties>::TargetPath(void)
0x18013f0b9  lea     rcx, [rsp+220h+var_1A8]; this
0x18013f0be  call    ??1IJumpListImageHelpersStatics@Private@JumpList@Shell@WindowsInternal@winrt@@QEAA@XZ; winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics(void)
0x18013f0c3  lea     rcx, [rbp+120h+hstringHeader]; this
0x18013f0c7  call    ??1IJumpListImageHelpersStatics@Private@JumpList@Shell@WindowsInternal@winrt@@QEAA@XZ; winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics(void)
0x18013f0cc  lea     rcx, [rsp+220h+var_1B8]; this
0x18013f0d1  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18013f0d6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18013f0da  inc     rdx
0x18013f0dd  cmp     [rax+rdx*2], r15w
0x18013f0e2  jnz     short loc_18013F0DA
0x18013f0e4  mov     qword ptr [rbp+120h+hstringHeader.Reserved], rax
0x18013f0e8  mov     qword ptr [rbp+120h+hstringHeader.Reserved+8], rdx
0x18013f0ec  lea     rdx, [rbp+120h+hstringHeader]
0x18013f0f0  lea     rcx, [r14+138h]
0x18013f0f7  call    ?TryActivateUsingDirectLaunch@DirectLaunchHelper@@QEAA_NV?$basic_zstring_view@G@wil@@@Z; DirectLaunchHelper::TryActivateUsingDirectLaunch(wil::basic_zstring_view<ushort>)
0x18013f0fc  test    al, al
0x18013f0fe  jz      short loc_18013F11E
0x18013f100  call    ?AppResolverTransformer_LaunchedUsingDirectLaunch@DataStoreTransformerTelemetry@@SAXXZ; DataStoreTransformerTelemetry::AppResolverTransformer_LaunchedUsingDirectLaunch(void)
0x18013f105  lea     rcx, [rsp+220h+var_1B8]
0x18013f10a  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18013f10f  lea     rcx, [rsp+220h+var_1B0]; this
0x18013f114  call    ??1IJumpListImageHelpersStatics@Private@JumpList@Shell@WindowsInternal@winrt@@QEAA@XZ; winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics(void)
0x18013f119  jmp     loc_18013F4BD
0x18013f11e  lea     rcx, [rsp+220h+var_1B8]
0x18013f123  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18013f128  lea     rcx, [rsp+220h+var_1B0]; this
0x18013f12d  call    ??1IJumpListImageHelpersStatics@Private@JumpList@Shell@WindowsInternal@winrt@@QEAA@XZ; winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics(void)
0x18013f132  mov     [rsp+220h+var_1C0], r15d
0x18013f137  mov     [rsp+220h+var_1F0], r15
0x18013f13c  test    rdi, rdi
0x18013f13f  jz      loc_18013F1CE
0x18013f145  mov     rax, [rdi]
0x18013f148  lea     rdx, [rsp+220h+var_1C0]
0x18013f14d  mov     rcx, rdi
0x18013f150  mov     rax, [rax+38h]
0x18013f154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f159  mov     ebx, eax
0x18013f15b  test    eax, eax
0x18013f15d  jns     short loc_18013F189
0x18013f15f  mov     edx, 0FCh; void *
0x18013f164  mov     rcx, [rbp+128h]; this
0x18013f16b  mov     r9d, eax; char *
0x18013f16e  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f175  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f17a  lea     rcx, [rsp+220h+var_1F0]
0x18013f17f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f184  jmp     loc_18013F4C0
0x18013f189  mov     rax, [rdi]
0x18013f18c  mov     rbx, [rax+80h]
0x18013f193  lea     rcx, [rsp+220h+var_1F0]
0x18013f198  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f19d  lea     rdx, [rsp+220h+var_1F0]
0x18013f1a2  mov     rcx, rdi
0x18013f1a5  mov     rax, rbx
0x18013f1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f1ad  mov     ebx, eax
0x18013f1af  test    eax, eax
0x18013f1b1  jns     short loc_18013F1BA
0x18013f1b3  mov     edx, 0FDh
0x18013f1b8  jmp     short loc_18013F164
0x18013f1ba  mov     qword ptr [rbp+120h+hstringHeader.Reserved], r15
0x18013f1be  lea     rcx, [rbp+120h+hstringHeader]
0x18013f1c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f1c7  cmp     [rsp+220h+var_1F0], r15
0x18013f1cc  jnz     short loc_18013F20A
0x18013f1ce  mov     [rbp+120h+var_188], r15
0x18013f1d2  mov     r9d, 27h ; '''; unsigned int
0x18013f1d8  lea     r8d, [r9+1]; unsigned int
0x18013f1dc  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x18013f1e3  lea     rcx, [rbp+120h+hstringHeader]; hstringHeader
0x18013f1e7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18013f1ec  lea     rdx, [rsp+220h+var_1F0]
0x18013f1f1  mov     rcx, [rbp+120h+var_188]
0x18013f1f5  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18013f1fa  mov     ebx, eax
0x18013f1fc  test    eax, eax
0x18013f1fe  jns     short loc_18013F20A
0x18013f200  mov     edx, 108h
0x18013f205  jmp     loc_18013F164
0x18013f20a  mov     [rsp+220h+var_1E0], r15
0x18013f20f  mov     rax, [rsi]
0x18013f212  mov     rbx, [rax+30h]
0x18013f216  lea     rcx, [rsp+220h+var_1E0]
0x18013f21b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f220  lea     rdx, [rsp+220h+var_1E0]
0x18013f225  mov     rcx, rsi
0x18013f228  mov     rax, rbx
0x18013f22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f230  mov     ebx, eax
0x18013f232  test    eax, eax
0x18013f234  jns     short loc_18013F260
0x18013f236  mov     rcx, [rbp+128h]; this
0x18013f23d  mov     r9d, eax; char *
0x18013f240  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f247  mov     edx, 10Ch; void *
0x18013f24c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f251  lea     rcx, [rsp+220h+var_1E0]
0x18013f256  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f25b  jmp     loc_18013F17A
0x18013f260  mov     [rsp+220h+var_1D0], r15
0x18013f265  lea     rdx, [rsp+220h+var_1D0]
0x18013f26a  lea     rcx, [rsp+220h+var_1E0]
0x18013f26f  call    ??$As@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>>)
0x18013f274  mov     ebx, eax
0x18013f276  test    eax, eax
0x18013f278  jns     short loc_18013F2A1
0x18013f27a  mov     rcx, [rbp+128h]; this
0x18013f281  mov     r9d, eax; char *
0x18013f284  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f28b  mov     edx, 10Fh; void *
0x18013f290  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f295  lea     rcx, [rsp+220h+var_1D0]
0x18013f29a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f29f  jmp     short loc_18013F251
0x18013f2a1  mov     [rsp+220h+string], r15
0x18013f2a6  mov     rdi, [rsp+220h+var_1D0]
0x18013f2ab  mov     rax, [rdi]
0x18013f2ae  mov     rbx, [rax+30h]
0x18013f2b2  xor     ecx, ecx; string
0x18013f2b4  call    cs:__imp_WindowsDeleteString
0x18013f2ba  mov     [rsp+220h+string], r15
0x18013f2bf  lea     rdx, [rsp+220h+string]
0x18013f2c4  mov     rcx, rdi
0x18013f2c7  mov     rax, rbx
0x18013f2ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f2cf  mov     ebx, eax
0x18013f2d1  test    eax, eax
0x18013f2d3  jns     short loc_18013F302
0x18013f2d5  mov     rcx, [rbp+128h]; this
0x18013f2dc  mov     r9d, eax; char *
0x18013f2df  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f2e6  mov     edx, 112h; void *
0x18013f2eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f2f0  mov     rcx, [rsp+220h+string]; string
0x18013f2f5  call    cs:__imp_WindowsDeleteString
0x18013f2fb  mov     [rsp+220h+string], r15
0x18013f300  jmp     short loc_18013F295
0x18013f302  mov     [rsp+220h+pUnk], r15
0x18013f307  lea     rcx, [rsp+220h+pUnk]
0x18013f30c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f311  lea     rax, [rsp+220h+pUnk]
0x18013f316  mov     qword ptr [rsp+220h+ppv], rax; int
0x18013f31b  lea     r9, _GUID_9767060c_9476_42e2_8f7b_2f10fd13765c; riid
0x18013f322  xor     edx, edx; pUnkOuter
0x18013f324  mov     r8d, 404h; dwClsContext
0x18013f32a  lea     rcx, _GUID_228826af_02e1_4226_a9e0_99a855e455a6; rclsid
0x18013f331  call    cs:__imp_CoCreateInstance
0x18013f337  mov     ebx, eax
0x18013f339  test    eax, eax
0x18013f33b  jns     short loc_18013F364
0x18013f33d  mov     rcx, [rbp+128h]; this
0x18013f344  mov     r9d, eax; char *
0x18013f347  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f34e  mov     edx, 116h; void *
0x18013f353  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f358  lea     rcx, [rsp+220h+pUnk]
0x18013f35d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f362  jmp     short loc_18013F2F0
0x18013f364  call    IsCoAllowSetForegroundWindowPresent
0x18013f369  test    al, al
0x18013f36b  jz      short loc_18013F37A
0x18013f36d  xor     edx, edx; lpvReserved
0x18013f36f  mov     rcx, [rsp+220h+pUnk]; pUnk
0x18013f374  call    cs:__imp_CoAllowSetForegroundWindow
0x18013f37a  mov     [rsp+220h+var_1C8], r15
0x18013f37f  mov     rdi, [rsp+220h+pUnk]
0x18013f384  mov     rax, [rdi]
0x18013f387  mov     rbx, [rax+60h]
0x18013f38b  lea     rcx, [rsp+220h+var_1C8]
0x18013f390  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f395  lea     r9, [rsp+220h+var_1C8]
0x18013f39a  lea     r8, _GUID_1a91faba_b93c_456b_a10d_0036d2a68be6
0x18013f3a1  lea     rdx, _GUID_c735d7d4_b88a_41f2_b35d_da0141e7348a
0x18013f3a8  mov     rcx, rdi
0x18013f3ab  mov     rax, rbx
0x18013f3ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f3b3  mov     ebx, eax
0x18013f3b5  test    eax, eax
0x18013f3b7  jns     short loc_18013F3E3
0x18013f3b9  mov     edx, 11Fh; void *
0x18013f3be  mov     rcx, [rbp+128h]; this
0x18013f3c5  mov     r9d, eax; char *
0x18013f3c8  lea     r8, aShellcommonShe_148; "shellcommon\\shell\\datastorecache\\tra"...
0x18013f3cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013f3d4  lea     rcx, [rsp+220h+var_1C8]
0x18013f3d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f3de  jmp     loc_18013F358
0x18013f3e3  mov     eax, [rsp+220h+var_1C0]
0x18013f3e7  mov     edx, 2
0x18013f3ec  test    al, 1
0x18013f3ee  jnz     short loc_18013F41C
0x18013f3f0  test    dl, al
0x18013f3f2  jz      short loc_18013F3FB
0x18013f3f4  mov     edx, 3
0x18013f3f9  jmp     short loc_18013F41C
0x18013f3fb  mov     edx, 4
0x18013f400  test    dl, al
0x18013f402  jz      short loc_18013F40B
0x18013f404  mov     edx, 1
0x18013f409  jmp     short loc_18013F41C
0x18013f40b  test    al, 10h
0x18013f40d  jnz     short loc_18013F41C
0x18013f40f  mov     edx, r15d
0x18013f412  test    al, 20h
0x18013f414  mov     eax, 5
0x18013f419  cmovnz  edx, eax
0x18013f41c  mov     rcx, [rsp+220h+var_1F0]
0x18013f421  call    ?RequestActivationType@AppActivationPropertySetHelpers@@YAJPEAUIPropertySet@Collections@Foundation@Windows@@W4ActivationType@1@@Z; AppActivationPropertySetHelpers::RequestActivationType(Windows::Foundation::Collections::IPropertySet *,AppActivationPropertySetHelpers::ActivationType)
0x18013f426  mov     ebx, eax
0x18013f428  test    eax, eax
0x18013f42a  jns     short loc_18013F433
0x18013f42c  mov     edx, 138h
0x18013f431  jmp     short loc_18013F3BE
0x18013f433  mov     rsi, [rsp+220h+var_1C8]
0x18013f438  mov     rax, [rsi]
0x18013f43b  mov     rdi, [rax+18h]
0x18013f43f  mov     rbx, [rsp+220h+var_1F0]
0x18013f444  xor     edx, edx; length
0x18013f446  mov     rcx, [rsp+220h+string]; string
0x18013f44b  call    cs:__imp_WindowsGetStringRawBuffer
0x18013f451  mov     r8, rbx
0x18013f454  mov     rdx, rax
0x18013f457  mov     rcx, rsi
0x18013f45a  mov     rax, rdi
0x18013f45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013f462  mov     ebx, eax
0x18013f464  test    eax, eax
0x18013f466  jns     short loc_18013F472
0x18013f468  mov     edx, 13Fh
0x18013f46d  jmp     loc_18013F3BE
0x18013f472  lea     rcx, [rbp+120h+var_180]
0x18013f476  call    ?Stop@?$ActivityBase@VDataStoreTransformerLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DataStoreTransformerLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18013f47b  lea     rcx, [rsp+220h+var_1C8]
0x18013f480  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f485  lea     rcx, [rsp+220h+pUnk]
0x18013f48a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f48f  mov     rcx, [rsp+220h+string]; string
0x18013f494  call    cs:__imp_WindowsDeleteString
0x18013f49a  mov     [rsp+220h+string], r15
0x18013f49f  lea     rcx, [rsp+220h+var_1D0]
0x18013f4a4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f4a9  lea     rcx, [rsp+220h+var_1E0]
0x18013f4ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f4b3  lea     rcx, [rsp+220h+var_1F0]
0x18013f4b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013f4bd  mov     ebx, r15d
0x18013f4c0  lea     rcx, [rbp+120h+var_180]; this
0x18013f4c4  call    ??1AppResolverTransformerActivateTile@DataStoreTransformerTelemetry@@QEAA@XZ; DataStoreTransformerTelemetry::AppResolverTransformerActivateTile::~AppResolverTransformerActivateTile(void)
0x18013f4c9  mov     eax, ebx
0x18013f4cb  mov     rcx, [rbp+120h+var_30]
0x18013f4d2  xor     rcx, rsp; StackCookie
0x18013f4d5  call    __security_check_cookie
0x18013f4da  mov     rbx, [rsp+220h+arg_18]
  ... truncated ...
```
