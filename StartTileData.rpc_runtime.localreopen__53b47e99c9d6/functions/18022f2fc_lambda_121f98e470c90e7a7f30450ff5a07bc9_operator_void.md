# _lambda_121f98e470c90e7a7f30450ff5a07bc9_::operator()(void)

- ea: `0x18022f2fc`
- end: `0x18022f8c9`
- name: `??R_lambda_121f98e470c90e7a7f30450ff5a07bc9_@@QEBAJXZ`
- size: `1485`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18022f9e0`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x18002dde0`
- `0x18004a468`
- `0x18004ffc0`
- `0x180060178`
- `0x18008272c`
- `0x1800cdc84`
- `0x18017cee8`
- `0x18017e110`
- `0x180185e1c`
- `0x180201e50`
- `0x18022f2fc`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f4e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f60d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f69b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f6e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f6f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f4e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f516`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f60d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f650`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f670`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f69b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f6e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18022f6f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022f7c5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18022f7c5`

## string_xrefs

- `0x18022f35c`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f3b7`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f45f`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f4c4`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f59e`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f5d9`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f639`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f6cf`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f72e`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`
- `0x18022f824`: `shellcommon\shell\tiles\curatedtilecollections\collectioninitialization\lib\mfumodificationpostprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall _lambda_121f98e470c90e7a7f30450ff5a07bc9_::operator()(__int64 a1)
{
  int v2; // eax
  HRESULT v3; // ebx
  __int64 v4; // rcx
  int v5; // eax
  _QWORD *i; // rsi
  _QWORD *v7; // r14
  __int64 *TileIdentifier; // rax
  __int64 v9; // rcx
  const char *v10; // r9
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rbx
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, HSTRING *); // rbx
  int v22; // eax
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING, HSTRING *); // rbx
  int v25; // eax
  LPVOID v26; // rdi
  __int64 (__fastcall *v27)(LPVOID, GUID *, GUID *, __int64 *); // rbx
  int v28; // eax
  __int64 v29; // rdx
  int ppv; // [rsp+20h] [rbp-E8h]
  int ppva; // [rsp+20h] [rbp-E8h]
  __int64 v33; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v34; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v35; // [rsp+40h] [rbp-C8h] BYREF
  HSTRING v36; // [rsp+48h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING v38; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID v40; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+70h] [rbp-98h] BYREF
  __int64 v42; // [rsp+78h] [rbp-90h] BYREF
  HRESULT v43; // [rsp+80h] [rbp-88h] BYREF
  __int128 v44; // [rsp+88h] [rbp-80h] BYREF
  __int64 v45; // [rsp+98h] [rbp-70h]
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v47; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v44 = 0;
  v45 = 0;
  v2 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(**(_QWORD **)(*(_QWORD *)a1 + 16LL) + 104LL))(
         *(_QWORD *)(*(_QWORD *)a1 + 16LL),
         &v44);
  v3 = v2;
  if ( v2 >= 0 )
  {
    if ( (_QWORD)v44 != *((_QWORD *)&v44 + 1) )
    {
      v34 = 0;
      v33 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      v5 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
             v4,
             &v33);
      v3 = v5;
      if ( v5 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodificatio"
                        "npostprocessor.cpp",
          (const char *)(unsigned int)v5,
          ppv);
LABEL_6:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
        goto LABEL_47;
      }
      v7 = (_QWORD *)*((_QWORD *)&v44 + 1);
      for ( i = (_QWORD *)v44; i != v7; i += 2 )
      {
        v35 = 0;
        try
        {
          TileIdentifier = (__int64 *)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(
                                        *i,
                                        &v43);
          v9 = *TileIdentifier;
          *TileIdentifier = 0;
          v35 = v9;
          wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v43);
          v11 = *i;
        }
        catch ( ... )
        {
          v43 = wil::details::in1diag3::Return_CaughtException(
                  retaddr,
                  (void *)0x39,
                  (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumod"
                                "ificationpostprocessor.cpp",
                  v10);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          v3 = v43;
          goto LABEL_47;
        }
        if ( (unsigned int)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileType(v11) )
        {
          if ( (unsigned int)WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileType(*i) != 1 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x63,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodific"
                            "ationpostprocessor.cpp",
              (const char *)0x80070057LL,
              ppv);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
            v3 = -2147024809;
            goto LABEL_47;
          }
          if ( !v34 )
          {
            v17 = **(_QWORD **)(*(_QWORD *)a1 + 24LL);
            v47 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(
              &hstringHeader,
              L"WindowsInternal.Shell.UnifiedTile.CuratedTileCollections.CuratedCollectionInitializationStatics",
              0x60u,
              0x5Fu);
            v18 = Windows::Foundation::GetActivationFactoryAsUser<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedCollectionInitializationStatics>>(
                    v47,
                    v17,
                    &v34);
            v3 = v18;
            if ( v18 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x52,
                (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodif"
                              "icationpostprocessor.cpp",
                (const char *)(unsigned int)v18,
                ppv);
              goto LABEL_14;
            }
          }
          v39 = 0;
          v19 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(
                  &v35,
                  &v39);
          v3 = v19;
          if ( v19 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x57,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodific"
                            "ationpostprocessor.cpp",
              (const char *)(unsigned int)v19,
              ppv);
            goto LABEL_27;
          }
          v36 = 0;
          v20 = v39;
          v21 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v39 + 48LL);
          WindowsDeleteString(0);
          v36 = 0;
          v22 = v21(v20, &v36);
          v3 = v22;
          if ( v22 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5A,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodific"
                            "ationpostprocessor.cpp",
              (const char *)(unsigned int)v22,
              ppv);
            goto LABEL_30;
          }
          v38 = 0;
          v23 = v34;
          v24 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v34 + 104LL);
          WindowsDeleteString(0);
          v38 = 0;
          v3 = v24(v23, v36, &v38);
          if ( v3 < 0 )
            goto LABEL_32;
          v25 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v33 + 104LL))(v33, v38);
          v3 = v25;
          if ( v25 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x5E,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodific"
                            "ationpostprocessor.cpp",
              (const char *)(unsigned int)v25,
              ppv);
LABEL_32:
            WindowsDeleteString(v38);
            v38 = 0;
LABEL_30:
            WindowsDeleteString(v36);
            v36 = 0;
LABEL_27:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
LABEL_14:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
            goto LABEL_6;
          }
          WindowsDeleteString(v38);
          v38 = 0;
          WindowsDeleteString(v36);
          v36 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
        }
        else
        {
          v41 = 0;
          v12 = Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(
                  &v35,
                  &v41);
          v3 = v12;
          if ( v12 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3E,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodific"
                            "ationpostprocessor.cpp",
              (const char *)(unsigned int)v12,
              ppv);
            goto LABEL_13;
          }
          string = 0;
          v13 = v41;
          v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 48LL);
          WindowsDeleteString(0);
          string = 0;
          v15 = v14(v13, &string);
          v3 = v15;
          if ( v15 < 0 )
          {
            v16 = 65;
            goto LABEL_17;
          }
          v15 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v33 + 104LL))(v33, string);
          v3 = v15;
          if ( v15 < 0 )
          {
            v16 = 66;
LABEL_17:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v16,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodific"
                            "ationpostprocessor.cpp",
              (const char *)(unsigned int)v15,
              ppv);
            WindowsDeleteString(string);
            string = 0;
LABEL_13:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
            goto LABEL_14;
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      }
      v40 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      v3 = CoCreateInstance(
             &GUID_228826af_02e1_4226_a9e0_99a855e455a6,
             0,
             0x404u,
             &GUID_9767060c_9476_42e2_8f7b_2f10fd13765c,
             &v40);
      if ( v3 < 0 )
      {
LABEL_39:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
        goto LABEL_6;
      }
      v42 = 0;
      v26 = v40;
      v27 = *(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, __int64 *))(*(_QWORD *)v40 + 96LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      v28 = v27(v26, &GUID_e2923845_a1d4_49a0_84a6_419152538eb8, &GUID_99e01be7_d840_6dfb_694f_8814c2ec727e, &v42);
      v3 = v28;
      if ( v28 < 0 )
      {
        v29 = 108;
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v29,
          (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodificatio"
                        "npostprocessor.cpp",
          (const char *)(unsigned int)v28,
          ppva);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        goto LABEL_39;
      }
      v28 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v42 + 64LL))(v42, v33);
      v3 = v28;
      if ( v28 < 0 )
      {
        v29 = 109;
        goto LABEL_42;
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    }
    v3 = 0;
    goto LABEL_47;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2B,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\collectioninitialization\\lib\\mfumodificationpostprocessor.cpp",
    (const char *)(unsigned int)v2,
    ppv);
LABEL_47:
  std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::~vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(&v44);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18022f2fc  mov     r11, rsp
0x18022f2ff  push    rbx
0x18022f300  push    rsi
0x18022f301  push    rdi
0x18022f302  push    r12
0x18022f304  push    r14
0x18022f306  push    r15
0x18022f308  sub     rsp, 0D8h
0x18022f30f  mov     rax, cs:__security_cookie
0x18022f316  xor     rax, rsp
0x18022f319  mov     [rsp+108h+var_48], rax
0x18022f321  mov     r15, rcx
0x18022f324  xorps   xmm0, xmm0
0x18022f327  movdqu  xmmword ptr [r11-80h], xmm0
0x18022f32d  xor     r12d, r12d
0x18022f330  mov     [r11-70h], r12
0x18022f334  mov     rax, [rcx]
0x18022f337  mov     rcx, [rax+10h]
0x18022f33b  mov     rax, [rcx]
0x18022f33e  lea     rdx, [r11-80h]
0x18022f342  mov     rax, [rax+68h]
0x18022f346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f34b  mov     ebx, eax
0x18022f34d  test    eax, eax
0x18022f34f  jns     short loc_18022F372
0x18022f351  mov     rcx, [rsp+108h]; this
0x18022f359  mov     r9d, eax; char *
0x18022f35c  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f363  lea     edx, [r12+2Bh]; void *
0x18022f368  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f36d  jmp     loc_18022F899
0x18022f372  mov     rax, [rsp+108h+var_78]
0x18022f37a  cmp     [rsp+108h+var_80], rax
0x18022f382  jz      loc_18022F896
0x18022f388  mov     [rsp+108h+var_D0], r12
0x18022f38d  mov     [rsp+108h+var_D8], r12
0x18022f392  lea     rcx, [rsp+108h+var_D8]
0x18022f397  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f39c  lea     rdx, [rsp+108h+var_D8]
0x18022f3a1  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x18022f3a6  mov     ebx, eax
0x18022f3a8  test    eax, eax
0x18022f3aa  jns     short loc_18022F3E3
0x18022f3ac  mov     rcx, [rsp+108h]; this
0x18022f3b4  mov     r9d, eax; char *
0x18022f3b7  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f3be  mov     edx, 30h ; '0'; void *
0x18022f3c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f3c8  nop
0x18022f3c9  lea     rcx, [rsp+108h+var_D8]
0x18022f3ce  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f3d3  nop
0x18022f3d4  lea     rcx, [rsp+108h+var_D0]
0x18022f3d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f3de  jmp     loc_18022F899
0x18022f3e3  mov     rsi, [rsp+108h+var_80]
0x18022f3eb  mov     r14, [rsp+108h+var_78]
0x18022f3f3  cmp     rsi, r14
0x18022f3f6  jz      loc_18022F796
0x18022f3fc  mov     [rsp+108h+var_C8], r12
0x18022f401  lea     rdx, [rsp+108h+var_88]
0x18022f409  mov     rcx, [rsi]
0x18022f40c  call    ?GetTileIdentifier@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileIdentifier(void)
0x18022f411  mov     rcx, [rax]
0x18022f414  mov     [rax], r12
0x18022f417  mov     [rsp+108h+var_C8], rcx
0x18022f41c  lea     rcx, [rsp+108h+var_88]; void *
0x18022f424  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18022f429  nop
0x18022f42a  mov     rcx, [rsi]
0x18022f42d  call    ?GetTileType@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAA?BW4LayoutTileType@23456@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileType(void)
0x18022f432  test    eax, eax
0x18022f434  jnz     loc_18022F530
0x18022f43a  mov     [rsp+108h+var_98], r12
0x18022f43f  lea     rdx, [rsp+108h+var_98]
0x18022f444  lea     rcx, [rsp+108h+var_C8]
0x18022f449  call    ??$As@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IPackagedUnifiedTileIdentifier>>)
0x18022f44e  mov     ebx, eax
0x18022f450  test    eax, eax
0x18022f452  jns     short loc_18022F48B
0x18022f454  mov     rcx, [rsp+108h]; this
0x18022f45c  mov     r9d, eax; char *
0x18022f45f  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f466  mov     edx, 3Eh ; '>'; void *
0x18022f46b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f470  nop
0x18022f471  lea     rcx, [rsp+108h+var_98]
0x18022f476  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f47b  nop
0x18022f47c  lea     rcx, [rsp+108h+var_C8]
0x18022f481  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f486  jmp     loc_18022F3C9
0x18022f48b  mov     [rsp+108h+string], r12
0x18022f490  mov     rdi, [rsp+108h+var_98]
0x18022f495  mov     rax, [rdi]
0x18022f498  mov     rbx, [rax+30h]
0x18022f49c  xor     ecx, ecx; string
0x18022f49e  call    cs:__imp_WindowsDeleteString
0x18022f4a4  mov     [rsp+108h+string], r12
0x18022f4a9  lea     rdx, [rsp+108h+string]
0x18022f4ae  mov     rcx, rdi
0x18022f4b1  mov     rax, rbx
0x18022f4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f4b9  mov     ebx, eax
0x18022f4bb  test    eax, eax
0x18022f4bd  jns     short loc_18022F4EE
0x18022f4bf  mov     edx, 41h ; 'A'; void *
0x18022f4c4  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f4cb  mov     r9d, eax; char *
0x18022f4ce  mov     rcx, [rsp+108h]; this
0x18022f4d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f4db  nop
0x18022f4dc  mov     rcx, [rsp+108h+string]; string
0x18022f4e1  call    cs:__imp_WindowsDeleteString
0x18022f4e7  mov     [rsp+108h+string], r12
0x18022f4ec  jmp     short loc_18022F471
0x18022f4ee  mov     rcx, [rsp+108h+var_D8]
0x18022f4f3  mov     rax, [rcx]
0x18022f4f6  mov     rdx, [rsp+108h+string]
0x18022f4fb  mov     rax, [rax+68h]
0x18022f4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f504  mov     ebx, eax
0x18022f506  test    eax, eax
0x18022f508  jns     short loc_18022F511
0x18022f50a  mov     edx, 42h ; 'B'
0x18022f50f  jmp     short loc_18022F4C4
0x18022f511  mov     rcx, [rsp+108h+string]; string
0x18022f516  call    cs:__imp_WindowsDeleteString
0x18022f51c  mov     [rsp+108h+string], r12
0x18022f521  lea     rcx, [rsp+108h+var_98]
0x18022f526  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f52b  jmp     loc_18022F70D
0x18022f530  mov     rcx, [rsi]
0x18022f533  call    ?GetTileType@LayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@QEAA?BW4LayoutTileType@23456@XZ; WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile::GetTileType(void)
0x18022f538  cmp     eax, 1
0x18022f53b  jnz     loc_18022F720
0x18022f541  cmp     [rsp+108h+var_D0], r12
0x18022f546  jnz     short loc_18022F5B4
0x18022f548  mov     rax, [r15]
0x18022f54b  mov     rcx, [rax+18h]
0x18022f54f  mov     rbx, [rcx]
0x18022f552  mov     [rsp+108h+var_50], r12
0x18022f55a  mov     r9d, 5Fh ; '_'; unsigned int
0x18022f560  lea     r8d, [r9+1]; unsigned int
0x18022f564  lea     rdx, ?RuntimeClass_WindowsInternal_Shell_UnifiedTile_CuratedTileCollections_CuratedCollectionInitializationStatics@@3QBGB; "WindowsInternal.Shell.UnifiedTile.Curat"...
0x18022f56b  lea     rcx, [rsp+108h+hstringHeader]; hstringHeader
0x18022f573  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18022f578  lea     r8, [rsp+108h+var_D0]
0x18022f57d  mov     rdx, rbx
0x18022f580  mov     rcx, [rsp+108h+var_50]
0x18022f588  call    ??$GetActivationFactoryAsUser@V?$ComPtr@UICuratedCollectionInitializationStatics@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAUIUser@System@1@V?$ComPtrRef@V?$ComPtr@UICuratedCollectionInitializationStatics@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactoryAsUser<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedCollectionInitializationStatics>>(HSTRING__ *,Windows::System::IUser *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedCollectionInitializationStatics>>)
0x18022f58d  mov     ebx, eax
0x18022f58f  test    eax, eax
0x18022f591  jns     short loc_18022F5B4
0x18022f593  mov     rcx, [rsp+108h]; this
0x18022f59b  mov     r9d, eax; char *
0x18022f59e  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f5a5  mov     edx, 52h ; 'R'; void *
0x18022f5aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f5af  jmp     loc_18022F47C
0x18022f5b4  mov     [rsp+108h+var_A8], r12
0x18022f5b9  lea     rdx, [rsp+108h+var_A8]
0x18022f5be  lea     rcx, [rsp+108h+var_C8]
0x18022f5c3  call    ??$As@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@?$ComPtr@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::As<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::IWin32UnifiedTileIdentifier>>)
0x18022f5c8  mov     ebx, eax
0x18022f5ca  test    eax, eax
0x18022f5cc  jns     short loc_18022F5FA
0x18022f5ce  mov     rcx, [rsp+108h]; this
0x18022f5d6  mov     r9d, eax; char *
0x18022f5d9  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f5e0  mov     edx, 57h ; 'W'; void *
0x18022f5e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f5ea  nop
0x18022f5eb  lea     rcx, [rsp+108h+var_A8]
0x18022f5f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f5f5  jmp     loc_18022F47C
0x18022f5fa  mov     [rsp+108h+var_C0], r12
0x18022f5ff  mov     rdi, [rsp+108h+var_A8]
0x18022f604  mov     rax, [rdi]
0x18022f607  mov     rbx, [rax+30h]
0x18022f60b  xor     ecx, ecx; string
0x18022f60d  call    cs:__imp_WindowsDeleteString
0x18022f613  mov     [rsp+108h+var_C0], r12
0x18022f618  lea     rdx, [rsp+108h+var_C0]
0x18022f61d  mov     rcx, rdi
0x18022f620  mov     rax, rbx
0x18022f623  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f628  mov     ebx, eax
0x18022f62a  test    eax, eax
0x18022f62c  jns     short loc_18022F65D
0x18022f62e  mov     rcx, [rsp+108h]; this
0x18022f636  mov     r9d, eax; char *
0x18022f639  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f640  mov     edx, 5Ah ; 'Z'; void *
0x18022f645  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f64a  nop
0x18022f64b  mov     rcx, [rsp+108h+var_C0]; string
0x18022f650  call    cs:__imp_WindowsDeleteString
0x18022f656  mov     [rsp+108h+var_C0], r12
0x18022f65b  jmp     short loc_18022F5EB
0x18022f65d  mov     [rsp+108h+var_B0], r12
0x18022f662  mov     rdi, [rsp+108h+var_D0]
0x18022f667  mov     rax, [rdi]
0x18022f66a  mov     rbx, [rax+68h]
0x18022f66e  xor     ecx, ecx; string
0x18022f670  call    cs:__imp_WindowsDeleteString
0x18022f676  mov     [rsp+108h+var_B0], r12
0x18022f67b  lea     r8, [rsp+108h+var_B0]
0x18022f680  mov     rdx, [rsp+108h+var_C0]
0x18022f685  mov     rcx, rdi
0x18022f688  mov     rax, rbx
0x18022f68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f690  mov     ebx, eax
0x18022f692  test    eax, eax
0x18022f694  jns     short loc_18022F6A8
0x18022f696  mov     rcx, [rsp+108h+var_B0]; string
0x18022f69b  call    cs:__imp_WindowsDeleteString
0x18022f6a1  mov     [rsp+108h+var_B0], r12
0x18022f6a6  jmp     short loc_18022F64B
0x18022f6a8  mov     rcx, [rsp+108h+var_D8]
0x18022f6ad  mov     rax, [rcx]
0x18022f6b0  mov     rdx, [rsp+108h+var_B0]
0x18022f6b5  mov     rax, [rax+68h]
0x18022f6b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18022f6be  mov     ebx, eax
0x18022f6c0  test    eax, eax
0x18022f6c2  jns     short loc_18022F6E2
0x18022f6c4  mov     rcx, [rsp+108h]; this
0x18022f6cc  mov     r9d, eax; char *
0x18022f6cf  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f6d6  mov     edx, 5Eh ; '^'; void *
0x18022f6db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f6e0  jmp     short loc_18022F696
0x18022f6e2  mov     rcx, [rsp+108h+var_B0]; string
0x18022f6e7  call    cs:__imp_WindowsDeleteString
0x18022f6ed  mov     [rsp+108h+var_B0], r12
0x18022f6f2  mov     rcx, [rsp+108h+var_C0]; string
0x18022f6f7  call    cs:__imp_WindowsDeleteString
0x18022f6fd  mov     [rsp+108h+var_C0], r12
0x18022f702  lea     rcx, [rsp+108h+var_A8]
0x18022f707  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f70c  nop
0x18022f70d  lea     rcx, [rsp+108h+var_C8]
0x18022f712  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f717  add     rsi, 10h
0x18022f71b  jmp     loc_18022F3F3
0x18022f720  mov     rcx, [rsp+108h]; this
0x18022f728  mov     r9d, 80070057h; char *
0x18022f72e  lea     r8, aShellcommonShe_231; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18022f735  mov     edx, 63h ; 'c'; void *
0x18022f73a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022f73f  nop
0x18022f740  lea     rcx, [rsp+108h+var_C8]
0x18022f745  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f74a  nop
0x18022f74b  lea     rcx, [rsp+108h+var_D8]
0x18022f750  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f755  nop
0x18022f756  lea     rcx, [rsp+108h+var_D0]
0x18022f75b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f760  mov     ebx, 80070057h
0x18022f765  jmp     loc_18022F899
0x18022f76a  lea     rcx, [rsp+108h+var_C8]
0x18022f76f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f774  nop
0x18022f775  lea     rcx, [rsp+108h+var_D8]
0x18022f77a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f77f  nop
0x18022f780  lea     rcx, [rsp+108h+var_D0]
0x18022f785  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f78a  mov     ebx, [rsp+108h+var_88]
0x18022f791  jmp     loc_18022F899
0x18022f796  mov     [rsp+108h+var_A0], r12
0x18022f79b  lea     rcx, [rsp+108h+var_A0]
0x18022f7a0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f7a5  lea     rax, [rsp+108h+var_A0]
0x18022f7aa  mov     qword ptr [rsp+108h+ppv], rax; int
0x18022f7af  lea     r9, _GUID_9767060c_9476_42e2_8f7b_2f10fd13765c; riid
0x18022f7b6  xor     edx, edx; pUnkOuter
0x18022f7b8  mov     r8d, 404h; dwClsContext
0x18022f7be  lea     rcx, _GUID_228826af_02e1_4226_a9e0_99a855e455a6; rclsid
0x18022f7c5  call    cs:__imp_CoCreateInstance
0x18022f7cb  mov     ebx, eax
0x18022f7cd  test    eax, eax
0x18022f7cf  jns     short loc_18022F7E0
0x18022f7d1  lea     rcx, [rsp+108h+var_A0]
0x18022f7d6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f7db  jmp     loc_18022F3C9
0x18022f7e0  mov     [rsp+108h+var_90], r12
0x18022f7e5  mov     rdi, [rsp+108h+var_A0]
0x18022f7ea  mov     rax, [rdi]
0x18022f7ed  mov     rbx, [rax+60h]
0x18022f7f1  lea     rcx, [rsp+108h+var_90]
0x18022f7f6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18022f7fb  lea     r9, [rsp+108h+var_90]
0x18022f800  lea     r8, _GUID_99e01be7_d840_6dfb_694f_8814c2ec727e
0x18022f807  lea     rdx, _GUID_e2923845_a1d4_49a0_84a6_419152538eb8
0x18022f80e  mov     rcx, rdi
0x18022f811  mov     rax, rbx
0x18022f814  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
