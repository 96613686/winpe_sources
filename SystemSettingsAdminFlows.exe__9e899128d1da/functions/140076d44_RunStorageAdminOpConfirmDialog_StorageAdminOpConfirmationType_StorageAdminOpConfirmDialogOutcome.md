# RunStorageAdminOpConfirmDialog(StorageAdminOpConfirmationType,StorageAdminOpConfirmDialogOutcome &)

- ea: `0x140076d44`
- end: `0x140077321`
- name: `?RunStorageAdminOpConfirmDialog@@YAJW4StorageAdminOpConfirmationType@@AEAUStorageAdminOpConfirmDialogOutcome@@@Z`
- size: `1501`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14005d7a0`
- `0x14005d860`
- `0x14005d9c0`
- `0x14005daa0`
- `0x14005db80`
- `0x14005dca0`
- `0x14005ddc0`
- `0x14005e250`
- `0x14005e4e0`

## callees

- `0x140005f30`
- `0x140005fdc`
- `0x14001fc88`
- `0x140031b28`
- `0x1400337b0`
- `0x140076d44`
- `0x140077670`
- `0x1400776ac`

## import_xrefs

- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076df5`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076e17`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076e39`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076e5b`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076e7d`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076e9f`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076ed1`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076f1d`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076f3f`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076f61`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076f83`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076fa5`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140076fc7`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x14007701c`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x14007703e`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140077060`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140077082`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x1400770a4`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x1400770c6`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140077118`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x14007713a`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140077159`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140077178`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x140077197`
- `SystemSettingsThresholdAdminFlowUI!StorageOpConfirmPage_CreateInstance` at `0x1400771b6`
- `SystemSettingsThresholdAdminFlowUI!DeletePartitionConfirmPage_CreateInstance` at `0x140076ec1`

## string_xrefs

- `0x140076ee7`: `CreateVhdConfirm_PromptText`
- `0x140076edc`: `CreateVhdConfirm_HeaderText`
- `0x140076e2d`: `RenameVolumeConfirm_PromptText`
- `0x140076e22`: `RenameVolumeConfirm_HeaderText`
- `0x1400770dc`: `DeletePoolConfirm_PromptText`
- `0x1400770d1`: `DeletePoolConfirm_HeaderText`
- `0x140076f33`: `RenamePoolConfirm_PromptText`
- `0x140076f28`: `RenamePoolConfirm_HeaderText`
- `0x140076f55`: `CreatePoolConfirm_PromptText`
- `0x140076f4a`: `CreatePoolConfirm_HeaderText`
- `0x140077054`: `CreateSpaceConfirm_PromptText`
- `0x140077049`: `CreateSpaceConfirm_HeaderText`
- `0x140077098`: `RemovePoolDisksConfirm_PromptText`
- `0x14007708d`: `RemovePoolDisksConfirm_HeaderText`
- `0x140077032`: `DeleteSpaceConfirm_PromptText`
- `0x140077027`: `DeleteSpaceConfirm_HeaderText`
- `0x140077150`: `RemoveAccessPathConfirm_PromptText`
- `0x140077145`: `RemoveAccessPathConfirm_HeaderText`
- `0x14007716f`: `MountVolumeToPathConfirm_PromptText`
- `0x140077164`: `MountVolumeToPathConfirm_HeaderText`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall RunStorageAdminOpConfirmDialog(int a1, _QWORD *a2)
{
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  const wchar_t *v8; // rax
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  unsigned int v24; // ebx
  _DWORD *v25; // rdi
  __int64 *v26; // rax
  __int64 v27; // rcx
  std::_Ref_count_base *v28; // rcx
  void (__stdcall *v29)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK); // rcx
  _QWORD v31[2]; // [rsp+20h] [rbp-79h] BYREF
  __int64 v32; // [rsp+30h] [rbp-69h] BYREF
  std::_Ref_count_base *v33; // [rsp+38h] [rbp-61h]
  _OWORD pv[2]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v35; // [rsp+60h] [rbp-39h]
  __int64 v36; // [rsp+68h] [rbp-31h]
  std::_Ref_count_base *v37[2]; // [rsp+70h] [rbp-29h]
  void (__fastcall *v38)(struct StorageOpConfirmDialogOutcomeNotifyData *); // [rsp+80h] [rbp-19h]
  char *v39; // [rsp+88h] [rbp-11h]
  __int128 v40; // [rsp+90h] [rbp-9h]
  __int128 v41; // [rsp+A0h] [rbp+7h]
  __int128 v42; // [rsp+B0h] [rbp+17h]
  __int64 v43; // [rsp+C0h] [rbp+27h]

  memset(pv, 0, sizeof(pv));
  v35 = 0;
  v36 = 0;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  if ( a1 > 14 )
  {
    if ( a1 > 21 )
    {
      v19 = a1 - 22;
      if ( !v19 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"ExtendSpaceConfirm_HeaderText";
        v8 = L"ExtendSpaceConfirm_PromptText";
        goto LABEL_57;
      }
      v20 = v19 - 1;
      if ( !v20 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"SwitchPartitionStyleConfirm_HeaderText";
        v8 = L"SwitchPartitionStyleConfirm_PromptText";
        goto LABEL_57;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"TriggerOptimizePoolConfirm_HeaderText";
        v8 = L"TriggerOptimizePoolConfirm_PromptText";
        goto LABEL_57;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"MountVolumeToPathConfirm_HeaderText";
        v8 = L"MountVolumeToPathConfirm_PromptText";
        goto LABEL_57;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"RemoveAccessPathConfirm_HeaderText";
        v8 = L"RemoveAccessPathConfirm_PromptText";
        goto LABEL_57;
      }
      if ( v23 == 1 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"UnretireDiskConfirm_HeaderText";
        v8 = L"UnretireDiskConfirm_PromptText";
        goto LABEL_57;
      }
    }
    else
    {
      v14 = a1 - 15;
      if ( !v14 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"DeletePoolConfirm_HeaderText";
        v8 = L"DeletePoolConfirm_PromptText";
        goto LABEL_57;
      }
      v15 = v14 - 1;
      if ( !v15 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"AddPoolDisksConfirm_HeaderText";
        v8 = L"AddPoolDisksConfirm_PromptText";
        goto LABEL_57;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"RemovePoolDisksConfirm_HeaderText";
        v8 = L"RemovePoolDisksConfirm_PromptText";
        goto LABEL_57;
      }
      v17 = v16 - 1;
      if ( !v17 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"PreparePoolDiskRemovalConfirm_HeaderText";
        v8 = L"PreparePoolDiskRemovalConfirm_PromptText";
        goto LABEL_57;
      }
      v18 = v17 - 1;
      if ( !v18 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"CreateSpaceConfirm_HeaderText";
        v8 = L"CreateSpaceConfirm_PromptText";
        goto LABEL_57;
      }
      if ( v18 == 1 )
      {
        v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
        *(_QWORD *)&v41 = L"DeleteSpaceConfirm_HeaderText";
        v8 = L"DeleteSpaceConfirm_PromptText";
        goto LABEL_57;
      }
    }
    goto LABEL_50;
  }
  if ( a1 > 7 )
  {
    v9 = a1 - 8;
    if ( !v9 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"AttachVhdConfirm_HeaderText";
      v8 = L"AttachVhdConfirm_PromptText";
      goto LABEL_57;
    }
    v10 = v9 - 1;
    if ( !v10 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"DetachVhdConfirm_HeaderText";
      v8 = L"DetachVhdConfirm_PromptText";
      goto LABEL_57;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"OnlineDiskConfirm_HeaderText";
      v8 = L"OnlineDiskConfirm_PromptText";
      goto LABEL_57;
    }
    v12 = v11 - 1;
    if ( !v12 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"OfflineDiskConfirm_HeaderText";
      v8 = L"OfflineDiskConfirm_PromptText";
      goto LABEL_57;
    }
    v13 = v12 - 1;
    if ( !v13 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"CreatePoolConfirm_HeaderText";
      v8 = L"CreatePoolConfirm_PromptText";
      goto LABEL_57;
    }
    if ( v13 == 1 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"RenamePoolConfirm_HeaderText";
      v8 = L"RenamePoolConfirm_PromptText";
      goto LABEL_57;
    }
    goto LABEL_50;
  }
  if ( a1 == 7 )
  {
    v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
    *(_QWORD *)&v41 = L"CreateVhdConfirm_HeaderText";
    v8 = L"CreateVhdConfirm_PromptText";
    goto LABEL_57;
  }
  if ( a1 )
  {
    v3 = a1 - 1;
    if ( !v3 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"ResizePartitionConfirm_HeaderText";
      v8 = L"ResizePartitionConfirm_PromptText";
      goto LABEL_57;
    }
    v4 = v3 - 1;
    if ( !v4 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"InitializeDiskConfirm_HeaderText";
      v8 = L"InitializeDiskConfirm_PromptText";
      goto LABEL_57;
    }
    v5 = v4 - 1;
    if ( !v5 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"FormatVolumeConfirm_HeaderText";
      v8 = L"FormatVolumeConfirm_PromptText";
      goto LABEL_57;
    }
    v6 = v5 - 1;
    if ( !v6 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"InitializeVolumeConfirm_HeaderText";
      v8 = L"InitializeVolumeConfirm_PromptText";
      goto LABEL_57;
    }
    v7 = v6 - 1;
    if ( !v7 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"RenameVolumeConfirm_HeaderText";
      v8 = L"RenameVolumeConfirm_PromptText";
      goto LABEL_57;
    }
    if ( v7 == 1 )
    {
      v37[1] = (std::_Ref_count_base *)StorageOpConfirmPage_CreateInstance;
      *(_QWORD *)&v41 = L"SetDriveLetterConfirm_HeaderText";
      v8 = L"SetDriveLetterConfirm_PromptText";
LABEL_57:
      *((_QWORD *)&v41 + 1) = v8;
      goto LABEL_58;
    }
LABEL_50:
    v24 = -2147024809;
    goto LABEL_69;
  }
  v37[1] = (std::_Ref_count_base *)DeletePartitionConfirmPage_CreateInstance;
LABEL_58:
  LODWORD(v43) = 270;
  v25 = operator new(0x20u);
  *(_OWORD *)v25 = 0;
  v25[2] = 1;
  v25[3] = 1;
  *(_QWORD *)v25 = &std::_Ref_count_obj2<StorageAdminOpConfirmationDialog>::`vftable';
  *((_QWORD *)v25 + 2) = 0;
  v25[6] = 0;
  v24 = -2147023728;
  v25[5] = -2147023728;
  v31[0] = v25 + 4;
  v31[1] = v25;
  if ( v25 == (_DWORD *)-16LL )
  {
    v24 = -2147024882;
  }
  else
  {
    v26 = std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>(&v32, v31);
    v27 = *v26;
    *v26 = v36;
    v36 = v27;
    v28 = (std::_Ref_count_base *)v26[1];
    v26[1] = (__int64)v37[0];
    v37[0] = v28;
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    *(_QWORD *)&v42 = L"Yes";
    *((_QWORD *)&v42 + 1) = L"No";
    v38 = StorageAdminOpConfirmationDialog::NotifyDialogOutcome;
    v39 = (char *)(v25 + 4);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixVhdAndPoolModernAdminDialogHang>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixVhdAndPoolModernAdminDialogHang>::GetImpl'::`2'::impl)
      || !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_CreateVhdPrompt>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_CreateVhdPrompt>::GetImpl'::`2'::impl) )
    {
      v29 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))StorageAdminOpConfirmationDialog::RunXamlPopupDialog;
    }
    else
    {
      LODWORD(pv[0]) = 185;
      v29 = (void (__stdcall *)(PTP_CALLBACK_INSTANCE, PVOID, PTP_WORK))RunXAMLFlowWork;
    }
    RunFlowThread(v29, (unsigned int *)pv);
    if ( *((_BYTE *)v25 + 24) )
    {
      *a2 = *((_QWORD *)v25 + 2);
      v24 = 0;
    }
  }
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v25);
LABEL_69:
  if ( v37[0] )
    std::_Ref_count_base::_Decref(v37[0]);
  return v24;
}

```

## disassembly

```asm
0x140076d44  mov     [rsp-8+arg_0], rbx
0x140076d49  mov     [rsp-8+arg_10], rsi
0x140076d4e  push    rbp
0x140076d4f  push    rdi
0x140076d50  push    r14
0x140076d52  lea     rbp, [rsp-47h]
0x140076d57  sub     rsp, 0E0h
0x140076d5e  mov     rax, cs:__security_cookie
0x140076d65  xor     rax, rsp
0x140076d68  mov     [rbp+57h+var_20], rax
0x140076d6c  mov     r14, rdx
0x140076d6f  xorps   xmm0, xmm0
0x140076d72  xor     eax, eax
0x140076d74  movups  [rbp+57h+pv], xmm0
0x140076d78  movups  [rbp+57h+var_A0], xmm0
0x140076d7c  mov     [rbp+57h+var_90], rax
0x140076d80  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x140076d84  mov     [rbp+57h+var_88], rax
0x140076d88  xorps   xmm1, xmm1
0x140076d8b  movdqa  xmmword ptr [rbp+57h+var_88+8], xmm1
0x140076d90  mov     [rbp+57h+var_70], rax
0x140076d94  mov     [rbp+57h+var_68], rax
0x140076d98  movdqa  [rbp+57h+var_60], xmm0
0x140076d9d  movdqa  [rbp+57h+var_50], xmm1
0x140076da2  movdqa  [rbp+57h+var_40], xmm0
0x140076da7  mov     [rbp+57h+var_30], rax
0x140076dab  cmp     ecx, 0Eh
0x140076dae  jg      loc_140076FE9
0x140076db4  cmp     ecx, 7
0x140076db7  jg      loc_140076EF3
0x140076dbd  jz      loc_140076ED1
0x140076dc3  test    ecx, ecx
0x140076dc5  jz      loc_140076EC1
0x140076dcb  sub     ecx, 1
0x140076dce  jz      loc_140076E9F
0x140076dd4  sub     ecx, 1
0x140076dd7  jz      loc_140076E7D
0x140076ddd  sub     ecx, 1
0x140076de0  jz      short loc_140076E5B
0x140076de2  sub     ecx, 1
0x140076de5  jz      short loc_140076E39
0x140076de7  sub     ecx, 1
0x140076dea  jz      short loc_140076E17
0x140076dec  cmp     ecx, 1
0x140076def  jnz     loc_14007710E
0x140076df5  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076dfc  mov     [rbp+57h+var_78], rax
0x140076e00  lea     rax, aSetdriveletter; "SetDriveLetterConfirm_HeaderText"
0x140076e07  mov     qword ptr [rbp+57h+var_50], rax
0x140076e0b  lea     rax, aSetdriveletter_0; "SetDriveLetterConfirm_PromptText"
0x140076e12  jmp     loc_1400771D3
0x140076e17  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076e1e  mov     [rbp+57h+var_78], rax
0x140076e22  lea     rax, aRenamevolumeco; "RenameVolumeConfirm_HeaderText"
0x140076e29  mov     qword ptr [rbp+57h+var_50], rax
0x140076e2d  lea     rax, aRenamevolumeco_0; "RenameVolumeConfirm_PromptText"
0x140076e34  jmp     loc_1400771D3
0x140076e39  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076e40  mov     [rbp+57h+var_78], rax
0x140076e44  lea     rax, aInitializevolu; "InitializeVolumeConfirm_HeaderText"
0x140076e4b  mov     qword ptr [rbp+57h+var_50], rax
0x140076e4f  lea     rax, aInitializevolu_0; "InitializeVolumeConfirm_PromptText"
0x140076e56  jmp     loc_1400771D3
0x140076e5b  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076e62  mov     [rbp+57h+var_78], rax
0x140076e66  lea     rax, aFormatvolumeco; "FormatVolumeConfirm_HeaderText"
0x140076e6d  mov     qword ptr [rbp+57h+var_50], rax
0x140076e71  lea     rax, aFormatvolumeco_0; "FormatVolumeConfirm_PromptText"
0x140076e78  jmp     loc_1400771D3
0x140076e7d  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076e84  mov     [rbp+57h+var_78], rax
0x140076e88  lea     rax, aInitializedisk_0; "InitializeDiskConfirm_HeaderText"
0x140076e8f  mov     qword ptr [rbp+57h+var_50], rax
0x140076e93  lea     rax, aInitializedisk; "InitializeDiskConfirm_PromptText"
0x140076e9a  jmp     loc_1400771D3
0x140076e9f  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076ea6  mov     [rbp+57h+var_78], rax
0x140076eaa  lea     rax, aResizepartitio; "ResizePartitionConfirm_HeaderText"
0x140076eb1  mov     qword ptr [rbp+57h+var_50], rax
0x140076eb5  lea     rax, aResizepartitio_0; "ResizePartitionConfirm_PromptText"
0x140076ebc  jmp     loc_1400771D3
0x140076ec1  mov     rax, cs:__imp_DeletePartitionConfirmPage_CreateInstance
0x140076ec8  mov     [rbp+57h+var_78], rax
0x140076ecc  jmp     loc_1400771D7
0x140076ed1  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076ed8  mov     [rbp+57h+var_78], rax
0x140076edc  lea     rax, aCreatevhdconfi; "CreateVhdConfirm_HeaderText"
0x140076ee3  mov     qword ptr [rbp+57h+var_50], rax
0x140076ee7  lea     rax, aCreatevhdconfi_0; "CreateVhdConfirm_PromptText"
0x140076eee  jmp     loc_1400771D3
0x140076ef3  sub     ecx, 8
0x140076ef6  jz      loc_140076FC7
0x140076efc  sub     ecx, 1
0x140076eff  jz      loc_140076FA5
0x140076f05  sub     ecx, 1
0x140076f08  jz      short loc_140076F83
0x140076f0a  sub     ecx, 1
0x140076f0d  jz      short loc_140076F61
0x140076f0f  sub     ecx, 1
0x140076f12  jz      short loc_140076F3F
0x140076f14  cmp     ecx, 1
0x140076f17  jnz     loc_14007710E
0x140076f1d  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076f24  mov     [rbp+57h+var_78], rax
0x140076f28  lea     rax, aRenamepoolconf; "RenamePoolConfirm_HeaderText"
0x140076f2f  mov     qword ptr [rbp+57h+var_50], rax
0x140076f33  lea     rax, aRenamepoolconf_0; "RenamePoolConfirm_PromptText"
0x140076f3a  jmp     loc_1400771D3
0x140076f3f  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076f46  mov     [rbp+57h+var_78], rax
0x140076f4a  lea     rax, aCreatepoolconf_0; "CreatePoolConfirm_HeaderText"
0x140076f51  mov     qword ptr [rbp+57h+var_50], rax
0x140076f55  lea     rax, aCreatepoolconf; "CreatePoolConfirm_PromptText"
0x140076f5c  jmp     loc_1400771D3
0x140076f61  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076f68  mov     [rbp+57h+var_78], rax
0x140076f6c  lea     rax, aOfflinediskcon; "OfflineDiskConfirm_HeaderText"
0x140076f73  mov     qword ptr [rbp+57h+var_50], rax
0x140076f77  lea     rax, aOfflinediskcon_0; "OfflineDiskConfirm_PromptText"
0x140076f7e  jmp     loc_1400771D3
0x140076f83  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076f8a  mov     [rbp+57h+var_78], rax
0x140076f8e  lea     rax, aOnlinediskconf; "OnlineDiskConfirm_HeaderText"
0x140076f95  mov     qword ptr [rbp+57h+var_50], rax
0x140076f99  lea     rax, aOnlinediskconf_0; "OnlineDiskConfirm_PromptText"
0x140076fa0  jmp     loc_1400771D3
0x140076fa5  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076fac  mov     [rbp+57h+var_78], rax
0x140076fb0  lea     rax, aDetachvhdconfi_0; "DetachVhdConfirm_HeaderText"
0x140076fb7  mov     qword ptr [rbp+57h+var_50], rax
0x140076fbb  lea     rax, aDetachvhdconfi; "DetachVhdConfirm_PromptText"
0x140076fc2  jmp     loc_1400771D3
0x140076fc7  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140076fce  mov     [rbp+57h+var_78], rax
0x140076fd2  lea     rax, aAttachvhdconfi; "AttachVhdConfirm_HeaderText"
0x140076fd9  mov     qword ptr [rbp+57h+var_50], rax
0x140076fdd  lea     rax, aAttachvhdconfi_0; "AttachVhdConfirm_PromptText"
0x140076fe4  jmp     loc_1400771D3
0x140076fe9  cmp     ecx, 15h
0x140076fec  jg      loc_1400770E8
0x140076ff2  sub     ecx, 0Fh
0x140076ff5  jz      loc_1400770C6
0x140076ffb  sub     ecx, 1
0x140076ffe  jz      loc_1400770A4
0x140077004  sub     ecx, 1
0x140077007  jz      short loc_140077082
0x140077009  sub     ecx, 1
0x14007700c  jz      short loc_140077060
0x14007700e  sub     ecx, 1
0x140077011  jz      short loc_14007703E
0x140077013  cmp     ecx, 1
0x140077016  jnz     loc_14007710E
0x14007701c  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140077023  mov     [rbp+57h+var_78], rax
0x140077027  lea     rax, aDeletespacecon; "DeleteSpaceConfirm_HeaderText"
0x14007702e  mov     qword ptr [rbp+57h+var_50], rax
0x140077032  lea     rax, aDeletespacecon_0; "DeleteSpaceConfirm_PromptText"
0x140077039  jmp     loc_1400771D3
0x14007703e  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140077045  mov     [rbp+57h+var_78], rax
0x140077049  lea     rax, aCreatespacecon_0; "CreateSpaceConfirm_HeaderText"
0x140077050  mov     qword ptr [rbp+57h+var_50], rax
0x140077054  lea     rax, aCreatespacecon; "CreateSpaceConfirm_PromptText"
0x14007705b  jmp     loc_1400771D3
0x140077060  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140077067  mov     [rbp+57h+var_78], rax
0x14007706b  lea     rax, aPreparepooldis; "PreparePoolDiskRemovalConfirm_HeaderTex"...
0x140077072  mov     qword ptr [rbp+57h+var_50], rax
0x140077076  lea     rax, aPreparepooldis_0; "PreparePoolDiskRemovalConfirm_PromptTex"...
0x14007707d  jmp     loc_1400771D3
0x140077082  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140077089  mov     [rbp+57h+var_78], rax
0x14007708d  lea     rax, aRemovepooldisk; "RemovePoolDisksConfirm_HeaderText"
0x140077094  mov     qword ptr [rbp+57h+var_50], rax
0x140077098  lea     rax, aRemovepooldisk_0; "RemovePoolDisksConfirm_PromptText"
0x14007709f  jmp     loc_1400771D3
0x1400770a4  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x1400770ab  mov     [rbp+57h+var_78], rax
0x1400770af  lea     rax, aAddpooldisksco; "AddPoolDisksConfirm_HeaderText"
0x1400770b6  mov     qword ptr [rbp+57h+var_50], rax
0x1400770ba  lea     rax, aAddpooldisksco_0; "AddPoolDisksConfirm_PromptText"
0x1400770c1  jmp     loc_1400771D3
0x1400770c6  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x1400770cd  mov     [rbp+57h+var_78], rax
0x1400770d1  lea     rax, aDeletepoolconf; "DeletePoolConfirm_HeaderText"
0x1400770d8  mov     qword ptr [rbp+57h+var_50], rax
0x1400770dc  lea     rax, aDeletepoolconf_0; "DeletePoolConfirm_PromptText"
0x1400770e3  jmp     loc_1400771D3
0x1400770e8  sub     ecx, 16h
0x1400770eb  jz      loc_1400771B6
0x1400770f1  sub     ecx, 1
0x1400770f4  jz      loc_140077197
0x1400770fa  sub     ecx, 1
0x1400770fd  jz      short loc_140077178
0x1400770ff  sub     ecx, 1
0x140077102  jz      short loc_140077159
0x140077104  sub     ecx, 1
0x140077107  jz      short loc_14007713A
0x140077109  cmp     ecx, 1
0x14007710c  jz      short loc_140077118
0x14007710e  mov     ebx, 80070057h
0x140077113  jmp     loc_1400772ED
0x140077118  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x14007711f  mov     [rbp+57h+var_78], rax
0x140077123  lea     rax, aUnretirediskco; "UnretireDiskConfirm_HeaderText"
0x14007712a  mov     qword ptr [rbp+57h+var_50], rax
0x14007712e  lea     rax, aUnretirediskco_0; "UnretireDiskConfirm_PromptText"
0x140077135  jmp     loc_1400771D3
0x14007713a  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140077141  mov     [rbp+57h+var_78], rax
0x140077145  lea     rax, aRemoveaccesspa_0; "RemoveAccessPathConfirm_HeaderText"
0x14007714c  mov     qword ptr [rbp+57h+var_50], rax
0x140077150  lea     rax, aRemoveaccesspa; "RemoveAccessPathConfirm_PromptText"
0x140077157  jmp     short loc_1400771D3
0x140077159  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x140077160  mov     [rbp+57h+var_78], rax
0x140077164  lea     rax, aMountvolumetop_0; "MountVolumeToPathConfirm_HeaderText"
0x14007716b  mov     qword ptr [rbp+57h+var_50], rax
0x14007716f  lea     rax, aMountvolumetop; "MountVolumeToPathConfirm_PromptText"
0x140077176  jmp     short loc_1400771D3
0x140077178  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x14007717f  mov     [rbp+57h+var_78], rax
0x140077183  lea     rax, aTriggeroptimiz; "TriggerOptimizePoolConfirm_HeaderText"
0x14007718a  mov     qword ptr [rbp+57h+var_50], rax
0x14007718e  lea     rax, aTriggeroptimiz_0; "TriggerOptimizePoolConfirm_PromptText"
0x140077195  jmp     short loc_1400771D3
0x140077197  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x14007719e  mov     [rbp+57h+var_78], rax
0x1400771a2  lea     rax, aSwitchpartitio; "SwitchPartitionStyleConfirm_HeaderText"
0x1400771a9  mov     qword ptr [rbp+57h+var_50], rax
0x1400771ad  lea     rax, aSwitchpartitio_0; "SwitchPartitionStyleConfirm_PromptText"
0x1400771b4  jmp     short loc_1400771D3
0x1400771b6  mov     rax, cs:__imp_StorageOpConfirmPage_CreateInstance
0x1400771bd  mov     [rbp+57h+var_78], rax
0x1400771c1  lea     rax, aExtendspacecon; "ExtendSpaceConfirm_HeaderText"
0x1400771c8  mov     qword ptr [rbp+57h+var_50], rax
0x1400771cc  lea     rax, aExtendspacecon_0; "ExtendSpaceConfirm_PromptText"
0x1400771d3  mov     qword ptr [rbp+57h+var_50+8], rax
0x1400771d7  mov     dword ptr [rbp+57h+var_30], 10Eh
0x1400771de  mov     ecx, 20h ; ' '; Size
0x1400771e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400771e8  mov     rdi, rax
0x1400771eb  mov     [rbp+57h+var_D0], rax
0x1400771ef  xorps   xmm0, xmm0
0x1400771f2  movups  xmmword ptr [rax], xmm0
0x1400771f5  mov     eax, 1
0x1400771fa  mov     [rdi+8], eax
0x1400771fd  mov     [rdi+0Ch], eax
0x140077200  lea     rax, ??_7?$_Ref_count_obj2@VStorageAdminOpConfirmationDialog@@@std@@6B@; const std::_Ref_count_obj2<StorageAdminOpConfirmationDialog>::`vftable'
0x140077207  mov     [rdi], rax
0x14007720a  lea     rsi, [rdi+10h]
0x14007720e  xor     eax, eax
0x140077210  mov     [rsi], rax
0x140077213  mov     [rsi+8], eax
0x140077216  mov     ebx, 80070490h
0x14007721b  mov     [rsi+4], ebx
0x14007721e  mov     [rbp+57h+var_D0], rsi
0x140077222  mov     [rbp+57h+var_C8], rdi
0x140077226  test    rsi, rsi
0x140077229  jnz     short loc_140077235
0x14007722b  mov     ebx, 8007000Eh
0x140077230  jmp     loc_1400772E4
0x140077235  lea     rdx, [rbp+57h+var_D0]
0x140077239  lea     rcx, [rbp+57h+var_C0]
0x14007723d  call    ??0?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>(std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> const &)
0x140077242  mov     rdx, rax
0x140077245  mov     rcx, [rax]
0x140077248  mov     rax, [rbp+57h+var_88]
0x14007724c  mov     [rdx], rax
0x14007724f  mov     [rbp+57h+var_88], rcx
0x140077253  mov     rcx, [rdx+8]
0x140077257  mov     rax, [rbp+57h+var_88+8]
0x14007725b  mov     [rdx+8], rax
0x14007725f  mov     [rbp+57h+var_88+8], rcx
0x140077263  mov     rcx, [rbp+57h+var_B8]; this
0x140077267  test    rcx, rcx
0x14007726a  jz      short loc_140077271
0x14007726c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140077271  lea     rax, aYes; "Yes"
0x140077278  mov     qword ptr [rbp+57h+var_40], rax
0x14007727c  lea     rax, aNo; "No"
0x140077283  mov     qword ptr [rbp+57h+var_40+8], rax
0x140077287  lea     rax, ?NotifyDialogOutcome@StorageAdminOpConfirmationDialog@@SAXPEAUStorageOpConfirmDialogOutcomeNotifyData@@@Z; StorageAdminOpConfirmationDialog::NotifyDialogOutcome(StorageOpConfirmDialogOutcomeNotifyData *)
0x14007728e  mov     [rbp+57h+var_70], rax
0x140077292  mov     [rbp+57h+var_68], rsi
0x140077296  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixVhdAndPoolModernAdminDialogHang@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixVhdAndPoolModernAdminDialogHang@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixVhdAndPoolModernAdminDialogHang> `wil::Feature<__WilFeatureTraits_Feature_FixVhdAndPoolModernAdminDialogHang>::GetImpl(void)'::`2'::impl
0x14007729d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixVhdAndPoolModernAdminDialogHang@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixVhdAndPoolModernAdminDialogHang>::__private_IsEnabled(void)
0x1400772a2  test    al, al
0x1400772a4  jnz     short loc_1400772C6
0x1400772a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AdminFlowRejuv_CreateVhdPrompt@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AdminFlowRejuv_CreateVhdPrompt@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_CreateVhdPrompt> `wil::Feature<__WilFeatureTraits_Feature_AdminFlowRejuv_CreateVhdPrompt>::GetImpl(void)'::`2'::impl
0x1400772ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AdminFlowRejuv_CreateVhdPrompt@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdminFlowRejuv_CreateVhdPrompt>::__private_IsEnabled(void)
0x1400772b2  test    al, al
0x1400772b4  jz      short loc_1400772C6
0x1400772b6  mov     dword ptr [rbp+57h+pv], 0B9h
0x1400772bd  lea     rcx, ?RunXAMLFlowWork@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; RunXAMLFlowWork(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)
0x1400772c4  jmp     short loc_1400772CD
0x1400772c6  lea     rcx, ?RunXamlPopupDialog@StorageAdminOpConfirmationDialog@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1400772cd  lea     rdx, [rbp+57h+pv]; pv
0x1400772d1  call    ?RunFlowThread@@YAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@ZPEAUTHREAD_CONTEXT@@@Z; RunFlowThread(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *),THREAD_CONTEXT *)
0x1400772d6  cmp     byte ptr [rsi+8], 0
  ... truncated ...
```
