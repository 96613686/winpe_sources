# PiiSafeShellitemParsingNameProperties::PopulateBasicFields(IShellItem *)

- ea: `0x180546068`
- end: `0x180546682`
- name: `?PopulateBasicFields@PiiSafeShellitemParsingNameProperties@@AEAAXPEAUIShellItem@@@Z`
- size: `1562`
- prototype: `void(PiiSafeShellitemParsingNameProperties *__hidden this, struct IShellItem *)`
- caller_count: `2`
- callee_count: `36`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1802b0138`
- `0x180541e08`

## callees

- `0x18000d354`
- `0x18000d6cc`
- `0x18001b390`
- `0x18003def0`
- `0x18004a0a0`
- `0x1800551a0`
- `0x18005dc50`
- `0x18005f240`
- `0x180074990`
- `0x1800dd190`
- `0x18010a850`
- `0x18010ac0c`
- `0x18012210c`
- `0x18012a9a0`
- `0x18014be50`
- `0x1801aad28`
- `0x1801f85b0`
- `0x18029f42c`
- `0x18029f4a0`
- `0x1802aefe4`
- `0x1802c18a0`
- `0x1802e7c04`
- `0x18031c400`
- `0x1803221e4`
- `0x1803a4cb0`
- `0x180544260`
- `0x1805442cc`
- `0x180544878`
- `0x1805459cc`
- `0x180546068`
- `0x180547628`
- `0x1805476d4`
- `0x18054774c`
- `0x180547c00`
- `0x180547c78`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18054626e`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x18054626e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805462a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180546311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805463a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18054641f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18054642e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805464a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805464b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18054650f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18054651e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180546648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805462a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180546311`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805463a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18054641f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18054642e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805464a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1805464b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18054650f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18054651e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180546648`

## string_xrefs

- `0x180546108`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`
- `0x1805465af`: `onecoreuap\internal\shell\inc\private\piiSafeShellitemParsingName.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall PiiSafeShellitemParsingNameProperties::PopulateBasicFields(
        PiiSafeShellitemParsingNameProperties *this,
        struct IShellItem *a2)
{
  const unsigned __int16 **v4; // r15
  _WORD *v5; // rax
  unsigned __int8 v6; // al
  int v7; // eax
  bool v8; // r13
  char v9; // al
  char v10; // bl
  PiiSafeShellitemParsingNameProperties *v11; // rcx
  __int64 v12; // rdi
  char v13; // bl
  unsigned __int8 LocalDiskLocation; // r12
  unsigned __int8 v15; // al
  PWSTR v16; // rbx
  size_t v17; // rdx
  __int64 RelativeToRootPath; // rax
  __int64 *v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rax
  const unsigned __int16 *InstanceOfChar; // rax
  __int64 v23; // rax
  _QWORD *v24; // rdi
  __int64 v25; // rax
  const unsigned __int16 *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  const struct _tagpropertykey *v29; // rdx
  __int64 v30; // r8
  double ReasonMarkerType; // xmm0_8
  __int64 v32; // r8
  bool v33; // zf
  char v34; // al
  ITEMIDLIST *v35; // rcx
  HRESULT v36; // eax
  __int64 v37; // rcx
  unsigned __int8 RegistryRootLocation; // bl
  const ITEMIDLIST *HomePidl_NoThrow; // rbx
  const ITEMIDLIST *GalleryPidl_NoThrow; // rdi
  int v41; // [rsp+20h] [rbp-49h] BYREF
  unsigned __int16 *v42; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv[2]; // [rsp+30h] [rbp-39h] BYREF
  LPITEMIDLIST ppidl[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v45; // [rsp+50h] [rbp-19h]
  PWSTR pszPath; // [rsp+60h] [rbp-9h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+68h] [rbp-1h] BYREF
  unsigned int v48; // [rsp+70h] [rbp+7h] BYREF
  __int64 v49; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

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
        v48 = 0;
        v7 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, unsigned int *))a2->lpVtbl->GetAttributes)(
               a2,
               2126589960,
               &v48);
        if ( v7 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x41A,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
            (const char *)(unsigned int)v7,
            v41);
          return;
        }
        if ( !(unsigned int)IShellItem_IsFolder(a2) || (v8 = 0, (unsigned int)IShellItem_IsContainerFile(a2)) )
          v8 = 1;
        v49 = 0;
        Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v49);
        if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(&v49, a2, 8) >= 0 )
        {
          LODWORD(pidl2) = 0;
          *(GUID *)ppidl = PKEY_Home_GraphFileType.fmtid;
          LODWORD(v45) = PKEY_Home_GraphFileType.pid;
          if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(&v49, ppidl, &pidl2) < 0
            || (v9 = 1, (unsigned int)((_DWORD)pidl2 - 1) > 1) )
          {
            v9 = 0;
          }
          *((_BYTE *)this + 81) = v9;
        }
        if ( *((_DWORD *)this + 28) == 10 || (v10 = 0, *((_DWORD *)this + 28) == 102) )
          v10 = 1;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl'::`2'::impl)
          && *((_DWORD *)this + 28) == 101 )
        {
          v10 = 1;
        }
        if ( v10 )
        {
          v12 = -1;
          do
            ++v12;
          while ( (*v4)[v12] );
          v13 = 0;
          LOBYTE(v41) = 0;
          if ( *((_DWORD *)this + 28) == 102 )
          {
            LocalDiskLocation = 119;
          }
          else
          {
            LocalDiskLocation = PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(v11, v4, &v41);
            v13 = v41;
          }
          v15 = PiiSafeShellitemParsingNameProperties::CalculatePathDepth(v11, *v4, v8);
          *((_QWORD *)this + 1) |= (unsigned __int64)v48 << 32;
          LODWORD(pidl2) = (unsigned __int8)(v15 - v13);
          *(_QWORD *)this |= v15 | ((unsigned __int64)LocalDiskLocation << 40) | (unsigned int)((_DWORD)pidl2 << 8);
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pszPath,
            *v4,
            -1);
          v16 = pszPath;
          if ( v8 )
          {
            v17 = -1;
            do
              ++v17;
            while ( pszPath[v17] );
            PathCchRemoveFileSpec(pszPath, v17);
          }
          RelativeToRootPath = PiiSafeShellitemParsingNameProperties::GetRelativeToRootPath(
                                 pv,
                                 &pszPath,
                                 (unsigned int)v12,
                                 (unsigned int)pidl2);
          v19 = (__int64 *)((char *)this + 96);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            (char *)this + 96,
            RelativeToRootPath);
          if ( pv[0] )
            CoTaskMemFree(pv[0]);
          v20 = *v19;
          if ( *v19 )
          {
            v21 = -1;
            do
              ++v21;
            while ( *(_WORD *)(v20 + 2 * v21) );
            *(_QWORD *)this |= (unsigned __int16)v21 << 16;
            *((_QWORD *)this + 9) |= PiiSafeShellitemParsingNameProperties::GetKeywords(v20, (char *)this + 96) << 32;
          }
          if ( v8 )
          {
            InstanceOfChar = PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(*v4, 0x5Cu);
            v23 = details::safemake_cotaskmem_string_nothrow(&v42, InstanceOfChar);
            v24 = (_QWORD *)((char *)this + 104);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              (char *)this + 104,
              v23);
            if ( v42 )
              CoTaskMemFree(v42);
            if ( *v24 )
            {
              v25 = -1;
              do
                ++v25;
              while ( *(_WORD *)(*v24 + 2 * v25) );
              *((_QWORD *)this + 1) |= (unsigned __int16)v25;
              v26 = PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(*v4, 0x2Eu);
              if ( v26 )
              {
                ppidl[0] = 0;
                ppidl[1] = 0;
                v45 = 0;
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
                  if ( pidl2 )
                    CoTaskMemFree((LPVOID)pidl2);
                }
                Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(ppidl);
              }
              *((_QWORD *)this + 9) |= PiiSafeShellitemParsingNameProperties::GetKeywords(v27, (char *)this + 104);
            }
            else
            {
              PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(&v42, a2, &PKEY_FileExtension);
              if ( v42 )
              {
                pidl2 = 0;
                v30 = -1;
                do
                  ++v30;
                while ( v42[v30 + 1] );
                if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                            &pidl2,
                            L"%lu:%.4s") >= 0 )
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                    (char *)this + 16,
                    &pidl2);
                if ( pidl2 )
                  CoTaskMemFree((LPVOID)pidl2);
                if ( v42 )
                  CoTaskMemFree(v42);
              }
            }
            if ( PiiSafeShellitemParsingNameProperties::TryGetBooleanPropertyFromShellItem(a2, v29) )
            {
              PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
                &v42,
                a2,
                &PKEY_MsGraph_RecommendationReason);
              if ( v42 )
              {
                ReasonMarkerType = PiiSafeShellitemParsingNameProperties::GetReasonMarkerType(v42);
                if ( ReasonMarkerType > -1.0 )
                  *((_DWORD *)this + 21) = (int)ReasonMarkerType;
              }
              PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(&pidl2, a2, &PKEY_Home_DriveType);
              if ( pidl2 )
              {
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                  (char *)this + 24,
                  &pidl2);
                if ( pidl2 )
                  CoTaskMemFree((LPVOID)pidl2);
              }
              if ( v42 )
                CoTaskMemFree(v42);
            }
            PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(
              pv,
              a2,
              &PKEY_MsGraph_GraphFileType);
            if ( pv[0] )
            {
              pidl2 = 0;
              v32 = -1;
              do
                ++v32;
              while ( *((_WORD *)pv[0] + v32) );
              if ( (int)wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                          &pidl2,
                          L"%lu:%.50s") >= 0 )
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
                  (char *)this + 32,
                  &pidl2);
              if ( pidl2 )
                CoTaskMemFree((LPVOID)pidl2);
              if ( pv[0] )
                CoTaskMemFree(pv[0]);
            }
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((char *)this + 40);
          *((_QWORD *)this + 6) = -1;
          *((_QWORD *)this + 7) = -1;
          SyncProviderTelemetryHelpers::GetProviderNameAndInfoFlags(
            a2,
            (unsigned __int16 **)this + 5,
            (PiiSafeShellitemParsingNameProperties *)((char *)this + 64));
          if ( !IShellItem_IsPartialCloudFilePlaceholder(a2) || (v33 = !IsFolderNotStreamItem(a2), v34 = 1, v33) )
            v34 = 0;
          *((_BYTE *)this + 80) = v34;
          if ( !v16 )
            goto LABEL_98;
          v35 = (ITEMIDLIST *)v16;
        }
        else
        {
          if ( *((_DWORD *)this + 28) != 11 )
            goto LABEL_98;
          pidl2 = 0;
          ppidl[0] = (LPITEMIDLIST)&pidl2;
          ppidl[1] = 0;
          LOBYTE(v45) = 1;
          v36 = SHGetIDListFromObject((IUnknown *)a2, &ppidl[1]);
          if ( v36 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x4AC,
              (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\piiSafeShellitemParsingName.h",
              (const char *)(unsigned int)v36,
              v41);
          wil::details::out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(ppidl);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56275225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_56275225>::GetImpl'::`2'::impl) )
          {
            RegistryRootLocation = PiiSafeShellitemParsingNameProperties::TryGetRegistryRootLocation(v37, a2, &pidl2);
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
          v35 = (ITEMIDLIST *)pidl2;
          pidl2 = 0;
          if ( !v35 )
            goto LABEL_98;
        }
        CoTaskMemFree(v35);
LABEL_98:
        *((_BYTE *)this + 116) = 1;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v49);
      }
    }
  }
}

```

## disassembly

```asm
0x180546068  mov     [rsp-8+arg_10], rbx
0x18054606d  push    rbp
0x18054606e  push    rsi
0x18054606f  push    rdi
0x180546070  push    r12
0x180546072  push    r13
0x180546074  push    r14
0x180546076  push    r15
0x180546078  lea     rbp, [rsp-27h]
0x18054607d  sub     rsp, 90h
0x180546084  mov     rax, cs:__security_cookie
0x18054608b  xor     rax, rsp
0x18054608e  mov     [rbp+57h+var_40], rax
0x180546092  mov     r14, rdx
0x180546095  mov     rsi, rcx
0x180546098  xor     r12d, r12d
0x18054609b  cmp     [rcx+74h], r12b
0x18054609f  jnz     loc_18054665B
0x1805460a5  lea     r15, [rcx+58h]
0x1805460a9  mov     rax, [r15]
0x1805460ac  test    rax, rax
0x1805460af  jz      loc_18054665B
0x1805460b5  cmp     [rax], r12w
0x1805460b9  jz      loc_18054665B
0x1805460bf  mov     eax, [rcx+70h]
0x1805460c2  sub     eax, 64h ; 'd'
0x1805460c5  lea     edi, [r12+1]
0x1805460ca  cmp     eax, edi
0x1805460cc  jbe     short loc_1805460D5
0x1805460ce  call    ?PopulateShellitemParsingNameRootType@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootType@@XZ; PiiSafeShellitemParsingNameProperties::PopulateShellitemParsingNameRootType(void)
0x1805460d3  jmp     short loc_1805460D7
0x1805460d5  mov     al, 0C8h
0x1805460d7  movzx   eax, al
0x1805460da  shl     rax, 34h
0x1805460de  or      [rsi], rax
0x1805460e1  mov     [rbp+57h+var_50], r12d
0x1805460e5  mov     rax, [r14]
0x1805460e8  lea     r8, [rbp+57h+var_50]
0x1805460ec  mov     edx, 7EC13008h
0x1805460f1  mov     rcx, r14
0x1805460f4  mov     rax, [rax+30h]
0x1805460f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1805460fd  mov     rcx, [rbp+5Fh]; this
0x180546101  test    eax, eax
0x180546103  jns     short loc_18054611E
0x180546105  mov     r9d, eax; char *
0x180546108  lea     r8, aOnecoreuapInte_25; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18054610f  mov     edx, 41Ah; void *
0x180546114  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180546119  jmp     loc_18054665B
0x18054611e  mov     rcx, r14; struct IShellItem *
0x180546121  call    ?IShellItem_IsFolder@@YAHPEAUIShellItem@@@Z; IShellItem_IsFolder(IShellItem *)
0x180546126  test    eax, eax
0x180546128  jz      short loc_180546139
0x18054612a  mov     rcx, r14; struct IShellItem *
0x18054612d  call    ?IShellItem_IsContainerFile@@YAHPEAUIShellItem@@@Z; IShellItem_IsContainerFile(IShellItem *)
0x180546132  test    eax, eax
0x180546134  mov     r13b, r12b
0x180546137  jz      short loc_18054613C
0x180546139  mov     r13b, dil
0x18054613c  mov     [rbp+57h+var_48], r12
0x180546140  lea     rcx, [rbp+57h+var_48]
0x180546144  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180546149  nop
0x18054614a  mov     r8d, 8
0x180546150  mov     rdx, r14
0x180546153  lea     rcx, [rbp+57h+var_48]
0x180546157  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS)
0x18054615c  test    eax, eax
0x18054615e  js      short loc_18054619F
0x180546160  mov     dword ptr [rbp+57h+pidl2], r12d
0x180546164  movups  xmm0, xmmword ptr cs:PKEY_Home_GraphFileType.fmtid.Data1
0x18054616b  movaps  xmmword ptr [rbp+57h+ppidl], xmm0
0x18054616f  mov     eax, cs:PKEY_Home_GraphFileType.pid
0x180546175  mov     dword ptr [rbp+57h+var_70], eax
0x180546178  lea     r8, [rbp+57h+pidl2]
0x18054617c  lea     rdx, [rbp+57h+ppidl]
0x180546180  lea     rcx, [rbp+57h+var_48]
0x180546184  call    ??$GetUInt32@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAK@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetUInt32<_tagpropertykey>(_tagpropertykey,ulong *)
0x180546189  test    eax, eax
0x18054618b  js      short loc_180546199
0x18054618d  mov     eax, dword ptr [rbp+57h+pidl2]
0x180546190  dec     eax
0x180546192  cmp     eax, edi
0x180546194  mov     al, dil
0x180546197  jbe     short loc_18054619C
0x180546199  mov     al, r12b
0x18054619c  mov     [rsi+51h], al
0x18054619f  cmp     dword ptr [rsi+70h], 0Ah
0x1805461a3  jz      short loc_1805461AE
0x1805461a5  cmp     dword ptr [rsi+70h], 66h ; 'f'
0x1805461a9  mov     bl, r12b
0x1805461ac  jnz     short loc_1805461B1
0x1805461ae  mov     bl, dil
0x1805461b1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_60851339@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339> `wil::Feature<__WilFeatureTraits_Feature_60851339>::GetImpl(void)'::`2'::impl
0x1805461b8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_60851339@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60851339>::__private_IsEnabled(void)
0x1805461bd  test    al, al
0x1805461bf  jz      short loc_1805461CB
0x1805461c1  movzx   ebx, bl
0x1805461c4  cmp     dword ptr [rsi+70h], 65h ; 'e'
0x1805461c8  cmovz   ebx, edi
0x1805461cb  test    bl, bl
0x1805461cd  jz      loc_18054657A
0x1805461d3  mov     rax, [r15]
0x1805461d6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1805461da  inc     rdi
0x1805461dd  cmp     [rax+rdi*2], r12w
0x1805461e2  jnz     short loc_1805461DA
0x1805461e4  mov     bl, r12b
0x1805461e7  mov     byte ptr [rbp+57h+var_A0], bl
0x1805461ea  cmp     dword ptr [rsi+70h], 66h ; 'f'
0x1805461ee  jnz     short loc_1805461F5
0x1805461f0  mov     r12b, 77h ; 'w'
0x1805461f3  jmp     short loc_180546207
0x1805461f5  lea     r8, [rbp+57h+var_A0]
0x1805461f9  mov     rdx, r15
0x1805461fc  call    ?FindLocalDiskLocation@PiiSafeShellitemParsingNameProperties@@AEAA?AW4ShellitemParsingNameRootLoc@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEAE@Z; PiiSafeShellitemParsingNameProperties::FindLocalDiskLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,uchar &)
0x180546201  mov     r12b, al
0x180546204  mov     bl, byte ptr [rbp+57h+var_A0]
0x180546207  mov     r8b, r13b; bool
0x18054620a  mov     rdx, [r15]; unsigned __int16 *
0x18054620d  call    ?CalculatePathDepth@PiiSafeShellitemParsingNameProperties@@AEAAEPEBG_N@Z; PiiSafeShellitemParsingNameProperties::CalculatePathDepth(ushort const *,bool)
0x180546212  mov     ecx, [rbp+57h+var_50]
0x180546215  shl     rcx, 20h
0x180546219  or      [rsi+8], rcx
0x18054621d  mov     cl, al
0x18054621f  sub     cl, bl
0x180546221  movzx   ecx, cl
0x180546224  mov     dword ptr [rbp+57h+pidl2], ecx
0x180546227  shl     ecx, 8
0x18054622a  mov     edx, ecx
0x18054622c  movzx   ecx, r12b
0x180546230  shl     rcx, 28h
0x180546234  or      rdx, rcx
0x180546237  movzx   eax, al
0x18054623a  or      rdx, rax
0x18054623d  or      [rsi], rdx
0x180546240  or      r8, 0FFFFFFFFFFFFFFFFh
0x180546244  mov     rdx, [r15]
0x180546247  lea     rcx, [rbp+57h+pszPath]
0x18054624b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180546250  nop
0x180546251  mov     rbx, [rbp+57h+pszPath]
0x180546255  xor     r12d, r12d
0x180546258  test    r13b, r13b
0x18054625b  jz      short loc_180546274
0x18054625d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180546261  inc     rdx; cchPath
0x180546264  cmp     [rbx+rdx*2], r12w
0x180546269  jnz     short loc_180546261
0x18054626b  mov     rcx, rbx; pszPath
0x18054626e  call    cs:__imp_PathCchRemoveFileSpec
0x180546274  mov     r8d, edi
0x180546277  mov     r9d, dword ptr [rbp+57h+pidl2]
0x18054627b  lea     rdx, [rbp+57h+pszPath]
0x18054627f  lea     rcx, [rbp+57h+pv]
0x180546283  call    ?GetRelativeToRootPath@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV23@KK@Z; PiiSafeShellitemParsingNameProperties::GetRelativeToRootPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &,ulong,ulong)
0x180546288  lea     rdi, [rsi+60h]
0x18054628c  mov     rdx, rax
0x18054628f  mov     rcx, rdi
0x180546292  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180546297  mov     rcx, [rbp+57h+pv]; pv
0x18054629b  test    rcx, rcx
0x18054629e  jz      short loc_1805462A6
0x1805462a0  call    cs:__imp_CoTaskMemFree
0x1805462a6  mov     rcx, [rdi]
0x1805462a9  test    rcx, rcx
0x1805462ac  jz      short loc_1805462D7
0x1805462ae  or      rax, 0FFFFFFFFFFFFFFFFh
0x1805462b2  inc     rax
0x1805462b5  cmp     [rcx+rax*2], r12w
0x1805462ba  jnz     short loc_1805462B2
0x1805462bc  movzx   eax, ax
0x1805462bf  shl     eax, 10h
0x1805462c2  cdqe
0x1805462c4  or      [rsi], rax
0x1805462c7  mov     rdx, rdi
0x1805462ca  call    ?GetKeywords@PiiSafeShellitemParsingNameProperties@@AEAA_KAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PiiSafeShellitemParsingNameProperties::GetKeywords(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x1805462cf  shl     rax, 20h
0x1805462d3  or      [rsi+48h], rax
0x1805462d7  test    r13b, r13b
0x1805462da  jz      loc_180546524
0x1805462e0  mov     edx, 5Ch ; '\'; unsigned __int16
0x1805462e5  mov     rcx, [r15]; unsigned __int16 *
0x1805462e8  call    ?LastInstanceOfChar@PiiSafeShellitemParsingNameProperties@@CAPEBGPEBGG@Z; PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(ushort const *,ushort)
0x1805462ed  mov     rdx, rax
0x1805462f0  lea     rcx, [rbp+57h+var_98]
0x1805462f4  call    details__safemake_cotaskmem_string_nothrow
0x1805462f9  lea     rdi, [rsi+68h]
0x1805462fd  mov     rdx, rax
0x180546300  mov     rcx, rdi
0x180546303  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180546308  mov     rcx, [rbp+57h+var_98]; pv
0x18054630c  test    rcx, rcx
0x18054630f  jz      short loc_180546317
0x180546311  call    cs:__imp_CoTaskMemFree
0x180546317  mov     rdx, [rdi]
0x18054631a  test    rdx, rdx
0x18054631d  jz      loc_1805463C0
0x180546323  or      r13, 0FFFFFFFFFFFFFFFFh
0x180546327  mov     rax, r13
0x18054632a  inc     rax
0x18054632d  cmp     [rdx+rax*2], r12w
0x180546332  jnz     short loc_18054632A
0x180546334  movzx   eax, ax
0x180546337  or      [rsi+8], rax
0x18054633b  mov     edx, 2Eh ; '.'; unsigned __int16
0x180546340  mov     rcx, [r15]; unsigned __int16 *
0x180546343  call    ?LastInstanceOfChar@PiiSafeShellitemParsingNameProperties@@CAPEBGPEBGG@Z; PiiSafeShellitemParsingNameProperties::LastInstanceOfChar(ushort const *,ushort)
0x180546348  test    rax, rax
0x18054634b  jz      short loc_1805463B2
0x18054634d  mov     [rbp+57h+ppidl], r12
0x180546351  mov     [rbp+57h+ppidl+8], r12
0x180546355  mov     [rbp+57h+var_70], r12
0x180546359  mov     r8, r13
0x18054635c  inc     r8
0x18054635f  cmp     [rax+r8*2], r12w
0x180546364  jnz     short loc_18054635C
0x180546366  mov     r9, rax
0x180546369  lea     rdx, aLu4s; "%lu:%.4s"
0x180546370  lea     rcx, [rbp+57h+ppidl]
0x180546374  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x180546379  test    eax, eax
0x18054637b  js      short loc_1805463A9
0x18054637d  mov     r8, r13
0x180546380  mov     rdx, [rbp+57h+ppidl]
0x180546384  lea     rcx, [rbp+57h+pidl2]
0x180546388  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18054638d  lea     rcx, [rsi+10h]
0x180546391  lea     rdx, [rbp+57h+pidl2]
0x180546395  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18054639a  mov     rcx, [rbp+57h+pidl2]; pv
0x18054639e  test    rcx, rcx
0x1805463a1  jz      short loc_1805463A9
0x1805463a3  call    cs:__imp_CoTaskMemFree
0x1805463a9  lea     rcx, [rbp+57h+ppidl]; void *
0x1805463ad  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1805463b2  mov     rdx, rdi
0x1805463b5  call    ?GetKeywords@PiiSafeShellitemParsingNameProperties@@AEAA_KAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; PiiSafeShellitemParsingNameProperties::GetKeywords(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> const &)
0x1805463ba  or      [rsi+48h], rax
0x1805463be  jmp     short loc_180546434
0x1805463c0  lea     r8, PKEY_FileExtension
0x1805463c7  mov     rdx, r14
0x1805463ca  lea     rcx, [rbp+57h+var_98]
0x1805463ce  call    ?TryGetStringPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x1805463d3  mov     rax, [rbp+57h+var_98]
0x1805463d7  or      r13, 0FFFFFFFFFFFFFFFFh
0x1805463db  test    rax, rax
0x1805463de  jz      short loc_180546434
0x1805463e0  lea     r9, [rax+2]
0x1805463e4  mov     [rbp+57h+pidl2], r12
0x1805463e8  mov     r8, r13
0x1805463eb  inc     r8
0x1805463ee  cmp     [r9+r8*2], r12w
0x1805463f3  jnz     short loc_1805463EB
0x1805463f5  lea     rdx, aLu4s; "%lu:%.4s"
0x1805463fc  lea     rcx, [rbp+57h+pidl2]
0x180546400  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180546405  test    eax, eax
0x180546407  js      short loc_180546416
0x180546409  lea     rcx, [rsi+10h]
0x18054640d  lea     rdx, [rbp+57h+pidl2]
0x180546411  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180546416  mov     rcx, [rbp+57h+pidl2]; pv
0x18054641a  test    rcx, rcx
0x18054641d  jz      short loc_180546425
0x18054641f  call    cs:__imp_CoTaskMemFree
0x180546425  mov     rcx, [rbp+57h+var_98]; pv
0x180546429  test    rcx, rcx
0x18054642c  jz      short loc_180546434
0x18054642e  call    cs:__imp_CoTaskMemFree
0x180546434  mov     rcx, r14; struct IShellItem *
0x180546437  call    ?TryGetBooleanPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA_NPEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetBooleanPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x18054643c  test    al, al
0x18054643e  jz      short loc_1805464B8
0x180546440  lea     r8, PKEY_MsGraph_RecommendationReason
0x180546447  mov     rdx, r14
0x18054644a  lea     rcx, [rbp+57h+var_98]
0x18054644e  call    ?TryGetStringPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x180546453  nop
0x180546454  mov     rcx, [rbp+57h+var_98]; unsigned __int16 *
0x180546458  test    rcx, rcx
0x18054645b  jz      short loc_180546473
0x18054645d  call    ?GetReasonMarkerType@PiiSafeShellitemParsingNameProperties@@CANQEBG@Z; PiiSafeShellitemParsingNameProperties::GetReasonMarkerType(ushort const * const)
0x180546462  comisd  xmm0, cs:__real@bff0000000000000
0x18054646a  jbe     short loc_180546473
0x18054646c  cvttsd2si eax, xmm0
0x180546470  mov     [rsi+54h], eax
0x180546473  lea     r8, PKEY_Home_DriveType
0x18054647a  mov     rdx, r14
0x18054647d  lea     rcx, [rbp+57h+pidl2]
0x180546481  call    ?TryGetStringPropertyFromShellItem@PiiSafeShellitemParsingNameProperties@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIShellItem@@AEBU_tagpropertykey@@@Z; PiiSafeShellitemParsingNameProperties::TryGetStringPropertyFromShellItem(IShellItem *,_tagpropertykey const &)
0x180546486  cmp     [rbp+57h+pidl2], r12
0x18054648a  jz      short loc_1805464A9
0x18054648c  lea     rcx, [rsi+18h]
0x180546490  lea     rdx, [rbp+57h+pidl2]
0x180546494  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180546499  mov     rcx, [rbp+57h+pidl2]; pv
0x18054649d  test    rcx, rcx
0x1805464a0  jz      short loc_1805464A9
  ... truncated ...
```
