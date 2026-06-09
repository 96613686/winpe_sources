# DataStoreCache::TargetedContentTransformer::CreatePlaceholderTile(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)

- ea: `0x18006f4ac`
- end: `0x18006f9b7`
- name: `?CreatePlaceholderTile@TargetedContentTransformer@DataStoreCache@@AEAAXPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z`
- size: `1291`
- prototype: `void __fastcall(DataStoreCache::TargetedContentTransformer *__hidden this, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180379330`

## callees

- `0x1800131dc`
- `0x180013b80`
- `0x180014650`
- `0x18001dac0`
- `0x18006f4ac`
- `0x18006f9c0`
- `0x18006f9e4`
- `0x18006fd68`
- `0x18006ff48`
- `0x180201e50`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f85f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f939`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f94c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f977`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f98a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f99d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f9b0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f85f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f939`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f94c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f977`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f98a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f99d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006f9b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f5cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f7ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f888`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f5cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f791`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f7ce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f80b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f888`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f8c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006f906`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f74e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006f74e`

## string_xrefs

- `0x18006f841`: `shellcommon\shell\DataStoreCache\inc\DataStoreCacheItemIdentifier.h`
- `0x18006f5c8`: `ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png`
- `0x18006f78a`: `ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png`
- `0x18006f7c7`: `ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png`
- `0x18006f804`: `ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png`
- `0x18006f881`: `ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png`
- `0x18006f8ff`: `ms-resource:///PreInstalledApps_PlaceholderTile/notification_text`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall DataStoreCache::TargetedContentTransformer::CreatePlaceholderTile(
        DataStoreCache::TargetedContentTransformer *this,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *a2)
{
  __int64 (__fastcall *v4)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, HSTRING *); // rbx
  int v5; // eax
  __int64 v6; // rax
  DataStoreCache::PropertyBagLookaside **v7; // rax
  DataStoreCache::PropertyBagLookaside *v8; // rsi
  __int64 v9; // rdi
  __int64 i; // rbx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  HRESULT v17; // eax
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  _GUID **v22; // rdx
  __int64 *v23; // rax
  __int64 v24; // r14
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rdi
  void (__fastcall *v28)(__int64, __int64, _QWORD, unsigned __int64); // rbx
  __int64 v29; // rax
  HRESULT v30; // eax
  HRESULT v31; // eax
  HRESULT v32; // eax
  HRESULT v33; // eax
  HRESULT v34; // eax
  HRESULT v35; // eax
  int v36; // [rsp+20h] [rbp-49h]
  char v37[8]; // [rsp+30h] [rbp-39h] BYREF
  HSTRING v38; // [rsp+38h] [rbp-31h] BYREF
  __int64 v39; // [rsp+40h] [rbp-29h] BYREF
  HSTRING v40; // [rsp+48h] [rbp-21h] BYREF
  __int64 v41; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v42[2]; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  HSTRING string; // [rsp+80h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  DataStoreCache::TargetedContentTransformer::GetContentDeliveryManagerPackageFullName(this, &v40);
  v38 = 0;
  v4 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, HSTRING *))(*(_QWORD *)a2 + 56LL);
  WindowsDeleteString(0);
  v38 = 0;
  v5 = v4(a2, &v38);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"shellcommon\\shell\\DataStoreCache\\inc\\DataStoreCacheItemIdentifier.h",
      (const char *)(unsigned int)v5,
      v36);
  v6 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 3) + 48LL))((char *)this + 24);
  v7 = (DataStoreCache::PropertyBagLookaside **)wil::MakeOrThrow<DataStoreCache::PropertyBagLookaside,_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &>(
                                                  &v39,
                                                  v6,
                                                  (char *)this + 104);
  v8 = *v7;
  *v7 = 0;
  v42[1] = v8;
  if ( v39 )
  {
    v39 = 0;
    ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release)();
  }
  v9 = *((_QWORD *)this + 13);
  for ( i = *((_QWORD *)this + 14); v9 != i; v9 += 8 )
  {
    v11 = *(_DWORD *)(*(_QWORD *)v9 + 8LL);
    if ( v11 > 13 )
    {
      v18 = v11 - 14;
      if ( !v18 )
      {
        string = 0;
        v33 = WindowsCreateStringReference(
                L"ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png",
                0x42u,
                &hstringHeader,
                &string);
        if ( v33 < 0 )
        {
          RaiseException(v33, 1u, 0, 0);
          __debugbreak();
        }
        DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
          v8,
          (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TargetedContentProperties::LargeTileLogo,
          string);
        continue;
      }
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            if ( v21 == 1 )
              DataStoreCache::PropertyBagLookaside::SetLookasideValueType<unsigned __int64>(
                v8,
                &DataStoreCache::TargetedContentProperties::LogoHashId,
                &qword_180408D68);
            continue;
          }
          v22 = &DataStoreCache::TargetedContentProperties::ShowNameOnLargeTile;
        }
        else
        {
          v22 = &DataStoreCache::TargetedContentProperties::ShowNameOnWideTile;
        }
      }
      else
      {
        v22 = &DataStoreCache::TargetedContentProperties::ShowNameOnMediumTile;
      }
      v37[0] = 0;
      DataStoreCache::PropertyBagLookaside::SetLookasideValueType<bool>(v8, v22, v37);
    }
    else if ( v11 == 13 )
    {
      string = 0;
      v30 = WindowsCreateStringReference(
              L"ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png",
              0x42u,
              &hstringHeader,
              &string);
      if ( v30 < 0 )
      {
        RaiseException(v30, 1u, 0, 0);
        __debugbreak();
      }
      DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
        v8,
        (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TargetedContentProperties::WideTileLogo,
        string);
    }
    else
    {
      v12 = v11 - 2;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 3;
          if ( v14 )
          {
            v15 = v14 - 3;
            if ( v15 )
            {
              v16 = v15 - 2;
              if ( v16 )
              {
                if ( v16 == 1 )
                {
                  string = 0;
                  v17 = WindowsCreateStringReference(
                          L"ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png",
                          0x42u,
                          &hstringHeader,
                          &string);
                  if ( v17 < 0 )
                  {
                    RaiseException(v17, 1u, 0, 0);
                    __debugbreak();
                  }
                  DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
                    v8,
                    (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TargetedContentProperties::MediumTileLogo,
                    string);
                }
              }
              else
              {
                string = 0;
                v32 = WindowsCreateStringReference(
                        L"ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png",
                        0x42u,
                        &hstringHeader,
                        &string);
                if ( v32 < 0 )
                {
                  RaiseException(v32, 1u, 0, 0);
                  __debugbreak();
                }
                DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
                  v8,
                  (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TargetedContentProperties::TinyTileLogo,
                  string);
              }
            }
            else
            {
              string = 0;
              v31 = WindowsCreateStringReference(
                      L"ms-appx:///Experiences/PreInstalledApps/DefaultSquareTileLogo1.png",
                      0x42u,
                      &hstringHeader,
                      &string);
              if ( v31 < 0 )
              {
                RaiseException(v31, 1u, 0, 0);
                __debugbreak();
              }
              DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
                v8,
                (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TargetedContentProperties::AppListIcon,
                string);
            }
          }
          else
          {
            string = 0;
            v35 = WindowsCreateStringReference(
                    L"ms-resource:///PreInstalledApps_PlaceholderTile/notification_text",
                    0x41u,
                    &hstringHeader,
                    &string);
            if ( v35 < 0 )
            {
              RaiseException(v35, 1u, 0, 0);
              JUMPOUT(0x18006F9B6LL);
            }
            DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
              v8,
              (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TargetedContentProperties::DisplayName,
              string);
          }
        }
        else
        {
          DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
            v8,
            (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TargetedContentProperties::PackageFullName,
            v40);
        }
      }
      else
      {
        string = 0;
        v34 = WindowsCreateStringReference(
                L"Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy",
                0x36u,
                &hstringHeader,
                &string);
        if ( v34 < 0 )
        {
          RaiseException(v34, 1u, 0, 0);
          __debugbreak();
        }
        DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(
          v8,
          (const struct DataStoreCache::DataStorePropertyIdentifier *)&DataStoreCache::TargetedContentProperties::PackageFamilyName,
          string);
      }
    }
  }
  v23 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *, HSTRING))(**((_QWORD **)this + 19) + 40LL))(
                     *((_QWORD *)this + 19),
                     &v41,
                     v38);
  v24 = *v23;
  *v23 = 0;
  v39 = v24;
  v25 = v41;
  if ( v41 )
  {
    v41 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  v26 = *((_QWORD *)this + 31);
  if ( v26 )
    (*(void (__fastcall **)(__int64, __int64, __int64, HSTRING))(*(_QWORD *)v26 + 48LL))(v26, v24, 1, v40);
  wil::com_ptr_t<DataStoreCache::IDataItem,wil::err_exception_policy>::query<DataStoreCache::IDataUpdate>(&v39, v42);
  v27 = v42[0];
  v28 = *(void (__fastcall **)(__int64, __int64, _QWORD, unsigned __int64))(*(_QWORD *)v42[0] + 24LL);
  v29 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 3) + 48LL))((char *)this + 24);
  v28(v27, v29, 0, ((unsigned __int64)v8 + 8) & -(__int64)(v8 != 0));
  if ( v42[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v42[0] + 16LL))(v42[0]);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( v8 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(v8);
  WindowsDeleteString(v38);
  v38 = 0;
  WindowsDeleteString(v40);
}

```

## disassembly

```asm
0x18006f4ac  mov     [rsp-8+arg_10], rbx
0x18006f4b1  push    rbp
0x18006f4b2  push    rsi
0x18006f4b3  push    rdi
0x18006f4b4  push    r12
0x18006f4b6  push    r13
0x18006f4b8  push    r14
0x18006f4ba  push    r15
0x18006f4bc  lea     rbp, [rsp-27h]
0x18006f4c1  sub     rsp, 90h
0x18006f4c8  mov     rax, cs:__security_cookie
0x18006f4cf  xor     rax, rsp
0x18006f4d2  mov     [rbp+57h+var_38], rax
0x18006f4d6  mov     rdi, rdx
0x18006f4d9  mov     r15, rcx
0x18006f4dc  xor     r13d, r13d
0x18006f4df  lea     rdx, [rbp+57h+var_78]
0x18006f4e3  call    ?GetContentDeliveryManagerPackageFullName@TargetedContentTransformer@DataStoreCache@@AEAA?AVHString@Wrappers@WRL@Microsoft@@XZ; DataStoreCache::TargetedContentTransformer::GetContentDeliveryManagerPackageFullName(void)
0x18006f4e8  nop
0x18006f4e9  mov     [rbp+57h+var_88], r13
0x18006f4ed  mov     rax, [rdi]
0x18006f4f0  mov     rbx, [rax+38h]
0x18006f4f4  xor     ecx, ecx; string
0x18006f4f6  call    cs:__imp_WindowsDeleteString
0x18006f4fc  mov     [rbp+57h+var_88], r13
0x18006f500  lea     rdx, [rbp+57h+var_88]
0x18006f504  mov     rcx, rdi
0x18006f507  mov     rax, rbx
0x18006f50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f50f  mov     rcx, [rbp+5Fh]; this
0x18006f513  test    eax, eax
0x18006f515  js      loc_18006F83E
0x18006f51b  lea     r12, [r15+18h]
0x18006f51f  mov     rax, [r12]
0x18006f523  mov     rcx, r12
0x18006f526  mov     rax, [rax+30h]
0x18006f52a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f52f  mov     rdx, rax
0x18006f532  lea     r8, [r15+68h]
0x18006f536  lea     rcx, [rbp+57h+var_80]
0x18006f53a  call    ??$MakeOrThrow@VPropertyBagLookaside@DataStoreCache@@AEBU_GUID@@AEAV?$vector@PEBUDataStorePropertyIdentifier@DataStoreCache@@V?$allocator@PEBUDataStorePropertyIdentifier@DataStoreCache@@@std@@@std@@@wil@@YA?AV?$ComPtr@VPropertyBagLookaside@DataStoreCache@@@WRL@Microsoft@@AEBU_GUID@@AEAV?$vector@PEBUDataStorePropertyIdentifier@DataStoreCache@@V?$allocator@PEBUDataStorePropertyIdentifier@DataStoreCache@@@std@@@std@@@Z; wil::MakeOrThrow<DataStoreCache::PropertyBagLookaside,_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &>(_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &)
0x18006f53f  mov     rsi, [rax]
0x18006f542  mov     [rax], r13
0x18006f545  mov     [rbp+57h+var_60], rsi
0x18006f549  mov     rcx, [rbp+57h+var_80]
0x18006f54d  test    rcx, rcx
0x18006f550  jz      short loc_18006F55B
0x18006f552  mov     [rbp+57h+var_80], r13
0x18006f556  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDataStorePropertyBag@DataStoreCache@@UIPropertyBagLookasidePrivate@5@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(void)
0x18006f55b  mov     rdi, [r15+68h]
0x18006f55f  mov     rbx, [r15+70h]
0x18006f563  cmp     rdi, rbx
0x18006f566  jz      loc_18006F654
0x18006f56c  mov     r14d, 42h ; 'B'
0x18006f572  mov     rax, [rdi]
0x18006f575  mov     ecx, [rax+8]
0x18006f578  cmp     ecx, 0Dh
0x18006f57b  jg      short loc_18006F5F3
0x18006f57d  jz      loc_18006F77B
0x18006f583  sub     ecx, 2
0x18006f586  jz      loc_18006F8AF
0x18006f58c  sub     ecx, 1
0x18006f58f  jz      loc_18006F953
0x18006f595  sub     ecx, 3
0x18006f598  jz      loc_18006F8EE
0x18006f59e  sub     ecx, 3
0x18006f5a1  jz      loc_18006F7B8
0x18006f5a7  sub     ecx, 2
0x18006f5aa  jz      loc_18006F7F5
0x18006f5b0  cmp     ecx, 1
0x18006f5b3  jnz     loc_18006F647
0x18006f5b9  mov     [rbp+57h+string], r13
0x18006f5bd  lea     r9, [rbp+57h+string]; string
0x18006f5c1  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006f5c5  mov     edx, r14d; length
0x18006f5c8  lea     rcx, ?c_tileMediumUri@PlaceholderTile@TargetedContent@CreativeFramework@@3QBGB; "ms-appx:///Experiences/PreInstalledApps"...
0x18006f5cf  call    cs:__imp_WindowsCreateStringReference
0x18006f5d5  test    eax, eax
0x18006f5d7  js      loc_18006F92D
0x18006f5dd  mov     r8, [rbp+57h+string]; HSTRING
0x18006f5e1  lea     rdx, ?MediumTileLogo@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; struct DataStoreCache::DataStorePropertyIdentifier *
0x18006f5e8  mov     rcx, rsi; this
0x18006f5eb  call    ?SetLookasideHSTRING@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(DataStoreCache::DataStorePropertyIdentifier const &,HSTRING__ *)
0x18006f5f0  nop
0x18006f5f1  jmp     short loc_18006F647
0x18006f5f3  sub     ecx, 0Eh
0x18006f5f6  jz      loc_18006F872
0x18006f5fc  sub     ecx, 1
0x18006f5ff  jz      short loc_18006F630
0x18006f601  sub     ecx, 1
0x18006f604  jz      loc_18006F832
0x18006f60a  sub     ecx, 1
0x18006f60d  jz      loc_18006F866
0x18006f613  cmp     ecx, 1
0x18006f616  jnz     short loc_18006F647
0x18006f618  lea     r8, qword_180408D68
0x18006f61f  lea     rdx, ?LogoHashId@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@_K@2@B; DataStoreCache::DataStoreProperty<unsigned __int64> const DataStoreCache::TargetedContentProperties::LogoHashId
0x18006f626  mov     rcx, rsi
0x18006f629  call    ??$SetLookasideValueType@_K@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@1@AEB_K@Z; DataStoreCache::PropertyBagLookaside::SetLookasideValueType<unsigned __int64>(DataStoreCache::DataStorePropertyIdentifier const &,unsigned __int64 const &)
0x18006f62e  jmp     short loc_18006F647
0x18006f630  lea     rdx, ?ShowNameOnMediumTile@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@_N@2@B; DataStoreCache::DataStoreProperty<bool> const DataStoreCache::TargetedContentProperties::ShowNameOnMediumTile
0x18006f637  mov     [rbp+57h+var_90], r13b
0x18006f63b  lea     r8, [rbp+57h+var_90]
0x18006f63f  mov     rcx, rsi
0x18006f642  call    ??$SetLookasideValueType@_N@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@1@AEB_N@Z; DataStoreCache::PropertyBagLookaside::SetLookasideValueType<bool>(DataStoreCache::DataStorePropertyIdentifier const &,bool const &)
0x18006f647  add     rdi, 8
0x18006f64b  cmp     rdi, rbx
0x18006f64e  jnz     loc_18006F572
0x18006f654  mov     rcx, [r15+98h]
0x18006f65b  mov     rax, [rcx]
0x18006f65e  mov     r8, [rbp+57h+var_88]
0x18006f662  lea     rdx, [rbp+57h+var_70]
0x18006f666  mov     rax, [rax+28h]
0x18006f66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f66f  mov     r14, [rax]
0x18006f672  mov     [rax], r13
0x18006f675  mov     [rbp+57h+var_80], r14
0x18006f679  mov     rcx, [rbp+57h+var_70]
0x18006f67d  test    rcx, rcx
0x18006f680  jz      short loc_18006F693
0x18006f682  mov     [rbp+57h+var_70], r13
0x18006f686  mov     rax, [rcx]
0x18006f689  mov     rax, [rax+10h]
0x18006f68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f692  nop
0x18006f693  mov     rcx, [r15+0F8h]
0x18006f69a  test    rcx, rcx
0x18006f69d  jz      short loc_18006F6B8
0x18006f69f  mov     rax, [rcx]
0x18006f6a2  mov     r9, [rbp+57h+var_78]
0x18006f6a6  mov     r8d, 1
0x18006f6ac  mov     rdx, r14
0x18006f6af  mov     rax, [rax+30h]
0x18006f6b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6b8  lea     rdx, [rbp+57h+var_68]
0x18006f6bc  lea     rcx, [rbp+57h+var_80]
0x18006f6c0  call    ??$query@UIDataUpdate@DataStoreCache@@@?$com_ptr_t@UIDataItem@DataStoreCache@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIDataUpdate@DataStoreCache@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<DataStoreCache::IDataItem,wil::err_exception_policy>::query<DataStoreCache::IDataUpdate>(void)
0x18006f6c5  nop
0x18006f6c6  mov     rdi, [rbp+57h+var_68]
0x18006f6ca  mov     rax, [rdi]
0x18006f6cd  mov     rbx, [rax+18h]
0x18006f6d1  mov     rax, [r12]
0x18006f6d5  mov     rcx, r12
0x18006f6d8  mov     rax, [rax+30h]
0x18006f6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f6e1  mov     rdx, rsi
0x18006f6e4  lea     r8, [rsi+8]
0x18006f6e8  neg     rdx
0x18006f6eb  sbb     r9, r9
0x18006f6ee  and     r9, r8
0x18006f6f1  xor     r8d, r8d
0x18006f6f4  mov     rdx, rax
0x18006f6f7  mov     rcx, rdi
0x18006f6fa  mov     rax, rbx
0x18006f6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f702  nop
0x18006f703  mov     rcx, [rbp+57h+var_68]
0x18006f707  test    rcx, rcx
0x18006f70a  jz      short loc_18006F719
0x18006f70c  mov     rax, [rcx]
0x18006f70f  mov     rax, [rax+10h]
0x18006f713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f718  nop
0x18006f719  test    r14, r14
0x18006f71c  jz      short loc_18006F72E
0x18006f71e  mov     rax, [r14]
0x18006f721  mov     rcx, r14
0x18006f724  mov     rax, [rax+10h]
0x18006f728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f72d  nop
0x18006f72e  test    rsi, rsi
0x18006f731  jz      short loc_18006F73C
0x18006f733  mov     rcx, rsi
0x18006f736  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDataStorePropertyBag@DataStoreCache@@UIPropertyBagLookasidePrivate@5@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(void)
0x18006f73b  nop
0x18006f73c  mov     rcx, [rbp+57h+var_88]; string
0x18006f740  call    cs:__imp_WindowsDeleteString
0x18006f746  mov     [rbp+57h+var_88], r13
0x18006f74a  mov     rcx, [rbp+57h+var_78]; string
0x18006f74e  call    cs:__imp_WindowsDeleteString
0x18006f754  mov     rcx, [rbp+57h+var_38]
0x18006f758  xor     rcx, rsp; StackCookie
0x18006f75b  call    __security_check_cookie
0x18006f760  mov     rbx, [rsp+0C0h+arg_10]
0x18006f768  add     rsp, 90h
0x18006f76f  pop     r15
0x18006f771  pop     r14
0x18006f773  pop     r13
0x18006f775  pop     r12
0x18006f777  pop     rdi
0x18006f778  pop     rsi
0x18006f779  pop     rbp
0x18006f77a  retn
0x18006f77b  mov     [rbp+57h+string], r13
0x18006f77f  lea     r9, [rbp+57h+string]; string
0x18006f783  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006f787  mov     edx, r14d; length
0x18006f78a  lea     rcx, ?c_tileMediumUri@PlaceholderTile@TargetedContent@CreativeFramework@@3QBGB; "ms-appx:///Experiences/PreInstalledApps"...
0x18006f791  call    cs:__imp_WindowsCreateStringReference
0x18006f797  test    eax, eax
0x18006f799  js      loc_18006F853
0x18006f79f  mov     r8, [rbp+57h+string]; HSTRING
0x18006f7a3  lea     rdx, ?WideTileLogo@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; struct DataStoreCache::DataStorePropertyIdentifier *
0x18006f7aa  mov     rcx, rsi; this
0x18006f7ad  call    ?SetLookasideHSTRING@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(DataStoreCache::DataStorePropertyIdentifier const &,HSTRING__ *)
0x18006f7b2  nop
0x18006f7b3  jmp     loc_18006F647
0x18006f7b8  mov     [rbp+57h+string], r13
0x18006f7bc  lea     r9, [rbp+57h+string]; string
0x18006f7c0  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006f7c4  mov     edx, r14d; length
0x18006f7c7  lea     rcx, ?c_tileMediumUri@PlaceholderTile@TargetedContent@CreativeFramework@@3QBGB; "ms-appx:///Experiences/PreInstalledApps"...
0x18006f7ce  call    cs:__imp_WindowsCreateStringReference
0x18006f7d4  test    eax, eax
0x18006f7d6  js      loc_18006F940
0x18006f7dc  mov     r8, [rbp+57h+string]; HSTRING
0x18006f7e0  lea     rdx, ?AppListIcon@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; struct DataStoreCache::DataStorePropertyIdentifier *
0x18006f7e7  mov     rcx, rsi; this
0x18006f7ea  call    ?SetLookasideHSTRING@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(DataStoreCache::DataStorePropertyIdentifier const &,HSTRING__ *)
0x18006f7ef  nop
0x18006f7f0  jmp     loc_18006F647
0x18006f7f5  mov     [rbp+57h+string], r13
0x18006f7f9  lea     r9, [rbp+57h+string]; string
0x18006f7fd  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006f801  mov     edx, r14d; length
0x18006f804  lea     rcx, ?c_tileMediumUri@PlaceholderTile@TargetedContent@CreativeFramework@@3QBGB; "ms-appx:///Experiences/PreInstalledApps"...
0x18006f80b  call    cs:__imp_WindowsCreateStringReference
0x18006f811  test    eax, eax
0x18006f813  js      loc_18006F96B
0x18006f819  mov     r8, [rbp+57h+string]; HSTRING
0x18006f81d  lea     rdx, ?TinyTileLogo@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; struct DataStoreCache::DataStorePropertyIdentifier *
0x18006f824  mov     rcx, rsi; this
0x18006f827  call    ?SetLookasideHSTRING@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(DataStoreCache::DataStorePropertyIdentifier const &,HSTRING__ *)
0x18006f82c  nop
0x18006f82d  jmp     loc_18006F647
0x18006f832  lea     rdx, ?ShowNameOnWideTile@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@_N@2@B; DataStoreCache::DataStoreProperty<bool> const DataStoreCache::TargetedContentProperties::ShowNameOnWideTile
0x18006f839  jmp     loc_18006F637
0x18006f83e  mov     r9d, eax; char *
0x18006f841  lea     r8, aShellcommonShe_92; "shellcommon\\shell\\DataStoreCache\\inc"...
0x18006f848  mov     edx, 80h; void *
0x18006f84d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006f853  xor     r9d, r9d; lpArguments
0x18006f856  xor     r8d, r8d; nNumberOfArguments
0x18006f859  lea     edx, [r9+1]; dwExceptionFlags
0x18006f85d  mov     ecx, eax; dwExceptionCode
0x18006f85f  call    cs:__imp_RaiseException
0x18006f865  int     3; Trap to Debugger
0x18006f866  lea     rdx, ?ShowNameOnLargeTile@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@_N@2@B; DataStoreCache::DataStoreProperty<bool> const DataStoreCache::TargetedContentProperties::ShowNameOnLargeTile
0x18006f86d  jmp     loc_18006F637
0x18006f872  mov     [rbp+57h+string], r13
0x18006f876  lea     r9, [rbp+57h+string]; string
0x18006f87a  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006f87e  mov     edx, r14d; length
0x18006f881  lea     rcx, ?c_tileMediumUri@PlaceholderTile@TargetedContent@CreativeFramework@@3QBGB; "ms-appx:///Experiences/PreInstalledApps"...
0x18006f888  call    cs:__imp_WindowsCreateStringReference
0x18006f88e  test    eax, eax
0x18006f890  js      loc_18006F97E
0x18006f896  mov     r8, [rbp+57h+string]; HSTRING
0x18006f89a  lea     rdx, ?LargeTileLogo@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; struct DataStoreCache::DataStorePropertyIdentifier *
0x18006f8a1  mov     rcx, rsi; this
0x18006f8a4  call    ?SetLookasideHSTRING@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(DataStoreCache::DataStorePropertyIdentifier const &,HSTRING__ *)
0x18006f8a9  nop
0x18006f8aa  jmp     loc_18006F647
0x18006f8af  mov     [rbp+57h+string], r13
0x18006f8b3  lea     r9, [rbp+57h+string]; string
0x18006f8b7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006f8bb  mov     edx, 36h ; '6'; length
0x18006f8c0  lea     rcx, ?c_ContentDeliveryManagerPackageFamilyName@Shared@CreativeFramework@@3QBGB; "Microsoft.Windows.ContentDeliveryManage"...
0x18006f8c7  call    cs:__imp_WindowsCreateStringReference
0x18006f8cd  test    eax, eax
0x18006f8cf  js      loc_18006F991
0x18006f8d5  mov     r8, [rbp+57h+string]; HSTRING
0x18006f8d9  lea     rdx, ?PackageFamilyName@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; struct DataStoreCache::DataStorePropertyIdentifier *
0x18006f8e0  mov     rcx, rsi; this
0x18006f8e3  call    ?SetLookasideHSTRING@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(DataStoreCache::DataStorePropertyIdentifier const &,HSTRING__ *)
0x18006f8e8  nop
0x18006f8e9  jmp     loc_18006F647
0x18006f8ee  mov     [rbp+57h+string], r13
0x18006f8f2  lea     r9, [rbp+57h+string]; string
0x18006f8f6  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006f8fa  mov     edx, 41h ; 'A'; length
0x18006f8ff  lea     rcx, ?c_displayNameUri@PlaceholderTile@TargetedContent@CreativeFramework@@3QBGB; "ms-resource:///PreInstalledApps_Placeho"...
0x18006f906  call    cs:__imp_WindowsCreateStringReference
0x18006f90c  test    eax, eax
0x18006f90e  js      loc_18006F9A4
0x18006f914  mov     r8, [rbp+57h+string]; HSTRING
0x18006f918  lea     rdx, ?DisplayName@TargetedContentProperties@DataStoreCache@@3U?$DataStoreProperty@PEAUHSTRING__@@@2@B; struct DataStoreCache::DataStorePropertyIdentifier *
0x18006f91f  mov     rcx, rsi; this
0x18006f922  call    ?SetLookasideHSTRING@PropertyBagLookaside@DataStoreCache@@QEAAXAEBUDataStorePropertyIdentifier@2@PEAUHSTRING__@@@Z; DataStoreCache::PropertyBagLookaside::SetLookasideHSTRING(DataStoreCache::DataStorePropertyIdentifier const &,HSTRING__ *)
0x18006f927  nop
0x18006f928  jmp     loc_18006F647
0x18006f92d  xor     r9d, r9d; lpArguments
0x18006f930  xor     r8d, r8d; nNumberOfArguments
0x18006f933  lea     edx, [r9+1]; dwExceptionFlags
0x18006f937  mov     ecx, eax; dwExceptionCode
0x18006f939  call    cs:__imp_RaiseException
0x18006f93f  int     3; Trap to Debugger
0x18006f940  xor     r9d, r9d; lpArguments
0x18006f943  xor     r8d, r8d; nNumberOfArguments
0x18006f946  lea     edx, [r9+1]; dwExceptionFlags
  ... truncated ...
```
