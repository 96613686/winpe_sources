# SyncProviderTelemetryHelpers::GetProviderNameAndInfoFlags(IShellItem *,ushort * *,STORAGE_PROVIDER_INFO_FLAGS *)

- ea: `0x180018e38`
- end: `0x1800191a2`
- name: `?GetProviderNameAndInfoFlags@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAGPEAW4STORAGE_PROVIDER_INFO_FLAGS@@@Z`
- size: `874`
- prototype: `__int64 __fastcall(struct IShellItem *, unsigned __int16 **, enum STORAGE_PROVIDER_INFO_FLAGS *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001b1f8`

## callees

- `0x1800033d0`
- `0x1800049e0`
- `0x1800054dc`
- `0x180006218`
- `0x1800063b4`
- `0x180011a34`
- `0x1800133a4`
- `0x180018e38`
- `0x18001966c`
- `0x180019f70`
- `0x180021460`
- `0x180021ad4`
- `0x180051010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018f80`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180018f80`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800190a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019049`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800190a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019112`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019128`

## string_xrefs

- `0x180018ee9`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180019064`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x1800190e8`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180019169`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall SyncProviderTelemetryHelpers::GetProviderNameAndInfoFlags(
        struct IShellItem *a1,
        unsigned __int16 **a2,
        enum STORAGE_PROVIDER_INFO_FLAGS *a3)
{
  int StorageProviderInfo; // ebx
  struct IStorageProviderInfo *v8; // rdi
  int (__fastcall *v9)(struct IStorageProviderInfo *, LPVOID *); // rbx
  int v10; // eax
  __int64 v11; // rdx
  void *v12; // rbx
  _WORD *v13; // rdi
  const char *v14; // r9
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, LPVOID *); // rbx
  int v17; // eax
  void *v18; // rcx
  wchar_t *v19; // rdx
  int v20; // eax
  int v21; // edi
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // [rsp+20h] [rbp-40h] BYREF
  void *v25; // [rsp+28h] [rbp-38h] BYREF
  __int64 v26; // [rsp+30h] [rbp-30h] BYREF
  _WORD *v27; // [rsp+38h] [rbp-28h] BYREF
  PROPERTYKEY v28; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF
  struct IStorageProviderInfo *v31; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID v32; // [rsp+B8h] [rbp+58h] BYREF

  *a2 = 0;
  *(_DWORD *)a3 = 0;
  if ( !Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered((Windows::Internal::SyncRootHelpers *)a1) )
    return 2147943568LL;
  v31 = 0;
  StorageProviderInfo = SyncProviderTelemetryHelpers::GetStorageProviderInfo(a1, &v31);
  if ( StorageProviderInfo >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl'::`2'::impl) )
    {
      pv = 0;
      v8 = v31;
      v9 = *(int (__fastcall **)(struct IStorageProviderInfo *, LPVOID *))(*(_QWORD *)v31 + 40LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pv,
        0);
      if ( v9(v8, &pv) < 0 )
      {
        v24 = 0;
        v10 = wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v24, a1);
        StorageProviderInfo = v10;
        if ( v10 < 0 )
        {
          v11 = 297;
LABEL_8:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v11,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
            (const char *)(unsigned int)v10,
            v24);
          Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(&v24);
LABEL_9:
          if ( pv )
            CoTaskMemFree(pv);
          goto LABEL_44;
        }
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        v28 = PKEY_StorageProviderId;
        v10 = wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v24, &v28, &pv);
        StorageProviderInfo = v10;
        if ( v10 < 0 )
        {
          v11 = 298;
          goto LABEL_8;
        }
        Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(&v24);
      }
      v12 = 0;
      v25 = 0;
      if ( pv )
      {
        if ( (unsigned int)_o__wcsicmp(pv, L"OneDrive") )
        {
          if ( pv )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v25,
              &pv);
            v12 = v25;
          }
        }
        else
        {
          v13 = 0;
          v27 = 0;
          v26 = 0;
          if ( (**(int (__fastcall ***)(struct IStorageProviderInfo *, GUID *, __int64 *))v31)(
                 v31,
                 &GUID_4905f136_1f36_4b43_bbcb_fb93964639cd,
                 &v26) < 0 )
            goto LABEL_24;
          v32 = 0;
          v15 = v26;
          v16 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v26 + 40LL);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v32,
            0);
          v17 = v16(v15, &v32);
          v18 = v32;
          if ( v17 >= 0 && v32 )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              &v27,
              &v32);
            v13 = v27;
            v18 = v32;
          }
          if ( v18 )
            CoTaskMemFree(v18);
          if ( !v13 || (v19 = L"OneDrive Business", !*v13) )
LABEL_24:
            v19 = L"OneDrive Consumer";
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &v32,
            (char *)v19,
            0xFFFFFFFFFFFFFFFFuLL,
            v14);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v25,
            &v32);
          if ( v32 )
            CoTaskMemFree(v32);
          v12 = v25;
          if ( !v25 )
          {
            StorageProviderInfo = -2147024882;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x147,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
              (const char *)0x8007000ELL,
              v24);
            ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v26);
            if ( v13 )
              CoTaskMemFree(v13);
            goto LABEL_9;
          }
          ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(&v26);
          if ( v13 )
            CoTaskMemFree(v13);
        }
      }
      v20 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, enum STORAGE_PROVIDER_INFO_FLAGS *))(*(_QWORD *)v31 + 168LL))(
              v31,
              a3);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x14E,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
          (const char *)(unsigned int)v20,
          v24);
        if ( v12 )
          CoTaskMemFree(v12);
        if ( pv )
          CoTaskMemFree(pv);
        StorageProviderInfo = v21;
        goto LABEL_44;
      }
      *a2 = (unsigned __int16 *)v12;
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_43;
    }
    v22 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, unsigned __int16 **))(*(_QWORD *)v31 + 40LL))(
            v31,
            a2);
    StorageProviderInfo = v22;
    if ( v22 >= 0 )
    {
      v22 = (*(__int64 (__fastcall **)(struct IStorageProviderInfo *, enum STORAGE_PROVIDER_INFO_FLAGS *))(*(_QWORD *)v31 + 168LL))(
              v31,
              a3);
      StorageProviderInfo = v22;
      if ( v22 >= 0 )
      {
LABEL_43:
        StorageProviderInfo = 0;
        goto LABEL_44;
      }
      v23 = 343;
    }
    else
    {
      v23 = 341;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
      (const char *)(unsigned int)v22,
      v24);
  }
LABEL_44:
  ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>((__int64 *)&v31);
  return (unsigned int)StorageProviderInfo;
}

```

## disassembly

```asm
0x180018e38  push    rbp
0x180018e3a  push    rbx
0x180018e3b  push    rsi
0x180018e3c  push    rdi
0x180018e3d  push    r12
0x180018e3f  push    r14
0x180018e41  push    r15
0x180018e43  mov     rbp, rsp
0x180018e46  sub     rsp, 60h
0x180018e4a  mov     r15, r8
0x180018e4d  mov     r14, rdx
0x180018e50  mov     rsi, rcx
0x180018e53  xor     r12d, r12d
0x180018e56  mov     [rdx], r12
0x180018e59  mov     [r8], r12d
0x180018e5c  call    ?AreAnyStorageProvidersRegistered@SyncRootHelpers@Internal@Windows@@YA_NXZ; Windows::Internal::SyncRootHelpers::AreAnyStorageProvidersRegistered(void)
0x180018e61  test    al, al
0x180018e63  jnz     short loc_180018E6F
0x180018e65  mov     eax, 80070490h
0x180018e6a  jmp     loc_18001913C
0x180018e6f  mov     [rbp+arg_10], r12
0x180018e73  lea     rdx, [rbp+arg_10]; struct IStorageProviderInfo **
0x180018e77  mov     rcx, rsi; struct IShellItem *
0x180018e7a  call    ?GetStorageProviderInfo@SyncProviderTelemetryHelpers@@SAJPEAUIShellItem@@PEAPEAUIStorageProviderInfo@@@Z; SyncProviderTelemetryHelpers::GetStorageProviderInfo(IShellItem *,IStorageProviderInfo * *)
0x180018e7f  mov     ebx, eax
0x180018e81  test    eax, eax
0x180018e83  js      loc_180019131
0x180018e89  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56314744@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744> `wil::Feature<__WilFeatureTraits_Feature_56314744>::GetImpl(void)'::`2'::impl
0x180018e90  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56314744@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56314744>::__private_IsEnabled(wil::ReportingKind)
0x180018e95  test    al, al
0x180018e97  jz      loc_18001914B
0x180018e9d  mov     [rbp+pv], r12
0x180018ea1  mov     rdi, [rbp+arg_10]
0x180018ea5  mov     rax, [rdi]
0x180018ea8  mov     rbx, [rax+28h]
0x180018eac  xor     edx, edx
0x180018eae  lea     rcx, [rbp+pv]
0x180018eb2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018eb7  lea     rdx, [rbp+pv]
0x180018ebb  mov     rcx, rdi
0x180018ebe  mov     rax, rbx
0x180018ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ec6  test    eax, eax
0x180018ec8  jns     loc_180018F65
0x180018ece  mov     [rbp+var_40], r12
0x180018ed2  mov     rdx, rsi
0x180018ed5  lea     rcx, [rbp+var_40]
0x180018ed9  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x180018ede  mov     ebx, eax
0x180018ee0  test    eax, eax
0x180018ee2  jns     short loc_180018F1F
0x180018ee4  mov     edx, 129h; void *
0x180018ee9  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180018ef0  mov     r9d, eax; char *
0x180018ef3  mov     rcx, [rbp+38h]; this
0x180018ef7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018efc  nop
0x180018efd  lea     rcx, [rbp+var_40]
0x180018f01  call    ??1?$ComPtr@UIDBFolderPriv@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(void)
0x180018f06  nop
0x180018f07  mov     rcx, [rbp+pv]; pv
0x180018f0b  test    rcx, rcx
0x180018f0e  jz      loc_180019131
0x180018f14  call    cs:__imp_CoTaskMemFree
0x180018f1a  jmp     loc_180019131
0x180018f1f  xor     edx, edx
0x180018f21  lea     rcx, [rbp+pv]
0x180018f25  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018f2a  movups  xmm0, xmmword ptr cs:PKEY_StorageProviderId.fmtid.Data1
0x180018f31  movaps  [rbp+var_20], xmm0
0x180018f35  mov     eax, cs:PKEY_StorageProviderId.pid
0x180018f3b  mov     [rbp+var_10], eax
0x180018f3e  lea     r8, [rbp+pv]
0x180018f42  lea     rdx, [rbp+var_20]
0x180018f46  lea     rcx, [rbp+var_40]
0x180018f4a  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180018f4f  mov     ebx, eax
0x180018f51  test    eax, eax
0x180018f53  jns     short loc_180018F5C
0x180018f55  mov     edx, 12Ah
0x180018f5a  jmp     short loc_180018EE9
0x180018f5c  lea     rcx, [rbp+var_40]
0x180018f60  call    ??1?$ComPtr@UIDBFolderPriv@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(void)
0x180018f65  mov     rbx, r12
0x180018f68  mov     [rbp+var_38], rbx
0x180018f6c  mov     rcx, [rbp+pv]
0x180018f70  test    rcx, rcx
0x180018f73  jz      loc_1800190C5
0x180018f79  lea     rdx, aOnedrive_1; "OneDrive"
0x180018f80  call    cs:__imp__o__wcsicmp
0x180018f86  test    eax, eax
0x180018f88  jnz     loc_1800190AE
0x180018f8e  mov     rdi, r12
0x180018f91  mov     [rbp+var_28], r12
0x180018f95  mov     [rbp+var_30], r12
0x180018f99  mov     rcx, [rbp+arg_10]
0x180018f9d  mov     rax, [rcx]
0x180018fa0  lea     r8, [rbp+var_30]
0x180018fa4  lea     rdx, _GUID_4905f136_1f36_4b43_bbcb_fb93964639cd
0x180018fab  mov     rax, [rax]
0x180018fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fb3  test    eax, eax
0x180018fb5  js      short loc_18001901F
0x180018fb7  mov     [rbp+arg_18], r12
0x180018fbb  mov     rsi, [rbp+var_30]
0x180018fbf  mov     rax, [rsi]
0x180018fc2  mov     rbx, [rax+28h]
0x180018fc6  xor     edx, edx
0x180018fc8  lea     rcx, [rbp+arg_18]
0x180018fcc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180018fd1  lea     rdx, [rbp+arg_18]
0x180018fd5  mov     rcx, rsi
0x180018fd8  mov     rax, rbx
0x180018fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018fe0  mov     rcx, [rbp+arg_18]
0x180018fe4  test    eax, eax
0x180018fe6  js      short loc_180019002
0x180018fe8  test    rcx, rcx
0x180018feb  jz      short loc_180019002
0x180018fed  lea     rdx, [rbp+arg_18]
0x180018ff1  lea     rcx, [rbp+var_28]
0x180018ff5  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180018ffa  mov     rdi, [rbp+var_28]
0x180018ffe  mov     rcx, [rbp+arg_18]; pv
0x180019002  test    rcx, rcx
0x180019005  jz      short loc_18001900D
0x180019007  call    cs:__imp_CoTaskMemFree
0x18001900d  test    rdi, rdi
0x180019010  jz      short loc_18001901F
0x180019012  cmp     [rdi], r12w
0x180019016  lea     rdx, aOnedriveBusine; "OneDrive Business"
0x18001901d  jnz     short loc_180019026
0x18001901f  lea     rdx, aOnedriveConsum; "OneDrive Consumer"
0x180019026  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001902a  lea     rcx, [rbp+arg_18]
0x18001902e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180019033  lea     rdx, [rbp+arg_18]
0x180019037  lea     rcx, [rbp+var_38]
0x18001903b  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180019040  mov     rcx, [rbp+arg_18]; pv
0x180019044  test    rcx, rcx
0x180019047  jz      short loc_18001904F
0x180019049  call    cs:__imp_CoTaskMemFree
0x18001904f  mov     rbx, [rbp+var_38]
0x180019053  test    rbx, rbx
0x180019056  jnz     short loc_180019094
0x180019058  mov     rcx, [rbp+38h]; this
0x18001905c  mov     ebx, 8007000Eh
0x180019061  mov     r9d, ebx; char *
0x180019064  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18001906b  mov     edx, 147h; void *
0x180019070  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019075  nop
0x180019076  lea     rcx, [rbp+var_30]
0x18001907a  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x18001907f  nop
0x180019080  test    rdi, rdi
0x180019083  jz      short loc_18001908F
0x180019085  mov     rcx, rdi; pv
0x180019088  call    cs:__imp_CoTaskMemFree
0x18001908e  nop
0x18001908f  jmp     loc_180018F07
0x180019094  lea     rcx, [rbp+var_30]
0x180019098  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x18001909d  nop
0x18001909e  test    rdi, rdi
0x1800190a1  jz      short loc_1800190C5
0x1800190a3  mov     rcx, rdi; pv
0x1800190a6  call    cs:__imp_CoTaskMemFree
0x1800190ac  jmp     short loc_1800190C5
0x1800190ae  cmp     [rbp+pv], r12
0x1800190b2  jz      short loc_1800190C5
0x1800190b4  lea     rdx, [rbp+pv]
0x1800190b8  lea     rcx, [rbp+var_38]
0x1800190bc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800190c1  mov     rbx, [rbp+var_38]
0x1800190c5  mov     rcx, [rbp+arg_10]
0x1800190c9  mov     rax, [rcx]
0x1800190cc  mov     rdx, r15
0x1800190cf  mov     rax, [rax+0A8h]
0x1800190d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190db  mov     edi, eax
0x1800190dd  test    eax, eax
0x1800190df  jns     short loc_18001911C
0x1800190e1  mov     rcx, [rbp+38h]; this
0x1800190e5  mov     r9d, eax; char *
0x1800190e8  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800190ef  mov     edx, 14Eh; void *
0x1800190f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800190f9  nop
0x1800190fa  test    rbx, rbx
0x1800190fd  jz      short loc_180019109
0x1800190ff  mov     rcx, rbx; pv
0x180019102  call    cs:__imp_CoTaskMemFree
0x180019108  nop
0x180019109  mov     rcx, [rbp+pv]; pv
0x18001910d  test    rcx, rcx
0x180019110  jz      short loc_180019118
0x180019112  call    cs:__imp_CoTaskMemFree
0x180019118  mov     ebx, edi
0x18001911a  jmp     short loc_180019131
0x18001911c  mov     [r14], rbx
0x18001911f  mov     rcx, [rbp+pv]; pv
0x180019123  test    rcx, rcx
0x180019126  jz      short loc_18001912E
0x180019128  call    cs:__imp_CoTaskMemFree
0x18001912e  mov     ebx, r12d
0x180019131  lea     rcx, [rbp+arg_10]
0x180019135  call    ??1?$CComPtrBase@UISearchIDListFactory@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ISearchIDListFactory>::~CComPtrBase<ISearchIDListFactory>(void)
0x18001913a  mov     eax, ebx
0x18001913c  add     rsp, 60h
0x180019140  pop     r15
0x180019142  pop     r14
0x180019144  pop     r12
0x180019146  pop     rdi
0x180019147  pop     rsi
0x180019148  pop     rbx
0x180019149  pop     rbp
0x18001914a  retn
0x18001914b  mov     rcx, [rbp+arg_10]
0x18001914f  mov     rax, [rcx]
0x180019152  mov     rdx, r14
0x180019155  mov     rax, [rax+28h]
0x180019159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001915e  mov     ebx, eax
0x180019160  test    eax, eax
0x180019162  jns     short loc_18001917E
0x180019164  mov     edx, 155h; void *
0x180019169  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180019170  mov     r9d, eax; char *
0x180019173  mov     rcx, [rbp+38h]; this
0x180019177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001917c  jmp     short loc_180019131
0x18001917e  mov     rcx, [rbp+arg_10]
0x180019182  mov     rax, [rcx]
0x180019185  mov     rdx, r15
0x180019188  mov     rax, [rax+0A8h]
0x18001918f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019194  mov     ebx, eax
0x180019196  test    eax, eax
0x180019198  jns     short loc_18001912E
0x18001919a  mov     edx, 157h
0x18001919f  jmp     short loc_180019169
```
