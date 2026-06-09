# RestoreMultiTaskingSettings::Run(void)

- ea: `0x18008a850`
- end: `0x18008ac14`
- name: `?Run@RestoreMultiTaskingSettings@@UEAA_NXZ`
- size: `964`
- prototype: `bool __fastcall(RestoreMultiTaskingSettings *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001649c`
- `0x180035c0c`
- `0x180036a3c`
- `0x1800871d4`
- `0x180087250`
- `0x1800872cc`
- `0x180087888`
- `0x180087968`
- `0x180087a48`
- `0x18008a850`
- `0x18008ac1c`
- `0x18008ac88`
- `0x18008ad74`

## string_xrefs

- `0x18008a922`: `EnableTaskGroups`
- `0x18008aae1`: `EnableTaskGroups`
- `0x18008a967`: `VirtualDesktopTaskbarFilter`
- `0x18008ab26`: `VirtualDesktopTaskbarFilter`
- `0x18008a9cd`: `MultiTaskingAltTabFilter`
- `0x18008ab8c`: `MultiTaskingAltTabFilter`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
char __fastcall RestoreMultiTaskingSettings::Run(RestoreMultiTaskingSettings *this)
{
  __int64 v1; // rcx
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  char v16; // [rsp+28h] [rbp-71h]
  int v17; // [rsp+28h] [rbp-71h]
  int v18; // [rsp+28h] [rbp-71h]
  int v19; // [rsp+28h] [rbp-71h]
  int v20; // [rsp+28h] [rbp-71h]
  int v21; // [rsp+28h] [rbp-71h]
  int v22; // [rsp+28h] [rbp-71h]
  char v23; // [rsp+28h] [rbp-71h]
  int v24; // [rsp+28h] [rbp-71h]
  int v25; // [rsp+28h] [rbp-71h]
  int v26; // [rsp+28h] [rbp-71h]
  int v27; // [rsp+28h] [rbp-71h]
  int v28; // [rsp+28h] [rbp-71h]
  int v29; // [rsp+28h] [rbp-71h]
  int v30; // [rsp+30h] [rbp-69h]
  int v31; // [rsp+30h] [rbp-69h]
  int v32; // [rsp+30h] [rbp-69h]
  int v33; // [rsp+30h] [rbp-69h]
  int v34; // [rsp+30h] [rbp-69h]
  int v35; // [rsp+30h] [rbp-69h]
  int v36; // [rsp+30h] [rbp-69h]
  int v37; // [rsp+30h] [rbp-69h]
  int v38; // [rsp+30h] [rbp-69h]
  int v39; // [rsp+30h] [rbp-69h]
  int v40; // [rsp+30h] [rbp-69h]
  int v41; // [rsp+30h] [rbp-69h]
  bool v42; // [rsp+40h] [rbp-59h] BYREF
  bool v43; // [rsp+41h] [rbp-58h]
  bool v44; // [rsp+42h] [rbp-57h]
  bool v45; // [rsp+43h] [rbp-56h]
  _BYTE v46[24]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v47[40]; // [rsp+68h] [rbp-31h] BYREF
  _BYTE v48[16]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int8 v49; // [rsp+A0h] [rbp+7h] BYREF
  unsigned __int8 v50; // [rsp+A1h] [rbp+8h]
  _BYTE v51[24]; // [rsp+B0h] [rbp+17h] BYREF
  unsigned __int8 v52; // [rsp+C8h] [rbp+2Fh] BYREF
  unsigned __int8 v53; // [rsp+C9h] [rbp+30h]
  _BYTE v54[24]; // [rsp+D8h] [rbp+3Fh] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixRestoreHang>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixRestoreHang>::GetImpl'::`2'::impl) )
  {
    wil::cloud_store::cloud_store(v47);
    wil::cloud_store::load<Windows::Data::Settings::MultiTasking::SnapWindows>(v47, &v42);
    v42 = (unsigned int)SetAeroSnapState(v42) != 0;
    v23 = 1;
    v43 = (unsigned int)SyncSetting(v8, L"SnapAssist", v43, 1, 3, v23, 30000) != 0;
    LOBYTE(v24) = 1;
    v44 = (unsigned int)SyncSetting(v9, L"EnableSnapAssistFlyout", v44, 1, 11, v24, v36) != 0;
    LOBYTE(v25) = 1;
    v45 = (unsigned int)SyncSetting(v10, L"EnableTaskGroups", v45, 1, 10, v25, v37) != 0;
    wil::cloud_store::save<Windows::Data::Settings::MultiTasking::SnapWindows>(v47, v48, &v42);
    wil::cloud_store::load<Windows::Data::Settings::MultiTasking::MultiTaskDesktop>(v47, &v49);
    LOBYTE(v26) = 1;
    v49 = SyncSetting(v11, L"VirtualDesktopTaskbarFilter", v49, 1, 8, v26, v38);
    LOBYTE(v27) = 1;
    v50 = SyncSetting(v12, L"VirtualDesktopAltTabFilter", v50, 1, 9, v27, v39);
    wil::cloud_store::save<Windows::Data::Settings::MultiTasking::MultiTaskDesktop>(v47, v48, &v49);
    wil::cloud_store::load<Windows::Data::Settings::MultiTasking::MultiTaskOthers>(v47, &v52);
    LOBYTE(v28) = 1;
    v52 = SyncSetting(v13, L"MultiTaskingAltTabFilter", v52, 2, 19, v28, v40);
    LOBYTE(v29) = 0;
    v53 = (unsigned int)SyncSetting(v14, L"DisallowShaking", v53 == 0, 1, 0, v29, v41) == 0;
    wil::cloud_store::save<Windows::Data::Settings::MultiTasking::MultiTaskOthers>(v47, v48, &v52);
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v54);
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v51);
  }
  else
  {
    wil::cloud_store::cloud_store(v47);
    wil::cloud_store::load<Windows::Data::Settings::MultiTasking::SnapWindows>(v47, &v42);
    v42 = (unsigned int)SetAeroSnapState(v42) != 0;
    v16 = 1;
    v43 = (unsigned int)SyncSetting(v1, L"SnapAssist", v43, 1, 3, v16, 0) != 0;
    LOBYTE(v17) = 1;
    v44 = (unsigned int)SyncSetting(v2, L"EnableSnapAssistFlyout", v44, 1, 11, v17, v30) != 0;
    LOBYTE(v18) = 1;
    v45 = (unsigned int)SyncSetting(v3, L"EnableTaskGroups", v45, 1, 10, v18, v31) != 0;
    wil::cloud_store::save<Windows::Data::Settings::MultiTasking::SnapWindows>(v47, v48, &v42);
    wil::cloud_store::load<Windows::Data::Settings::MultiTasking::MultiTaskDesktop>(v47, &v52);
    LOBYTE(v19) = 1;
    v52 = SyncSetting(v4, L"VirtualDesktopTaskbarFilter", v52, 1, 8, v19, v32);
    LOBYTE(v20) = 1;
    v53 = SyncSetting(v5, L"VirtualDesktopAltTabFilter", v53, 1, 9, v20, v33);
    wil::cloud_store::save<Windows::Data::Settings::MultiTasking::MultiTaskDesktop>(v47, v48, &v52);
    wil::cloud_store::load<Windows::Data::Settings::MultiTasking::MultiTaskOthers>(v47, &v49);
    LOBYTE(v21) = 1;
    v49 = SyncSetting(v6, L"MultiTaskingAltTabFilter", v49, 2, 19, v21, v34);
    LOBYTE(v22) = 0;
    v50 = (unsigned int)SyncSetting(v7, L"DisallowShaking", v50 == 0, 1, 0, v22, v35) == 0;
    wil::cloud_store::save<Windows::Data::Settings::MultiTasking::MultiTaskOthers>(v47, v48, &v49);
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v51);
    wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v54);
  }
  wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(v46);
  wil::cloud_store::~cloud_store((wil::cloud_store *)v47);
  return 1;
}

```

## disassembly

```asm
0x18008a850  mov     [rsp-8+arg_0], rbx
0x18008a855  mov     [rsp-8+arg_8], rdi
0x18008a85a  push    rbp
0x18008a85b  lea     rbp, [rsp-57h]
0x18008a860  sub     rsp, 0F0h
0x18008a867  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixRestoreHang@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixRestoreHang@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixRestoreHang> `wil::Feature<__WilFeatureTraits_Feature_FixRestoreHang>::GetImpl(void)'::`2'::impl
0x18008a86e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixRestoreHang@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixRestoreHang>::__private_IsEnabled(void)
0x18008a873  xor     edi, edi
0x18008a875  lea     rcx, [rbp+57h+var_88]
0x18008a879  test    al, al
0x18008a87b  jnz     loc_18008AA3A
0x18008a881  mov     [rsp+0F0h+var_C0], edi
0x18008a885  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x18008a88a  nop
0x18008a88b  lea     rdx, [rbp+57h+var_B0]
0x18008a88f  lea     rcx, [rbp+57h+var_88]
0x18008a893  call    ??$load@USnapWindows@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@USnapWindows@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Settings::MultiTasking::SnapWindows>(wil::cloud_store_load_options,char const *)
0x18008a898  nop
0x18008a899  mov     ecx, edi
0x18008a89b  cmp     [rbp+57h+var_B0], dil
0x18008a89f  setnz   cl; unsigned int
0x18008a8a2  call    ?SetAeroSnapState@@YAKK@Z; SetAeroSnapState(ulong)
0x18008a8a7  test    eax, eax
0x18008a8a9  setnz   [rbp+57h+var_B0]
0x18008a8ad  mov     r8d, edi
0x18008a8b0  cmp     [rbp+57h+var_AF], dil
0x18008a8b4  setnz   r8b
0x18008a8b8  lea     ebx, [rdi+1]
0x18008a8bb  mov     [rsp+0F0h+var_C8], bl
0x18008a8bf  mov     [rsp+0F0h+var_D0], 3
0x18008a8c7  mov     r9d, ebx
0x18008a8ca  lea     rdx, aSnapassist; "SnapAssist"
0x18008a8d1  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008a8d6  test    eax, eax
0x18008a8d8  setnz   [rbp+57h+var_AF]
0x18008a8dc  mov     r8d, edi
0x18008a8df  cmp     [rbp+57h+var_AE], dil
0x18008a8e3  setnz   r8b
0x18008a8e7  mov     [rsp+0F0h+var_C8], bl
0x18008a8eb  mov     [rsp+0F0h+var_D0], 0Bh
0x18008a8f3  mov     r9d, ebx
0x18008a8f6  lea     rdx, aEnablesnapassi; "EnableSnapAssistFlyout"
0x18008a8fd  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008a902  test    eax, eax
0x18008a904  setnz   [rbp+57h+var_AE]
0x18008a908  mov     r8d, edi
0x18008a90b  cmp     [rbp+57h+var_AD], dil
0x18008a90f  setnz   r8b
0x18008a913  mov     [rsp+0F0h+var_C8], bl
0x18008a917  mov     [rsp+0F0h+var_D0], 0Ah
0x18008a91f  mov     r9d, ebx
0x18008a922  lea     rdx, aEnabletaskgrou; "EnableTaskGroups"
0x18008a929  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008a92e  test    eax, eax
0x18008a930  setnz   [rbp+57h+var_AD]
0x18008a934  lea     r8, [rbp+57h+var_B0]
0x18008a938  lea     rdx, [rbp+57h+var_60]
0x18008a93c  lea     rcx, [rbp+57h+var_88]
0x18008a940  call    ??$save@USnapWindows@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@USnapWindows@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Settings::MultiTasking::SnapWindows>(wil::cloud_store_data<Windows::Data::Settings::MultiTasking::SnapWindows> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18008a945  lea     rdx, [rbp+57h+var_28]
0x18008a949  lea     rcx, [rbp+57h+var_88]
0x18008a94d  call    ??$load@UMultiTaskDesktop@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UMultiTaskDesktop@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Settings::MultiTasking::MultiTaskDesktop>(wil::cloud_store_load_options,char const *)
0x18008a952  nop
0x18008a953  movzx   r8d, [rbp+57h+var_28]
0x18008a958  mov     [rsp+0F0h+var_C8], bl
0x18008a95c  mov     [rsp+0F0h+var_D0], 8
0x18008a964  mov     r9d, ebx
0x18008a967  lea     rdx, aVirtualdesktop_1; "VirtualDesktopTaskbarFilter"
0x18008a96e  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008a973  mov     [rbp+57h+var_28], al
0x18008a976  movzx   r8d, [rbp+57h+var_27]
0x18008a97b  mov     [rsp+0F0h+var_C8], bl
0x18008a97f  mov     [rsp+0F0h+var_D0], 9
0x18008a987  mov     r9d, ebx
0x18008a98a  lea     rdx, aVirtualdesktop_0; "VirtualDesktopAltTabFilter"
0x18008a991  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008a996  mov     [rbp+57h+var_27], al
0x18008a999  lea     r8, [rbp+57h+var_28]
0x18008a99d  lea     rdx, [rbp+57h+var_60]
0x18008a9a1  lea     rcx, [rbp+57h+var_88]
0x18008a9a5  call    ??$save@UMultiTaskDesktop@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UMultiTaskDesktop@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Settings::MultiTasking::MultiTaskDesktop>(wil::cloud_store_data<Windows::Data::Settings::MultiTasking::MultiTaskDesktop> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18008a9aa  lea     rdx, [rbp+57h+var_50]
0x18008a9ae  lea     rcx, [rbp+57h+var_88]
0x18008a9b2  call    ??$load@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Settings::MultiTasking::MultiTaskOthers>(wil::cloud_store_load_options,char const *)
0x18008a9b7  nop
0x18008a9b8  movzx   r8d, [rbp+57h+var_50]
0x18008a9bd  mov     [rsp+0F0h+var_C8], bl
0x18008a9c1  mov     [rsp+0F0h+var_D0], 13h
0x18008a9c9  lea     r9d, [rdi+2]
0x18008a9cd  lea     rdx, aMultitaskingal_0; "MultiTaskingAltTabFilter"
0x18008a9d4  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008a9d9  mov     [rbp+57h+var_50], al
0x18008a9dc  mov     r8d, edi
0x18008a9df  cmp     [rbp+57h+var_4F], dil
0x18008a9e3  setz    r8b
0x18008a9e7  mov     [rsp+0F0h+var_C8], dil
0x18008a9ec  mov     [rsp+0F0h+var_D0], edi
0x18008a9f0  mov     r9d, ebx
0x18008a9f3  lea     rdx, aDisallowshakin; "DisallowShaking"
0x18008a9fa  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008a9ff  test    eax, eax
0x18008aa01  setz    [rbp+57h+var_4F]
0x18008aa05  lea     r8, [rbp+57h+var_50]
0x18008aa09  lea     rdx, [rbp+57h+var_60]
0x18008aa0d  lea     rcx, [rbp+57h+var_88]
0x18008aa11  call    ??$save@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Settings::MultiTasking::MultiTaskOthers>(wil::cloud_store_data<Windows::Data::Settings::MultiTasking::MultiTaskOthers> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18008aa16  nop
0x18008aa17  lea     rcx, [rbp+57h+var_40]
0x18008aa1b  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x18008aa20  nop
0x18008aa21  lea     rcx, [rbp+57h+var_18]
0x18008aa25  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x18008aa2a  nop
0x18008aa2b  lea     rcx, [rbp+57h+var_A0]
0x18008aa2f  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x18008aa34  nop
0x18008aa35  jmp     loc_18008ABF4
0x18008aa3a  mov     [rsp+0F0h+var_C0], 7530h
0x18008aa42  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x18008aa47  nop
0x18008aa48  lea     rdx, [rbp+57h+var_B0]
0x18008aa4c  lea     rcx, [rbp+57h+var_88]
0x18008aa50  call    ??$load@USnapWindows@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@USnapWindows@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Settings::MultiTasking::SnapWindows>(wil::cloud_store_load_options,char const *)
0x18008aa55  nop
0x18008aa56  mov     ecx, edi
0x18008aa58  cmp     [rbp+57h+var_B0], dil
0x18008aa5c  setnz   cl; unsigned int
0x18008aa5f  call    ?SetAeroSnapState@@YAKK@Z; SetAeroSnapState(ulong)
0x18008aa64  test    eax, eax
0x18008aa66  setnz   [rbp+57h+var_B0]
0x18008aa6a  mov     r8d, edi
0x18008aa6d  cmp     [rbp+57h+var_AF], dil
0x18008aa71  setnz   r8b
0x18008aa75  mov     ebx, 1
0x18008aa7a  mov     [rsp+0F0h+var_C8], bl
0x18008aa7e  mov     [rsp+0F0h+var_D0], 3
0x18008aa86  mov     r9d, ebx
0x18008aa89  lea     rdx, aSnapassist; "SnapAssist"
0x18008aa90  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008aa95  test    eax, eax
0x18008aa97  setnz   [rbp+57h+var_AF]
0x18008aa9b  mov     r8d, edi
0x18008aa9e  cmp     [rbp+57h+var_AE], dil
0x18008aaa2  setnz   r8b
0x18008aaa6  mov     [rsp+0F0h+var_C8], bl
0x18008aaaa  mov     [rsp+0F0h+var_D0], 0Bh
0x18008aab2  mov     r9d, ebx
0x18008aab5  lea     rdx, aEnablesnapassi; "EnableSnapAssistFlyout"
0x18008aabc  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008aac1  test    eax, eax
0x18008aac3  setnz   [rbp+57h+var_AE]
0x18008aac7  mov     r8d, edi
0x18008aaca  cmp     [rbp+57h+var_AD], dil
0x18008aace  setnz   r8b
0x18008aad2  mov     [rsp+0F0h+var_C8], bl
0x18008aad6  mov     [rsp+0F0h+var_D0], 0Ah
0x18008aade  mov     r9d, ebx
0x18008aae1  lea     rdx, aEnabletaskgrou; "EnableTaskGroups"
0x18008aae8  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008aaed  test    eax, eax
0x18008aaef  setnz   [rbp+57h+var_AD]
0x18008aaf3  lea     r8, [rbp+57h+var_B0]
0x18008aaf7  lea     rdx, [rbp+57h+var_60]
0x18008aafb  lea     rcx, [rbp+57h+var_88]
0x18008aaff  call    ??$save@USnapWindows@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@USnapWindows@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Settings::MultiTasking::SnapWindows>(wil::cloud_store_data<Windows::Data::Settings::MultiTasking::SnapWindows> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18008ab04  lea     rdx, [rbp+57h+var_50]
0x18008ab08  lea     rcx, [rbp+57h+var_88]
0x18008ab0c  call    ??$load@UMultiTaskDesktop@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UMultiTaskDesktop@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Settings::MultiTasking::MultiTaskDesktop>(wil::cloud_store_load_options,char const *)
0x18008ab11  nop
0x18008ab12  movzx   r8d, [rbp+57h+var_50]
0x18008ab17  mov     [rsp+0F0h+var_C8], bl
0x18008ab1b  mov     [rsp+0F0h+var_D0], 8
0x18008ab23  mov     r9d, ebx
0x18008ab26  lea     rdx, aVirtualdesktop_1; "VirtualDesktopTaskbarFilter"
0x18008ab2d  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008ab32  mov     [rbp+57h+var_50], al
0x18008ab35  movzx   r8d, [rbp+57h+var_4F]
0x18008ab3a  mov     [rsp+0F0h+var_C8], bl
0x18008ab3e  mov     [rsp+0F0h+var_D0], 9
0x18008ab46  mov     r9d, ebx
0x18008ab49  lea     rdx, aVirtualdesktop_0; "VirtualDesktopAltTabFilter"
0x18008ab50  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008ab55  mov     [rbp+57h+var_4F], al
0x18008ab58  lea     r8, [rbp+57h+var_50]
0x18008ab5c  lea     rdx, [rbp+57h+var_60]
0x18008ab60  lea     rcx, [rbp+57h+var_88]
0x18008ab64  call    ??$save@UMultiTaskDesktop@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UMultiTaskDesktop@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Settings::MultiTasking::MultiTaskDesktop>(wil::cloud_store_data<Windows::Data::Settings::MultiTasking::MultiTaskDesktop> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18008ab69  lea     rdx, [rbp+57h+var_28]
0x18008ab6d  lea     rcx, [rbp+57h+var_88]
0x18008ab71  call    ??$load@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Settings::MultiTasking::MultiTaskOthers>(wil::cloud_store_load_options,char const *)
0x18008ab76  nop
0x18008ab77  movzx   r8d, [rbp+57h+var_28]
0x18008ab7c  mov     [rsp+0F0h+var_C8], bl
0x18008ab80  mov     [rsp+0F0h+var_D0], 13h
0x18008ab88  lea     r9d, [rbx+1]
0x18008ab8c  lea     rdx, aMultitaskingal_0; "MultiTaskingAltTabFilter"
0x18008ab93  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008ab98  mov     [rbp+57h+var_28], al
0x18008ab9b  mov     r8d, edi
0x18008ab9e  cmp     [rbp+57h+var_27], dil
0x18008aba2  setz    r8b
0x18008aba6  mov     [rsp+0F0h+var_C8], dil
0x18008abab  mov     [rsp+0F0h+var_D0], edi
0x18008abaf  mov     r9d, ebx
0x18008abb2  lea     rdx, aDisallowshakin; "DisallowShaking"
0x18008abb9  call    ?SyncSetting@@YAKPEBG0KKW4SETTING_IDENTIFIER@@_N@Z; SyncSetting(ushort const *,ushort const *,ulong,ulong,SETTING_IDENTIFIER,bool)
0x18008abbe  test    eax, eax
0x18008abc0  setz    [rbp+57h+var_27]
0x18008abc4  lea     r8, [rbp+57h+var_28]
0x18008abc8  lea     rdx, [rbp+57h+var_60]
0x18008abcc  lea     rcx, [rbp+57h+var_88]
0x18008abd0  call    ??$save@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UMultiTaskOthers@MultiTasking@Settings@Data@Windows@@@1@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::Settings::MultiTasking::MultiTaskOthers>(wil::cloud_store_data<Windows::Data::Settings::MultiTasking::MultiTaskOthers> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18008abd5  nop
0x18008abd6  lea     rcx, [rbp+57h+var_18]
0x18008abda  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x18008abdf  nop
0x18008abe0  lea     rcx, [rbp+57h+var_40]
0x18008abe4  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x18008abe9  nop
0x18008abea  lea     rcx, [rbp+57h+var_A0]
0x18008abee  call    ??1?$com_ptr_t@UICloudDataRestore@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>::~com_ptr_t<Windows::Internal::Storage::Cloud::ICloudDataRestore,wil::err_exception_policy>(void)
0x18008abf3  nop
0x18008abf4  lea     rcx, [rbp+57h+var_88]; this
0x18008abf8  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x18008abfd  mov     al, bl
0x18008abff  lea     r11, [rsp+0F0h+var_s0]
0x18008ac07  mov     rbx, [r11+10h]
0x18008ac0b  mov     rdi, [r11+18h]
0x18008ac0f  mov     rsp, r11
0x18008ac12  pop     rbp
0x18008ac13  retn
```
