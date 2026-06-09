# WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::ActivateWithContextAsync(WindowsInternal::Shell::UnifiedTile::ITileActivationContext *,Windows::Foundation::IAsyncAction * *)

- ea: `0x180135ef0`
- end: `0x180136593`
- name: `?ActivateWithContextAsync@UnifiedTileWrapper@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAUITileActivationContext@234@PEAPEAUIAsyncAction@Foundation@Windows@@@Z`
- size: `1699`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper *__hidden this, struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1802df6c0`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18002ca10`
- `0x180073930`
- `0x18007a0ac`
- `0x1800a2c4c`
- `0x1800dd908`
- `0x1800ffc20`
- `0x180112c24`
- `0x180112cc8`
- `0x180135ef0`
- `0x18013659c`
- `0x1801a272c`
- `0x1801aefec`
- `0x180201e50`
- `0x1802def88`
- `0x1802df700`
- `0x1802e0ba4`
- `0x1802e0cec`
- `0x1802e0d2c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136057`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801360fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18013615f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801361e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801362e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136376`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136419`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136493`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136511`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136551`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136057`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801360fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18013615f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801361e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1801362e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136376`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136419`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136493`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136511`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180136551`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801362ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013633c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801362ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18013633c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180136393`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180135fac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180135fac`

## string_xrefs

- `0x180136030`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`
- `0x1801360c8`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`
- `0x18013612d`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`
- `0x1801361aa`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`
- `0x180136295`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`
- `0x180136325`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`
- `0x1801363dc`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`
- `0x180136456`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`
- `0x1801364df`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtilewrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::UnifiedTileWrapper::ActivateWithContextAsync(
        HSTRING *this,
        struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *a2,
        struct Windows::Foundation::IAsyncAction **a3)
{
  struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *v4; // rsi
  char v6; // di
  const unsigned __int16 *StringRawBuffer; // rbx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *, __int64 *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rcx
  int v15; // eax
  wil::filetime *v16; // rcx
  HSTRING v17; // rbx
  HSTRING v18; // r15
  struct _FILETIME system_time; // rax
  struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *v20; // rax
  int v21; // eax
  unsigned int v22; // edi
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, __int64 *); // rbx
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30[2]; // [rsp+20h] [rbp-1D8h] BYREF
  __int64 v31; // [rsp+28h] [rbp-1D0h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *v32; // [rsp+30h] [rbp-1C8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-1C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-1B8h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *v35; // [rsp+48h] [rbp-1B0h] BYREF
  _BYTE v36[32]; // [rsp+50h] [rbp-1A8h] BYREF
  _QWORD v37[42]; // [rsp+70h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v4 = a2;
  v35 = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowLatencyProfile>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LowLatencyProfile>::GetImpl'::`2'::impl) )
  {
    winrt::param::hstring::hstring((winrt::param::hstring *)v36, L"TileStoreTransformer.ActivateTileInternal");
    winrt::WindowsUdk::UI::Shell::LowLatencyAction::Create((const struct winrt::param::hstring *)&string);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowLatencyProfileForApplicationLaunch>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LowLatencyProfileForApplicationLaunch>::GetImpl'::`2'::impl) )
    {
      v30[0] = 4;
      winrt::impl::consume_WindowsUdk_UI_Shell_ILowLatencyAction<winrt::WindowsUdk::UI::Shell::ILowLatencyAction>::TriggerBoost(
        &string,
        v30);
      v6 = 1;
    }
    else
    {
      v6 = 1;
      v30[0] = 1;
      winrt::impl::consume_WindowsUdk_UI_Shell_ILowLatencyAction<winrt::WindowsUdk::UI::Shell::ILowLatencyAction>::TriggerBoost(
        &string,
        v30);
    }
    winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics((winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics *)&string);
  }
  else
  {
    v6 = 1;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(this[24], 0);
  wil::ActivityBase<UnifiedTileLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UnifiedTileLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v37);
  v37[0] = &UnifiedTileTelemetry::UnifiedTile_ActivateAsync::`vftable';
  UnifiedTileTelemetry::UnifiedTile_ActivateAsync::StartActivity(
    (UnifiedTileTelemetry::UnifiedTile_ActivateAsync *)v37,
    StringRawBuffer);
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, this + 23);
  v8 = 0;
  v31 = 0;
  if ( v4 )
  {
    v9 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *, __int64 *))(*(_QWORD *)v4 + 112LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v10 = v9(v4, &v31);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
        (const char *)(unsigned int)v10,
        v30[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
LABEL_56:
      UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync((UnifiedTileTelemetry::UnifiedTile_ActivateAsync *)v37);
      return v11;
    }
    v8 = v31;
  }
  v32 = 0;
  if ( !v8 && this[20] != this[19] )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    if ( v4 )
    {
      v13 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::TileActivationContext,WindowsInternal::Shell::UnifiedTile::ITileActivationContext,WindowsInternal::Shell::UnifiedTile::ITileActivationContext * &>(
              &v32,
              &v35);
      v11 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
          (const char *)(unsigned int)v13,
          v30[0]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        goto LABEL_56;
      }
    }
    else
    {
      v12 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::TileActivationContext,WindowsInternal::Shell::UnifiedTile::ITileActivationContext,>(&v32);
      v11 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9F,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
          (const char *)(unsigned int)v12,
          v30[0]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
        if ( SRWLock )
          ReleaseSRWLockShared(SRWLock);
        goto LABEL_56;
      }
    }
    v4 = v32;
    *(_QWORD *)v30 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
    v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
            v14,
            v30);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
        (const char *)(unsigned int)v15,
        v30[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
      goto LABEL_56;
    }
    v17 = this[19];
    v18 = this[20];
    while ( v17 != v18 )
    {
      system_time = wil::filetime::get_system_time(v16);
      if ( v6
        || (v16 = (wil::filetime *)((*(_QWORD *)&system_time & 0xFFFFFFFF00000000uLL)
                                  - 9000000000LL
                                  + system_time.dwLowDateTime),
            *((unsigned int *)v17 + 10) + ((unsigned __int64)*((unsigned int *)v17 + 11) << 32) > (unsigned __int64)v16) )
      {
        string = 0;
        v20 = (struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *)(v17 + 2);
        if ( *((_QWORD *)v17 + 4) > 7u )
          v20 = *(struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext **)v20;
        v35 = v20;
        v21 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string);
        v22 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB6,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
            (const char *)(unsigned int)v21,
            v30[0]);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
          if ( SRWLock )
            ReleaseSRWLockShared(SRWLock);
LABEL_37:
          UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync((UnifiedTileTelemetry::UnifiedTile_ActivateAsync *)v37);
          return v22;
        }
        v24 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**(_QWORD **)v30 + 104LL))(*(_QWORD *)v30, string);
        v22 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB7,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
            (const char *)(unsigned int)v24,
            v30[0]);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
          if ( SRWLock )
            ReleaseSRWLockShared(SRWLock);
          goto LABEL_37;
        }
        WindowsDeleteString(string);
      }
      v6 = 0;
      v17 += 12;
    }
    v25 = *(_QWORD *)v30;
    v26 = *(__int64 (__fastcall **)(__int64, __int64 *))(**(_QWORD **)v30 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v27 = v26(v25, &v31);
    v11 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
        (const char *)(unsigned int)v27,
        v30[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
      goto LABEL_56;
    }
    v28 = (*(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *, __int64))(*(_QWORD *)v4 + 104LL))(
            v4,
            v31);
    v11 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBD,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
        (const char *)(unsigned int)v28,
        v30[0]);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      if ( SRWLock )
        ReleaseSRWLockShared(SRWLock);
      goto LABEL_56;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v30);
  }
  v29 = (*(__int64 (__fastcall **)(HSTRING, struct WindowsInternal::Shell::UnifiedTile::ITileActivationContext *, struct Windows::Foundation::IAsyncAction **))(*(_QWORD *)this[13] + 136LL))(
          this[13],
          v4,
          a3);
  v11 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtilewrapper.cpp",
      (const char *)(unsigned int)v29,
      v30[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    goto LABEL_56;
  }
  wil::ActivityBase<UnifiedTileLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
  if ( SRWLock )
    ReleaseSRWLockShared(SRWLock);
  UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync((UnifiedTileTelemetry::UnifiedTile_ActivateAsync *)v37);
  return 0;
}

```

## disassembly

```asm
0x180135ef0  mov     [rsp+arg_18], rbx
0x180135ef5  push    rsi
0x180135ef6  push    rdi
0x180135ef7  push    r12
0x180135ef9  push    r14
0x180135efb  push    r15
0x180135efd  sub     rsp, 1D0h
0x180135f04  mov     rax, cs:__security_cookie
0x180135f0b  xor     rax, rsp
0x180135f0e  mov     [rsp+1F8h+var_38], rax
0x180135f16  mov     r12, r8
0x180135f19  mov     rsi, rdx
0x180135f1c  mov     r14, rcx
0x180135f1f  mov     [rsp+1F8h+var_1B0], rdx
0x180135f24  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LowLatencyProfile@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LowLatencyProfile@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowLatencyProfile> `wil::Feature<__WilFeatureTraits_Feature_LowLatencyProfile>::GetImpl(void)'::`2'::impl
0x180135f2b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LowLatencyProfile@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowLatencyProfile>::__private_IsEnabled(void)
0x180135f30  test    al, al
0x180135f32  jz      short loc_180135F9E
0x180135f34  lea     rdx, aTilestoretrans_13; "TileStoreTransformer.ActivateTileIntern"...
0x180135f3b  lea     rcx, [rsp+1F8h+var_1A8]; this
0x180135f40  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x180135f45  lea     rdx, [rsp+1F8h+var_1A8]
0x180135f4a  lea     rcx, [rsp+1F8h+string]; struct winrt::param::hstring *
0x180135f4f  call    ?Create@LowLatencyAction@Shell@UI@WindowsUdk@winrt@@SA@AEBUhstring@param@5@@Z; winrt::WindowsUdk::UI::Shell::LowLatencyAction::Create(winrt::param::hstring const &)
0x180135f54  nop
0x180135f55  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LowLatencyProfileForApplicationLaunch@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LowLatencyProfileForApplicationLaunch@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowLatencyProfileForApplicationLaunch> `wil::Feature<__WilFeatureTraits_Feature_LowLatencyProfileForApplicationLaunch>::GetImpl(void)'::`2'::impl
0x180135f5c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LowLatencyProfileForApplicationLaunch@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LowLatencyProfileForApplicationLaunch>::__private_IsEnabled(void)
0x180135f61  lea     rdx, [rsp+1F8h+var_1D8]
0x180135f66  lea     rcx, [rsp+1F8h+string]
0x180135f6b  test    al, al
0x180135f6d  jz      short loc_180135F83
0x180135f6f  mov     [rsp+1F8h+var_1D8], 4
0x180135f77  call    ?TriggerBoost@?$consume_WindowsUdk_UI_Shell_ILowLatencyAction@UILowLatencyAction@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBW4BoostType@Shell@UI@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_ILowLatencyAction<winrt::WindowsUdk::UI::Shell::ILowLatencyAction>::TriggerBoost(winrt::WindowsUdk::UI::Shell::BoostType const &)
0x180135f7c  mov     edi, 1
0x180135f81  jmp     short loc_180135F92
0x180135f83  mov     edi, 1
0x180135f88  mov     [rsp+1F8h+var_1D8], edi
0x180135f8c  call    ?TriggerBoost@?$consume_WindowsUdk_UI_Shell_ILowLatencyAction@UILowLatencyAction@Shell@UI@WindowsUdk@winrt@@@impl@winrt@@QEBA@AEBW4BoostType@Shell@UI@WindowsUdk@3@@Z; winrt::impl::consume_WindowsUdk_UI_Shell_ILowLatencyAction<winrt::WindowsUdk::UI::Shell::ILowLatencyAction>::TriggerBoost(winrt::WindowsUdk::UI::Shell::BoostType const &)
0x180135f91  nop
0x180135f92  lea     rcx, [rsp+1F8h+string]; this
0x180135f97  call    ??1IJumpListImageHelpersStatics@Private@JumpList@Shell@WindowsInternal@winrt@@QEAA@XZ; winrt::WindowsInternal::Shell::JumpList::Private::IJumpListImageHelpersStatics::~IJumpListImageHelpersStatics(void)
0x180135f9c  jmp     short loc_180135FA3
0x180135f9e  mov     edi, 1
0x180135fa3  xor     edx, edx; length
0x180135fa5  mov     rcx, [r14+0C0h]; string
0x180135fac  call    cs:__imp_WindowsGetStringRawBuffer
0x180135fb2  mov     rbx, rax
0x180135fb5  lea     rdx, aUnifiedtileAct; "UnifiedTile_ActivateAsync"
0x180135fbc  lea     rcx, [rsp+1F8h+var_188]; struct wil::details::IFailureCallback *
0x180135fc1  call    ??0?$ActivityBase@VUnifiedTileLogging@@$0A@$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UnifiedTileLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UnifiedTileLogging,0,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180135fc6  lea     rax, ??_7UnifiedTile_ActivateAsync@UnifiedTileTelemetry@@6B@; const UnifiedTileTelemetry::UnifiedTile_ActivateAsync::`vftable'
0x180135fcd  mov     [rsp+1F8h+var_188], rax
0x180135fd2  mov     rdx, rbx; unsigned __int16 *
0x180135fd5  lea     rcx, [rsp+1F8h+var_188]; this
0x180135fda  call    ?StartActivity@UnifiedTile_ActivateAsync@UnifiedTileTelemetry@@QEAAXPEBG@Z; UnifiedTileTelemetry::UnifiedTile_ActivateAsync::StartActivity(ushort const *)
0x180135fdf  nop
0x180135fe0  lea     rdx, [r14+0B8h]
0x180135fe7  lea     rcx, [rsp+1F8h+SRWLock]
0x180135fec  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180135ff1  nop
0x180135ff2  xor     eax, eax
0x180135ff4  mov     [rsp+1F8h+var_1D0], rax
0x180135ff9  test    rsi, rsi
0x180135ffc  jz      short loc_180136074
0x180135ffe  mov     rax, [rsi]
0x180136001  mov     rbx, [rax+70h]
0x180136005  lea     rcx, [rsp+1F8h+var_1D0]
0x18013600a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013600f  lea     rdx, [rsp+1F8h+var_1D0]
0x180136014  mov     rcx, rsi
0x180136017  mov     rax, rbx
0x18013601a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013601f  mov     ebx, eax
0x180136021  test    eax, eax
0x180136023  jns     short loc_18013606F
0x180136025  mov     rcx, [rsp+1F8h]; this
0x18013602d  mov     r9d, eax; char *
0x180136030  lea     r8, aShellcommonShe_136; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180136037  mov     edx, 97h; void *
0x18013603c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180136041  nop
0x180136042  lea     rcx, [rsp+1F8h+var_1D0]
0x180136047  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013604c  nop
0x18013604d  mov     rcx, [rsp+1F8h+SRWLock]; SRWLock
0x180136052  test    rcx, rcx
0x180136055  jz      short loc_18013605E
0x180136057  call    cs:__imp_ReleaseSRWLockShared
0x18013605d  nop
0x18013605e  lea     rcx, [rsp+1F8h+var_188]; this
0x180136063  call    ??1UnifiedTile_ActivateAsync@UnifiedTileTelemetry@@QEAA@XZ; UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync(void)
0x180136068  mov     eax, ebx
0x18013606a  jmp     loc_18013656A
0x18013606f  mov     rax, [rsp+1F8h+var_1D0]
0x180136074  mov     [rsp+1F8h+var_1C8], 0
0x18013607d  test    rax, rax
0x180136080  jnz     loc_1801364B5
0x180136086  mov     rax, [r14+0A0h]
0x18013608d  cmp     rax, [r14+98h]
0x180136094  jz      loc_1801364B5
0x18013609a  lea     rcx, [rsp+1F8h+var_1C8]
0x18013609f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801360a4  lea     rcx, [rsp+1F8h+var_1C8]
0x1801360a9  test    rsi, rsi
0x1801360ac  jnz     short loc_180136112
0x1801360ae  call    ??$MakeAndInitialize@VTileActivationContext@UnifiedTile@Shell@WindowsInternal@@UITileActivationContext@234@$$V@Details@WRL@Microsoft@@YAJPEAPEAUITileActivationContext@UnifiedTile@Shell@WindowsInternal@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::TileActivationContext,WindowsInternal::Shell::UnifiedTile::ITileActivationContext,>(WindowsInternal::Shell::UnifiedTile::ITileActivationContext * *)
0x1801360b3  mov     ebx, eax
0x1801360b5  test    eax, eax
0x1801360b7  jns     loc_180136177
0x1801360bd  mov     rcx, [rsp+1F8h]; this
0x1801360c5  mov     r9d, eax; char *
0x1801360c8  lea     r8, aShellcommonShe_136; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1801360cf  mov     edx, 9Fh; void *
0x1801360d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801360d9  nop
0x1801360da  lea     rcx, [rsp+1F8h+var_1C8]
0x1801360df  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801360e4  nop
0x1801360e5  lea     rcx, [rsp+1F8h+var_1D0]
0x1801360ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801360ef  nop
0x1801360f0  mov     rcx, [rsp+1F8h+SRWLock]; SRWLock
0x1801360f5  test    rcx, rcx
0x1801360f8  jz      short loc_180136101
0x1801360fa  call    cs:__imp_ReleaseSRWLockShared
0x180136100  nop
0x180136101  lea     rcx, [rsp+1F8h+var_188]; this
0x180136106  call    ??1UnifiedTile_ActivateAsync@UnifiedTileTelemetry@@QEAA@XZ; UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync(void)
0x18013610b  mov     eax, ebx
0x18013610d  jmp     loc_18013656A
0x180136112  lea     rdx, [rsp+1F8h+var_1B0]
0x180136117  call    ??$MakeAndInitialize@VTileActivationContext@UnifiedTile@Shell@WindowsInternal@@UITileActivationContext@234@AEAPEAU5234@@Details@WRL@Microsoft@@YAJPEAPEAUITileActivationContext@UnifiedTile@Shell@WindowsInternal@@AEAPEAU3456@@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::TileActivationContext,WindowsInternal::Shell::UnifiedTile::ITileActivationContext,WindowsInternal::Shell::UnifiedTile::ITileActivationContext * &>(WindowsInternal::Shell::UnifiedTile::ITileActivationContext * *,WindowsInternal::Shell::UnifiedTile::ITileActivationContext * &)
0x18013611c  mov     ebx, eax
0x18013611e  test    eax, eax
0x180136120  jns     short loc_180136177
0x180136122  mov     rcx, [rsp+1F8h]; this
0x18013612a  mov     r9d, eax; char *
0x18013612d  lea     r8, aShellcommonShe_136; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180136134  mov     edx, 0A4h; void *
0x180136139  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013613e  nop
0x18013613f  lea     rcx, [rsp+1F8h+var_1C8]
0x180136144  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180136149  nop
0x18013614a  lea     rcx, [rsp+1F8h+var_1D0]
0x18013614f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180136154  nop
0x180136155  mov     rcx, [rsp+1F8h+SRWLock]; SRWLock
0x18013615a  test    rcx, rcx
0x18013615d  jz      short loc_180136166
0x18013615f  call    cs:__imp_ReleaseSRWLockShared
0x180136165  nop
0x180136166  lea     rcx, [rsp+1F8h+var_188]; this
0x18013616b  call    ??1UnifiedTile_ActivateAsync@UnifiedTileTelemetry@@QEAA@XZ; UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync(void)
0x180136170  mov     eax, ebx
0x180136172  jmp     loc_18013656A
0x180136177  mov     rsi, [rsp+1F8h+var_1C8]
0x18013617c  mov     qword ptr [rsp+1F8h+var_1D8], 0; int
0x180136185  lea     rcx, [rsp+1F8h+var_1D8]
0x18013618a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013618f  lea     rdx, [rsp+1F8h+var_1D8]
0x180136194  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x180136199  mov     ebx, eax
0x18013619b  test    eax, eax
0x18013619d  jns     short loc_1801361FF
0x18013619f  mov     rcx, [rsp+1F8h]; this
0x1801361a7  mov     r9d, eax; char *
0x1801361aa  lea     r8, aShellcommonShe_136; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1801361b1  mov     edx, 0A9h; void *
0x1801361b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801361bb  nop
0x1801361bc  lea     rcx, [rsp+1F8h+var_1D8]
0x1801361c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801361c6  nop
0x1801361c7  lea     rcx, [rsp+1F8h+var_1C8]
0x1801361cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801361d1  nop
0x1801361d2  lea     rcx, [rsp+1F8h+var_1D0]
0x1801361d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801361dc  nop
0x1801361dd  mov     rcx, [rsp+1F8h+SRWLock]; SRWLock
0x1801361e2  test    rcx, rcx
0x1801361e5  jz      short loc_1801361EE
0x1801361e7  call    cs:__imp_ReleaseSRWLockShared
0x1801361ed  nop
0x1801361ee  lea     rcx, [rsp+1F8h+var_188]; this
0x1801361f3  call    ??1UnifiedTile_ActivateAsync@UnifiedTileTelemetry@@QEAA@XZ; UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync(void)
0x1801361f8  mov     eax, ebx
0x1801361fa  jmp     loc_18013656A
0x1801361ff  mov     rbx, [r14+98h]
0x180136206  mov     r15, [r14+0A0h]
0x18013620d  cmp     rbx, r15
0x180136210  jz      loc_1801363A5
0x180136216  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x18013621b  test    dil, dil
0x18013621e  jnz     short loc_180136259
0x180136220  mov     r8d, [rbx+2Ch]
0x180136224  shl     r8, 20h
0x180136228  mov     ecx, [rbx+28h]
0x18013622b  add     r8, rcx
0x18013622e  mov     rdx, rax
0x180136231  mov     rcx, 0FFFFFFFF00000000h
0x18013623b  and     rdx, rcx
0x18013623e  mov     ecx, eax
0x180136240  mov     rax, 0FFFFFFFDE78EE600h
0x18013624a  add     rax, rdx
0x18013624d  add     rcx, rax
0x180136250  cmp     r8, rcx
0x180136253  jbe     loc_180136399
0x180136259  mov     [rsp+1F8h+string], 0
0x180136262  lea     rax, [rbx+8]
0x180136266  cmp     qword ptr [rbx+20h], 7
0x18013626b  jbe     short loc_180136270
0x18013626d  mov     rax, [rax]
0x180136270  mov     [rsp+1F8h+var_1B0], rax
0x180136275  lea     rdx, [rsp+1F8h+var_1B0]
0x18013627a  lea     rcx, [rsp+1F8h+string]; string
0x18013627f  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180136284  mov     edi, eax
0x180136286  test    eax, eax
0x180136288  jns     short loc_1801362FE
0x18013628a  mov     rcx, [rsp+1F8h]; this
0x180136292  mov     r9d, eax; char *
0x180136295  lea     r8, aShellcommonShe_136; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18013629c  mov     edx, 0B6h; void *
0x1801362a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801362a6  nop
0x1801362a7  mov     rcx, [rsp+1F8h+string]; string
0x1801362ac  call    cs:__imp_WindowsDeleteString
0x1801362b2  mov     [rsp+1F8h+string], 0
0x1801362bb  lea     rcx, [rsp+1F8h+var_1D8]
0x1801362c0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801362c5  nop
0x1801362c6  lea     rcx, [rsp+1F8h+var_1C8]
0x1801362cb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801362d0  nop
0x1801362d1  lea     rcx, [rsp+1F8h+var_1D0]
0x1801362d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801362db  nop
0x1801362dc  mov     rcx, [rsp+1F8h+SRWLock]; SRWLock
0x1801362e1  test    rcx, rcx
0x1801362e4  jz      short loc_1801362ED
0x1801362e6  call    cs:__imp_ReleaseSRWLockShared
0x1801362ec  nop
0x1801362ed  lea     rcx, [rsp+1F8h+var_188]; this
0x1801362f2  call    ??1UnifiedTile_ActivateAsync@UnifiedTileTelemetry@@QEAA@XZ; UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync(void)
0x1801362f7  mov     eax, edi
0x1801362f9  jmp     loc_18013656A
0x1801362fe  mov     rcx, qword ptr [rsp+1F8h+var_1D8]
0x180136303  mov     rax, [rcx]
0x180136306  mov     rdx, [rsp+1F8h+string]
0x18013630b  mov     rax, [rax+68h]
0x18013630f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180136314  mov     edi, eax
0x180136316  test    eax, eax
0x180136318  jns     short loc_18013638E
0x18013631a  mov     rcx, [rsp+1F8h]; this
0x180136322  mov     r9d, eax; char *
0x180136325  lea     r8, aShellcommonShe_136; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18013632c  mov     edx, 0B7h; void *
0x180136331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180136336  nop
0x180136337  mov     rcx, [rsp+1F8h+string]; string
0x18013633c  call    cs:__imp_WindowsDeleteString
0x180136342  mov     [rsp+1F8h+string], 0
0x18013634b  lea     rcx, [rsp+1F8h+var_1D8]
0x180136350  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180136355  nop
0x180136356  lea     rcx, [rsp+1F8h+var_1C8]
0x18013635b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180136360  nop
0x180136361  lea     rcx, [rsp+1F8h+var_1D0]
0x180136366  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18013636b  nop
0x18013636c  mov     rcx, [rsp+1F8h+SRWLock]; SRWLock
0x180136371  test    rcx, rcx
0x180136374  jz      short loc_18013637D
0x180136376  call    cs:__imp_ReleaseSRWLockShared
0x18013637c  nop
0x18013637d  lea     rcx, [rsp+1F8h+var_188]; this
0x180136382  call    ??1UnifiedTile_ActivateAsync@UnifiedTileTelemetry@@QEAA@XZ; UnifiedTileTelemetry::UnifiedTile_ActivateAsync::~UnifiedTile_ActivateAsync(void)
0x180136387  mov     eax, edi
0x180136389  jmp     loc_18013656A
0x18013638e  mov     rcx, [rsp+1F8h+string]; string
0x180136393  call    cs:__imp_WindowsDeleteString
0x180136399  xor     dil, dil
0x18013639c  add     rbx, 30h ; '0'
0x1801363a0  jmp     loc_18013620D
0x1801363a5  mov     rdi, qword ptr [rsp+1F8h+var_1D8]
0x1801363aa  mov     rax, [rdi]
0x1801363ad  mov     rbx, [rax+40h]
0x1801363b1  lea     rcx, [rsp+1F8h+var_1D0]
0x1801363b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801363bb  lea     rdx, [rsp+1F8h+var_1D0]
0x1801363c0  mov     rcx, rdi
0x1801363c3  mov     rax, rbx
0x1801363c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801363cb  mov     ebx, eax
0x1801363cd  test    eax, eax
0x1801363cf  jns     short loc_180136431
  ... truncated ...
```
