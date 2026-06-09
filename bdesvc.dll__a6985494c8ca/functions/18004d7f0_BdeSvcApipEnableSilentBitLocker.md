# BdeSvcApipEnableSilentBitLocker

- ea: `0x18004d7f0`
- end: `0x18004e61a`
- name: `BdeSvcApipEnableSilentBitLocker`
- size: `3626`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180001fe8`
- `0x1800027c8`
- `0x180009f30`
- `0x180009f60`
- `0x18000daf8`
- `0x18000dc4c`
- `0x180020650`
- `0x180024468`
- `0x1800250a0`
- `0x18002a2e0`
- `0x18002a774`
- `0x180031f68`
- `0x180034070`
- `0x180034d1c`
- `0x18003a490`
- `0x18003a600`
- `0x18003a6b8`
- `0x18003a88c`
- `0x180048978`
- `0x180048a94`
- `0x18004a384`
- `0x18004b5f0`
- `0x18004b698`
- `0x18004d7f0`
- `0x180069a28`
- `0x18006b2e8`
- `0x18006c210`
- `0x18006f774`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18004d929`
- `RPCRT4!RpcImpersonateClient` at `0x18004d929`
- `RPCRT4!RpcRevertToSelf` at `0x18004dab9`
- `RPCRT4!RpcRevertToSelf` at `0x18004e596`
- `RPCRT4!RpcRevertToSelf` at `0x18004dab9`
- `RPCRT4!RpcRevertToSelf` at `0x18004e596`
- `FVEAPI!FveCheckTpmCapability` at `0x18004de87`
- `FVEAPI!FveCheckTpmCapability` at `0x18004de87`
- `FVEAPI!FveSetAllowKeyExport` at `0x18004dc52`
- `FVEAPI!FveSetAllowKeyExport` at `0x18004e271`
- `FVEAPI!FveSetAllowKeyExport` at `0x18004dc52`
- `FVEAPI!FveSetAllowKeyExport` at `0x18004e271`
- `FVEAPI!FveOpenVolumeW` at `0x18004db9a`
- `FVEAPI!FveOpenVolumeW` at `0x18004df89`
- `FVEAPI!FveOpenVolumeW` at `0x18004db9a`
- `FVEAPI!FveOpenVolumeW` at `0x18004df89`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18004e145`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18004e343`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18004e145`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18004e343`
- `FVEAPI!FveCloseVolume` at `0x18004df68`
- `FVEAPI!FveCloseVolume` at `0x18004e03e`
- `FVEAPI!FveCloseVolume` at `0x18004e118`
- `FVEAPI!FveCloseVolume` at `0x18004e315`
- `FVEAPI!FveCloseVolume` at `0x18004e42c`
- `FVEAPI!FveCloseVolume` at `0x18004df68`
- `FVEAPI!FveCloseVolume` at `0x18004e03e`
- `FVEAPI!FveCloseVolume` at `0x18004e118`
- `FVEAPI!FveCloseVolume` at `0x18004e315`
- `FVEAPI!FveCloseVolume` at `0x18004e42c`
- `FVEAPI!FveFindNextVolume` at `0x18004e221`
- `FVEAPI!FveFindNextVolume` at `0x18004e221`
- `FVEAPI!FveFindFirstVolume` at `0x18004e0ed`
- `FVEAPI!FveFindFirstVolume` at `0x18004e0ed`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18004d8ca`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18004d8ca`

## string_xrefs

- `0x18004e190`: `,FveOpenVolumeByHandle(R):`
- `0x18004e38a`: `,FveOpenVolumeByHandle(W):`

## pseudocode

```c
__int64 BdeSvcApipEnableSilentBitLocker()
{
  char v0; // r15
  bool v1; // r13
  bool v2; // bl
  char v3; // r14
  char v4; // di
  int v5; // r12d
  int PolicyInt; // esi
  PVOID *v7; // rcx
  unsigned int v8; // esi
  __int64 v9; // rdx
  int updated; // eax
  unsigned int v11; // esi
  unsigned int WinReConfiguration; // eax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  unsigned int EncryptableVolumeNamesForBcdDevices; // eax
  int v18; // ebx
  int v19; // edi
  int v20; // eax
  unsigned int v21; // ebx
  const wchar_t *v22; // rdx
  __int64 v23; // rax
  const void *v24; // r9
  unsigned __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rdi
  _QWORD *v28; // rbx
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // eax
  unsigned int v34; // ebx
  int v35; // eax
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // r9
  const unsigned __int16 *v39; // rax
  unsigned int v40; // eax
  __int64 v42; // [rsp+20h] [rbp-F0h]
  bool v43; // [rsp+90h] [rbp-80h] BYREF
  bool v44; // [rsp+91h] [rbp-7Fh] BYREF
  bool v45; // [rsp+92h] [rbp-7Eh] BYREF
  bool v46; // [rsp+93h] [rbp-7Dh] BYREF
  bool v47; // [rsp+94h] [rbp-7Ch] BYREF
  char v48; // [rsp+95h] [rbp-7Bh]
  int v49; // [rsp+98h] [rbp-78h] BYREF
  char v50; // [rsp+9Ch] [rbp-74h] BYREF
  char v51; // [rsp+9Dh] [rbp-73h] BYREF
  char v52[2]; // [rsp+9Eh] [rbp-72h] BYREF
  int v53; // [rsp+A0h] [rbp-70h] BYREF
  unsigned int v54; // [rsp+A4h] [rbp-6Ch] BYREF
  int v55; // [rsp+A8h] [rbp-68h] BYREF
  int v56; // [rsp+ACh] [rbp-64h] BYREF
  _BYTE v57[32]; // [rsp+B0h] [rbp-60h] BYREF
  const unsigned __int16 *v58; // [rsp+D0h] [rbp-40h] BYREF
  _BYTE v59[32]; // [rsp+D8h] [rbp-38h] BYREF
  void *v60; // [rsp+F8h] [rbp-18h] BYREF
  struct PathBuffer *v61; // [rsp+100h] [rbp-10h] BYREF
  _QWORD Src[2]; // [rsp+108h] [rbp-8h] BYREF
  __int64 v63; // [rsp+118h] [rbp+8h]
  unsigned __int64 v64; // [rsp+120h] [rbp+10h]
  int v65; // [rsp+128h] [rbp+18h] BYREF
  unsigned int v66; // [rsp+12Ch] [rbp+1Ch] BYREF
  unsigned __int64 v67; // [rsp+130h] [rbp+20h] BYREF
  void **v68; // [rsp+138h] [rbp+28h] BYREF
  __int64 v69; // [rsp+140h] [rbp+30h] BYREF
  __int128 v70; // [rsp+148h] [rbp+38h] BYREF
  _BYTE v71[528]; // [rsp+160h] [rbp+50h] BYREF

  v60 = (void *)-1LL;
  v43 = 0;
  v44 = 0;
  v67 = 0;
  v68 = &Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable';
  v0 = 0;
  v69 = 0;
  v70 = 0;
  v1 = 0;
  v61 = 0;
  v2 = 0;
  v66 = 0;
  v3 = 0;
  v54 = 0;
  v4 = 0;
  v65 = 0;
  v47 = 1;
  std::wstring::wstring(Src, &dword_180086574);
  v53 = 0;
  v5 = 0;
  v49 = 0;
  v45 = 0;
  v48 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 344, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  PolicyInt = PolicyManager_GetPolicyInt(L"BitLocker", L"AllowStandardUserEncryption", &v65);
  if ( PolicyInt )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    v46 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        345,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        (unsigned int)PolicyInt);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( PolicyInt < 0 )
      goto LABEL_147;
  }
  v46 = v65 != 0;
  v8 = RpcImpersonateClient(0);
  if ( v8 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 346, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v8);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    PolicyInt = v8 | 0x80010000;
    if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 0x40) == 0 )
      goto LABEL_147;
    v9 = 347;
    goto LABEL_16;
  }
  v48 = 1;
  PolicyInt = CheckIsStandardUser(&v45);
  if ( PolicyInt )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        348,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        (unsigned int)PolicyInt);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( PolicyInt < 0 )
      goto LABEL_147;
  }
  else
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v53 = 1;
  if ( v45 && !v46 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 )
      WPP_SF_(v7[2], 349, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
    updated = UpdateBitLockerStatusReg(2, 2147942450LL);
    if ( updated < 0 )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_34;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        350,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        (unsigned int)updated);
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_34:
    PolicyInt = -2147024846;
    if ( v7 == &WPP_GLOBAL_Control )
      goto LABEL_150;
    if ( (*((_BYTE *)v7 + 28) & 0x40) == 0 )
      goto LABEL_147;
    v9 = 351;
    goto LABEL_16;
  }
  v11 = RpcRevertToSelf();
  if ( !v11 )
  {
    v48 = 0;
    DeleteBitLockerStatusReg(2);
    PolicyInt = NgscbGetOSVolume(v71);
    if ( PolicyInt )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          354,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          (unsigned int)PolicyInt);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( PolicyInt < 0 )
        goto LABEL_147;
    }
    PolicyInt = FveOpenVolumeW(v71, 0, &v60);
    if ( PolicyInt )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          355,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          (unsigned int)PolicyInt);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( PolicyInt < 0 )
        goto LABEL_147;
    }
    PolicyInt = CFveApiWrapper::GetStatusFlags(v60, &v54);
    if ( PolicyInt )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          356,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          (unsigned int)PolicyInt);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( PolicyInt < 0 )
        goto LABEL_147;
    }
    PolicyInt = FveSetAllowKeyExport(1);
    if ( PolicyInt )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          357,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          (unsigned int)PolicyInt);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( PolicyInt < 0 )
        goto LABEL_147;
    }
    if ( (v54 & 0x401) != 1 )
    {
      WinReConfiguration = NgscbGetWinReConfiguration(&v44, 0, 0);
      PolicyInt = WinReConfiguration;
      if ( WinReConfiguration )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            358,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            WinReConfiguration);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( PolicyInt < 0 )
        {
          v1 = v44;
          goto LABEL_147;
        }
      }
      v1 = v44;
      v2 = 1;
      if ( !v44 )
      {
        v13 = UpdateBitLockerStatusReg(3, 2150695111LL);
        if ( v13 < 0 )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_77;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            359,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v13);
        }
        v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_77:
        PolicyInt = -2144272185;
        if ( v7 == &WPP_GLOBAL_Control )
          goto LABEL_150;
        if ( (*((_BYTE *)v7 + 28) & 0x40) == 0 )
          goto LABEL_147;
        v9 = 360;
        goto LABEL_16;
      }
      DeleteBitLockerStatusReg(3);
      PolicyInt = NgscbCheckIsTpmUnavailableForEnvironment(&v43);
      if ( PolicyInt )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            361,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)PolicyInt);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( PolicyInt < 0 )
          goto LABEL_147;
      }
      v4 = 1;
      if ( v43 )
      {
        v14 = UpdateBitLockerStatusReg(4, 2147943568LL);
        if ( v14 < 0 )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_91;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            362,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v14);
        }
        v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_91:
        PolicyInt = -2147023728;
        if ( v7 == &WPP_GLOBAL_Control )
          goto LABEL_150;
        if ( (*((_BYTE *)v7 + 28) & 0x40) == 0 )
          goto LABEL_147;
        v9 = 363;
        goto LABEL_16;
      }
      DeleteBitLockerStatusReg(4);
      v70 = 0x100000010uLL;
      PolicyInt = FveCheckTpmCapability(&v70);
      if ( PolicyInt )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            364,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)PolicyInt);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( PolicyInt < 0 )
          goto LABEL_147;
      }
      PolicyInt = DWORD2(v70);
      v3 = 1;
      if ( SDWORD2(v70) < 0 )
      {
        v15 = UpdateBitLockerStatusReg(5, DWORD2(v70));
        if ( v15 < 0 )
        {
          v7 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_105;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            365,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v15);
        }
        v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_105:
        if ( v7 == &WPP_GLOBAL_Control )
          goto LABEL_150;
        if ( (*((_BYTE *)v7 + 28) & 0x40) == 0 )
          goto LABEL_147;
        v9 = 366;
        goto LABEL_16;
      }
      DeleteBitLockerStatusReg(5);
      v0 = 1;
      if ( v60 != (void *)-1LL )
      {
        FveCloseVolume(v60);
        v60 = (void *)-1LL;
      }
      PolicyInt = FveOpenVolumeW(v71, 1, &v60);
      if ( PolicyInt )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            367,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)PolicyInt);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( PolicyInt < 0 )
          goto LABEL_147;
      }
      PolicyInt = TurnOnBitLocker(v60, 0);
      if ( PolicyInt )
      {
        v7 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            368,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)PolicyInt);
          v7 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( PolicyInt < 0 )
          goto LABEL_147;
      }
    }
    FveCloseVolume(v60);
    v60 = (void *)-1LL;
    LOBYTE(v16) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives>::GetImpl'::`2'::impl,
      v16);
    EncryptableVolumeNamesForBcdDevices = FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(&v61, &v66);
    PolicyInt = EncryptableVolumeNamesForBcdDevices;
    if ( EncryptableVolumeNamesForBcdDevices )
    {
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          370,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          EncryptableVolumeNamesForBcdDevices);
        v7 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( PolicyInt < 0 )
      {
        v53 = 2;
        v3 = v0;
        v4 = v0;
        v2 = v0;
        goto LABEL_147;
      }
    }
    v67 = 0xFFFFFFFF00000001uLL;
    v53 = 3;
    Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v68);
    if ( (int)FveFindFirstVolume(&v69, &v67) < 0 )
    {
LABEL_145:
      v2 = v0;
      v4 = v0;
      v3 = v0;
      goto LABEL_146;
    }
    v18 = 0;
    while ( 1 )
    {
      v19 = v18;
      v49 = v18 + 1;
      if ( v60 != (void *)-1LL )
      {
        FveCloseVolume(v60);
        v60 = (void *)-1LL;
      }
      LODWORD(v42) = 0;
      v20 = FveOpenVolumeByHandle(v69, 0, 0, 0xFFFFFFFFLL, v42, &v60);
      v21 = v20;
      if ( v20 < 0 )
        break;
      v29 = IsFDVEncryptableForSilentBitLocker(v60, v61, v66, &v47);
      v30 = v29;
      if ( v29 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            372,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v29);
        std::_Integral_to_string<unsigned short,long>(v57, v30);
        v22 = L",IsFDVEncryptableForSilentBitLocker:";
        goto LABEL_135;
      }
      if ( !v47 )
      {
        v18 = v19;
        v49 = v19;
        goto LABEL_144;
      }
      if ( v60 != (void *)-1LL )
      {
        FveCloseVolume(v60);
        v60 = (void *)-1LL;
      }
      LODWORD(v42) = 0;
      v31 = FveOpenVolumeByHandle(v69, 0, 1, 0xFFFFFFFFLL, v42, &v60);
      v32 = v31;
      if ( v31 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            373,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v31);
        std::_Integral_to_string<unsigned short,long>(v57, v32);
        v22 = L",FveOpenVolumeByHandle(W):";
        goto LABEL_135;
      }
      v33 = TurnOnBitLocker(v60, 1);
      v34 = v33;
      if ( v33 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            374,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            (unsigned int)v33);
        BdeSvcLogFailedSilentEncryption(v34);
        std::_Integral_to_string<unsigned short,long>(v57, v34);
        v22 = L",TurnOnBitLocker:";
        goto LABEL_135;
      }
LABEL_143:
      v18 = v49;
LABEL_144:
      if ( (int)FveFindNextVolume(v69, &v67) < 0 )
        goto LABEL_145;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        371,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        (unsigned int)v20);
    std::_Integral_to_string<unsigned short,long>(v57, v21);
    v22 = L",FveOpenVolumeByHandle(R):";
LABEL_135:
    v23 = std::operator+<unsigned short>(v59, v22, v57);
    v24 = (const void *)v23;
    v25 = *(_QWORD *)(v23 + 16);
    if ( *(_QWORD *)(v23 + 24) > 7u )
      v24 = *(const void **)v23;
    v26 = v63;
    if ( v25 > v64 - v63 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
        Src,
        v25);
    }
    else
    {
      v27 = v63 + v25;
      v63 += v25;
      v28 = Src;
      if ( v64 > 7 )
        v28 = (_QWORD *)Src[0];
      memmove_0((char *)v28 + 2 * v26, v24, 2 * v25);
      *((_WORD *)v28 + v27) = 0;
    }
    std::wstring::~wstring((__int64)v59);
    std::wstring::~wstring((__int64)v57);
    ++v5;
    goto LABEL_143;
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 352, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v11);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  PolicyInt = v11 | 0x80010000;
  if ( v7 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v7 + 28) & 0x40) != 0 )
    {
      v9 = 353;
LABEL_16:
      WPP_SF_d(v7[2], v9, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)PolicyInt);
LABEL_146:
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_147:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
      WPP_SF_d(v7[2], 375, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)PolicyInt);
  }
LABEL_150:
  FveSetAllowKeyExport(0);
  if ( PolicyInt < 0 )
  {
    if ( !v2 || v1 )
    {
      if ( v4 && v43 || v3 && !v0 )
        BdeSvcLogSilentEncryptionTPMFailure(PolicyInt);
      else
        BdeSvcLogFailedSilentEncryption(PolicyInt);
    }
    else
    {
      BdeSvcLogSilentEncryptionWinReFailure(PolicyInt);
    }
  }
  if ( v60 != (void *)-1LL )
  {
    FveCloseVolume(v60);
    v60 = (void *)-1LL;
  }
  if ( PolicyInt >= 0 && !v5 )
  {
    v35 = DeleteAllBitLockerStatusReg();
    if ( v35 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        376,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        (unsigned int)v35);
  }
  if ( (unsigned int)dword_18009A348 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A348, 0x400000000000LL) )
  {
    v39 = (const unsigned __int16 *)Src;
    if ( v64 > 7 )
      v39 = (const unsigned __int16 *)Src[0];
    v58 = v39;
    v56 = v65;
    v54 = PolicyInt;
    v55 = v5;
    v47 = v1;
    v44 = v2;
    v50 = v0;
    v51 = v3;
    v52[0] = v4;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v36,
      (int)&word_18008D9A6,
      v37,
      v38,
      (__int64)&v56,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)v52,
      (__int64)&v43,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v44,
      (__int64)&v47,
      (__int64)&v53,
      &v58,
      (__int64)&v49,
      (__int64)&v55,
      (__int64)&v54);
  }
  if ( v48 == 1 )
  {
    v40 = RpcRevertToSelf();
    if ( v40 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 377, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v40);
    }
  }
  std::wstring::~wstring((__int64)Src);
  v68 = &Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v68);
  return (unsigned int)PolicyInt;
}

```

## disassembly

```asm
0x18004d7f0  push    rbp
0x18004d7f2  push    rbx
0x18004d7f3  push    rsi
0x18004d7f4  push    rdi
0x18004d7f5  push    r12
0x18004d7f7  push    r13
0x18004d7f9  push    r14
0x18004d7fb  push    r15
0x18004d7fd  lea     rbp, [rsp-278h]
0x18004d805  sub     rsp, 388h
0x18004d80c  mov     rax, cs:__security_cookie
0x18004d813  xor     rax, rsp
0x18004d816  mov     [rbp+2B0h+var_50], rax
0x18004d81d  xor     esi, esi
0x18004d81f  mov     [rbp+2B0h+var_2C8], 0FFFFFFFFFFFFFFFFh
0x18004d827  xorps   xmm0, xmm0
0x18004d82a  mov     [rbp+2B0h+var_330], sil
0x18004d82e  lea     rax, ??_7?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable'
0x18004d835  mov     [rbp+2B0h+var_32F], sil
0x18004d839  lea     rdx, dword_180086574
0x18004d840  mov     [rbp+2B0h+var_290], rsi
0x18004d844  lea     rcx, [rbp+2B0h+Src]
0x18004d848  mov     [rbp+2B0h+var_288], rax
0x18004d84c  mov     r15b, sil
0x18004d84f  mov     [rbp+2B0h+var_280], rsi
0x18004d853  movups  [rbp+2B0h+var_278], xmm0
0x18004d857  mov     r13b, sil
0x18004d85a  mov     [rbp+2B0h+var_2C0], rsi
0x18004d85e  mov     bl, sil
0x18004d861  mov     [rbp+2B0h+var_294], esi
0x18004d864  mov     r14b, sil
0x18004d867  mov     [rbp+2B0h+var_31C], esi
0x18004d86a  mov     dil, sil
0x18004d86d  mov     [rbp+2B0h+var_298], esi
0x18004d870  mov     [rbp+2B0h+var_32C], 1
0x18004d874  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004d879  mov     [rbp+2B0h+var_320], esi
0x18004d87c  mov     r12d, esi
0x18004d87f  mov     [rbp+2B0h+var_328], esi
0x18004d882  mov     [rbp+2B0h+var_32E], sil
0x18004d886  mov     [rbp+2B0h+var_32B], sil
0x18004d88a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d891  lea     rax, WPP_GLOBAL_Control
0x18004d898  cmp     rcx, rax
0x18004d89b  jz      short loc_18004D8B8
0x18004d89d  test    byte ptr [rcx+1Ch], 20h
0x18004d8a1  jz      short loc_18004D8B8
0x18004d8a3  mov     rcx, [rcx+10h]
0x18004d8a7  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004d8ae  mov     edx, 158h
0x18004d8b3  call    WPP_SF_
0x18004d8b8  lea     r8, [rbp+2B0h+var_298]
0x18004d8bc  lea     rdx, aAllowstandardu; "AllowStandardUserEncryption"
0x18004d8c3  lea     rcx, aBitlocker; "BitLocker"
0x18004d8ca  call    cs:__imp_PolicyManager_GetPolicyInt
0x18004d8d1  nop     dword ptr [rax+rax+00h]
0x18004d8d6  mov     esi, eax
0x18004d8d8  test    eax, eax
0x18004d8da  jz      short loc_18004D91F
0x18004d8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d8e3  lea     rax, WPP_GLOBAL_Control
0x18004d8ea  mov     [rbp+2B0h+var_32D], bl
0x18004d8ed  cmp     rcx, rax
0x18004d8f0  jz      short loc_18004D917
0x18004d8f2  test    byte ptr [rcx+1Ch], 40h
0x18004d8f6  jz      short loc_18004D917
0x18004d8f8  mov     rcx, [rcx+10h]
0x18004d8fc  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004d903  mov     edx, 159h
0x18004d908  mov     r9d, esi
0x18004d90b  call    WPP_SF_d
0x18004d910  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d917  test    esi, esi
0x18004d919  js      loc_18004E245
0x18004d91f  cmp     [rbp+2B0h+var_298], r12d
0x18004d923  setnz   [rbp+2B0h+var_32D]
0x18004d927  xor     ecx, ecx; BindingHandle
0x18004d929  call    cs:__imp_RpcImpersonateClient
0x18004d930  nop     dword ptr [rax+rax+00h]
0x18004d935  mov     esi, eax
0x18004d937  test    eax, eax
0x18004d939  jz      short loc_18004D9B0
0x18004d93b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d942  lea     rax, WPP_GLOBAL_Control
0x18004d949  cmp     rcx, rax
0x18004d94c  jz      short loc_18004D97A
0x18004d94e  test    byte ptr [rcx+1Ch], 2
0x18004d952  jz      short loc_18004D97A
0x18004d954  mov     rcx, [rcx+10h]
0x18004d958  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004d95f  mov     edx, 15Ah
0x18004d964  mov     r9d, esi
0x18004d967  call    WPP_SF_d
0x18004d96c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d973  lea     rax, WPP_GLOBAL_Control
0x18004d97a  or      esi, 80010000h
0x18004d980  cmp     rcx, rax
0x18004d983  jz      loc_18004E245
0x18004d989  test    byte ptr [rcx+1Ch], 40h
0x18004d98d  jz      loc_18004E245
0x18004d993  mov     edx, 15Bh
0x18004d998  mov     rcx, [rcx+10h]
0x18004d99c  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004d9a3  mov     r9d, esi
0x18004d9a6  call    WPP_SF_d
0x18004d9ab  jmp     loc_18004E23E
0x18004d9b0  lea     rcx, [rbp+2B0h+var_32E]; bool *
0x18004d9b4  mov     [rbp+2B0h+var_32B], 1
0x18004d9b8  call    ?CheckIsStandardUser@@YAJPEA_N@Z; CheckIsStandardUser(bool *)
0x18004d9bd  mov     esi, eax
0x18004d9bf  test    eax, eax
0x18004d9c1  jz      short loc_18004DA04
0x18004d9c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d9ca  lea     rax, WPP_GLOBAL_Control
0x18004d9d1  cmp     rcx, rax
0x18004d9d4  jz      short loc_18004D9FB
0x18004d9d6  test    byte ptr [rcx+1Ch], 40h
0x18004d9da  jz      short loc_18004D9FB
0x18004d9dc  mov     rcx, [rcx+10h]
0x18004d9e0  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004d9e7  mov     edx, 15Ch
0x18004d9ec  mov     r9d, esi
0x18004d9ef  call    WPP_SF_d
0x18004d9f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d9fb  test    esi, esi
0x18004d9fd  jns     short loc_18004DA0B
0x18004d9ff  jmp     loc_18004E245
0x18004da04  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da0b  cmp     [rbp+2B0h+var_32E], 1
0x18004da0f  mov     [rbp+2B0h+var_320], 1
0x18004da16  jnz     loc_18004DAB9
0x18004da1c  cmp     [rbp+2B0h+var_32D], bl
0x18004da1f  jnz     loc_18004DAB9
0x18004da25  lea     rsi, WPP_GLOBAL_Control
0x18004da2c  cmp     rcx, rsi
0x18004da2f  jz      short loc_18004DA4C
0x18004da31  test    byte ptr [rcx+1Ch], 2
0x18004da35  jz      short loc_18004DA4C
0x18004da37  mov     rcx, [rcx+10h]
0x18004da3b  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004da42  mov     edx, 15Dh
0x18004da47  call    WPP_SF_
0x18004da4c  mov     edx, 80070032h
0x18004da51  mov     ecx, 2
0x18004da56  call    ?UpdateBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@K@Z; UpdateBitLockerStatusReg(BITLOCKER_CSP_STATUS,ulong)
0x18004da5b  test    eax, eax
0x18004da5d  jns     short loc_18004DA89
0x18004da5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da66  cmp     rcx, rsi
0x18004da69  jz      short loc_18004DA90
0x18004da6b  test    byte ptr [rcx+1Ch], 2
0x18004da6f  jz      short loc_18004DA90
0x18004da71  mov     rcx, [rcx+10h]
0x18004da75  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004da7c  mov     edx, 15Eh
0x18004da81  mov     r9d, eax
0x18004da84  call    WPP_SF_d
0x18004da89  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da90  lea     rax, WPP_GLOBAL_Control
0x18004da97  mov     esi, 80070032h
0x18004da9c  cmp     rcx, rax
0x18004da9f  jz      loc_18004E26F
0x18004daa5  test    byte ptr [rcx+1Ch], 40h
0x18004daa9  jz      loc_18004E24C
0x18004daaf  mov     edx, 15Fh
0x18004dab4  jmp     loc_18004D998
0x18004dab9  call    cs:__imp_RpcRevertToSelf
0x18004dac0  nop     dword ptr [rax+rax+00h]
0x18004dac5  mov     esi, eax
0x18004dac7  test    eax, eax
0x18004dac9  jz      short loc_18004DB2D
0x18004dacb  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dad2  lea     rax, WPP_GLOBAL_Control
0x18004dad9  cmp     rcx, rax
0x18004dadc  jz      short loc_18004DB0A
0x18004dade  test    byte ptr [rcx+1Ch], 2
0x18004dae2  jz      short loc_18004DB0A
0x18004dae4  mov     rcx, [rcx+10h]
0x18004dae8  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004daef  mov     edx, 160h
0x18004daf4  mov     r9d, esi
0x18004daf7  call    WPP_SF_d
0x18004dafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db03  lea     rax, WPP_GLOBAL_Control
0x18004db0a  or      esi, 80010000h
0x18004db10  cmp     rcx, rax
0x18004db13  jz      loc_18004E26F
0x18004db19  test    byte ptr [rcx+1Ch], 40h
0x18004db1d  jz      loc_18004E24C
0x18004db23  mov     edx, 161h
0x18004db28  jmp     loc_18004D998
0x18004db2d  mov     ecx, 2
0x18004db32  mov     [rbp+2B0h+var_32B], bl
0x18004db35  call    ?DeleteBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@@Z; DeleteBitLockerStatusReg(BITLOCKER_CSP_STATUS)
0x18004db3a  lea     rcx, [rbp+2B0h+var_260]
0x18004db3e  call    NgscbGetOSVolume
0x18004db43  mov     esi, eax
0x18004db45  test    eax, eax
0x18004db47  jz      short loc_18004DB90
0x18004db49  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db50  lea     rax, WPP_GLOBAL_Control
0x18004db57  cmp     rcx, rax
0x18004db5a  jz      short loc_18004DB88
0x18004db5c  test    byte ptr [rcx+1Ch], 40h
0x18004db60  jz      short loc_18004DB88
0x18004db62  mov     rcx, [rcx+10h]
0x18004db66  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004db6d  mov     edx, 162h
0x18004db72  mov     r9d, esi
0x18004db75  call    WPP_SF_d
0x18004db7a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db81  lea     rax, WPP_GLOBAL_Control
0x18004db88  test    esi, esi
0x18004db8a  js      loc_18004E24C
0x18004db90  lea     r8, [rbp+2B0h+var_2C8]
0x18004db94  xor     edx, edx
0x18004db96  lea     rcx, [rbp+2B0h+var_260]
0x18004db9a  call    cs:__imp_FveOpenVolumeW
0x18004dba1  nop     dword ptr [rax+rax+00h]
0x18004dba6  mov     esi, eax
0x18004dba8  test    eax, eax
0x18004dbaa  jz      short loc_18004DBF3
0x18004dbac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dbb3  lea     rax, WPP_GLOBAL_Control
0x18004dbba  cmp     rcx, rax
0x18004dbbd  jz      short loc_18004DBEB
0x18004dbbf  test    byte ptr [rcx+1Ch], 40h
0x18004dbc3  jz      short loc_18004DBEB
0x18004dbc5  mov     rcx, [rcx+10h]
0x18004dbc9  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004dbd0  mov     edx, 163h
0x18004dbd5  mov     r9d, esi
0x18004dbd8  call    WPP_SF_d
0x18004dbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dbe4  lea     rax, WPP_GLOBAL_Control
0x18004dbeb  test    esi, esi
0x18004dbed  js      loc_18004E24C
0x18004dbf3  mov     rcx, [rbp+2B0h+var_2C8]; void *
0x18004dbf7  lea     rdx, [rbp+2B0h+var_31C]; unsigned int *
0x18004dbfb  call    ?GetStatusFlags@CFveApiWrapper@@SAJPEAXPEAK@Z; CFveApiWrapper::GetStatusFlags(void *,ulong *)
0x18004dc00  mov     esi, eax
0x18004dc02  test    eax, eax
0x18004dc04  jz      short loc_18004DC4D
0x18004dc06  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc0d  lea     rax, WPP_GLOBAL_Control
0x18004dc14  cmp     rcx, rax
0x18004dc17  jz      short loc_18004DC45
0x18004dc19  test    byte ptr [rcx+1Ch], 40h
0x18004dc1d  jz      short loc_18004DC45
0x18004dc1f  mov     rcx, [rcx+10h]
0x18004dc23  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004dc2a  mov     edx, 164h
0x18004dc2f  mov     r9d, esi
0x18004dc32  call    WPP_SF_d
0x18004dc37  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc3e  lea     rax, WPP_GLOBAL_Control
0x18004dc45  test    esi, esi
0x18004dc47  js      loc_18004E24C
0x18004dc4d  mov     ecx, 1
0x18004dc52  call    cs:__imp_FveSetAllowKeyExport
0x18004dc59  nop     dword ptr [rax+rax+00h]
0x18004dc5e  mov     esi, eax
0x18004dc60  test    eax, eax
0x18004dc62  jz      short loc_18004DCAB
0x18004dc64  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc6b  lea     rax, WPP_GLOBAL_Control
0x18004dc72  cmp     rcx, rax
0x18004dc75  jz      short loc_18004DCA3
0x18004dc77  test    byte ptr [rcx+1Ch], 40h
0x18004dc7b  jz      short loc_18004DCA3
0x18004dc7d  mov     rcx, [rcx+10h]
0x18004dc81  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004dc88  mov     edx, 165h
0x18004dc8d  mov     r9d, esi
0x18004dc90  call    WPP_SF_d
0x18004dc95  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dc9c  lea     rax, WPP_GLOBAL_Control
0x18004dca3  test    esi, esi
0x18004dca5  js      loc_18004E24C
0x18004dcab  mov     eax, [rbp+2B0h+var_31C]
0x18004dcae  and     eax, 401h
0x18004dcb3  cmp     eax, 1
0x18004dcb6  jz      loc_18004E03A
0x18004dcbc  xor     r8d, r8d; unsigned int
0x18004dcbf  lea     rcx, [rbp+2B0h+var_32F]; bool *
0x18004dcc3  xor     edx, edx; unsigned __int16 *
0x18004dcc5  call    ?NgscbGetWinReConfiguration@@YAJPEA_NPEAGK@Z; NgscbGetWinReConfiguration(bool *,ushort *,ulong)
0x18004dcca  mov     esi, eax
0x18004dccc  test    eax, eax
0x18004dcce  jz      short loc_18004DD15
0x18004dcd0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dcd7  lea     r13, WPP_GLOBAL_Control
0x18004dcde  cmp     rcx, r13
0x18004dce1  jz      short loc_18004DD08
0x18004dce3  test    byte ptr [rcx+1Ch], 40h
0x18004dce7  jz      short loc_18004DD08
0x18004dce9  mov     rcx, [rcx+10h]
0x18004dced  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004dcf4  mov     edx, 166h
0x18004dcf9  mov     r9d, eax
  ... truncated ...
```
