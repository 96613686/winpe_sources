# QuickMachineRecoveryAdminFlowHandler::SetQuickMachineRecoverySetting(ushort const *,ushort const *)

- ea: `0x140071a28`
- end: `0x140071d88`
- name: `?SetQuickMachineRecoverySetting@QuickMachineRecoveryAdminFlowHandler@@SAJPEBG0@Z`
- size: `864`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140020120`
- `0x140071a28`

## callees

- `0x140004e68`
- `0x140071680`
- `0x140071970`
- `0x140071a28`
- `0x140071da4`
- `0x140073cec`
- `0x140073db8`
- `0x140073f30`
- `0x14007d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140071b65`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140071bea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140071c03`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140071c1c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140071b65`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140071bea`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140071c03`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140071c1c`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140071b72`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140071c30`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140071b72`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x140071c30`
- `KERNEL32!GetProcAddress` at `0x140071b36`
- `KERNEL32!GetProcAddress` at `0x140071b36`
- `KERNEL32!LoadLibraryExW` at `0x140071ab9`
- `KERNEL32!LoadLibraryExW` at `0x140071ab9`
- `KERNEL32!GetLastError` at `0x140071afb`
- `KERNEL32!GetLastError` at `0x140071cdc`
- `KERNEL32!GetLastError` at `0x140071afb`
- `KERNEL32!GetLastError` at `0x140071cdc`

## string_xrefs

- `0x140071ab2`: `reagent.dll`
- `0x140071aea`: `Failed to load reagent.dll`

## pseudocode

```c
__int64 __fastcall QuickMachineRecoveryAdminFlowHandler::SetQuickMachineRecoverySetting(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  HMODULE v6; // rax
  FARPROC ProcAddress; // r15
  unsigned int v8; // esi
  _OWORD *v9; // rax
  int *v10; // rdx
  __int64 v11; // rcx
  signed int v12; // eax
  _QWORD v14[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v16[604]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v17[656]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(v16, 0, sizeof(v16));
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
    UnattendInitializeLogEx2();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
    UnattendLogW(0, L"Enter QuickMachineRecoveryAdminFlowHandler::SetQuickMachineRecoverySetting");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
    UnattendLogW(0, L"Setting: %s, Value: %s", a1, a2);
  v14[1] = LoadLibraryExW(L"reagent.dll", 0, 0);
  v14[0] = &RAII::CAutoFreeLibrary::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<HINSTANCE__ *>::operator!(v14) )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
      UnattendLogW(1, L"Failed to load reagent.dll");
LABEL_10:
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_39;
  }
  v6 = (HMODULE)(*(__int64 (__fastcall **)(_QWORD *))(v14[0] + 32LL))(v14);
  ProcAddress = GetProcAddress(v6, "WinReSetSetting");
  if ( !ProcAddress )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
      UnattendLogW(1, L"Failed to get WinReSetSetting function");
    goto LABEL_10;
  }
  v5 = 0;
  if ( !(unsigned int)_o__wcsicmp(a1, L"SetCloudRemediation") )
  {
    v15 = _o__wtoi(a2);
    if ( !v15 )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
        UnattendLogW(0, L"Turning off AutoRemediation because CloudRemediation is off...");
      v5 = QuickMachineRecoveryAdminFlowHandler::SetQuickMachineRecoverySetting(L"SetAutoRemediation", L"0");
      if ( (v5 & 0x80000000) != 0 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
          UnattendLogW(1, L"Failed to set AutoRemediation to 0");
        goto LABEL_39;
      }
    }
    v8 = 6;
    goto LABEL_30;
  }
  if ( !(unsigned int)_o__wcsicmp(a1, L"SetAutoRemediation") )
  {
    v8 = 1;
LABEL_29:
    v15 = _o__wtoi(a2);
LABEL_30:
    v9 = v17;
    v10 = &v15;
    v11 = 4;
    do
    {
      *v9 = *(_OWORD *)v10;
      v9[1] = *((_OWORD *)v10 + 1);
      v9[2] = *((_OWORD *)v10 + 2);
      v9[3] = *((_OWORD *)v10 + 3);
      v9[4] = *((_OWORD *)v10 + 4);
      v9[5] = *((_OWORD *)v10 + 5);
      v9[6] = *((_OWORD *)v10 + 6);
      v9[7] = *((_OWORD *)v10 + 7);
      v9 += 8;
      v10 += 32;
      --v11;
    }
    while ( v11 );
    *v9 = *(_OWORD *)v10;
    v9[1] = *((_OWORD *)v10 + 1);
    v9[2] = *((_OWORD *)v10 + 2);
    v9[3] = *((_OWORD *)v10 + 3);
    v9[4] = *((_OWORD *)v10 + 4);
    v9[5] = *((_OWORD *)v10 + 5);
    if ( !((unsigned int (__fastcall *)(_QWORD, _BYTE *, __int64))ProcAddress)(v8, v17, 128) )
    {
      v12 = GetLastError();
      v5 = v12;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
        UnattendLogW(1, L"fnWinReSetSetting failed with 0x%x", v5);
    }
    goto LABEL_39;
  }
  if ( !(unsigned int)_o__wcsicmp(a1, L"SetRetryInterval") )
  {
    v8 = 3;
    goto LABEL_29;
  }
  if ( !(unsigned int)_o__wcsicmp(a1, L"SetTimeToReboot") )
  {
    v8 = 2;
    goto LABEL_29;
  }
  v5 = -2147024809;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
    UnattendLogW(1, L"Invalid setting: %s", a1);
LABEL_39:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
    UnattendLogW(0, L"Exit QuickMachineRecoveryAdminFlowHandler::SetQuickMachineRecoverySetting");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl'::`2'::impl) )
    UnattendFinalizeLog();
  v14[0] = &RAII::CAutoFreeLibrary::`vftable';
  RAII::CAutoFreeLibrary::Release((RAII::CAutoFreeLibrary *)v14);
  return v5;
}

```

## disassembly

```asm
0x140071a28  push    rbp
0x140071a2a  push    rbx
0x140071a2b  push    rsi
0x140071a2c  push    r12
0x140071a2e  push    r13
0x140071a30  push    r14
0x140071a32  push    r15
0x140071a34  lea     rbp, [rsp-3F0h]
0x140071a3c  sub     rsp, 4F0h
0x140071a43  mov     r14, rdx
0x140071a46  mov     rsi, rcx
0x140071a49  xor     edx, edx; Val
0x140071a4b  mov     r8d, 25Ch; Size
0x140071a51  lea     rcx, [rsp+520h+var_4EC]; void *
0x140071a56  call    memset_0
0x140071a5b  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::GetImpl(void)'::`2'::impl
0x140071a62  mov     rcx, r12
0x140071a65  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071a6a  test    al, al
0x140071a6c  jz      short loc_140071A73
0x140071a6e  call    UnattendInitializeLogEx2
0x140071a73  mov     rcx, r12
0x140071a76  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071a7b  test    al, al
0x140071a7d  jz      short loc_140071A8D
0x140071a7f  lea     rdx, aEnterQuickmach; "Enter QuickMachineRecoveryAdminFlowHand"...
0x140071a86  xor     ecx, ecx
0x140071a88  call    UnattendLogW
0x140071a8d  mov     rcx, r12
0x140071a90  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071a95  test    al, al
0x140071a97  jz      short loc_140071AAD
0x140071a99  mov     r9, r14
0x140071a9c  mov     r8, rsi
0x140071a9f  lea     rdx, aSettingSValueS; "Setting: %s, Value: %s"
0x140071aa6  xor     ecx, ecx
0x140071aa8  call    UnattendLogW
0x140071aad  xor     r8d, r8d; dwFlags
0x140071ab0  xor     edx, edx; hFile
0x140071ab2  lea     rcx, aReagentDll; "reagent.dll"
0x140071ab9  call    cs:__imp_LoadLibraryExW
0x140071abf  mov     [rsp+520h+var_4F8], rax
0x140071ac4  lea     r13, ??_7CAutoFreeLibrary@RAII@@6B@; const RAII::CAutoFreeLibrary::`vftable'
0x140071acb  mov     [rsp+520h+var_500], r13
0x140071ad0  lea     rcx, [rsp+520h+var_500]
0x140071ad5  call    ??7?$CAutoCleanupBase@PEAUHINSTANCE__@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<HINSTANCE__ *>::operator!(void)
0x140071ada  test    al, al
0x140071adc  jz      short loc_140071B19
0x140071ade  mov     rcx, r12
0x140071ae1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071ae6  test    al, al
0x140071ae8  jz      short loc_140071AFB
0x140071aea  lea     rdx, aFailedToLoadRe; "Failed to load reagent.dll"
0x140071af1  mov     ecx, 1
0x140071af6  call    UnattendLogW
0x140071afb  call    cs:__imp_GetLastError
0x140071b01  mov     ebx, eax
0x140071b03  test    eax, eax
0x140071b05  jle     loc_140071D38
0x140071b0b  movzx   ebx, ax
0x140071b0e  or      ebx, 80070000h
0x140071b14  jmp     loc_140071D38
0x140071b19  mov     rax, [rsp+520h+var_500]
0x140071b1e  lea     rcx, [rsp+520h+var_500]
0x140071b23  mov     rax, [rax+20h]
0x140071b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071b2c  mov     rcx, rax; hModule
0x140071b2f  lea     rdx, aWinresetsettin; "WinReSetSetting"
0x140071b36  call    cs:__imp_GetProcAddress
0x140071b3c  mov     r15, rax
0x140071b3f  test    rax, rax
0x140071b42  jnz     short loc_140071B59
0x140071b44  mov     rcx, r12
0x140071b47  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071b4c  test    al, al
0x140071b4e  jz      short loc_140071AFB
0x140071b50  lea     rdx, aFailedToGetWin; "Failed to get WinReSetSetting function"
0x140071b57  jmp     short loc_140071AF1
0x140071b59  xor     ebx, ebx
0x140071b5b  lea     rdx, aSetcloudremedi; "SetCloudRemediation"
0x140071b62  mov     rcx, rsi
0x140071b65  call    cs:__imp__o__wcsicmp
0x140071b6b  test    eax, eax
0x140071b6d  jnz     short loc_140071BE0
0x140071b6f  mov     rcx, r14
0x140071b72  call    cs:__imp__o__wtoi
0x140071b78  mov     [rsp+520h+var_4F0], eax
0x140071b7c  test    eax, eax
0x140071b7e  jnz     short loc_140071BD9
0x140071b80  mov     rcx, r12
0x140071b83  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071b88  test    al, al
0x140071b8a  jz      short loc_140071B9A
0x140071b8c  lea     rdx, aTurningOffAuto; "Turning off AutoRemediation because Clo"...
0x140071b93  xor     ecx, ecx
0x140071b95  call    UnattendLogW
0x140071b9a  lea     rdx, a0; "0"
0x140071ba1  lea     rcx, aSetautoremedia; "SetAutoRemediation"
0x140071ba8  call    ?SetQuickMachineRecoverySetting@QuickMachineRecoveryAdminFlowHandler@@SAJPEBG0@Z; QuickMachineRecoveryAdminFlowHandler::SetQuickMachineRecoverySetting(ushort const *,ushort const *)
0x140071bad  mov     ebx, eax
0x140071baf  test    eax, eax
0x140071bb1  jns     short loc_140071BD9
0x140071bb3  mov     rcx, r12
0x140071bb6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071bbb  test    al, al
0x140071bbd  jz      loc_140071D38
0x140071bc3  lea     rdx, aFailedToSetAut; "Failed to set AutoRemediation to 0"
0x140071bca  mov     ecx, 1
0x140071bcf  call    UnattendLogW
0x140071bd4  jmp     loc_140071D38
0x140071bd9  mov     esi, 6
0x140071bde  jmp     short loc_140071C3A
0x140071be0  lea     rdx, aSetautoremedia; "SetAutoRemediation"
0x140071be7  mov     rcx, rsi
0x140071bea  call    cs:__imp__o__wcsicmp
0x140071bf0  test    eax, eax
0x140071bf2  jnz     short loc_140071BF9
0x140071bf4  lea     esi, [rax+1]
0x140071bf7  jmp     short loc_140071C2D
0x140071bf9  lea     rdx, aSetretryinterv; "SetRetryInterval"
0x140071c00  mov     rcx, rsi
0x140071c03  call    cs:__imp__o__wcsicmp
0x140071c09  test    eax, eax
0x140071c0b  jnz     short loc_140071C12
0x140071c0d  lea     esi, [rax+3]
0x140071c10  jmp     short loc_140071C2D
0x140071c12  lea     rdx, aSettimetoreboo; "SetTimeToReboot"
0x140071c19  mov     rcx, rsi
0x140071c1c  call    cs:__imp__o__wcsicmp
0x140071c22  test    eax, eax
0x140071c24  jnz     loc_140071D13
0x140071c2a  lea     esi, [rax+2]
0x140071c2d  mov     rcx, r14
0x140071c30  call    cs:__imp__o__wtoi
0x140071c36  mov     [rsp+520h+var_4F0], eax
0x140071c3a  lea     rax, [rbp+420h+var_290]
0x140071c41  lea     rdx, [rsp+520h+var_4F0]
0x140071c46  mov     ecx, 4
0x140071c4b  lea     r8d, [rcx+7Ch]
0x140071c4f  movups  xmm0, xmmword ptr [rdx]
0x140071c52  movups  xmmword ptr [rax], xmm0
0x140071c55  movups  xmm1, xmmword ptr [rdx+10h]
0x140071c59  movups  xmmword ptr [rax+10h], xmm1
0x140071c5d  movups  xmm0, xmmword ptr [rdx+20h]
0x140071c61  movups  xmmword ptr [rax+20h], xmm0
0x140071c65  movups  xmm1, xmmword ptr [rdx+30h]
0x140071c69  movups  xmmword ptr [rax+30h], xmm1
0x140071c6d  movups  xmm0, xmmword ptr [rdx+40h]
0x140071c71  movups  xmmword ptr [rax+40h], xmm0
0x140071c75  movups  xmm1, xmmword ptr [rdx+50h]
0x140071c79  movups  xmmword ptr [rax+50h], xmm1
0x140071c7d  movups  xmm0, xmmword ptr [rdx+60h]
0x140071c81  movups  xmmword ptr [rax+60h], xmm0
0x140071c85  movups  xmm1, xmmword ptr [rdx+70h]
0x140071c89  movups  xmmword ptr [rax+70h], xmm1
0x140071c8d  add     rax, r8
0x140071c90  add     rdx, r8
0x140071c93  sub     rcx, 1
0x140071c97  jnz     short loc_140071C4F
0x140071c99  movups  xmm0, xmmword ptr [rdx]
0x140071c9c  movups  xmmword ptr [rax], xmm0
0x140071c9f  movups  xmm1, xmmword ptr [rdx+10h]
0x140071ca3  movups  xmmword ptr [rax+10h], xmm1
0x140071ca7  movups  xmm0, xmmword ptr [rdx+20h]
0x140071cab  movups  xmmword ptr [rax+20h], xmm0
0x140071caf  movups  xmm1, xmmword ptr [rdx+30h]
0x140071cb3  movups  xmmword ptr [rax+30h], xmm1
0x140071cb7  movups  xmm0, xmmword ptr [rdx+40h]
0x140071cbb  movups  xmmword ptr [rax+40h], xmm0
0x140071cbf  movups  xmm1, xmmword ptr [rdx+50h]
0x140071cc3  movups  xmmword ptr [rax+50h], xmm1
0x140071cc7  lea     rdx, [rbp+420h+var_290]
0x140071cce  mov     ecx, esi
0x140071cd0  mov     rax, r15
0x140071cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140071cd8  test    eax, eax
0x140071cda  jnz     short loc_140071D38
0x140071cdc  call    cs:__imp_GetLastError
0x140071ce2  mov     ebx, eax
0x140071ce4  test    eax, eax
0x140071ce6  jle     short loc_140071CF1
0x140071ce8  movzx   ebx, ax
0x140071ceb  or      ebx, 80070000h
0x140071cf1  mov     rcx, r12
0x140071cf4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071cf9  test    al, al
0x140071cfb  jz      short loc_140071D38
0x140071cfd  mov     r8d, ebx
0x140071d00  lea     rdx, aFnwinresetsett; "fnWinReSetSetting failed with 0x%x"
0x140071d07  mov     ecx, 1
0x140071d0c  call    UnattendLogW
0x140071d11  jmp     short loc_140071D38
0x140071d13  mov     ebx, 80070057h
0x140071d18  mov     rcx, r12
0x140071d1b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071d20  test    al, al
0x140071d22  jz      short loc_140071D38
0x140071d24  mov     r8, rsi
0x140071d27  lea     rdx, aInvalidSetting; "Invalid setting: %s"
0x140071d2e  mov     ecx, 1
0x140071d33  call    UnattendLogW
0x140071d38  mov     rcx, r12
0x140071d3b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071d40  test    al, al
0x140071d42  jz      short loc_140071D52
0x140071d44  lea     rdx, aExitQuickmachi; "Exit QuickMachineRecoveryAdminFlowHandl"...
0x140071d4b  xor     ecx, ecx
0x140071d4d  call    UnattendLogW
0x140071d52  mov     rcx, r12
0x140071d55  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRSettingsLogging>::__private_IsEnabled(void)
0x140071d5a  test    al, al
0x140071d5c  jz      short loc_140071D64
0x140071d5e  call    UnattendFinalizeLog
0x140071d63  nop
0x140071d64  mov     [rsp+520h+var_500], r13
0x140071d69  lea     rcx, [rsp+520h+var_500]; this
0x140071d6e  call    ?Release@CAutoFreeLibrary@RAII@@UEAAXXZ; RAII::CAutoFreeLibrary::Release(void)
0x140071d73  mov     eax, ebx
0x140071d75  add     rsp, 4F0h
0x140071d7c  pop     r15
0x140071d7e  pop     r14
0x140071d80  pop     r13
0x140071d82  pop     r12
0x140071d84  pop     rsi
0x140071d85  pop     rbx
0x140071d86  pop     rbp
0x140071d87  retn
```
