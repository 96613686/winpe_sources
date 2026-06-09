# DataStoreCache::AppLifecycleTransformer::UpdateAppLifecycleDataForDataItem(Microsoft::WRL::ComPtr<DataStoreCache::IDataItem> const &,bool,_GUID const *,std::unordered_map<DataStoreCache::DataItemIdentifier,WindowsInternal::Shell::UnifiedTile::AppState,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,WindowsInternal::Shell::UnifiedTile::AppState>>> *)

- ea: `0x1800149c8`
- end: `0x180014f3e`
- name: `?UpdateAppLifecycleDataForDataItem@AppLifecycleTransformer@DataStoreCache@@AEAAXAEBV?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@_NPEBU_GUID@@PEAV?$unordered_map@VDataItemIdentifier@DataStoreCache@@W4AppState@UnifiedTile@Shell@WindowsInternal@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@8@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@W4AppState@UnifiedTile@Shell@WindowsInternal@@@std@@@8@@std@@@Z`
- size: `1398`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015368`
- `0x18031aa04`

## callees

- `0x18000a8b0`
- `0x18000ce94`
- `0x18000ef70`
- `0x1800149c8`
- `0x180014f44`
- `0x180015118`
- `0x180015524`
- `0x1800159a0`
- `0x18001ac50`
- `0x18001dac0`
- `0x18006fe30`
- `0x180117500`
- `0x180117598`
- `0x18011f9ac`
- `0x1801e5070`
- `0x180201e50`
- `0x18031baf0`
- `0x18031bcf8`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014aee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014c07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014a9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014aee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014b67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014c07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e9e`

## string_xrefs

- `0x180014c6f`: `shellcommon\shell\datastorecache\transformers\applifecycletransformer\lib\applifecycletransformer.cpp`
- `0x180014edc`: `shellcommon\shell\datastorecache\transformers\applifecycletransformer\lib\applifecycletransformer.cpp`
- `0x180014ef1`: `shellcommon\shell\datastorecache\transformers\applifecycletransformer\lib\applifecycletransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall DataStoreCache::AppLifecycleTransformer::UpdateAppLifecycleDataForDataItem(
        DataStoreCache::AppLifecycleTransformer *this,
        HSTRING a2,
        char a3,
        _QWORD *a4,
        __int64 a5)
{
  __int64 v8; // rcx
  const struct DataStoreCache::DataItemIdentifier *v9; // rax
  std::_Ref_count_base *v10; // rdi
  unsigned int AppStateForTileStoreItem; // ebx
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, void **, HSTRING *); // rbx
  char v16; // al
  HSTRING v17; // rbx
  __int64 v19; // rax
  __int64 v20; // rax
  std::_Ref_count_base *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, HSTRING *); // rbx
  _QWORD *v27; // rax
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  std::_Ref_count_base *v31; // r12
  std::_Ref_count_base *v32; // rcx
  HSTRING v33; // rbx
  HSTRING v34; // rcx
  UINT32 v35; // r8d
  __int64 v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  std::_Ref_count_base *v39; // rcx
  unsigned int InstallDelay; // ebx
  unsigned int InstallState; // eax
  __int64 v42; // r8
  HSTRING *v43; // rax
  int v44; // [rsp+20h] [rbp-D8h]
  HSTRING v46; // [rsp+38h] [rbp-C0h] BYREF
  HSTRING v47; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v48; // [rsp+48h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-A8h] BYREF
  std::_Ref_count_base *v50; // [rsp+58h] [rbp-A0h]
  std::_Ref_count_base *v51[2]; // [rsp+60h] [rbp-98h]
  std::_Ref_count_base *v52; // [rsp+70h] [rbp-88h] BYREF
  std::_Ref_count_base *v53[2]; // [rsp+78h] [rbp-80h] BYREF
  HSTRING v54; // [rsp+88h] [rbp-70h] BYREF
  std::_Ref_count_base *v55; // [rsp+90h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  string = a2;
  *(_OWORD *)v51 = 0;
  v48 = 0;
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const struct _GUID *, GUID *, __int64 *))(**(_QWORD **)a2 + 48LL))(
         *(_QWORD *)a2,
         &c_tileStoreTransformerId,
         &GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb,
         &v48)
    && v48 )
  {
    if ( a4 )
    {
      v24 = *a4 - *(_QWORD *)&c_tileStoreTransformerId.Data1;
      if ( *a4 == *(_QWORD *)&c_tileStoreTransformerId.Data1 )
        v24 = a4[1] - *(_QWORD *)c_tileStoreTransformerId.Data4;
      if ( v24 )
        goto LABEL_11;
    }
    v46 = 0;
    v14 = v48;
    v15 = *(__int64 (__fastcall **)(__int64, void **, HSTRING *))(*(_QWORD *)v48 + 32LL);
    WindowsDeleteString(0);
    v46 = 0;
    v16 = v15(v14, &DataStoreCache::TileStoreProperties::PackageFamilyName, &v46);
    v17 = v46;
    if ( !v16 || !v46 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\applifecycletransformer\\lib\\applifecycletransformer.cpp",
        (const char *)0x8007139FLL,
        v44);
    v19 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)a2 + 32LL))(*(_QWORD *)a2, &v47);
    v20 = DataStoreCache::AppLifecycleTransformer::AddTileToIndex(this, v53, v19, v17);
    v10 = *(std::_Ref_count_base **)v20;
    v21 = *(std::_Ref_count_base **)(v20 + 8);
    *(_QWORD *)v20 = 0;
    *(_QWORD *)(v20 + 8) = 0;
    v51[0] = v10;
    v51[1] = v21;
    if ( v53[1] )
      std::_Ref_count_base::_Decref(v53[1]);
    WindowsDeleteString(v47);
    if ( a5 )
    {
      std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalVolatileTilePropertiesPriv>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalVolatileTilePropertiesPriv>>>,0>>::find(
        a5,
        &v47,
        v10);
      if ( v47 == *(HSTRING *)(a5 + 8) )
      {
        LOBYTE(v23) = a3;
        AppStateForTileStoreItem = DataStoreCache::AppLifecycleTransformer::GetAppStateForTileStoreItem(this, a2, v23);
        *(_DWORD *)(*(_QWORD *)std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,enum WindowsInternal::Shell::UnifiedTile::AppState,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,enum WindowsInternal::Shell::UnifiedTile::AppState>>,0>>::_Try_emplace<DataStoreCache::DataItemIdentifier const &,>(
                                 a5,
                                 v53,
                                 v10)
                  + 24LL) = AppStateForTileStoreItem;
      }
      else
      {
        AppStateForTileStoreItem = *((_DWORD *)v47 + 6);
      }
      v12 = AppStateForTileStoreItem;
    }
    else
    {
      LOBYTE(v22) = a3;
      v12 = (unsigned int)DataStoreCache::AppLifecycleTransformer::GetAppStateForTileStoreItem(this, a2, v22);
    }
    DataStoreCache::AppLifecycleTransformer::ApplyAppLifecycleData(this, a2, v12, 0);
    WindowsDeleteString(v46);
    goto LABEL_9;
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD, const struct _GUID *))(**(_QWORD **)a2 + 56LL))(
         *(_QWORD *)a2,
         &c_placeholderTileTransformerId)
    && *((_QWORD *)this + 42) )
  {
    v46 = 0;
    v25 = *((_QWORD *)this + 44);
    v26 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
    v27 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)a2 + 32LL))(*(_QWORD *)a2, &v54);
    v28 = v26(v25, *v27, &v46);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x188,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\applifecycletransformer\\lib\\applifecycletransformer.cpp",
        (const char *)(unsigned int)v28,
        v44);
    WindowsDeleteString(v54);
    LODWORD(v47) = 0;
    v29 = (*(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v46 + 48LL))(v46, &v47);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x18B,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\applifecycletransformer\\lib\\applifecycletransformer.cpp",
        (const char *)(unsigned int)v29,
        v44);
    if ( (_DWORD)v47 == 1 )
    {
      *(_OWORD *)v53 = 0;
      try
      {
        v30 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 136LL))(*((_QWORD *)this + 42));
        v31 = *(std::_Ref_count_base **)v30;
        v52 = *(std::_Ref_count_base **)(v30 + 8);
        v32 = v52;
        *(_QWORD *)v30 = 0;
        *(_QWORD *)(v30 + 8) = 0;
        v53[0] = v31;
        v53[1] = v32;
        if ( v55 )
          std::_Ref_count_base::_Decref(v55);
      }
      catch ( DataStoreCache::CloudUtil::ItemDoesNotExistException )
      {
        v43 = (HSTRING *)(*(__int64 (__fastcall **)(_QWORD, std::_Ref_count_base **))(**(_QWORD **)string + 32LL))(
                           *(_QWORD *)string,
                           &v52);
        string = (HSTRING)WindowsGetStringRawBuffer(*v43, 0);
        DataStoreTransformerTelemetry::AppLifecycleTransformerPlaceholderTileNotFound<unsigned short const *>(&string);
        WindowsDeleteString((HSTRING)v52);
        if ( v53[1] )
          std::_Ref_count_base::_Decref(v53[1]);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        return;
      }
      DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetPackageFamilyName();
      v33 = string;
      if ( v50 )
        std::_Ref_count_base::_Decref(v50);
      if ( !*((_QWORD *)v33 + 2)
        || (unsigned int)DataStoreCache::PlaceholderTileTransformer::PlaceholderTileLocalImpl::GetInstallReason(*((_QWORD *)v31 + 2)) == 2 )
      {
        v10 = v51[0];
      }
      else
      {
        v35 = *((_DWORD *)v33 + 4);
        if ( *((_QWORD *)v33 + 3) > 7u )
          v33 = *(HSTRING *)v33;
        v36 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (PCWSTR)v33, v35)
                        + 24);
        v37 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)a2 + 32LL))(*(_QWORD *)a2, &v54);
        v38 = DataStoreCache::AppLifecycleTransformer::AddTileToIndex(this, &string, v37, v36);
        v10 = *(std::_Ref_count_base **)v38;
        v39 = *(std::_Ref_count_base **)(v38 + 8);
        *(_QWORD *)v38 = 0;
        *(_QWORD *)(v38 + 8) = 0;
        v51[0] = v10;
        v51[1] = v39;
        if ( v50 )
          std::_Ref_count_base::_Decref(v50);
        WindowsDeleteString(v54);
        InstallDelay = DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetInstallDelay(*(_QWORD *)v31);
        InstallState = DataStoreCache::PlaceholderTileTransformer::PlaceholderTileLocalImpl::GetInstallState(*((_QWORD *)v31 + 2));
        v42 = (unsigned int)DataStoreCache::TranslatePlaceholderInstallStateToAppState(InstallState, InstallDelay);
        DataStoreCache::AppLifecycleTransformer::ApplyAppLifecycleData(this, a2, v42, 0);
      }
      if ( v52 )
        std::_Ref_count_base::_Decref(v52);
    }
    else
    {
      v10 = v51[0];
    }
    v34 = v46;
    if ( v46 )
    {
      v46 = 0;
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v34 + 16LL))(v34);
    }
    goto LABEL_9;
  }
  if ( a4 )
  {
    DataStoreCache::AppLifecycleTransformer::RemoveAppLifecycleData(v8, a2);
    v9 = (const struct DataStoreCache::DataItemIdentifier *)(*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)a2 + 32LL))(
                                                              *(_QWORD *)a2,
                                                              &string);
    DataStoreCache::AppLifecycleTransformer::RemoveTileFromIndex(this, v9);
    WindowsDeleteString(string);
    v10 = v51[0];
LABEL_9:
    if ( v10 )
      *((_BYTE *)v10 + 28) = 1;
  }
LABEL_11:
  v13 = v48;
  if ( v48 )
  {
    v48 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v51[1] )
    std::_Ref_count_base::_Decref(v51[1]);
}

```

## disassembly

```asm
0x1800149c8  push    rbx
0x1800149ca  push    rsi
0x1800149cb  push    rdi
0x1800149cc  push    r12
0x1800149ce  push    r13
0x1800149d0  push    r14
0x1800149d2  push    r15
0x1800149d4  sub     rsp, 0C0h
0x1800149db  mov     rax, cs:__security_cookie
0x1800149e2  xor     rax, rsp
0x1800149e5  mov     [rsp+0F8h+var_40], rax
0x1800149ed  mov     rbx, r9
0x1800149f0  mov     [rsp+0F8h+var_C8], r8b
0x1800149f5  mov     r14, rdx
0x1800149f8  mov     r13, rcx
0x1800149fb  mov     [rsp+0F8h+string], rdx
0x180014a00  mov     r12, [rsp+0F8h+arg_20]
0x180014a08  xor     esi, esi
0x180014a0a  xorps   xmm0, xmm0
0x180014a0d  movdqu  xmmword ptr [rsp+0F8h+var_98], xmm0
0x180014a13  mov     [rsp+0F8h+var_B0], rsi
0x180014a18  mov     rcx, [rdx]
0x180014a1b  mov     rax, [rcx]
0x180014a1e  lea     r9, [rsp+0F8h+var_B0]
0x180014a23  lea     r8, _GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb
0x180014a2a  lea     rdx, c_tileStoreTransformerId
0x180014a31  mov     rax, [rax+30h]
0x180014a35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a3a  test    al, al
0x180014a3c  jz      short loc_180014A49
0x180014a3e  cmp     [rsp+0F8h+var_B0], rsi
0x180014a43  jnz     loc_180014B4B
0x180014a49  mov     rcx, [r14]
0x180014a4c  mov     rax, [rcx]
0x180014a4f  lea     rdx, c_placeholderTileTransformerId
0x180014a56  mov     rax, [rax+38h]
0x180014a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a5f  test    al, al
0x180014a61  jnz     loc_180014CA6
0x180014a67  test    rbx, rbx
0x180014a6a  jz      loc_180014AFD
0x180014a70  mov     rdx, r14
0x180014a73  call    ?RemoveAppLifecycleData@AppLifecycleTransformer@DataStoreCache@@AEBAXAEBV?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@@Z; DataStoreCache::AppLifecycleTransformer::RemoveAppLifecycleData(Microsoft::WRL::ComPtr<DataStoreCache::IDataItem> const &)
0x180014a78  mov     rcx, [r14]
0x180014a7b  mov     rax, [rcx]
0x180014a7e  lea     rdx, [rsp+0F8h+string]
0x180014a83  mov     rax, [rax+20h]
0x180014a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a8c  mov     rdx, rax; struct DataStoreCache::DataItemIdentifier *
0x180014a8f  mov     rcx, r13; this
0x180014a92  call    ?RemoveTileFromIndex@AppLifecycleTransformer@DataStoreCache@@AEAAXAEBVDataItemIdentifier@2@@Z; DataStoreCache::AppLifecycleTransformer::RemoveTileFromIndex(DataStoreCache::DataItemIdentifier const &)
0x180014a97  mov     rcx, [rsp+0F8h+string]; string
0x180014a9c  call    cs:__imp_WindowsDeleteString
0x180014aa2  mov     r15d, 1
0x180014aa8  mov     rdi, [rsp+0F8h+var_98]
0x180014aad  jmp     short loc_180014AF4
0x180014aaf  mov     r8b, [rsp+0F8h+var_C8]
0x180014ab4  mov     rdx, r14
0x180014ab7  mov     rcx, r13
0x180014aba  call    ?GetAppStateForTileStoreItem@AppLifecycleTransformer@DataStoreCache@@AEBA?AW4AppState@UnifiedTile@Shell@WindowsInternal@@AEBV?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@_N@Z; DataStoreCache::AppLifecycleTransformer::GetAppStateForTileStoreItem(Microsoft::WRL::ComPtr<DataStoreCache::IDataItem> const &,bool)
0x180014abf  mov     ebx, eax
0x180014ac1  mov     r8, rdi
0x180014ac4  lea     rdx, [rsp+0F8h+var_80]
0x180014ac9  mov     rcx, r12
0x180014acc  call    ??$_Try_emplace@AEBVDataItemIdentifier@DataStoreCache@@$$V@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@W4AppState@UnifiedTile@Shell@WindowsInternal@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@W4AppState@UnifiedTile@Shell@WindowsInternal@@@std@@@8@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@W4AppState@UnifiedTile@Shell@WindowsInternal@@@std@@PEAX@std@@_N@1@AEBVDataItemIdentifier@DataStoreCache@@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,WindowsInternal::Shell::UnifiedTile::AppState,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,WindowsInternal::Shell::UnifiedTile::AppState>>,0>>::_Try_emplace<DataStoreCache::DataItemIdentifier const &,>(DataStoreCache::DataItemIdentifier const &)
0x180014ad1  mov     rcx, [rax]
0x180014ad4  mov     [rcx+18h], ebx
0x180014ad7  mov     r8d, ebx
0x180014ada  xor     r9d, r9d
0x180014add  mov     rdx, r14
0x180014ae0  mov     rcx, r13
0x180014ae3  call    ?ApplyAppLifecycleData@AppLifecycleTransformer@DataStoreCache@@AEBAXAEBV?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@W4AppState@UnifiedTile@Shell@WindowsInternal@@I@Z; DataStoreCache::AppLifecycleTransformer::ApplyAppLifecycleData(Microsoft::WRL::ComPtr<DataStoreCache::IDataItem> const &,WindowsInternal::Shell::UnifiedTile::AppState,uint)
0x180014ae8  nop
0x180014ae9  mov     rcx, [rsp+0F8h+var_C0]; string
0x180014aee  call    cs:__imp_WindowsDeleteString
0x180014af4  test    rdi, rdi
0x180014af7  jz      short loc_180014AFD
0x180014af9  xchg    r15b, [rdi+1Ch]
0x180014afd  mov     rcx, [rsp+0F8h+var_B0]
0x180014b02  test    rcx, rcx
0x180014b05  jz      short loc_180014B19
0x180014b07  mov     [rsp+0F8h+var_B0], rsi
0x180014b0c  mov     rax, [rcx]
0x180014b0f  mov     rax, [rax+10h]
0x180014b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b18  nop
0x180014b19  mov     rcx, [rsp+0F8h+var_98+8]; this
0x180014b1e  test    rcx, rcx
0x180014b21  jz      short loc_180014B28
0x180014b23  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014b28  mov     rcx, [rsp+0F8h+var_40]
0x180014b30  xor     rcx, rsp; StackCookie
0x180014b33  call    __security_check_cookie
0x180014b38  add     rsp, 0C0h
0x180014b3f  pop     r15
0x180014b41  pop     r14
0x180014b43  pop     r13
0x180014b45  pop     r12
0x180014b47  pop     rdi
0x180014b48  pop     rsi
0x180014b49  pop     rbx
0x180014b4a  retn
0x180014b4b  test    rbx, rbx
0x180014b4e  jnz     loc_180014C81
0x180014b54  mov     [rsp+0F8h+var_C0], rsi
0x180014b59  mov     rdi, [rsp+0F8h+var_B0]
0x180014b5e  mov     rax, [rdi]
0x180014b61  mov     rbx, [rax+20h]
0x180014b65  xor     ecx, ecx; string
0x180014b67  call    cs:__imp_WindowsDeleteString
0x180014b6d  mov     [rsp+0F8h+var_C0], rsi
0x180014b72  lea     r8, [rsp+0F8h+var_C0]
0x180014b77  lea     rdx, ?PackageFamilyName@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TileStoreProperties::PackageFamilyName
0x180014b7e  mov     rcx, rdi
0x180014b81  mov     rax, rbx
0x180014b84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b89  mov     rbx, [rsp+0F8h+var_C0]
0x180014b8e  test    al, al
0x180014b90  jnz     loc_180014C3A
0x180014b96  mov     r15d, 1
0x180014b9c  mov     al, r15b
0x180014b9f  mov     rcx, [rsp+0F8h]; this
0x180014ba7  test    al, al
0x180014ba9  jnz     loc_180014C69
0x180014baf  mov     rcx, [r14]
0x180014bb2  mov     rax, [rcx]
0x180014bb5  lea     rdx, [rsp+0F8h+var_B8]
0x180014bba  mov     rax, [rax+20h]
0x180014bbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bc3  nop
0x180014bc4  mov     r9, rbx
0x180014bc7  mov     r8, rax
0x180014bca  lea     rdx, [rsp+0F8h+var_80]
0x180014bcf  mov     rcx, r13
0x180014bd2  call    ?AddTileToIndex@AppLifecycleTransformer@DataStoreCache@@AEAA?AV?$shared_ptr@UCachedTileLifecycleData@AppLifecycleTransformer@DataStoreCache@@@std@@AEBVDataItemIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::AppLifecycleTransformer::AddTileToIndex(DataStoreCache::DataItemIdentifier const &,HSTRING__ *)
0x180014bd7  mov     rdi, [rax]
0x180014bda  mov     rcx, [rax+8]
0x180014bde  mov     [rax], rsi
0x180014be1  mov     [rax+8], rsi
0x180014be5  mov     [rsp+0F8h+var_98], rdi
0x180014bea  mov     [rsp+0F8h+var_98+8], rcx
0x180014bef  mov     rcx, [rsp+0F8h+var_80+8]; this
0x180014bf7  test    rcx, rcx
0x180014bfa  jz      short loc_180014C02
0x180014bfc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014c01  nop
0x180014c02  mov     rcx, [rsp+0F8h+var_B8]; string
0x180014c07  call    cs:__imp_WindowsDeleteString
0x180014c0d  test    r12, r12
0x180014c10  jz      short loc_180014C51
0x180014c12  mov     r8, rdi
0x180014c15  lea     rdx, [rsp+0F8h+var_B8]
0x180014c1a  mov     rcx, r12
0x180014c1d  call    ?find@?$_Hash@V?$_Umap_traits@VDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICDSLocalVolatileTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@V?$_Uhash_compare@VDataItemIdentifier@DataStoreCache@@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@@std@@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICDSLocalVolatileTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V?$ComPtr@UICDSLocalVolatileTilePropertiesPriv@CDSProperties@Shell@WindowsInternal@@@WRL@Microsoft@@@std@@@std@@@std@@@2@AEBVDataItemIdentifier@DataStoreCache@@@Z; std::_Hash<std::_Umap_traits<DataStoreCache::DataItemIdentifier,Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalVolatileTilePropertiesPriv>,std::_Uhash_compare<DataStoreCache::DataItemIdentifier,std::hash<DataStoreCache::DataItemIdentifier>,std::equal_to<DataStoreCache::DataItemIdentifier>>,std::allocator<std::pair<DataStoreCache::DataItemIdentifier const,Microsoft::WRL::ComPtr<WindowsInternal::Shell::CDSProperties::ICDSLocalVolatileTilePropertiesPriv>>>,0>>::find(DataStoreCache::DataItemIdentifier const &)
0x180014c22  mov     rax, [rsp+0F8h+var_B8]
0x180014c27  cmp     rax, [r12+8]
0x180014c2c  jz      loc_180014AAF
0x180014c32  mov     ebx, [rax+18h]
0x180014c35  jmp     loc_180014AD7
0x180014c3a  test    rbx, rbx
0x180014c3d  jz      loc_180014B96
0x180014c43  mov     al, sil
0x180014c46  mov     r15d, 1
0x180014c4c  jmp     loc_180014B9F
0x180014c51  mov     r8b, [rsp+0F8h+var_C8]
0x180014c56  mov     rdx, r14
0x180014c59  mov     rcx, r13
0x180014c5c  call    ?GetAppStateForTileStoreItem@AppLifecycleTransformer@DataStoreCache@@AEBA?AW4AppState@UnifiedTile@Shell@WindowsInternal@@AEBV?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@_N@Z; DataStoreCache::AppLifecycleTransformer::GetAppStateForTileStoreItem(Microsoft::WRL::ComPtr<DataStoreCache::IDataItem> const &,bool)
0x180014c61  mov     r8d, eax
0x180014c64  jmp     loc_180014ADA
0x180014c69  mov     r9d, 8007139Fh; char *
0x180014c6f  lea     r8, aShellcommonShe_59; "shellcommon\\shell\\datastorecache\\tra"...
0x180014c76  mov     edx, 15Bh; void *
0x180014c7b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180014c81  mov     rax, [rbx]
0x180014c84  sub     rax, qword ptr cs:c_tileStoreTransformerId.Data1
0x180014c8b  jnz     short loc_180014C98
0x180014c8d  mov     rax, [rbx+8]
0x180014c91  sub     rax, qword ptr cs:c_tileStoreTransformerId.Data4
0x180014c98  test    rax, rax
0x180014c9b  jnz     loc_180014AFD
0x180014ca1  jmp     loc_180014B54
0x180014ca6  cmp     [r13+150h], rsi
0x180014cad  jz      loc_180014A67
0x180014cb3  mov     [rsp+0F8h+var_C0], rsi
0x180014cb8  mov     rdi, [r13+160h]
0x180014cbf  mov     rax, [rdi]
0x180014cc2  mov     rbx, [rax+30h]
0x180014cc6  lea     rcx, [rsp+0F8h+var_C0]
0x180014ccb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180014cd0  mov     rcx, [r14]
0x180014cd3  mov     rdx, [rcx]
0x180014cd6  mov     rax, [rdx+20h]
0x180014cda  lea     rdx, [rsp+0F8h+var_70]
0x180014ce2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ce7  nop
0x180014ce8  lea     r8, [rsp+0F8h+var_C0]
0x180014ced  mov     rdx, [rax]
0x180014cf0  mov     rcx, rdi
0x180014cf3  mov     rax, rbx
0x180014cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cfb  mov     rcx, [rsp+0F8h]; this
0x180014d03  test    eax, eax
0x180014d05  js      loc_180014ED9
0x180014d0b  mov     rcx, [rsp+0F8h+var_70]; string
0x180014d13  call    cs:__imp_WindowsDeleteString
0x180014d19  mov     dword ptr [rsp+0F8h+var_B8], esi
0x180014d1d  mov     rcx, [rsp+0F8h+var_C0]
0x180014d22  mov     rax, [rcx]
0x180014d25  lea     rdx, [rsp+0F8h+var_B8]
0x180014d2a  mov     rax, [rax+30h]
0x180014d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d33  mov     rcx, [rsp+0F8h]; this
0x180014d3b  test    eax, eax
0x180014d3d  js      loc_180014EEE
0x180014d43  mov     r15d, 1
0x180014d49  cmp     dword ptr [rsp+0F8h+var_B8], r15d
0x180014d4e  jnz     loc_180014F33
0x180014d54  xorps   xmm0, xmm0
0x180014d57  movdqu  xmmword ptr [rsp+0F8h+var_80], xmm0
0x180014d5d  mov     rcx, [r13+150h]
0x180014d64  mov     rax, [rcx]
0x180014d67  mov     r8, [rsp+0F8h+var_C0]
0x180014d6c  lea     rdx, [rsp+0F8h+var_70]
0x180014d74  mov     rax, [rax+88h]
0x180014d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d80  mov     r12, [rax]
0x180014d83  mov     rcx, [rax+8]
0x180014d87  mov     [rsp+0F8h+var_88], rcx
0x180014d8c  mov     [rax], rsi
0x180014d8f  mov     [rax+8], rsi
0x180014d93  mov     [rsp+0F8h+var_80], r12
0x180014d98  mov     [rsp+0F8h+var_80+8], rcx
0x180014da0  mov     rcx, [rsp+0F8h+var_68]; this
0x180014da8  test    rcx, rcx
0x180014dab  jz      short loc_180014DB3
0x180014dad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014db2  nop
0x180014db3  lea     rdx, [rsp+0F8h+string]
0x180014db8  mov     rcx, [r12]
0x180014dbc  call    ?GetPackageFamilyName@PlaceholderTileImpl@PlaceholderTileTransformer@DataStoreCache@@QEAA?AV?$shared_ptr@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileImpl::GetPackageFamilyName(void)
0x180014dc1  mov     rbx, [rsp+0F8h+string]
0x180014dc6  mov     rcx, [rsp+0F8h+var_A0]; this
0x180014dcb  test    rcx, rcx
0x180014dce  jz      short loc_180014DD5
0x180014dd0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014dd5  cmp     [rbx+10h], rsi
0x180014dd9  jnz     short loc_180014E11
0x180014ddb  mov     rdi, [rsp+0F8h+var_98]
0x180014de0  mov     rcx, [rsp+0F8h+var_88]; this
0x180014de5  test    rcx, rcx
0x180014de8  jz      short loc_180014DF0
0x180014dea  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014def  nop
0x180014df0  mov     rcx, [rsp+0F8h+var_C0]
0x180014df5  test    rcx, rcx
0x180014df8  jz      short loc_180014E0C
0x180014dfa  mov     [rsp+0F8h+var_C0], rsi
0x180014dff  mov     rax, [rcx]
0x180014e02  mov     rax, [rax+10h]
0x180014e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e0b  nop
0x180014e0c  jmp     loc_180014AF4
0x180014e11  mov     rcx, [r12+10h]
0x180014e16  call    ?GetInstallReason@PlaceholderTileLocalImpl@PlaceholderTileTransformer@DataStoreCache@@QEAA?AW4InstallReasonType@23@XZ; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileLocalImpl::GetInstallReason(void)
0x180014e1b  cmp     eax, 2
0x180014e1e  jz      short loc_180014DDB
0x180014e20  mov     r8d, [rbx+10h]; length
0x180014e24  cmp     qword ptr [rbx+18h], 7
0x180014e29  jbe     short loc_180014E2E
0x180014e2b  mov     rbx, [rbx]
0x180014e2e  mov     rdx, rbx; sourceString
0x180014e31  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x180014e39  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x180014e3e  nop
0x180014e3f  mov     rbx, [rax+18h]
0x180014e43  mov     rcx, [r14]
0x180014e46  mov     rax, [rcx]
0x180014e49  lea     rdx, [rsp+0F8h+var_70]
0x180014e51  mov     rax, [rax+20h]
0x180014e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e5a  nop
0x180014e5b  mov     r9, rbx
0x180014e5e  mov     r8, rax
0x180014e61  lea     rdx, [rsp+0F8h+string]
0x180014e66  mov     rcx, r13
0x180014e69  call    ?AddTileToIndex@AppLifecycleTransformer@DataStoreCache@@AEAA?AV?$shared_ptr@UCachedTileLifecycleData@AppLifecycleTransformer@DataStoreCache@@@std@@AEBVDataItemIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::AppLifecycleTransformer::AddTileToIndex(DataStoreCache::DataItemIdentifier const &,HSTRING__ *)
0x180014e6e  mov     rdi, [rax]
0x180014e71  mov     rcx, [rax+8]
0x180014e75  mov     [rax], rsi
0x180014e78  mov     [rax+8], rsi
0x180014e7c  mov     [rsp+0F8h+var_98], rdi
0x180014e81  mov     [rsp+0F8h+var_98+8], rcx
0x180014e86  mov     rcx, [rsp+0F8h+var_A0]; this
0x180014e8b  test    rcx, rcx
0x180014e8e  jz      short loc_180014E96
0x180014e90  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180014e95  nop
0x180014e96  mov     rcx, [rsp+0F8h+var_70]; string
0x180014e9e  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
