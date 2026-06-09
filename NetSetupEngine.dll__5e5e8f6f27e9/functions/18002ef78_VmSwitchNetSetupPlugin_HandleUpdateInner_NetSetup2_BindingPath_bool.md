# VmSwitchNetSetupPlugin::HandleUpdateInner(NetSetup2::BindingPath &,bool)

- ea: `0x18002ef78`
- end: `0x18002f90b`
- name: `?HandleUpdateInner@VmSwitchNetSetupPlugin@@AEAA_NAEAVBindingPath@NetSetup2@@_N@Z`
- size: `2451`
- prototype: `bool(VmSwitchNetSetupPlugin *__hidden this, struct NetSetup2::BindingPath *, bool)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18002ede0`

## callees

- `0x180005c94`
- `0x18000a430`
- `0x18000d474`
- `0x18000fd70`
- `0x180015f50`
- `0x180016a20`
- `0x180016a7c`
- `0x180017320`
- `0x1800179a8`
- `0x180029d20`
- `0x180029ff4`
- `0x18002ef78`
- `0x18002f914`
- `0x18002f93c`
- `0x180030fac`
- `0x18004291c`
- `0x1800440ac`
- `0x180044d04`
- `0x18005b1e4`
- `0x18005b424`
- `0x18005c848`
- `0x18005cec0`
- `0x180064704`
- `0x18007b86c`
- `0x18007e824`
- `0x18007eb6c`
- `0x18007ec80`
- `0x18007ef50`
- `0x18007f254`
- `0x1800810a2`
- `0x1800810d0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18002f210`
- `msvcrt!_wcsicmp` at `0x18002f236`
- `msvcrt!_wcsicmp` at `0x18002f521`
- `msvcrt!_wcsicmp` at `0x18002f5c6`
- `msvcrt!_wcsicmp` at `0x18002f61e`
- `msvcrt!_wcsicmp` at `0x18002f6dc`
- `msvcrt!_wcsicmp` at `0x18002f7c3`
- `msvcrt!_wcsicmp` at `0x18002f81f`
- `msvcrt!_wcsicmp` at `0x18002f847`
- `msvcrt!_wcsicmp` at `0x18002f210`
- `msvcrt!_wcsicmp` at `0x18002f236`
- `msvcrt!_wcsicmp` at `0x18002f521`
- `msvcrt!_wcsicmp` at `0x18002f5c6`
- `msvcrt!_wcsicmp` at `0x18002f61e`
- `msvcrt!_wcsicmp` at `0x18002f6dc`
- `msvcrt!_wcsicmp` at `0x18002f7c3`
- `msvcrt!_wcsicmp` at `0x18002f81f`
- `msvcrt!_wcsicmp` at `0x18002f847`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
char __fastcall VmSwitchNetSetupPlugin::HandleUpdateInner(
        VmSwitchNetSetupPlugin *this,
        struct NetSetup2::BindingPath *a2,
        char a3)
{
  const struct _NETSETUP_OBJECT_ID *v5; // rdi
  char *v6; // r12
  __int64 v7; // r8
  bool Boolean; // r15
  __int64 v9; // r13
  int v10; // edx
  int v11; // r8d
  wchar_t **v12; // r9
  void *v13; // rax
  __int64 v14; // rdx
  const wchar_t *v15; // rcx
  int v16; // ebx
  const wchar_t *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rdx
  NetSetup2::Property *lpVtbl; // rcx
  bool v22; // bl
  bool IsOnline; // bl
  const wchar_t *v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  const wchar_t *v27; // rcx
  __int64 v28; // rdx
  const wchar_t *v29; // rcx
  __int64 v30; // rdx
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  const wchar_t *v33; // rcx
  const wchar_t *v34; // rcx
  const wchar_t *v35; // rcx
  const wchar_t *v36; // rcx
  bool v37[8]; // [rsp+38h] [rbp-D0h] BYREF
  NetSetup2::ActiveObject *v38; // [rsp+40h] [rbp-C8h]
  void *Block; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B8h]
  __int64 v41; // [rsp+60h] [rbp-A8h]
  bool v42[3648]; // [rsp+68h] [rbp-A0h] BYREF
  bool v43[8]; // [rsp+EA8h] [rbp+DA0h] BYREF
  wchar_t *v44[2]; // [rsp+EB0h] [rbp+DA8h] BYREF
  __int64 v45; // [rsp+EC0h] [rbp+DB8h]
  unsigned __int64 v46; // [rsp+EC8h] [rbp+DC0h]
  wchar_t *String1[2]; // [rsp+ED0h] [rbp+DC8h] BYREF
  __int64 v48; // [rsp+EE0h] [rbp+DD8h]
  unsigned __int64 v49; // [rsp+EE8h] [rbp+DE0h]
  GUID v50; // [rsp+EF0h] [rbp+DE8h] BYREF
  int v51; // [rsp+F04h] [rbp+DFCh]
  _BYTE v52[24]; // [rsp+F08h] [rbp+E00h] BYREF
  GUID v53; // [rsp+F20h] [rbp+E18h] BYREF
  int v54; // [rsp+F30h] [rbp+E28h]
  __int128 v55; // [rsp+F34h] [rbp+E2Ch] BYREF
  void **v56; // [rsp+F50h] [rbp+E48h] BYREF
  _BYTE v57[32]; // [rsp+F58h] [rbp+E50h] BYREF

  v41 = -2;
  v38 = a2;
  NetSetup2::ActiveObject::GetProperty((void ***)a2, &v50, (__int128 *)&NETSETUPPKEY_Binding_Path, 0);
  NetSetup2::Property::GetObjectIdArray(&v50, &Block);
  std::vector<_NETSETUPPROPKEY>::_Tidy(v52);
  v5 = (const struct _NETSETUP_OBJECT_ID *)Block;
  v6 = (char *)Block + 4;
  NetSetup2::details::GetObjectWithFilter<NetSetup2::NetworkInterface>(&v56, *(_QWORD *)this, v7, (char *)Block + 4);
  NetSetup2::ActiveObject::GetProperty(&v56, &v50, (__int128 *)&NETSETUPPKEY_Interface_IsLightweight, 0);
  Boolean = NetSetup2::Property::GetBoolean((NetSetup2::Property *)&v50);
  std::vector<_NETSETUPPROPKEY>::_Tidy(v52);
  v9 = v40;
  NetSetup2::details::GetObjectWithFilter<NetSetup2::ActiveObject>(
    &v50,
    *(_QWORD *)this,
    *(unsigned int *)(v40 - 20),
    v40 - 16);
  NetSetup2::ActiveObject::GetProperty((void ***)&v50, &v53, &NETSETUPPKEY_Driver_Identifier, 0);
  if ( (_DWORD)v55 )
  {
    NetSetup2::Property::GetString(&v53, v44);
  }
  else
  {
    v46 = 7;
    v45 = 0;
    LOWORD(v44[0]) = 0;
  }
  std::vector<_NETSETUPPROPKEY>::_Tidy((char *)&v55 + 4);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v50.Data4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v12 = v44;
    if ( v46 >= 8 )
      LODWORD(v12) = v44[0];
    WPP_SF_S_guid_c(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, v11, (_DWORD)v12, (__int64)v6, a3);
  }
  NetSetup2::ActiveObject::GetProperty(&v56, &v50, (__int128 *)NETSETUPPKEY_Interface_PnpMatchingHardwareId, 0);
  if ( v51 )
  {
    NetSetup2::Property::GetString(&v50, String1);
  }
  else
  {
    v49 = 7;
    v48 = 0;
    LOWORD(String1[0]) = 0;
  }
  std::vector<_NETSETUPPROPKEY>::_Tidy(v52);
  if ( !v48 && !Boolean )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids, v6);
    v13 = (void *)NetSetup2::NetworkInterface::getordefault_DownlevelPnpMatchingHardwareId(&v56, &v53);
    std::wstring::operator=(String1, v13);
    LOBYTE(v14) = 1;
    std::wstring::_Tidy(&v53, v14, 0);
  }
  v15 = (const wchar_t *)String1;
  if ( v49 >= 8 )
    v15 = String1[0];
  v16 = _wcsicmp(v15, L"vms_mp");
  v17 = (const wchar_t *)v44;
  if ( v46 >= 8 )
    v17 = v44[0];
  if ( _wcsicmp(v17, L"vms_pp") )
  {
    v24 = (const wchar_t *)String1;
    if ( v49 >= 8 )
      v24 = String1[0];
    if ( _wcsicmp(v24, L"vms_vsmp") || !a3 )
    {
      v35 = (const wchar_t *)v44;
      if ( v46 >= 8 )
        v35 = v44[0];
      if ( _wcsicmp(v35, L"vms_vsp") )
      {
        v36 = (const wchar_t *)v44;
        if ( v46 >= 8 )
          v36 = v44[0];
        if ( _wcsicmp(v36, L"vms_vsf") )
          goto LABEL_29;
      }
      if ( a3 )
        goto LABEL_29;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
      if ( v49 >= 8 )
        operator delete(String1[0]);
      v49 = 7;
      v48 = 0;
      LOWORD(String1[0]) = 0;
      if ( v46 >= 8 )
        operator delete(v44[0]);
      v45 = 0;
      LOWORD(v44[0]) = 0;
      goto LABEL_111;
    }
    if ( *(_DWORD *)(v9 - 20) != 3 )
    {
      v34 = (const wchar_t *)v44;
      if ( v46 >= 8 )
        v34 = v44[0];
      if ( !_wcsicmp(v34, L"vms_vsp") )
        goto LABEL_29;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        goto LABEL_87;
      v26 = 22;
LABEL_95:
      WPP_SF_(v25[2], v26, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
      goto LABEL_87;
    }
    if ( !VmSwitchNetSetupPlugin::IsExtensionFilterClassValid(this, (const struct _NETSETUP_OBJECT_ID *)(v9 - 20)) )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        goto LABEL_87;
      v26 = 17;
      goto LABEL_95;
    }
    NetSetup2::details::TransactionBase::GetFilterDriverById(*(_QWORD *)this, &v50, v9 - 16);
    NetSetup2::FilterDriver::get_Class(&v50, &v53);
    v27 = (const wchar_t *)v44;
    if ( v46 >= 8 )
      v27 = v44[0];
    if ( !_wcsicmp(v27, L"vms_vsf") )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
LABEL_69:
      LOBYTE(v28) = 1;
      std::wstring::_Tidy(&v53, v28, 0);
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v50.Data4);
      a3 = 1;
      goto LABEL_29;
    }
    v29 = (const wchar_t *)&v53;
    if ( *(_QWORD *)((char *)&v55 + 4) >= 8u )
      v29 = *(const wchar_t **)&v53.Data1;
    if ( !_wcsicmp(v29, L"ms_switch_capture")
      && NetSetup2::FilterDriver::get_IsMonitoring((NetSetup2::FilterDriver *)&v50) )
    {
      goto LABEL_69;
    }
    v43[0] = 0;
    v37[0] = 0;
    VmSwitchNetSetupPlugin::GetExtensionEnableDisableProperty(this, v5, (const struct _GUID *)(v9 - 16), v43, v37);
    if ( v43[0] )
    {
      v33 = (const wchar_t *)v44;
      if ( v46 >= 8 )
        v33 = v44[0];
      if ( _wcsicmp(v33, L"MS_WfpLwf_vSwitch") )
        goto LABEL_88;
      memset_0(v42, 0, 0xE38u);
      if ( !VmSwitchNetSetupPlugin::TryGetSwitchInfoByMiniportId(this, v5, (struct _VMS_ENUM_SWITCH_INFO_OUT *)v42) )
      {
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
          goto LABEL_86;
        v32 = 20;
        goto LABEL_85;
      }
      if ( !v42[3620] )
      {
LABEL_88:
        LOBYTE(v30) = 1;
        std::wstring::_Tidy(&v53, v30, 0);
LABEL_49:
        std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v50.Data4);
        goto LABEL_29;
      }
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        goto LABEL_86;
      v32 = 21;
    }
    else
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        goto LABEL_86;
      v32 = 19;
    }
LABEL_85:
    WPP_SF_(v31[2], v32, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
LABEL_86:
    LOBYTE(v30) = 1;
    std::wstring::_Tidy(&v53, v30, 0);
    std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v50.Data4);
LABEL_87:
    a3 = 0;
    goto LABEL_29;
  }
  if ( !a3 )
  {
    lpVtbl = (NetSetup2::Property *)NetSetup2::ActiveObject::GetProperty(v38, (const struct _NETSETUPPROPKEY *)&v50).lpVtbl;
    v22 = NetSetup2::Property::GetBoolean(lpVtbl);
    std::vector<_NETSETUPPROPKEY>::_Tidy(v52);
    if ( v22 )
      goto LABEL_29;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
    VmSwitchNetSetupPlugin::RemovePtNicMappingIfExists(this, v5);
    VmSwitchNetSetupPlugin::EnableBindings(this, v5, 1);
    if ( Boolean )
      goto LABEL_29;
    *(_QWORD *)&v53.Data1 = *(_QWORD *)this;
    *(_QWORD *)v53.Data4 = 0;
    v54 = 9;
    v55 = 0;
    IsOnline = NetSetup2::TransactionObject::get_IsOnline((NetSetup2::TransactionObject *)&v53);
    std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v53.Data4);
    if ( !IsOnline )
      goto LABEL_29;
    NetSetup2::details::TransactionBase::GetNetworkInterfaceById(*(_QWORD *)this, &v50, v6);
    v43[0] = 1;
    NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(&v50, NETSETUPPKEY_Interface_DeviceNeedsRestart, v43);
    goto LABEL_49;
  }
  if ( !v16 || Boolean )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
  }
  else
  {
    NetSetup2::ActiveObject::GetProperty(&v56, &v50, (__int128 *)&qword_1800D4480, 0);
    if ( v51 == 17 && NetSetup2::Property::GetBoolean((NetSetup2::Property *)&v50) )
    {
      VmSwitchNetSetupPlugin::EnableBindings(this, v5, 0);
      std::vector<_NETSETUPPROPKEY>::_Tidy(v52);
LABEL_29:
      LOBYTE(v18) = 1;
      std::wstring::_Tidy(String1, v18, 0);
      LOBYTE(v19) = 1;
      std::wstring::_Tidy(v44, v19, 0);
      std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v57);
      std::vector<NetSetupLoadedPlugin const *>::~vector<NetSetupLoadedPlugin const *>((__int64)&Block);
      return a3;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids);
    std::vector<_NETSETUPPROPKEY>::_Tidy(v52);
  }
  if ( v49 >= 8 )
    operator delete(String1[0]);
  v49 = 7;
  v48 = 0;
  LOWORD(String1[0]) = 0;
  if ( v46 >= 8 )
    operator delete(v44[0]);
  v45 = 0;
  LOWORD(v44[0]) = 0;
LABEL_111:
  v46 = 7;
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(v57);
  if ( v5 )
    operator delete(v5);
  return 0;
}

```

## disassembly

```asm
0x18002ef78  mov     rax, rsp
0x18002ef7b  push    rbp
0x18002ef7c  push    rsi
0x18002ef7d  push    rdi
0x18002ef7e  push    r12
0x18002ef80  push    r13
0x18002ef82  push    r14
0x18002ef84  push    r15
0x18002ef86  lea     rbp, [rax-0EB8h]
0x18002ef8d  sub     rsp, 0F80h
0x18002ef94  mov     [rsp+0FB0h+var_F58], 0FFFFFFFFFFFFFFFEh
0x18002ef9d  mov     [rax+18h], rbx
0x18002efa1  mov     rax, cs:__security_cookie
0x18002efa8  xor     rax, rsp
0x18002efab  mov     [rbp+0EB0h+var_40], rax
0x18002efb2  mov     sil, r8b
0x18002efb5  mov     rax, rdx
0x18002efb8  mov     [rsp+0FB0h+var_F78], rdx
0x18002efbd  mov     r14, rcx
0x18002efc0  xor     ebx, ebx
0x18002efc2  xor     r9d, r9d
0x18002efc5  lea     r8, NETSETUPPKEY_Binding_Path; unsigned int
0x18002efcc  lea     rdx, [rbp+0EB0h+var_C8]; struct _NETSETUPPROPKEY *
0x18002efd3  mov     rcx, rax; this
0x18002efd6  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18002efdb  nop
0x18002efdc  lea     rdx, [rsp+0FB0h+Block]
0x18002efe1  lea     rcx, [rbp+0EB0h+var_C8]
0x18002efe8  call    ?GetObjectIdArray@Property@NetSetup2@@QEBA?AV?$vector@U_NETSETUP_OBJECT_ID@@V?$allocator@U_NETSETUP_OBJECT_ID@@@std@@@std@@XZ; NetSetup2::Property::GetObjectIdArray(void)
0x18002efed  nop
0x18002efee  lea     rcx, [rbp+0EB0h+var_B0]
0x18002eff5  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002effa  nop
0x18002effb  mov     rdi, [rsp+0FB0h+Block]
0x18002f000  lea     r12, [rdi+4]
0x18002f004  mov     r9, r12
0x18002f007  mov     rdx, [r14]
0x18002f00a  lea     rcx, [rbp+0EB0h+var_68]
0x18002f011  call    ??$GetObjectWithFilter@VNetworkInterface@NetSetup2@@@details@NetSetup2@@YA?AVNetworkInterface@1@AEBVTransactionBase@01@W4_NETSETUP_OBJECT_TYPE@@PEBU_GUID@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@@Z; NetSetup2::details::GetObjectWithFilter<NetSetup2::NetworkInterface>(NetSetup2::details::TransactionBase const &,_NETSETUP_OBJECT_TYPE,_GUID const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *)
0x18002f016  nop
0x18002f017  xor     r9d, r9d
0x18002f01a  lea     r8, NETSETUPPKEY_Interface_IsLightweight; unsigned int
0x18002f021  lea     rdx, [rbp+0EB0h+var_C8]; struct _NETSETUPPROPKEY *
0x18002f028  lea     rcx, [rbp+0EB0h+var_68]; this
0x18002f02f  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18002f034  nop
0x18002f035  lea     rcx, [rbp+0EB0h+var_C8]; this
0x18002f03c  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x18002f041  mov     r15b, al
0x18002f044  lea     rcx, [rbp+0EB0h+var_B0]
0x18002f04b  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002f050  mov     r13, [rsp+0FB0h+var_F68]
0x18002f055  lea     r9, [r13-10h]
0x18002f059  mov     r8d, [r13-14h]
0x18002f05d  mov     rdx, [r14]
0x18002f060  lea     rcx, [rbp+0EB0h+var_C8]
0x18002f067  call    ??$GetObjectWithFilter@VActiveObject@NetSetup2@@@details@NetSetup2@@YA?AVActiveObject@1@AEBVTransactionBase@01@W4_NETSETUP_OBJECT_TYPE@@PEBU_GUID@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@@Z; NetSetup2::details::GetObjectWithFilter<NetSetup2::ActiveObject>(NetSetup2::details::TransactionBase const &,_NETSETUP_OBJECT_TYPE,_GUID const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *)
0x18002f06c  nop
0x18002f06d  xor     r9d, r9d
0x18002f070  lea     r8, NETSETUPPKEY_Driver_Identifier; unsigned int
0x18002f077  lea     rdx, [rbp+0EB0h+var_98]; struct _NETSETUPPROPKEY *
0x18002f07e  lea     rcx, [rbp+0EB0h+var_C8]; this
0x18002f085  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18002f08a  nop
0x18002f08b  cmp     dword ptr [rbp+0EB0h+var_84], ebx
0x18002f091  jnz     short loc_18002F0AE
0x18002f093  mov     [rbp+0EB0h+var_F0], 7
0x18002f09e  mov     [rbp+0EB0h+var_F8], rbx
0x18002f0a5  mov     word ptr [rbp+0EB0h+var_108], bx
0x18002f0ac  jmp     short loc_18002F0C2
0x18002f0ae  lea     rdx, [rbp+0EB0h+var_108]
0x18002f0b5  lea     rcx, [rbp+0EB0h+var_98]
0x18002f0bc  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18002f0c1  nop
0x18002f0c2  lea     rcx, [rbp+0EB0h+var_84+4]
0x18002f0c9  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002f0ce  nop
0x18002f0cf  lea     rcx, [rbp+0EB0h+var_C0]
0x18002f0d6  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18002f0db  lea     rax, WPP_GLOBAL_Control
0x18002f0e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0e9  cmp     rcx, rax
0x18002f0ec  jz      short loc_18002F11E
0x18002f0ee  cmp     byte ptr [rcx+19h], 4
0x18002f0f2  jb      short loc_18002F11E
0x18002f0f4  lea     r9, [rbp+0EB0h+var_108]
0x18002f0fb  cmp     [rbp+0EB0h+var_F0], 8
0x18002f103  cmovnb  r9, [rbp+0EB0h+var_108]
0x18002f10b  mov     [rsp+0FB0h+var_F88], sil
0x18002f110  mov     [rsp+0FB0h+var_F90], r12
0x18002f115  mov     rcx, [rcx+10h]
0x18002f119  call    WPP_SF_S_guid_c
0x18002f11e  xor     r9d, r9d
0x18002f121  lea     r8, NETSETUPPKEY_Interface_PnpMatchingHardwareId; unsigned int
0x18002f128  lea     rdx, [rbp+0EB0h+var_C8]; struct _NETSETUPPROPKEY *
0x18002f12f  lea     rcx, [rbp+0EB0h+var_68]; this
0x18002f136  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18002f13b  nop
0x18002f13c  cmp     [rbp+0EB0h+var_B4], ebx
0x18002f142  jnz     short loc_18002F15F
0x18002f144  mov     [rbp+0EB0h+var_D0], 7
0x18002f14f  mov     [rbp+0EB0h+var_D8], rbx
0x18002f156  mov     word ptr [rbp+0EB0h+String1], bx
0x18002f15d  jmp     short loc_18002F173
0x18002f15f  lea     rdx, [rbp+0EB0h+String1]
0x18002f166  lea     rcx, [rbp+0EB0h+var_C8]
0x18002f16d  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x18002f172  nop
0x18002f173  lea     rcx, [rbp+0EB0h+var_B0]
0x18002f17a  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002f17f  nop
0x18002f180  cmp     [rbp+0EB0h+var_D8], rbx
0x18002f187  jnz     short loc_18002F1F2
0x18002f189  test    r15b, r15b
0x18002f18c  jnz     short loc_18002F1F2
0x18002f18e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f195  lea     rax, WPP_GLOBAL_Control
0x18002f19c  cmp     rcx, rax
0x18002f19f  jz      short loc_18002F1BF
0x18002f1a1  cmp     byte ptr [rcx+19h], 4
0x18002f1a5  jb      short loc_18002F1BF
0x18002f1a7  mov     edx, 0Dh
0x18002f1ac  mov     r9, r12
0x18002f1af  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18002f1b6  mov     rcx, [rcx+10h]
0x18002f1ba  call    WPP_SF__guid_
0x18002f1bf  lea     rdx, [rbp+0EB0h+var_98]
0x18002f1c6  lea     rcx, [rbp+0EB0h+var_68]
0x18002f1cd  call    ?getordefault_DownlevelPnpMatchingHardwareId@NetworkInterface@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::NetworkInterface::getordefault_DownlevelPnpMatchingHardwareId(void)
0x18002f1d2  mov     rdx, rax; Src
0x18002f1d5  lea     rcx, [rbp+0EB0h+String1]; void *
0x18002f1dc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002f1e1  xor     r8d, r8d
0x18002f1e4  mov     dl, 1
0x18002f1e6  lea     rcx, [rbp+0EB0h+var_98]
0x18002f1ed  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002f1f2  lea     rcx, [rbp+0EB0h+String1]
0x18002f1f9  cmp     [rbp+0EB0h+var_D0], 8
0x18002f201  cmovnb  rcx, [rbp+0EB0h+String1]; String1
0x18002f209  lea     rdx, aVmsMp_0; "vms_mp"
0x18002f210  call    cs:__imp__wcsicmp
0x18002f216  mov     ebx, eax
0x18002f218  lea     rcx, [rbp+0EB0h+var_108]
0x18002f21f  cmp     [rbp+0EB0h+var_F0], 8
0x18002f227  cmovnb  rcx, [rbp+0EB0h+var_108]; String1
0x18002f22f  lea     rdx, aVmsPp_0; "vms_pp"
0x18002f236  call    cs:__imp__wcsicmp
0x18002f23c  test    eax, eax
0x18002f23e  jnz     loc_18002F503
0x18002f244  xor     r13d, r13d
0x18002f247  test    sil, sil
0x18002f24a  jz      loc_18002F3EE
0x18002f250  test    ebx, ebx
0x18002f252  jz      loc_18002F3BB
0x18002f258  test    r15b, r15b
0x18002f25b  jnz     loc_18002F3BB
0x18002f261  xor     r9d, r9d
0x18002f264  lea     r8, qword_1800D4480; unsigned int
0x18002f26b  lea     rdx, [rbp+0EB0h+var_C8]; struct _NETSETUPPROPKEY *
0x18002f272  lea     rcx, [rbp+0EB0h+var_68]; this
0x18002f279  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x18002f27e  nop
0x18002f27f  cmp     [rbp+0EB0h+var_B4], 11h
0x18002f286  jnz     loc_18002F324
0x18002f28c  lea     rcx, [rbp+0EB0h+var_C8]; this
0x18002f293  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x18002f298  test    al, al
0x18002f29a  jz      loc_18002F324
0x18002f2a0  xor     r8d, r8d; bool
0x18002f2a3  mov     rdx, rdi; struct _NETSETUP_OBJECT_ID *
0x18002f2a6  mov     rcx, r14; this
0x18002f2a9  call    ?EnableBindings@VmSwitchNetSetupPlugin@@AEAAXAEBU_NETSETUP_OBJECT_ID@@_N@Z; VmSwitchNetSetupPlugin::EnableBindings(_NETSETUP_OBJECT_ID const &,bool)
0x18002f2ae  nop
0x18002f2af  lea     rcx, [rbp+0EB0h+var_B0]
0x18002f2b6  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002f2bb  nop
0x18002f2bc  xor     r8d, r8d
0x18002f2bf  mov     dl, 1
0x18002f2c1  lea     rcx, [rbp+0EB0h+String1]
0x18002f2c8  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002f2cd  nop
0x18002f2ce  xor     r8d, r8d
0x18002f2d1  mov     dl, 1
0x18002f2d3  lea     rcx, [rbp+0EB0h+var_108]
0x18002f2da  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002f2df  nop
0x18002f2e0  lea     rcx, [rbp+0EB0h+var_60]
0x18002f2e7  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18002f2ec  nop
0x18002f2ed  lea     rcx, [rsp+0FB0h+Block]
0x18002f2f2  call    ??1?$vector@PEBVNetSetupLoadedPlugin@@V?$allocator@PEBVNetSetupLoadedPlugin@@@std@@@std@@QEAA@XZ; std::vector<NetSetupLoadedPlugin const *>::~vector<NetSetupLoadedPlugin const *>(void)
0x18002f2f7  mov     al, sil
0x18002f2fa  mov     rcx, [rbp+0EB0h+var_40]
0x18002f301  xor     rcx, rsp; StackCookie
0x18002f304  call    __security_check_cookie
0x18002f309  mov     rbx, [rsp+0FB0h+arg_10]
0x18002f311  add     rsp, 0F80h
0x18002f318  pop     r15
0x18002f31a  pop     r14
0x18002f31c  pop     r13
0x18002f31e  pop     r12
0x18002f320  pop     rdi
0x18002f321  pop     rsi
0x18002f322  pop     rbp
0x18002f323  retn
0x18002f324  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f32b  lea     rax, WPP_GLOBAL_Control
0x18002f332  cmp     rcx, rax
0x18002f335  jz      short loc_18002F353
0x18002f337  cmp     byte ptr [rcx+19h], 3
0x18002f33b  jb      short loc_18002F353
0x18002f33d  mov     edx, 0Fh
0x18002f342  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18002f349  mov     rcx, [rcx+10h]
0x18002f34d  call    WPP_SF_
0x18002f352  nop
0x18002f353  lea     rcx, [rbp+0EB0h+var_B0]
0x18002f35a  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002f35f  nop
0x18002f360  cmp     [rbp+0EB0h+var_D0], 8
0x18002f368  jb      short loc_18002F376
0x18002f36a  mov     rcx, [rbp+0EB0h+String1]; Block
0x18002f371  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f376  mov     ebx, 7
0x18002f37b  mov     [rbp+0EB0h+var_D0], rbx
0x18002f382  mov     [rbp+0EB0h+var_D8], r13
0x18002f389  mov     word ptr [rbp+0EB0h+String1], r13w
0x18002f391  cmp     [rbp+0EB0h+var_F0], 8
0x18002f399  jb      short loc_18002F3A7
0x18002f39b  mov     rcx, [rbp+0EB0h+var_108]; Block
0x18002f3a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002f3a7  mov     [rbp+0EB0h+var_F8], r13
0x18002f3ae  mov     word ptr [rbp+0EB0h+var_108], r13w
0x18002f3b6  jmp     loc_18002F8E3
0x18002f3bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f3c2  lea     rax, WPP_GLOBAL_Control
0x18002f3c9  cmp     rcx, rax
0x18002f3cc  jz      short loc_18002F360
0x18002f3ce  cmp     byte ptr [rcx+19h], 4
0x18002f3d2  jb      short loc_18002F360
0x18002f3d4  mov     edx, 0Eh
0x18002f3d9  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18002f3e0  mov     rcx, [rcx+10h]
0x18002f3e4  call    WPP_SF_
0x18002f3e9  jmp     loc_18002F360
0x18002f3ee  lea     r8, NETSETUPPKEY_Binding_VmswitchDisabledNewBindpath
0x18002f3f5  lea     rdx, [rbp+0EB0h+var_C8]; struct _NETSETUPPROPKEY *
0x18002f3fc  mov     rcx, [rsp+0FB0h+var_F78]; this
0x18002f401  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &)
0x18002f406  nop
0x18002f407  mov     rcx, rax; this
0x18002f40a  call    ?GetBoolean@Property@NetSetup2@@QEBA_NXZ; NetSetup2::Property::GetBoolean(void)
0x18002f40f  mov     bl, al
0x18002f411  lea     rcx, [rbp+0EB0h+var_B0]
0x18002f418  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002f41d  test    bl, bl
0x18002f41f  jnz     loc_18002F2BC
0x18002f425  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f42c  lea     rax, WPP_GLOBAL_Control
0x18002f433  cmp     rcx, rax
0x18002f436  jz      short loc_18002F453
0x18002f438  cmp     byte ptr [rcx+19h], 4
0x18002f43c  jb      short loc_18002F453
0x18002f43e  mov     edx, 10h
0x18002f443  lea     r8, WPP_feca66596a5b3ea6168f85467ce9bec4_Traceguids
0x18002f44a  mov     rcx, [rcx+10h]
0x18002f44e  call    WPP_SF_
0x18002f453  mov     rdx, rdi; struct _NETSETUP_OBJECT_ID *
0x18002f456  mov     rcx, r14; this
0x18002f459  call    ?RemovePtNicMappingIfExists@VmSwitchNetSetupPlugin@@AEAAXAEBU_NETSETUP_OBJECT_ID@@@Z; VmSwitchNetSetupPlugin::RemovePtNicMappingIfExists(_NETSETUP_OBJECT_ID const &)
0x18002f45e  mov     r8b, 1; bool
0x18002f461  mov     rdx, rdi; struct _NETSETUP_OBJECT_ID *
0x18002f464  mov     rcx, r14; this
0x18002f467  call    ?EnableBindings@VmSwitchNetSetupPlugin@@AEAAXAEBU_NETSETUP_OBJECT_ID@@_N@Z; VmSwitchNetSetupPlugin::EnableBindings(_NETSETUP_OBJECT_ID const &,bool)
0x18002f46c  test    r15b, r15b
0x18002f46f  jnz     loc_18002F2BC
0x18002f475  xorps   xmm0, xmm0
0x18002f478  mov     rax, [r14]
0x18002f47b  mov     [rbp+0EB0h+var_98], rax
0x18002f482  mov     [rbp+0EB0h+var_90], r13
0x18002f489  mov     [rbp+0EB0h+var_88], 9
0x18002f493  movdqu  [rbp+0EB0h+var_84], xmm0
0x18002f49b  lea     rcx, [rbp+0EB0h+var_98]; this
0x18002f4a2  call    ?get_IsOnline@TransactionObject@NetSetup2@@QEBA_NXZ; NetSetup2::TransactionObject::get_IsOnline(void)
0x18002f4a7  mov     bl, al
0x18002f4a9  lea     rcx, [rbp+0EB0h+var_90]
0x18002f4b0  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x18002f4b5  test    bl, bl
0x18002f4b7  jz      loc_18002F2BC
0x18002f4bd  mov     r8, r12
0x18002f4c0  lea     rdx, [rbp+0EB0h+var_C8]
0x18002f4c7  mov     rcx, [r14]
0x18002f4ca  call    ?GetNetworkInterfaceById@TransactionBase@details@NetSetup2@@QEAA?AVNetworkInterface@3@AEBU_GUID@@@Z; NetSetup2::details::TransactionBase::GetNetworkInterfaceById(_GUID const &)
0x18002f4cf  nop
0x18002f4d0  mov     [rbp+0EB0h+var_110], 1
0x18002f4d7  lea     r8, [rbp+0EB0h+var_110]
0x18002f4de  lea     rdx, NETSETUPPKEY_Interface_DeviceNeedsRestart
0x18002f4e5  lea     rcx, [rbp+0EB0h+var_C8]
0x18002f4ec  call    ??$SetPropertyToValue@$0BB@_N@ActiveObject@NetSetup2@@IEAAXAEBU_NETSETUPPROPKEY@@AEB_N@Z; NetSetup2::ActiveObject::SetPropertyToValue<17,bool>(_NETSETUPPROPKEY const &,bool const &)
0x18002f4f1  nop
  ... truncated ...
```
