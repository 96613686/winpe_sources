# DataStoreCache::TileStoreTransformer::UpdateSecondaryTiles(DataStoreCache::DataItemIdentifier const &,DataStoreCache::IDataStorePropertyBag *,DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles &)

- ea: `0x1800c7eb8`
- end: `0x1800c8397`
- name: `?UpdateSecondaryTiles@TileStoreTransformer@DataStoreCache@@AEAAXAEBVDataItemIdentifier@2@PEAUIDataStorePropertyBag@2@AEAVTileStoreTransformerReconcileTiles@DataStoreTransformerTelemetry@@@Z`
- size: `1247`
- prototype: `void __fastcall(DataStoreCache::TileStoreTransformer *__hidden this, const struct DataStoreCache::DataItemIdentifier *, struct DataStoreCache::IDataStorePropertyBag *, struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001b3e4`

## callees

- `0x18000b5f0`
- `0x18000ce94`
- `0x1800131dc`
- `0x180013b80`
- `0x18001dac0`
- `0x180022020`
- `0x18006fd68`
- `0x1800c6f9c`
- `0x1800c7eb8`
- `0x1800c83a0`
- `0x1800c846c`
- `0x1800c851c`
- `0x1800c855c`
- `0x18011e8bc`
- `0x180147be8`
- `0x18036cfb8`
- `0x180371f30`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c7efa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c7efa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c7f7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c7f7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c809e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c80df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7f8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c7fc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c809e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c80df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c820c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c820c`

## string_xrefs

- `0x1800c813e`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`
- `0x1800c8254`: `shellcommon\shell\datastorecache\transformers\tilestore\lib\tilestoretransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall DataStoreCache::TileStoreTransformer::UpdateSecondaryTiles(
        DataStoreCache::TileStoreTransformer *this,
        const struct DataStoreCache::DataItemIdentifier *a2,
        struct DataStoreCache::IDataStorePropertyBag *a3,
        struct DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles *a4)
{
  DataStoreCache::TileStoreTransformer *v6; // rdi
  RTL_SRWLOCK *v7; // r15
  __int64 SecondaryTileIdentifiersForPrimaryTileIdentifier; // rbx
  DataStoreCache::DataItemIdentifier *v9; // rdi
  DataStoreCache::DataItemIdentifier *v10; // r14
  HSTRING *v11; // r12
  __int64 v12; // rsi
  HSTRING v13; // rcx
  unsigned __int8 (__fastcall *v14)(struct DataStoreCache::IDataStorePropertyBag *, void *, HSTRING *); // rbx
  HSTRING *v15; // r15
  __int64 v16; // rdi
  unsigned __int8 (__fastcall *v17)(__int64, const struct _GUID *, GUID *, __int64); // rbx
  __int64 v18; // rax
  struct DataStoreCache::IDataStorePropertyBag *v19; // rdi
  unsigned __int8 (__fastcall *v20)(struct DataStoreCache::IDataStorePropertyBag *, void *, HSTRING *); // rbx
  HSTRING v21; // r8
  bool v22; // r9
  struct DataStoreCache::IDataStorePropertyBag *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  DataStoreCache::PropertyBagLookaside *v28; // rbx
  DataStoreCache::TileStoreTransformer *v29; // rdi
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rax
  char *v33; // rcx
  struct DataStoreCache::IDataStorePropertyBag *v34; // rbx
  int (__fastcall *v35)(struct DataStoreCache::IDataStorePropertyBag *, GUID *, __int64 *); // rdi
  int v36; // [rsp+28h] [rbp-69h]
  HSTRING v37; // [rsp+38h] [rbp-59h] BYREF
  DataStoreCache::PropertyBagLookaside *StringRawBuffer; // [rsp+40h] [rbp-51h] BYREF
  struct DataStoreCache::IDataStorePropertyBag *v39; // [rsp+48h] [rbp-49h] BYREF
  __int64 v40; // [rsp+50h] [rbp-41h] BYREF
  __int64 v41; // [rsp+58h] [rbp-39h] BYREF
  HSTRING string; // [rsp+60h] [rbp-31h] BYREF
  __int64 v43; // [rsp+68h] [rbp-29h] BYREF
  __int64 v44; // [rsp+70h] [rbp-21h] BYREF
  char *v45; // [rsp+78h] [rbp-19h] BYREF
  DataStoreCache::DataItemIdentifier *v46; // [rsp+80h] [rbp-11h] BYREF
  HSTRING *v47; // [rsp+88h] [rbp-9h]
  __int64 v48; // [rsp+90h] [rbp-1h]
  __int64 v49; // [rsp+98h] [rbp+7h] BYREF
  DataStoreCache::DataItemIdentifier *v50[9]; // [rsp+A0h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+5Fh]

  v6 = this;
  std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(&v46);
  v7 = (RTL_SRWLOCK *)((char *)v6 + 152);
  AcquireSRWLockShared((PSRWLOCK)v6 + 19);
  v45 = (char *)v6 + 152;
  SecondaryTileIdentifiersForPrimaryTileIdentifier = DataStoreCache::TileStoreTransformer::GetSecondaryTileIdentifiersForPrimaryTileIdentifier(
                                                       v50,
                                                       (char *)v6 + 224,
                                                       a2);
  if ( &v46 == (DataStoreCache::DataItemIdentifier **)SecondaryTileIdentifiersForPrimaryTileIdentifier )
  {
    v12 = v48;
    v11 = v47;
    v10 = v46;
  }
  else
  {
    v9 = v46;
    if ( v46 )
    {
      std::_Destroy_range<std::allocator<DataStoreCache::DataItemIdentifier>>(v46);
      std::_Deallocate<16>(v9, (v48 - (_QWORD)v9) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    v10 = *(DataStoreCache::DataItemIdentifier **)SecondaryTileIdentifiersForPrimaryTileIdentifier;
    v46 = *(DataStoreCache::DataItemIdentifier **)SecondaryTileIdentifiersForPrimaryTileIdentifier;
    v11 = *(HSTRING **)(SecondaryTileIdentifiersForPrimaryTileIdentifier + 8);
    v47 = v11;
    v12 = *(_QWORD *)(SecondaryTileIdentifiersForPrimaryTileIdentifier + 16);
    v48 = v12;
    *(_QWORD *)SecondaryTileIdentifiersForPrimaryTileIdentifier = 0;
    *(_QWORD *)(SecondaryTileIdentifiersForPrimaryTileIdentifier + 8) = 0;
    *(_QWORD *)(SecondaryTileIdentifiersForPrimaryTileIdentifier + 16) = 0;
    v6 = this;
  }
  if ( v50[0] )
  {
    std::_Destroy_range<std::allocator<DataStoreCache::DataItemIdentifier>>(v50[0]);
    std::_Deallocate<16>(v50[0], (v50[2] - v50[0]) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  if ( v7 )
    ReleaseSRWLockShared(v7);
  v13 = 0;
  v37 = 0;
  if ( v10 != (DataStoreCache::DataItemIdentifier *)v11 )
  {
    v14 = *(unsigned __int8 (__fastcall **)(struct DataStoreCache::IDataStorePropertyBag *, void *, HSTRING *))(*(_QWORD *)a3 + 32LL);
    WindowsDeleteString(0);
    v37 = 0;
    if ( v14(a3, &DataStoreCache::TileStoreProperties::PackageFullName, &v37) )
    {
      v43 = 0;
      if ( !(*(unsigned __int8 (__fastcall **)(struct DataStoreCache::IDataStorePropertyBag *, void **, __int64, __int64 *))(*(_QWORD *)a3 + 24LL))(
              a3,
              &DataStoreCache::TileStoreProperties::TileRevision,
              8,
              &v43) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x885,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
          (const char *)0x80070490LL,
          v36);
      v15 = (HSTRING *)v10;
      while ( 1 )
      {
        (*(void (__fastcall **)(_QWORD, __int64 *, HSTRING))(**((_QWORD **)v6 + 55) + 40LL))(
          *((_QWORD *)v6 + 55),
          &v40,
          *v15);
        v39 = 0;
        v16 = v40;
        v17 = *(unsigned __int8 (__fastcall **)(__int64, const struct _GUID *, GUID *, __int64))(*(_QWORD *)v40 + 48LL);
        v18 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(&v39);
        if ( v17(v16, &c_tileStoreTransformerId, &GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb, v18) )
        {
          string = 0;
          v19 = v39;
          v20 = *(unsigned __int8 (__fastcall **)(struct DataStoreCache::IDataStorePropertyBag *, void *, HSTRING *))(*(_QWORD *)v39 + 32LL);
          WindowsDeleteString(0);
          string = 0;
          if ( v20(v19, &DataStoreCache::TileStoreProperties::PackageFullName, &string)
            && !DataStoreCache::AreStringsEqual((DataStoreCache *)v37, string, v21, v22) )
          {
            StringRawBuffer = 0;
            v41 = 0;
            v34 = v39;
            v35 = **(int (__fastcall ***)(struct DataStoreCache::IDataStorePropertyBag *, GUID *, __int64 *))v39;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
            if ( v35(v34, &GUID_58e38d18_77ad_494b_be1a_9ce327d10b5c, &v41) < 0 )
            {
              v29 = this;
              v32 = wil::MakeOrThrow<DataStoreCache::PropertyBagLookaside,_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &>(
                      &v45,
                      &c_tileStoreTransformerId,
                      (char *)this + 128);
              Microsoft::WRL::ComPtr<DataStoreCache::PropertyBagLookaside>::operator=(&StringRawBuffer, v32);
              v33 = v45;
              if ( v45 )
              {
                v45 = 0;
                Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(v33);
              }
              v28 = StringRawBuffer;
              DataStoreCache::PropertyBagLookaside::SetCachedPropertyBag(StringRawBuffer, v39);
            }
            else
            {
              v25 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 24LL))(v41, &v49);
              Microsoft::WRL::ComPtr<DataStoreCache::PropertyBagLookaside>::operator=(&StringRawBuffer, v25);
              v27 = v49;
              if ( v49 )
              {
                v49 = 0;
                Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(v27);
              }
              v28 = StringRawBuffer;
              v29 = this;
            }
            DataStoreCache::PropertyBagLookaside::SetLookasideValueType<__int64>(v28, v26, &v43);
            DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
              v28,
              (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TileStoreProperties::PackageFullName,
              v37);
            v30 = *((_QWORD *)v29 + 57);
            if ( v30 )
              (*(void (__fastcall **)(__int64, __int64, __int64, HSTRING))(*(_QWORD *)v30 + 48LL))(v30, v40, 1, v37);
            v44 = 0;
            v31 = Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::As<DataStoreCache::IDataUpdate>(&v40, &v44);
            if ( v31 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x8B3,
                (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\tilestore\\lib\\tilestoretransformer.cpp",
                (const char *)(unsigned int)v31,
                v36);
            (*(void (__fastcall **)(__int64, const struct _GUID *, _QWORD, unsigned __int64))(*(_QWORD *)v44 + 24LL))(
              v44,
              &c_tileStoreTransformerId,
              0,
              ((unsigned __int64)v28 + 8) & -(__int64)(v28 != 0));
            StringRawBuffer = (DataStoreCache::PropertyBagLookaside *)WindowsGetStringRawBuffer(*v15, 0);
            DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles::SecondaryTileUpdatedForPrimaryTileChange<unsigned short const *,__int64 &>(
              a4,
              &StringRawBuffer,
              &v43);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v44);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
            if ( v28 )
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(v28);
          }
          WindowsDeleteString(string);
        }
        v23 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(struct DataStoreCache::IDataStorePropertyBag *))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v24 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        if ( ++v15 == v11 )
          break;
        v6 = this;
      }
    }
    v13 = v37;
  }
  WindowsDeleteString(v13);
  v37 = 0;
  if ( v10 )
  {
    std::_Destroy_range<std::allocator<DataStoreCache::DataItemIdentifier>>(v10);
    std::_Deallocate<16>(v10, (v12 - (_QWORD)v10) & 0xFFFFFFFFFFFFFFF8uLL);
  }
}

```

## disassembly

```asm
0x1800c7eb8  mov     rax, rsp
0x1800c7ebb  mov     [rax+10h], rbx
0x1800c7ebf  mov     [rax+20h], r9
0x1800c7ec3  mov     [rax+8], rcx
0x1800c7ec7  push    rbp
0x1800c7ec8  push    rsi
0x1800c7ec9  push    rdi
0x1800c7eca  push    r12
0x1800c7ecc  push    r13
0x1800c7ece  push    r14
0x1800c7ed0  push    r15
0x1800c7ed2  lea     rbp, [rax-5Fh]
0x1800c7ed6  sub     rsp, 0B0h
0x1800c7edd  mov     r13, r8
0x1800c7ee0  mov     rbx, rdx
0x1800c7ee3  mov     rdi, rcx
0x1800c7ee6  lea     rcx, [rbp+57h+var_68]
0x1800c7eea  call    ??0?$vector@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@V?$allocator@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(void)
0x1800c7eef  nop
0x1800c7ef0  lea     r15, [rdi+98h]
0x1800c7ef7  mov     rcx, r15; SRWLock
0x1800c7efa  call    cs:__imp_AcquireSRWLockShared
0x1800c7f00  mov     [rbp+57h+var_70], r15
0x1800c7f04  lea     rdx, [rdi+0E0h]
0x1800c7f0b  mov     r8, rbx
0x1800c7f0e  lea     rcx, [rbp+57h+var_48]
0x1800c7f12  call    ?GetSecondaryTileIdentifiersForPrimaryTileIdentifier@TileStoreTransformer@DataStoreCache@@CA?AV?$vector@VDataItemIdentifier@DataStoreCache@@V?$allocator@VDataItemIdentifier@DataStoreCache@@@std@@@std@@AEBV?$unordered_multimap@VDataItemIdentifier@DataStoreCache@@V12@U?$hash@VDataItemIdentifier@DataStoreCache@@@std@@U?$equal_to@VDataItemIdentifier@DataStoreCache@@@4@V?$allocator@U?$pair@$$CBVDataItemIdentifier@DataStoreCache@@V12@@std@@@4@@4@AEBVDataItemIdentifier@2@@Z; DataStoreCache::TileStoreTransformer::GetSecondaryTileIdentifiersForPrimaryTileIdentifier(std::unordered_multimap<DataStoreCache::DataItemIdentifier,DataStoreCache::DataItemIdentifier> const &,DataStoreCache::DataItemIdentifier const &)
0x1800c7f17  mov     rbx, rax
0x1800c7f1a  lea     rax, [rbp+57h+var_68]
0x1800c7f1e  cmp     rax, rbx
0x1800c7f21  jz      loc_1800C82DC
0x1800c7f27  mov     rdi, [rbp+57h+var_68]
0x1800c7f2b  test    rdi, rdi
0x1800c7f2e  jnz     loc_1800C82B8
0x1800c7f34  mov     r14, [rbx]
0x1800c7f37  mov     [rbp+57h+var_68], r14
0x1800c7f3b  mov     r12, [rbx+8]
0x1800c7f3f  mov     [rbp+57h+var_60], r12
0x1800c7f43  mov     rsi, [rbx+10h]
0x1800c7f47  mov     [rbp+57h+var_58], rsi
0x1800c7f4b  mov     qword ptr [rbx], 0
0x1800c7f52  mov     qword ptr [rbx+8], 0
0x1800c7f5a  mov     qword ptr [rbx+10h], 0
0x1800c7f62  mov     rdi, [rbp+57h+arg_0]
0x1800c7f66  mov     rcx, [rbp+57h+var_48]; this
0x1800c7f6a  test    rcx, rcx
0x1800c7f6d  jnz     loc_1800C82ED
0x1800c7f73  test    r15, r15
0x1800c7f76  jz      short loc_1800C7F81
0x1800c7f78  mov     rcx, r15; SRWLock
0x1800c7f7b  call    cs:__imp_ReleaseSRWLockShared
0x1800c7f81  xor     ecx, ecx; string
0x1800c7f83  mov     [rbp+57h+var_B0], rcx
0x1800c7f87  cmp     r14, r12
0x1800c7f8a  jnz     short loc_1800C7FBE
0x1800c7f8c  call    cs:__imp_WindowsDeleteString
0x1800c7f92  mov     [rbp+57h+var_B0], 0
0x1800c7f9a  test    r14, r14
0x1800c7f9d  jnz     loc_1800C8375
0x1800c7fa3  mov     rbx, [rsp+0E0h+arg_8]
0x1800c7fab  add     rsp, 0B0h
0x1800c7fb2  pop     r15
0x1800c7fb4  pop     r14
0x1800c7fb6  pop     r13
0x1800c7fb8  pop     r12
0x1800c7fba  pop     rdi
0x1800c7fbb  pop     rsi
0x1800c7fbc  pop     rbp
0x1800c7fbd  retn
0x1800c7fbe  mov     rax, [r13+0]
0x1800c7fc2  mov     rbx, [rax+20h]
0x1800c7fc6  xor     ecx, ecx; string
0x1800c7fc8  call    cs:__imp_WindowsDeleteString
0x1800c7fce  mov     [rbp+57h+var_B0], 0
0x1800c7fd6  lea     r8, [rbp+57h+var_B0]
0x1800c7fda  lea     rdx, ?PackageFullName@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TileStoreProperties::PackageFullName
0x1800c7fe1  mov     rcx, r13
0x1800c7fe4  mov     rax, rbx
0x1800c7fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c7fec  test    al, al
0x1800c7fee  jnz     short loc_1800C7FF6
0x1800c7ff0  mov     rcx, [rbp+57h+var_B0]
0x1800c7ff4  jmp     short loc_1800C7F8C
0x1800c7ff6  mov     [rbp+57h+var_80], 0
0x1800c7ffe  mov     rbx, [rbp+5Fh]
0x1800c8002  mov     rax, [r13+0]
0x1800c8006  lea     r9, [rbp+57h+var_80]
0x1800c800a  mov     r8d, 8
0x1800c8010  lea     rdx, ?TileRevision@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@_K@2@B; DataStoreCache::DataStoreProperty<unsigned __int64> const DataStoreCache::TileStoreProperties::TileRevision
0x1800c8017  mov     rcx, r13
0x1800c801a  mov     rax, [rax+18h]
0x1800c801e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8023  test    al, al
0x1800c8025  jz      loc_1800C8138
0x1800c802b  mov     r15, r14
0x1800c802e  mov     r13, [rbp+57h+arg_18]
0x1800c8032  mov     rcx, [rdi+1B8h]
0x1800c8039  mov     rax, [rcx]
0x1800c803c  mov     r8, [r15]
0x1800c803f  lea     rdx, [rbp+57h+var_98]
0x1800c8043  mov     rax, [rax+28h]
0x1800c8047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c804c  nop
0x1800c804d  mov     [rbp+57h+var_A0], 0
0x1800c8055  mov     rdi, [rbp+57h+var_98]
0x1800c8059  mov     rax, [rdi]
0x1800c805c  mov     rbx, [rax+30h]
0x1800c8060  lea     rcx, [rbp+57h+var_A0]
0x1800c8064  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIUnifiedTilePrivate@Private@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::Private::IUnifiedTilePrivate>>)
0x1800c8069  mov     r9, rax
0x1800c806c  lea     r8, _GUID_9dbb8733_cc6a_4eba_92cc_25fc80f0c2cb
0x1800c8073  lea     rdx, c_tileStoreTransformerId
0x1800c807a  mov     rcx, rdi
0x1800c807d  mov     rax, rbx
0x1800c8080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8085  test    al, al
0x1800c8087  jz      short loc_1800C80E6
0x1800c8089  mov     [rbp+57h+string], 0
0x1800c8091  mov     rdi, [rbp+57h+var_A0]
0x1800c8095  mov     rax, [rdi]
0x1800c8098  mov     rbx, [rax+20h]
0x1800c809c  xor     ecx, ecx; string
0x1800c809e  call    cs:__imp_WindowsDeleteString
0x1800c80a4  mov     [rbp+57h+string], 0
0x1800c80ac  lea     r8, [rbp+57h+string]
0x1800c80b0  lea     rdx, ?PackageFullName@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; DataStoreCache::DataStoreProperty<HSTRING__ *> const DataStoreCache::TileStoreProperties::PackageFullName
0x1800c80b7  mov     rcx, rdi
0x1800c80ba  mov     rax, rbx
0x1800c80bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c80c2  test    al, al
0x1800c80c4  jz      short loc_1800C80DB
0x1800c80c6  mov     rdx, [rbp+57h+string]; HSTRING
0x1800c80ca  mov     rcx, [rbp+57h+var_B0]; this
0x1800c80ce  call    ?AreStringsEqual@DataStoreCache@@YA_NPEAUHSTRING__@@0_N@Z; DataStoreCache::AreStringsEqual(HSTRING__ *,HSTRING__ *,bool)
0x1800c80d3  test    al, al
0x1800c80d5  jz      loc_1800C830F
0x1800c80db  mov     rcx, [rbp+57h+string]; string
0x1800c80df  call    cs:__imp_WindowsDeleteString
0x1800c80e5  nop
0x1800c80e6  mov     rcx, [rbp+57h+var_A0]
0x1800c80ea  test    rcx, rcx
0x1800c80ed  jz      short loc_1800C8104
0x1800c80ef  mov     [rbp+57h+var_A0], 0
0x1800c80f7  mov     rax, [rcx]
0x1800c80fa  mov     rax, [rax+10h]
0x1800c80fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8103  nop
0x1800c8104  mov     rcx, [rbp+57h+var_98]
0x1800c8108  test    rcx, rcx
0x1800c810b  jz      short loc_1800C8122
0x1800c810d  mov     [rbp+57h+var_98], 0
0x1800c8115  mov     rax, [rcx]
0x1800c8118  mov     rax, [rax+10h]
0x1800c811c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8121  nop
0x1800c8122  add     r15, 8
0x1800c8126  cmp     r15, r12
0x1800c8129  jz      loc_1800C7FF0
0x1800c812f  mov     rdi, [rbp+57h+arg_0]
0x1800c8133  jmp     loc_1800C8032
0x1800c8138  mov     r9d, 80070490h; char *
0x1800c813e  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x1800c8145  mov     edx, 885h; void *
0x1800c814a  mov     rcx, rbx; this
0x1800c814d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c8153  mov     rcx, [rbp+57h+var_90]
0x1800c8157  mov     rax, [rcx]
0x1800c815a  lea     rdx, [rbp+57h+var_50]
0x1800c815e  mov     rax, [rax+18h]
0x1800c8162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8167  mov     rdx, rax
0x1800c816a  lea     rcx, [rbp+57h+var_A8]
0x1800c816e  call    ??4?$ComPtr@VPropertyBagLookaside@DataStoreCache@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<DataStoreCache::PropertyBagLookaside>::operator=(Microsoft::WRL::ComPtr<DataStoreCache::PropertyBagLookaside> &&)
0x1800c8173  mov     rcx, [rbp+57h+var_50]
0x1800c8177  test    rcx, rcx
0x1800c817a  jz      short loc_1800C8189
0x1800c817c  mov     [rbp+57h+var_50], 0
0x1800c8184  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDataStorePropertyBag@DataStoreCache@@UIPropertyBagLookasidePrivate@5@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(void)
0x1800c8189  mov     rbx, [rbp+57h+var_A8]
0x1800c818d  mov     rdi, [rbp+57h+arg_0]
0x1800c8191  lea     r8, [rbp+57h+var_80]
0x1800c8195  mov     rcx, rbx
0x1800c8198  call    ??$SetLookasideValueType@_J@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@1@AEB_J@Z; DataStoreCache::PropertyBagLookaside::SetLookasideValueType<__int64>(DataStoreCache::DataStorePropertyIdentifier const &,__int64 const &)
0x1800c819d  mov     r8, [rbp+57h+var_B0]; HSTRING
0x1800c81a1  lea     rdx, ?PackageFullName@TileStoreProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; struct DataStoreCache::DataStorePropertyIdentifier *
0x1800c81a8  mov     rcx, rbx; this
0x1800c81ab  call    ?SetLookasideHSTRING@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(DataStoreCache::DataStorePropertyIdentifier const &,HSTRING__ *)
0x1800c81b0  mov     rcx, [rdi+1C8h]
0x1800c81b7  test    rcx, rcx
0x1800c81ba  jnz     loc_1800C8356
0x1800c81c0  mov     [rbp+57h+var_78], 0
0x1800c81c8  lea     rdx, [rbp+57h+var_78]
0x1800c81cc  lea     rcx, [rbp+57h+var_98]
0x1800c81d0  call    ??$As@UIDataUpdate@DataStoreCache@@@?$ComPtr@UIDataItem@DataStoreCache@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIDataUpdate@DataStoreCache@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<DataStoreCache::IDataItem>::As<DataStoreCache::IDataUpdate>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<DataStoreCache::IDataUpdate>>)
0x1800c81d5  mov     rcx, [rbp+5Fh]; this
0x1800c81d9  test    eax, eax
0x1800c81db  js      short loc_1800C8251
0x1800c81dd  mov     rcx, [rbp+57h+var_78]
0x1800c81e1  mov     r8, [rcx]
0x1800c81e4  mov     rax, rbx
0x1800c81e7  lea     rdx, [rbx+8]
0x1800c81eb  neg     rax
0x1800c81ee  sbb     r9, r9
0x1800c81f1  and     r9, rdx
0x1800c81f4  mov     rax, [r8+18h]
0x1800c81f8  xor     r8d, r8d
0x1800c81fb  lea     rdx, c_tileStoreTransformerId
0x1800c8202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8207  xor     edx, edx; length
0x1800c8209  mov     rcx, [r15]; string
0x1800c820c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c8212  mov     [rbp+57h+var_A8], rax
0x1800c8216  lea     r8, [rbp+57h+var_80]
0x1800c821a  lea     rdx, [rbp+57h+var_A8]
0x1800c821e  mov     rcx, r13
0x1800c8221  call    ??$SecondaryTileUpdatedForPrimaryTileChange@PEBGAEA_J@TileStoreTransformerReconcileTiles@DataStoreTransformerTelemetry@@QEAAX$$QEAPEBGAEA_J@Z; DataStoreTransformerTelemetry::TileStoreTransformerReconcileTiles::SecondaryTileUpdatedForPrimaryTileChange<ushort const *,__int64 &>(ushort const * &&,__int64 &)
0x1800c8226  nop
0x1800c8227  lea     rcx, [rbp+57h+var_78]
0x1800c822b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c8230  nop
0x1800c8231  lea     rcx, [rbp+57h+var_90]
0x1800c8235  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c823a  nop
0x1800c823b  test    rbx, rbx
0x1800c823e  jz      loc_1800C80DB
0x1800c8244  mov     rcx, rbx
0x1800c8247  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDataStorePropertyBag@DataStoreCache@@UIPropertyBagLookasidePrivate@5@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(void)
0x1800c824c  jmp     loc_1800C80DB
0x1800c8251  mov     r9d, eax; char *
0x1800c8254  lea     r8, aShellcommonShe_151; "shellcommon\\shell\\datastorecache\\tra"...
0x1800c825b  mov     edx, 8B3h; void *
0x1800c8260  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800c8266  mov     rdi, [rbp+57h+arg_0]
0x1800c826a  lea     r8, [rdi+80h]
0x1800c8271  lea     rdx, c_tileStoreTransformerId
0x1800c8278  lea     rcx, [rbp+57h+var_70]
0x1800c827c  call    ??$MakeOrThrow@VPropertyBagLookaside@DataStoreCache@@AEBU_GUID@@AEAV?$vector@PEBUDataStorePropertyIdentifier@DataStoreCache@@V?$allocator@PEBUDataStorePropertyIdentifier@DataStoreCache@@@std@@@std@@@wil@@YA?AV?$ComPtr@VPropertyBagLookaside@DataStoreCache@@@WRL@Microsoft@@AEBU_GUID@@AEAV?$vector@PEBUDataStorePropertyIdentifier@DataStoreCache@@V?$allocator@PEBUDataStorePropertyIdentifier@DataStoreCache@@@std@@@std@@@Z; wil::MakeOrThrow<DataStoreCache::PropertyBagLookaside,_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &>(_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &)
0x1800c8281  mov     rdx, rax
0x1800c8284  lea     rcx, [rbp+57h+var_A8]
0x1800c8288  call    ??4?$ComPtr@VPropertyBagLookaside@DataStoreCache@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<DataStoreCache::PropertyBagLookaside>::operator=(Microsoft::WRL::ComPtr<DataStoreCache::PropertyBagLookaside> &&)
0x1800c828d  mov     rcx, [rbp+57h+var_70]
0x1800c8291  test    rcx, rcx
0x1800c8294  jz      short loc_1800C82A3
0x1800c8296  mov     [rbp+57h+var_70], 0
0x1800c829e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDataStorePropertyBag@DataStoreCache@@UIPropertyBagLookasidePrivate@5@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(void)
0x1800c82a3  mov     rdx, [rbp+57h+var_A0]; struct DataStoreCache::IDataStorePropertyBag *
0x1800c82a7  mov     rbx, [rbp+57h+var_A8]
0x1800c82ab  mov     rcx, rbx; this
0x1800c82ae  call    ?SetCachedPropertyBag@PropertyBagLookaside@DataStoreCache@@QEAAXPEAUIDataStorePropertyBag@2@@Z; DataStoreCache::PropertyBagLookaside::SetCachedPropertyBag(DataStoreCache::IDataStorePropertyBag *)
0x1800c82b3  jmp     loc_1800C8191
0x1800c82b8  mov     rdx, [rbp+57h+var_60]
0x1800c82bc  mov     rcx, rdi; this
0x1800c82bf  call    ??$_Destroy_range@V?$allocator@VDataItemIdentifier@DataStoreCache@@@std@@@std@@YAXPEAVDataItemIdentifier@DataStoreCache@@QEAV12@AEAV?$allocator@VDataItemIdentifier@DataStoreCache@@@0@@Z; std::_Destroy_range<std::allocator<DataStoreCache::DataItemIdentifier>>(DataStoreCache::DataItemIdentifier *,DataStoreCache::DataItemIdentifier * const,std::allocator<DataStoreCache::DataItemIdentifier> &)
0x1800c82c4  mov     rdx, [rbp+57h+var_58]
0x1800c82c8  sub     rdx, rdi
0x1800c82cb  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800c82cf  mov     rcx, rdi
0x1800c82d2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c82d7  jmp     loc_1800C7F34
0x1800c82dc  mov     rsi, [rbp+57h+var_58]
0x1800c82e0  mov     r12, [rbp+57h+var_60]
0x1800c82e4  mov     r14, [rbp+57h+var_68]
0x1800c82e8  jmp     loc_1800C7F66
0x1800c82ed  mov     rdx, [rbp+57h+var_40]
0x1800c82f1  call    ??$_Destroy_range@V?$allocator@VDataItemIdentifier@DataStoreCache@@@std@@@std@@YAXPEAVDataItemIdentifier@DataStoreCache@@QEAV12@AEAV?$allocator@VDataItemIdentifier@DataStoreCache@@@0@@Z; std::_Destroy_range<std::allocator<DataStoreCache::DataItemIdentifier>>(DataStoreCache::DataItemIdentifier *,DataStoreCache::DataItemIdentifier * const,std::allocator<DataStoreCache::DataItemIdentifier> &)
0x1800c82f6  mov     rcx, [rbp+57h+var_48]
0x1800c82fa  mov     rdx, [rbp+57h+var_38]
0x1800c82fe  sub     rdx, rcx
0x1800c8301  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1800c8305  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800c830a  jmp     loc_1800C7F73
0x1800c830f  mov     [rbp+57h+var_A8], 0
0x1800c8317  mov     [rbp+57h+var_90], 0
0x1800c831f  mov     rbx, [rbp+57h+var_A0]
0x1800c8323  mov     rax, [rbx]
0x1800c8326  mov     rdi, [rax]
0x1800c8329  lea     rcx, [rbp+57h+var_90]
0x1800c832d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c8332  lea     r8, [rbp+57h+var_90]
0x1800c8336  lea     rdx, _GUID_58e38d18_77ad_494b_be1a_9ce327d10b5c
0x1800c833d  mov     rcx, rbx
0x1800c8340  mov     rax, rdi
0x1800c8343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8348  nop
0x1800c8349  test    eax, eax
0x1800c834b  js      loc_1800C8266
0x1800c8351  jmp     loc_1800C8153
0x1800c8356  mov     rax, [rcx]
0x1800c8359  mov     r9, [rbp+57h+var_B0]
0x1800c835d  mov     r8d, 1
0x1800c8363  mov     rdx, [rbp+57h+var_98]
0x1800c8367  mov     rax, [rax+30h]
0x1800c836b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8370  jmp     loc_1800C81C0
0x1800c8375  mov     rdx, r12
0x1800c8378  mov     rcx, r14; this
0x1800c837b  call    ??$_Destroy_range@V?$allocator@VDataItemIdentifier@DataStoreCache@@@std@@@std@@YAXPEAVDataItemIdentifier@DataStoreCache@@QEAV12@AEAV?$allocator@VDataItemIdentifier@DataStoreCache@@@0@@Z; std::_Destroy_range<std::allocator<DataStoreCache::DataItemIdentifier>>(DataStoreCache::DataItemIdentifier *,DataStoreCache::DataItemIdentifier * const,std::allocator<DataStoreCache::DataItemIdentifier> &)
0x1800c8380  sub     rsi, r14
0x1800c8383  and     rsi, 0FFFFFFFFFFFFFFF8h
0x1800c8387  mov     rdx, rsi
  ... truncated ...
```
