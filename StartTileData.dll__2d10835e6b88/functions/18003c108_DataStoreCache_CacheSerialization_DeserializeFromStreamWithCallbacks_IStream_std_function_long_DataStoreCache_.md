# DataStoreCache::CacheSerialization::DeserializeFromStreamWithCallbacks(IStream *,std::function<long (DataStoreCache::GlobalHeader const &)> const &,std::function<long (DataStoreCache::CollectionDataHeader const &)> const &,std::function<Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer> (DataStoreCache::PerTransformerHeader const &)> const &,std::function<long (ushort const *)> const &)

- ea: `0x18003c108`
- end: `0x18003ca63`
- name: `?DeserializeFromStreamWithCallbacks@CacheSerialization@DataStoreCache@@AEBAJPEAUIStream@@AEBV?$function@$$A6AJAEBUGlobalHeader@DataStoreCache@@@Z@std@@AEBV?$function@$$A6AJAEBUCollectionDataHeader@DataStoreCache@@@Z@5@AEBV?$function@$$A6A?AV?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@AEBUPerTransformerHeader@DataStoreCache@@@Z@5@AEBV?$function@$$A6AJPEBG@Z@5@@Z`
- size: `2395`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800676d4`
- `0x1801590c8`

## callees

- `0x18000b5f0`
- `0x18000ce94`
- `0x18001aca4`
- `0x18001dfb8`
- `0x180032290`
- `0x18003794c`
- `0x18003a680`
- `0x18003a6b4`
- `0x18003a940`
- `0x18003aa78`
- `0x18003ad40`
- `0x18003ae74`
- `0x18003c108`
- `0x18003ca6c`
- `0x18003ca88`
- `0x180096474`
- `0x1800f427c`
- `0x18012b1ac`
- `0x180130784`
- `0x180188a54`
- `0x180201e50`
- `0x1802022fc`
- `0x18020295c`
- `0x18020c250`
- `0x18031581c`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c5bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c62a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c4d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c5bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c62a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003c996`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003c5d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003c5d1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18003c7c0`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18003c7c0`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003c8df`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003ca0d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003ca3b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003c8df`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003ca0d`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18003ca3b`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c1a4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c213`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c26d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c30f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c3ca`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c54f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c598`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c65c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c6aa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c1a4`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c213`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c26d`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c30f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c3ca`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c54f`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c598`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c65c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Read` at `0x18003c6aa`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18003c1eb`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x18003c1eb`

## string_xrefs

- `0x18003c45d`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003c4be`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003c86b`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003c8b5`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003c8f9`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003c94f`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003c96a`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003c9c6`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003ca1e`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003ca4a`: `shellcommon\shell\datastorecache\cache\lib\cacheserialization.cpp`
- `0x18003c167`: `Cache_DeserializeFromStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall DataStoreCache::CacheSerialization::DeserializeFromStreamWithCallbacks(
        __int64 a1,
        IStream *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // r15
  __int64 v10; // r13
  unsigned __int64 v11; // r12
  DataStoreCache::CacheSerialization *v12; // rcx
  __int64 v13; // rbx
  HRESULT v14; // eax
  unsigned int v15; // edi
  HRESULT v16; // eax
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  HRESULT v20; // eax
  __int64 v21; // rax
  __int64 v22; // rdi
  __int64 v23; // rcx
  unsigned int v24; // ebx
  void *v25; // rdi
  HRESULT v26; // eax
  __int64 v27; // rax
  unsigned __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // r9
  __int64 v31; // rdx
  unsigned int v33; // r13d
  HRESULT v34; // eax
  unsigned int v35; // ebx
  void *v36; // rsi
  HRESULT v37; // eax
  HRESULT v38; // eax
  __int64 v39; // rcx
  HRESULT v40; // eax
  unsigned int i; // r15d
  const struct std::nothrow_t *v42; // rdx
  unsigned int v43; // ebx
  HRESULT v44; // eax
  __int64 v45; // rdi
  __int64 v46; // rax
  __int64 v47; // rdi
  _QWORD *v48; // rbx
  __int64 v49; // rax
  __int64 *v50; // rbx
  __int64 v51; // rax
  int v52; // eax
  int v53; // edi
  const struct std::nothrow_t *v54; // rdx
  unsigned __int64 v55; // r9
  __int64 v56; // rdx
  __int64 v57; // rdx
  __int64 v58; // rdx
  __int64 v59; // r9
  int v60; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  void *v62; // [rsp+38h] [rbp-C8h] BYREF
  int v63; // [rsp+40h] [rbp-C0h]
  __int64 v64; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v65; // [rsp+50h] [rbp-B0h]
  size_t v66; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v67[2]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v68; // [rsp+70h] [rbp-90h] BYREF
  int v69; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v70[2]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v71[3]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v72; // [rsp+B0h] [rbp-50h]
  __int64 v73; // [rsp+B8h] [rbp-48h]
  __int64 pv; // [rsp+C0h] [rbp-40h] BYREF
  void *v75; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v76; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v77; // [rsp+E0h] [rbp-20h]
  __int64 v78; // [rsp+E8h] [rbp-18h]
  __int64 v79; // [rsp+F0h] [rbp-10h]
  __int128 v80; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v81[16]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 v82[16]; // [rsp+120h] [rbp+20h] BYREF
  size_t v83; // [rsp+130h] [rbp+30h]
  __int128 v84; // [rsp+138h] [rbp+38h] BYREF
  size_t Size; // [rsp+148h] [rbp+48h]
  __int128 v86; // [rsp+150h] [rbp+50h] BYREF
  __int64 v87; // [rsp+160h] [rbp+60h]
  __int128 v88; // [rsp+168h] [rbp+68h] BYREF
  __int128 v89; // [rsp+178h] [rbp+78h]
  void **v90; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v91[272]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v92[8]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v93[48]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v6 = a4;
  v78 = a4;
  v10 = a5;
  v79 = a5;
  v77 = a6;
  LODWORD(v11) = 0;
  v63 = 0;
  wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v90);
  v90 = &DataStoreCacheTelemetry::Cache_DeserializeFromStream::`vftable';
  DataStoreCacheTelemetry::Cache_DeserializeFromStream::StartActivity((DataStoreCacheTelemetry::Cache_DeserializeFromStream *)&v90);
  pv = 0;
  LODWORD(v13) = IStream_Read(a2, &pv, 8u);
  if ( (int)v13 < 0 )
  {
    v55 = (unsigned int)v13;
    v56 = 413;
    goto LABEL_103;
  }
  v67[0] = 0;
  LODWORD(v13) = DataStoreCache::CacheSerialization::CRCCheckStream(v12, a2, v67);
  if ( (int)v13 < 0 )
  {
    v28 = (unsigned int)v13;
    v29 = 415;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
      (const char *)v28,
      v60);
    goto LABEL_32;
  }
  if ( !*(_BYTE *)(a1 + 64) && pv != v67[0] )
  {
    DataStoreCacheTelemetry::Cache_CRCFailure();
    LODWORD(v13) = -2147024873;
    wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v90, 2147942423LL);
    goto LABEL_32;
  }
  v14 = IStream_Reset(a2);
  LODWORD(v13) = v14;
  v15 = 0;
  if ( v14 < 0 )
  {
    v28 = (unsigned int)v14;
    v29 = 422;
    goto LABEL_31;
  }
  v88 = 0;
  v89 = 0;
  v16 = IStream_Read(a2, &v88, 0x20u);
  v13 = (unsigned int)v16;
  if ( v16 < 0 )
  {
    v56 = 427;
    goto LABEL_102;
  }
  v17 = *(_QWORD *)(a3 + 56);
  if ( !v17 )
  {
    std::_Xbad_function_call();
    goto LABEL_23;
  }
  v18 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v17 + 16LL))(v17, &v88);
  if ( v18 < 0 )
  {
    LODWORD(v13) = v18;
    goto LABEL_32;
  }
  while ( 1 )
  {
    v65 = v15;
    if ( v15 >= (unsigned int)v89 )
    {
      wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v90, 0);
      v90 = &DataStoreCacheTelemetry::Cache_DeserializeFromStream::`vftable';
      wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v90);
      wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v93);
      wil::details::shared_object<wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v92);
      wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v91);
      return 0;
    }
    v86 = 0;
    v87 = 0;
    v16 = IStream_Read(a2, &v86, 0x18u);
    LODWORD(v13) = v16;
    if ( v16 < 0 )
    {
      v56 = 434;
LABEL_102:
      v55 = (unsigned int)v16;
LABEL_103:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v56,
        (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
        (const char *)v55,
        v60);
LABEL_38:
      DataStoreCacheTelemetry::Cache_DeserializeFromStream::~Cache_DeserializeFromStream((DataStoreCacheTelemetry::Cache_DeserializeFromStream *)&v90);
      return (unsigned int)v13;
    }
    v19 = *(_QWORD *)(v6 + 56);
    if ( !v19 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    v16 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 16LL))(v19, &v86);
    LODWORD(v13) = v16;
    if ( v16 < 0 )
    {
      v56 = 435;
      goto LABEL_102;
    }
    v69 = 0;
    v70[0] = 0;
    v70[1] = 0;
    std::list<std::pair<unsigned short const * const,std::pair<unsigned int,Microsoft::WRL::Wrappers::HString>>>::_Alloc_sentinel_and_proxy(v70);
    std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(v71);
    v72 = 7;
    v73 = 8;
    v69 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<enum DataStoreCache::PlaceholderTileTransformer::InstallDelayType>>,std::_Iterator_base0>>>::_Assign_grow(
      v71,
      16,
      v70[0]);
    LODWORD(a3) = 0;
LABEL_14:
    if ( (unsigned int)a3 < (unsigned int)v87 )
      break;
    v33 = 0;
LABEL_41:
    if ( v33 < HIDWORD(v87) )
    {
      v66 = 0;
      v34 = IStream_Read(a2, &v66, 8u);
      LODWORD(v13) = v34;
      if ( v34 < 0 )
      {
        v59 = (unsigned int)v34;
        v58 = 462;
      }
      else
      {
        if ( HIDWORD(v66) <= 0x19000 )
        {
          v35 = HIDWORD(v66);
          v36 = operator new[](HIDWORD(v66));
          memset_0(v36, 0, v35);
          v62 = v36;
          v37 = IStream_Read(a2, v36, HIDWORD(v66));
          LODWORD(v13) = v37;
          if ( v37 >= 0 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *((_WORD *)v36 + v13) );
            string = 0;
            WindowsDeleteString(0);
            string = 0;
            v38 = WindowsCreateString((PCNZWCH)v36, v13, &string);
            LODWORD(v13) = v38;
            if ( v38 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1D9,
                (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
                (const char *)(unsigned int)v38,
                v60);
              WindowsDeleteString(string);
              string = 0;
              operator delete(v36, v54);
              goto LABEL_76;
            }
            v67[0] = (unsigned __int64)v36;
            v39 = *(_QWORD *)(v77 + 56);
            if ( v39 )
            {
              v40 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v39 + 16LL))(v39, v67);
              LODWORD(v13) = v40;
              if ( v40 < 0 )
              {
                v31 = 474;
              }
              else
              {
                LODWORD(v11) = v11 | 4;
                v63 = v11;
                for ( i = 0; ; ++i )
                {
                  if ( i >= (unsigned int)v66 )
                  {
                    WindowsDeleteString(string);
                    string = 0;
                    operator delete(v36, v42);
                    ++v33;
                    goto LABEL_41;
                  }
                  *(_OWORD *)v82 = 0;
                  LODWORD(v83) = 0;
                  v40 = IStream_Read(a2, v82, 0x14u);
                  LODWORD(v13) = v40;
                  if ( v40 < 0 )
                    break;
                  if ( (unsigned int)v83 > 0x19000 )
                  {
                    LODWORD(v13) = -2147418113;
                    v30 = 2147549183LL;
                    v31 = 480;
                    goto LABEL_34;
                  }
                  if ( !(_DWORD)v83 )
                  {
                    LODWORD(v13) = -2147418113;
                    v30 = 2147549183LL;
                    v31 = 483;
                    goto LABEL_34;
                  }
                  v43 = v83;
                  v11 = (unsigned __int64)operator new[]((unsigned int)v83);
                  memset_0((void *)v11, 0, v43);
                  v67[0] = v11;
                  v44 = IStream_Read(a2, (void *)v11, v83);
                  LODWORD(v13) = v44;
                  if ( v44 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1E6,
                      (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
                      (const char *)(unsigned int)v44,
                      v60);
                    std::unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>::~unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>(v67);
                    goto LABEL_35;
                  }
                  v45 = std::_Conditionally_enabled_hash<HSTRING__ *,1>::operator()(&v82[8]);
                  v46 = std::_Conditionally_enabled_hash<HSTRING__ *,1>::operator()(v82);
                  v47 = v72 & (v46 ^ v45);
                  v48 = *(_QWORD **)(v71[0] + 16 * v47 + 8);
                  if ( v48 == (_QWORD *)v70[0] )
                    goto LABEL_70;
                  while ( 1 )
                  {
                    v49 = *(_QWORD *)v82 - v48[2];
                    if ( *(_QWORD *)v82 == v48[2] )
                      v49 = *(_QWORD *)&v82[8] - v48[3];
                    if ( !v49 )
                      break;
                    if ( v48 == *(_QWORD **)(v71[0] + 16 * v47) )
                      goto LABEL_70;
                    v48 = (_QWORD *)v48[1];
                  }
                  if ( !v48 )
                  {
LABEL_70:
                    std::_Xout_of_range("invalid unordered_map<K, T> key");
                    goto LABEL_71;
                  }
                  v50 = (__int64 *)v48[4];
                  *(_QWORD *)&v76 = v50;
                  if ( v50 )
                    (*(void (__fastcall **)(__int64 *))(*v50 + 8))(v50);
                  v51 = *v50;
                  v67[0] = 0;
                  v68 = v11;
                  v80 = *(_OWORD *)v82;
                  v60 = v83;
                  v52 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int128 *, unsigned __int64 *))(v51 + 48))(
                          v50,
                          string,
                          &v80,
                          &v68);
                  v53 = v52;
                  if ( v52 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1E9,
                      (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
                      (const char *)(unsigned int)v52,
                      v60);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v76);
                    std::unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>::~unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>(v67);
                    WindowsDeleteString(string);
                    string = 0;
                    std::unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>::~unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>(&v62);
                    std::_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>::~_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>(&v69);
                    LODWORD(v13) = v53;
                    goto LABEL_38;
                  }
                  LODWORD(v11) = v63 | 8;
                  v63 |= 8u;
                  if ( v50 )
                    (*(void (__fastcall **)(__int64 *))(*v50 + 16))(v50);
                }
                v31 = 479;
              }
              v30 = (unsigned int)v40;
LABEL_34:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v31,
                (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
                (const char *)v30,
                v60);
LABEL_35:
              WindowsDeleteString(string);
              string = 0;
              goto LABEL_36;
            }
            std::_Xbad_function_call();
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D2,
            (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
            (const char *)(unsigned int)v37,
            v60);
LABEL_36:
          std::unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>::~unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>(&v62);
          goto LABEL_37;
        }
        v58 = 463;
LABEL_88:
        LODWORD(v13) = -2147418113;
        v59 = 2147549183LL;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v58,
        (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
        (const char *)v59,
        v60);
      goto LABEL_37;
    }
LABEL_71:
    std::_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>::~_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>(&v69);
    v15 = v65 + 1;
    v6 = v78;
    v10 = v79;
  }
  v84 = 0;
  LODWORD(Size) = 0;
  v20 = IStream_Read(a2, &v84, 0x14u);
  LODWORD(v13) = v20;
  if ( v20 >= 0 )
  {
    if ( (unsigned int)Size > 0x19000 )
    {
      v58 = 444;
      goto LABEL_88;
    }
    std::_Func_class<std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>,Microsoft::WRL::Wrappers::HString const &>::operator()(
      v10,
      &v64,
      &v84);
    v21 = std::_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>::_Try_emplace<_GUID const &,>(
            &v69,
            v81,
            &v84);
    v22 = *(_QWORD *)v21;
    v13 = v64;
    if ( *(_QWORD *)(*(_QWORD *)v21 + 32LL) != v64 )
    {
      if ( v64 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 8LL))(v64);
      v23 = *(_QWORD *)(v22 + 32);
      *(_QWORD *)(v22 + 32) = v13;
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v13 = v64;
    }
LABEL_23:
    if ( (_DWORD)Size )
    {
      v24 = Size;
      v25 = operator new[]((unsigned int)Size);
      memset_0(v25, 0, v24);
      v62 = v25;
      v26 = IStream_Read(a2, v25, Size);
      LODWORD(v13) = v26;
      if ( v26 < 0 )
      {
        v57 = 451;
LABEL_85:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v57,
          (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
          (const char *)(unsigned int)v26,
          v60);
        std::unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>::~unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>(&v62);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
LABEL_37:
        std::_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>::~_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>(&v69);
        goto LABEL_38;
      }
      v27 = *(_QWORD *)v64;
      v62 = 0;
      v75 = v25;
      v76 = v84;
      *(_OWORD *)v67 = v86;
      v60 = Size;
      v26 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, __int128 *, void **))(v27 + 32))(
              v64,
              v67,
              &v76,
              &v75);
      LODWORD(v13) = v26;
      if ( v26 < 0 )
      {
        v57 = 453;
        goto LABEL_85;
      }
      LODWORD(v11) = v11 | 2;
      v13 = v64;
    }
    if ( v13 )
    {
      v64 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    LODWORD(a3) = a3 + 1;
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1BB,
    (unsigned int)"shellcommon\\shell\\datastorecache\\cache\\lib\\cacheserialization.cpp",
    (const char *)(unsigned int)v20,
    v60);
LABEL_76:
  std::_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>::~_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>(&v69);
LABEL_32:
  v90 = &DataStoreCacheTelemetry::Cache_DeserializeFromStream::`vftable';
  wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v90);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v93);
  wil::details::shared_object<wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v92);
  wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v91);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18003c108  mov     [rsp-8+arg_0], rbx
0x18003c10d  push    rbp
0x18003c10e  push    rsi
0x18003c10f  push    rdi
0x18003c110  push    r12
0x18003c112  push    r13
0x18003c114  push    r14
0x18003c116  push    r15
0x18003c118  lea     rbp, [rsp-1F0h]
0x18003c120  sub     rsp, 2F0h
0x18003c127  mov     rax, cs:__security_cookie
0x18003c12e  xor     rax, rsp
0x18003c131  mov     [rbp+220h+var_40], rax
0x18003c138  mov     r15, r9
0x18003c13b  mov     [rbp+220h+var_238], r9
0x18003c13f  mov     rsi, r8
0x18003c142  mov     r14, rdx
0x18003c145  mov     rdi, rcx
0x18003c148  mov     r13, [rbp+220h+arg_20]
0x18003c14f  mov     [rbp+220h+var_230], r13
0x18003c153  mov     rax, [rbp+220h+arg_28]
0x18003c15a  mov     [rbp+220h+var_240], rax
0x18003c15e  xor     ebx, ebx
0x18003c160  mov     r12d, ebx
0x18003c163  mov     [rsp+320h+var_2E0], ebx
0x18003c167  lea     rdx, aCacheDeseriali; "Cache_DeserializeFromStream"
0x18003c16e  lea     rcx, [rbp+220h+var_190]; struct wil::details::IFailureCallback *
0x18003c175  call    ??0?$ActivityBase@VDataStoreCacheLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003c17a  lea     rax, ??_7Cache_DeserializeFromStream@DataStoreCacheTelemetry@@6B@; const DataStoreCacheTelemetry::Cache_DeserializeFromStream::`vftable'
0x18003c181  mov     [rbp+220h+var_190], rax
0x18003c188  lea     rcx, [rbp+220h+var_190]; this
0x18003c18f  call    ?StartActivity@Cache_DeserializeFromStream@DataStoreCacheTelemetry@@QEAAXXZ; DataStoreCacheTelemetry::Cache_DeserializeFromStream::StartActivity(void)
0x18003c194  nop
0x18003c195  mov     [rbp+220h+pv], rbx
0x18003c199  lea     r8d, [rbx+8]; cb
0x18003c19d  lea     rdx, [rbp+220h+pv]; pv
0x18003c1a1  mov     rcx, r14; pstm
0x18003c1a4  call    cs:__imp_IStream_Read
0x18003c1aa  mov     ebx, eax
0x18003c1ac  xor     eax, eax
0x18003c1ae  test    ebx, ebx
0x18003c1b0  js      loc_18003C8C8
0x18003c1b6  mov     [rsp+320h+var_2C0], rax
0x18003c1bb  lea     r8, [rsp+320h+var_2C0]; unsigned __int64 *
0x18003c1c0  mov     rdx, r14; struct IStream *
0x18003c1c3  call    ?CRCCheckStream@CacheSerialization@DataStoreCache@@AEBAJPEAUIStream@@PEA_K@Z; DataStoreCache::CacheSerialization::CRCCheckStream(IStream *,unsigned __int64 *)
0x18003c1c8  mov     ebx, eax
0x18003c1ca  xor     eax, eax
0x18003c1cc  test    ebx, ebx
0x18003c1ce  js      loc_18003C455
0x18003c1d4  cmp     [rdi+40h], al
0x18003c1d7  jnz     short loc_18003C1E8
0x18003c1d9  mov     rax, [rsp+320h+var_2C0]
0x18003c1de  cmp     [rbp+220h+pv], rax
0x18003c1e2  jnz     loc_18003C844
0x18003c1e8  mov     rcx, r14; pstm
0x18003c1eb  call    cs:__imp_IStream_Reset
0x18003c1f1  mov     ebx, eax
0x18003c1f3  xor     edi, edi
0x18003c1f5  test    eax, eax
0x18003c1f7  js      loc_18003C837
0x18003c1fd  xorps   xmm0, xmm0
0x18003c200  movups  [rbp+220h+var_1B8], xmm0
0x18003c204  movups  [rbp+220h+var_1A8], xmm0
0x18003c208  lea     r8d, [rdi+20h]; cb
0x18003c20c  lea     rdx, [rbp+220h+var_1B8]; pv
0x18003c210  mov     rcx, r14; pstm
0x18003c213  call    cs:__imp_IStream_Read
0x18003c219  mov     ebx, eax
0x18003c21b  test    eax, eax
0x18003c21d  js      loc_18003C8D5
0x18003c223  mov     rcx, [rsi+38h]
0x18003c227  test    rcx, rcx
0x18003c22a  jz      loc_18003C8DF
0x18003c230  mov     rax, [rcx]
0x18003c233  lea     rdx, [rbp+220h+var_1B8]
0x18003c237  mov     rax, [rax+10h]
0x18003c23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c240  test    eax, eax
0x18003c242  js      loc_18003C8A4
0x18003c248  mov     [rsp+320h+var_2D0], edi
0x18003c24c  cmp     edi, dword ptr [rbp+220h+var_1A8]
0x18003c24f  jnb     loc_18003C7E3
0x18003c255  xorps   xmm0, xmm0
0x18003c258  xor     eax, eax
0x18003c25a  movups  [rbp+220h+var_1D0], xmm0
0x18003c25e  mov     [rbp+220h+var_1C0], rax
0x18003c262  lea     r8d, [rax+18h]; cb
0x18003c266  lea     rdx, [rbp+220h+var_1D0]; pv
0x18003c26a  mov     rcx, r14; pstm
0x18003c26d  call    cs:__imp_IStream_Read
0x18003c273  mov     ebx, eax
0x18003c275  xor     edi, edi
0x18003c277  test    eax, eax
0x18003c279  js      loc_18003CA42
0x18003c27f  mov     rcx, [r15+38h]
0x18003c283  test    rcx, rcx
0x18003c286  jz      loc_18003CA3B
0x18003c28c  mov     rax, [rcx]
0x18003c28f  lea     rdx, [rbp+220h+var_1D0]
0x18003c293  mov     rax, [rax+10h]
0x18003c297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c29c  mov     ebx, eax
0x18003c29e  test    eax, eax
0x18003c2a0  js      loc_18003CA34
0x18003c2a6  mov     [rbp+220h+var_2A0], edi
0x18003c2a9  mov     [rbp+220h+var_298], rdi
0x18003c2ad  mov     [rbp+220h+var_290], rdi
0x18003c2b1  lea     rcx, [rbp+220h+var_298]
0x18003c2b5  call    ?_Alloc_sentinel_and_proxy@?$list@U?$pair@QEBGU?$pair@IVHString@Wrappers@WRL@Microsoft@@@std@@@std@@V?$allocator@U?$pair@QEBGU?$pair@IVHString@Wrappers@WRL@Microsoft@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::pair<ushort const * const,std::pair<uint,Microsoft::WRL::Wrappers::HString>>>::_Alloc_sentinel_and_proxy(void)
0x18003c2ba  nop
0x18003c2bb  lea     rcx, [rbp+220h+var_288]
0x18003c2bf  call    ??0?$vector@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@V?$allocator@V?$shared_ptr@V?$CloudItemInternal@V?$GenericCloudItem@UPlaceholderTileCollectionLocal@Data@Windows@@$0A@@CloudUtil@DataStoreCache@@@Internal@CloudUtil@DataStoreCache@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>::vector<std::shared_ptr<DataStoreCache::CloudUtil::Internal::CloudItemInternal<DataStoreCache::CloudUtil::GenericCloudItem<Windows::Data::PlaceholderTileCollectionLocal,0>>>>(void)
0x18003c2c4  nop
0x18003c2c5  mov     [rbp+220h+var_270], 7
0x18003c2cd  mov     [rbp+220h+var_268], 8
0x18003c2d5  mov     [rbp+220h+var_2A0], 3F800000h
0x18003c2dc  mov     r8, [rbp+220h+var_298]
0x18003c2e0  lea     edx, [rdi+10h]
0x18003c2e3  lea     rcx, [rbp+220h+var_288]
0x18003c2e7  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@W4InstallDelayType@PlaceholderTileTransformer@DataStoreCache@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@W4InstallDelayType@PlaceholderTileTransformer@DataStoreCache@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<DataStoreCache::PlaceholderTileTransformer::InstallDelayType>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<DataStoreCache::PlaceholderTileTransformer::InstallDelayType>>,std::_Iterator_base0>)
0x18003c2ec  nop
0x18003c2ed  mov     esi, edi
0x18003c2ef  cmp     esi, dword ptr [rbp+220h+var_1C0]
0x18003c2f2  jnb     loc_18003C52F
0x18003c2f8  xorps   xmm0, xmm0
0x18003c2fb  xor     eax, eax
0x18003c2fd  movups  [rbp+220h+var_1E8], xmm0
0x18003c301  mov     dword ptr [rbp+220h+Size], eax
0x18003c304  lea     r8d, [rax+14h]; cb
0x18003c308  lea     rdx, [rbp+220h+var_1E8]; pv
0x18003c30c  mov     rcx, r14; pstm
0x18003c30f  call    cs:__imp_IStream_Read
0x18003c315  mov     ebx, eax
0x18003c317  test    eax, eax
0x18003c319  js      loc_18003C8AB
0x18003c31f  cmp     dword ptr [rbp+220h+Size], 19000h
0x18003c326  ja      loc_18003C92A
0x18003c32c  lea     r8, [rbp+220h+var_1E8]
0x18003c330  lea     rdx, [rsp+320h+var_2D8]
0x18003c335  mov     rcx, r13
0x18003c338  call    ??R?$_Func_class@V?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@AEBVHString@Wrappers@WRL@Microsoft@@@std@@QEBA?AV?$shared_ptr@VLayoutTile@Internal@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Func_class<std::shared_ptr<WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::Internal::LayoutTile>,Microsoft::WRL::Wrappers::HString const &>::operator()(Microsoft::WRL::Wrappers::HString const &)
0x18003c33d  nop
0x18003c33e  lea     r8, [rbp+220h+var_1E8]
0x18003c342  lea     rdx, [rbp+220h+var_210]
0x18003c346  lea     rcx, [rbp+220h+var_2A0]
0x18003c34a  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$_Hash@V?$_Umap_traits@U_GUID@@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x18003c34f  mov     rdi, [rax]
0x18003c352  mov     rbx, [rsp+320h+var_2D8]
0x18003c357  cmp     [rdi+20h], rbx
0x18003c35b  jz      loc_18003C8E6
0x18003c361  test    rbx, rbx
0x18003c364  jz      short loc_18003C376
0x18003c366  mov     rax, [rbx]
0x18003c369  mov     rcx, rbx
0x18003c36c  mov     rax, [rax+8]
0x18003c370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c375  nop
0x18003c376  mov     rcx, [rdi+20h]
0x18003c37a  mov     [rdi+20h], rbx
0x18003c37e  xor     edi, edi
0x18003c380  test    rcx, rcx
0x18003c383  jz      short loc_18003C392
0x18003c385  mov     rax, [rcx]
0x18003c388  mov     rax, [rax+10h]
0x18003c38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c391  nop
0x18003c392  mov     rbx, [rsp+320h+var_2D8]
0x18003c397  mov     eax, dword ptr [rbp+220h+Size]
0x18003c39a  test    eax, eax
0x18003c39c  jz      loc_18003C434
0x18003c3a2  mov     ebx, eax
0x18003c3a4  mov     ecx, eax; unsigned __int64
0x18003c3a6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c3ab  mov     rdi, rax
0x18003c3ae  mov     r8d, ebx; Size
0x18003c3b1  xor     edx, edx; Val
0x18003c3b3  mov     rcx, rax; void *
0x18003c3b6  call    memset_0
0x18003c3bb  mov     [rsp+320h+var_2E8], rdi
0x18003c3c0  mov     r8d, dword ptr [rbp+220h+Size]; cb
0x18003c3c4  mov     rdx, rdi; pv
0x18003c3c7  mov     rcx, r14; pstm
0x18003c3ca  call    cs:__imp_IStream_Read
0x18003c3d0  mov     ebx, eax
0x18003c3d2  xor     r8d, r8d
0x18003c3d5  test    eax, eax
0x18003c3d7  js      loc_18003C8F4
0x18003c3dd  mov     rcx, [rsp+320h+var_2D8]
0x18003c3e2  mov     rax, [rcx]
0x18003c3e5  mov     [rsp+320h+var_2E8], r8
0x18003c3ea  mov     [rbp+220h+var_258], rdi
0x18003c3ee  movups  xmm0, [rbp+220h+var_1E8]
0x18003c3f2  movdqu  [rbp+220h+var_250], xmm0
0x18003c3f7  movups  xmm1, [rbp+220h+var_1D0]
0x18003c3fb  movdqu  xmmword ptr [rsp+320h+var_2C0], xmm1
0x18003c401  mov     edx, dword ptr [rbp+220h+Size]
0x18003c404  mov     qword ptr [rsp+320h+var_300], rdx
0x18003c409  lea     r9, [rbp+220h+var_258]
0x18003c40d  lea     r8, [rbp+220h+var_250]
0x18003c411  lea     rdx, [rsp+320h+var_2C0]
0x18003c416  mov     rax, [rax+20h]
0x18003c41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c41f  mov     ebx, eax
0x18003c421  xor     edi, edi
0x18003c423  test    eax, eax
0x18003c425  js      loc_18003C8ED
0x18003c42b  or      r12d, 2
0x18003c42f  mov     rbx, [rsp+320h+var_2D8]
0x18003c434  test    rbx, rbx
0x18003c437  jz      short loc_18003C44E
0x18003c439  mov     [rsp+320h+var_2D8], rdi
0x18003c43e  mov     rax, [rbx]
0x18003c441  mov     rcx, rbx
0x18003c444  mov     rax, [rax+10h]
0x18003c448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c44d  nop
0x18003c44e  inc     esi
0x18003c450  jmp     loc_18003C2EF
0x18003c455  mov     r9d, ebx; char *
0x18003c458  mov     edx, 19Fh; void *
0x18003c45d  lea     r8, aShellcommonShe_206; "shellcommon\\shell\\datastorecache\\cac"...
0x18003c464  mov     rcx, [rbp+228h]; this
0x18003c46b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c470  nop
0x18003c471  lea     rax, ??_7Cache_DeserializeFromStream@DataStoreCacheTelemetry@@6B@; const DataStoreCacheTelemetry::Cache_DeserializeFromStream::`vftable'
0x18003c478  mov     [rbp+220h+var_190], rax
0x18003c47f  lea     rcx, [rbp+220h+var_190]
0x18003c486  call    ?Destroy@?$ActivityBase@VDataStoreCacheLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18003c48b  lea     rcx, [rbp+220h+var_70]; this
0x18003c492  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18003c497  lea     rcx, [rbp+220h+var_78]
0x18003c49e  call    ?reset@?$shared_object@V?$ActivityData@VDataStoreCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDataStoreCacheLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18003c4a3  lea     rcx, [rbp+220h+var_188]
0x18003c4aa  call    ??1?$ActivityData@VDataStoreCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDataStoreCacheLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DataStoreCacheLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DataStoreCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x18003c4af  jmp     short loc_18003C503
0x18003c4b1  mov     ebx, 8000FFFFh
0x18003c4b6  mov     r9d, ebx; char *
0x18003c4b9  mov     edx, 1E3h; void *
0x18003c4be  lea     r8, aShellcommonShe_206; "shellcommon\\shell\\datastorecache\\cac"...
0x18003c4c5  mov     rcx, [rbp+228h]; this
0x18003c4cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c4d1  nop
0x18003c4d2  mov     rcx, [rsp+320h+string]; string
0x18003c4d7  call    cs:__imp_WindowsDeleteString
0x18003c4dd  mov     [rsp+320h+string], rdi
0x18003c4e2  lea     rcx, [rsp+320h+var_2E8]
0x18003c4e7  call    ??1?$unique_ptr@$$BY0A@UIMAGE_DOWNLOAD_RESULT@@U?$default_delete@$$BY0A@UIMAGE_DOWNLOAD_RESULT@@@std@@@std@@QEAA@XZ; std::unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>::~unique_ptr<IMAGE_DOWNLOAD_RESULT [0]>(void)
0x18003c4ec  nop
0x18003c4ed  lea     rcx, [rbp+220h+var_2A0]
0x18003c4f1  call    ??1?$_Hash@V?$_Umap_traits@U_GUID@@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$ComPtr@UICacheableDataStoreTransformer@DataStoreCache@@@WRL@Microsoft@@@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>::~_Hash<std::_Umap_traits<_GUID,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,Microsoft::WRL::ComPtr<DataStoreCache::ICacheableDataStoreTransformer>>>,0>>(void)
0x18003c4f6  nop
0x18003c4f7  lea     rcx, [rbp+220h+var_190]; this
0x18003c4fe  call    ??1Cache_DeserializeFromStream@DataStoreCacheTelemetry@@QEAA@XZ; DataStoreCacheTelemetry::Cache_DeserializeFromStream::~Cache_DeserializeFromStream(void)
0x18003c503  mov     eax, ebx
0x18003c505  mov     rcx, [rbp+220h+var_40]
0x18003c50c  xor     rcx, rsp; StackCookie
0x18003c50f  call    __security_check_cookie
0x18003c514  mov     rbx, [rsp+320h+arg_0]
0x18003c51c  add     rsp, 2F0h
0x18003c523  pop     r15
0x18003c525  pop     r14
0x18003c527  pop     r13
0x18003c529  pop     r12
0x18003c52b  pop     rdi
0x18003c52c  pop     rsi
0x18003c52d  pop     rbp
0x18003c52e  retn
0x18003c52f  mov     r13d, edi
0x18003c532  cmp     r13d, dword ptr [rbp+220h+var_1C0+4]
0x18003c536  jnb     loc_18003C7C7
0x18003c53c  mov     [rsp+320h+var_2C8], rdi
0x18003c541  mov     r8d, 8; cb
0x18003c547  lea     rdx, [rsp+320h+var_2C8]; pv
0x18003c54c  mov     rcx, r14; pstm
0x18003c54f  call    cs:__imp_IStream_Read
0x18003c555  mov     ebx, eax
0x18003c557  test    eax, eax
0x18003c559  js      loc_18003C940
0x18003c55f  cmp     dword ptr [rsp+320h+var_2C8+4], 19000h
0x18003c567  ja      loc_18003C931
0x18003c56d  mov     ebx, dword ptr [rsp+320h+var_2C8+4]
0x18003c571  mov     ecx, ebx; unsigned __int64
0x18003c573  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18003c578  mov     rsi, rax
0x18003c57b  mov     r8d, ebx; Size
0x18003c57e  xor     edx, edx; Val
0x18003c580  mov     rcx, rax; void *
0x18003c583  call    memset_0
0x18003c588  mov     [rsp+320h+var_2E8], rsi
0x18003c58d  mov     r8d, dword ptr [rsp+320h+var_2C8+4]; cb
0x18003c592  mov     rdx, rsi; pv
0x18003c595  mov     rcx, r14; pstm
0x18003c598  call    cs:__imp_IStream_Read
0x18003c59e  mov     ebx, eax
0x18003c5a0  test    eax, eax
0x18003c5a2  js      loc_18003CA14
0x18003c5a8  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003c5ac  inc     rbx
0x18003c5af  cmp     [rsi+rbx*2], di
  ... truncated ...
```
