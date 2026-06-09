# WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::GetVerbs(IShellItem *,WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *,HSTRING__ *,Windows::Foundation::Collections::IVectorView<WindowsInternal::Shell::UnifiedTile::TileVerb *> * *)

- ea: `0x1802db560`
- end: `0x1802dbac5`
- name: `?GetVerbs@TileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@SAJPEAUIShellItem@@PEAUIVerbEnumerationArgs@345@PEAUHSTRING__@@PEAPEAU?$IVectorView@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@Z`
- size: `1381`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012b2a0`
- `0x1802db2d0`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180033860`
- `0x180039420`
- `0x1800b1a9c`
- `0x1800b4fd0`
- `0x1800db7c8`
- `0x180123b1c`
- `0x18012be74`
- `0x1801593b0`
- `0x180161204`
- `0x18019a0e8`
- `0x18019b360`
- `0x1801aa8c0`
- `0x1801b8548`
- `0x180201e50`
- `0x1802db560`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802db76d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802db90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802db9ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802db76d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802db90e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802db9ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802db80f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1802db80f`
- `ext-ms-win-com-ole32-l1-1-0!OleUninitialize` at `0x1802dba0e`
- `ext-ms-win-com-ole32-l1-1-0!OleUninitialize` at `0x1802dba64`
- `ext-ms-win-com-ole32-l1-1-0!OleUninitialize` at `0x1802dba0e`
- `ext-ms-win-com-ole32-l1-1-0!OleUninitialize` at `0x1802dba64`
- `ext-ms-win-com-ole32-l1-1-0!OleInitialize` at `0x1802db64c`
- `ext-ms-win-com-ole32-l1-1-0!OleInitialize` at `0x1802db64c`
- `ext-ms-win-ntuser-menu-l1-1-0!CreatePopupMenu` at `0x1802db6d4`
- `ext-ms-win-ntuser-menu-l1-1-0!CreatePopupMenu` at `0x1802db6d4`

## string_xrefs

- `0x1802db5f4`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1802db636`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1802db655`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`
- `0x1802dbab3`: `ShellCommon\internal\Shell\inc\Private\TileShellItemVerb.h`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::GetVerbs(
        __int64 a1,
        WindowsInternal::Shell::UnifiedTile::Private *a2,
        __int64 a3,
        _QWORD *a4)
{
  const char *v7; // r9
  __int64 v8; // rcx
  int v9; // eax
  unsigned int LastError; // ebx
  struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs **v11; // r8
  int v12; // eax
  HRESULT v13; // eax
  int v14; // r14d
  __int64 (__fastcall *v15)(__int64, _QWORD, const GUID *, GUID *); // rbx
  int v16; // eax
  const char *v17; // r9
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  __int64 (__fastcall ***v22)(_QWORD, GUID *, HMENU *); // rdi
  __int64 (__fastcall *v23)(_QWORD, GUID *, HMENU *); // rbx
  int v24; // eax
  __int64 (__fastcall ***v25)(_QWORD, GUID *, HMENU *); // rdi
  __int64 (__fastcall *v26)(_QWORD, GUID *, __int64 *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // rdx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  int v38[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  HMENU PopupMenu; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v44[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v45; // [rsp+88h] [rbp-78h] BYREF
  PCWSTR v46[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v47[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  *a4 = 0;
  wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v47);
  v47[0] = &UnifiedTileTelemetry::TileShellItemVerbGetVerbs::`vftable';
  UnifiedTileTelemetry::TileShellItemVerbGetVerbs::StartActivity((UnifiedTileTelemetry::TileShellItemVerbGetVerbs *)v47);
  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x29,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      v7);
  v42 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  v9 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::TileVerb,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0>>(
         v8,
         &v42);
  LastError = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v9,
      v35);
LABEL_50:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    UnifiedTileTelemetry::TileShellItemVerbGetVerbs::~TileShellItemVerbGetVerbs((UnifiedTileTelemetry::TileShellItemVerbGetVerbs *)v47);
    return LastError;
  }
  v39 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  v12 = WindowsInternal::Shell::UnifiedTile::Private::CopyVerbEnumerationArgs(
          a2,
          (struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *)&v39,
          v11);
  LastError = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v12,
      v35);
LABEL_49:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    goto LABEL_50;
  }
  v13 = OleInitialize(0);
  v14 = v13;
  if ( v13 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x35,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v13,
      v35);
  *(_QWORD *)v38 = 0;
  v15 = *(__int64 (__fastcall **)(__int64, _QWORD, const GUID *, GUID *))(*(_QWORD *)a1 + 24LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38);
  v16 = v15(a1, 0, &BHID_SFUIObject, &GUID_000214e4_0000_0000_c000_000000000046);
  LastError = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v16,
      (int)v38);
    goto LABEL_47;
  }
  PopupMenu = CreatePopupMenu();
  wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&int DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>>(
    v44,
    &PopupMenu);
  if ( !v44[0] || !*(_QWORD *)v44[0] )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x47,
                  (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
                  v17);
    goto LABEL_46;
  }
  v40 = 0;
  v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 48LL))(v39, &v40);
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v18,
      (int)v38);
LABEL_46:
    std::shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>::~shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>(v44);
LABEL_47:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38);
    if ( v14 >= 0 )
      OleUninitialize();
    goto LABEL_49;
  }
  string = 0;
  v19 = v39;
  v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v21 = v20(v19, &string);
  if ( v21 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v21,
      (int)v38);
    goto LABEL_26;
  }
  if ( string )
  {
    PopupMenu = 0;
    v22 = *(__int64 (__fastcall ****)(_QWORD, GUID *, HMENU *))v38;
    v23 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, HMENU *))v38;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&PopupMenu);
    v24 = v23(v22, &GUID_649e2263_dc09_466f_9d66_3eb133ee8f81, &PopupMenu);
    if ( v24 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
        (const char *)(unsigned int)v24,
        (int)v38);
LABEL_25:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&PopupMenu);
      goto LABEL_26;
    }
    v46[0] = WindowsGetStringRawBuffer(string, 0);
    (*(void (__fastcall **)(HMENU, PCWSTR *, __int64))(*(_QWORD *)PopupMenu + 24LL))(PopupMenu, v46, 1);
    v45 = 0;
    v25 = *(__int64 (__fastcall ****)(_QWORD, GUID *, HMENU *))v38;
    v26 = ***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v38;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
    v27 = v26(v25, &GUID_7690aa79_f8fc_4615_a327_36f7d18f5d91, &v45);
    if ( v27 >= 0 )
    {
      v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v45 + 32LL))(v45, 512);
      if ( v27 >= 0 )
      {
LABEL_24:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        goto LABEL_25;
      }
      v28 = 113;
    }
    else
    {
      v28 = 110;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v27,
      (int)v38);
    goto LABEL_24;
  }
LABEL_26:
  if ( v44[0] )
    v29 = *(_QWORD *)v44[0];
  else
    v29 = 0;
  v36 = 0x7FFF;
  v30 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)v38 + 24LL))(
          *(_QWORD *)v38,
          v29,
          0,
          1);
  LastError = v30;
  if ( v30 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7B,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v30,
      0x7FFF);
LABEL_31:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_46;
  }
  v41 = 0;
  v31 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs>::As<WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate>(
          &v39,
          &v41);
  LastError = v31;
  if ( v31 < 0 )
  {
    v32 = 126;
LABEL_34:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v32,
      (unsigned int)"ShellCommon\\internal\\Shell\\inc\\Private\\TileShellItemVerb.h",
      (const char *)(unsigned int)v31,
      v36);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    goto LABEL_31;
  }
  if ( v44[0] )
    v33 = *(_QWORD *)v44[0];
  else
    v33 = 0;
  v36 = v41;
  v31 = WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::EnumerateMenuRecursive(
          v44,
          *(_QWORD *)v38,
          v33,
          v40);
  LastError = v31;
  if ( v31 < 0 )
  {
    v32 = 129;
    goto LABEL_34;
  }
  v31 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v42 + 64LL))(v42, a4);
  LastError = v31;
  if ( v31 < 0 )
  {
    v32 = 130;
    goto LABEL_34;
  }
  wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v47, 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
  WindowsDeleteString(string);
  string = 0;
  std::shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>::~shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>(v44);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38);
  if ( v14 >= 0 )
    OleUninitialize();
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
  UnifiedTileTelemetry::TileShellItemVerbGetVerbs::~TileShellItemVerbGetVerbs((UnifiedTileTelemetry::TileShellItemVerbGetVerbs *)v47);
  return 0;
}

```

## disassembly

```asm
0x1802db560  push    rbp
0x1802db562  push    rbx
0x1802db563  push    rsi
0x1802db564  push    rdi
0x1802db565  push    r12
0x1802db567  push    r13
0x1802db569  push    r14
0x1802db56b  push    r15
0x1802db56d  lea     rbp, [rsp-108h]
0x1802db575  sub     rsp, 208h
0x1802db57c  mov     rax, cs:__security_cookie
0x1802db583  xor     rax, rsp
0x1802db586  mov     [rbp+140h+var_50], rax
0x1802db58d  mov     r12, r9
0x1802db590  mov     r13, r8
0x1802db593  mov     rdi, rdx
0x1802db596  mov     r15, rcx
0x1802db599  xor     esi, esi
0x1802db59b  mov     [r9], rsi
0x1802db59e  lea     rdx, aTileshellitemv; "TileShellItemVerbGetVerbs"
0x1802db5a5  lea     rcx, [rbp+140h+var_1A0]; struct wil::details::IFailureCallback *
0x1802db5a9  call    ??0?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1802db5ae  lea     rax, ??_7TileShellItemVerbGetVerbs@UnifiedTileTelemetry@@6B@; const UnifiedTileTelemetry::TileShellItemVerbGetVerbs::`vftable'
0x1802db5b5  mov     [rbp+140h+var_1A0], rax
0x1802db5b9  lea     rcx, [rbp+140h+var_1A0]; this
0x1802db5bd  call    ?StartActivity@TileShellItemVerbGetVerbs@UnifiedTileTelemetry@@QEAAXXZ; UnifiedTileTelemetry::TileShellItemVerbGetVerbs::StartActivity(void)
0x1802db5c2  test    rdi, rdi
0x1802db5c5  jz      loc_1802DBAAC
0x1802db5cb  mov     [rsp+240h+var_1D8], rsi
0x1802db5d0  lea     rcx, [rsp+240h+var_1D8]
0x1802db5d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db5da  lea     rdx, [rsp+240h+var_1D8]
0x1802db5df  call    ??$CreateExternalObjectVector@VTileVerb@UnifiedTile@Shell@WindowsInternal@@V?$AgileVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@U?$DefaultEqualityPredicate@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@6789@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<WindowsInternal::Shell::UnifiedTile::TileVerb,Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<WindowsInternal::Shell::UnifiedTile::TileVerb *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<WindowsInternal::Shell::UnifiedTile::TileVerb *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<WindowsInternal::Shell::UnifiedTile::TileVerb *>,0> * *)
0x1802db5e4  mov     ebx, eax
0x1802db5e6  test    eax, eax
0x1802db5e8  jns     short loc_1802DB608
0x1802db5ea  mov     rcx, [rbp+148h]; this
0x1802db5f1  mov     r9d, eax; char *
0x1802db5f4  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1802db5fb  lea     edx, [rsi+2Ch]; void *
0x1802db5fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db603  jmp     loc_1802DBA74
0x1802db608  mov     [rsp+240h+var_1F0], rsi
0x1802db60d  lea     rcx, [rsp+240h+var_1F0]
0x1802db612  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db617  lea     rdx, [rsp+240h+var_1F0]; struct WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *
0x1802db61c  mov     rcx, rdi; this
0x1802db61f  call    ?CopyVerbEnumerationArgs@Private@UnifiedTile@Shell@WindowsInternal@@YAJPEAUIVerbEnumerationArgs@234@PEAPEAU5234@@Z; WindowsInternal::Shell::UnifiedTile::Private::CopyVerbEnumerationArgs(WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs *,WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs * *)
0x1802db624  mov     ebx, eax
0x1802db626  xor     edi, edi
0x1802db628  test    eax, eax
0x1802db62a  jns     short loc_1802DB64A
0x1802db62c  mov     rcx, [rbp+148h]; this
0x1802db633  mov     r9d, eax; char *
0x1802db636  lea     r8, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1802db63d  lea     edx, [rdi+30h]; void *
0x1802db640  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db645  jmp     loc_1802DBA6A
0x1802db64a  xor     ecx, ecx; pvReserved
0x1802db64c  call    cs:__imp_OleInitialize
0x1802db652  mov     r14d, eax
0x1802db655  lea     rsi, aShellcommonInt_2; "ShellCommon\\internal\\Shell\\inc\\Priv"...
0x1802db65c  test    eax, eax
0x1802db65e  jns     short loc_1802DB677
0x1802db660  mov     rcx, [rbp+148h]; this
0x1802db667  mov     r9d, eax; char *
0x1802db66a  mov     r8, rsi; unsigned int
0x1802db66d  mov     edx, 35h ; '5'; void *
0x1802db672  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802db677  mov     qword ptr [rsp+240h+var_1F8], rdi
0x1802db67c  mov     rdx, [r15]
0x1802db67f  mov     rbx, [rdx+18h]
0x1802db683  lea     rcx, [rsp+240h+var_1F8]
0x1802db688  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db68d  lea     rax, [rsp+240h+var_1F8]
0x1802db692  mov     qword ptr [rsp+240h+var_220], rax; int
0x1802db697  lea     r9, _GUID_000214e4_0000_0000_c000_000000000046
0x1802db69e  lea     r8, BHID_SFUIObject
0x1802db6a5  xor     edx, edx
0x1802db6a7  mov     rcx, r15
0x1802db6aa  mov     rax, rbx
0x1802db6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db6b2  mov     ebx, eax
0x1802db6b4  test    eax, eax
0x1802db6b6  jns     short loc_1802DB6D4
0x1802db6b8  mov     rcx, [rbp+148h]; this
0x1802db6bf  mov     r9d, eax; char *
0x1802db6c2  mov     r8, rsi; unsigned int
0x1802db6c5  mov     edx, 40h ; '@'; void *
0x1802db6ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db6cf  jmp     loc_1802DBA55
0x1802db6d4  call    cs:__imp_CreatePopupMenu
0x1802db6da  mov     [rsp+240h+var_1D0], rax
0x1802db6df  lea     rdx, [rsp+240h+var_1D0]
0x1802db6e4  lea     rcx, [rsp+240h+var_1C8]
0x1802db6e9  call    ??$?0PEAUHMENU__@@@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@$$QEAPEAUHMENU__@@@Z; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>>(HMENU__ * &&)
0x1802db6ee  mov     rax, [rsp+240h+var_1C8]
0x1802db6f3  test    rax, rax
0x1802db6f6  jz      loc_1802DBA35
0x1802db6fc  cmp     [rax], rdi
0x1802db6ff  jz      loc_1802DBA35
0x1802db705  mov     [rsp+240h+var_1E8], edi
0x1802db709  mov     rcx, [rsp+240h+var_1F0]
0x1802db70e  mov     rax, [rcx]
0x1802db711  lea     rdx, [rsp+240h+var_1E8]
0x1802db716  mov     rax, [rax+30h]
0x1802db71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db71f  mov     ebx, eax
0x1802db721  test    eax, eax
0x1802db723  jns     short loc_1802DB741
0x1802db725  mov     rcx, [rbp+148h]; this
0x1802db72c  mov     r9d, eax; char *
0x1802db72f  mov     r8, rsi; unsigned int
0x1802db732  mov     edx, 4Bh ; 'K'; void *
0x1802db737  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db73c  jmp     loc_1802DBA4B
0x1802db741  mov     eax, [rsp+240h+var_1E8]
0x1802db745  and     al, 4
0x1802db747  neg     al
0x1802db749  sbb     r15d, r15d
0x1802db74c  and     r15d, 0FFFF9100h
0x1802db753  add     r15d, 8000h
0x1802db75a  mov     [rsp+240h+string], rdi
0x1802db75f  mov     rdi, [rsp+240h+var_1F0]
0x1802db764  mov     rax, [rdi]
0x1802db767  mov     rbx, [rax+60h]
0x1802db76b  xor     ecx, ecx; string
0x1802db76d  call    cs:__imp_WindowsDeleteString
0x1802db773  mov     [rsp+240h+string], 0
0x1802db77c  lea     rdx, [rsp+240h+string]
0x1802db781  mov     rcx, rdi
0x1802db784  mov     rax, rbx
0x1802db787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db78c  xor     edi, edi
0x1802db78e  test    eax, eax
0x1802db790  jns     short loc_1802DB7AC
0x1802db792  mov     rcx, [rbp+148h]; this
0x1802db799  mov     r9d, eax; char *
0x1802db79c  mov     r8, rsi; unsigned int
0x1802db79f  lea     edx, [rdi+63h]; void *
0x1802db7a2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802db7a7  jmp     loc_1802DB8B0
0x1802db7ac  cmp     [rsp+240h+string], rdi
0x1802db7b1  jz      loc_1802DB8B0
0x1802db7b7  mov     [rsp+240h+var_1D0], rdi
0x1802db7bc  mov     rdi, qword ptr [rsp+240h+var_1F8]
0x1802db7c1  mov     rax, [rdi]
0x1802db7c4  mov     rbx, [rax]
0x1802db7c7  lea     rcx, [rsp+240h+var_1D0]
0x1802db7cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db7d1  lea     r8, [rsp+240h+var_1D0]
0x1802db7d6  lea     rdx, _GUID_649e2263_dc09_466f_9d66_3eb133ee8f81
0x1802db7dd  mov     rcx, rdi
0x1802db7e0  mov     rax, rbx
0x1802db7e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db7e8  xor     edi, edi
0x1802db7ea  test    eax, eax
0x1802db7ec  jns     short loc_1802DB808
0x1802db7ee  mov     rcx, [rbp+148h]; this
0x1802db7f5  mov     r9d, eax; char *
0x1802db7f8  mov     r8, rsi; unsigned int
0x1802db7fb  lea     edx, [rdi+68h]; void *
0x1802db7fe  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802db803  jmp     loc_1802DB8A6
0x1802db808  xor     edx, edx; length
0x1802db80a  mov     rcx, [rsp+240h+string]; string
0x1802db80f  call    cs:__imp_WindowsGetStringRawBuffer
0x1802db815  mov     [rbp+140h+var_1B0], rax
0x1802db819  mov     rcx, [rsp+240h+var_1D0]
0x1802db81e  mov     rax, [rcx]
0x1802db821  mov     r8d, 1
0x1802db827  lea     rdx, [rbp+140h+var_1B0]
0x1802db82b  mov     rax, [rax+18h]
0x1802db82f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db834  mov     [rbp+140h+var_1B8], rdi
0x1802db838  mov     rdi, qword ptr [rsp+240h+var_1F8]
0x1802db83d  mov     rax, [rdi]
0x1802db840  mov     rbx, [rax]
0x1802db843  lea     rcx, [rbp+140h+var_1B8]
0x1802db847  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db84c  lea     r8, [rbp+140h+var_1B8]
0x1802db850  lea     rdx, _GUID_7690aa79_f8fc_4615_a327_36f7d18f5d91
0x1802db857  mov     rcx, rdi
0x1802db85a  mov     rax, rbx
0x1802db85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db862  xor     edi, edi
0x1802db864  test    eax, eax
0x1802db866  jns     short loc_1802DB86D
0x1802db868  lea     edx, [rdi+6Eh]
0x1802db86b  jmp     short loc_1802DB88B
0x1802db86d  mov     rcx, [rbp+140h+var_1B8]
0x1802db871  mov     rax, [rcx]
0x1802db874  mov     edx, 200h
0x1802db879  mov     rax, [rax+20h]
0x1802db87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db882  test    eax, eax
0x1802db884  jns     short loc_1802DB89D
0x1802db886  mov     edx, 71h ; 'q'; void *
0x1802db88b  mov     r9d, eax; char *
0x1802db88e  mov     r8, rsi; unsigned int
0x1802db891  mov     rcx, [rbp+148h]; this
0x1802db898  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802db89d  lea     rcx, [rbp+140h+var_1B8]
0x1802db8a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db8a6  lea     rcx, [rsp+240h+var_1D0]
0x1802db8ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db8b0  mov     rcx, qword ptr [rsp+240h+var_1F8]
0x1802db8b5  mov     rax, [rcx]
0x1802db8b8  mov     r10, [rax+18h]
0x1802db8bc  mov     rax, [rsp+240h+var_1C8]
0x1802db8c1  test    rax, rax
0x1802db8c4  jz      short loc_1802DB8CB
0x1802db8c6  mov     rdx, [rax]
0x1802db8c9  jmp     short loc_1802DB8CE
0x1802db8cb  mov     rdx, rdi
0x1802db8ce  mov     dword ptr [rsp+240h+var_218], r15d
0x1802db8d3  mov     [rsp+240h+var_220], 7FFFh; int
0x1802db8db  mov     r9d, 1
0x1802db8e1  xor     r8d, r8d
0x1802db8e4  mov     rax, r10
0x1802db8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db8ec  mov     ebx, eax
0x1802db8ee  test    eax, eax
0x1802db8f0  jns     short loc_1802DB91E
0x1802db8f2  mov     rcx, [rbp+148h]; this
0x1802db8f9  mov     r9d, eax; char *
0x1802db8fc  mov     r8, rsi; unsigned int
0x1802db8ff  mov     edx, 7Bh ; '{'; void *
0x1802db904  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db909  mov     rcx, [rsp+240h+string]; string
0x1802db90e  call    cs:__imp_WindowsDeleteString
0x1802db914  mov     [rsp+240h+string], rdi
0x1802db919  jmp     loc_1802DBA4B
0x1802db91e  mov     [rsp+240h+var_1E0], rdi
0x1802db923  lea     rdx, [rsp+240h+var_1E0]
0x1802db928  lea     rcx, [rsp+240h+var_1F0]
0x1802db92d  call    ??$As@UIVerbEnumerationArgsPrivate@Private@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIVerbEnumerationArgs@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIVerbEnumerationArgsPrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IVerbEnumerationArgs>::As<WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate>>)
0x1802db932  mov     ebx, eax
0x1802db934  test    eax, eax
0x1802db936  jns     short loc_1802DB95B
0x1802db938  mov     edx, 7Eh ; '~'; void *
0x1802db93d  mov     rcx, [rbp+148h]; this
0x1802db944  mov     r9d, eax; char *
0x1802db947  mov     r8, rsi; unsigned int
0x1802db94a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802db94f  lea     rcx, [rsp+240h+var_1E0]
0x1802db954  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db959  jmp     short loc_1802DB909
0x1802db95b  mov     rcx, [rsp+240h+var_1D8]
0x1802db960  mov     rdx, [rsp+240h+var_1E0]
0x1802db965  mov     rax, [rsp+240h+var_1C8]
0x1802db96a  test    rax, rax
0x1802db96d  jz      short loc_1802DB974
0x1802db96f  mov     r8, [rax]
0x1802db972  jmp     short loc_1802DB977
0x1802db974  mov     r8, rdi
0x1802db977  mov     [rsp+240h+var_208], rcx
0x1802db97c  mov     [rsp+240h+var_210], rdi
0x1802db981  mov     [rsp+240h+var_218], r13
0x1802db986  mov     qword ptr [rsp+240h+var_220], rdx
0x1802db98b  mov     r9d, [rsp+240h+var_1E8]
0x1802db990  mov     rdx, qword ptr [rsp+240h+var_1F8]
0x1802db995  lea     rcx, [rsp+240h+var_1C8]
0x1802db99a  call    ?EnumerateMenuRecursive@TileShellItemVerb@Private@UnifiedTile@Shell@WindowsInternal@@CAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHMENU__@@P6AHPEAU1@@Z$1?DestroyMenu@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@PEAUIContextMenu@@PEAUHMENU__@@W4VerbEnumerationOptions@345@PEAUIVerbEnumerationArgsPrivate@2345@PEAUHSTRING__@@5PEAU?$IVector@PEAVTileVerb@UnifiedTile@Shell@WindowsInternal@@@Collections@Foundation@Windows@@@Z; WindowsInternal::Shell::UnifiedTile::Private::TileShellItemVerb::EnumerateMenuRecursive(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HMENU__ *,int (*)(HMENU__ *),&DestroyMenu(HMENU__ *),wistd::integral_constant<unsigned __int64,0>,HMENU__ *,HMENU__ *,0,std::nullptr_t>>>>> const &,IContextMenu *,HMENU__ *,WindowsInternal::Shell::UnifiedTile::VerbEnumerationOptions,WindowsInternal::Shell::UnifiedTile::Private::IVerbEnumerationArgsPrivate *,HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::IVector<WindowsInternal::Shell::UnifiedTile::TileVerb *> *)
0x1802db99f  mov     ebx, eax
0x1802db9a1  test    eax, eax
0x1802db9a3  jns     short loc_1802DB9AC
0x1802db9a5  mov     edx, 81h
0x1802db9aa  jmp     short loc_1802DB93D
0x1802db9ac  mov     rcx, [rsp+240h+var_1D8]
0x1802db9b1  mov     rax, [rcx]
0x1802db9b4  mov     rdx, r12
0x1802db9b7  mov     rax, [rax+40h]
0x1802db9bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802db9c0  mov     ebx, eax
0x1802db9c2  test    eax, eax
0x1802db9c4  jns     short loc_1802DB9D0
0x1802db9c6  mov     edx, 82h
0x1802db9cb  jmp     loc_1802DB93D
0x1802db9d0  xor     edx, edx
0x1802db9d2  lea     rcx, [rbp+140h+var_1A0]
0x1802db9d6  call    ?Stop@?$ActivityBase@VUnifiedTileLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<UnifiedTileLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1802db9db  lea     rcx, [rsp+240h+var_1E0]
0x1802db9e0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802db9e5  mov     rcx, [rsp+240h+string]; string
0x1802db9ea  call    cs:__imp_WindowsDeleteString
0x1802db9f0  mov     [rsp+240h+string], rdi
0x1802db9f5  lea     rcx, [rsp+240h+var_1C8]; void *
0x1802db9fa  call    ??1?$shared_ptr@V?$CDSDataTransformer@UTileCollectionContainer@CuratedTileCollection@Data@Windows@@UIInspectable@@@CDSDataTransformer@DataStoreCache@@@std@@QEAA@XZ; std::shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>::~shared_ptr<DataStoreCache::CDSDataTransformer::CDSDataTransformer<Windows::Data::CuratedTileCollection::TileCollectionContainer,IInspectable>>(void)
0x1802db9ff  lea     rcx, [rsp+240h+var_1F8]
0x1802dba04  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802dba09  test    r14d, r14d
0x1802dba0c  js      short loc_1802DBA14
0x1802dba0e  call    cs:__imp_OleUninitialize
0x1802dba14  lea     rcx, [rsp+240h+var_1F0]
0x1802dba19  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802dba1e  lea     rcx, [rsp+240h+var_1D8]
0x1802dba23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1802dba28  lea     rcx, [rbp+140h+var_1A0]; this
0x1802dba2c  call    ??1TileShellItemVerbGetVerbs@UnifiedTileTelemetry@@QEAA@XZ; UnifiedTileTelemetry::TileShellItemVerbGetVerbs::~TileShellItemVerbGetVerbs(void)
  ... truncated ...
```
