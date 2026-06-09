# CSyncRootManagerCache::InitializeStorageProviderInfosCache(HKEY__ *,tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>> &,SPGSP_FLAGS)

- ea: `0x1800165bc`
- end: `0x180016b31`
- name: `?InitializeStorageProviderInfosCache@CSyncRootManagerCache@@AEAAJPEAUHKEY__@@AEAV?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@W4SPGSP_FLAGS@@@Z`
- size: `1397`
- prototype: `__int64 __fastcall(__int64, HKEY, __int64, int)`
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180009374`

## callees

- `0x180006a10`
- `0x1800077c8`
- `0x1800077ec`
- `0x180007900`
- `0x180007c58`
- `0x18000a838`
- `0x18000fdf0`
- `0x18000ffec`
- `0x180015a1c`
- `0x1800165bc`
- `0x180016b38`
- `0x180016bb0`
- `0x180016bd8`
- `0x180016bf4`
- `0x180016d28`
- `0x180016d78`
- `0x180016dac`
- `0x180016fe8`
- `0x180017a98`
- `0x180017ab0`
- `0x180017d28`
- `0x180017fc8`
- `0x1800180b0`
- `0x1800272c8`
- `0x18002edcc`
- `0x180037c5c`
- `0x180038708`

## import_xrefs

- `SHCORE!SHEnumKeyExW` at `0x180016720`
- `SHCORE!SHEnumKeyExW` at `0x180016720`
- `SHCORE!SHQueryInfoKeyW` at `0x180016615`
- `SHCORE!SHQueryInfoKeyW` at `0x180016615`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001684c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016962`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001684c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016962`

## string_xrefs

- `0x18001667a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x18001686a`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180016a68`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180016ab5`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180016ad3`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`
- `0x180016af9`: `shellcommon\shell\fileexplorer\windows.fileexplorer.common\src\syncrootmanager.cpp`

## pseudocode

```c
__int64 __fastcall CSyncRootManagerCache::InitializeStorageProviderInfosCache(__int64 a1, HKEY a2, __int64 a3, int a4)
{
  HKEY v5; // rdi
  DWORD v7; // esi
  LSTATUS v8; // ebx
  DWORD v9; // eax
  LPWSTR v10; // r15
  __int64 v12; // rdi
  unsigned int v13; // eax
  void *v14; // rbx
  CStorageProviderRootsCache *v15; // rdi
  CStorageProviderRootsCache *v16; // rbx
  __int64 v17; // rax
  int v18; // eax
  int v19; // ecx
  int v20; // ecx
  _WORD *v21; // rax
  int v22; // esi
  __int64 v23; // rdx
  __int64 v24; // rdx
  CStorageProviderRootsCache **v25; // rax
  __int64 v26; // rsi
  __int64 v27; // rsi
  __int64 UserIdentity; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdx
  unsigned int v32; // edx
  unsigned int v33; // [rsp+28h] [rbp-59h]
  DWORD pcSubKeys; // [rsp+38h] [rbp-49h] BYREF
  int v35; // [rsp+3Ch] [rbp-45h]
  __int128 v36; // [rsp+40h] [rbp-41h] BYREF
  _BYTE v37[8]; // [rsp+50h] [rbp-31h] BYREF
  _BYTE v38[8]; // [rsp+58h] [rbp-29h] BYREF
  void *v39; // [rsp+60h] [rbp-21h] BYREF
  DWORD v40; // [rsp+68h] [rbp-19h]
  LPWSTR pszName; // [rsp+70h] [rbp-11h] BYREF
  DWORD pcchName; // [rsp+78h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-1h] BYREF
  _QWORD *v44; // [rsp+88h] [rbp+7h]
  _QWORD v45[8]; // [rsp+98h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]
  DWORD pcchMaxSubKeyLen; // [rsp+E8h] [rbp+67h] BYREF
  HKEY v48; // [rsp+F0h] [rbp+6Fh]
  int v49; // [rsp+100h] [rbp+7Fh]

  v49 = a4;
  v48 = a2;
  v5 = a2;
  v7 = 0;
  v44 = (_QWORD *)(a1 + 104);
  winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Clear(a1 + 104);
  pcSubKeys = 0;
  pcchMaxSubKeyLen = 0;
  v8 = SHQueryInfoKeyW(v5, &pcSubKeys, &pcchMaxSubKeyLen, 0, 0);
  if ( v8 < 0 )
  {
    v31 = 3800;
LABEL_56:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
      (const char *)(unsigned int)v8,
      v33);
    return (unsigned int)v8;
  }
  v8 = CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::_EnsureCapacity(
         a1 + 32,
         pcSubKeys);
  if ( v8 < 0 )
  {
    v31 = 3802;
    goto LABEL_56;
  }
  v35 = 0;
  v9 = ++pcchMaxSubKeyLen;
  while ( 1 )
  {
    v40 = v7;
    if ( v7 >= pcSubKeys )
    {
      v12 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(a3);
      pszName = (LPWSTR)v12;
      if ( v12 )
        _InterlockedIncrement((volatile signed __int32 *)(v12 + 280));
      tip2::details::shared_data<0,0,0>::begin_update(v12 + 8);
      *(_DWORD *)(v12 + 272) = v35;
      tip2::details::shared_data<0,0,0>::end_update(v12 + 8);
      wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::reset(&pszName);
      wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>(&pszName);
      if ( (unsigned int)IsDesktopExplorerProcess() )
      {
        *(_QWORD *)&v36 = *v44;
        winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v36);
        v30 = WNF_SHEL_SYNC_ROOT_IDENTITIES;
      }
      else
      {
        if ( !g_isWamEnabledForTests )
          return 0;
        *(_QWORD *)&v36 = *v44;
        winrt::Windows::Foundation::IUnknown::add_ref((winrt::Windows::Foundation::IUnknown *)&v36);
        v30 = (__int64)g_testWnfStateName;
      }
      WnfValueSet::Publish(v30, &v36);
      return 0;
    }
    pcchName = v9;
    wil::make_cotaskmem_string_nothrow((wil *)&pszName, 0, v9);
    v10 = pszName;
    if ( !pszName )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEE2,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)0x8007000ELL,
        v33);
      return 2147942414LL;
    }
    v13 = SHEnumKeyExW(v5, v7, pszName, &pcchName);
    if ( v13 )
      break;
    v14 = operator new(0x2A8u);
    v39 = v14;
    memset_0(v14, 0, 0x2A8u);
    v15 = CStorageProviderRootsCache::CStorageProviderRootsCache((CStorageProviderRootsCache *)v14);
    v16 = v15;
    v39 = v15;
    if ( !v15 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEE6,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)0x8007000ELL,
        v33);
LABEL_31:
      v22 = -2147024882;
      goto LABEL_32;
    }
    v36 = 0;
    v17 = *(_QWORD *)(a1 + 88);
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
    v36 = *(_OWORD *)(a1 + 80);
    v18 = CStorageProviderRootsCache::Initialize((_DWORD)v15, (_DWORD)v48, (_DWORD)v10, (unsigned int)&v36, v49);
    LODWORD(v36) = v18;
    if ( v18 == -2147024882 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xEEA,
        (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
        (const char *)0x8007000ELL,
        v33);
      CStorageProviderRootsCache::`scalar deleting destructor'(v15, v32);
      goto LABEL_31;
    }
    if ( v18 >= 0 )
    {
      v19 = *((_DWORD *)v15 + 164);
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          if ( v20 != 1 )
          {
LABEL_21:
            if ( *((_QWORD *)v15 + 27) )
            {
              v21 = (_WORD *)*((_QWORD *)v15 + 33);
              if ( v21 )
              {
                if ( *v21 && *((_QWORD *)v15 + 36) )
                {
                  v27 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(a3);
                  *(_QWORD *)&v36 = v27;
                  if ( v27 )
                    _InterlockedIncrement((volatile signed __int32 *)(v27 + 280));
                  tip2::details::shared_data<0,0,0>::begin_update(v27 + 8);
                  *(_BYTE *)(v27 + 279) = 1;
                  tip2::details::shared_data<0,0,0>::end_update(v27 + 8);
                  wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::reset(&v36);
                  wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>(&v36);
                  UserIdentity = CStorageProviderRootsCache::GetUserIdentity(v15, &v36);
                  v45[0] = v10;
                  v45[1] = std::_WChar_traits<unsigned short>::length(v10, v29, UserIdentity);
                  CSyncRootManagerCache::AddSyncRootWnfData(a1, v45);
                  winrt::handle_type<winrt::impl::hstring_traits>::close(v38);
                  winrt::handle_type<winrt::impl::hstring_traits>::close(v37);
                  winrt::handle_type<winrt::impl::hstring_traits>::close((char *)&v36 + 8);
                }
              }
            }
            v16 = 0;
            v39 = 0;
            v22 = 0;
            v23 = *(_QWORD *)(a1 + 40);
            if ( v23 != *(_QWORD *)(a1 + 56)
              || (v22 = CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::_EnsureCapacity(
                          a1 + 32,
                          v23 + 1),
                  v22 >= 0) )
            {
              v24 = *(_QWORD *)(a1 + 40);
              *(_QWORD *)(a1 + 40) = v24 + 1;
              v25 = (CStorageProviderRootsCache **)(*(_QWORD *)(a1 + 32) + 8 * v24);
              if ( !v25 )
              {
LABEL_27:
                ++v35;
                v15 = 0;
                v7 = v40;
                goto LABEL_28;
              }
              *v25 = v15;
            }
            if ( v22 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xF14,
                (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
                (const char *)(unsigned int)v22,
                v33);
              goto LABEL_32;
            }
            goto LABEL_27;
          }
          v26 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(a3);
          *(_QWORD *)&v36 = v26;
          if ( v26 )
            _InterlockedIncrement((volatile signed __int32 *)(v26 + 280));
          tip2::details::shared_data<0,0,0>::begin_update(v26 + 8);
          *(_BYTE *)(v26 + 277) = 1;
        }
        else
        {
          wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            &pv,
            v10,
            -1);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            a1 + 96,
            &pv);
          if ( pv )
            CoTaskMemFree(pv);
          v26 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(a3);
          *(_QWORD *)&v36 = v26;
          if ( v26 )
            _InterlockedIncrement((volatile signed __int32 *)(v26 + 280));
          tip2::details::shared_data<0,0,0>::begin_update(v26 + 8);
          *(_BYTE *)(v26 + 276) = 1;
        }
      }
      else
      {
        v26 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(a3);
        *(_QWORD *)&v36 = v26;
        if ( v26 )
          _InterlockedIncrement((volatile signed __int32 *)(v26 + 280));
        tip2::details::shared_data<0,0,0>::begin_update(v26 + 8);
        *(_BYTE *)(v26 + 278) = 1;
      }
      tip2::details::shared_data<0,0,0>::end_update(v26 + 8);
      wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::reset(&v36);
      wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>(&v36);
      goto LABEL_21;
    }
    v39 = v10;
    CloudFilesTelemetry::StorageProviderRootsCache_InitializeFailed<long const &,unsigned short *>(&v36, &v39, 0);
LABEL_28:
    if ( v16 )
    {
      if ( v15 )
        CStorageProviderRootsCache::`scalar deleting destructor'(v15, v24);
    }
    CoTaskMemFree(v10);
    ++v7;
    v9 = pcchMaxSubKeyLen;
    v5 = v48;
  }
  v22 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xEE3,
          (unsigned int)"shellcommon\\shell\\fileexplorer\\windows.fileexplorer.common\\src\\syncrootmanager.cpp",
          (const char *)v13,
          v33);
LABEL_32:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszName);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1800165bc  mov     rax, rsp
0x1800165bf  mov     [rax+18h], rbx
0x1800165c3  mov     [rax+20h], r9d
0x1800165c7  mov     [rax+10h], rdx
0x1800165cb  push    rbp
0x1800165cc  push    rsi
0x1800165cd  push    rdi
0x1800165ce  push    r12
0x1800165d0  push    r13
0x1800165d2  push    r14
0x1800165d4  push    r15
0x1800165d6  lea     rbp, [rax-5Fh]
0x1800165da  sub     rsp, 0A0h
0x1800165e1  mov     r12, r8
0x1800165e4  mov     rdi, rdx
0x1800165e7  mov     r13, rcx
0x1800165ea  xor     esi, esi
0x1800165ec  lea     r15, [rcx+68h]
0x1800165f0  mov     [rbp+57h+var_50], r15
0x1800165f4  mov     rcx, r15
0x1800165f7  call    ?Clear@?$consume_Windows_Foundation_Collections_IMap@UIPropertySet@Collections@Foundation@Windows@winrt@@Uhstring@5@UIInspectable@345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Foundation::Collections::IPropertySet,winrt::hstring,winrt::Windows::Foundation::IInspectable>::Clear(void)
0x1800165fc  mov     [rbp+57h+pcSubKeys], esi
0x1800165ff  mov     [rbp+57h+pcchMaxSubKeyLen], esi
0x180016602  mov     [rsp+20h], rsi; unsigned int
0x180016607  xor     r9d, r9d; pcValues
0x18001660a  lea     r8, [rbp+57h+pcchMaxSubKeyLen]; pcchMaxSubKeyLen
0x18001660e  lea     rdx, [rbp+57h+pcSubKeys]; pcSubKeys
0x180016612  mov     rcx, rdi; hkey
0x180016615  call    cs:__imp_SHQueryInfoKeyW
0x18001661b  mov     ebx, eax
0x18001661d  test    eax, eax
0x18001661f  js      loc_180016A5C
0x180016625  lea     r14, [r13+20h]
0x180016629  mov     edx, [rbp+57h+pcSubKeys]
0x18001662c  mov     rcx, r14
0x18001662f  call    ?_EnsureCapacity@?$CTSimpleArray@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardCompareHelper@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardMergeHelper@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@@@QEAAJ_K0@Z; CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180016634  mov     ebx, eax
0x180016636  test    eax, eax
0x180016638  js      loc_180016A63
0x18001663e  mov     [rbp+57h+var_9C], esi
0x180016641  mov     eax, [rbp+57h+pcchMaxSubKeyLen]
0x180016644  inc     eax
0x180016646  mov     [rbp+57h+pcchMaxSubKeyLen], eax
0x180016649  mov     [rbp+57h+var_70], esi
0x18001664c  cmp     esi, [rbp+57h+pcSubKeys]
0x18001664f  jnb     short loc_180016693
0x180016651  mov     [rbp+57h+pcchName], eax
0x180016654  mov     r8d, eax; unsigned __int64
0x180016657  xor     edx, edx; unsigned __int16 *
0x180016659  lea     rcx, [rbp+57h+pszName]; this
0x18001665d  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180016662  nop
0x180016663  mov     r15, [rbp+57h+pszName]
0x180016667  test    r15, r15
0x18001666a  jnz     loc_180016714
0x180016670  mov     rcx, [rbp+5Fh]; this
0x180016674  mov     r9d, 8007000Eh; char *
0x18001667a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180016681  mov     edx, 0EE2h; void *
0x180016686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001668b  nop
0x18001668c  mov     eax, 8007000Eh
0x180016691  jmp     short loc_1800166F9
0x180016693  mov     rcx, r12
0x180016696  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(void)
0x18001669b  mov     rdi, [rax]
0x18001669e  mov     [rbp+57h+pszName], rdi
0x1800166a2  xor     esi, esi
0x1800166a4  test    rdi, rdi
0x1800166a7  jz      short loc_1800166B0
0x1800166a9  lock inc dword ptr [rdi+118h]
0x1800166b0  lea     rcx, [rdi+8]
0x1800166b4  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800166b9  mov     eax, [rbp+57h+var_9C]
0x1800166bc  mov     [rdi+110h], eax
0x1800166c2  lea     rcx, [rdi+8]
0x1800166c6  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x1800166cb  lea     rcx, [rbp+57h+pszName]
0x1800166cf  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::reset(void)
0x1800166d4  lea     rcx, [rbp+57h+pszName]
0x1800166d8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>(void)
0x1800166dd  call    IsDesktopExplorerProcess
0x1800166e2  test    eax, eax
0x1800166e4  jnz     loc_180016A16
0x1800166ea  cmp     cs:?g_isWamEnabledForTests@@3_NA, sil; bool g_isWamEnabledForTests
0x1800166f1  jnz     loc_180016B11
0x1800166f7  xor     eax, eax
0x1800166f9  mov     rbx, [rsp+0D0h+arg_10]
0x180016701  add     rsp, 0A0h
0x180016708  pop     r15
0x18001670a  pop     r14
0x18001670c  pop     r13
0x18001670e  pop     r12
0x180016710  pop     rdi
0x180016711  pop     rsi
0x180016712  pop     rbp
0x180016713  retn
0x180016714  lea     r9, [rbp+57h+pcchName]; pcchName
0x180016718  mov     r8, r15; pszName
0x18001671b  mov     edx, esi; dwIndex
0x18001671d  mov     rcx, rdi; hkey
0x180016720  call    cs:__imp_SHEnumKeyExW
0x180016726  test    eax, eax
0x180016728  jnz     loc_180016AF2
0x18001672e  mov     edi, 2A8h
0x180016733  mov     ecx, edi; Size
0x180016735  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001673a  mov     rbx, rax
0x18001673d  mov     [rbp+57h+var_78], rax
0x180016741  mov     r8d, edi; Size
0x180016744  xor     edx, edx; Val
0x180016746  mov     rcx, rax; void *
0x180016749  call    memset_0
0x18001674e  mov     rcx, rbx; this
0x180016751  call    ??0CStorageProviderRootsCache@@QEAA@XZ; CStorageProviderRootsCache::CStorageProviderRootsCache(void)
0x180016756  mov     rdi, rax
0x180016759  mov     rbx, rax
0x18001675c  mov     [rbp+57h+var_78], rax
0x180016760  test    rax, rax
0x180016763  jz      loc_180016860
0x180016769  xorps   xmm0, xmm0
0x18001676c  movdqu  [rbp+57h+var_98], xmm0
0x180016771  mov     rax, [r13+58h]
0x180016775  test    rax, rax
0x180016778  jz      short loc_18001677E
0x18001677a  lock inc dword ptr [rax+8]
0x18001677e  mov     rax, [r13+50h]
0x180016782  mov     qword ptr [rbp+57h+var_98], rax
0x180016786  mov     rax, [r13+58h]
0x18001678a  mov     qword ptr [rbp+57h+var_98+8], rax
0x18001678e  mov     eax, [rbp+57h+arg_18]
0x180016791  mov     [rsp+20h], eax; int
0x180016795  lea     r9, [rbp+57h+var_98]
0x180016799  mov     r8, r15
0x18001679c  mov     rdx, [rbp+57h+arg_8]
0x1800167a0  mov     rcx, rdi
0x1800167a3  call    ?Initialize@CStorageProviderRootsCache@@QEAAJPEAUHKEY__@@PEBGV?$shared_ptr@VWamAccountsCache@@@std@@W4SPGSP_FLAGS@@@Z; CStorageProviderRootsCache::Initialize(HKEY__ *,ushort const *,std::shared_ptr<WamAccountsCache>,SPGSP_FLAGS)
0x1800167a8  mov     dword ptr [rbp+57h+var_98], eax
0x1800167ab  mov     edx, 8007000Eh
0x1800167b0  cmp     eax, edx
0x1800167b2  jz      loc_180016ACC
0x1800167b8  xor     r8d, r8d
0x1800167bb  test    eax, eax
0x1800167bd  js      loc_180016A82
0x1800167c3  mov     ecx, [rdi+290h]
0x1800167c9  test    ecx, ecx
0x1800167cb  jz      loc_180016891
0x1800167d1  sub     ecx, 1
0x1800167d4  jz      loc_1800168DF
0x1800167da  cmp     ecx, 1
0x1800167dd  jz      loc_180016932
0x1800167e3  cmp     [rdi+0D8h], r8
0x1800167ea  jz      short loc_1800167FC
0x1800167ec  mov     rax, [rdi+108h]
0x1800167f3  test    rax, rax
0x1800167f6  jnz     loc_18001696A
0x1800167fc  mov     rbx, r8
0x1800167ff  mov     [rbp+57h+var_78], rbx
0x180016803  mov     esi, r8d
0x180016806  mov     rdx, [r14+8]
0x18001680a  cmp     rdx, [r14+18h]
0x18001680e  jz      loc_180016A3F
0x180016814  mov     rdx, [r14+8]; unsigned int
0x180016818  lea     rcx, [rdx+1]
0x18001681c  mov     [r14+8], rcx
0x180016820  mov     rcx, [r14]
0x180016823  lea     rax, [rcx+rdx*8]
0x180016827  test    rax, rax
0x18001682a  jz      short loc_180016837
0x18001682c  mov     [rax], rdi
0x18001682f  test    esi, esi
0x180016831  js      loc_180016AAE
0x180016837  inc     [rbp+57h+var_9C]
0x18001683a  mov     rdi, r8
0x18001683d  mov     esi, [rbp+57h+var_70]
0x180016840  test    rbx, rbx
0x180016843  jnz     loc_180016A98
0x180016849  mov     rcx, r15; pv
0x18001684c  call    cs:__imp_CoTaskMemFree
0x180016852  inc     esi
0x180016854  mov     eax, [rbp+57h+pcchMaxSubKeyLen]
0x180016857  mov     rdi, [rbp+57h+arg_8]
0x18001685b  jmp     loc_180016649
0x180016860  mov     rcx, [rbp+5Fh]; this
0x180016864  mov     r9d, 8007000Eh; char *
0x18001686a  lea     r8, aShellcommonShe_2; "shellcommon\\shell\\fileexplorer\\windo"...
0x180016871  mov     edx, 0EE6h; void *
0x180016876  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001687b  nop
0x18001687c  mov     esi, 8007000Eh
0x180016881  lea     rcx, [rbp+57h+pszName]; void *
0x180016885  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18001688a  mov     eax, esi
0x18001688c  jmp     loc_1800166F9
0x180016891  mov     rcx, r12
0x180016894  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(void)
0x180016899  mov     rsi, [rax]
0x18001689c  mov     qword ptr [rbp+57h+var_98], rsi
0x1800168a0  test    rsi, rsi
0x1800168a3  jz      short loc_1800168AC
0x1800168a5  lock inc dword ptr [rsi+118h]
0x1800168ac  lea     rcx, [rsi+8]
0x1800168b0  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800168b5  mov     byte ptr [rsi+116h], 1
0x1800168bc  lea     rcx, [rsi+8]
0x1800168c0  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x1800168c5  lea     rcx, [rbp+57h+var_98]
0x1800168c9  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::reset(void)
0x1800168ce  lea     rcx, [rbp+57h+var_98]
0x1800168d2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>(void)
0x1800168d7  xor     r8d, r8d
0x1800168da  jmp     loc_1800167E3
0x1800168df  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800168e3  mov     rdx, r15
0x1800168e6  lea     rcx, [rbp+57h+pv]
0x1800168ea  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800168ef  lea     rcx, [r13+60h]
0x1800168f3  lea     rdx, [rbp+57h+pv]
0x1800168f7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800168fc  mov     rcx, [rbp+57h+pv]; pv
0x180016900  test    rcx, rcx
0x180016903  jnz     short loc_180016962
0x180016905  mov     rcx, r12
0x180016908  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(void)
0x18001690d  mov     rsi, [rax]
0x180016910  mov     qword ptr [rbp+57h+var_98], rsi
0x180016914  test    rsi, rsi
0x180016917  jz      short loc_180016920
0x180016919  lock inc dword ptr [rsi+118h]
0x180016920  lea     rcx, [rsi+8]
0x180016924  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180016929  mov     byte ptr [rsi+114h], 1
0x180016930  jmp     short loc_1800168BC
0x180016932  mov     rcx, r12
0x180016935  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(void)
0x18001693a  mov     rsi, [rax]
0x18001693d  mov     qword ptr [rbp+57h+var_98], rsi
0x180016941  test    rsi, rsi
0x180016944  jz      short loc_18001694D
0x180016946  lock inc dword ptr [rsi+118h]
0x18001694d  lea     rcx, [rsi+8]
0x180016951  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x180016956  mov     byte ptr [rsi+115h], 1
0x18001695d  jmp     loc_1800168BC
0x180016962  call    cs:__imp_CoTaskMemFree
0x180016968  jmp     short loc_180016905
0x18001696a  cmp     [rax], r8w
0x18001696e  jz      loc_1800167FC
0x180016974  cmp     [rdi+120h], r8
0x18001697b  jz      loc_1800167FC
0x180016981  mov     rcx, r12
0x180016984  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>>::ensure_data(void)
0x180016989  mov     rsi, [rax]
0x18001698c  mov     qword ptr [rbp+57h+var_98], rsi
0x180016990  test    rsi, rsi
0x180016993  jz      short loc_18001699C
0x180016995  lock inc dword ptr [rsi+118h]
0x18001699c  lea     rcx, [rsi+8]
0x1800169a0  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x1800169a5  mov     byte ptr [rsi+117h], 1
0x1800169ac  lea     rcx, [rsi+8]
0x1800169b0  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x1800169b5  lea     rcx, [rbp+57h+var_98]
0x1800169b9  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::reset(void)
0x1800169be  lea     rcx, [rbp+57h+var_98]
0x1800169c2  call    ??1?$com_ptr_t@V?$merged_data@U_tip_PrimarySyncRootCalculationTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_PrimarySyncRootCalculationTest,_tip_PrimarySyncRootCalculationTest>,wil::err_returncode_policy>(void)
0x1800169c7  lea     rdx, [rbp+57h+var_98]
0x1800169cb  mov     rcx, rdi
0x1800169ce  call    CStorageProviderRootsCache__GetUserIdentity
0x1800169d3  mov     r8, rax
0x1800169d6  mov     [rbp+57h+var_40], r15
0x1800169da  mov     rcx, r15
0x1800169dd  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800169e2  mov     [rbp+57h+var_38], rax
0x1800169e6  lea     rdx, [rbp+57h+var_40]
0x1800169ea  mov     rcx, r13
0x1800169ed  call    CSyncRootManagerCache__AddSyncRootWnfData
0x1800169f2  nop
0x1800169f3  lea     rcx, [rbp+57h+var_80]
0x1800169f7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800169fc  lea     rcx, [rbp+57h+var_88]
0x180016a00  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180016a05  lea     rcx, [rbp+57h+var_98+8]
0x180016a09  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180016a0e  xor     r8d, r8d
0x180016a11  jmp     loc_1800167FC
0x180016a16  mov     rax, [rbp+57h+var_50]
0x180016a1a  mov     rax, [rax]
0x180016a1d  mov     qword ptr [rbp+57h+var_98], rax
0x180016a21  lea     rcx, [rbp+57h+var_98]; this
0x180016a25  call    ?add_ref@IUnknown@Foundation@Windows@winrt@@AEBAXXZ; winrt::Windows::Foundation::IUnknown::add_ref(void)
0x180016a2a  mov     rcx, cs:WNF_SHEL_SYNC_ROOT_IDENTITIES
0x180016a31  lea     rdx, [rbp+57h+var_98]
0x180016a35  call    ?Publish@WnfValueSet@@YAXU_WNF_STATE_NAME@@UValueSet@Collections@Foundation@Windows@winrt@@@Z; WnfValueSet::Publish(_WNF_STATE_NAME,winrt::Windows::Foundation::Collections::ValueSet)
0x180016a3a  jmp     loc_1800166F7
0x180016a3f  inc     rdx
0x180016a42  mov     rcx, r14
0x180016a45  call    ?_EnsureCapacity@?$CTSimpleArray@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardCompareHelper@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@V?$CSimpleArrayStandardMergeHelper@V?$unique_ptr@UExplorerCommandVerb@StateRepoHelpers@@U?$default_delete@UExplorerCommandVerb@StateRepoHelpers@@@wistd@@@wistd@@@@@@QEAAJ_K0@Z; CTSimpleArray<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>,4294967294,CTPolicyCoTaskMem<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardCompareHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>,CSimpleArrayStandardMergeHelper<wistd::unique_ptr<StateRepoHelpers::ExplorerCommandVerb,wistd::default_delete<StateRepoHelpers::ExplorerCommandVerb>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180016a4a  mov     esi, eax
0x180016a4c  xor     r8d, r8d
  ... truncated ...
```
