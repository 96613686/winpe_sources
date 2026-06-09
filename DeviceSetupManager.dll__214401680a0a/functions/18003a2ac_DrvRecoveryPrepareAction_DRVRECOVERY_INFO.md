# DrvRecoveryPrepareAction(_DRVRECOVERY_INFO *)

- ea: `0x18003a2ac`
- end: `0x18003a641`
- name: `?DrvRecoveryPrepareAction@@YAHPEAU_DRVRECOVERY_INFO@@@Z`
- size: `917`
- prototype: `__int64 __fastcall(struct _DRVRECOVERY_INFO *)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800299a0`

## callees

- `0x180038fe0`
- `0x18003a2ac`
- `0x18003a648`
- `0x18003a754`
- `0x18003a7e8`
- `0x18003b940`
- `0x18003b988`
- `0x18003c2b0`
- `0x18003c374`
- `0x18003e200`
- `0x180040430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a602`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003a602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a3f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a57b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a3f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a57b`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a2e6`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a319`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a37f`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a444`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a59d`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a5d1`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a5f4`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a2e6`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a319`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a37f`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a444`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a59d`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a5d1`
- `DEVRTL!DevRtlWriteTextLog` at `0x18003a5f4`

## string_xrefs

- `0x18003a36d`: `Previous recovery attempt may have terminated unexpectedly.`
- `0x18003a588`: `Failed to write state information. Error = 0x%08X`
- `0x18003a5ba`: `Updated recovery state: %ws`

## pseudocode

```c
__int64 __fastcall DrvRecoveryPrepareAction(struct _DRVRECOVERY_INFO *a1)
{
  unsigned int v2; // r15d
  __int64 StateName; // rax
  unsigned int v4; // ebp
  int v5; // eax
  int LastError; // edi
  int v7; // esi
  int v8; // r14d
  int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v14; // [rsp+60h] [rbp+8h] BYREF

  v14 = 0;
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 196612, "{Prepare Recovery Action}");
  v2 = *((_DWORD *)a1 + 142);
  StateName = pDrvRecoveryGetStateName(v2);
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 4, "Initial recovery state: %ws", StateName);
  v4 = 1;
  if ( *((_DWORD *)a1 + 149) == 1 )
    DrvRecoveryLogBegin(a1);
  v5 = *((_DWORD *)a1 + 142);
  if ( *((_DWORD *)a1 + 138) )
  {
    LastError = v5 != 4 ? 0xBC2 : 0;
    goto LABEL_50;
  }
  v7 = 7;
  switch ( v5 )
  {
    case 4:
      v8 = 1;
      DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 2, "Previous recovery attempt may have terminated unexpectedly.");
      *((_DWORD *)a1 + 142) = 5;
      break;
    case 7:
      LastError = 0;
      goto LABEL_50;
    case 0:
      LastError = 13;
      goto LABEL_50;
    default:
      v8 = 0;
      if ( v5 == 1 )
      {
        *((_DWORD *)a1 + 142) = 2;
      }
      else if ( v5 == 6 )
      {
        *((_DWORD *)a1 + 142) = 5;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::GetImpl'::`2'::impl) )
          ++*((_DWORD *)a1 + 146);
      }
      break;
  }
  v9 = *((_DWORD *)a1 + 142);
  if ( (v9 == 2 || v9 == 9) && !(unsigned int)pDrvRecoveryInvalidateDrivers(a1)
    || !(unsigned int)pDrvRecoveryUpdateDynamicData(a1) )
  {
    goto LABEL_19;
  }
  if ( !(unsigned int)DrvUtilsUpdateInfoContainsDriverInf(*((_QWORD *)a1 + 67), 15) )
  {
    DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 4, "No driver packages to recover.");
LABEL_30:
    *((_DWORD *)a1 + 142) = v7;
    goto LABEL_45;
  }
  v7 = *((_DWORD *)a1 + 142);
  switch ( v7 )
  {
    case 3:
      goto LABEL_44;
    case 2:
      if ( (unsigned int)pDrvRecoveryCheckDriversRemovable(a1, &v14) )
      {
        v7 = v14 != 0 ? 5 : 8;
        *((_DWORD *)a1 + 142) = v7;
        break;
      }
LABEL_19:
      LastError = GetLastError();
      *((_DWORD *)a1 + 142) = 1;
      goto LABEL_50;
    case 8:
      if ( !(unsigned int)pDrvRecoveryCheckDriversRemovable(a1, &v14) )
        goto LABEL_19;
      if ( v14 )
      {
        *((_DWORD *)a1 + 142) = 5;
        v7 = 5;
      }
      else
      {
        v7 = *((_DWORD *)a1 + 142);
      }
      break;
    case 9:
      v10 = *((_DWORD *)a1 + 150);
      if ( v10 == -1 || v10 <= 2 )
      {
        *((_DWORD *)a1 + 142) = 5;
        v7 = 5;
      }
      if ( (unsigned int)(*((_DWORD *)a1 + 151) - 2) > 0xFFFFFFFC )
      {
        *((_DWORD *)a1 + 142) = 5;
        goto LABEL_28;
      }
      break;
  }
  if ( v7 != 5 )
    goto LABEL_45;
LABEL_28:
  if ( !(unsigned int)pSetupStringTableIsEmpty(*((_QWORD *)a1 + 68)) )
  {
    v7 = ++*((_DWORD *)a1 + 150) < 2u ? 3 : 8;
    goto LABEL_30;
  }
  if ( !++*((_DWORD *)a1 + 151) )
  {
    *((_DWORD *)a1 + 142) = 3;
LABEL_44:
    v7 = 3;
    goto LABEL_45;
  }
  *((_DWORD *)a1 + 142) = 9;
  v7 = 9;
LABEL_45:
  LastError = 0;
  if ( *((_DWORD *)a1 + 149) != 3 && (unsigned int)(v7 - 7) <= 2 )
  {
    DrvRecoveryLogEnd(a1, v8);
    *((_DWORD *)a1 + 149) = 3;
  }
  if ( !pDrvRecoveryWriteInfo(a1) )
  {
    LastError = GetLastError();
    DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 1, "Failed to write state information. Error = 0x%08X", LastError);
  }
LABEL_50:
  v11 = *((unsigned int *)a1 + 142);
  if ( (_DWORD)v11 != v2 )
  {
    v12 = pDrvRecoveryGetStateName(v11);
    DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 4, "Updated recovery state: %ws", v12);
  }
  DevRtlWriteTextLog(*((_QWORD *)a1 + 70), 512, 327684, "{Prepare Recovery Action - exit(0x%08X)}", LastError);
  *((_DWORD *)a1 + 139) = LastError;
  SetLastError(LastError);
  if ( LastError && LastError != 3010 )
    return 0;
  return v4;
}

```

## disassembly

```asm
0x18003a2ac  mov     [rsp+arg_8], rbx
0x18003a2b1  mov     [rsp+arg_10], rbp
0x18003a2b6  push    rsi
0x18003a2b7  push    rdi
0x18003a2b8  push    r13
0x18003a2ba  push    r14
0x18003a2bc  push    r15
0x18003a2be  sub     rsp, 30h
0x18003a2c2  mov     rbx, rcx
0x18003a2c5  mov     [rsp+58h+arg_0], 0
0x18003a2cd  mov     rcx, [rcx+230h]
0x18003a2d4  lea     r9, aPrepareRecover_0; "{Prepare Recovery Action}"
0x18003a2db  mov     edx, 200h
0x18003a2e0  mov     r8d, 30004h
0x18003a2e6  call    cs:__imp_DevRtlWriteTextLog
0x18003a2ec  mov     r15d, [rbx+238h]
0x18003a2f3  mov     ecx, r15d
0x18003a2f6  call    ?pDrvRecoveryGetStateName@@YAPEBGW4_DRIVER_RECOVERY_STATE@@@Z; pDrvRecoveryGetStateName(_DRIVER_RECOVERY_STATE)
0x18003a2fb  mov     rcx, [rbx+230h]
0x18003a302  lea     r9, aInitialRecover; "Initial recovery state: %ws"
0x18003a309  mov     edx, 200h
0x18003a30e  mov     [rsp+58h+var_38], rax
0x18003a313  mov     r8d, 4
0x18003a319  call    cs:__imp_DevRtlWriteTextLog
0x18003a31f  mov     ebp, 1
0x18003a324  cmp     [rbx+254h], ebp
0x18003a32a  jnz     short loc_18003A334
0x18003a32c  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a32f  call    ?DrvRecoveryLogBegin@@YAXPEAU_DRVRECOVERY_INFO@@@Z; DrvRecoveryLogBegin(_DRVRECOVERY_INFO *)
0x18003a334  cmp     dword ptr [rbx+228h], 0
0x18003a33b  mov     eax, [rbx+238h]
0x18003a341  jz      short loc_18003A355
0x18003a343  sub     eax, 4
0x18003a346  neg     eax
0x18003a348  sbb     edi, edi
0x18003a34a  and     edi, 0BC2h
0x18003a350  jmp     loc_18003A5A3
0x18003a355  mov     edi, 5
0x18003a35a  lea     esi, [rdi+2]
0x18003a35d  lea     r13d, [rdi-3]
0x18003a361  cmp     eax, 4
0x18003a364  jnz     short loc_18003A38D
0x18003a366  mov     rcx, [rbx+230h]
0x18003a36d  lea     r9, aPreviousRecove; "Previous recovery attempt may have term"...
0x18003a374  mov     r8d, r13d
0x18003a377  mov     edx, 200h
0x18003a37c  mov     r14d, ebp
0x18003a37f  call    cs:__imp_DevRtlWriteTextLog
0x18003a385  mov     [rbx+238h], edi
0x18003a38b  jmp     short loc_18003A3D5
0x18003a38d  cmp     eax, esi
0x18003a38f  jnz     short loc_18003A398
0x18003a391  xor     edi, edi
0x18003a393  jmp     loc_18003A5A3
0x18003a398  test    eax, eax
0x18003a39a  jnz     short loc_18003A3A4
0x18003a39c  lea     edi, [rax+0Dh]
0x18003a39f  jmp     loc_18003A5A3
0x18003a3a4  xor     r14d, r14d
0x18003a3a7  cmp     eax, ebp
0x18003a3a9  jnz     short loc_18003A3B4
0x18003a3ab  mov     [rbx+238h], r13d
0x18003a3b2  jmp     short loc_18003A3D5
0x18003a3b4  cmp     eax, 6
0x18003a3b7  jnz     short loc_18003A3D5
0x18003a3b9  mov     [rbx+238h], edi
0x18003a3bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix> `wil::Feature<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::GetImpl(void)'::`2'::impl
0x18003a3c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DriverRecovery_DataFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DriverRecovery_DataFix>::__private_IsEnabled(void)
0x18003a3cb  test    al, al
0x18003a3cd  jz      short loc_18003A3D5
0x18003a3cf  add     [rbx+248h], ebp
0x18003a3d5  mov     eax, [rbx+238h]
0x18003a3db  cmp     eax, r13d
0x18003a3de  jz      short loc_18003A3E5
0x18003a3e0  cmp     eax, 9
0x18003a3e3  jnz     short loc_18003A404
0x18003a3e5  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a3e8  call    ?pDrvRecoveryInvalidateDrivers@@YAHPEAU_DRVRECOVERY_INFO@@@Z; pDrvRecoveryInvalidateDrivers(_DRVRECOVERY_INFO *)
0x18003a3ed  test    eax, eax
0x18003a3ef  jnz     short loc_18003A404
0x18003a3f1  call    cs:__imp_GetLastError
0x18003a3f7  mov     edi, eax
0x18003a3f9  mov     [rbx+238h], ebp
0x18003a3ff  jmp     loc_18003A5A3
0x18003a404  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a407  call    ?pDrvRecoveryUpdateDynamicData@@YAHPEAU_DRVRECOVERY_INFO@@@Z; pDrvRecoveryUpdateDynamicData(_DRVRECOVERY_INFO *)
0x18003a40c  test    eax, eax
0x18003a40e  jz      short loc_18003A3F1
0x18003a410  mov     rcx, [rbx+218h]
0x18003a417  xor     r8d, r8d
0x18003a41a  lea     edx, [r8+0Fh]
0x18003a41e  call    DrvUtilsUpdateInfoContainsDriverInf
0x18003a423  mov     r13d, 3
0x18003a429  test    eax, eax
0x18003a42b  jnz     short loc_18003A44C
0x18003a42d  mov     rcx, [rbx+230h]
0x18003a434  lea     r9, aNoDriverPackag; "No driver packages to recover."
0x18003a43b  mov     edx, 200h
0x18003a440  lea     r8d, [r13+1]
0x18003a444  call    cs:__imp_DevRtlWriteTextLog
0x18003a44a  jmp     short loc_18003A4B6
0x18003a44c  mov     esi, [rbx+238h]
0x18003a452  cmp     esi, r13d
0x18003a455  jz      loc_18003A547
0x18003a45b  cmp     esi, 2
0x18003a45e  jnz     short loc_18003A4C1
0x18003a460  lea     rdx, [rsp+58h+arg_0]; int *
0x18003a465  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a468  call    ?pDrvRecoveryCheckDriversRemovable@@YAHPEAU_DRVRECOVERY_INFO@@PEAH@Z; pDrvRecoveryCheckDriversRemovable(_DRVRECOVERY_INFO *,int *)
0x18003a46d  test    eax, eax
0x18003a46f  jz      short loc_18003A3F1
0x18003a471  mov     eax, [rsp+58h+arg_0]
0x18003a475  neg     eax
0x18003a477  sbb     esi, esi
0x18003a479  and     esi, 0FFFFFFFDh
0x18003a47c  add     esi, 8
0x18003a47f  mov     [rbx+238h], esi
0x18003a485  cmp     esi, edi
0x18003a487  jnz     loc_18003A54A
0x18003a48d  mov     rcx, [rbx+220h]
0x18003a494  call    pSetupStringTableIsEmpty
0x18003a499  test    eax, eax
0x18003a49b  jnz     loc_18003A52E
0x18003a4a1  add     [rbx+258h], ebp
0x18003a4a7  cmp     dword ptr [rbx+258h], 2
0x18003a4ae  sbb     esi, esi
0x18003a4b0  and     esi, 0FFFFFFFBh
0x18003a4b3  add     esi, 8
0x18003a4b6  mov     [rbx+238h], esi
0x18003a4bc  jmp     loc_18003A54A
0x18003a4c1  cmp     esi, 8
0x18003a4c4  jnz     short loc_18003A4F4
0x18003a4c6  lea     rdx, [rsp+58h+arg_0]; int *
0x18003a4cb  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a4ce  call    ?pDrvRecoveryCheckDriversRemovable@@YAHPEAU_DRVRECOVERY_INFO@@PEAH@Z; pDrvRecoveryCheckDriversRemovable(_DRVRECOVERY_INFO *,int *)
0x18003a4d3  test    eax, eax
0x18003a4d5  jz      loc_18003A3F1
0x18003a4db  cmp     [rsp+58h+arg_0], 0
0x18003a4e0  jz      short loc_18003A4EC
0x18003a4e2  mov     [rbx+238h], edi
0x18003a4e8  mov     esi, edi
0x18003a4ea  jmp     short loc_18003A485
0x18003a4ec  mov     esi, [rbx+238h]
0x18003a4f2  jmp     short loc_18003A485
0x18003a4f4  cmp     esi, 9
0x18003a4f7  jnz     short loc_18003A485
0x18003a4f9  mov     eax, [rbx+258h]
0x18003a4ff  cmp     eax, 0FFFFFFFFh
0x18003a502  jz      short loc_18003A509
0x18003a504  cmp     eax, 2
0x18003a507  ja      short loc_18003A511
0x18003a509  mov     [rbx+238h], edi
0x18003a50f  mov     esi, edi
0x18003a511  mov     eax, [rbx+25Ch]
0x18003a517  sub     eax, 2
0x18003a51a  cmp     eax, 0FFFFFFFCh
0x18003a51d  jbe     loc_18003A485
0x18003a523  mov     [rbx+238h], edi
0x18003a529  jmp     loc_18003A48D
0x18003a52e  add     [rbx+25Ch], ebp
0x18003a534  cmp     [rbx+25Ch], ebp
0x18003a53a  jnb     loc_18003A62F
0x18003a540  mov     [rbx+238h], r13d
0x18003a547  mov     esi, r13d
0x18003a54a  xor     edi, edi
0x18003a54c  cmp     [rbx+254h], r13d
0x18003a553  jz      short loc_18003A56F
0x18003a555  lea     eax, [rsi-7]
0x18003a558  cmp     eax, 2
0x18003a55b  ja      short loc_18003A56F
0x18003a55d  mov     edx, r14d; int
0x18003a560  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a563  call    ?DrvRecoveryLogEnd@@YAXPEAU_DRVRECOVERY_INFO@@H@Z; DrvRecoveryLogEnd(_DRVRECOVERY_INFO *,int)
0x18003a568  mov     [rbx+254h], r13d
0x18003a56f  mov     rcx, rbx; struct _DRVRECOVERY_INFO *
0x18003a572  call    ?pDrvRecoveryWriteInfo@@YAHPEAU_DRVRECOVERY_INFO@@@Z; pDrvRecoveryWriteInfo(_DRVRECOVERY_INFO *)
0x18003a577  test    eax, eax
0x18003a579  jnz     short loc_18003A5A3
0x18003a57b  call    cs:__imp_GetLastError
0x18003a581  mov     rcx, [rbx+230h]
0x18003a588  lea     r9, aFailedToWriteS; "Failed to write state information. Erro"...
0x18003a58f  mov     r8d, ebp
0x18003a592  mov     dword ptr [rsp+58h+var_38], eax
0x18003a596  mov     edx, 200h
0x18003a59b  mov     edi, eax
0x18003a59d  call    cs:__imp_DevRtlWriteTextLog
0x18003a5a3  mov     ecx, [rbx+238h]
0x18003a5a9  cmp     ecx, r15d
0x18003a5ac  jz      short loc_18003A5D7
0x18003a5ae  call    ?pDrvRecoveryGetStateName@@YAPEBGW4_DRIVER_RECOVERY_STATE@@@Z; pDrvRecoveryGetStateName(_DRIVER_RECOVERY_STATE)
0x18003a5b3  mov     rcx, [rbx+230h]
0x18003a5ba  lea     r9, aUpdatedRecover; "Updated recovery state: %ws"
0x18003a5c1  mov     edx, 200h
0x18003a5c6  mov     [rsp+58h+var_38], rax
0x18003a5cb  mov     r8d, 4
0x18003a5d1  call    cs:__imp_DevRtlWriteTextLog
0x18003a5d7  mov     rcx, [rbx+230h]
0x18003a5de  lea     r9, aPrepareRecover; "{Prepare Recovery Action - exit(0x%08X)"...
0x18003a5e5  mov     edx, 200h
0x18003a5ea  mov     dword ptr [rsp+58h+var_38], edi
0x18003a5ee  mov     r8d, 50004h
0x18003a5f4  call    cs:__imp_DevRtlWriteTextLog
0x18003a5fa  mov     ecx, edi; dwErrCode
0x18003a5fc  mov     [rbx+22Ch], edi
0x18003a602  call    cs:__imp_SetLastError
0x18003a608  test    edi, edi
0x18003a60a  jz      short loc_18003A616
0x18003a60c  cmp     edi, 0BC2h
0x18003a612  jz      short loc_18003A616
0x18003a614  xor     ebp, ebp
0x18003a616  mov     rbx, [rsp+58h+arg_8]
0x18003a61b  mov     eax, ebp
0x18003a61d  mov     rbp, [rsp+58h+arg_10]
0x18003a622  add     rsp, 30h
0x18003a626  pop     r15
0x18003a628  pop     r14
0x18003a62a  pop     r13
0x18003a62c  pop     rdi
0x18003a62d  pop     rsi
0x18003a62e  retn
0x18003a62f  mov     eax, 9
0x18003a634  mov     [rbx+238h], eax
0x18003a63a  mov     esi, eax
0x18003a63c  jmp     loc_18003A54A
```
