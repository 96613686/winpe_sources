# WaasMedic::AutomaticCorruptionRepairPlugin::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)

- ea: `0x1800387e0`
- end: `0x180038ea2`
- name: `?IsActionApplicable2@AutomaticCorruptionRepairPlugin@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z`
- size: `1730`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180009a54`
- `0x1800179c4`
- `0x18001cae0`
- `0x18002543c`
- `0x180025b44`
- `0x1800272b4`
- `0x180028a74`
- `0x180029168`
- `0x18003741c`
- `0x180037db4`
- `0x1800386f4`
- `0x1800387e0`
- `0x180039d3c`
- `0x180055fb8`
- `0x1800561c0`
- `0x180056a90`
- `0x18005718c`
- `0x180064010`

## string_xrefs

- `0x180038857`: `Plugin is applicable due to manual remediation.`
- `0x180038802`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x18003882a`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x1800388c9`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x180038a32`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x180038a88`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x180038ae5`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x180038b95`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x180038c40`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x180038d09`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x180038dce`: `onecore\enduser\waasmedic\lib\plugins\automaticcorruptionrepairplugin.cpp`
- `0x18003891c`: `No local repair source configured`
- `0x18003887b`: `Plugin not applicable. Reason code: %d`
- `0x1800389b3`: `CorruptionRepairPlugin.IterationCount`
- `0x1800389f2`: `Touchstone has already ran.`
- `0x180038a15`: `SYSTEM\WaaS\Plugin`
- `0x180038ce3`: `SYSTEM\WaaS\Plugin`
- `0x180038da8`: `SYSTEM\WaaS\Plugin`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::AutomaticCorruptionRepairPlugin::IsActionApplicable2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4)
{
  unsigned int v5; // ebx
  int IsActionApplicable2; // eax
  int HasUnrestrictedConnection; // edi
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  unsigned int v15; // edx
  int NDays; // eax
  int v17; // eax
  int AllowInPlaceUpgradeRegKeyValue; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // [rsp+20h] [rbp-58h]
  bool v24[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v25; // [rsp+38h] [rbp-40h] BYREF
  __int128 v26; // [rsp+40h] [rbp-38h] BYREF
  __int64 v27; // [rsp+50h] [rbp-28h]
  int v28; // [rsp+58h] [rbp-20h] BYREF
  int v29; // [rsp+5Ch] [rbp-1Ch] BYREF
  unsigned int v30; // [rsp+60h] [rbp-18h] BYREF
  int v31; // [rsp+64h] [rbp-14h] BYREF
  int v32; // [rsp+68h] [rbp-10h] BYREF
  _DWORD v33[3]; // [rsp+6Ch] [rbp-Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]
  char v35; // [rsp+B8h] [rbp+40h] BYREF

  if ( !a4 )
  {
    v5 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
      (const char *)0x80004003LL,
      v23);
    return v5;
  }
  IsActionApplicable2 = WaasMedic::CRemediationPluginBase::IsActionApplicable2();
  HasUnrestrictedConnection = IsActionApplicable2;
  if ( IsActionApplicable2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
      (const char *)(unsigned int)IsActionApplicable2,
      v23);
    return (unsigned int)HasUnrestrictedConnection;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl)
    || *a4 != 16 )
  {
    if ( *a4 != 3 && *a4 )
    {
      LogLevelW(4u, L"Plugin not applicable. Reason code: %d");
      return 0;
    }
    winrt::Windows::Internal::WaasMedicDocked::CBSHelper::CBSHelper((winrt::Windows::Internal::WaasMedicDocked::CBSHelper *)&v25);
    v35 = 0;
    v33[0] = 0;
    HasUnrestrictedConnection = *(_DWORD *)winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::CanUseWUAsRepairSource(
                                             &v25,
                                             &v28,
                                             &v35,
                                             v33);
    if ( HasUnrestrictedConnection < 0 )
    {
      v9 = 52;
      goto LABEL_15;
    }
    if ( !v35 )
    {
      v24[0] = 0;
      HasUnrestrictedConnection = *(_DWORD *)winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::HasLocalRepairSource(
                                               &v25,
                                               &v28,
                                               v24);
      if ( HasUnrestrictedConnection < 0 )
      {
        v9 = 57;
        goto LABEL_15;
      }
      if ( !v24[0] )
      {
        LogLevelW(4u, L"No local repair source configured");
LABEL_23:
        *a4 = 4;
        goto LABEL_116;
      }
    }
    v28 = 0;
    HasUnrestrictedConnection = WaasMedic::MiscUtil::FreeSpaceInMB(&v28);
    if ( HasUnrestrictedConnection < 0 )
    {
      v9 = 68;
      goto LABEL_15;
    }
    if ( v28 >= 1000 )
    {
      v24[0] = 0;
      HasUnrestrictedConnection = WaasMedic::NetworkUtil::HasUnrestrictedConnection(v24);
      if ( HasUnrestrictedConnection < 0 )
      {
        v9 = 77;
        goto LABEL_15;
      }
      if ( !v24[0] )
      {
        LogLevelW(4u, L"Device not connected to network or metered connection found. Cannot perform ACR");
        goto LABEL_23;
      }
      v29 = 0;
      v11 = WaasMedic::RegQueryDwordValue(
              v10,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\rempl\\shell",
              L"CorruptionRepairPlugin.IterationCount",
              &v29);
      HasUnrestrictedConnection = v11;
      if ( v11 == -2147024894 )
        goto LABEL_40;
      if ( v11 )
      {
        if ( v11 >= 0 )
        {
LABEL_16:
          if ( v25 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
          return (unsigned int)HasUnrestrictedConnection;
        }
        v9 = 91;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
          (const char *)(unsigned int)HasUnrestrictedConnection,
          v23);
        goto LABEL_16;
      }
      if ( !v29 )
      {
LABEL_40:
        v26 = 0;
        v27 = 0;
        v24[0] = 0;
        v14 = WaasMedic::UsoHelper::Initialize((WaasMedic::UsoHelper *)&v26);
        HasUnrestrictedConnection = v14;
        if ( v14 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x68,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
            (const char *)(unsigned int)v14,
            v23);
          if ( *((_QWORD *)&v26 + 1) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
          if ( (_QWORD)v26 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
          goto LABEL_16;
        }
        NDays = WaasMedic::UsoHelper::SeenErrorInLastNDays((WaasMedic::UsoHelper *)&v26, v15, v24);
        HasUnrestrictedConnection = NDays;
        if ( NDays < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x69,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
            (const char *)(unsigned int)NDays,
            v23);
          if ( *((_QWORD *)&v26 + 1) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
          if ( (_QWORD)v26 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
          goto LABEL_16;
        }
        if ( v24[0] )
        {
          v24[0] = 0;
          v17 = WaasMedic::UsoHelper::IsInPlaceUpgradeInProgress((WaasMedic::UsoHelper *)&v26, v24);
          HasUnrestrictedConnection = v17;
          if ( v17 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x72,
              (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
              (const char *)(unsigned int)v17,
              v23);
            if ( *((_QWORD *)&v26 + 1) )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
            if ( (_QWORD)v26 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
            goto LABEL_16;
          }
          if ( v24[0] )
          {
            *a4 = 15;
            LogLevelW(4u, L"USO reported cloud based In-Place Upgrade is in progress. ACR not eligible to run.");
            if ( *((_QWORD *)&v26 + 1) )
              (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
            if ( (_QWORD)v26 )
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
          }
          else
          {
            v30 = 0;
            AllowInPlaceUpgradeRegKeyValue = WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(&v30);
            HasUnrestrictedConnection = AllowInPlaceUpgradeRegKeyValue;
            if ( AllowInPlaceUpgradeRegKeyValue < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x7B,
                (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
                (const char *)(unsigned int)AllowInPlaceUpgradeRegKeyValue,
                v23);
              if ( *((_QWORD *)&v26 + 1) )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
              if ( (_QWORD)v26 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
              goto LABEL_16;
            }
            if ( v30 )
            {
              *a4 = 14;
              LogLevelW(4u, L"In-Place Upgrade is in progress:%d. ACR not eligible to run.");
              if ( *((_QWORD *)&v26 + 1) )
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
              if ( (_QWORD)v26 )
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
            }
            else
            {
              v31 = 0;
              v20 = WaasMedic::RegQueryDwordValue(v19, L"SYSTEM\\WaaS\\Plugin", L"EscalatetoInPlaceUpgrade", &v31);
              HasUnrestrictedConnection = v20;
              if ( v20 == -2147024894 )
                goto LABEL_97;
              if ( v20 )
              {
                if ( v20 < 0 )
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x86,
                    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
                    (const char *)(unsigned int)v20,
                    v23);
                if ( *((_QWORD *)&v26 + 1) )
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
                if ( (_QWORD)v26 )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
                goto LABEL_16;
              }
              if ( !v31 )
              {
LABEL_97:
                v32 = 0;
                v22 = WaasMedic::RegQueryDwordValue(v21, L"SYSTEM\\WaaS\\Plugin", L"EscalateToMCR", &v32);
                HasUnrestrictedConnection = v22;
                if ( v22 == -2147024894 )
                  goto LABEL_112;
                if ( v22 )
                {
                  if ( v22 < 0 )
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x90,
                      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
                      (const char *)(unsigned int)v22,
                      v23);
                  if ( *((_QWORD *)&v26 + 1) )
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
                  if ( (_QWORD)v26 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
                  goto LABEL_16;
                }
                if ( !v32 )
                {
LABEL_112:
                  if ( *((_QWORD *)&v26 + 1) )
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
                  if ( (_QWORD)v26 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
                }
                else
                {
                  *a4 = 12;
                  LogLevelW(4u, L"Found existing escalation to MCR. Marking ACR is inapplicable.");
                  if ( *((_QWORD *)&v26 + 1) )
                    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
                  if ( (_QWORD)v26 )
                    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
                }
              }
              else
              {
                *a4 = 12;
                LogLevelW(4u, L"Found existing escalation to IPU. Marking ACR is inapplicable.");
                if ( *((_QWORD *)&v26 + 1) )
                  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
                if ( (_QWORD)v26 )
                  (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
              }
            }
          }
        }
        else
        {
          *a4 = 12;
          LogLevelW(4u, L"No updating errors found.");
          if ( *((_QWORD *)&v26 + 1) )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v26 + 1) + 16LL))(*((_QWORD *)&v26 + 1));
          if ( (_QWORD)v26 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v26 + 16LL))(v26);
        }
      }
      else
      {
        *a4 = 12;
        LogLevelW(4u, L"Touchstone has already ran.");
        LOBYTE(v23) = 0;
        v13 = WaasMedic::RegSetDwordValue(v12, L"SYSTEM\\WaaS\\Plugin", L"EscalateToMCR", 1);
        v5 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x61,
            (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\automaticcorruptionrepairplugin.cpp",
            (const char *)(unsigned int)v13,
            v23);
          if ( v25 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
          return v5;
        }
      }
    }
    else
    {
      LogLevelW(4u, L"Not enough disk space to perform ACR. Found space: %d MB");
      *a4 = 9;
    }
LABEL_116:
    if ( v25 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v25);
    return 0;
  }
  LogLevelW(4u, L"Plugin is applicable due to manual remediation.");
  return 0;
}

```

## disassembly

```asm
0x1800387e0  push    rbp
0x1800387e2  push    rbx
0x1800387e3  push    rsi
0x1800387e4  push    rdi
0x1800387e5  mov     rbp, rsp
0x1800387e8  sub     rsp, 78h
0x1800387ec  mov     rbx, r9
0x1800387ef  xor     esi, esi
0x1800387f1  test    r9, r9
0x1800387f4  jnz     short loc_180038818
0x1800387f6  mov     rcx, [rbp+20h]; this
0x1800387fa  mov     ebx, 80004003h
0x1800387ff  mov     r9d, ebx; char *
0x180038802  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180038809  lea     edx, [rsi+1Bh]; void *
0x18003880c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038811  mov     eax, ebx
0x180038813  jmp     loc_180038E99
0x180038818  call    ?IsActionApplicable2@CRemediationPluginBase@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)
0x18003881d  mov     edi, eax
0x18003881f  test    eax, eax
0x180038821  jns     short loc_180038842
0x180038823  mov     rcx, [rbp+20h]; this
0x180038827  mov     r9d, eax; char *
0x18003882a  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180038831  mov     edx, 1Ch; void *
0x180038836  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003883b  mov     eax, edi
0x18003883d  jmp     loc_180038E99
0x180038842  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x180038849  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x18003884e  test    al, al
0x180038850  jz      short loc_18003886D
0x180038852  cmp     dword ptr [rbx], 10h
0x180038855  jnz     short loc_18003886D
0x180038857  lea     rdx, aPluginIsApplic; "Plugin is applicable due to manual reme"...
0x18003885e  mov     ecx, 4; unsigned __int8
0x180038863  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038868  jmp     loc_180038E97
0x18003886d  mov     r8d, [rbx]
0x180038870  cmp     r8d, 3
0x180038874  jz      short loc_180038891
0x180038876  test    r8d, r8d
0x180038879  jz      short loc_180038891
0x18003887b  lea     rdx, aPluginNotAppli; "Plugin not applicable. Reason code: %d"
0x180038882  mov     ecx, 4; unsigned __int8
0x180038887  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003888c  jmp     loc_180038E97
0x180038891  lea     rcx, [rbp+var_40]; this
0x180038895  call    ??0CBSHelper@WaasMedicDocked@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::WaasMedicDocked::CBSHelper::CBSHelper(void)
0x18003889a  nop
0x18003889b  mov     [rbp+arg_18], sil
0x18003889f  mov     [rbp+var_C], esi
0x1800388a2  lea     r9, [rbp+var_C]
0x1800388a6  lea     r8, [rbp+arg_18]
0x1800388aa  lea     rdx, [rbp+var_20]
0x1800388ae  lea     rcx, [rbp+var_40]
0x1800388b2  call    ?CanUseWUAsRepairSource@?$consume_Windows_Internal_WaasMedicDocked_ICBSHelper@UICBSHelper@WaasMedicDocked@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEA_NAEAI@Z; winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::CanUseWUAsRepairSource(bool &,uint &)
0x1800388b7  mov     edi, [rax]
0x1800388b9  test    edi, edi
0x1800388bb  jns     short loc_1800388EE
0x1800388bd  mov     edx, 34h ; '4'; void *
0x1800388c2  mov     rcx, [rbp+20h]; this
0x1800388c6  mov     r9d, edi; char *
0x1800388c9  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x1800388d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800388d5  nop
0x1800388d6  cmp     [rbp+var_40], rsi
0x1800388da  jz      loc_18003883B
0x1800388e0  lea     rcx, [rbp+var_40]
0x1800388e4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800388e9  jmp     loc_18003883B
0x1800388ee  cmp     [rbp+arg_18], sil
0x1800388f2  jnz     short loc_180038938
0x1800388f4  mov     [rbp+var_48], sil
0x1800388f8  lea     r8, [rbp+var_48]
0x1800388fc  lea     rdx, [rbp+var_20]
0x180038900  lea     rcx, [rbp+var_40]
0x180038904  call    ?HasLocalRepairSource@?$consume_Windows_Internal_WaasMedicDocked_ICBSHelper@UICBSHelper@WaasMedicDocked@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEA_N@Z; winrt::impl::consume_Windows_Internal_WaasMedicDocked_ICBSHelper<winrt::Windows::Internal::WaasMedicDocked::ICBSHelper>::HasLocalRepairSource(bool &)
0x180038909  mov     edi, [rax]
0x18003890b  test    edi, edi
0x18003890d  jns     short loc_180038916
0x18003890f  mov     edx, 39h ; '9'
0x180038914  jmp     short loc_1800388C2
0x180038916  cmp     [rbp+var_48], sil
0x18003891a  jnz     short loc_180038938
0x18003891c  lea     rdx, aNoLocalRepairS; "No local repair source configured"
0x180038923  mov     ecx, 4; unsigned __int8
0x180038928  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18003892d  mov     dword ptr [rbx], 4
0x180038933  jmp     loc_180038E88
0x180038938  mov     [rbp+var_20], esi
0x18003893b  lea     rcx, [rbp+var_20]; int *
0x18003893f  call    ?FreeSpaceInMB@MiscUtil@WaasMedic@@SAJAEAH@Z; WaasMedic::MiscUtil::FreeSpaceInMB(int &)
0x180038944  mov     edi, eax
0x180038946  test    eax, eax
0x180038948  jns     short loc_180038954
0x18003894a  mov     edx, 44h ; 'D'
0x18003894f  jmp     loc_1800388C2
0x180038954  mov     r8d, [rbp+var_20]
0x180038958  cmp     r8d, 3E8h
0x18003895f  jge     short loc_18003897D
0x180038961  lea     rdx, aNotEnoughDiskS; "Not enough disk space to perform ACR. F"...
0x180038968  mov     ecx, 4; unsigned __int8
0x18003896d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038972  mov     dword ptr [rbx], 9
0x180038978  jmp     loc_180038E88
0x18003897d  mov     [rbp+var_48], sil
0x180038981  lea     rcx, [rbp+var_48]; bool *
0x180038985  call    ?HasUnrestrictedConnection@NetworkUtil@WaasMedic@@SAJAEA_N@Z; WaasMedic::NetworkUtil::HasUnrestrictedConnection(bool &)
0x18003898a  mov     edi, eax
0x18003898c  test    eax, eax
0x18003898e  jns     short loc_18003899A
0x180038990  mov     edx, 4Dh ; 'M'
0x180038995  jmp     loc_1800388C2
0x18003899a  cmp     [rbp+var_48], sil
0x18003899e  jnz     short loc_1800389AC
0x1800389a0  lea     rdx, aDeviceNotConne_0; "Device not connected to network or mete"...
0x1800389a7  jmp     loc_180038923
0x1800389ac  mov     [rbp+var_1C], esi
0x1800389af  lea     r9, [rbp+var_1C]
0x1800389b3  lea     r8, aCorruptionrepa; "CorruptionRepairPlugin.IterationCount"
0x1800389ba  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800389c1  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAKW4RegistryHiveType@1@@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *,WaasMedic::RegistryHiveType)
0x1800389c6  mov     edi, eax
0x1800389c8  cmp     eax, 80070002h
0x1800389cd  jz      loc_180038A5C
0x1800389d3  test    eax, eax
0x1800389d5  jz      short loc_1800389E7
0x1800389d7  jns     loc_1800388D6
0x1800389dd  mov     edx, 5Bh ; '['
0x1800389e2  jmp     loc_1800388C2
0x1800389e7  cmp     [rbp+var_1C], esi
0x1800389ea  jbe     short loc_180038A5C
0x1800389ec  mov     dword ptr [rbx], 0Ch
0x1800389f2  lea     rdx, aTouchstoneHasA; "Touchstone has already ran."
0x1800389f9  mov     ecx, 4; unsigned __int8
0x1800389fe  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038a03  mov     byte ptr [rsp+78h+var_58], sil; int
0x180038a08  mov     r9d, 1
0x180038a0e  lea     r8, aEscalatetomcr; "EscalateToMCR"
0x180038a15  lea     rdx, aSystemWaasPlug; "SYSTEM\\WaaS\\Plugin"
0x180038a1c  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x180038a21  mov     ebx, eax
0x180038a23  test    eax, eax
0x180038a25  jns     loc_180038E88
0x180038a2b  mov     rcx, [rbp+20h]; this
0x180038a2f  mov     r9d, eax; char *
0x180038a32  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180038a39  mov     edx, 61h ; 'a'; void *
0x180038a3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038a43  nop
0x180038a44  cmp     [rbp+var_40], rsi
0x180038a48  jz      loc_180038811
0x180038a4e  lea     rcx, [rbp+var_40]
0x180038a52  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180038a57  jmp     loc_180038811
0x180038a5c  xor     eax, eax
0x180038a5e  mov     [rbp+var_28], rax
0x180038a62  xorps   xmm1, xmm1
0x180038a65  movdqu  [rbp+var_38], xmm1
0x180038a6a  mov     byte ptr [rbp+var_28], sil
0x180038a6e  mov     [rbp+var_48], sil
0x180038a72  lea     rcx, [rbp+var_38]; this
0x180038a76  call    ?Initialize@UsoHelper@WaasMedic@@QEAAJXZ; WaasMedic::UsoHelper::Initialize(void)
0x180038a7b  mov     edi, eax
0x180038a7d  test    eax, eax
0x180038a7f  jns     short loc_180038ACB
0x180038a81  mov     rcx, [rbp+20h]; this
0x180038a85  mov     r9d, eax; char *
0x180038a88  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180038a8f  mov     edx, 68h ; 'h'; void *
0x180038a94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038a99  nop
0x180038a9a  mov     rcx, qword ptr [rbp+var_38+8]
0x180038a9e  test    rcx, rcx
0x180038aa1  jz      short loc_180038AB0
0x180038aa3  mov     rax, [rcx]
0x180038aa6  mov     rax, [rax+10h]
0x180038aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038aaf  nop
0x180038ab0  mov     rcx, qword ptr [rbp+var_38]
0x180038ab4  test    rcx, rcx
0x180038ab7  jz      short loc_180038AC6
0x180038ab9  mov     rax, [rcx]
0x180038abc  mov     rax, [rax+10h]
0x180038ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ac5  nop
0x180038ac6  jmp     loc_1800388D6
0x180038acb  lea     r8, [rbp+var_48]; bool *
0x180038acf  lea     rcx, [rbp+var_38]; this
0x180038ad3  call    ?SeenErrorInLastNDays@UsoHelper@WaasMedic@@QEAAJIAEA_N@Z; WaasMedic::UsoHelper::SeenErrorInLastNDays(uint,bool &)
0x180038ad8  mov     edi, eax
0x180038ada  test    eax, eax
0x180038adc  jns     short loc_180038B28
0x180038ade  mov     rcx, [rbp+20h]; this
0x180038ae2  mov     r9d, eax; char *
0x180038ae5  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180038aec  mov     edx, 69h ; 'i'; void *
0x180038af1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038af6  nop
0x180038af7  mov     rcx, qword ptr [rbp+var_38+8]
0x180038afb  test    rcx, rcx
0x180038afe  jz      short loc_180038B0D
0x180038b00  mov     rax, [rcx]
0x180038b03  mov     rax, [rax+10h]
0x180038b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b0c  nop
0x180038b0d  mov     rcx, qword ptr [rbp+var_38]
0x180038b11  test    rcx, rcx
0x180038b14  jz      short loc_180038B23
0x180038b16  mov     rax, [rcx]
0x180038b19  mov     rax, [rax+10h]
0x180038b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b22  nop
0x180038b23  jmp     loc_1800388D6
0x180038b28  cmp     [rbp+var_48], sil
0x180038b2c  jnz     short loc_180038B77
0x180038b2e  mov     dword ptr [rbx], 0Ch
0x180038b34  lea     rdx, aNoUpdatingErro; "No updating errors found."
0x180038b3b  mov     ecx, 4; unsigned __int8
0x180038b40  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038b45  nop
0x180038b46  mov     rcx, qword ptr [rbp+var_38+8]
0x180038b4a  test    rcx, rcx
0x180038b4d  jz      short loc_180038B5C
0x180038b4f  mov     rax, [rcx]
0x180038b52  mov     rax, [rax+10h]
0x180038b56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b5b  nop
0x180038b5c  mov     rcx, qword ptr [rbp+var_38]
0x180038b60  test    rcx, rcx
0x180038b63  jz      short loc_180038B72
0x180038b65  mov     rax, [rcx]
0x180038b68  mov     rax, [rax+10h]
0x180038b6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038b71  nop
0x180038b72  jmp     loc_180038E88
0x180038b77  mov     [rbp+var_48], sil
0x180038b7b  lea     rdx, [rbp+var_48]; bool *
0x180038b7f  lea     rcx, [rbp+var_38]; this
0x180038b83  call    ?IsInPlaceUpgradeInProgress@UsoHelper@WaasMedic@@QEAAJAEA_N@Z; WaasMedic::UsoHelper::IsInPlaceUpgradeInProgress(bool &)
0x180038b88  mov     edi, eax
0x180038b8a  test    eax, eax
0x180038b8c  jns     short loc_180038BD8
0x180038b8e  mov     rcx, [rbp+20h]; this
0x180038b92  mov     r9d, eax; char *
0x180038b95  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180038b9c  mov     edx, 72h ; 'r'; void *
0x180038ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038ba6  nop
0x180038ba7  mov     rcx, qword ptr [rbp+var_38+8]
0x180038bab  test    rcx, rcx
0x180038bae  jz      short loc_180038BBD
0x180038bb0  mov     rax, [rcx]
0x180038bb3  mov     rax, [rax+10h]
0x180038bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bbc  nop
0x180038bbd  mov     rcx, qword ptr [rbp+var_38]
0x180038bc1  test    rcx, rcx
0x180038bc4  jz      short loc_180038BD3
0x180038bc6  mov     rax, [rcx]
0x180038bc9  mov     rax, [rax+10h]
0x180038bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038bd2  nop
0x180038bd3  jmp     loc_1800388D6
0x180038bd8  cmp     [rbp+var_48], sil
0x180038bdc  jz      short loc_180038C27
0x180038bde  mov     dword ptr [rbx], 0Fh
0x180038be4  lea     rdx, aUsoReportedClo_0; "USO reported cloud based In-Place Upgra"...
0x180038beb  mov     ecx, 4; unsigned __int8
0x180038bf0  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038bf5  nop
0x180038bf6  mov     rcx, qword ptr [rbp+var_38+8]
0x180038bfa  test    rcx, rcx
0x180038bfd  jz      short loc_180038C0C
0x180038bff  mov     rax, [rcx]
0x180038c02  mov     rax, [rax+10h]
0x180038c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c0b  nop
0x180038c0c  mov     rcx, qword ptr [rbp+var_38]
0x180038c10  test    rcx, rcx
0x180038c13  jz      short loc_180038C22
0x180038c15  mov     rax, [rcx]
0x180038c18  mov     rax, [rax+10h]
0x180038c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c21  nop
0x180038c22  jmp     loc_180038E88
0x180038c27  mov     [rbp+var_18], esi
0x180038c2a  lea     rcx, [rbp+var_18]; unsigned int *
0x180038c2e  call    ?GetAllowInPlaceUpgradeRegKeyValue@IpuHelper@WaasMedic@@SAJAEAK@Z; WaasMedic::IpuHelper::GetAllowInPlaceUpgradeRegKeyValue(ulong &)
0x180038c33  mov     edi, eax
0x180038c35  test    eax, eax
0x180038c37  jns     short loc_180038C83
0x180038c39  mov     rcx, [rbp+20h]; this
0x180038c3d  mov     r9d, eax; char *
0x180038c40  lea     r8, aOnecoreEnduser_26; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180038c47  mov     edx, 7Bh ; '{'; void *
0x180038c4c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038c51  nop
  ... truncated ...
```
