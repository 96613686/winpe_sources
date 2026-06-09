# SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingToggle::DoGenericAsyncWork(void)

- ea: `0x180034ca0`
- end: `0x180034f52`
- name: `?DoGenericAsyncWork@CRenewableChargingToggle@BatterySaverOneCoreDataModel@SystemSettings@@UEAAXXZ`
- size: `690`
- prototype: `void __fastcall(SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingToggle *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180017998`
- `0x180019d34`
- `0x18002570c`
- `0x18002abc4`
- `0x18003448c`
- `0x180034510`
- `0x180034548`
- `0x180034ca0`
- `0x1800372d0`
- `0x180037bc8`
- `0x180037e3c`
- `0x180037e68`
- `0x180039608`
- `0x18003a4ec`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180034d43`
- `ntdll!RtlPublishWnfStateData` at `0x180034d43`

## string_xrefs

- `0x180034e86`: `CRenewableChargingTipTestReason::registry_update_failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingToggle::DoGenericAsyncWork(
        SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingToggle *this)
{
  SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingToggle *v2; // rcx
  int v3; // edi
  volatile signed __int32 *v4; // rbx
  volatile signed __int32 *v5; // rbx
  const char *v6; // rdx
  const char *v7; // rax
  int v8; // edi
  __int64 v9; // r8
  volatile signed __int32 *v10; // rbx
  const char *v11; // rdx
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  _QWORD v14[4]; // [rsp+30h] [rbp-19h] BYREF
  void **v15; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v16[48]; // [rsp+58h] [rbp+Fh] BYREF
  volatile signed __int32 *v17; // [rsp+88h] [rbp+3Fh]
  bool v18; // [rsp+B0h] [rbp+67h] BYREF
  volatile signed __int32 *v19; // [rsp+B8h] [rbp+6Fh] BYREF
  volatile signed __int32 **v20; // [rsp+C0h] [rbp+77h] BYREF

  v19 = 0;
  tip2::tip_test<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::start(
    (__int64 *)&v19,
    (__int64)v14);
  v15 = &tip2::test_watcher<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>>::`vftable';
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v16,
    (struct wil::details::IFailureCallback *)&v15,
    0,
    1);
  v17 = v19;
  if ( v19 )
    _InterlockedIncrement(v19 + 70);
  wil::com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>((void **)&v19);
  memset(v14, 0, 24);
  v18 = *((_BYTE *)this + 272) == 0;
  v3 = RtlPublishWnfStateData(WNF_PO_POWER_ADAPTER_REC_OVERRIDE, 0, &v18, 1, 0);
  if ( v3 < 0 )
  {
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180057650);
    v4 = v17;
    v19 = v17;
    if ( v17 )
      _InterlockedIncrement(v17 + 70);
    tip2::details::shared_data<1,0,0>::begin_update((__int64)(v4 + 2));
    *((_DWORD *)v4 + 68) = v3 | 0x10000000;
    tip2::test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(&v19);
    v5 = v17;
    v19 = v17;
    if ( v17 )
      _InterlockedIncrement(v17 + 70);
    tip2::details::shared_data<1,0,0>::begin_update((__int64)(v5 + 2));
    v7 = tip2::details::reason_string((tip2::details *)"CRenewableChargingTipTestReason::wnf_publish_failed", v6);
    if ( *((_BYTE *)v5 + 168) )
      goto LABEL_11;
    *((_BYTE *)v5 + 168) = 3;
    *((_WORD *)v5 + 85) = 2;
LABEL_10:
    *((_QWORD *)v5 + 22) = v7;
LABEL_11:
    *((_DWORD *)v5 + 18) |= 0xB00u;
    if ( *((_QWORD *)v5 + 31) )
      tip2::details::shared_data<1,0,0>::complete_helper((__int64)(v5 + 2), 10);
    goto LABEL_25;
  }
  v8 = SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingToggle::SetRECStatusRegistry(
         v2,
         L"IsRECEnabled",
         L"dword");
  if ( v8 < 0 )
  {
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180057650);
    v10 = v17;
    v19 = v17;
    if ( v17 )
      _InterlockedIncrement(v17 + 70);
    tip2::details::shared_data<1,0,0>::begin_update((__int64)(v10 + 2));
    *((_DWORD *)v10 + 68) = v8;
    tip2::test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(&v19);
    v5 = v17;
    v19 = v17;
    if ( v17 )
      _InterlockedIncrement(v17 + 70);
    tip2::details::shared_data<1,0,0>::begin_update((__int64)(v5 + 2));
    v7 = tip2::details::reason_string((tip2::details *)"CRenewableChargingTipTestReason::registry_update_failed", v11);
    if ( *((_BYTE *)v5 + 168) )
      goto LABEL_11;
    *((_BYTE *)v5 + 168) = 3;
    *((_WORD *)v5 + 85) = 3;
    goto LABEL_10;
  }
  LODWORD(v19) = *((unsigned __int8 *)this + 272);
  v20 = &v19;
  SystemSettings::DataModel::CSingletonHelper<int>::_Notify<_lambda_e398eed577395da8d81f0cd0fd7d36b5_>(
    (__int64)&SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStateSingleton,
    (unsigned int **)&v20,
    v9);
  v12 = v17;
  v19 = v17;
  if ( v17 )
    _InterlockedIncrement(v17 + 70);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v12 + 2));
  *((_DWORD *)v12 + 68) = v8;
  tip2::test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(&v19);
  v13 = v17;
  v19 = v17;
  if ( v17 )
    _InterlockedIncrement(v17 + 70);
  tip2::details::shared_data<1,0,0>::begin_update((__int64)(v13 + 2));
  tip2::details::shared_data<1,0,0>::complete((__int64)(v13 + 2));
LABEL_25:
  tip2::test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(&v19);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)v14);
  tip2::test_watcher<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_watcher<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(&v15);
}

```

## disassembly

```asm
0x180034ca0  push    rbp
0x180034ca2  push    rbx
0x180034ca3  push    rdi
0x180034ca4  lea     rbp, [rsp-47h]
0x180034ca9  sub     rsp, 90h
0x180034cb0  mov     rbx, rcx
0x180034cb3  mov     [rbp+57h+arg_8], 0
0x180034cbb  lea     rdx, [rbp+57h+var_70]
0x180034cbf  lea     rcx, [rbp+57h+arg_8]
0x180034cc3  call    ?start@?$tip_test@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@@tip2@@QEAA?AU_GUID@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::start(void)
0x180034cc8  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_EnergySaverToggleTest@@U1@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<_tip_EnergySaverToggleTest,_tip_EnergySaverToggleTest>>::`vftable'
0x180034ccf  mov     [rbp+57h+var_50], rax
0x180034cd3  mov     r9b, 1; bool
0x180034cd6  xor     r8d, r8d; struct wil::CallContextInfo *
0x180034cd9  lea     rdx, [rbp+57h+var_50]; struct wil::details::IFailureCallback *
0x180034cdd  lea     rcx, [rbp+57h+var_48]; this
0x180034ce1  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180034ce6  mov     rax, [rbp+57h+arg_8]
0x180034cea  mov     [rbp+57h+var_18], rax
0x180034cee  test    rax, rax
0x180034cf1  jz      short loc_180034CFA
0x180034cf3  lock inc dword ptr [rax+118h]
0x180034cfa  lea     rcx, [rbp+57h+arg_8]
0x180034cfe  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>,wil::err_returncode_policy>(void)
0x180034d03  nop
0x180034d04  mov     [rbp+57h+var_70], 0
0x180034d0c  mov     [rbp+57h+var_68], 0
0x180034d14  mov     [rbp+57h+var_60], 0
0x180034d1c  cmp     byte ptr [rbx+110h], 0
0x180034d23  setz    [rbp+57h+arg_0]
0x180034d27  mov     [rsp+0A0h+var_80], 0
0x180034d30  mov     r9d, 1
0x180034d36  lea     r8, [rbp+57h+arg_0]
0x180034d3a  xor     edx, edx
0x180034d3c  mov     rcx, cs:WNF_PO_POWER_ADAPTER_REC_OVERRIDE
0x180034d43  call    cs:__imp_RtlPublishWnfStateData
0x180034d49  mov     edi, eax
0x180034d4b  test    eax, eax
0x180034d4d  jns     loc_180034E03
0x180034d53  lea     rdx, stru_180057650; unsigned __int16 *
0x180034d5a  mov     rcx, rbx; this
0x180034d5d  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180034d62  mov     rbx, [rbp+57h+var_18]
0x180034d66  mov     [rbp+57h+arg_8], rbx
0x180034d6a  test    rbx, rbx
0x180034d6d  jz      short loc_180034D76
0x180034d6f  lock inc dword ptr [rbx+118h]
0x180034d76  lea     rcx, [rbx+8]
0x180034d7a  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180034d7f  bts     edi, 1Ch
0x180034d83  mov     [rbx+110h], edi
0x180034d89  lea     rcx, [rbp+57h+arg_8]
0x180034d8d  call    ??1?$test_data_control@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(void)
0x180034d92  mov     rbx, [rbp+57h+var_18]
0x180034d96  mov     [rbp+57h+arg_8], rbx
0x180034d9a  test    rbx, rbx
0x180034d9d  jz      short loc_180034DA6
0x180034d9f  lock inc dword ptr [rbx+118h]
0x180034da6  lea     rcx, [rbx+8]
0x180034daa  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180034daf  lea     rcx, aCrenewablechar; "CRenewableChargingTipTestReason::wnf_pu"...
0x180034db6  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180034dbb  cmp     byte ptr [rbx+0A8h], 0
0x180034dc2  jnz     short loc_180034DDB
0x180034dc4  mov     byte ptr [rbx+0A8h], 3
0x180034dcb  mov     word ptr [rbx+0AAh], 2
0x180034dd4  mov     [rbx+0B0h], rax
0x180034ddb  or      dword ptr [rbx+48h], 0B00h
0x180034de2  cmp     qword ptr [rbx+0F8h], 0
0x180034dea  jz      loc_180034F2A
0x180034df0  mov     edx, 0Ah
0x180034df5  lea     rcx, [rbx+8]
0x180034df9  call    ?complete_helper@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<1,0,0>::complete_helper(TestQueryOptions)
0x180034dfe  jmp     loc_180034F2A
0x180034e03  xor     r9d, r9d
0x180034e06  cmp     [rbx+110h], r9b
0x180034e0d  setnz   r9b; unsigned __int64
0x180034e11  lea     r8, aDword; "dword"
0x180034e18  lea     rdx, aIsrecenabled; "IsRECEnabled"
0x180034e1f  call    ?SetRECStatusRegistry@CRenewableChargingToggle@BatterySaverOneCoreDataModel@SystemSettings@@AEAAJPEBG0_K@Z; SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingToggle::SetRECStatusRegistry(ushort const *,ushort const *,unsigned __int64)
0x180034e24  mov     edi, eax
0x180034e26  test    eax, eax
0x180034e28  jns     loc_180034EB6
0x180034e2e  lea     rdx, stru_180057650; unsigned __int16 *
0x180034e35  mov     rcx, rbx; this
0x180034e38  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180034e3d  mov     rbx, [rbp+57h+var_18]
0x180034e41  mov     [rbp+57h+arg_8], rbx
0x180034e45  test    rbx, rbx
0x180034e48  jz      short loc_180034E51
0x180034e4a  lock inc dword ptr [rbx+118h]
0x180034e51  lea     rcx, [rbx+8]
0x180034e55  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180034e5a  mov     [rbx+110h], edi
0x180034e60  lea     rcx, [rbp+57h+arg_8]
0x180034e64  call    ??1?$test_data_control@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(void)
0x180034e69  mov     rbx, [rbp+57h+var_18]
0x180034e6d  mov     [rbp+57h+arg_8], rbx
0x180034e71  test    rbx, rbx
0x180034e74  jz      short loc_180034E7D
0x180034e76  lock inc dword ptr [rbx+118h]
0x180034e7d  lea     rcx, [rbx+8]
0x180034e81  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180034e86  lea     rcx, aCrenewablechar_1; "CRenewableChargingTipTestReason::regist"...
0x180034e8d  call    ?reason_string@details@tip2@@YAPEBDPEBD@Z; tip2::details::reason_string(char const *)
0x180034e92  cmp     byte ptr [rbx+0A8h], 0
0x180034e99  jnz     loc_180034DDB
0x180034e9f  mov     ecx, 3
0x180034ea4  mov     [rbx+0A8h], cl
0x180034eaa  mov     [rbx+0AAh], cx
0x180034eb1  jmp     loc_180034DD4
0x180034eb6  movzx   eax, byte ptr [rbx+110h]
0x180034ebd  mov     dword ptr [rbp+57h+arg_8], eax
0x180034ec0  lea     rax, [rbp+57h+arg_8]
0x180034ec4  mov     [rbp+57h+arg_10], rax
0x180034ec8  lea     rdx, [rbp+57h+arg_10]
0x180034ecc  lea     rcx, ?g_CRenewableChargingStateSingleton@BatterySaverOneCoreDataModel@SystemSettings@@3VCRenewableChargingStateSingleton@12@A; SystemSettings::BatterySaverOneCoreDataModel::CRenewableChargingStateSingleton SystemSettings::BatterySaverOneCoreDataModel::g_CRenewableChargingStateSingleton
0x180034ed3  call    ??$_Notify@V_lambda_e398eed577395da8d81f0cd0fd7d36b5_@@@?$CSingletonHelper@H@DataModel@SystemSettings@@AEAAXAEBV_lambda_e398eed577395da8d81f0cd0fd7d36b5_@@@Z; SystemSettings::DataModel::CSingletonHelper<int>::_Notify<_lambda_e398eed577395da8d81f0cd0fd7d36b5_>(_lambda_e398eed577395da8d81f0cd0fd7d36b5_ const &)
0x180034ed8  mov     rbx, [rbp+57h+var_18]
0x180034edc  mov     [rbp+57h+arg_8], rbx
0x180034ee0  test    rbx, rbx
0x180034ee3  jz      short loc_180034EEC
0x180034ee5  lock inc dword ptr [rbx+118h]
0x180034eec  lea     rcx, [rbx+8]
0x180034ef0  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180034ef5  mov     [rbx+110h], edi
0x180034efb  lea     rcx, [rbp+57h+arg_8]
0x180034eff  call    ??1?$test_data_control@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(void)
0x180034f04  mov     rbx, [rbp+57h+var_18]
0x180034f08  mov     [rbp+57h+arg_8], rbx
0x180034f0c  test    rbx, rbx
0x180034f0f  jz      short loc_180034F18
0x180034f11  lock inc dword ptr [rbx+118h]
0x180034f18  lea     rcx, [rbx+8]
0x180034f1c  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x180034f21  lea     rcx, [rbx+8]
0x180034f25  call    ?complete@?$shared_data@$00$0A@$0A@@details@tip2@@QEAAXXZ; tip2::details::shared_data<1,0,0>::complete(void)
0x180034f2a  lea     rcx, [rbp+57h+arg_8]
0x180034f2e  call    ??1?$test_data_control@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_data_control<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(void)
0x180034f33  nop
0x180034f34  lea     rcx, [rbp+57h+var_70]
0x180034f38  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180034f3d  nop
0x180034f3e  lea     rcx, [rbp+57h+var_50]
0x180034f42  call    ??1?$test_watcher@V?$merged_data@U_tip_CleanEnergyChargingToggleTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>::~test_watcher<tip2::details::merged_data<_tip_CleanEnergyChargingToggleTest,_tip_CleanEnergyChargingToggleTest>>(void)
0x180034f47  add     rsp, 90h
0x180034f4e  pop     rdi
0x180034f4f  pop     rbx
0x180034f50  pop     rbp
0x180034f51  retn
```
