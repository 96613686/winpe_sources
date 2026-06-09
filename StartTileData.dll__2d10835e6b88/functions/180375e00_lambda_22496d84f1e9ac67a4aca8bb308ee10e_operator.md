# _lambda_22496d84f1e9ac67a4aca8bb308ee10e_::operator()

- ea: `0x180375e00`
- end: `0x180376417`
- name: `_lambda_22496d84f1e9ac67a4aca8bb308ee10e_::operator()`
- size: `1559`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18037bd60`

## callees

- `0x180013b80`
- `0x18001dac0`
- `0x18002dde0`
- `0x18006f9c0`
- `0x18006f9e4`
- `0x18006fd68`
- `0x1800756e4`
- `0x18007ae80`
- `0x180089820`
- `0x1800c5b3c`
- `0x180112f58`
- `0x180123654`
- `0x180157ee0`
- `0x180161204`
- `0x1801677f0`
- `0x1801a11e4`
- `0x180201e50`
- `0x180374810`
- `0x180374dec`
- `0x180375530`
- `0x180375958`
- `0x1803759b0`
- `0x180375e00`
- `0x1803780a4`
- `0x1803781ac`
- `0x18037aa64`
- `0x18037abec`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18037628b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18037628b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180375f0a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180375f0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180375edd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x180375edd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180375ead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180375f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803760e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180376194`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803762de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037633d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037635b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180375ead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180375f6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803760e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180376194`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803762de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037633d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18037635b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180375eec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180376249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180376316`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180375eec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180376249`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180376316`

## string_xrefs

- `0x1803762bc`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x18037639c`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1803763b1`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1803763c6`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1803763da`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x1803763ef`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x180376404`: `shellcommon\shell\datastorecache\transformers\targetedcontenttransformer\lib\targetedcontenttransformer.cpp`
- `0x180375f21`: `TargetedContentTransformer_UpdateDataItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
char __fastcall lambda_22496d84f1e9ac67a4aca8bb308ee10e_::operator()(__int64 *a1, unsigned __int16 *a2, __int64 a3)
{
  __int64 *v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  UINT32 StringLen; // ebx
  const WCHAR *StringRawBuffer; // rax
  const unsigned __int16 **v14; // rbx
  const unsigned __int16 **v15; // rsi
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  __int64 *v18; // rcx
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rbx
  __int64 v25; // rax
  struct DataStoreCache::PropertyBagLookaside **v26; // rax
  struct DataStoreCache::PropertyBagLookaside *v27; // rbx
  __int64 v28; // rcx
  const struct DataStoreCache::DataStorePropertyIdentifier **v29; // rsi
  const struct DataStoreCache::DataStorePropertyIdentifier **v30; // r15
  __int64 (__fastcall *v31)(__int64, HSTRING *); // rsi
  int v32; // eax
  __int64 *v33; // rax
  __int64 v34; // rdi
  __int64 v35; // rcx
  __int64 v36; // rcx
  HSTRING v37; // rdi
  void (__fastcall *v38)(HSTRING, __int64, _QWORD, unsigned __int64); // rsi
  __int64 v39; // rax
  __int64 v40; // rbx
  PCWSTR v41; // rdx
  int v42; // eax
  const unsigned __int16 *v43; // rax
  const char *v44; // r9
  int bIgnoreCase; // [rsp+20h] [rbp-248h]
  int bIgnoreCasea; // [rsp+20h] [rbp-248h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-248h]
  int bIgnoreCasec; // [rsp+20h] [rbp-248h]
  HSTRING v50; // [rsp+30h] [rbp-238h] BYREF
  HSTRING v51; // [rsp+38h] [rbp-230h] BYREF
  HSTRING v52; // [rsp+40h] [rbp-228h] BYREF
  HSTRING string; // [rsp+48h] [rbp-220h] BYREF
  int v54; // [rsp+50h] [rbp-218h] BYREF
  struct Windows::Services::TargetedContent::ITargetedContentItem *v55; // [rsp+58h] [rbp-210h] BYREF
  __int64 *v56; // [rsp+60h] [rbp-208h] BYREF
  __int64 v57; // [rsp+68h] [rbp-200h] BYREF
  __int64 v58; // [rsp+70h] [rbp-1F8h] BYREF
  unsigned __int16 *v59; // [rsp+78h] [rbp-1F0h] BYREF
  __int64 v60; // [rsp+80h] [rbp-1E8h] BYREF
  struct DataStoreCache::PropertyBagLookaside *v61; // [rsp+88h] [rbp-1E0h] BYREF
  _DWORD v62[6]; // [rsp+90h] [rbp-1D8h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-1C0h]
  _BYTE v64[40]; // [rsp+B8h] [rbp-1B0h] BYREF
  _QWORD v65[42]; // [rsp+E0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v59 = a2;
  v5 = (__int64 *)DataStoreCache::TargetedContentTransformer::ComputeTileIdentifier(*a1, &v58, *(_QWORD *)a1[1], a2);
  v6 = *v5;
  *v5 = 0;
  v60 = v6;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v58);
  if ( !*(_QWORD *)a1[2]
    || (v7 = *a1,
        v8 = wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_returncode_policy>::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_returncode_policy>(
               &v50,
               &v60),
        (unsigned __int8)DataStoreCache::TargetedContentTransformer::IsTilePinnedToStart(v7, v9, v8)) )
  {
    string = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(a3, &string);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x504,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcontenttransformer.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
    StringLen = WindowsGetStringLen(string);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( CompareStringOrdinal(*(LPCWCH *)a1[3], -1, StringRawBuffer, StringLen, 1) == 2 )
    {
      v14 = (const unsigned __int16 **)a1[3];
      v15 = (const unsigned __int16 **)a1[1];
      wil::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v65);
      try
      {
        v65[0] = &DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem::`vftable';
        DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem::StartActivity(
          (DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem *)v65,
          *v15,
          *v14,
          v59);
        v52 = 0;
        v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a3 + 64LL);
        WindowsDeleteString(0);
        v52 = 0;
        v17 = v16(a3, &v52);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x50D,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcon"
                          "tenttransformer.cpp",
            (const char *)(unsigned int)v17,
            bIgnoreCasea);
        v56 = 0;
        v18 = *(__int64 **)a1[4];
        v19 = *v18;
        v56 = 0;
        v20 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 **))(v19 + 80))(v18, v52, &v56);
        if ( v20 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x510,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcon"
                          "tenttransformer.cpp",
            (const char *)(unsigned int)v20,
            bIgnoreCasea);
        v54 = 0;
        v21 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v56 + 48))(v56, &v54);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x513,
            (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedcon"
                          "tenttransformer.cpp",
            (const char *)(unsigned int)v21,
            bIgnoreCasea);
        if ( v54 == 1 )
        {
          v55 = 0;
          v22 = *v56;
          v55 = 0;
          v23 = (*(__int64 (__fastcall **)(__int64 *, struct Windows::Services::TargetedContent::ITargetedContentItem **))(v22 + 64))(
                  v56,
                  &v55);
          if ( v23 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x518,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedc"
                            "ontenttransformer.cpp",
              (const char *)(unsigned int)v23,
              bIgnoreCasea);
          v24 = *a1;
          v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*a1 + 24) + 48LL))(*a1 + 24);
          v26 = (struct DataStoreCache::PropertyBagLookaside **)wil::MakeOrThrow<DataStoreCache::PropertyBagLookaside,_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &>(
                                                                  &v57,
                                                                  v25,
                                                                  v24 + 104);
          v27 = *v26;
          *v26 = 0;
          v61 = v27;
          v28 = v57;
          if ( v57 )
          {
            v57 = 0;
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(v28);
          }
          DataStoreCache::TargetedContentTransformer::UpdateContext::UpdateContext(
            (DataStoreCache::TargetedContentTransformer::UpdateContext *)v62,
            v55,
            string,
            v27,
            *(struct Windows::Services::TargetedContent::ITargetedContentContainer **)a1[4]);
          DataStoreCache::TargetedContentTransformer::AddTileBasicInfo((struct DataStoreCache::TargetedContentTransformer::UpdateContext *)v62);
          v29 = *(const struct DataStoreCache::DataStorePropertyIdentifier ***)(*a1 + 104);
          v30 = *(const struct DataStoreCache::DataStorePropertyIdentifier ***)(*a1 + 112);
          while ( v29 != v30 )
            DataStoreCache::TargetedContentTransformer::AddTileProperty(
              *v29++,
              (struct DataStoreCache::TargetedContentTransformer::UpdateContext *)v62);
          v51 = 0;
          v31 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 56LL);
          WindowsDeleteString(0);
          v51 = 0;
          v32 = v31(v6, &v51);
          if ( v32 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x524,
              (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedc"
                            "ontenttransformer.cpp",
              (const char *)(unsigned int)v32,
              bIgnoreCaseb);
          v33 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, __int64 *, HSTRING))(**(_QWORD **)(*a1 + 152) + 40LL))(
                             *(_QWORD *)(*a1 + 152),
                             &v57,
                             v51);
          v34 = *v33;
          *v33 = 0;
          v58 = v34;
          v35 = v57;
          if ( v57 )
          {
            v57 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          v36 = *a1;
          if ( *(_QWORD *)(*a1 + 248) )
          {
            DataStoreCache::TargetedContentTransformer::GetContentDeliveryManagerPackageFullName(v36, &v50);
            (*(void (__fastcall **)(_QWORD, __int64, __int64, HSTRING))(**(_QWORD **)(*a1 + 248) + 48LL))(
              *(_QWORD *)(*a1 + 248),
              v34,
              1,
              v50);
            WindowsDeleteString(v50);
          }
          if ( (unsigned __int8)DataStoreCache::TargetedContentTransformer::TrySwapTile(
                                  v36,
                                  v62[0],
                                  v63,
                                  *(_QWORD *)a1[3],
                                  a1[5]) )
          {
            ++*(_DWORD *)(a1[5] + 108);
          }
          else
          {
            wil::com_ptr_t<DataStoreCache::IDataItem,wil::err_exception_policy>::query<DataStoreCache::IDataUpdate>(
              &v58,
              &v50);
            v37 = v50;
            v38 = *(void (__fastcall **)(HSTRING, __int64, _QWORD, unsigned __int64))(*(_QWORD *)v50 + 24LL);
            v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*a1 + 24) + 48LL))(*a1 + 24);
            v38(v37, v39, 0, ((unsigned __int64)v27 + 8) & -(__int64)(v27 != 0));
            ++*(_DWORD *)(a1[5] + 96);
            wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v50);
          }
          Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v50, *a1 + 128);
          v40 = *a1;
          v41 = WindowsGetStringRawBuffer(v51, 0);
          std::wstring::wstring(v64, v41);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Erase<std::wstring>(
            v40 + 160,
            v64);
          std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v64);
          if ( v50 )
            ReleaseSRWLockExclusive((PSRWLOCK)v50);
          if ( *(_BYTE *)a1[6] )
          {
            v42 = (*(__int64 (__fastcall **)(struct Windows::Services::TargetedContent::ITargetedContentItem *, _QWORD))(*(_QWORD *)v55 + 56LL))(
                    v55,
                    0);
            if ( v42 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x554,
                (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targete"
                              "dcontenttransformer.cpp",
                (const char *)(unsigned int)v42,
                bIgnoreCasec);
          }
          wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v58);
          WindowsDeleteString(v51);
          v51 = 0;
          DataStoreCache::TargetedContentTransformer::UpdateContext::~UpdateContext((DataStoreCache::TargetedContentTransformer::UpdateContext *)v62);
          wil::com_ptr_t<DataStoreCache::PropertyBagLookaside,wil::err_exception_policy>::~com_ptr_t<DataStoreCache::PropertyBagLookaside,wil::err_exception_policy>(&v61);
          wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v55);
        }
        v43 = WindowsGetStringRawBuffer(v52, 0);
        DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem::Stop(
          (DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem *)v65,
          v43);
        wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v56);
        WindowsDeleteString(v52);
        v52 = 0;
        DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem::~TargetedContentTransformer_UpdateDataItem((DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem *)v65);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x559,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\targetedcontenttransformer\\lib\\targetedconte"
                        "nttransformer.cpp",
          v44);
      }
    }
    WindowsDeleteString(string);
  }
  else
  {
    DataStoreTransformerTelemetry::TargetedContentTransformer_SkippingTileNotInCollection<unsigned short const * &>(&v59);
  }
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v60);
  return 1;
}

```

## disassembly

```asm
0x180375e00  mov     [rsp+arg_18], rbx
0x180375e05  push    rsi
0x180375e06  push    rdi
0x180375e07  push    r12
0x180375e09  push    r14
0x180375e0b  push    r15
0x180375e0d  sub     rsp, 240h
0x180375e14  mov     rax, cs:__security_cookie
0x180375e1b  xor     rax, rsp
0x180375e1e  mov     [rsp+268h+var_38], rax
0x180375e26  mov     r15, r8
0x180375e29  mov     r14, rcx
0x180375e2c  mov     [rsp+268h+var_1F0], rdx
0x180375e31  mov     r8, [rcx+8]
0x180375e35  mov     r9, rdx
0x180375e38  mov     r8, [r8]
0x180375e3b  lea     rdx, [rsp+268h+var_1F8]
0x180375e40  mov     rcx, [rcx]
0x180375e43  call    ?ComputeTileIdentifier@TargetedContentTransformer@DataStoreCache@@AEBA?AV?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_exception_policy@wil@@@wil@@PEBG0@Z; DataStoreCache::TargetedContentTransformer::ComputeTileIdentifier(ushort const *,ushort const *)
0x180375e48  mov     rdi, [rax]
0x180375e4b  xor     r12d, r12d
0x180375e4e  mov     [rax], r12
0x180375e51  mov     [rsp+268h+var_1E8], rdi
0x180375e59  lea     rcx, [rsp+268h+var_1F8]; void *
0x180375e5e  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180375e63  mov     rax, [r14+10h]
0x180375e67  cmp     [rax], r12
0x180375e6a  jz      short loc_180375E9F
0x180375e6c  mov     rbx, [r14]
0x180375e6f  lea     rdx, [rsp+268h+var_1E8]
0x180375e77  lea     rcx, [rsp+268h+var_238]
0x180375e7c  call    ??0?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_returncode_policy>::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_returncode_policy>(wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_returncode_policy> const &)
0x180375e81  mov     r8, rax
0x180375e84  mov     rcx, rbx
0x180375e87  call    ?IsTilePinnedToStart@TargetedContentTransformer@DataStoreCache@@AEAA_NPEAUICuratedTileCollection@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@V?$com_ptr_t@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@Uerr_returncode_policy@wil@@@wil@@@Z; DataStoreCache::TargetedContentTransformer::IsTilePinnedToStart(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::ICuratedTileCollection *,wil::com_ptr_t<WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,wil::err_returncode_policy>)
0x180375e8c  test    al, al
0x180375e8e  jnz     short loc_180375E9F
0x180375e90  lea     rcx, [rsp+268h+var_1F0]
0x180375e95  call    ??$TargetedContentTransformer_SkippingTileNotInCollection@AEAPEBG@DataStoreTransformerTelemetry@@SAXAEAPEBG@Z; DataStoreTransformerTelemetry::TargetedContentTransformer_SkippingTileNotInCollection<ushort const * &>(ushort const * &)
0x180375e9a  jmp     loc_180376362
0x180375e9f  mov     [rsp+268h+string], r12
0x180375ea4  mov     rax, [r15]
0x180375ea7  mov     rbx, [rax+38h]
0x180375eab  xor     ecx, ecx; string
0x180375ead  call    cs:__imp_WindowsDeleteString
0x180375eb3  mov     [rsp+268h+string], r12
0x180375eb8  lea     rdx, [rsp+268h+string]
0x180375ebd  mov     rcx, r15
0x180375ec0  mov     rax, rbx
0x180375ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180375ec8  mov     rcx, [rsp+268h]; this
0x180375ed0  test    eax, eax
0x180375ed2  js      loc_180376399
0x180375ed8  mov     rcx, [rsp+268h+string]; string
0x180375edd  call    cs:__imp_WindowsGetStringLen
0x180375ee3  mov     ebx, eax
0x180375ee5  xor     edx, edx; length
0x180375ee7  mov     rcx, [rsp+268h+string]; string
0x180375eec  call    cs:__imp_WindowsGetStringRawBuffer
0x180375ef2  mov     rcx, [r14+18h]
0x180375ef6  mov     [rsp+268h+bIgnoreCase], 1; int
0x180375efe  mov     r9d, ebx; cchCount2
0x180375f01  mov     r8, rax; lpString2
0x180375f04  or      edx, 0FFFFFFFFh; cchCount1
0x180375f07  mov     rcx, [rcx]; lpString1
0x180375f0a  call    cs:__imp_CompareStringOrdinal
0x180375f10  cmp     eax, 2
0x180375f13  jnz     loc_180376356
0x180375f19  mov     rbx, [r14+18h]
0x180375f1d  mov     rsi, [r14+8]
0x180375f21  lea     rdx, aTargetedconten_5; "TargetedContentTransformer_UpdateDataIt"...
0x180375f28  lea     rcx, [rsp+268h+var_188]; struct wil::details::IFailureCallback *
0x180375f30  call    ??0?$ActivityBase@VDataStoreTransformerLogging@@$00$0A@$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DataStoreTransformerLogging,1,0,4,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180375f35  lea     rax, ??_7TargetedContentTransformer_UpdateDataItem@DataStoreTransformerTelemetry@@6B@; const DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem::`vftable'
0x180375f3c  mov     [rsp+268h+var_188], rax
0x180375f44  mov     r9, [rsp+268h+var_1F0]; unsigned __int16 *
0x180375f49  mov     r8, [rbx]; unsigned __int16 *
0x180375f4c  mov     rdx, [rsi]; unsigned __int16 *
0x180375f4f  lea     rcx, [rsp+268h+var_188]; this
0x180375f57  call    ?StartActivity@TargetedContentTransformer_UpdateDataItem@DataStoreTransformerTelemetry@@QEAAXPEBG00@Z; DataStoreTransformerTelemetry::TargetedContentTransformer_UpdateDataItem::StartActivity(ushort const *,ushort const *,ushort const *)
0x180375f5c  nop
0x180375f5d  mov     [rsp+268h+var_228], r12
0x180375f62  mov     rax, [r15]
0x180375f65  mov     rbx, [rax+40h]
0x180375f69  xor     ecx, ecx; string
0x180375f6b  call    cs:__imp_WindowsDeleteString
0x180375f71  mov     [rsp+268h+var_228], r12
0x180375f76  lea     rdx, [rsp+268h+var_228]
0x180375f7b  mov     rcx, r15
0x180375f7e  mov     rax, rbx
0x180375f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180375f86  mov     rcx, [rsp+268h]; this
0x180375f8e  test    eax, eax
0x180375f90  js      loc_1803763AE
0x180375f96  mov     [rsp+268h+var_208], r12
0x180375f9b  mov     rax, [r14+20h]
0x180375f9f  mov     rcx, [rax]
0x180375fa2  mov     rax, [rcx]
0x180375fa5  mov     [rsp+268h+var_208], r12
0x180375faa  lea     r8, [rsp+268h+var_208]
0x180375faf  mov     rdx, [rsp+268h+var_228]
0x180375fb4  mov     rax, [rax+50h]
0x180375fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180375fbd  mov     rcx, [rsp+268h]; this
0x180375fc5  test    eax, eax
0x180375fc7  js      loc_1803763C3
0x180375fcd  mov     [rsp+268h+var_218], r12d
0x180375fd2  mov     rcx, [rsp+268h+var_208]
0x180375fd7  mov     rax, [rcx]
0x180375fda  lea     rdx, [rsp+268h+var_218]
0x180375fdf  mov     rax, [rax+30h]
0x180375fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180375fe8  mov     rcx, [rsp+268h]; this
0x180375ff0  test    eax, eax
0x180375ff2  js      loc_1803763D7
0x180375ff8  cmp     [rsp+268h+var_218], 1
0x180375ffd  jnz     loc_18037630F
0x180376003  mov     [rsp+268h+var_210], r12
0x180376008  mov     rcx, [rsp+268h+var_208]
0x18037600d  mov     rax, [rcx]
0x180376010  mov     [rsp+268h+var_210], r12
0x180376015  lea     rdx, [rsp+268h+var_210]
0x18037601a  mov     rax, [rax+40h]
0x18037601e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180376023  mov     rcx, [rsp+268h]; this
0x18037602b  test    eax, eax
0x18037602d  js      loc_1803763EC
0x180376033  mov     rbx, [r14]
0x180376036  lea     rcx, [rbx+18h]
0x18037603a  mov     rax, [rcx]
0x18037603d  mov     rax, [rax+30h]
0x180376041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180376046  lea     r8, [rbx+68h]
0x18037604a  mov     rdx, rax
0x18037604d  lea     rcx, [rsp+268h+var_200]
0x180376052  call    ??$MakeOrThrow@VPropertyBagLookaside@DataStoreCache@@AEBU_GUID@@AEAV?$vector@PEBUDataStorePropertyIdentifier@DataStoreCache@@V?$allocator@PEBUDataStorePropertyIdentifier@DataStoreCache@@@std@@@std@@@wil@@YA?AV?$ComPtr@VPropertyBagLookaside@DataStoreCache@@@WRL@Microsoft@@AEBU_GUID@@AEAV?$vector@PEBUDataStorePropertyIdentifier@DataStoreCache@@V?$allocator@PEBUDataStorePropertyIdentifier@DataStoreCache@@@std@@@std@@@Z; wil::MakeOrThrow<DataStoreCache::PropertyBagLookaside,_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &>(_GUID const &,std::vector<DataStoreCache::DataStorePropertyIdentifier const *> &)
0x180376057  mov     rbx, [rax]
0x18037605a  mov     [rax], r12
0x18037605d  mov     [rsp+268h+var_1E0], rbx
0x180376065  mov     rcx, [rsp+268h+var_200]
0x18037606a  test    rcx, rcx
0x18037606d  jz      short loc_180376079
0x18037606f  mov     [rsp+268h+var_200], r12
0x180376074  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDataStorePropertyBag@DataStoreCache@@UIPropertyBagLookasidePrivate@5@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,DataStoreCache::IDataStorePropertyBag,DataStoreCache::IPropertyBagLookasidePrivate>::Release(void)
0x180376079  mov     rax, [r14+20h]
0x18037607d  mov     rcx, [rax]
0x180376080  mov     qword ptr [rsp+268h+bIgnoreCase], rcx; int
0x180376085  mov     r9, rbx; struct DataStoreCache::PropertyBagLookaside *
0x180376088  mov     r8, [rsp+268h+string]; HSTRING
0x18037608d  mov     rdx, [rsp+268h+var_210]; struct Windows::Services::TargetedContent::ITargetedContentItem *
0x180376092  lea     rcx, [rsp+268h+var_1D8]; this
0x18037609a  call    ??0UpdateContext@TargetedContentTransformer@DataStoreCache@@QEAA@PEAUITargetedContentItem@TargetedContent@Services@Windows@@PEAUHSTRING__@@PEAVPropertyBagLookaside@2@PEAUITargetedContentContainer@456@@Z; DataStoreCache::TargetedContentTransformer::UpdateContext::UpdateContext(Windows::Services::TargetedContent::ITargetedContentItem *,HSTRING__ *,DataStoreCache::PropertyBagLookaside *,Windows::Services::TargetedContent::ITargetedContentContainer *)
0x18037609f  nop
0x1803760a0  lea     rcx, [rsp+268h+var_1D8]; struct DataStoreCache::TargetedContentTransformer::UpdateContext *
0x1803760a8  call    ?AddTileBasicInfo@TargetedContentTransformer@DataStoreCache@@CAXAEAUUpdateContext@12@@Z; DataStoreCache::TargetedContentTransformer::AddTileBasicInfo(DataStoreCache::TargetedContentTransformer::UpdateContext &)
0x1803760ad  mov     rax, [r14]
0x1803760b0  mov     rsi, [rax+68h]
0x1803760b4  mov     r15, [rax+70h]
0x1803760b8  cmp     rsi, r15
0x1803760bb  jz      short loc_1803760D3
0x1803760bd  lea     rdx, [rsp+268h+var_1D8]; struct DataStoreCache::TargetedContentTransformer::UpdateContext *
0x1803760c5  mov     rcx, [rsi]; struct DataStoreCache::DataStorePropertyIdentifier *
0x1803760c8  call    ?AddTileProperty@TargetedContentTransformer@DataStoreCache@@CAXAEBUDataStorePropertyIdentifier@2@AEAUUpdateContext@12@@Z; DataStoreCache::TargetedContentTransformer::AddTileProperty(DataStoreCache::DataStorePropertyIdentifier const &,DataStoreCache::TargetedContentTransformer::UpdateContext &)
0x1803760cd  add     rsi, 8
0x1803760d1  jmp     short loc_1803760B8
0x1803760d3  mov     [rsp+268h+var_230], r12
0x1803760d8  mov     rax, [rdi]
0x1803760db  mov     rsi, [rax+38h]
0x1803760df  xor     ecx, ecx; string
0x1803760e1  call    cs:__imp_WindowsDeleteString
0x1803760e7  mov     [rsp+268h+var_230], r12
0x1803760ec  lea     rdx, [rsp+268h+var_230]
0x1803760f1  mov     rcx, rdi
0x1803760f4  mov     rax, rsi
0x1803760f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803760fc  mov     rcx, [rsp+268h]; this
0x180376104  test    eax, eax
0x180376106  js      loc_180376401
0x18037610c  mov     rax, [r14]
0x18037610f  mov     rcx, [rax+98h]
0x180376116  mov     rax, [rcx]
0x180376119  mov     r8, [rsp+268h+var_230]
0x18037611e  lea     rdx, [rsp+268h+var_200]
0x180376123  mov     rax, [rax+28h]
0x180376127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037612c  mov     rdi, [rax]
0x18037612f  mov     [rax], r12
0x180376132  mov     [rsp+268h+var_1F8], rdi
0x180376137  mov     rcx, [rsp+268h+var_200]
0x18037613c  test    rcx, rcx
0x18037613f  jz      short loc_180376153
0x180376141  mov     [rsp+268h+var_200], r12
0x180376146  mov     rax, [rcx]
0x180376149  mov     rax, [rax+10h]
0x18037614d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180376152  nop
0x180376153  mov     rcx, [r14]
0x180376156  cmp     [rcx+0F8h], r12
0x18037615d  jz      short loc_18037619A
0x18037615f  lea     rdx, [rsp+268h+var_238]
0x180376164  call    ?GetContentDeliveryManagerPackageFullName@TargetedContentTransformer@DataStoreCache@@AEAA?AVHString@Wrappers@WRL@Microsoft@@XZ; DataStoreCache::TargetedContentTransformer::GetContentDeliveryManagerPackageFullName(void)
0x180376169  nop
0x18037616a  mov     rax, [r14]
0x18037616d  mov     rcx, [rax+0F8h]
0x180376174  mov     rax, [rcx]
0x180376177  mov     r9, [rsp+268h+var_238]
0x18037617c  mov     r8d, 1
0x180376182  mov     rdx, rdi
0x180376185  mov     rax, [rax+30h]
0x180376189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18037618e  nop
0x18037618f  mov     rcx, [rsp+268h+var_238]; string
0x180376194  call    cs:__imp_WindowsDeleteString
0x18037619a  mov     r9, [r14+18h]
0x18037619e  mov     rax, [r14+28h]
0x1803761a2  mov     qword ptr [rsp+268h+bIgnoreCase], rax; int
0x1803761a7  mov     r9, [r9]
0x1803761aa  mov     r8, [rsp+268h+var_1C0]
0x1803761b2  mov     rdx, qword ptr [rsp+268h+var_1D8]
0x1803761ba  call    ?TrySwapTile@TargetedContentTransformer@DataStoreCache@@AEAA_NPEAUITargetedContentItem@TargetedContent@Services@Windows@@PEAU?$IMapView@PEAUHSTRING__@@PEAVTargetedContentValue@TargetedContent@Services@Windows@@@Collections@Foundation@6@PEBGPEAUPlaceholderContext@12@@Z; DataStoreCache::TargetedContentTransformer::TrySwapTile(Windows::Services::TargetedContent::ITargetedContentItem *,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Services::TargetedContent::TargetedContentValue *> *,ushort const *,DataStoreCache::TargetedContentTransformer::PlaceholderContext *)
0x1803761bf  test    al, al
0x1803761c1  jnz     short loc_180376226
0x1803761c3  lea     rdx, [rsp+268h+var_238]
0x1803761c8  lea     rcx, [rsp+268h+var_1F8]
0x1803761cd  call    ??$query@UIDataUpdate@DataStoreCache@@@?$com_ptr_t@UIDataItem@DataStoreCache@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIDataUpdate@DataStoreCache@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<DataStoreCache::IDataItem,wil::err_exception_policy>::query<DataStoreCache::IDataUpdate>(void)
0x1803761d2  nop
0x1803761d3  mov     rdi, [rsp+268h+var_238]
0x1803761d8  mov     rax, [rdi]
0x1803761db  mov     rsi, [rax+18h]
0x1803761df  lea     rax, [rbx+8]
0x1803761e3  neg     rbx
0x1803761e6  sbb     rbx, rbx
0x1803761e9  and     rbx, rax
0x1803761ec  mov     rcx, [r14]
0x1803761ef  add     rcx, 18h
0x1803761f3  mov     rdx, [rcx]
0x1803761f6  mov     rax, [rdx+30h]
0x1803761fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803761ff  mov     r9, rbx
0x180376202  xor     r8d, r8d
0x180376205  mov     rdx, rax
0x180376208  mov     rcx, rdi
0x18037620b  mov     rax, rsi
0x18037620e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180376213  mov     rax, [r14+28h]
0x180376217  inc     dword ptr [rax+60h]
0x18037621a  lea     rcx, [rsp+268h+var_238]; void *
0x18037621f  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x180376224  jmp     short loc_18037622D
0x180376226  mov     rax, [r14+28h]
0x18037622a  inc     dword ptr [rax+6Ch]
0x18037622d  mov     rdx, [r14]
0x180376230  sub     rdx, 0FFFFFFFFFFFFFF80h
0x180376234  lea     rcx, [rsp+268h+var_238]
0x180376239  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18037623e  nop
0x18037623f  mov     rbx, [r14]
0x180376242  xor     edx, edx; length
0x180376244  mov     rcx, [rsp+268h+var_230]; string
0x180376249  call    cs:__imp_WindowsGetStringRawBuffer
0x18037624f  mov     rdx, rax
0x180376252  lea     rcx, [rsp+268h+var_1B0]
0x18037625a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18037625f  lea     rdx, [rsp+268h+var_1B0]
0x180376267  lea     rcx, [rbx+0A0h]
0x18037626e  call    ??$_Erase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@AEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Erase<std::wstring>(std::wstring const &)
0x180376273  lea     rcx, [rsp+268h+var_1B0]; void *
0x18037627b  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x180376280  nop
0x180376281  mov     rcx, [rsp+268h+var_238]; SRWLock
0x180376286  test    rcx, rcx
0x180376289  jz      short loc_180376291
0x18037628b  call    cs:__imp_ReleaseSRWLockExclusive
0x180376291  mov     rax, [r14+30h]
0x180376295  cmp     [rax], r12b
0x180376298  jz      short loc_1803762CE
0x18037629a  mov     rcx, [rsp+268h+var_210]
0x18037629f  mov     rax, [rcx]
0x1803762a2  xor     edx, edx
0x1803762a4  mov     rax, [rax+38h]
0x1803762a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803762ad  mov     rcx, [rsp+268h]; this
0x1803762b5  test    eax, eax
0x1803762b7  jns     short loc_1803762CE
0x1803762b9  mov     r9d, eax; char *
0x1803762bc  lea     r8, aShellcommonShe_103; "shellcommon\\shell\\datastorecache\\tra"...
0x1803762c3  mov     edx, 554h; void *
0x1803762c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1803762cd  nop
0x1803762ce  lea     rcx, [rsp+268h+var_1F8]; void *
0x1803762d3  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1803762d8  nop
0x1803762d9  mov     rcx, [rsp+268h+var_230]; string
0x1803762de  call    cs:__imp_WindowsDeleteString
0x1803762e4  mov     [rsp+268h+var_230], r12
0x1803762e9  lea     rcx, [rsp+268h+var_1D8]; this
0x1803762f1  call    ??1UpdateContext@TargetedContentTransformer@DataStoreCache@@QEAA@XZ; DataStoreCache::TargetedContentTransformer::UpdateContext::~UpdateContext(void)
0x1803762f6  nop
0x1803762f7  lea     rcx, [rsp+268h+var_1E0]
0x1803762ff  call    ??1?$com_ptr_t@VPropertyBagLookaside@DataStoreCache@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<DataStoreCache::PropertyBagLookaside,wil::err_exception_policy>::~com_ptr_t<DataStoreCache::PropertyBagLookaside,wil::err_exception_policy>(void)
  ... truncated ...
```
