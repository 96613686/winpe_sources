# PiiSafeShellitemParsingNameProperties::PopulateBasicFields(IShellItem *)

- ea: `0x18001b1f8`
- end: `0x18001b8a2`
- name: `?PopulateBasicFields@PiiSafeShellitemParsingNameProperties@@AEAAXPEAUIShellItem@@@Z`
- size: `1706`
- prototype: `void(PiiSafeShellitemParsingNameProperties *__hidden this, struct IShellItem *)`
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180012498`

## callees

- `0x1800049e0`
- `0x1800061e8`
- `0x180006218`
- `0x1800063b4`
- `0x1800064d4`
- `0x180011988`
- `0x180011ac4`
- `0x180012254`
- `0x1800125f8`
- `0x180012bb0`
- `0x1800133ec`
- `0x180014328`
- `0x18001866c`
- `0x180018764`
- `0x180018af0`
- `0x180018e38`
- `0x1800191a8`
- `0x180019d68`
- `0x180019e80`
- `0x180019f70`
- `0x18001a864`
- `0x18001aaa0`
- `0x18001b1f8`
- `0x18001b8a8`
- `0x18001e444`
- `0x18001e4bc`
- `0x180020850`
- `0x180021424`
- `0x180021550`
- `0x180051010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x18001b7d2`
- `SHELL32!SHGetIDListFromObject` at `0x18001b7d2`
- `SHELL32!__imp_ILIsEqual` at `0x18001b832`
- `SHELL32!__imp_ILIsEqual` at `0x18001b850`
- `SHELL32!__imp_ILIsEqual` at `0x18001b832`
- `SHELL32!__imp_ILIsEqual` at `0x18001b850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b534`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b5b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b5bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b6a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b6b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b714`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b534`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b5b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b5bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b6a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b6b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b714`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b877`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18001b3fd`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18001b3fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall PiiSafeShellitemParsingNameProperties::PopulateBasicFields(
        PiiSafeShellitemParsingNameProperties *this,
        struct IShellItem *a2)
{
  const unsigned __int16 **v4; // r12
  _WORD *v5; // rax
  unsigned __int8 v6; // al
  int v7; // eax
  __int64 v8; // r8
  bool v9; // r13
  char v10; // al
  char v11; // bl
  PiiSafeShellitemParsingNameProperties *v12; // rcx
  __int64 v13; // rdi
  char v14; // bl
  unsigned __int8 LocalDiskLocation; // r15
  unsigned __int8 v16; // al
  const char *v17; // r9
  PWSTR v18; // rbx
  size_t v19; // rdx
  _QWORD *RelativeToRootPath; // rax
  __int64 *v21; // rdi
  __int64 v22; // rcx
  __int64 v23; // rax
  const unsigned __int16 *InstanceOfChar; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rdi
  __int64 v27; // rax
  const unsigned __int16 *v28; // rax
  __int64 v29; // rcx
  __int64 v30; // r8
  const char *v31; // r9
  __int64 v32; // r8
  char v33; // di
  double v34; // xmm0_8
  __int64 v35; // r8
  char v36; // al
  void *v37; // rcx
  HRESULT v38; // eax
  __int64 v39; // r8
  __int64 v40; // rcx
  unsigned __int8 RegistryRootLocation; // bl
  const ITEMIDLIST *HomePidl_NoThrow; // rbx
  const ITEMIDLIST *GalleryPidl_NoThrow; // rdi
  __int64 v44; // [rsp+20h] [rbp-40h] BYREF
  PWSTR pszPath; // [rsp+28h] [rbp-38h] BYREF
  LPVOID v46; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v47; // [rsp+38h] [rbp-28h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v49; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  LPVOID pv; // [rsp+A0h] [rbp+40h] BYREF
  unsigned int v52; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID v53; // [rsp+B8h] [rbp+58h] BYREF

  if ( !*((_BYTE *)this + 116) )
  {
    v4 = (const unsigned __int16 **)((char *)this + 88);
    v5 = (_WORD *)*((_QWORD *)this + 11);
    if ( v5 )
    {
      if ( *v5 )
      {
        if ( (unsigned int)(*((_DWORD *)this + 28) - 100) <= 1 )
          v6 = -56;
        else
          v6 = PiiSafeShellitemParsingNameProperties::PopulateShellitemParsingNameRootType();
        *(_QWORD *)this |= (unsigned __int64)v6 << 52;
        v52 = 0;
        v7 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned int *))a2->lpVtbl->GetAttributes)(
               a2,
               2126589960,
               &v52);
        if ( v7 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x41A, v8, (const char *)(unsigned int)v7);
          return;
        }
        LODWORD(pv) = 0;
        if ( ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetAttributes)(a2, 541065216, &pv) < 0
          || ((unsigned int)pv & 0x20000000) == 0
          || ((unsigned int)pv & 0x400000) != 0
          || (v9 = 0, (unsigned int)IShellItem_IsContainerFile(a2)) )
        {
          v9 = 1;
        }
        v44 = 0;
        if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v44, a2) >= 0 )
        {
          LODWORD(pv) = 0;
          *(_OWORD *)ppidl = PKEY_Home_GraphFileType;
          LODWORD(v49) = 19;
          if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(&v44, ppidl, &pv) < 0
            || (v10 = 1, (unsigned int)((_DWORD)pv - 1) > 1) )
          {
            v10 = 0;
          }
          *((_BYTE *)this + 81) = v10;
        }
        if ( *((_DWORD *)this + 28) == 10 || (v11 = 0, *((_DWORD *)this + 28) == 102) )
          v11 = 1;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl'::`2'::impl)
          && *((_DWORD *)this + 28) == 101 )
        {
          v11 = 1;
        }
        if ( v11 )
        {
          v13 = -1;
          do
            ++v13;
          while ( (*v4)[v13] );
          v14 = 0;
          LOBYTE(pv) = 0;
          if ( *((_DWORD *)this + 28) == 102 )
          {
            LocalDiskLocation = 119;
          }
          else
          {
            LocalDiskLocation = PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(v12, v4, &pv);
            v14 = (char)pv;
          }
          v16 = PiiSafeShellitemParsingNameProperties::CalculatePathDepth(v12, *v4, v9);
          *((_QWORD *)this + 1) |= (unsigned __int64)v52 << 32;
          LODWORD(pv) = (unsigned __int8)(v16 - v14);
          *(_QWORD *)this |= v16 | ((unsigned __int64)LocalDiskLocation << 40) | (unsigned int)((_DWORD)pv << 8);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pszPath,
            (char *)*v4,
            0xFFFFFFFFFFFFFFFFuLL,
            v17);
          v18 = pszPath;
          if ( v9 )
          {
            v19 = -1;
            do
              ++v19;
            while ( pszPath[v19] );
            PathCchRemoveFileSpec(pszPath, v19);
          }
          RelativeToRootPath = (_QWORD *)PiiSafeShellitemParsingNameProperties::GetRelativeToRootPath(
                                           &pv,
                                           &pszPath,
                                           (unsigned int)v13,
                                           (unsigned int)pv);
          v21 = (__int64 *)((char *)this + 96);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            (_QWORD *)this + 12,
            RelativeToRootPath);
          if ( pv )
            CoTaskMemFree(pv);
          v22 = *v21;
          if ( *v21 )
          {
            v23 = -1;
            do
              ++v23;
            while ( *(_WORD *)(v22 + 2 * v23) );
            *(_QWORD *)this |= (unsigned __int16)v23 << 16;
            *((_QWORD *)this + 9) |= PiiSafeShellitemParsingNameProperties::GetKeywords(v22, (char *)this + 96) << 32;
          }
          if ( v9 )
          {
            InstanceOfChar = PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(*v4, 0x5Cu);
            v25 = (_QWORD *)details::safemake_cotaskmem_string_nothrow(&pv, InstanceOfChar);
            v26 = (_QWORD *)((char *)this + 104);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              (_QWORD *)this + 13,
              v25);
            if ( pv )
              CoTaskMemFree(pv);
            if ( *v26 )
            {
              v27 = -1;
              do
                ++v27;
              while ( *(_WORD *)(*v26 + 2 * v27) );
              *((_QWORD *)this + 1) |= (unsigned __int16)v27;
              v28 = PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(*v4, 0x2Eu);
              if ( v28 )
              {
                ppidl[0] = 0;
                ppidl[1] = 0;
                v49 = 0;
                v30 = -1;
                do
                  ++v30;
                while ( v28[v30] );
                if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                            ppidl,
                            L"%lu:%.4s",
                            v30,
                            v28) >= 0 )
                {
                  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                    &pv,
                    (char *)ppidl[0],
                    0xFFFFFFFFFFFFFFFFuLL,
                    v31);
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    (_QWORD *)this + 2,
                    &pv);
                  if ( pv )
                    CoTaskMemFree(pv);
                }
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)ppidl);
              }
              *((_QWORD *)this + 9) |= PiiSafeShellitemParsingNameProperties::GetKeywords(v29, (char *)this + 104);
            }
            else
            {
              PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(&v53, a2, &PKEY_FileExtension);
              if ( v53 )
              {
                pv = 0;
                v32 = -1;
                do
                  ++v32;
                while ( *((_WORD *)v53 + v32 + 1) );
                if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                            (__int64)&pv,
                            (__int64)L"%lu:%.4s") >= 0 )
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    (_QWORD *)this + 2,
                    &pv);
                if ( pv )
                  CoTaskMemFree(pv);
                if ( v53 )
                  CoTaskMemFree(v53);
              }
            }
            v33 = 0;
            LOBYTE(pv) = 0;
            v53 = 0;
            if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v53, a2) >= 0 )
            {
              *(_OWORD *)ppidl = PKEY_Home_Recommended;
              LODWORD(v49) = 20;
              wil::PropertyStoreHelperBase<IPropertyStore>::GetBoolean<_tagpropertykey>(&v53, ppidl, &pv);
              v33 = (char)pv;
            }
            Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(&v53);
            if ( v33 )
            {
              PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
                &v46,
                a2,
                PKEY_MsGraph_RecommendationReason);
              if ( v46 )
              {
                v53 = 0;
                ppidl[0] = (LPITEMIDLIST)v46;
                ppidl[1] = (LPITEMIDLIST)&v53;
                v34 = (int)_lambda_c3ddcf9081ed21b3602a2c72fc5f6745_::operator()((__int64)ppidl) < 0
                    ? DOUBLE_N1_0
                    : *(double *)&v53;
                if ( v34 > -1.0 )
                  *((_DWORD *)this + 21) = (int)v34;
              }
              PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(&pv, a2, PKEY_Home_DriveType);
              if ( pv )
              {
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                  (_QWORD *)this + 3,
                  &pv);
                if ( pv )
                  CoTaskMemFree(pv);
              }
              if ( v46 )
                CoTaskMemFree(v46);
            }
            PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
              &v47,
              a2,
              PKEY_MsGraph_GraphFileType);
            if ( v47 )
            {
              pv = 0;
              v35 = -1;
              do
                ++v35;
              while ( *((_WORD *)v47 + v35) );
              if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                          (__int64)&pv,
                          (__int64)L"%lu:%.50s") >= 0 )
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                  (_QWORD *)this + 4,
                  &pv);
              if ( pv )
                CoTaskMemFree(pv);
              if ( v47 )
                CoTaskMemFree(v47);
            }
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)this + 40);
          *((_QWORD *)this + 6) = -1;
          *((_QWORD *)this + 7) = -1;
          SyncProviderTelemetryHelpers::GetProviderNameAndInfoFlags(
            a2,
            (unsigned __int16 **)this + 5,
            (PiiSafeShellitemParsingNameProperties *)((char *)this + 64));
          LODWORD(pv) = 0;
          if ( IShellItem_GetFilePlaceholderStatus(a2, (unsigned int *)&pv) < 0
            || ((unsigned __int8)pv & 0xA) != 8
            || (LODWORD(pv) = 0,
                ((int (__fastcall *)(struct IShellItem *, __int64, LPVOID *))a2->lpVtbl->GetAttributes)(
                  a2,
                  541065216,
                  &pv) < 0)
            || (v36 = 1, (_DWORD)pv != 0x20000000) )
          {
            v36 = 0;
          }
          *((_BYTE *)this + 80) = v36;
          if ( !v18 )
            goto LABEL_107;
          v37 = v18;
        }
        else
        {
          if ( *((_DWORD *)this + 28) != 11 )
            goto LABEL_107;
          pv = 0;
          ppidl[0] = (LPITEMIDLIST)&pv;
          ppidl[1] = 0;
          LOBYTE(v49) = 1;
          v38 = SHGetIDListFromObject((IUnknown *)a2, &ppidl[1]);
          if ( v38 < 0 )
            wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x4AC, v39, (const char *)(unsigned int)v38);
          wil::details::out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)ppidl);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
          {
            RegistryRootLocation = PiiSafeShellitemParsingNameProperties::TryGetRegistryRootLocation(v40, a2, &pv);
          }
          else
          {
            HomePidl_NoThrow = (const ITEMIDLIST *)GetHomePidl_NoThrow();
            GalleryPidl_NoThrow = (const ITEMIDLIST *)GetGalleryPidl_NoThrow();
            if ( HomePidl_NoThrow && ILIsEqual(HomePidl_NoThrow, (LPCITEMIDLIST)pv) )
            {
              RegistryRootLocation = 120;
            }
            else
            {
              RegistryRootLocation = 0;
              if ( GalleryPidl_NoThrow && ILIsEqual(GalleryPidl_NoThrow, (LPCITEMIDLIST)pv) )
                RegistryRootLocation = 121;
            }
          }
          *(_QWORD *)this |= (unsigned __int64)RegistryRootLocation << 40;
          v37 = pv;
          pv = 0;
          if ( !v37 )
            goto LABEL_107;
        }
        CoTaskMemFree(v37);
LABEL_107:
        *((_BYTE *)this + 116) = 1;
        Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(&v44);
      }
    }
  }
}

```

## disassembly

```asm
0x18001b1f8  mov     [rsp-38h+arg_8], rbx
0x18001b1fd  push    rbp
0x18001b1fe  push    rsi
0x18001b1ff  push    rdi
0x18001b200  push    r12
0x18001b202  push    r13
0x18001b204  push    r14
0x18001b206  push    r15
0x18001b208  mov     rbp, rsp
0x18001b20b  sub     rsp, 60h
0x18001b20f  mov     r14, rdx
0x18001b212  mov     rsi, rcx
0x18001b215  xor     r15d, r15d
0x18001b218  cmp     [rcx+74h], r15b
0x18001b21c  jnz     loc_18001B88A
0x18001b222  lea     r12, [rcx+58h]
0x18001b226  mov     rax, [r12]
0x18001b22a  test    rax, rax
0x18001b22d  jz      loc_18001B88A
0x18001b233  cmp     [rax], r15w
0x18001b237  jz      loc_18001B88A
0x18001b23d  mov     eax, [rcx+70h]
0x18001b240  sub     eax, 64h ; 'd'
0x18001b243  lea     edi, [r15+1]
0x18001b247  cmp     eax, edi
0x18001b249  jbe     short loc_18001B252
0x18001b24b  call    ?PopulateShellitemParsingNameRootType@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootType@@XZ; PiiSafeShellitemParsingNameProperties::PopulateShellitemParsingNameRootType(void)
0x18001b250  jmp     short loc_18001B254
0x18001b252  mov     al, 0C8h
0x18001b254  movzx   eax, al
0x18001b257  shl     rax, 34h
0x18001b25b  or      [rsi], rax
0x18001b25e  mov     [rbp+arg_10], r15d
0x18001b262  mov     rax, [r14]
0x18001b265  lea     r8, [rbp+arg_10]
0x18001b269  mov     edx, 7EC13008h
0x18001b26e  mov     rcx, r14
0x18001b271  mov     rax, [rax+30h]
0x18001b275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b27a  mov     rcx, [rbp+38h]; this
0x18001b27e  test    eax, eax
0x18001b280  jns     short loc_18001B294
0x18001b282  mov     r9d, eax; char *
0x18001b285  mov     edx, 41Ah; void *
0x18001b28a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b28f  jmp     loc_18001B88A
0x18001b294  mov     dword ptr [rbp+pv], r15d
0x18001b298  mov     rax, [r14]
0x18001b29b  lea     r8, [rbp+pv]
0x18001b29f  mov     edx, 20400000h
0x18001b2a4  mov     rcx, r14
0x18001b2a7  mov     rax, [rax+30h]
0x18001b2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2b0  test    eax, eax
0x18001b2b2  js      short loc_18001B2D5
0x18001b2b4  test    dword ptr [rbp+pv], 20000000h
0x18001b2bb  jz      short loc_18001B2D5
0x18001b2bd  test    dword ptr [rbp+pv], 400000h
0x18001b2c4  jnz     short loc_18001B2D5
0x18001b2c6  mov     rcx, r14; struct IShellItem *
0x18001b2c9  call    ?IShellItem_IsContainerFile@@YAHPEAUIShellItem@@@Z; IShellItem_IsContainerFile(IShellItem *)
0x18001b2ce  test    eax, eax
0x18001b2d0  mov     r13b, r15b
0x18001b2d3  jz      short loc_18001B2D8
0x18001b2d5  mov     r13b, dil
0x18001b2d8  mov     [rbp+var_40], r15
0x18001b2dc  mov     rdx, r14
0x18001b2df  lea     rcx, [rbp+var_40]
0x18001b2e3  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x18001b2e8  test    eax, eax
0x18001b2ea  js      short loc_18001B32B
0x18001b2ec  mov     dword ptr [rbp+pv], r15d
0x18001b2f0  movups  xmm0, cs:PKEY_Home_GraphFileType
0x18001b2f7  movaps  xmmword ptr [rbp+ppidl], xmm0
0x18001b2fb  mov     eax, cs:dword_180058580
0x18001b301  mov     dword ptr [rbp+var_10], eax
0x18001b304  lea     r8, [rbp+pv]
0x18001b308  lea     rdx, [rbp+ppidl]
0x18001b30c  lea     rcx, [rbp+var_40]
0x18001b310  call    ??$GetUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x18001b315  test    eax, eax
0x18001b317  js      short loc_18001B325
0x18001b319  mov     eax, dword ptr [rbp+pv]
0x18001b31c  dec     eax
0x18001b31e  cmp     eax, edi
0x18001b320  mov     al, dil
0x18001b323  jbe     short loc_18001B328
0x18001b325  mov     al, r15b
0x18001b328  mov     [rsi+51h], al
0x18001b32b  cmp     dword ptr [rsi+70h], 0Ah
0x18001b32f  jz      short loc_18001B33A
0x18001b331  cmp     dword ptr [rsi+70h], 66h ; 'f'
0x18001b335  mov     bl, r15b
0x18001b338  jnz     short loc_18001B33D
0x18001b33a  mov     bl, dil
0x18001b33d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60851339@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339> `wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl(void)'::`2'::impl
0x18001b344  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(void)
0x18001b349  test    al, al
0x18001b34b  jz      short loc_18001B357
0x18001b34d  movzx   ebx, bl
0x18001b350  cmp     dword ptr [rsi+70h], 65h ; 'e'
0x18001b354  cmovz   ebx, edi
0x18001b357  test    bl, bl
0x18001b359  jz      loc_18001B7AD
0x18001b35f  mov     rax, [r12]
0x18001b363  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001b367  inc     rdi
0x18001b36a  cmp     [rax+rdi*2], r15w
0x18001b36f  jnz     short loc_18001B367
0x18001b371  mov     bl, r15b
0x18001b374  mov     byte ptr [rbp+pv], bl
0x18001b377  cmp     dword ptr [rsi+70h], 66h ; 'f'
0x18001b37b  jnz     short loc_18001B382
0x18001b37d  mov     r15b, 77h ; 'w'
0x18001b380  jmp     short loc_18001B394
0x18001b382  lea     r8, [rbp+pv]
0x18001b386  mov     rdx, r12
0x18001b389  call    ?FindLocalDiskLocation@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootLoc@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAE@Z; PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,uchar &)
0x18001b38e  mov     r15b, al
0x18001b391  mov     bl, byte ptr [rbp+pv]
0x18001b394  mov     r8b, r13b; bool
0x18001b397  mov     rdx, [r12]; unsigned __int16 *
0x18001b39b  call    ?CalculatePathDepth@PiiSafeShellitemParsingNameProperties@@AEAAEPEBG_N@Z; PiiSafeShellitemParsingNameProperties::CalculatePathDepth(ushort const *,bool)
0x18001b3a0  mov     ecx, [rbp+arg_10]
0x18001b3a3  shl     rcx, 20h
0x18001b3a7  or      [rsi+8], rcx
0x18001b3ab  mov     cl, al
0x18001b3ad  sub     cl, bl
0x18001b3af  movzx   ecx, cl
0x18001b3b2  mov     dword ptr [rbp+pv], ecx
0x18001b3b5  shl     ecx, 8
0x18001b3b8  mov     edx, ecx
0x18001b3ba  movzx   ecx, r15b
0x18001b3be  shl     rcx, 28h
0x18001b3c2  or      rdx, rcx
0x18001b3c5  movzx   eax, al
0x18001b3c8  or      rdx, rax
0x18001b3cb  or      [rsi], rdx
0x18001b3ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001b3d2  mov     rdx, [r12]
0x18001b3d6  lea     rcx, [rbp+pszPath]
0x18001b3da  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001b3df  nop
0x18001b3e0  mov     rbx, [rbp+pszPath]
0x18001b3e4  xor     r15d, r15d
0x18001b3e7  test    r13b, r13b
0x18001b3ea  jz      short loc_18001B403
0x18001b3ec  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001b3f0  inc     rdx; cchPath
0x18001b3f3  cmp     [rbx+rdx*2], r15w
0x18001b3f8  jnz     short loc_18001B3F0
0x18001b3fa  mov     rcx, rbx; pszPath
0x18001b3fd  call    cs:__imp_PathCchRemoveFileSpec
0x18001b403  mov     r8d, edi
0x18001b406  mov     r9d, dword ptr [rbp+pv]
0x18001b40a  lea     rdx, [rbp+pszPath]
0x18001b40e  lea     rcx, [rbp+pv]
0x18001b412  call    ?GetRelativeToRootPath@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV23@KK@Z; PiiSafeShellitemParsingNameProperties::GetRelativeToRootPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,ulong,ulong)
0x18001b417  lea     rdi, [rsi+60h]
0x18001b41b  mov     rdx, rax
0x18001b41e  mov     rcx, rdi
0x18001b421  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001b426  mov     rcx, [rbp+pv]; pv
0x18001b42a  test    rcx, rcx
0x18001b42d  jz      short loc_18001B435
0x18001b42f  call    cs:__imp_CoTaskMemFree
0x18001b435  mov     rcx, [rdi]
0x18001b438  test    rcx, rcx
0x18001b43b  jz      short loc_18001B466
0x18001b43d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001b441  inc     rax
0x18001b444  cmp     [rcx+rax*2], r15w
0x18001b449  jnz     short loc_18001B441
0x18001b44b  movzx   eax, ax
0x18001b44e  shl     eax, 10h
0x18001b451  cdqe
0x18001b453  or      [rsi], rax
0x18001b456  mov     rdx, rdi
0x18001b459  call    ?GetKeywords@PiiSafeShellitemParsingNameProperties@@AEAA_KAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PiiSafeShellitemParsingNameProperties::GetKeywords(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x18001b45e  shl     rax, 20h
0x18001b462  or      [rsi+48h], rax
0x18001b466  test    r13b, r13b
0x18001b469  jz      loc_18001B729
0x18001b46f  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001b474  mov     rcx, [r12]; unsigned __int16 *
0x18001b478  call    ?LastInstanceOfChar@PiiSafeShellitemParsingNameProperties@@CAPEBGPEBGG@Z; PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(ushort const *,ushort)
0x18001b47d  mov     rdx, rax
0x18001b480  lea     rcx, [rbp+pv]
0x18001b484  call    details__safemake_cotaskmem_string_nothrow
0x18001b489  lea     rdi, [rsi+68h]
0x18001b48d  mov     rdx, rax
0x18001b490  mov     rcx, rdi
0x18001b493  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001b498  mov     rcx, [rbp+pv]; pv
0x18001b49c  test    rcx, rcx
0x18001b49f  jz      short loc_18001B4A7
0x18001b4a1  call    cs:__imp_CoTaskMemFree
0x18001b4a7  mov     rdx, [rdi]
0x18001b4aa  test    rdx, rdx
0x18001b4ad  jz      loc_18001B551
0x18001b4b3  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001b4b7  mov     rax, r13
0x18001b4ba  inc     rax
0x18001b4bd  cmp     [rdx+rax*2], r15w
0x18001b4c2  jnz     short loc_18001B4BA
0x18001b4c4  movzx   eax, ax
0x18001b4c7  or      [rsi+8], rax
0x18001b4cb  mov     edx, 2Eh ; '.'; unsigned __int16
0x18001b4d0  mov     rcx, [r12]; unsigned __int16 *
0x18001b4d4  call    ?LastInstanceOfChar@PiiSafeShellitemParsingNameProperties@@CAPEBGPEBGG@Z; PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(ushort const *,ushort)
0x18001b4d9  test    rax, rax
0x18001b4dc  jz      short loc_18001B543
0x18001b4de  mov     [rbp+ppidl], r15
0x18001b4e2  mov     [rbp+ppidl+8], r15
0x18001b4e6  mov     [rbp+var_10], r15
0x18001b4ea  mov     r8, r13
0x18001b4ed  inc     r8
0x18001b4f0  cmp     [rax+r8*2], r15w
0x18001b4f5  jnz     short loc_18001B4ED
0x18001b4f7  mov     r9, rax
0x18001b4fa  lea     rdx, aLu4s; "%lu:%.4s"
0x18001b501  lea     rcx, [rbp+ppidl]
0x18001b505  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18001b50a  test    eax, eax
0x18001b50c  js      short loc_18001B53A
0x18001b50e  mov     r8, r13
0x18001b511  mov     rdx, [rbp+ppidl]
0x18001b515  lea     rcx, [rbp+pv]
0x18001b519  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001b51e  lea     rcx, [rsi+10h]
0x18001b522  lea     rdx, [rbp+pv]
0x18001b526  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001b52b  mov     rcx, [rbp+pv]; pv
0x18001b52f  test    rcx, rcx
0x18001b532  jz      short loc_18001B53A
0x18001b534  call    cs:__imp_CoTaskMemFree
0x18001b53a  lea     rcx, [rbp+ppidl]
0x18001b53e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001b543  mov     rdx, rdi
0x18001b546  call    ?GetKeywords@PiiSafeShellitemParsingNameProperties@@AEAA_KAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PiiSafeShellitemParsingNameProperties::GetKeywords(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x18001b54b  or      [rsi+48h], rax
0x18001b54f  jmp     short loc_18001B5C5
0x18001b551  lea     r8, PKEY_FileExtension
0x18001b558  mov     rdx, r14
0x18001b55b  lea     rcx, [rbp+arg_18]
0x18001b55f  call    ?TryGetStringPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x18001b564  mov     rax, [rbp+arg_18]
0x18001b568  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001b56c  test    rax, rax
0x18001b56f  jz      short loc_18001B5C5
0x18001b571  lea     r9, [rax+2]
0x18001b575  mov     [rbp+pv], r15
0x18001b579  mov     r8, r13
0x18001b57c  inc     r8
0x18001b57f  cmp     [r9+r8*2], r15w
0x18001b584  jnz     short loc_18001B57C
0x18001b586  lea     rdx, aLu4s; "%lu:%.4s"
0x18001b58d  lea     rcx, [rbp+pv]
0x18001b591  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18001b596  test    eax, eax
0x18001b598  js      short loc_18001B5A7
0x18001b59a  lea     rcx, [rsi+10h]
0x18001b59e  lea     rdx, [rbp+pv]
0x18001b5a2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18001b5a7  mov     rcx, [rbp+pv]; pv
0x18001b5ab  test    rcx, rcx
0x18001b5ae  jz      short loc_18001B5B6
0x18001b5b0  call    cs:__imp_CoTaskMemFree
0x18001b5b6  mov     rcx, [rbp+arg_18]; pv
0x18001b5ba  test    rcx, rcx
0x18001b5bd  jz      short loc_18001B5C5
0x18001b5bf  call    cs:__imp_CoTaskMemFree
0x18001b5c5  mov     dil, r15b
0x18001b5c8  mov     byte ptr [rbp+pv], r15b
0x18001b5cc  mov     [rbp+arg_18], r15
0x18001b5d0  mov     rdx, r14
0x18001b5d3  lea     rcx, [rbp+arg_18]
0x18001b5d7  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x18001b5dc  test    eax, eax
0x18001b5de  js      short loc_18001B609
0x18001b5e0  movups  xmm0, cs:PKEY_Home_Recommended
0x18001b5e7  movaps  xmmword ptr [rbp+ppidl], xmm0
0x18001b5eb  mov     eax, cs:dword_180057FD8
0x18001b5f1  mov     dword ptr [rbp+var_10], eax
0x18001b5f4  lea     r8, [rbp+pv]
0x18001b5f8  lea     rdx, [rbp+ppidl]
0x18001b5fc  lea     rcx, [rbp+arg_18]
0x18001b600  call    ??$GetBoolean@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEA_N@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetBoolean<_tagpropertykey>(_tagpropertykey,bool *)
0x18001b605  mov     dil, byte ptr [rbp+pv]
0x18001b609  lea     rcx, [rbp+arg_18]
0x18001b60d  call    ??1?$ComPtr@UIDBFolderPriv@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IDBFolderPriv>::~ComPtr<IDBFolderPriv>(void)
0x18001b612  test    dil, dil
0x18001b615  jz      loc_18001B6BD
0x18001b61b  lea     r8, PKEY_MsGraph_RecommendationReason
0x18001b622  mov     rdx, r14
0x18001b625  lea     rcx, [rbp+var_30]
0x18001b629  call    ?TryGetStringPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x18001b62e  nop
0x18001b62f  mov     rax, [rbp+var_30]
0x18001b633  test    rax, rax
  ... truncated ...
```
