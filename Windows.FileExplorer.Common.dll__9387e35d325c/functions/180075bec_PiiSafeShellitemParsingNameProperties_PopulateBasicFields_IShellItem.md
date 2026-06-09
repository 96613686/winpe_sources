# PiiSafeShellitemParsingNameProperties::PopulateBasicFields(IShellItem *)

- ea: `0x180075bec`
- end: `0x180076217`
- name: `?PopulateBasicFields@PiiSafeShellitemParsingNameProperties@@AEAAXPEAUIShellItem@@@Z`
- size: `1579`
- prototype: `void(PiiSafeShellitemParsingNameProperties *__hidden this, struct IShellItem *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180071868`

## callees

- `0x180006a10`
- `0x180007900`
- `0x18000b9b0`
- `0x180015a1c`
- `0x18001d028`
- `0x18001f138`
- `0x1800309ec`
- `0x180030a20`
- `0x180031a24`
- `0x180031c54`
- `0x180035f08`
- `0x18003cccc`
- `0x180041334`
- `0x180043c98`
- `0x180071e38`
- `0x180072350`
- `0x180072f50`
- `0x180073db4`
- `0x180074098`
- `0x18007440c`
- `0x18007469c`
- `0x180074948`
- `0x1800751d0`
- `0x180075200`
- `0x180075364`
- `0x180075bec`
- `0x180076220`
- `0x180077568`
- `0x180077614`
- `0x18007768c`
- `0x180077ee8`
- `0x180077f60`
- `0x180089010`

## import_xrefs

- `Windows.Storage!ILIsEqual` at `0x1800761af`
- `Windows.Storage!ILIsEqual` at `0x1800761cd`
- `Windows.Storage!ILIsEqual` at `0x1800761af`
- `Windows.Storage!ILIsEqual` at `0x1800761cd`
- `Windows.Storage!SHGetIDListFromObject` at `0x180076148`
- `Windows.Storage!SHGetIDListFromObject` at `0x180076148`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180075e1d`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x180075e1d`

## string_xrefs

- `0x180075c79`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x180076159`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PiiSafeShellitemParsingNameProperties::PopulateBasicFields(
        PiiSafeShellitemParsingNameProperties *this,
        struct IShellItem *a2)
{
  char v4; // r14
  const unsigned __int16 *const *v5; // r15
  _WORD *v6; // rax
  unsigned __int8 v7; // al
  int v8; // eax
  struct IPropertyStore *v9; // rdx
  char v10; // r13
  char v11; // al
  char v12; // bl
  PiiSafeShellitemParsingNameProperties *v13; // rcx
  __int64 v14; // rbx
  unsigned __int8 LocalDiskLocation; // r12
  unsigned __int8 v16; // al
  unsigned int v17; // r14d
  size_t v18; // rdx
  __int64 RelativeToRootPath; // rax
  __int64 v20; // rcx
  __int64 v21; // rax
  const unsigned __int16 *InstanceOfChar; // rax
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  const unsigned __int16 *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  const struct _tagpropertykey *v29; // rdx
  __int64 v30; // r8
  double v31; // xmm0_8
  __int64 v32; // r8
  bool v33; // al
  HRESULT v34; // eax
  __int64 v35; // rcx
  unsigned __int8 RegistryRootLocation; // bl
  const ITEMIDLIST *HomePidl_NoThrow; // rbx
  const ITEMIDLIST *GalleryPidl_NoThrow; // rsi
  int v39; // [rsp+20h] [rbp-40h] BYREF
  double v40; // [rsp+28h] [rbp-38h] BYREF
  ITEMIDLIST *v41; // [rsp+30h] [rbp-30h] BYREF
  __int64 v42; // [rsp+38h] [rbp-28h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v44; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  LPCITEMIDLIST pidl2; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v47; // [rsp+B0h] [rbp+50h] BYREF
  PWSTR pszPath; // [rsp+B8h] [rbp+58h] BYREF

  v4 = 0;
  if ( !*((_BYTE *)this + 116) )
  {
    v5 = (const unsigned __int16 *const *)((char *)this + 88);
    v6 = (_WORD *)*((_QWORD *)this + 11);
    if ( v6 )
    {
      if ( *v6 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 28) - 100) <= 1 )
          v7 = -56;
        else
          v7 = PiiSafeShellitemParsingNameProperties::PopulateShellitemParsingNameRootType();
        *(_QWORD *)this |= (unsigned __int64)v7 << 52;
        v47 = 0;
        v8 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned int *))a2->lpVtbl->GetAttributes)(
               a2,
               2126589960,
               &v47);
        if ( v8 >= 0 )
        {
          LODWORD(pidl2) = 0;
          v10 = 1;
          if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPCITEMIDLIST *))a2->lpVtbl->GetAttributes)(
                 a2,
                 541065216,
                 &pidl2) >= 0
            && ((unsigned int)pidl2 & 0x20000000) != 0
            && ((unsigned int)pidl2 & 0x400000) == 0 )
          {
            LODWORD(pidl2) = 0;
            if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPCITEMIDLIST *))a2->lpVtbl->GetAttributes)(
                   a2,
                   541065216,
                   &pidl2) < 0
              || ((unsigned int)pidl2 & 0x20400000) != 0x20400000 )
            {
              v10 = 0;
            }
          }
          wil::PropertyStoreHelper::PropertyStoreHelper((wil::PropertyStoreHelper *)&v39, v9);
          if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v39, a2, 8) >= 0 )
          {
            LODWORD(pidl2) = 0;
            *(_OWORD *)ppidl = PKEY_Home_GraphFileType;
            LODWORD(v44) = 19;
            if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(&v39, ppidl, &pidl2) < 0
              || (v11 = 1, (unsigned int)((_DWORD)pidl2 - 1) > 1) )
            {
              v11 = 0;
            }
            *((_BYTE *)this + 81) = v11;
          }
          if ( *((_DWORD *)this + 28) == 10 || (v12 = 0, *((_DWORD *)this + 28) == 102) )
            v12 = 1;
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl'::`2'::impl)
            && *((_DWORD *)this + 28) == 101 )
          {
            v12 = 1;
          }
          if ( v12 )
          {
            v14 = -1;
            do
              ++v14;
            while ( (*v5)[v14] );
            LOBYTE(pidl2) = 0;
            if ( *((_DWORD *)this + 28) == 102 )
            {
              LocalDiskLocation = 119;
            }
            else
            {
              LocalDiskLocation = PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(
                                    (__int64)v13,
                                    v5,
                                    (unsigned __int8 *)&pidl2);
              v4 = (char)pidl2;
            }
            v16 = PiiSafeShellitemParsingNameProperties::CalculatePathDepth(v13, *v5, v10);
            *((_QWORD *)this + 1) |= (unsigned __int64)v47 << 32;
            v17 = (unsigned __int8)(v16 - v4);
            *(_QWORD *)this |= v16 | ((unsigned __int64)LocalDiskLocation << 40) | (v17 << 8);
            wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              &pszPath,
              *v5,
              -1);
            if ( v10 )
            {
              v18 = -1;
              do
                ++v18;
              while ( pszPath[v18] );
              PathCchRemoveFileSpec(pszPath, v18);
            }
            RelativeToRootPath = PiiSafeShellitemParsingNameProperties::GetRelativeToRootPath(
                                   &pidl2,
                                   &pszPath,
                                   (unsigned int)v14,
                                   v17);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              (char *)this + 96,
              RelativeToRootPath);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pidl2);
            v20 = *((_QWORD *)this + 12);
            if ( v20 )
            {
              v21 = -1;
              do
                ++v21;
              while ( *(_WORD *)(v20 + 2 * v21) );
              *(_QWORD *)this |= (unsigned __int16)v21 << 16;
              *((_QWORD *)this + 9) |= PiiSafeShellitemParsingNameProperties::GetKeywords(v20, (char *)this + 96) << 32;
            }
            if ( v10 )
            {
              InstanceOfChar = PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(*v5, 0x5Cu);
              v23 = details::safemake_cotaskmem_string_nothrow(&pidl2, InstanceOfChar);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                (char *)this + 104,
                v23);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pidl2);
              v24 = *((_QWORD *)this + 13);
              if ( v24 )
              {
                v25 = -1;
                do
                  ++v25;
                while ( *(_WORD *)(v24 + 2 * v25) );
                *((_QWORD *)this + 1) |= (unsigned __int16)v25;
                v26 = PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(*v5, 0x2Eu);
                if ( v26 )
                {
                  ppidl[0] = 0;
                  ppidl[1] = 0;
                  v44 = 0;
                  v28 = -1;
                  do
                    ++v28;
                  while ( v26[v28] );
                  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                              ppidl,
                              L"%lu:%.4s",
                              v28,
                              v26) >= 0 )
                  {
                    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                      &pidl2,
                      ppidl[0],
                      -1);
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                      (char *)this + 16,
                      &pidl2);
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pidl2);
                  }
                  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
                }
                *((_QWORD *)this + 9) |= PiiSafeShellitemParsingNameProperties::GetKeywords(v27, (char *)this + 104);
              }
              else
              {
                PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(&v40, a2, &PKEY_FileExtension);
                if ( v40 != 0.0 )
                {
                  pidl2 = 0;
                  v30 = -1;
                  do
                    ++v30;
                  while ( *(_WORD *)(*(_QWORD *)&v40 + 2LL + 2 * v30) );
                  if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                              &pidl2,
                              L"%lu:%.4s") >= 0 )
                    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                      (char *)this + 16,
                      &pidl2);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pidl2);
                }
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v40);
              }
              if ( PiiSafeShellitemParsingNameProperties::TryGetBooleanPropertyFromShellItem(a2, v29) )
              {
                PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
                  &v41,
                  a2,
                  PKEY_MsGraph_RecommendationReason);
                if ( v41 )
                {
                  v40 = 0.0;
                  ppidl[0] = v41;
                  ppidl[1] = (LPITEMIDLIST)&v40;
                  v31 = (int)_lambda_c3ddcf9081ed21b3602a2c72fc5f6745_::operator()(ppidl) < 0 ? DOUBLE_N1_0 : v40;
                  if ( v31 > -1.0 )
                    *((_DWORD *)this + 21) = (int)v31;
                }
                PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
                  &pidl2,
                  a2,
                  PKEY_Home_DriveType);
                if ( pidl2 )
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    (char *)this + 24,
                    &pidl2);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pidl2);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v41);
              }
              PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
                &v42,
                a2,
                PKEY_MsGraph_GraphFileType);
              if ( v42 )
              {
                pidl2 = 0;
                v32 = -1;
                do
                  ++v32;
                while ( *(_WORD *)(v42 + 2 * v32) );
                if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                            &pidl2,
                            L"%lu:%.50s") >= 0 )
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    (char *)this + 32,
                    &pidl2);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pidl2);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v42);
            }
            Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 40);
            *((_QWORD *)this + 6) = -1;
            *((_QWORD *)this + 7) = -1;
            SyncProviderTelemetryHelpers::GetProviderNameAndInfoFlags(
              a2,
              (unsigned __int16 **)this + 5,
              (PiiSafeShellitemParsingNameProperties *)((char *)this + 64));
            v33 = IShellItem_IsPartialCloudFilePlaceholder(a2) && IsFolderNotStreamItem(a2);
            *((_BYTE *)this + 80) = v33;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszPath);
          }
          else if ( *((_DWORD *)this + 28) == 11 )
          {
            pidl2 = 0;
            ppidl[0] = (LPITEMIDLIST)&pidl2;
            ppidl[1] = 0;
            LOBYTE(v44) = 1;
            v34 = SHGetIDListFromObject((IUnknown *)a2, &ppidl[1]);
            if ( v34 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x4AC,
                (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
                (const char *)(unsigned int)v34,
                v39);
            wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
            {
              RegistryRootLocation = PiiSafeShellitemParsingNameProperties::TryGetRegistryRootLocation(v35, a2, &pidl2);
            }
            else
            {
              HomePidl_NoThrow = (const ITEMIDLIST *)GetHomePidl_NoThrow();
              GalleryPidl_NoThrow = (const ITEMIDLIST *)GetGalleryPidl_NoThrow();
              if ( HomePidl_NoThrow && ILIsEqual(HomePidl_NoThrow, pidl2) )
              {
                RegistryRootLocation = 120;
              }
              else
              {
                RegistryRootLocation = 0;
                if ( GalleryPidl_NoThrow && ILIsEqual(GalleryPidl_NoThrow, pidl2) )
                  RegistryRootLocation = 121;
              }
            }
            *(_QWORD *)this |= (unsigned __int64)RegistryRootLocation << 40;
            wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
              &pidl2,
              0);
          }
          *((_BYTE *)this + 116) = 1;
          Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>::~ComPtr<Windows::Internal::StateRepository::IPackage>(&v39);
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x41A,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
            (const char *)(unsigned int)v8,
            v39);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180075bec  mov     [rsp-38h+arg_8], rbx
0x180075bf1  push    rbp
0x180075bf2  push    rsi
0x180075bf3  push    rdi
0x180075bf4  push    r12
0x180075bf6  push    r13
0x180075bf8  push    r14
0x180075bfa  push    r15
0x180075bfc  mov     rbp, rsp
0x180075bff  sub     rsp, 60h
0x180075c03  mov     rsi, rdx
0x180075c06  mov     rdi, rcx
0x180075c09  xor     r14d, r14d
0x180075c0c  cmp     [rcx+74h], r14b
0x180075c10  jnz     loc_1800761FF
0x180075c16  lea     r15, [rcx+58h]
0x180075c1a  mov     rax, [r15]
0x180075c1d  test    rax, rax
0x180075c20  jz      loc_1800761FF
0x180075c26  cmp     [rax], r14w
0x180075c2a  jz      loc_1800761FF
0x180075c30  mov     eax, [rcx+70h]
0x180075c33  sub     eax, 64h ; 'd'
0x180075c36  lea     r12d, [r14+1]
0x180075c3a  cmp     eax, r12d
0x180075c3d  jbe     short loc_180075C46
0x180075c3f  call    ?PopulateShellitemParsingNameRootType@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootType@@XZ; PiiSafeShellitemParsingNameProperties::PopulateShellitemParsingNameRootType(void)
0x180075c44  jmp     short loc_180075C48
0x180075c46  mov     al, 0C8h
0x180075c48  movzx   eax, al
0x180075c4b  shl     rax, 34h
0x180075c4f  or      [rdi], rax
0x180075c52  mov     [rbp+arg_10], r14d
0x180075c56  mov     rax, [rsi]
0x180075c59  lea     r8, [rbp+arg_10]
0x180075c5d  mov     edx, 7EC13008h
0x180075c62  mov     rcx, rsi
0x180075c65  mov     rax, [rax+30h]
0x180075c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075c6e  mov     rcx, [rbp+38h]; this
0x180075c72  test    eax, eax
0x180075c74  jns     short loc_180075C8F
0x180075c76  mov     r9d, eax; char *
0x180075c79  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180075c80  mov     edx, 41Ah; void *
0x180075c85  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180075c8a  jmp     loc_1800761FF
0x180075c8f  mov     dword ptr [rbp+pidl2], r14d
0x180075c93  mov     rax, [rsi]
0x180075c96  lea     r8, [rbp+pidl2]
0x180075c9a  mov     ebx, 20400000h
0x180075c9f  mov     edx, ebx
0x180075ca1  mov     rcx, rsi
0x180075ca4  mov     rax, [rax+30h]
0x180075ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cad  test    eax, eax
0x180075caf  js      short loc_180075CEE
0x180075cb1  test    dword ptr [rbp+pidl2], 20000000h
0x180075cb8  jz      short loc_180075CEE
0x180075cba  test    dword ptr [rbp+pidl2], 400000h
0x180075cc1  jnz     short loc_180075CEE
0x180075cc3  mov     dword ptr [rbp+pidl2], r14d
0x180075cc7  mov     rax, [rsi]
0x180075cca  lea     r8, [rbp+pidl2]
0x180075cce  mov     edx, ebx
0x180075cd0  mov     rcx, rsi
0x180075cd3  mov     rax, [rax+30h]
0x180075cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cdc  test    eax, eax
0x180075cde  js      short loc_180075CE9
0x180075ce0  mov     eax, dword ptr [rbp+pidl2]
0x180075ce3  and     eax, ebx
0x180075ce5  cmp     eax, ebx
0x180075ce7  jz      short loc_180075CEE
0x180075ce9  mov     r13b, r14b
0x180075cec  jmp     short loc_180075CF1
0x180075cee  mov     r13b, r12b
0x180075cf1  lea     rcx, [rbp+var_40]; this
0x180075cf5  call    ??0PropertyStoreHelper@wil@@QEAA@PEAUIPropertyStore@@@Z; wil::PropertyStoreHelper::PropertyStoreHelper(IPropertyStore *)
0x180075cfa  nop
0x180075cfb  mov     r8d, 8
0x180075d01  mov     rdx, rsi
0x180075d04  lea     rcx, [rbp+var_40]
0x180075d08  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x180075d0d  test    eax, eax
0x180075d0f  js      short loc_180075D51
0x180075d11  mov     dword ptr [rbp+pidl2], r14d
0x180075d15  movups  xmm0, cs:PKEY_Home_GraphFileType
0x180075d1c  movaps  xmmword ptr [rbp+ppidl], xmm0
0x180075d20  mov     eax, cs:dword_180093D90
0x180075d26  mov     dword ptr [rbp+var_10], eax
0x180075d29  lea     r8, [rbp+pidl2]
0x180075d2d  lea     rdx, [rbp+ppidl]
0x180075d31  lea     rcx, [rbp+var_40]
0x180075d35  call    ??$GetUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x180075d3a  test    eax, eax
0x180075d3c  js      short loc_180075D4B
0x180075d3e  mov     eax, dword ptr [rbp+pidl2]
0x180075d41  dec     eax
0x180075d43  cmp     eax, r12d
0x180075d46  mov     al, r12b
0x180075d49  jbe     short loc_180075D4E
0x180075d4b  mov     al, r14b
0x180075d4e  mov     [rdi+51h], al
0x180075d51  cmp     dword ptr [rdi+70h], 0Ah
0x180075d55  jz      short loc_180075D60
0x180075d57  cmp     dword ptr [rdi+70h], 66h ; 'f'
0x180075d5b  mov     bl, r14b
0x180075d5e  jnz     short loc_180075D63
0x180075d60  mov     bl, r12b
0x180075d63  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60851339@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339> `wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl(void)'::`2'::impl
0x180075d6a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(void)
0x180075d6f  test    al, al
0x180075d71  jz      short loc_180075D7E
0x180075d73  movzx   ebx, bl
0x180075d76  cmp     dword ptr [rdi+70h], 65h ; 'e'
0x180075d7a  cmovz   ebx, r12d
0x180075d7e  test    bl, bl
0x180075d80  jz      loc_180076123
0x180075d86  mov     rax, [r15]
0x180075d89  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180075d8d  inc     rbx
0x180075d90  cmp     [rax+rbx*2], r14w
0x180075d95  jnz     short loc_180075D8D
0x180075d97  mov     byte ptr [rbp+pidl2], r14b
0x180075d9b  cmp     dword ptr [rdi+70h], 66h ; 'f'
0x180075d9f  jnz     short loc_180075DA6
0x180075da1  mov     r12b, 77h ; 'w'
0x180075da4  jmp     short loc_180075DB9
0x180075da6  lea     r8, [rbp+pidl2]
0x180075daa  mov     rdx, r15
0x180075dad  call    ?FindLocalDiskLocation@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootLoc@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAE@Z; PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,uchar &)
0x180075db2  mov     r12b, al
0x180075db5  mov     r14b, byte ptr [rbp+pidl2]
0x180075db9  mov     r8b, r13b; bool
0x180075dbc  mov     rdx, [r15]; unsigned __int16 *
0x180075dbf  call    ?CalculatePathDepth@PiiSafeShellitemParsingNameProperties@@AEAAEPEBG_N@Z; PiiSafeShellitemParsingNameProperties::CalculatePathDepth(ushort const *,bool)
0x180075dc4  mov     ecx, [rbp+arg_10]
0x180075dc7  shl     rcx, 20h
0x180075dcb  or      [rdi+8], rcx
0x180075dcf  mov     cl, al
0x180075dd1  sub     cl, r14b
0x180075dd4  movzx   r14d, cl
0x180075dd8  mov     edx, r14d
0x180075ddb  shl     edx, 8
0x180075dde  movzx   ecx, r12b
0x180075de2  shl     rcx, 28h
0x180075de6  or      rdx, rcx
0x180075de9  movzx   eax, al
0x180075dec  or      rdx, rax
0x180075def  or      [rdi], rdx
0x180075df2  or      r8, 0FFFFFFFFFFFFFFFFh
0x180075df6  mov     rdx, [r15]
0x180075df9  lea     rcx, [rbp+pszPath]
0x180075dfd  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180075e02  nop
0x180075e03  xor     r12d, r12d
0x180075e06  test    r13b, r13b
0x180075e09  jz      short loc_180075E23
0x180075e0b  mov     rcx, [rbp+pszPath]; pszPath
0x180075e0f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180075e13  inc     rdx; cchPath
0x180075e16  cmp     [rcx+rdx*2], r12w
0x180075e1b  jnz     short loc_180075E13
0x180075e1d  call    cs:__imp_PathCchRemoveFileSpec
0x180075e23  mov     r8d, ebx
0x180075e26  mov     r9d, r14d
0x180075e29  lea     rdx, [rbp+pszPath]
0x180075e2d  lea     rcx, [rbp+pidl2]
0x180075e31  call    ?GetRelativeToRootPath@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV23@KK@Z; PiiSafeShellitemParsingNameProperties::GetRelativeToRootPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,ulong,ulong)
0x180075e36  lea     rbx, [rdi+60h]
0x180075e3a  mov     rdx, rax
0x180075e3d  mov     rcx, rbx
0x180075e40  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180075e45  lea     rcx, [rbp+pidl2]; void *
0x180075e49  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180075e4e  mov     rcx, [rbx]
0x180075e51  or      r14, 0FFFFFFFFFFFFFFFFh
0x180075e55  test    rcx, rcx
0x180075e58  jz      short loc_180075E82
0x180075e5a  mov     rax, r14
0x180075e5d  inc     rax
0x180075e60  cmp     [rcx+rax*2], r12w
0x180075e65  jnz     short loc_180075E5D
0x180075e67  movzx   eax, ax
0x180075e6a  shl     eax, 10h
0x180075e6d  cdqe
0x180075e6f  or      [rdi], rax
0x180075e72  mov     rdx, rbx
0x180075e75  call    ?GetKeywords@PiiSafeShellitemParsingNameProperties@@AEAA_KAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PiiSafeShellitemParsingNameProperties::GetKeywords(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x180075e7a  shl     rax, 20h
0x180075e7e  or      [rdi+48h], rax
0x180075e82  test    r13b, r13b
0x180075e85  jz      loc_1800760C5
0x180075e8b  mov     edx, 5Ch ; '\'; unsigned __int16
0x180075e90  mov     rcx, [r15]; unsigned __int16 *
0x180075e93  call    ?LastInstanceOfChar@PiiSafeShellitemParsingNameProperties@@CAPEBGPEBGG@Z; PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(ushort const *,ushort)
0x180075e98  mov     rdx, rax
0x180075e9b  lea     rcx, [rbp+pidl2]
0x180075e9f  call    details__safemake_cotaskmem_string_nothrow
0x180075ea4  lea     rbx, [rdi+68h]
0x180075ea8  mov     rdx, rax
0x180075eab  mov     rcx, rbx
0x180075eae  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180075eb3  lea     rcx, [rbp+pidl2]; void *
0x180075eb7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180075ebc  mov     rcx, [rbx]
0x180075ebf  test    rcx, rcx
0x180075ec2  jz      loc_180075F5B
0x180075ec8  mov     rax, r14
0x180075ecb  inc     rax
0x180075ece  cmp     [rcx+rax*2], r12w
0x180075ed3  jnz     short loc_180075ECB
0x180075ed5  movzx   eax, ax
0x180075ed8  or      [rdi+8], rax
0x180075edc  mov     edx, 2Eh ; '.'; unsigned __int16
0x180075ee1  mov     rcx, [r15]; unsigned __int16 *
0x180075ee4  call    ?LastInstanceOfChar@PiiSafeShellitemParsingNameProperties@@CAPEBGPEBGG@Z; PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(ushort const *,ushort)
0x180075ee9  test    rax, rax
0x180075eec  jz      short loc_180075F4D
0x180075eee  mov     [rbp+ppidl], r12
0x180075ef2  mov     [rbp+ppidl+8], r12
0x180075ef6  mov     [rbp+var_10], r12
0x180075efa  mov     r8, r14
0x180075efd  inc     r8
0x180075f00  cmp     [rax+r8*2], r12w
0x180075f05  jnz     short loc_180075EFD
0x180075f07  mov     r9, rax
0x180075f0a  lea     rdx, aLu4s; "%lu:%.4s"
0x180075f11  lea     rcx, [rbp+ppidl]
0x180075f15  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180075f1a  test    eax, eax
0x180075f1c  js      short loc_180075F44
0x180075f1e  mov     r8, r14
0x180075f21  mov     rdx, [rbp+ppidl]
0x180075f25  lea     rcx, [rbp+pidl2]
0x180075f29  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180075f2e  lea     rcx, [rdi+10h]
0x180075f32  lea     rdx, [rbp+pidl2]
0x180075f36  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180075f3b  lea     rcx, [rbp+pidl2]; void *
0x180075f3f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180075f44  lea     rcx, [rbp+ppidl]
0x180075f48  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180075f4d  mov     rdx, rbx
0x180075f50  call    ?GetKeywords@PiiSafeShellitemParsingNameProperties@@AEAA_KAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PiiSafeShellitemParsingNameProperties::GetKeywords(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x180075f55  or      [rdi+48h], rax
0x180075f59  jmp     short loc_180075FBF
0x180075f5b  lea     r8, PKEY_FileExtension
0x180075f62  mov     rdx, rsi
0x180075f65  lea     rcx, [rbp+var_38]
0x180075f69  call    ?TryGetStringPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x180075f6e  mov     rax, [rbp+var_38]
0x180075f72  test    rax, rax
0x180075f75  jz      short loc_180075FB6
0x180075f77  lea     r9, [rax+2]
0x180075f7b  mov     [rbp+pidl2], r12
0x180075f7f  mov     r8, r14
0x180075f82  inc     r8
0x180075f85  cmp     [r9+r8*2], r12w
0x180075f8a  jnz     short loc_180075F82
0x180075f8c  lea     rdx, aLu4s; "%lu:%.4s"
0x180075f93  lea     rcx, [rbp+pidl2]
0x180075f97  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180075f9c  test    eax, eax
0x180075f9e  js      short loc_180075FAD
0x180075fa0  lea     rcx, [rdi+10h]
0x180075fa4  lea     rdx, [rbp+pidl2]
0x180075fa8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180075fad  lea     rcx, [rbp+pidl2]; void *
0x180075fb1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180075fb6  lea     rcx, [rbp+var_38]; void *
0x180075fba  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180075fbf  mov     rcx, rsi; struct IShellItem *
0x180075fc2  call    ?TryGetBooleanPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA_NPEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetBooleanPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x180075fc7  test    al, al
0x180075fc9  jz      loc_180076065
0x180075fcf  lea     r8, PKEY_MsGraph_RecommendationReason
0x180075fd6  mov     rdx, rsi
0x180075fd9  lea     rcx, [rbp+var_30]
0x180075fdd  call    ?TryGetStringPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x180075fe2  nop
0x180075fe3  mov     rax, [rbp+var_30]
0x180075fe7  test    rax, rax
0x180075fea  jz      short loc_18007602C
0x180075fec  xorps   xmm0, xmm0
0x180075fef  movsd   [rbp+var_38], xmm0
0x180075ff4  mov     [rbp+ppidl], rax
0x180075ff8  lea     rax, [rbp+var_38]
0x180075ffc  mov     [rbp+ppidl+8], rax
0x180076000  lea     rcx, [rbp+ppidl]
0x180076004  call    ??R_lambda_c3ddcf9081ed21b3602a2c72fc5f6745_@@QEBA@XZ; _lambda_c3ddcf9081ed21b3602a2c72fc5f6745_::operator()(void)
0x180076009  movsd   xmm1, cs:__real@bff0000000000000
0x180076011  test    eax, eax
0x180076013  js      short loc_18007601C
0x180076015  movsd   xmm0, [rbp+var_38]
0x18007601a  jmp     short loc_18007601F
0x18007601c  movaps  xmm0, xmm1
0x18007601f  comisd  xmm0, xmm1
0x180076023  jbe     short loc_18007602C
  ... truncated ...
```
