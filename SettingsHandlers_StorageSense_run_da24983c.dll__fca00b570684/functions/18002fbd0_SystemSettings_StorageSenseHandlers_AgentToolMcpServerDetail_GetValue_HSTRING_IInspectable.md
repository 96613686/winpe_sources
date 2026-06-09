# SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::GetValue(HSTRING__ *,IInspectable * *)

- ea: `0x18002fbd0`
- end: `0x1800303fd`
- name: `?GetValue@AgentToolMcpServerDetail@StorageSenseHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `2093`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x180018b4c`
- `0x180019eb4`
- `0x18001f688`
- `0x180023df8`
- `0x1800292a8`
- `0x18002ace4`
- `0x18002adf4`
- `0x18002bad4`
- `0x18002d094`
- `0x18002f9b0`
- `0x18002fbd0`
- `0x1800305b4`
- `0x180030f04`
- `0x180035c0c`
- `0x1800e3010`

## string_xrefs

- `0x1800300a4`: `SystemSettings_StorageSense_HiddenAppAdvancedPageLink`
- `0x180030084`: `SystemSettings_StorageSense_HiddenSystemComponentsAdvancedPageLink`
- `0x18002fd14`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\agenttoollist.cpp`
- `0x18002fd7a`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\agenttoollist.cpp`
- `0x1800301f1`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\agenttoollist.cpp`
- `0x18003029e`: `onecoreuap\shell\coresettinghandlers\storagesense\lib\agenttoollist.cpp`
- `0x18002fce1`: `SystemSettings_StorageSense_AgentTools_CanAlwaysUseFormat`
- `0x18002fca7`: `SystemSettings_StorageSense_AgentTools_CannotAccessFormat`
- `0x18002fc6a`: `SystemSettings_StorageSense_AgentTools_WillAskForPermissionFormat`
- `0x18003001e`: `SettingsPageSystemComponents`
- `0x18003003e`: `SettingsPageInstalledApps`
- `0x18003026b`: `SystemSettings_StorageSense_AgentTools_ConfigureMCPB`
- `0x18003031f`: `SystemSettings_AgentTools_Remote`
- `0x18003033f`: `SystemSettings_AgentTools_Local`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::GetValue(
        SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  int ConsentValue; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int Boolean; // ebx
  __int64 v12; // r9
  __int64 v13; // rdx
  unsigned __int16 **v14; // rbx
  int String; // eax
  unsigned __int16 **v16; // rbx
  unsigned __int16 **v17; // rbx
  const unsigned __int16 *v19; // r8
  const unsigned __int16 *v20; // rax
  __int64 v21; // rdx
  const unsigned __int16 *v22; // r8
  const unsigned __int16 *v23; // rax
  const unsigned __int16 *v24; // r8
  const unsigned __int16 *v25; // rax
  const unsigned __int16 *v26; // r8
  const unsigned __int16 *v27; // r8
  unsigned __int8 v28; // cl
  const unsigned __int16 *v29; // r8
  const unsigned __int16 *v30; // r8
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // r8
  const unsigned __int16 *v33; // rax
  const unsigned __int16 *v34; // r8
  const unsigned __int16 *v35; // r8
  const unsigned __int16 *v36; // rax
  SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *v37; // rcx
  const unsigned __int16 *v38; // r8
  SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *v39; // rcx
  const unsigned __int16 *v40; // r8
  const unsigned __int16 *v41; // r8
  const unsigned __int16 *v42; // rax
  const unsigned __int16 *v43; // r8
  unsigned __int8 HasValidUserConfig; // al
  const unsigned __int16 *v45; // r8
  int v46; // eax
  __int64 v47; // rdx
  const unsigned __int16 *v48; // r8
  unsigned __int16 **v49; // rbx
  int v50; // eax
  __int64 v51; // rdx
  const unsigned __int16 *v52; // r8
  const unsigned __int16 *v53; // rax
  const unsigned __int16 *v54; // r8
  const unsigned __int16 *v55; // r8
  const unsigned __int16 *v56; // rax
  const unsigned __int16 *v57; // rax
  int v58; // [rsp+20h] [rbp-20h]
  int v59; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  struct SystemSettings::StorageSenseHandlers::UserConfigMCPB *v61; // [rsp+70h] [rbp+30h] BYREF

  *a3 = 0;
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1801090B0, (const unsigned __int16 *)a3) )
  {
    v61 = 0;
    ConsentValue = SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::GetConsentValue(this);
    if ( ConsentValue )
    {
      v8 = ConsentValue - 1;
      if ( !v8 )
        goto LABEL_10;
      v9 = v8 - 1;
      if ( !v9 )
      {
        v14 = (unsigned __int16 **)winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 216));
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v61,
          0);
        String = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
                   (SystemSettings::DataModel *)L"SystemSettings_StorageSense_AgentTools_WillAskForPermissionFormat",
                   (const unsigned __int16 *)&v61,
                   v14);
        Boolean = String;
        if ( String < 0 )
        {
          v13 = 1508;
LABEL_16:
          v12 = (unsigned int)String;
          goto LABEL_17;
        }
        goto LABEL_14;
      }
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( v10 != 1 )
        {
          Boolean = -2147024809;
          v12 = 2147942487LL;
          v13 = 1511;
LABEL_17:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v13,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\agenttoollist.cpp",
            (const char *)v12,
            v58);
LABEL_18:
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v61);
          return (unsigned int)Boolean;
        }
LABEL_10:
        v16 = (unsigned __int16 **)winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 216));
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v61,
          0);
        String = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
                   (SystemSettings::DataModel *)L"SystemSettings_StorageSense_AgentTools_CannotAccessFormat",
                   (const unsigned __int16 *)&v61,
                   v16);
        Boolean = String;
        if ( String < 0 )
        {
          v13 = 1504;
          goto LABEL_16;
        }
        goto LABEL_14;
      }
    }
    v17 = (unsigned __int16 **)winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 216));
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v61,
      0);
    String = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
               (SystemSettings::DataModel *)L"SystemSettings_StorageSense_AgentTools_CanAlwaysUseFormat",
               (const unsigned __int16 *)&v61,
               v17);
    Boolean = String;
    if ( String < 0 )
    {
      v13 = 1499;
      goto LABEL_16;
    }
LABEL_14:
    String = SystemSettings::DataModel::PropValueHelper::CreateString((const unsigned __int16 *)v61, a3);
    Boolean = String;
    if ( String < 0 )
    {
      v13 = 1515;
      goto LABEL_16;
    }
    goto LABEL_94;
  }
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180106C48, v6) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180108F90, v19) )
    {
      v23 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 232));
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v23, a3);
      if ( Boolean < 0 )
      {
        v21 = 1523;
        goto LABEL_24;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180108C20, v22) )
    {
      v25 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 264));
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v25, a3);
      if ( Boolean < 0 )
      {
        v21 = 1529;
        goto LABEL_24;
      }
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180108C50, v24) )
    {
      if ( !(unsigned __int8)winrt::operator==((char *)this + 264, &qword_18018BE60) )
      {
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(1u, a3);
        if ( Boolean < 0 )
        {
          v21 = 1541;
          goto LABEL_24;
        }
        return 0;
      }
LABEL_87:
      *a3 = 0;
      return 0;
    }
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109268, v26) )
    {
      if ( *((_BYTE *)this + 328) || *((_QWORD *)this + 35) || (v28 = 0, *((_QWORD *)this + 36)) )
        v28 = 1;
      Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(v28, a3);
      if ( Boolean >= 0 )
        return 0;
      v21 = 1547;
    }
    else
    {
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109290, v27) )
      {
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_BYTE *)this + 328), a3);
        if ( Boolean < 0 )
        {
          v21 = 1551;
          goto LABEL_24;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1801092D8, v29) )
      {
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_QWORD *)this + 35) != 0, a3);
        if ( Boolean < 0 )
        {
          v21 = 1555;
          goto LABEL_24;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109310, v30) )
      {
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_QWORD *)this + 36) != 0, a3);
        if ( Boolean < 0 )
        {
          v21 = 1559;
          goto LABEL_24;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109340, v31) )
      {
        v33 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 296));
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v33, a3);
        if ( Boolean < 0 )
        {
          v21 = 1563;
          goto LABEL_24;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109358, v32) )
      {
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(*((_QWORD *)this + 38) != 0, a3);
        if ( Boolean < 0 )
        {
          v21 = 1567;
          goto LABEL_24;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109378, v34) )
      {
        v36 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 304));
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v36, a3);
        if ( Boolean < 0 )
        {
          v21 = 1571;
          goto LABEL_24;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109398, v35) )
      {
        if ( SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::IsPackageSystemComponent(
               v37,
               (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 320)) )
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(L"SettingsPageSystemComponents", a3);
          if ( Boolean < 0 )
          {
            v21 = 1579;
            goto LABEL_24;
          }
        }
        else
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(L"SettingsPageInstalledApps", a3);
          if ( Boolean < 0 )
          {
            v21 = 1583;
            goto LABEL_24;
          }
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109428, v38) )
      {
        if ( SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::IsPackageSystemComponent(
               v39,
               (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 320)) )
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(
                      L"SystemSettings_StorageSense_HiddenSystemComponentsAdvancedPageLink",
                      a3);
          if ( Boolean < 0 )
          {
            v21 = 1590;
            goto LABEL_24;
          }
        }
        else
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(
                      L"SystemSettings_StorageSense_HiddenAppAdvancedPageLink",
                      a3);
          if ( Boolean < 0 )
          {
            v21 = 1594;
            goto LABEL_24;
          }
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109448, v40) )
      {
        v42 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 320));
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v42, a3);
        if ( Boolean < 0 )
        {
          v21 = 1599;
          goto LABEL_24;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109480, v41) )
      {
        HasValidUserConfig = SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::HasValidUserConfig(this);
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateBoolean(HasValidUserConfig, a3);
        if ( Boolean < 0 )
        {
          v21 = 1603;
          goto LABEL_24;
        }
        return 0;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1801094A8, v43) )
      {
        if ( SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::HasValidUserConfig(this) )
        {
          v61 = 0;
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v61);
          v46 = SystemSettings::StorageSenseHandlers::UserConfigMCPB::CreateInstance(
                  (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 208),
                  (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 216),
                  (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 224),
                  (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 232),
                  (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 248),
                  (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 256),
                  (SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 320),
                  &v61);
          Boolean = v46;
          if ( v46 >= 0 )
          {
            v46 = (**(__int64 (__fastcall ***)(struct SystemSettings::StorageSenseHandlers::UserConfigMCPB *, GUID *, struct IInspectable **))v61)(
                    v61,
                    &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                    a3);
            Boolean = v46;
            if ( v46 >= 0 )
            {
              Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v61);
              return 0;
            }
            v47 = 1621;
          }
          else
          {
            v47 = 1619;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v47,
            (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\agenttoollist.cpp",
            (const char *)(unsigned int)v46,
            v59);
          Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v61);
          return (unsigned int)Boolean;
        }
        goto LABEL_87;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1801094D0, v45) )
      {
        v61 = 0;
        v49 = (unsigned __int16 **)winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 232));
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v61,
          0);
        v50 = SystemSettings::DataModel::FormatResourceMessageArgAlloc(
                (SystemSettings::DataModel *)L"SystemSettings_StorageSense_AgentTools_ConfigureMCPB",
                (const unsigned __int16 *)&v61,
                v49);
        Boolean = v50;
        if ( v50 >= 0 )
        {
          v50 = SystemSettings::DataModel::PropValueHelper::CreateString((const unsigned __int16 *)v61, a3);
          Boolean = v50;
          if ( v50 >= 0 )
          {
LABEL_94:
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v61);
            return 0;
          }
          v51 = 1634;
        }
        else
        {
          v51 = 1633;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v51,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\agenttoollist.cpp",
          (const char *)(unsigned int)v50,
          v58);
        goto LABEL_18;
      }
      if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109580, v48) )
      {
        v53 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 272));
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v53, a3);
        if ( Boolean >= 0 )
          return 0;
        v21 = 1638;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109590, v52) )
      {
        if ( *((_BYTE *)this + 312) )
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(L"SystemSettings_AgentTools_Remote", a3);
          if ( Boolean >= 0 )
            return 0;
          v21 = 1644;
        }
        else
        {
          Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(L"SystemSettings_AgentTools_Local", a3);
          if ( Boolean >= 0 )
            return 0;
          v21 = 1648;
        }
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109640, v54) )
      {
        v56 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 280));
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v56, a3);
        if ( Boolean >= 0 )
          return 0;
        v21 = 1653;
      }
      else if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_180109668, v55) )
      {
        v57 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 288));
        Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v57, a3);
        if ( Boolean >= 0 )
          return 0;
        v21 = 1657;
      }
      else
      {
        Boolean = SystemSettings::DataModel::CListSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetValue(
                    this,
                    a2,
                    a3);
        if ( Boolean >= 0 )
          return 0;
        v21 = 1663;
      }
    }
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\agenttoollist.cpp",
      (const char *)(unsigned int)Boolean,
      v58);
    return (unsigned int)Boolean;
  }
  v20 = winrt::hstring::c_str((SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail *)((char *)this + 240));
  Boolean = SystemSettings::DataModel::PropValueHelper::CreateString(v20, a3);
  if ( Boolean < 0 )
  {
    v21 = 1519;
    goto LABEL_24;
  }
  return 0;
}

```

## disassembly

```asm
0x18002fbd0  mov     [rsp-18h+arg_0], rbx
0x18002fbd5  mov     [rsp-18h+arg_8], rsi
0x18002fbda  push    rbp
0x18002fbdb  push    rdi
0x18002fbdc  push    r14
0x18002fbde  mov     rbp, rsp
0x18002fbe1  sub     rsp, 40h
0x18002fbe5  mov     rdi, r8
0x18002fbe8  mov     rsi, rdx
0x18002fbeb  mov     rbx, rcx
0x18002fbee  xor     r14d, r14d
0x18002fbf1  mov     [r8], r14
0x18002fbf4  lea     rdx, stru_1801090B0; HSTRING
0x18002fbfb  mov     rcx, rsi; this
0x18002fbfe  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fc03  test    al, al
0x18002fc05  jz      loc_18002FD3A
0x18002fc0b  mov     [rbp+arg_10], r14
0x18002fc0f  mov     rcx, rbx
0x18002fc12  call    ?GetConsentValue@AgentToolMcpServerDetail@StorageSenseHandlers@SystemSettings@@QEBA?AW4McpConsentValue@Mcp@Agents@AI@Internal@Windows@winrt@@XZ; SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::GetConsentValue(void)
0x18002fc17  test    eax, eax
0x18002fc19  jz      loc_18002FCC0
0x18002fc1f  sub     eax, 1
0x18002fc22  jz      short loc_18002FC86
0x18002fc24  sub     eax, 1
0x18002fc27  jz      short loc_18002FC49
0x18002fc29  sub     eax, 1
0x18002fc2c  jz      loc_18002FCC0
0x18002fc32  cmp     eax, 1
0x18002fc35  jz      short loc_18002FC86
0x18002fc37  mov     ebx, 80070057h
0x18002fc3c  mov     r9d, ebx
0x18002fc3f  mov     edx, 5E7h
0x18002fc44  jmp     loc_18002FD14
0x18002fc49  lea     rcx, [rbx+0D8h]; this
0x18002fc50  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002fc55  mov     rbx, rax
0x18002fc58  xor     edx, edx
0x18002fc5a  lea     rcx, [rbp+arg_10]
0x18002fc5e  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002fc63  mov     r8, rbx; unsigned __int16 **
0x18002fc66  lea     rdx, [rbp+arg_10]; unsigned __int16 *
0x18002fc6a  lea     rcx, aSystemsettings_294; "SystemSettings_StorageSense_AgentTools_"...
0x18002fc71  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x18002fc76  mov     ebx, eax
0x18002fc78  test    eax, eax
0x18002fc7a  jns     short loc_18002FCFA
0x18002fc7c  mov     edx, 5E4h
0x18002fc81  jmp     loc_18002FD11
0x18002fc86  lea     rcx, [rbx+0D8h]; this
0x18002fc8d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002fc92  mov     rbx, rax
0x18002fc95  xor     edx, edx
0x18002fc97  lea     rcx, [rbp+arg_10]
0x18002fc9b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002fca0  mov     r8, rbx; unsigned __int16 **
0x18002fca3  lea     rdx, [rbp+arg_10]; unsigned __int16 *
0x18002fca7  lea     rcx, aSystemsettings_116; "SystemSettings_StorageSense_AgentTools_"...
0x18002fcae  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x18002fcb3  mov     ebx, eax
0x18002fcb5  test    eax, eax
0x18002fcb7  jns     short loc_18002FCFA
0x18002fcb9  mov     edx, 5E0h
0x18002fcbe  jmp     short loc_18002FD11
0x18002fcc0  lea     rcx, [rbx+0D8h]; this
0x18002fcc7  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002fccc  mov     rbx, rax
0x18002fccf  xor     edx, edx
0x18002fcd1  lea     rcx, [rbp+arg_10]
0x18002fcd5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002fcda  mov     r8, rbx; unsigned __int16 **
0x18002fcdd  lea     rdx, [rbp+arg_10]; unsigned __int16 *
0x18002fce1  lea     rcx, aSystemsettings_295; "SystemSettings_StorageSense_AgentTools_"...
0x18002fce8  call    ?FormatResourceMessageArgAlloc@DataModel@SystemSettings@@YAJPEBGPEAPEAGZZ; SystemSettings::DataModel::FormatResourceMessageArgAlloc(ushort const *,ushort * *,...)
0x18002fced  mov     ebx, eax
0x18002fcef  test    eax, eax
0x18002fcf1  jns     short loc_18002FCFA
0x18002fcf3  mov     edx, 5DBh
0x18002fcf8  jmp     short loc_18002FD11
0x18002fcfa  mov     rdx, rdi; struct IInspectable **
0x18002fcfd  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18002fd01  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18002fd06  mov     ebx, eax
0x18002fd08  test    eax, eax
0x18002fd0a  jns     short loc_18002FD35
0x18002fd0c  mov     edx, 5EBh; void *
0x18002fd11  mov     r9d, eax; char *
0x18002fd14  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\coresettinghandlers"...
0x18002fd1b  mov     rcx, [rbp+18h]; this
0x18002fd1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd24  nop
0x18002fd25  lea     rcx, [rbp+arg_10]
0x18002fd29  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002fd2e  mov     eax, ebx
0x18002fd30  jmp     loc_18003021B
0x18002fd35  jmp     loc_1800302B4
0x18002fd3a  lea     rdx, stru_180106C48; HSTRING
0x18002fd41  mov     rcx, rsi; this
0x18002fd44  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fd49  test    al, al
0x18002fd4b  jz      short loc_18002FD88
0x18002fd4d  lea     rcx, [rbx+0F0h]; this
0x18002fd54  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002fd59  mov     rcx, rax; unsigned __int16 *
0x18002fd5c  mov     rdx, rdi; struct IInspectable **
0x18002fd5f  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18002fd64  mov     ebx, eax
0x18002fd66  test    eax, eax
0x18002fd68  jns     loc_180030219
0x18002fd6e  mov     edx, 5EFh; void *
0x18002fd73  mov     rcx, [rbp+18h]; this
0x18002fd77  mov     r9d, ebx; char *
0x18002fd7a  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\coresettinghandlers"...
0x18002fd81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd86  jmp     short loc_18002FD2E
0x18002fd88  lea     rdx, stru_180108F90; HSTRING
0x18002fd8f  mov     rcx, rsi; this
0x18002fd92  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fd97  test    al, al
0x18002fd99  jz      short loc_18002FDC3
0x18002fd9b  lea     rcx, [rbx+0E8h]; this
0x18002fda2  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002fda7  mov     rcx, rax; unsigned __int16 *
0x18002fdaa  mov     rdx, rdi; struct IInspectable **
0x18002fdad  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18002fdb2  mov     ebx, eax
0x18002fdb4  test    eax, eax
0x18002fdb6  jns     loc_180030219
0x18002fdbc  mov     edx, 5F3h
0x18002fdc1  jmp     short loc_18002FD73
0x18002fdc3  lea     rdx, stru_180108C20; HSTRING
0x18002fdca  mov     rcx, rsi; this
0x18002fdcd  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fdd2  test    al, al
0x18002fdd4  jz      short loc_18002FE01
0x18002fdd6  lea     rcx, [rbx+108h]; this
0x18002fddd  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002fde2  mov     rcx, rax; unsigned __int16 *
0x18002fde5  mov     rdx, rdi; struct IInspectable **
0x18002fde8  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18002fded  mov     ebx, eax
0x18002fdef  test    eax, eax
0x18002fdf1  jns     loc_180030219
0x18002fdf7  mov     edx, 5F9h
0x18002fdfc  jmp     loc_18002FD73
0x18002fe01  lea     rdx, stru_180108C50; HSTRING
0x18002fe08  mov     rcx, rsi; this
0x18002fe0b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fe10  test    al, al
0x18002fe12  jz      short loc_18002FE4D
0x18002fe14  lea     rcx, [rbx+108h]
0x18002fe1b  lea     rdx, qword_18018BE60
0x18002fe22  call    ??8winrt@@YA_NAEBUhstring@0@0@Z; winrt::operator==(winrt::hstring const &,winrt::hstring const &)
0x18002fe27  test    al, al
0x18002fe29  jnz     loc_18003022E
0x18002fe2f  mov     rdx, rdi; struct IInspectable **
0x18002fe32  mov     cl, 1; unsigned __int8
0x18002fe34  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18002fe39  mov     ebx, eax
0x18002fe3b  test    eax, eax
0x18002fe3d  jns     loc_180030219
0x18002fe43  mov     edx, 605h
0x18002fe48  jmp     loc_18002FD73
0x18002fe4d  lea     rdx, stru_180109268; HSTRING
0x18002fe54  mov     rcx, rsi; this
0x18002fe57  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fe5c  test    al, al
0x18002fe5e  jz      short loc_18002FE9C
0x18002fe60  cmp     [rbx+148h], r14b
0x18002fe67  jnz     short loc_18002FE7E
0x18002fe69  cmp     [rbx+118h], r14
0x18002fe70  jnz     short loc_18002FE7E
0x18002fe72  cmp     [rbx+120h], r14
0x18002fe79  mov     cl, r14b
0x18002fe7c  jz      short loc_18002FE80
0x18002fe7e  mov     cl, 1; unsigned __int8
0x18002fe80  mov     rdx, rdi; struct IInspectable **
0x18002fe83  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18002fe88  mov     ebx, eax
0x18002fe8a  test    eax, eax
0x18002fe8c  jns     loc_180030219
0x18002fe92  mov     edx, 60Bh
0x18002fe97  jmp     loc_18002FD73
0x18002fe9c  lea     rdx, stru_180109290; HSTRING
0x18002fea3  mov     rcx, rsi; this
0x18002fea6  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002feab  test    al, al
0x18002fead  jz      short loc_18002FED1
0x18002feaf  mov     rdx, rdi; struct IInspectable **
0x18002feb2  mov     cl, [rbx+148h]; unsigned __int8
0x18002feb8  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18002febd  mov     ebx, eax
0x18002febf  test    eax, eax
0x18002fec1  jns     loc_180030219
0x18002fec7  mov     edx, 60Fh
0x18002fecc  jmp     loc_18002FD73
0x18002fed1  lea     rdx, stru_1801092D8; HSTRING
0x18002fed8  mov     rcx, rsi; this
0x18002fedb  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002fee0  test    al, al
0x18002fee2  jz      short loc_18002FF0A
0x18002fee4  cmp     [rbx+118h], r14
0x18002feeb  setnz   cl; unsigned __int8
0x18002feee  mov     rdx, rdi; struct IInspectable **
0x18002fef1  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18002fef6  mov     ebx, eax
0x18002fef8  test    eax, eax
0x18002fefa  jns     loc_180030219
0x18002ff00  mov     edx, 613h
0x18002ff05  jmp     loc_18002FD73
0x18002ff0a  lea     rdx, stru_180109310; HSTRING
0x18002ff11  mov     rcx, rsi; this
0x18002ff14  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002ff19  test    al, al
0x18002ff1b  jz      short loc_18002FF43
0x18002ff1d  cmp     [rbx+120h], r14
0x18002ff24  setnz   cl; unsigned __int8
0x18002ff27  mov     rdx, rdi; struct IInspectable **
0x18002ff2a  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18002ff2f  mov     ebx, eax
0x18002ff31  test    eax, eax
0x18002ff33  jns     loc_180030219
0x18002ff39  mov     edx, 617h
0x18002ff3e  jmp     loc_18002FD73
0x18002ff43  lea     rdx, stru_180109340; HSTRING
0x18002ff4a  mov     rcx, rsi; this
0x18002ff4d  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002ff52  test    al, al
0x18002ff54  jz      short loc_18002FF81
0x18002ff56  lea     rcx, [rbx+128h]; this
0x18002ff5d  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002ff62  mov     rcx, rax; unsigned __int16 *
0x18002ff65  mov     rdx, rdi; struct IInspectable **
0x18002ff68  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18002ff6d  mov     ebx, eax
0x18002ff6f  test    eax, eax
0x18002ff71  jns     loc_180030219
0x18002ff77  mov     edx, 61Bh
0x18002ff7c  jmp     loc_18002FD73
0x18002ff81  lea     rdx, stru_180109358; HSTRING
0x18002ff88  mov     rcx, rsi; this
0x18002ff8b  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002ff90  test    al, al
0x18002ff92  jz      short loc_18002FFBA
0x18002ff94  cmp     [rbx+130h], r14
0x18002ff9b  setnz   cl; unsigned __int8
0x18002ff9e  mov     rdx, rdi; struct IInspectable **
0x18002ffa1  call    ?CreateBoolean@PropValueHelper@DataModel@SystemSettings@@SAJEPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateBoolean(uchar,IInspectable * *)
0x18002ffa6  mov     ebx, eax
0x18002ffa8  test    eax, eax
0x18002ffaa  jns     loc_180030219
0x18002ffb0  mov     edx, 61Fh
0x18002ffb5  jmp     loc_18002FD73
0x18002ffba  lea     rdx, stru_180109378; HSTRING
0x18002ffc1  mov     rcx, rsi; this
0x18002ffc4  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002ffc9  test    al, al
0x18002ffcb  jz      short loc_18002FFF8
0x18002ffcd  lea     rcx, [rbx+130h]; this
0x18002ffd4  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18002ffd9  mov     rcx, rax; unsigned __int16 *
0x18002ffdc  mov     rdx, rdi; struct IInspectable **
0x18002ffdf  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18002ffe4  mov     ebx, eax
0x18002ffe6  test    eax, eax
0x18002ffe8  jns     loc_180030219
0x18002ffee  mov     edx, 623h
0x18002fff3  jmp     loc_18002FD73
0x18002fff8  lea     rdx, stru_180109398; HSTRING
0x18002ffff  mov     rcx, rsi; this
0x180030002  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x180030007  test    al, al
0x180030009  jz      short loc_18003005E
0x18003000b  lea     rdx, [rbx+140h]; struct winrt::hstring *
0x180030012  call    ?IsPackageSystemComponent@AgentToolMcpServerDetail@StorageSenseHandlers@SystemSettings@@AEAA_NAEAUhstring@winrt@@@Z; SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::IsPackageSystemComponent(winrt::hstring &)
0x180030017  mov     rdx, rdi; struct IInspectable **
0x18003001a  test    al, al
0x18003001c  jz      short loc_18003003E
0x18003001e  lea     rcx, aSettingspagesy; "SettingsPageSystemComponents"
0x180030025  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003002a  mov     ebx, eax
0x18003002c  test    eax, eax
0x18003002e  jns     loc_180030219
0x180030034  mov     edx, 62Bh
0x180030039  jmp     loc_18002FD73
0x18003003e  lea     rcx, aSettingspagein; "SettingsPageInstalledApps"
0x180030045  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18003004a  mov     ebx, eax
0x18003004c  test    eax, eax
0x18003004e  jns     loc_180030219
0x180030054  mov     edx, 62Fh
0x180030059  jmp     loc_18002FD73
0x18003005e  lea     rdx, stru_180109428; HSTRING
0x180030065  mov     rcx, rsi; this
0x180030068  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18003006d  test    al, al
0x18003006f  jz      short loc_1800300C4
0x180030071  lea     rdx, [rbx+140h]; struct winrt::hstring *
0x180030078  call    ?IsPackageSystemComponent@AgentToolMcpServerDetail@StorageSenseHandlers@SystemSettings@@AEAA_NAEAUhstring@winrt@@@Z; SystemSettings::StorageSenseHandlers::AgentToolMcpServerDetail::IsPackageSystemComponent(winrt::hstring &)
0x18003007d  mov     rdx, rdi; struct IInspectable **
  ... truncated ...
```
