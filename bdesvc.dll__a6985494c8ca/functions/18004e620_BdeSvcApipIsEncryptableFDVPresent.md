# BdeSvcApipIsEncryptableFDVPresent

- ea: `0x18004e620`
- end: `0x18004ebcb`
- name: `BdeSvcApipIsEncryptableFDVPresent`
- size: `1451`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000dc4c`
- `0x180020650`
- `0x180034070`
- `0x180048c8c`
- `0x18004a384`
- `0x18004b5f0`
- `0x18004e620`
- `0x18006b2e8`
- `0x18006c210`
- `0x18006f774`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18004e745`
- `RPCRT4!RpcImpersonateClient` at `0x18004e745`
- `RPCRT4!RpcRevertToSelf` at `0x18004e887`
- `RPCRT4!RpcRevertToSelf` at `0x18004eb59`
- `RPCRT4!RpcRevertToSelf` at `0x18004e887`
- `RPCRT4!RpcRevertToSelf` at `0x18004eb59`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18004e9af`
- `FVEAPI!FveOpenVolumeByHandle` at `0x18004e9af`
- `FVEAPI!FveCloseVolume` at `0x18004e97d`
- `FVEAPI!FveCloseVolume` at `0x18004eb3f`
- `FVEAPI!FveCloseVolume` at `0x18004e97d`
- `FVEAPI!FveCloseVolume` at `0x18004eb3f`
- `FVEAPI!FveFindNextVolume` at `0x18004ea8a`
- `FVEAPI!FveFindNextVolume` at `0x18004ea8a`
- `FVEAPI!FveFindFirstVolume` at `0x18004e95d`
- `FVEAPI!FveFindFirstVolume` at `0x18004e95d`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18004e6f4`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x18004e6f4`

## pseudocode

```c
__int64 __fastcall BdeSvcApipIsEncryptableFDVPresent(__int64 a1, _DWORD *a2)
{
  _DWORD *v2; // rsi
  signed int v3; // ebx
  char v4; // r14
  unsigned int PolicyInt; // eax
  PVOID *v6; // rcx
  bool v7; // di
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // eax
  int updated; // eax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  unsigned int EncryptableVolumeNamesForBcdDevices; // eax
  int i; // eax
  unsigned int v18; // edi
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v22; // [rsp+20h] [rbp-50h]
  bool v23; // [rsp+30h] [rbp-40h] BYREF
  bool v24; // [rsp+31h] [rbp-3Fh] BYREF
  void *v25; // [rsp+38h] [rbp-38h] BYREF
  struct PathBuffer *v26; // [rsp+40h] [rbp-30h] BYREF
  int v27; // [rsp+48h] [rbp-28h] BYREF
  unsigned int v28; // [rsp+4Ch] [rbp-24h] BYREF
  unsigned __int64 v29; // [rsp+50h] [rbp-20h] BYREF
  void **v30; // [rsp+58h] [rbp-18h] BYREF
  __int64 v31; // [rsp+60h] [rbp-10h] BYREF

  v25 = (void *)-1LL;
  v30 = &Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable';
  v2 = a2;
  v29 = 0;
  v31 = 0;
  v26 = 0;
  v28 = 0;
  v24 = 1;
  v27 = 0;
  v23 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 325, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  if ( !v2 )
  {
    v3 = -2147467261;
    goto LABEL_94;
  }
  v4 = 0;
  *v2 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives>::GetImpl'::`2'::impl,
    a2);
  PolicyInt = PolicyManager_GetPolicyInt(L"BitLocker", L"AllowStandardUserEncryption", &v27);
  v3 = PolicyInt;
  if ( PolicyInt )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 327, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, PolicyInt);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 < 0 )
      goto LABEL_82;
  }
  v7 = v27 != 0;
  v8 = RpcImpersonateClient(0);
  v9 = v8;
  if ( v8 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v8);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = v9 | 0x80010000;
    if ( v6 == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_82;
    v10 = 329;
    goto LABEL_18;
  }
  v4 = 1;
  v12 = CheckIsStandardUser(&v23);
  v3 = v12;
  if ( v12 )
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 330, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v12);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 < 0 )
      goto LABEL_82;
  }
  else
  {
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v23 || v7 )
  {
    v14 = RpcRevertToSelf();
    v15 = v14;
    if ( !v14 )
    {
      v4 = 0;
      DeleteBitLockerStatusReg(2);
      EncryptableVolumeNamesForBcdDevices = FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(&v26, &v28);
      v3 = EncryptableVolumeNamesForBcdDevices;
      if ( EncryptableVolumeNamesForBcdDevices )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            336,
            &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
            EncryptableVolumeNamesForBcdDevices);
          v6 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v3 < 0 )
          goto LABEL_82;
      }
      v29 = 0xFFFFFFFF00000001uLL;
      Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v30);
      for ( i = FveFindFirstVolume(&v31, &v29); ; i = FveFindNextVolume(v31, &v29) )
      {
        v18 = i;
        if ( i < 0 )
          break;
        if ( v25 != (void *)-1LL )
        {
          FveCloseVolume(v25);
          v25 = (void *)-1LL;
        }
        LODWORD(v22) = 0;
        v3 = FveOpenVolumeByHandle(v31, 0, 0, 0xFFFFFFFFLL, v22, &v25);
        if ( v3 == -2147024894 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              337,
              &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
              2147942402LL);
          v3 = 0;
        }
        else
        {
          if ( v3 )
          {
            v6 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                338,
                &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
                (unsigned int)v3);
              v6 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v3 < 0 )
              goto LABEL_82;
          }
          v19 = IsFDVEncryptableForSilentBitLocker(v25, v26, v28, &v24);
          v3 = v19;
          if ( v19 )
          {
            v6 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 339, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v19);
              v6 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v3 < 0 )
              goto LABEL_82;
          }
          if ( v24 )
          {
            *v2 = 1;
            goto LABEL_81;
          }
        }
      }
      if ( i == -2147024878 )
        goto LABEL_81;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          340,
          &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
          (unsigned int)i);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v3 = v18;
      if ( v6 == &WPP_GLOBAL_Control )
        goto LABEL_85;
      if ( (*((_BYTE *)v6 + 28) & 0x40) == 0 )
        goto LABEL_82;
      v10 = 341;
      v11 = v18;
LABEL_80:
      WPP_SF_d(v6[2], v10, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v11);
LABEL_81:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_82;
    }
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 334, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v14);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    v3 = v15 | 0x80010000;
    if ( v6 == &WPP_GLOBAL_Control )
      goto LABEL_85;
    if ( (*((_BYTE *)v6 + 28) & 0x40) == 0 )
      goto LABEL_82;
    v10 = 335;
LABEL_18:
    v11 = (unsigned int)v3;
    goto LABEL_80;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 2) != 0 )
    WPP_SF_(v6[2], 331, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids);
  updated = UpdateBitLockerStatusReg(2u, -2147024846);
  if ( updated >= 0 )
    goto LABEL_35;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      332,
      &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
      (unsigned int)updated);
LABEL_35:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v3 = -2147024846;
  if ( v6 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v6 + 28) & 0x40) == 0 )
    {
LABEL_82:
      if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
        WPP_SF_d(v6[2], 342, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, (unsigned int)v3);
      goto LABEL_85;
    }
    v10 = 333;
    goto LABEL_18;
  }
LABEL_85:
  if ( v26 )
  {
    PathBuffer::`vector deleting destructor'(v26);
    v26 = 0;
  }
  if ( v25 != (void *)-1LL )
  {
    FveCloseVolume(v25);
    v25 = (void *)-1LL;
  }
  if ( v4 == 1 )
  {
    v20 = RpcRevertToSelf();
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 343, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v20);
    }
  }
LABEL_94:
  v30 = &Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v30);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004e620  mov     [rsp-28h+arg_0], rbx
0x18004e625  mov     [rsp-28h+arg_10], rsi
0x18004e62a  push    rbp
0x18004e62b  push    rdi
0x18004e62c  push    r12
0x18004e62e  push    r13
0x18004e630  push    r14
0x18004e632  mov     rbp, rsp
0x18004e635  sub     rsp, 70h
0x18004e639  mov     rax, cs:__security_cookie
0x18004e640  xor     rax, rsp
0x18004e643  mov     [rbp+var_8], rax
0x18004e647  lea     rax, ??_7?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable'
0x18004e64e  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFFh
0x18004e656  mov     [rbp+var_18], rax
0x18004e65a  mov     rsi, rdx
0x18004e65d  mov     [rbp+var_20], 0
0x18004e665  mov     [rbp+var_10], 0
0x18004e66d  mov     [rbp+var_30], 0
0x18004e675  mov     [rbp+var_24], 0
0x18004e67c  mov     [rbp+var_3F], 1
0x18004e680  mov     [rbp+var_28], 0
0x18004e687  mov     [rbp+var_40], 0
0x18004e68b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e692  lea     r12, WPP_GLOBAL_Control
0x18004e699  lea     r13, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x18004e6a0  cmp     rcx, r12
0x18004e6a3  jz      short loc_18004E6BC
0x18004e6a5  test    byte ptr [rcx+1Ch], 20h
0x18004e6a9  jz      short loc_18004E6BC
0x18004e6ab  mov     rcx, [rcx+10h]
0x18004e6af  mov     edx, 145h
0x18004e6b4  mov     r8, r13
0x18004e6b7  call    WPP_SF_
0x18004e6bc  test    rsi, rsi
0x18004e6bf  jnz     short loc_18004E6CB
0x18004e6c1  mov     ebx, 80004003h
0x18004e6c6  jmp     loc_18004EB8F
0x18004e6cb  xor     r14b, r14b
0x18004e6ce  mov     dword ptr [rsi], 0
0x18004e6d4  mov     dl, 1
0x18004e6d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives>::GetImpl(void)'::`2'::impl
0x18004e6dd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Encrypt_All_Drives>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004e6e2  lea     r8, [rbp+var_28]
0x18004e6e6  lea     rdx, aAllowstandardu; "AllowStandardUserEncryption"
0x18004e6ed  lea     rcx, aBitlocker; "BitLocker"
0x18004e6f4  call    cs:__imp_PolicyManager_GetPolicyInt
0x18004e6fb  nop     dword ptr [rax+rax+00h]
0x18004e700  mov     ebx, eax
0x18004e702  test    eax, eax
0x18004e704  jz      short loc_18004E73B
0x18004e706  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e70d  cmp     rcx, r12
0x18004e710  jz      short loc_18004E733
0x18004e712  test    byte ptr [rcx+1Ch], 40h
0x18004e716  jz      short loc_18004E733
0x18004e718  mov     rcx, [rcx+10h]
0x18004e71c  mov     edx, 147h
0x18004e721  mov     r9d, eax
0x18004e724  mov     r8, r13
0x18004e727  call    WPP_SF_d
0x18004e72c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e733  test    ebx, ebx
0x18004e735  js      loc_18004EB00
0x18004e73b  cmp     [rbp+var_28], 0
0x18004e73f  setnz   dil
0x18004e743  xor     ecx, ecx; BindingHandle
0x18004e745  call    cs:__imp_RpcImpersonateClient
0x18004e74c  nop     dword ptr [rax+rax+00h]
0x18004e751  mov     ebx, eax
0x18004e753  test    eax, eax
0x18004e755  jz      short loc_18004E7AA
0x18004e757  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e75e  cmp     rcx, r12
0x18004e761  jz      short loc_18004E784
0x18004e763  test    byte ptr [rcx+1Ch], 2
0x18004e767  jz      short loc_18004E784
0x18004e769  mov     rcx, [rcx+10h]
0x18004e76d  mov     edx, 148h
0x18004e772  mov     r9d, eax
0x18004e775  mov     r8, r13
0x18004e778  call    WPP_SF_d
0x18004e77d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e784  or      ebx, 80010000h
0x18004e78a  cmp     rcx, r12
0x18004e78d  jz      loc_18004EB1F
0x18004e793  test    byte ptr [rcx+1Ch], 40h
0x18004e797  jz      loc_18004EB00
0x18004e79d  mov     edx, 149h
0x18004e7a2  mov     r9d, ebx
0x18004e7a5  jmp     loc_18004EAED
0x18004e7aa  lea     rcx, [rbp+var_40]; bool *
0x18004e7ae  mov     r14b, 1
0x18004e7b1  call    ?CheckIsStandardUser@@YAJPEA_N@Z; CheckIsStandardUser(bool *)
0x18004e7b6  mov     ebx, eax
0x18004e7b8  test    eax, eax
0x18004e7ba  jz      short loc_18004E7F3
0x18004e7bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e7c3  cmp     rcx, r12
0x18004e7c6  jz      short loc_18004E7E9
0x18004e7c8  test    byte ptr [rcx+1Ch], 40h
0x18004e7cc  jz      short loc_18004E7E9
0x18004e7ce  mov     rcx, [rcx+10h]
0x18004e7d2  mov     edx, 14Ah
0x18004e7d7  mov     r9d, eax
0x18004e7da  mov     r8, r13
0x18004e7dd  call    WPP_SF_d
0x18004e7e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e7e9  test    ebx, ebx
0x18004e7eb  js      loc_18004EB00
0x18004e7f1  jmp     short loc_18004E7FA
0x18004e7f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e7fa  cmp     [rbp+var_40], r14b
0x18004e7fe  jnz     loc_18004E887
0x18004e804  test    dil, dil
0x18004e807  jnz     short loc_18004E887
0x18004e809  cmp     rcx, r12
0x18004e80c  jz      short loc_18004E825
0x18004e80e  test    byte ptr [rcx+1Ch], 2
0x18004e812  jz      short loc_18004E825
0x18004e814  mov     rcx, [rcx+10h]
0x18004e818  mov     edx, 14Bh
0x18004e81d  mov     r8, r13
0x18004e820  call    WPP_SF_
0x18004e825  mov     edx, 80070032h
0x18004e82a  mov     ecx, 2
0x18004e82f  call    ?UpdateBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@K@Z; UpdateBitLockerStatusReg(BITLOCKER_CSP_STATUS,ulong)
0x18004e834  test    eax, eax
0x18004e836  jns     short loc_18004E85E
0x18004e838  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e83f  cmp     rcx, r12
0x18004e842  jz      short loc_18004E865
0x18004e844  test    byte ptr [rcx+1Ch], 2
0x18004e848  jz      short loc_18004E865
0x18004e84a  mov     rcx, [rcx+10h]
0x18004e84e  mov     edx, 14Ch
0x18004e853  mov     r9d, eax
0x18004e856  mov     r8, r13
0x18004e859  call    WPP_SF_d
0x18004e85e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e865  mov     ebx, 80070032h
0x18004e86a  cmp     rcx, r12
0x18004e86d  jz      loc_18004EB1F
0x18004e873  test    byte ptr [rcx+1Ch], 40h
0x18004e877  jz      loc_18004EB00
0x18004e87d  mov     edx, 14Dh
0x18004e882  jmp     loc_18004E7A2
0x18004e887  call    cs:__imp_RpcRevertToSelf
0x18004e88e  nop     dword ptr [rax+rax+00h]
0x18004e893  mov     ebx, eax
0x18004e895  test    eax, eax
0x18004e897  jz      short loc_18004E8E9
0x18004e899  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e8a0  cmp     rcx, r12
0x18004e8a3  jz      short loc_18004E8C6
0x18004e8a5  test    byte ptr [rcx+1Ch], 2
0x18004e8a9  jz      short loc_18004E8C6
0x18004e8ab  mov     rcx, [rcx+10h]
0x18004e8af  mov     edx, 14Eh
0x18004e8b4  mov     r9d, eax
0x18004e8b7  mov     r8, r13
0x18004e8ba  call    WPP_SF_d
0x18004e8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e8c6  or      ebx, 80010000h
0x18004e8cc  cmp     rcx, r12
0x18004e8cf  jz      loc_18004EB1F
0x18004e8d5  test    byte ptr [rcx+1Ch], 40h
0x18004e8d9  jz      loc_18004EB00
0x18004e8df  mov     edx, 14Fh
0x18004e8e4  jmp     loc_18004E7A2
0x18004e8e9  mov     ecx, 2
0x18004e8ee  xor     r14b, r14b
0x18004e8f1  call    ?DeleteBitLockerStatusReg@@YAJW4BITLOCKER_CSP_STATUS@@@Z; DeleteBitLockerStatusReg(BITLOCKER_CSP_STATUS)
0x18004e8f6  lea     rdx, [rbp+var_24]; unsigned int *
0x18004e8fa  lea     rcx, [rbp+var_30]; struct PathBuffer **
0x18004e8fe  call    ?GetEncryptableVolumeNamesForBcdDevices@FveBcdUtil@@SAJPEAPEAVPathBuffer@@PEAK@Z; FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(PathBuffer * *,ulong *)
0x18004e903  mov     ebx, eax
0x18004e905  test    eax, eax
0x18004e907  jz      short loc_18004E93E
0x18004e909  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e910  cmp     rcx, r12
0x18004e913  jz      short loc_18004E936
0x18004e915  test    byte ptr [rcx+1Ch], 40h
0x18004e919  jz      short loc_18004E936
0x18004e91b  mov     rcx, [rcx+10h]
0x18004e91f  mov     edx, 150h
0x18004e924  mov     r9d, eax
0x18004e927  mov     r8, r13
0x18004e92a  call    WPP_SF_d
0x18004e92f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e936  test    ebx, ebx
0x18004e938  js      loc_18004EB00
0x18004e93e  lea     rcx, [rbp+var_18]
0x18004e942  mov     dword ptr [rbp+var_20], 1
0x18004e949  mov     dword ptr [rbp+var_20+4], 0FFFFFFFFh
0x18004e950  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x18004e955  lea     rdx, [rbp+var_20]
0x18004e959  lea     rcx, [rbp+var_10]
0x18004e95d  call    cs:__imp_FveFindFirstVolume
0x18004e964  nop     dword ptr [rax+rax+00h]
0x18004e969  mov     edi, eax
0x18004e96b  test    eax, eax
0x18004e96d  js      loc_18004EAA3
0x18004e973  mov     rcx, [rbp+var_38]
0x18004e977  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004e97b  jz      short loc_18004E991
0x18004e97d  call    cs:__imp_FveCloseVolume
0x18004e984  nop     dword ptr [rax+rax+00h]
0x18004e989  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFFh
0x18004e991  mov     rcx, [rbp+var_10]
0x18004e995  lea     rax, [rbp+var_38]
0x18004e999  mov     [rsp+70h+var_48], rax
0x18004e99e  or      r9d, 0FFFFFFFFh
0x18004e9a2  xor     r8d, r8d
0x18004e9a5  mov     dword ptr [rsp+70h+var_50], 0
0x18004e9ad  xor     edx, edx
0x18004e9af  call    cs:__imp_FveOpenVolumeByHandle
0x18004e9b6  nop     dword ptr [rax+rax+00h]
0x18004e9bb  mov     ebx, eax
0x18004e9bd  mov     eax, 80070002h
0x18004e9c2  cmp     ebx, eax
0x18004e9c4  jnz     short loc_18004E9F3
0x18004e9c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e9cd  cmp     rcx, r12
0x18004e9d0  jz      short loc_18004E9EC
0x18004e9d2  test    byte ptr [rcx+1Ch], 4
0x18004e9d6  jz      short loc_18004E9EC
0x18004e9d8  mov     rcx, [rcx+10h]
0x18004e9dc  mov     edx, 151h
0x18004e9e1  mov     r9d, eax
0x18004e9e4  mov     r8, r13
0x18004e9e7  call    WPP_SF_d
0x18004e9ec  xor     ebx, ebx
0x18004e9ee  jmp     loc_18004EA82
0x18004e9f3  test    ebx, ebx
0x18004e9f5  jz      short loc_18004EA2C
0x18004e9f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e9fe  cmp     rcx, r12
0x18004ea01  jz      short loc_18004EA24
0x18004ea03  test    byte ptr [rcx+1Ch], 40h
0x18004ea07  jz      short loc_18004EA24
0x18004ea09  mov     rcx, [rcx+10h]
0x18004ea0d  mov     edx, 152h
0x18004ea12  mov     r9d, ebx
0x18004ea15  mov     r8, r13
0x18004ea18  call    WPP_SF_d
0x18004ea1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ea24  test    ebx, ebx
0x18004ea26  js      loc_18004EB00
0x18004ea2c  mov     r8d, [rbp+var_24]; unsigned int
0x18004ea30  lea     r9, [rbp+var_3F]; bool *
0x18004ea34  mov     rdx, [rbp+var_30]; struct PathBuffer *
0x18004ea38  mov     rcx, [rbp+var_38]; void *
0x18004ea3c  call    ?IsFDVEncryptableForSilentBitLocker@@YAJPEAXPEAVPathBuffer@@KPEA_N@Z; IsFDVEncryptableForSilentBitLocker(void *,PathBuffer *,ulong,bool *)
0x18004ea41  mov     ebx, eax
0x18004ea43  test    eax, eax
0x18004ea45  jz      short loc_18004EA7C
0x18004ea47  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ea4e  cmp     rcx, r12
0x18004ea51  jz      short loc_18004EA74
0x18004ea53  test    byte ptr [rcx+1Ch], 40h
0x18004ea57  jz      short loc_18004EA74
0x18004ea59  mov     rcx, [rcx+10h]
0x18004ea5d  mov     edx, 153h
0x18004ea62  mov     r9d, eax
0x18004ea65  mov     r8, r13
0x18004ea68  call    WPP_SF_d
0x18004ea6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ea74  test    ebx, ebx
0x18004ea76  js      loc_18004EB00
0x18004ea7c  cmp     [rbp+var_3F], 1
0x18004ea80  jz      short loc_18004EA9B
0x18004ea82  mov     rcx, [rbp+var_10]
0x18004ea86  lea     rdx, [rbp+var_20]
0x18004ea8a  call    cs:__imp_FveFindNextVolume
0x18004ea91  nop     dword ptr [rax+rax+00h]
0x18004ea96  jmp     loc_18004E969
0x18004ea9b  mov     dword ptr [rsi], 1
0x18004eaa1  jmp     short loc_18004EAF9
0x18004eaa3  cmp     edi, 80070012h
0x18004eaa9  jz      short loc_18004EAF9
0x18004eaab  mov     rcx, cs:WPP_GLOBAL_Control
0x18004eab2  cmp     rcx, r12
0x18004eab5  jz      short loc_18004EAD8
0x18004eab7  test    byte ptr [rcx+1Ch], 2
0x18004eabb  jz      short loc_18004EAD8
0x18004eabd  mov     rcx, [rcx+10h]
0x18004eac1  mov     edx, 154h
0x18004eac6  mov     r9d, edi
0x18004eac9  mov     r8, r13
0x18004eacc  call    WPP_SF_d
0x18004ead1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ead8  mov     ebx, edi
0x18004eada  cmp     rcx, r12
0x18004eadd  jz      short loc_18004EB1F
0x18004eadf  test    byte ptr [rcx+1Ch], 40h
0x18004eae3  jz      short loc_18004EB00
0x18004eae5  mov     edx, 155h
0x18004eaea  mov     r9d, edi
0x18004eaed  mov     rcx, [rcx+10h]
  ... truncated ...
```
