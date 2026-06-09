# _lambda_a35d1d3c2efa15fd8a590ef2da36bca9_::operator()_winrt::Windows::Internal::Shell::AppRestore::RestorableApp_

- ea: `0x18006b230`
- end: `0x18006b45b`
- name: `_lambda_a35d1d3c2efa15fd8a590ef2da36bca9_::operator()_winrt::Windows::Internal::Shell::AppRestore::RestorableApp_`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006e244`

## callees

- `0x180012b84`
- `0x180012c0c`
- `0x1800162a4`
- `0x180020ee8`
- `0x1800283c4`
- `0x180031f38`
- `0x180036ea8`
- `0x1800388d4`
- `0x180038934`
- `0x18006b230`
- `0x18006b658`
- `0x18006e1f0`
- `0x18006e374`
- `0x18006e45c`
- `0x18006f638`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18006b2ab`
- `KERNEL32!CompareStringOrdinal` at `0x18006b2ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall lambda_a35d1d3c2efa15fd8a590ef2da36bca9_::operator()_winrt::Windows::Internal::Shell::AppRestore::RestorableApp_(
        __int64 a1,
        __int64 a2)
{
  char v4; // si
  unsigned int v5; // eax
  char result; // al
  const WCHAR *v7; // rax
  char v8; // di
  LPCWCH v9; // r8
  __int64 v10; // rbx
  __int64 v11; // rax
  char v12; // bl
  winrt::hstring *v13; // rax
  __int64 v14; // rax
  winrt::hstring *AllRestorableTiles; // rax
  const WCHAR *v16; // rax
  winrt::hstring *v17; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-29h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v20[8]; // [rsp+40h] [rbp-19h] BYREF
  const unsigned __int16 *v21; // [rsp+48h] [rbp-11h] BYREF
  const WCHAR *v22; // [rsp+50h] [rbp-9h] BYREF
  unsigned __int16 *v23; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v24[8]; // [rsp+60h] [rbp+7h] BYREF
  _BYTE v25[8]; // [rsp+68h] [rbp+Fh] BYREF
  _BYTE v26[8]; // [rsp+70h] [rbp+17h] BYREF
  _BYTE v27[8]; // [rsp+78h] [rbp+1Fh] BYREF
  _BYTE v28[48]; // [rsp+80h] [rbp+27h] BYREF
  char v29; // [rsp+D0h] [rbp+77h] BYREF
  const unsigned __int16 *v30; // [rsp+D8h] [rbp+7Fh] BYREF

  v4 = 0;
  LODWORD(v30) = 0;
  v5 = winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::CatalogSource(a2);
  result = winrt::Windows::Internal::Shell::AppRestore::implementation::IsSupported(v5);
  if ( result )
  {
    winrt::impl::consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableTileStoreInternal<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableTileStoreInternal>::FindAllRestorableTiles(
      a1,
      v20);
    winrt::impl::consume_Windows_Internal_UserSettingsBackup_Orchestrator_IBackupUnitSummary<winrt::Windows::Internal::UserSettingsBackup::Orchestrator::IBackupUnitSummary>::Id(
      a2,
      v19);
    winrt::hstring::c_str((winrt::hstring *)v19);
    v7 = winrt::hstring::c_str((winrt::hstring *)v20);
    v8 = 1;
    if ( CompareStringOrdinal(v7, -1, v9, -1, 1) == 2 )
    {
      ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 204LL);
LABEL_16:
      winrt::handle_type<winrt::impl::hstring_traits>::close(v19);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v20);
      return v8;
    }
    v10 = winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::TelemetryId(
            a2,
            v18);
    v11 = winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::FullName(
            a1,
            &v29);
    LOBYTE(v10) = winrt::operator==(v11, v10);
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v29);
    winrt::handle_type<winrt::impl::hstring_traits>::close(v18);
    if ( (_BYTE)v10 )
    {
      winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableAppInternal>(
        a2,
        v18);
      v12 = winrt::impl::consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableAppInternal<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableAppInternal>::AreProductCodeAndAppNameEqual(v18);
      v29 = v12;
      v13 = (winrt::hstring *)winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::TelemetryId(
                                a2,
                                v28);
      v21 = winrt::hstring::c_str(v13);
      if ( *(_QWORD *)winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::CompatibleData(
                        a2,
                        v27) )
      {
        v14 = winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::CompatibleData(
                a2,
                v26);
        LODWORD(v30) = 1;
        AllRestorableTiles = (winrt::hstring *)winrt::impl::consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableTileStoreInternal<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableTileStoreInternal>::FindAllRestorableTiles(
                                                 v14,
                                                 v25);
        v4 = 3;
        LODWORD(v30) = 3;
        v16 = winrt::hstring::c_str(AllRestorableTiles);
      }
      else
      {
        v16 = &word_1801382A0;
      }
      v22 = v16;
      v17 = (winrt::hstring *)winrt::impl::consume_Windows_Internal_UserSettingsBackup_Orchestrator_IBackupUnitSummary<winrt::Windows::Internal::UserSettingsBackup::Orchestrator::IBackupUnitSummary>::Id(
                                a2,
                                v24);
      v30 = winrt::hstring::c_str(v17);
      v23 = CloudRestoreLauncherTelemetry::s_restoredDeviceProfileId;
      CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps_SameTileAndProductName<unsigned short *,unsigned short const *,unsigned short const *,unsigned short const *,bool &>(
        (unsigned int)&v23,
        (unsigned int)&v30,
        (unsigned int)&v22,
        (unsigned int)&v21,
        (__int64)&v29);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v24);
      if ( (v4 & 2) != 0 )
      {
        v4 &= ~2u;
        winrt::handle_type<winrt::impl::hstring_traits>::close(v25);
      }
      if ( (v4 & 1) != 0 )
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v26);
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v27);
      winrt::handle_type<winrt::impl::hstring_traits>::close(v28);
      if ( v12 )
      {
        ++*(_DWORD *)(*(_QWORD *)(a1 + 8) + 208LL);
        _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v18);
        goto LABEL_16;
      }
      _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_((_lambda_12ef4a55c56a96ec7ad58335194b061f_ *)v18);
    }
    v8 = 0;
    goto LABEL_16;
  }
  return result;
}

```

## disassembly

```asm
0x18006b230  mov     [rsp-8+arg_0], rbx
0x18006b235  push    rbp
0x18006b236  push    rsi
0x18006b237  push    rdi
0x18006b238  push    r14
0x18006b23a  push    r15
0x18006b23c  lea     rbp, [rsp-37h]
0x18006b241  sub     rsp, 90h
0x18006b248  mov     r14, rdx
0x18006b24b  mov     r15, rcx
0x18006b24e  xor     esi, esi
0x18006b250  mov     dword ptr [rbp+57h+arg_18], esi
0x18006b253  mov     rcx, rdx
0x18006b256  call    ?CatalogSource@?$consume_Windows_Internal_Shell_AppRestore_IRestorableApp@UIRestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::CatalogSource(void)
0x18006b25b  mov     ecx, eax
0x18006b25d  call    ?IsSupported@implementation@AppRestore@Shell@Internal@Windows@winrt@@YA_NW4CatalogSource@23456@@Z; winrt::Windows::Internal::Shell::AppRestore::implementation::IsSupported(winrt::Windows::Internal::Shell::AppRestore::CatalogSource)
0x18006b262  test    al, al
0x18006b264  jz      loc_18006B444
0x18006b26a  lea     rdx, [rbp+57h+var_70]
0x18006b26e  mov     rcx, r15
0x18006b271  call    ?FindAllRestorableTiles@?$consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableTileStoreInternal@UIRestorableTileStoreInternal@Internal@AppRestore@Shell@2Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableTileStoreInternal<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableTileStoreInternal>::FindAllRestorableTiles(void)
0x18006b276  nop
0x18006b277  lea     rdx, [rbp+57h+var_78]
0x18006b27b  mov     rcx, r14
0x18006b27e  call    ?Id@?$consume_Windows_Internal_UserSettingsBackup_Orchestrator_IBackupUnitSummary@UIBackupUnitSummary@Orchestrator@UserSettingsBackup@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UserSettingsBackup_Orchestrator_IBackupUnitSummary<winrt::Windows::Internal::UserSettingsBackup::Orchestrator::IBackupUnitSummary>::Id(void)
0x18006b283  nop
0x18006b284  lea     rcx, [rbp+57h+var_78]; this
0x18006b288  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18006b28d  mov     r8, rax
0x18006b290  lea     rcx, [rbp+57h+var_70]; this
0x18006b294  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18006b299  mov     rcx, rax; lpString1
0x18006b29c  mov     edi, 1
0x18006b2a1  mov     [rsp+0B0h+bIgnoreCase], edi; bIgnoreCase
0x18006b2a5  or      edx, 0FFFFFFFFh; cchCount1
0x18006b2a8  mov     r9d, edx; cchCount2
0x18006b2ab  call    cs:__imp_CompareStringOrdinal
0x18006b2b1  cmp     eax, 2
0x18006b2b4  jnz     short loc_18006B2C5
0x18006b2b6  mov     rcx, [r15+8]
0x18006b2ba  add     [rcx+0CCh], edi
0x18006b2c0  jmp     loc_18006B42E
0x18006b2c5  lea     rdx, [rbp+57h+var_80]
0x18006b2c9  mov     rcx, r14
0x18006b2cc  call    ?TelemetryId@?$consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::TelemetryId(void)
0x18006b2d1  mov     rbx, rax
0x18006b2d4  lea     rdx, [rbp+57h+arg_10]
0x18006b2d8  mov     rcx, r15
0x18006b2db  call    ?FullName@?$consume_Windows_ApplicationModel_IPackageId@UIPackageId@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_IPackageId<winrt::Windows::ApplicationModel::IPackageId>::FullName(void)
0x18006b2e0  mov     rdx, rbx
0x18006b2e3  mov     rcx, rax
0x18006b2e6  call    ??8winrt@@YA_NAEBUhstring@0@0@Z; winrt::operator==(winrt::hstring const &,winrt::hstring const &)
0x18006b2eb  mov     bl, al
0x18006b2ed  lea     rcx, [rbp+57h+arg_10]
0x18006b2f1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18006b2f6  nop
0x18006b2f7  lea     rcx, [rbp+57h+var_80]
0x18006b2fb  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18006b300  test    bl, bl
0x18006b302  jz      loc_18006B42B
0x18006b308  lea     rdx, [rbp+57h+var_80]
0x18006b30c  mov     rcx, r14
0x18006b30f  call    ??$as@UIRestorableAppInternal@Internal@AppRestore@Shell@2Windows@winrt@@@IUnknown@Foundation@Windows@winrt@@QEBA?A_PXZ
0x18006b314  nop
0x18006b315  lea     rcx, [rbp+57h+var_80]
0x18006b319  call    ?AreProductCodeAndAppNameEqual@?$consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableAppInternal@UIRestorableAppInternal@Internal@AppRestore@Shell@2Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableAppInternal<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableAppInternal>::AreProductCodeAndAppNameEqual(void)
0x18006b31e  mov     bl, al
0x18006b320  mov     [rbp+57h+arg_10], al
0x18006b323  lea     rdx, [rbp+57h+var_30]
0x18006b327  mov     rcx, r14
0x18006b32a  call    ?TelemetryId@?$consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier@UIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_WindowsInternal_Shell_UnifiedTile_IUnifiedTileIdentifier<winrt::WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier>::TelemetryId(void)
0x18006b32f  nop
0x18006b330  mov     rcx, rax; this
0x18006b333  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18006b338  mov     [rbp+57h+var_68], rax
0x18006b33c  lea     rdx, [rbp+57h+var_38]
0x18006b340  mov     rcx, r14
0x18006b343  call    ?CompatibleData@?$consume_Windows_Internal_Shell_AppRestore_IRestorableApp@UIRestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::CompatibleData(void)
0x18006b348  nop
0x18006b349  cmp     qword ptr [rax], 0
0x18006b34d  jz      short loc_18006B37E
0x18006b34f  lea     rdx, [rbp+57h+var_40]
0x18006b353  mov     rcx, r14
0x18006b356  call    ?CompatibleData@?$consume_Windows_Internal_Shell_AppRestore_IRestorableApp@UIRestorableApp@AppRestore@Shell@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_IRestorableApp<winrt::Windows::Internal::Shell::AppRestore::IRestorableApp>::CompatibleData(void)
0x18006b35b  nop
0x18006b35c  mov     dword ptr [rbp+57h+arg_18], edi
0x18006b35f  lea     rdx, [rbp+57h+var_48]
0x18006b363  mov     rcx, rax
0x18006b366  call    ?FindAllRestorableTiles@?$consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableTileStoreInternal@UIRestorableTileStoreInternal@Internal@AppRestore@Shell@2Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Shell_AppRestore_Internal_IRestorableTileStoreInternal<winrt::Windows::Internal::Shell::AppRestore::Internal::IRestorableTileStoreInternal>::FindAllRestorableTiles(void)
0x18006b36b  nop
0x18006b36c  mov     esi, 3
0x18006b371  mov     dword ptr [rbp+57h+arg_18], esi
0x18006b374  mov     rcx, rax; this
0x18006b377  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18006b37c  jmp     short loc_18006B385
0x18006b37e  lea     rax, word_1801382A0
0x18006b385  mov     [rbp+57h+var_60], rax
0x18006b389  lea     rdx, [rbp+57h+var_50]
0x18006b38d  mov     rcx, r14
0x18006b390  call    ?Id@?$consume_Windows_Internal_UserSettingsBackup_Orchestrator_IBackupUnitSummary@UIBackupUnitSummary@Orchestrator@UserSettingsBackup@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_UserSettingsBackup_Orchestrator_IBackupUnitSummary<winrt::Windows::Internal::UserSettingsBackup::Orchestrator::IBackupUnitSummary>::Id(void)
0x18006b395  mov     rcx, rax; this
0x18006b398  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18006b39d  mov     [rbp+57h+arg_18], rax
0x18006b3a1  mov     rax, cs:?s_restoredDeviceProfileId@CloudRestoreLauncherTelemetry@@2V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> CloudRestoreLauncherTelemetry::s_restoredDeviceProfileId
0x18006b3a8  mov     [rbp+57h+var_58], rax
0x18006b3ac  lea     rax, [rbp+57h+arg_10]
0x18006b3b0  mov     qword ptr [rsp+0B0h+bIgnoreCase], rax
0x18006b3b5  lea     r9, [rbp+57h+var_68]
0x18006b3b9  lea     r8, [rbp+57h+var_60]
0x18006b3bd  lea     rdx, [rbp+57h+arg_18]
0x18006b3c1  lea     rcx, [rbp+57h+var_58]
0x18006b3c5  call    ??$AppRestoreOrchestratorRestoreApps_SameTileAndProductName@PEAGPEBGPEBGPEBGAEA_N@CloudRestoreLauncherTelemetry@@SAX$$QEAPEAG$$QEAPEBG11AEA_N@Z; CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps_SameTileAndProductName<ushort *,ushort const *,ushort const *,ushort const *,bool &>(ushort * &&,ushort const * &&,ushort const * &&,ushort const * &&,bool &)
0x18006b3ca  lea     rcx, [rbp+57h+var_50]
0x18006b3ce  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18006b3d3  nop
0x18006b3d4  test    sil, 2
0x18006b3d8  jz      short loc_18006B3E7
0x18006b3da  and     esi, 0FFFFFFFDh
0x18006b3dd  lea     rcx, [rbp+57h+var_48]
0x18006b3e1  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18006b3e6  nop
0x18006b3e7  test    dil, sil
0x18006b3ea  jz      short loc_18006B3F6
0x18006b3ec  lea     rcx, [rbp+57h+var_40]; this
0x18006b3f0  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18006b3f5  nop
0x18006b3f6  lea     rcx, [rbp+57h+var_38]; this
0x18006b3fa  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18006b3ff  nop
0x18006b400  lea     rcx, [rbp+57h+var_30]
0x18006b404  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18006b409  test    bl, bl
0x18006b40b  jz      short loc_18006B422
0x18006b40d  mov     rax, [r15+8]
0x18006b411  add     [rax+0D0h], edi
0x18006b417  lea     rcx, [rbp+57h+var_80]; this
0x18006b41b  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18006b420  jmp     short loc_18006B42E
0x18006b422  lea     rcx, [rbp+57h+var_80]; this
0x18006b426  call    ??1_lambda_12ef4a55c56a96ec7ad58335194b061f_@@QEAA@XZ; _lambda_12ef4a55c56a96ec7ad58335194b061f_::~_lambda_12ef4a55c56a96ec7ad58335194b061f_(void)
0x18006b42b  xor     dil, dil
0x18006b42e  lea     rcx, [rbp+57h+var_78]
0x18006b432  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18006b437  nop
0x18006b438  lea     rcx, [rbp+57h+var_70]
0x18006b43c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18006b441  mov     al, dil
0x18006b444  mov     rbx, [rsp+0B0h+arg_0]
0x18006b44c  add     rsp, 90h
0x18006b453  pop     r15
0x18006b455  pop     r14
0x18006b457  pop     rdi
0x18006b458  pop     rsi
0x18006b459  pop     rbp
0x18006b45a  retn
```
