# WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::OnEvent(_GUID const &,IUnknown *)

- ea: `0x180026fa0`
- end: `0x18002776a`
- name: `?OnEvent@AppsListGeneratedCollection@UnifiedTile@Shell@WindowsInternal@@UEAAJAEBU_GUID@@PEAUIUnknown@@@Z`
- size: `1994`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *__hidden this, const struct _GUID *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x180022020`
- `0x18002266c`
- `0x18002519c`
- `0x1800254cc`
- `0x180026fa0`
- `0x18003e708`
- `0x180042cf0`
- `0x180042d20`
- `0x180046874`
- `0x1800486c0`
- `0x1800dd1e4`
- `0x1801585a0`
- `0x180161204`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002741f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800274ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002753d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800275cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027651`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800271d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002741f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800274ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002753d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800275cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027651`

## string_xrefs

- `0x1800270c1`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x180027194`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x1800272c9`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x1800273de`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x18002746d`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x1800274fc`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x18002758b`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x18002761a`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`
- `0x18002772c`: `shellcommon\shell\tiles\unifiedtilemodel\lib\appslistgeneratedcollection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::OnEvent(
        WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        const char *a4)
{
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // ebx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v11; // r8
  int v12; // eax
  struct DataStoreCache::IDataItemChangeEvent *v13; // rdx
  unsigned int v14; // ebx
  WindowsInternal::Shell::UnifiedTile *v15; // rcx
  __int64 v16; // rcx
  __int64 result; // rax
  __int64 v18; // rcx
  WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *v19; // rdi
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v20; // rbx
  int v21; // eax
  unsigned int v22; // esi
  struct DataStoreCache::IDataItem *v23; // rcx
  WindowsInternal::Shell::UnifiedTile *v24; // rcx
  __int64 v25; // rcx
  int v26; // eax
  WindowsInternal::Shell::UnifiedTile *v27; // rcx
  __int64 v28; // rcx
  struct DataStoreCache::IDataItem *v29; // rcx
  int v30; // eax
  unsigned int v31; // edi
  struct DataStoreCache::IDataItem *v32; // rcx
  struct DataStoreCache::IDataItem *v33; // rcx
  int TileContainer; // eax
  unsigned int v35; // esi
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // [rsp+20h] [rbp-78h]
  int v40; // [rsp+20h] [rbp-78h]
  HSTRING string; // [rsp+30h] [rbp-68h] BYREF
  __int64 v42; // [rsp+38h] [rbp-60h] BYREF
  struct DataStoreCache::IDataItem *v43; // [rsp+40h] [rbp-58h] BYREF
  WindowsInternal::Shell::UnifiedTile *v44; // [rsp+48h] [rbp-50h] BYREF
  WindowsInternal::Shell::UnifiedTile::SimpleContainer *v45; // [rsp+50h] [rbp-48h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::CollectionTile *v46; // [rsp+58h] [rbp-40h] BYREF
  struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *v47[7]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  struct WindowsInternal::Shell::UnifiedTile::CollectionTile *v49; // [rsp+B8h] [rbp+20h] BYREF

  v6 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data1 )
    v6 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data4;
  try
  {
    if ( v6 )
      return 0;
    v42 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v7 = 0;
    v42 = 0;
    v8 = *((_QWORD *)this + 7);
    if ( v8 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v8 + 24LL))(
             v8,
             &GUID_1048dc30_f4f7_4ff4_970e_5058ca17cc26,
             &v42);
      v7 = v42;
    }
    else
    {
      v9 = 0;
    }
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
        (const char *)(unsigned int)v9,
        v39);
      v18 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      result = (unsigned int)v9;
    }
    else
    {
      if ( !v7 )
        return 0;
      v44 = 0;
      QueryInterface = a3->lpVtbl->QueryInterface;
      v11 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(&v44);
      v12 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64))QueryInterface)(
              a3,
              &GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e,
              v11);
      v14 = v12;
      if ( v12 >= 0 )
      {
        if ( !WindowsInternal::Shell::UnifiedTile::CouldDataItemChangeAffectAppListVisibility(v44, v13) )
        {
LABEL_10:
          v15 = v44;
          if ( v44 )
          {
            v44 = 0;
            (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v15 + 16LL))(v15);
          }
          v16 = v42;
          if ( v42 )
          {
            v42 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          return 0;
        }
        (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *, struct DataStoreCache::IDataItem **))(*(_QWORD *)v44 + 40LL))(
          v44,
          &v43);
        (*(void (__fastcall **)(struct DataStoreCache::IDataItem *, HSTRING *))(*(_QWORD *)v43 + 32LL))(v43, &string);
        WindowsInternal::Shell::UnifiedTile::_anonymous_namespace_::GetAppListEligibleUnifiedTile(v47, v43, v42);
        v19 = (WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection *)((char *)this - 24);
        v20 = v47[0];
        if ( v47[0] )
        {
          v45 = 0;
          LOBYTE(v49) = 0;
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v45);
          v21 = WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::EnsureContainerForTile(
                  v19,
                  (const struct DataStoreCache::DataItemIdentifier *)&string,
                  v20,
                  &v45,
                  (bool *)&v49);
          v22 = v21;
          if ( v21 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x209,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
              (const char *)(unsigned int)v21,
              v40);
            if ( v45 )
            {
              v45 = 0;
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer,Microsoft::WRL::FtmBase>::Release();
            }
            if ( v20 )
              (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v20 + 16LL))(v20);
            WindowsDeleteString(string);
            string = 0;
            v23 = v43;
            if ( v43 )
            {
              v43 = 0;
              (*(void (__fastcall **)(struct DataStoreCache::IDataItem *))(*(_QWORD *)v23 + 16LL))(v23);
            }
            v24 = v44;
            if ( v44 )
            {
              v44 = 0;
              (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v24 + 16LL))(v24);
            }
            v25 = v42;
            if ( v42 )
            {
              v42 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
            }
            return v22;
          }
          if ( (_BYTE)v49 )
          {
LABEL_42:
            if ( v45 )
            {
              v45 = 0;
              goto LABEL_44;
            }
            goto LABEL_45;
          }
          v46 = 0;
          v49 = 0;
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v49);
          Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v46);
          TileContainer = WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::FindTileContainer(
                            v19,
                            (const struct DataStoreCache::DataItemIdentifier *)&string,
                            &v46,
                            &v49);
          v35 = TileContainer;
          if ( TileContainer < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x214,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
              (const char *)(unsigned int)TileContainer,
              v40);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v49);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v46);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v45);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
            WindowsDeleteString(string);
            string = 0;
            v32 = v43;
            if ( v43 )
            {
              v43 = 0;
              (*(void (__fastcall **)(struct DataStoreCache::IDataItem *))(*(_QWORD *)v32 + 16LL))(v32);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
            return v35;
          }
          if ( !v46 || !v49 )
          {
            v30 = WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddDataItem(v45, v43, 1);
            v31 = v30;
            if ( v30 >= 0 )
            {
LABEL_52:
              Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v49);
              Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v46);
              goto LABEL_42;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x222,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
              (const char *)(unsigned int)v30,
              v40);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v49);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v46);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v45);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
            WindowsDeleteString(string);
            string = 0;
            v33 = v43;
            if ( v43 )
              goto LABEL_63;
LABEL_64:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
            return v31;
          }
          v36 = WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::RemoveTileFromContainer(
                  v19,
                  (const struct DataStoreCache::DataItemIdentifier *)&string,
                  v46);
          v31 = v36;
          if ( v36 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x21B,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
              (const char *)(unsigned int)v36,
              v40);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v49);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v46);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v45);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
            WindowsDeleteString(string);
            string = 0;
            v33 = v43;
            if ( !v43 )
              goto LABEL_64;
          }
          else
          {
            v37 = WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddCollectionTile(
                    v45,
                    (const struct DataStoreCache::DataItemIdentifier *)&string,
                    v49,
                    1);
            v31 = v37;
            if ( v37 >= 0 )
              goto LABEL_52;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x21C,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
              (const char *)(unsigned int)v37,
              v40);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v49);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v46);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v45);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
            WindowsDeleteString(string);
            string = 0;
            v33 = v43;
            if ( !v43 )
              goto LABEL_64;
          }
LABEL_63:
          v43 = 0;
          (*(void (__fastcall **)(struct DataStoreCache::IDataItem *))(*(_QWORD *)v33 + 16LL))(v33);
          goto LABEL_64;
        }
        v49 = 0;
        v46 = 0;
        Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v49);
        v26 = WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::FindTileContainer(
                v19,
                (const struct DataStoreCache::DataItemIdentifier *)&string,
                &v49,
                &v46);
        if ( v26 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x22D,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
            (const char *)(unsigned int)v26,
            v39);
        }
        else if ( v49 )
        {
          v38 = WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::RemoveTileFromContainer(
                  v19,
                  (const struct DataStoreCache::DataItemIdentifier *)&string,
                  v49);
          v31 = v38;
          if ( v38 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x230,
              (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
              (const char *)(unsigned int)v38,
              v39);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v46);
            Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(&v49);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v47);
            WindowsDeleteString(string);
            string = 0;
            v33 = v43;
            if ( !v43 )
              goto LABEL_64;
            goto LABEL_63;
          }
        }
        Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(&v46);
        if ( v49 )
        {
          v49 = 0;
LABEL_44:
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer,Microsoft::WRL::FtmBase>::Release();
        }
LABEL_45:
        if ( v20 )
          (*(void (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *))(*(_QWORD *)v20 + 16LL))(v20);
        WindowsDeleteString(string);
        string = 0;
        v29 = v43;
        if ( v43 )
        {
          v43 = 0;
          (*(void (__fastcall **)(struct DataStoreCache::IDataItem *))(*(_QWORD *)v29 + 16LL))(v29);
        }
        goto LABEL_10;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
        (const char *)(unsigned int)v12,
        v39);
      v27 = v44;
      if ( v44 )
      {
        v44 = 0;
        (*(void (__fastcall **)(WindowsInternal::Shell::UnifiedTile *))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v28 = v42;
      if ( v42 )
      {
        v42 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      result = v14;
    }
  }
  catch ( ... )
  {
    LODWORD(v49) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x237,
                     (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\appslistgeneratedcollection.cpp",
                     a4);
    return (unsigned int)v49;
  }
  return result;
}

```

## disassembly

```asm
0x180026fa0  push    rbx
0x180026fa2  push    rsi
0x180026fa3  push    rdi
0x180026fa4  push    r14
0x180026fa6  sub     rsp, 78h
0x180026faa  mov     rsi, r8
0x180026fad  mov     rdi, rcx
0x180026fb0  mov     rax, [rdx]
0x180026fb3  sub     rax, qword ptr cs:_GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data1
0x180026fba  jnz     short loc_180026FC7
0x180026fbc  mov     rax, [rdx+8]
0x180026fc0  sub     rax, qword ptr cs:_GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e.Data4
0x180026fc7  xor     r14d, r14d
0x180026fca  test    rax, rax
0x180026fcd  jnz     loc_1800270A6
0x180026fd3  mov     [rsp+98h+var_60], r14
0x180026fd8  lea     rcx, [rsp+98h+var_60]
0x180026fdd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180026fe2  nop
0x180026fe3  mov     eax, r14d
0x180026fe6  mov     [rsp+98h+var_60], rax
0x180026feb  mov     rcx, [rdi+38h]
0x180026fef  test    rcx, rcx
0x180026ff2  jz      loc_180027694
0x180026ff8  mov     rax, [rcx]
0x180026ffb  lea     r8, [rsp+98h+var_60]
0x180027000  lea     rdx, _GUID_1048dc30_f4f7_4ff4_970e_5058ca17cc26
0x180027007  mov     rax, [rax+18h]
0x18002700b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027010  mov     ebx, eax
0x180027012  mov     rax, [rsp+98h+var_60]
0x180027017  test    ebx, ebx
0x180027019  js      loc_1800270B6
0x18002701f  test    rax, rax
0x180027022  jz      loc_1800270B2
0x180027028  mov     [rsp+98h+var_50], r14
0x18002702d  mov     rax, [rsi]
0x180027030  mov     rbx, [rax]
0x180027033  lea     rcx, [rsp+98h+var_50]
0x180027038  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>)
0x18002703d  mov     r8, rax
0x180027040  lea     rdx, _GUID_532e9f4f_52ed_47b0_ab7a_bf957722001e
0x180027047  mov     rcx, rsi
0x18002704a  mov     rax, rbx
0x18002704d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027052  mov     ebx, eax
0x180027054  test    eax, eax
0x180027056  js      loc_1800272BE
0x18002705c  mov     rcx, [rsp+98h+var_50]; this
0x180027061  call    ?CouldDataItemChangeAffectAppListVisibility@UnifiedTile@Shell@WindowsInternal@@YA_NPEAUIDataItemChangeEvent@DataStoreCache@@@Z; WindowsInternal::Shell::UnifiedTile::CouldDataItemChangeAffectAppListVisibility(DataStoreCache::IDataItemChangeEvent *)
0x180027066  test    al, al
0x180027068  jnz     loc_1800270F3
0x18002706e  mov     rcx, [rsp+98h+var_50]
0x180027073  test    rcx, rcx
0x180027076  jz      short loc_18002708A
0x180027078  mov     [rsp+98h+var_50], r14
0x18002707d  mov     rax, [rcx]
0x180027080  mov     rax, [rax+10h]
0x180027084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027089  nop
0x18002708a  mov     rcx, [rsp+98h+var_60]
0x18002708f  test    rcx, rcx
0x180027092  jz      short loc_1800270A6
0x180027094  mov     [rsp+98h+var_60], r14
0x180027099  mov     rax, [rcx]
0x18002709c  mov     rax, [rax+10h]
0x1800270a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270a5  nop
0x1800270a6  xor     eax, eax
0x1800270a8  add     rsp, 78h
0x1800270ac  pop     r14
0x1800270ae  pop     rdi
0x1800270af  pop     rsi
0x1800270b0  pop     rbx
0x1800270b1  retn
0x1800270b2  xor     eax, eax
0x1800270b4  jmp     short loc_1800270A8
0x1800270b6  mov     rcx, [rsp+98h]; this
0x1800270be  mov     r9d, ebx; char *
0x1800270c1  lea     r8, aShellcommonShe_116; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800270c8  mov     edx, 1F9h; void *
0x1800270cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800270d2  nop
0x1800270d3  mov     rcx, [rsp+98h+var_60]
0x1800270d8  test    rcx, rcx
0x1800270db  jz      short loc_1800270EF
0x1800270dd  mov     [rsp+98h+var_60], r14
0x1800270e2  mov     rax, [rcx]
0x1800270e5  mov     rax, [rax+10h]
0x1800270e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270ee  nop
0x1800270ef  mov     eax, ebx
0x1800270f1  jmp     short loc_1800270A8
0x1800270f3  mov     rcx, [rsp+98h+var_50]
0x1800270f8  mov     rax, [rcx]
0x1800270fb  lea     rdx, [rsp+98h+var_58]
0x180027100  mov     rax, [rax+28h]
0x180027104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027109  nop
0x18002710a  mov     rcx, [rsp+98h+var_58]
0x18002710f  mov     rax, [rcx]
0x180027112  lea     rdx, [rsp+98h+string]
0x180027117  mov     rax, [rax+20h]
0x18002711b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027120  mov     r8, [rsp+98h+var_60]
0x180027125  mov     rdx, [rsp+98h+var_58]
0x18002712a  lea     rcx, [rsp+98h+var_38]
0x18002712f  call    WindowsInternal__Shell__UnifiedTile___anonymous_namespace___GetAppListEligibleUnifiedTile
0x180027134  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180027138  mov     rbx, [rsp+98h+var_38]
0x18002713d  test    rbx, rbx
0x180027140  jz      loc_18002723A
0x180027146  mov     [rsp+98h+var_48], r14
0x18002714b  mov     byte ptr [rsp+98h+arg_18], r14b
0x180027153  lea     rcx, [rsp+98h+var_48]
0x180027158  call    ?InternalRelease@?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(void)
0x18002715d  lea     rax, [rsp+98h+arg_18]
0x180027165  mov     qword ptr [rsp+98h+var_78], rax; int
0x18002716a  lea     r9, [rsp+98h+var_48]; struct WindowsInternal::Shell::UnifiedTile::SimpleContainer **
0x18002716f  mov     r8, rbx; struct WindowsInternal::Shell::UnifiedTile::IUnifiedTile *
0x180027172  lea     rdx, [rsp+98h+string]; struct DataStoreCache::DataItemIdentifier *
0x180027177  mov     rcx, rdi; this
0x18002717a  call    ?EnsureContainerForTile@AppsListGeneratedCollection@UnifiedTile@Shell@WindowsInternal@@AEAAJAEBVDataItemIdentifier@DataStoreCache@@PEAUIUnifiedTile@234@PEAPEAVSimpleContainer@234@PEA_N@Z; WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::EnsureContainerForTile(DataStoreCache::DataItemIdentifier const &,WindowsInternal::Shell::UnifiedTile::IUnifiedTile *,WindowsInternal::Shell::UnifiedTile::SimpleContainer * *,bool *)
0x18002717f  mov     esi, eax
0x180027181  test    eax, eax
0x180027183  jns     loc_18002731A
0x180027189  mov     rcx, [rsp+98h]; this
0x180027191  mov     r9d, eax; char *
0x180027194  lea     r8, aShellcommonShe_116; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x18002719b  mov     edx, 209h; void *
0x1800271a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800271a5  mov     rcx, [rsp+98h+var_48]
0x1800271aa  test    rcx, rcx
0x1800271ad  jz      short loc_1800271BA
0x1800271af  mov     [rsp+98h+var_48], r14
0x1800271b4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UITileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer,Microsoft::WRL::FtmBase>::Release(void)
0x1800271b9  nop
0x1800271ba  test    rbx, rbx
0x1800271bd  jz      short loc_1800271CF
0x1800271bf  mov     rax, [rbx]
0x1800271c2  mov     rcx, rbx
0x1800271c5  mov     rax, [rax+10h]
0x1800271c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271ce  nop
0x1800271cf  mov     rcx, [rsp+98h+string]; string
0x1800271d4  call    cs:__imp_WindowsDeleteString
0x1800271da  mov     [rsp+98h+string], r14
0x1800271df  mov     rcx, [rsp+98h+var_58]
0x1800271e4  test    rcx, rcx
0x1800271e7  jz      short loc_1800271FB
0x1800271e9  mov     [rsp+98h+var_58], r14
0x1800271ee  mov     rax, [rcx]
0x1800271f1  mov     rax, [rax+10h]
0x1800271f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271fa  nop
0x1800271fb  mov     rcx, [rsp+98h+var_50]
0x180027200  test    rcx, rcx
0x180027203  jz      short loc_180027217
0x180027205  mov     [rsp+98h+var_50], r14
0x18002720a  mov     rax, [rcx]
0x18002720d  mov     rax, [rax+10h]
0x180027211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027216  nop
0x180027217  mov     rcx, [rsp+98h+var_60]
0x18002721c  test    rcx, rcx
0x18002721f  jz      short loc_180027233
0x180027221  mov     [rsp+98h+var_60], r14
0x180027226  mov     rax, [rcx]
0x180027229  mov     rax, [rax+10h]
0x18002722d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027232  nop
0x180027233  mov     eax, esi
0x180027235  jmp     loc_1800270A8
0x18002723a  mov     [rsp+98h+arg_18], r14
0x180027242  mov     [rsp+98h+var_40], r14
0x180027247  lea     rcx, [rsp+98h+var_40]
0x18002724c  call    ?InternalRelease@?$ComPtr@VCollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(void)
0x180027251  lea     rcx, [rsp+98h+arg_18]
0x180027259  call    ?InternalRelease@?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(void)
0x18002725e  lea     r9, [rsp+98h+var_40]; struct WindowsInternal::Shell::UnifiedTile::CollectionTile **
0x180027263  lea     r8, [rsp+98h+arg_18]; struct WindowsInternal::Shell::UnifiedTile::SimpleContainer **
0x18002726b  lea     rdx, [rsp+98h+string]; struct DataStoreCache::DataItemIdentifier *
0x180027270  mov     rcx, rdi; this
0x180027273  call    ?FindTileContainer@AppsListGeneratedCollection@UnifiedTile@Shell@WindowsInternal@@AEBAJAEBVDataItemIdentifier@DataStoreCache@@PEAPEAVSimpleContainer@234@PEAPEAVCollectionTile@234@@Z; WindowsInternal::Shell::UnifiedTile::AppsListGeneratedCollection::FindTileContainer(DataStoreCache::DataItemIdentifier const &,WindowsInternal::Shell::UnifiedTile::SimpleContainer * *,WindowsInternal::Shell::UnifiedTile::CollectionTile * *)
0x180027278  mov     rcx, [rsp+98h]; this
0x180027280  test    eax, eax
0x180027282  js      loc_180027729
0x180027288  mov     r8, [rsp+98h+arg_18]; struct WindowsInternal::Shell::UnifiedTile::SimpleContainer *
0x180027290  test    r8, r8
0x180027293  jnz     loc_180027742
0x180027299  lea     rcx, [rsp+98h+var_40]
0x18002729e  call    ?InternalRelease@?$ComPtr@VCollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(void)
0x1800272a3  mov     rcx, [rsp+98h+arg_18]
0x1800272ab  test    rcx, rcx
0x1800272ae  jz      loc_18002733D
0x1800272b4  mov     [rsp+98h+arg_18], r14
0x1800272bc  jmp     short loc_180027337
0x1800272be  mov     rcx, [rsp+98h]; this
0x1800272c6  mov     r9d, ebx; char *
0x1800272c9  lea     r8, aShellcommonShe_116; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800272d0  mov     edx, 1FDh; void *
0x1800272d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800272da  nop
0x1800272db  mov     rcx, [rsp+98h+var_50]
0x1800272e0  test    rcx, rcx
0x1800272e3  jz      short loc_1800272F7
0x1800272e5  mov     [rsp+98h+var_50], r14
0x1800272ea  mov     rax, [rcx]
0x1800272ed  mov     rax, [rax+10h]
0x1800272f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800272f6  nop
0x1800272f7  mov     rcx, [rsp+98h+var_60]
0x1800272fc  test    rcx, rcx
0x1800272ff  jz      short loc_180027313
0x180027301  mov     [rsp+98h+var_60], r14
0x180027306  mov     rax, [rcx]
0x180027309  mov     rax, [rax+10h]
0x18002730d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027312  nop
0x180027313  mov     eax, ebx
0x180027315  jmp     loc_1800270A8
0x18002731a  cmp     byte ptr [rsp+98h+arg_18], r14b
0x180027322  jz      loc_18002769C
0x180027328  mov     rcx, [rsp+98h+var_48]
0x18002732d  test    rcx, rcx
0x180027330  jz      short loc_18002733D
0x180027332  mov     [rsp+98h+var_48], r14
0x180027337  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UITileCollectionContainer@UnifiedTile@Shell@WindowsInternal@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,WindowsInternal::Shell::UnifiedTile::ITileCollectionContainer,Microsoft::WRL::FtmBase>::Release(void)
0x18002733c  nop
0x18002733d  test    rbx, rbx
0x180027340  jz      short loc_180027352
0x180027342  mov     rax, [rbx]
0x180027345  mov     rcx, rbx
0x180027348  mov     rax, [rax+10h]
0x18002734c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027351  nop
0x180027352  mov     rcx, [rsp+98h+string]; string
0x180027357  call    cs:__imp_WindowsDeleteString
0x18002735d  mov     [rsp+98h+string], r14
0x180027362  mov     rcx, [rsp+98h+var_58]
0x180027367  test    rcx, rcx
0x18002736a  jz      short loc_18002737E
0x18002736c  mov     [rsp+98h+var_58], r14
0x180027371  mov     rax, [rcx]
0x180027374  mov     rax, [rax+10h]
0x180027378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002737d  nop
0x18002737e  jmp     loc_18002706E
0x180027383  mov     r8, [rsp+98h+var_40]; struct WindowsInternal::Shell::UnifiedTile::SimpleContainer *
0x180027388  test    r8, r8
0x18002738b  jz      short loc_18002739B
0x18002738d  cmp     [rsp+98h+arg_18], r14
0x180027395  jnz     loc_1800276E9
0x18002739b  mov     r8b, 1; bool
0x18002739e  mov     rdx, [rsp+98h+var_58]; struct DataStoreCache::IDataItem *
0x1800273a3  mov     rcx, [rsp+98h+var_48]; this
0x1800273a8  call    ?AddDataItem@SimpleContainer@UnifiedTile@Shell@WindowsInternal@@QEAAJPEAUIDataItem@DataStoreCache@@_N@Z; WindowsInternal::Shell::UnifiedTile::SimpleContainer::AddDataItem(DataStoreCache::IDataItem *,bool)
0x1800273ad  mov     edi, eax
0x1800273af  test    eax, eax
0x1800273b1  js      loc_180027580
0x1800273b7  lea     rcx, [rsp+98h+arg_18]
0x1800273bf  call    ?InternalRelease@?$ComPtr@VCollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(void)
0x1800273c4  lea     rcx, [rsp+98h+var_40]
0x1800273c9  call    ?InternalRelease@?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(void)
0x1800273ce  jmp     loc_180027328
0x1800273d3  mov     rcx, [rsp+98h]; this
0x1800273db  mov     r9d, esi; char *
0x1800273de  lea     r8, aShellcommonShe_116; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800273e5  mov     edx, 214h; void *
0x1800273ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800273ef  lea     rcx, [rsp+98h+arg_18]
0x1800273f7  call    ?InternalRelease@?$ComPtr@VCollectionTile@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CollectionTile>::InternalRelease(void)
0x1800273fc  lea     rcx, [rsp+98h+var_40]
0x180027401  call    ?InternalRelease@?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(void)
0x180027406  lea     rcx, [rsp+98h+var_48]
0x18002740b  call    ?InternalRelease@?$ComPtr@VSimpleContainer@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::SimpleContainer>::InternalRelease(void)
0x180027410  lea     rcx, [rsp+98h+var_38]
0x180027415  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002741a  mov     rcx, [rsp+98h+string]; string
0x18002741f  call    cs:__imp_WindowsDeleteString
0x180027425  mov     [rsp+98h+string], r14
0x18002742a  mov     rcx, [rsp+98h+var_58]
0x18002742f  test    rcx, rcx
0x180027432  jz      short loc_180027446
0x180027434  mov     [rsp+98h+var_58], r14
0x180027439  mov     rax, [rcx]
0x18002743c  mov     rax, [rax+10h]
0x180027440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027445  nop
0x180027446  lea     rcx, [rsp+98h+var_50]
0x18002744b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180027450  nop
0x180027451  lea     rcx, [rsp+98h+var_60]
0x180027456  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002745b  mov     eax, esi
0x18002745d  jmp     loc_1800270A8
0x180027462  mov     rcx, [rsp+98h]; this
0x18002746a  mov     r9d, edi; char *
0x18002746d  lea     r8, aShellcommonShe_116; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180027474  mov     edx, 21Bh; void *
  ... truncated ...
```
