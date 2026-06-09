# ShieldProvider::AccountProtectionShield::RefreshWindowsHelloSubPillar(void)

- ea: `0x1800c9520`
- end: `0x1800c9c03`
- name: `?RefreshWindowsHelloSubPillar@AccountProtectionShield@ShieldProvider@@AEAAJXZ`
- size: `1763`
- prototype: `__int64 __fastcall(ShieldProvider::AccountProtectionShield *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c93a0`

## callees

- `0x18000d7fc`
- `0x18000f02c`
- `0x18000f094`
- `0x18001c9f8`
- `0x1800c8284`
- `0x1800c8440`
- `0x1800c9520`
- `0x1800ce8f8`
- `0x1800cfdb8`
- `0x1800d0c14`
- `0x1800d5940`
- `0x1800d79c4`
- `0x1800d7aac`
- `0x1800d7b4c`
- `0x1800d83ac`
- `0x1800d8528`
- `0x1800d86ac`
- `0x1800d8790`
- `0x1800e1764`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800c96db`
- `KERNEL32!LocalFree` at `0x1800c98bd`
- `KERNEL32!LocalFree` at `0x1800c96db`
- `KERNEL32!LocalFree` at `0x1800c98bd`
- `ole32!CoTaskMemFree` at `0x1800c9576`
- `ole32!CoTaskMemFree` at `0x1800c95e8`
- `ole32!CoTaskMemFree` at `0x1800c963c`
- `ole32!CoTaskMemFree` at `0x1800c9bcb`
- `ole32!CoTaskMemFree` at `0x1800c9be7`
- `ole32!CoTaskMemFree` at `0x1800c9576`
- `ole32!CoTaskMemFree` at `0x1800c95e8`
- `ole32!CoTaskMemFree` at `0x1800c963c`
- `ole32!CoTaskMemFree` at `0x1800c9bcb`
- `ole32!CoTaskMemFree` at `0x1800c9be7`

## string_xrefs

- `0x1800c9855`: `onecore\amcore\antimalware\source\shieldprovider\shieldproviderservice\accountprotectionshield\accountprotectionshield.cpp`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AccountProtectionShield::RefreshWindowsHelloSubPillar(
        ShieldProvider::AccountProtectionShield *this)
{
  void *v2; // rbx
  int v3; // esi
  unsigned __int16 *v4; // r8
  char i; // al
  unsigned __int16 **v6; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  _QWORD *v10; // rcx
  int JoinInfo; // edi
  __int64 v12; // rdx
  char v13; // r13
  char v14; // r12
  int v15; // eax
  __int64 v16; // rcx
  int v17; // r9d
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  int CanCurrentUserProvisionNgcKey; // eax
  __int64 v21; // rdx
  HLOCAL v22; // rcx
  int *v23; // r8
  char j; // al
  __int64 v25; // rdi
  int IsAccountPasswordLess; // eax
  __int64 v27; // rdx
  unsigned int v28; // r14d
  int v29; // eax
  __int64 v30; // rdx
  int v31; // eax
  int v32; // ecx
  int v33; // [rsp+20h] [rbp-59h]
  __int64 v34; // [rsp+30h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-41h] BYREF
  __int64 v36; // [rsp+40h] [rbp-39h] BYREF
  __int64 v37; // [rsp+48h] [rbp-31h] BYREF
  int v38; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v39[16]; // [rsp+58h] [rbp-21h] BYREF
  char v40; // [rsp+68h] [rbp-11h]
  _BYTE v41[96]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  LPVOID pv; // [rsp+E0h] [rbp+67h] BYREF
  bool v44; // [rsp+E8h] [rbp+6Fh]
  int v45; // [rsp+F0h] [rbp+77h] BYREF
  int v46; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 0;
  v3 = 0;
  pv = 0;
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v39,
    (char *)this + 64);
  for ( i = 1; ; i = 0 )
  {
    v40 = i;
    if ( !i )
      break;
    v6 = (unsigned __int16 **)*((_QWORD *)this + 21);
    if ( !v6 )
    {
      v10 = WPP_GLOBAL_Control;
      JoinInfo = -2147024875;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v12 = 59;
LABEL_17:
        WPP_SF_d(v10[2], v12, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, (unsigned int)JoinInfo);
      }
      goto LABEL_18;
    }
    if ( v2 )
    {
      CoTaskMemFree(v2);
      pv = 0;
    }
    v7 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&pv, v6, v4);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v7);
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v39);
      if ( pv )
        CoTaskMemFree(pv);
      return v8;
    }
    v3 = *((_DWORD *)this + 48);
    v2 = pv;
  }
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v39);
  v13 = 0;
  v14 = 0;
  v44 = 0;
  LOBYTE(pv) = 0;
  ShieldProvider::AccountProtectionShield::IsRemoteSession(this, (bool *)&pv);
  if ( (_BYTE)pv )
    goto LABEL_73;
  v13 = 0;
  v37 = 0;
  hMem = 0;
  v15 = NgcEnumContainers(v2, &hMem, &v37);
  JoinInfo = v15;
  if ( v15 < 0 )
  {
    if ( v15 != -2146893782 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          61,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)v15);
LABEL_28:
      if ( hMem )
        LocalFree(hMem);
      if ( v37 )
        NgcFreeEnumState();
      goto LABEL_19;
    }
    v45 = 2;
    v46 = 1;
    v36 = 0;
    JoinInfo = DsrGetJoinInfo(v16, &v36);
    if ( JoinInfo < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 62;
LABEL_36:
        WPP_SF_d(v18[2], v19, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids, (unsigned int)JoinInfo);
        goto LABEL_37;
      }
      goto LABEL_37;
    }
    if ( v36 )
    {
      JoinInfo = NgcQueryEnabled((_DWORD)v2, *(_QWORD *)(v36 + 32), (unsigned int)&v45, v17);
      if ( JoinInfo < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 63;
          goto LABEL_36;
        }
LABEL_37:
        if ( v36 )
          DsrFreeJoinInfo();
        goto LABEL_28;
      }
    }
    else
    {
      JoinInfo = NgcQueryEnabled((_DWORD)v2, 0, (unsigned int)&v45, v17);
      if ( JoinInfo < 0 )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v19 = 64;
          goto LABEL_36;
        }
        goto LABEL_37;
      }
    }
    if ( !v45 || !v46 )
      goto LABEL_64;
    v38 = 0;
    JoinInfo = DsrIsDeviceJoined(&v38);
    if ( JoinInfo < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v19 = 65;
        goto LABEL_36;
      }
      goto LABEL_37;
    }
    if ( (unsigned int)(v3 - 5) <= 1 && v38 )
    {
      LODWORD(v34) = 0;
      CanCurrentUserProvisionNgcKey = DsrCanCurrentUserProvisionNgcKey(&v34);
      if ( CanCurrentUserProvisionNgcKey < 0 )
      {
        v21 = 732;
LABEL_58:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"onecore\\amcore\\antimalware\\source\\shieldprovider\\shieldproviderservice\\accountprotectionsh"
                        "ield\\accountprotectionshield.cpp",
          (const char *)(unsigned int)CanCurrentUserProvisionNgcKey,
          v33);
        goto LABEL_64;
      }
    }
    else
    {
      if ( (unsigned int)(v3 - 2) > 1 || v45 != 1 )
        goto LABEL_65;
      LODWORD(v34) = 0;
      CanCurrentUserProvisionNgcKey = DsrCanCurrentUserProvisionNgcKey(&v34);
      if ( CanCurrentUserProvisionNgcKey < 0 )
      {
        v21 = 740;
        goto LABEL_58;
      }
    }
    if ( (_DWORD)v34 )
    {
LABEL_65:
      if ( v36 )
        DsrFreeJoinInfo();
      v22 = hMem;
      goto LABEL_69;
    }
LABEL_64:
    v14 = 1;
    goto LABEL_65;
  }
  v22 = hMem;
  v13 = 1;
  v44 = *((_DWORD *)hMem + 4) != 2;
LABEL_69:
  if ( v22 )
    LocalFree(v22);
  if ( v37 )
    NgcFreeEnumState();
LABEL_73:
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
    v39,
    (char *)this + 64);
  for ( j = 1; ; j = 0 )
  {
    v40 = j;
    if ( !j )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v39);
      if ( v2 )
        CoTaskMemFree(v2);
      return 0;
    }
    if ( (_BYTE)pv )
    {
      v34 = 116;
      goto LABEL_115;
    }
    v25 = *((_QWORD *)this + 17);
    v46 = 0;
    IsAccountPasswordLess = ShieldProvider::MpIsAccountPasswordLess((ShieldProvider *)v2, (unsigned __int16 *)&v46, v23);
    v28 = IsAccountPasswordLess;
    if ( IsAccountPasswordLess < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
          (unsigned int)IsAccountPasswordLess);
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v39);
      if ( v2 )
        CoTaskMemFree(v2);
      return v28;
    }
    if ( !v13 )
      break;
    if ( v44 && ((*((_DWORD *)this + 48) - 4) & 0xFFFFFFFD) == 0 )
    {
      if ( v46 )
      {
        LODWORD(v34) = 118;
LABEL_99:
        HIDWORD(v34) = 8;
        goto LABEL_115;
      }
      LOBYTE(v45) = 0;
      JoinInfo = ShieldProvider::GetWarningStateDismissal(119, &v45);
      if ( JoinInfo < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v12 = 67;
          goto LABEL_17;
        }
        goto LABEL_18;
      }
      if ( !(_BYTE)v45 )
      {
        LODWORD(v34) = 119;
LABEL_112:
        HIDWORD(v34) = 4;
        goto LABEL_115;
      }
      LODWORD(v34) = 120;
      goto LABEL_114;
    }
    LOBYTE(v27) = 1;
    v34 = 0x200000070LL;
    v29 = ShieldProvider::SetOrRemoveWarningStateDismissal(113, v27);
    if ( v29 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)v29);
    LOBYTE(v30) = 1;
    v31 = ShieldProvider::SetOrRemoveWarningStateDismissal(119, v30);
    if ( v31 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids,
        (unsigned int)v31);
LABEL_115:
    if ( !(unsigned __int8)ShieldProvider::IsEqualPillarStatus(v34, *((_QWORD *)this + 25)) )
    {
      *((_QWORD *)this + 25) = v23;
      *((_BYTE *)this + 208) = 1;
    }
  }
  if ( v46 )
  {
    v32 = *((_DWORD *)this + 48);
    if ( ((v32 - 4) & 0xFFFFFFFD) == 0 )
    {
      if ( !ShieldProvider::AccountProtectionShield::IsMSAInConnectGracePeriod(this, v32 == 4) )
      {
        LODWORD(v34) = 117;
        goto LABEL_99;
      }
      goto LABEL_113;
    }
  }
  if ( *((_DWORD *)this + 48) == 1 )
  {
    if ( (_DWORD)v25 == 108 )
      v34 = 116;
    else
      v34 = 0x200000074LL;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(
      v41,
      qword_18013A100);
    if ( ShieldProvider::AccountProtectionShield::s_fConnectGracePeriodUsed )
    {
      ShieldProvider::AccountProtectionShield::s_ullTimeOfConnect = 0;
      ShieldProvider::AccountProtectionShield::s_fConnectGracePeriodUsed = 0;
    }
    v41[16] = 0;
    CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v41);
    goto LABEL_115;
  }
  if ( v14 )
  {
    v34 = 0x100000074LL;
    goto LABEL_115;
  }
  LOBYTE(v45) = 0;
  JoinInfo = ShieldProvider::GetWarningStateDismissal(113, &v45);
  if ( JoinInfo >= 0 )
  {
    if ( !(_BYTE)v45 )
    {
      LODWORD(v34) = 113;
      goto LABEL_112;
    }
LABEL_113:
    LODWORD(v34) = 114;
LABEL_114:
    HIDWORD(v34) = 2;
    goto LABEL_115;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 70;
    goto LABEL_17;
  }
LABEL_18:
  CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v39);
LABEL_19:
  if ( v2 )
    CoTaskMemFree(v2);
  return (unsigned int)JoinInfo;
}

```

## disassembly

```asm
0x1800c9520  push    rbp
0x1800c9522  push    rbx
0x1800c9523  push    rsi
0x1800c9524  push    rdi
0x1800c9525  push    r12
0x1800c9527  push    r13
0x1800c9529  push    r14
0x1800c952b  push    r15
0x1800c952d  lea     rbp, [rsp-1Fh]
0x1800c9532  sub     rsp, 98h
0x1800c9539  mov     r15, rcx
0x1800c953c  lea     rdx, [rcx+40h]
0x1800c9540  xor     ebx, ebx
0x1800c9542  lea     rcx, [rbp+57h+var_78]
0x1800c9546  xor     esi, esi
0x1800c9548  mov     [rbp+57h+pv], rbx
0x1800c954c  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800c9551  mov     al, 1
0x1800c9553  mov     [rbp+57h+var_68], al
0x1800c9556  test    al, al
0x1800c9558  jz      loc_1800C9649
0x1800c955e  mov     rdi, [r15+0A8h]
0x1800c9565  test    rdi, rdi
0x1800c9568  jz      loc_1800C95F5
0x1800c956e  test    rbx, rbx
0x1800c9571  jz      short loc_1800C9584
0x1800c9573  mov     rcx, rbx; pv
0x1800c9576  call    cs:__imp_CoTaskMemFree
0x1800c957c  mov     [rbp+57h+pv], 0
0x1800c9584  mov     rdx, rdi; unsigned __int16 **
0x1800c9587  lea     rcx, [rbp+57h+pv]; this
0x1800c958b  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800c9590  mov     ebx, eax
0x1800c9592  test    eax, eax
0x1800c9594  js      short loc_1800C95A5
0x1800c9596  mov     esi, [r15+0C0h]
0x1800c959d  xor     al, al
0x1800c959f  mov     rbx, [rbp+57h+pv]
0x1800c95a3  jmp     short loc_1800C9553
0x1800c95a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c95ac  lea     rsi, WPP_GLOBAL_Control
0x1800c95b3  cmp     rcx, rsi
0x1800c95b6  jz      short loc_1800C95D6
0x1800c95b8  test    byte ptr [rcx+1Ch], 1
0x1800c95bc  jz      short loc_1800C95D6
0x1800c95be  mov     rcx, [rcx+10h]
0x1800c95c2  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c95c9  mov     edx, 3Ch ; '<'
0x1800c95ce  mov     r9d, ebx
0x1800c95d1  call    WPP_SF_d
0x1800c95d6  lea     rcx, [rbp+57h+var_78]
0x1800c95da  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c95df  mov     rcx, [rbp+57h+pv]; pv
0x1800c95e3  test    rcx, rcx
0x1800c95e6  jz      short loc_1800C95EE
0x1800c95e8  call    cs:__imp_CoTaskMemFree
0x1800c95ee  mov     eax, ebx
0x1800c95f0  jmp     loc_1800C9BEF
0x1800c95f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c95fc  lea     rsi, WPP_GLOBAL_Control
0x1800c9603  mov     edi, 80070015h
0x1800c9608  cmp     rcx, rsi
0x1800c960b  jz      short loc_1800C962B
0x1800c960d  test    byte ptr [rcx+1Ch], 1
0x1800c9611  jz      short loc_1800C962B
0x1800c9613  mov     edx, 3Bh ; ';'
0x1800c9618  mov     rcx, [rcx+10h]
0x1800c961c  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c9623  mov     r9d, edi
0x1800c9626  call    WPP_SF_d
0x1800c962b  lea     rcx, [rbp+57h+var_78]
0x1800c962f  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c9634  test    rbx, rbx
0x1800c9637  jz      short loc_1800C9642
0x1800c9639  mov     rcx, rbx; pv
0x1800c963c  call    cs:__imp_CoTaskMemFree
0x1800c9642  mov     eax, edi
0x1800c9644  jmp     loc_1800C9BEF
0x1800c9649  lea     rcx, [rbp+57h+var_78]
0x1800c964d  call    ??1?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@XZ; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(void)
0x1800c9652  xor     r13b, r13b
0x1800c9655  lea     rdx, [rbp+57h+pv]; bool *
0x1800c9659  xor     r12b, r12b
0x1800c965c  mov     [rbp+57h+arg_8], r13b
0x1800c9660  mov     rcx, r15; this
0x1800c9663  mov     byte ptr [rbp+57h+pv], r12b
0x1800c9667  call    ?IsRemoteSession@AccountProtectionShield@ShieldProvider@@AEAAJPEA_N@Z; ShieldProvider::AccountProtectionShield::IsRemoteSession(bool *)
0x1800c966c  cmp     byte ptr [rbp+57h+pv], r12b
0x1800c9670  jnz     loc_1800C98D1
0x1800c9676  xor     r13d, r13d
0x1800c9679  lea     r8, [rbp+57h+var_88]
0x1800c967d  lea     rdx, [rbp+57h+hMem]
0x1800c9681  mov     [rbp+57h+var_88], r13
0x1800c9685  mov     rcx, rbx
0x1800c9688  mov     [rbp+57h+hMem], r13
0x1800c968c  call    NgcEnumContainers
0x1800c9691  mov     edi, eax
0x1800c9693  test    eax, eax
0x1800c9695  jns     loc_1800C98A9
0x1800c969b  cmp     eax, 8009002Ah
0x1800c96a0  jz      short loc_1800C96F8
0x1800c96a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c96a9  lea     rsi, WPP_GLOBAL_Control
0x1800c96b0  cmp     rcx, rsi
0x1800c96b3  jz      short loc_1800C96D2
0x1800c96b5  test    byte ptr [rcx+1Ch], 1
0x1800c96b9  jz      short loc_1800C96D2
0x1800c96bb  mov     rcx, [rcx+10h]
0x1800c96bf  lea     edx, [r13+3Dh]
0x1800c96c3  mov     r9d, eax
0x1800c96c6  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c96cd  call    WPP_SF_d
0x1800c96d2  mov     rcx, [rbp+57h+hMem]; hMem
0x1800c96d6  test    rcx, rcx
0x1800c96d9  jz      short loc_1800C96E1
0x1800c96db  call    cs:__imp_LocalFree
0x1800c96e1  mov     rcx, [rbp+57h+var_88]
0x1800c96e5  test    rcx, rcx
0x1800c96e8  jz      loc_1800C9634
0x1800c96ee  call    NgcFreeEnumState
0x1800c96f3  jmp     loc_1800C9634
0x1800c96f8  lea     rdx, [rbp+57h+var_90]
0x1800c96fc  mov     [rbp+57h+arg_10], 2
0x1800c9703  mov     [rbp+57h+arg_18], 1
0x1800c970a  mov     [rbp+57h+var_90], r13
0x1800c970e  call    DsrGetJoinInfo
0x1800c9713  mov     edi, eax
0x1800c9715  test    eax, eax
0x1800c9717  jns     short loc_1800C9761
0x1800c9719  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9720  lea     rsi, WPP_GLOBAL_Control
0x1800c9727  cmp     rcx, rsi
0x1800c972a  jz      short loc_1800C974A
0x1800c972c  test    byte ptr [rcx+1Ch], 1
0x1800c9730  jz      short loc_1800C974A
0x1800c9732  mov     edx, 3Eh ; '>'
0x1800c9737  mov     rcx, [rcx+10h]
0x1800c973b  lea     r8, WPP_d58076b2fc1b308a90bad3c9c9b1a1e5_Traceguids
0x1800c9742  mov     r9d, edi
0x1800c9745  call    WPP_SF_d
0x1800c974a  mov     rcx, [rbp+57h+var_90]
0x1800c974e  test    rcx, rcx
0x1800c9751  jz      loc_1800C96D2
0x1800c9757  call    DsrFreeJoinInfo
0x1800c975c  jmp     loc_1800C96D2
0x1800c9761  mov     rdx, [rbp+57h+var_90]
0x1800c9765  lea     rax, [rbp+57h+arg_18]
0x1800c9769  mov     [rsp+0D0h+var_A8], rax
0x1800c976e  lea     r8, [rbp+57h+arg_10]
0x1800c9772  mov     rcx, rbx
0x1800c9775  test    rdx, rdx
0x1800c9778  jz      short loc_1800C97A9
0x1800c977a  mov     rdx, [rdx+20h]
0x1800c977e  call    NgcQueryEnabled
0x1800c9783  mov     edi, eax
0x1800c9785  test    eax, eax
0x1800c9787  jns     short loc_1800C97DB
0x1800c9789  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9790  lea     rsi, WPP_GLOBAL_Control
0x1800c9797  cmp     rcx, rsi
0x1800c979a  jz      short loc_1800C974A
0x1800c979c  test    byte ptr [rcx+1Ch], 1
0x1800c97a0  jz      short loc_1800C974A
0x1800c97a2  mov     edx, 3Fh ; '?'
0x1800c97a7  jmp     short loc_1800C9737
0x1800c97a9  call    NgcQueryEnabled
0x1800c97ae  mov     edi, eax
0x1800c97b0  test    eax, eax
0x1800c97b2  jns     short loc_1800C97DB
0x1800c97b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c97bb  lea     rsi, WPP_GLOBAL_Control
0x1800c97c2  cmp     rcx, rsi
0x1800c97c5  jz      short loc_1800C974A
0x1800c97c7  test    byte ptr [rcx+1Ch], 1
0x1800c97cb  jz      loc_1800C974A
0x1800c97d1  mov     edx, 40h ; '@'
0x1800c97d6  jmp     loc_1800C9737
0x1800c97db  cmp     [rbp+57h+arg_10], r13d
0x1800c97df  jz      loc_1800C9892
0x1800c97e5  cmp     [rbp+57h+arg_18], r13d
0x1800c97e9  jz      loc_1800C9892
0x1800c97ef  lea     rcx, [rbp+57h+var_80]
0x1800c97f3  mov     [rbp+57h+var_80], r13d
0x1800c97f7  call    DsrIsDeviceJoined
0x1800c97fc  mov     edi, eax
0x1800c97fe  test    eax, eax
0x1800c9800  jns     short loc_1800C982D
0x1800c9802  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9809  lea     rsi, WPP_GLOBAL_Control
0x1800c9810  cmp     rcx, rsi
0x1800c9813  jz      loc_1800C974A
0x1800c9819  test    byte ptr [rcx+1Ch], 1
0x1800c981d  jz      loc_1800C974A
0x1800c9823  mov     edx, 41h ; 'A'
0x1800c9828  jmp     loc_1800C9737
0x1800c982d  lea     eax, [rsi-5]
0x1800c9830  cmp     eax, 1
0x1800c9833  ja      short loc_1800C9866
0x1800c9835  cmp     [rbp+57h+var_80], r13d
0x1800c9839  jz      short loc_1800C9866
0x1800c983b  lea     rcx, [rbp+57h+var_A0]
0x1800c983f  mov     dword ptr [rbp+57h+var_A0], r13d
0x1800c9843  call    DsrCanCurrentUserProvisionNgcKey
0x1800c9848  test    eax, eax
0x1800c984a  jns     short loc_1800C988C
0x1800c984c  mov     edx, 2DCh; void *
0x1800c9851  mov     rcx, [rbp+5Fh]; this
0x1800c9855  lea     r8, aOnecoreAmcoreA_9; "onecore\\amcore\\antimalware\\source\\s"...
0x1800c985c  mov     r9d, eax; char *
0x1800c985f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c9864  jmp     short loc_1800C9892
0x1800c9866  lea     eax, [rsi-2]
0x1800c9869  cmp     eax, 1
0x1800c986c  ja      short loc_1800C9895
0x1800c986e  cmp     [rbp+57h+arg_10], 1
0x1800c9872  jnz     short loc_1800C9895
0x1800c9874  lea     rcx, [rbp+57h+var_A0]
0x1800c9878  mov     dword ptr [rbp+57h+var_A0], r13d
0x1800c987c  call    DsrCanCurrentUserProvisionNgcKey
0x1800c9881  test    eax, eax
0x1800c9883  jns     short loc_1800C988C
0x1800c9885  mov     edx, 2E4h
0x1800c988a  jmp     short loc_1800C9851
0x1800c988c  cmp     dword ptr [rbp+57h+var_A0], r13d
0x1800c9890  jnz     short loc_1800C9895
0x1800c9892  mov     r12b, 1
0x1800c9895  mov     rcx, [rbp+57h+var_90]
0x1800c9899  test    rcx, rcx
0x1800c989c  jz      short loc_1800C98A3
0x1800c989e  call    DsrFreeJoinInfo
0x1800c98a3  mov     rcx, [rbp+57h+hMem]
0x1800c98a7  jmp     short loc_1800C98B8
0x1800c98a9  mov     rcx, [rbp+57h+hMem]; hMem
0x1800c98ad  mov     r13b, 1
0x1800c98b0  cmp     dword ptr [rcx+10h], 2
0x1800c98b4  setnz   [rbp+57h+arg_8]
0x1800c98b8  test    rcx, rcx
0x1800c98bb  jz      short loc_1800C98C3
0x1800c98bd  call    cs:__imp_LocalFree
0x1800c98c3  mov     rcx, [rbp+57h+var_88]
0x1800c98c7  test    rcx, rcx
0x1800c98ca  jz      short loc_1800C98D1
0x1800c98cc  call    NgcFreeEnumState
0x1800c98d1  lea     rdx, [r15+40h]
0x1800c98d5  lea     rcx, [rbp+57h+var_78]
0x1800c98d9  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1800c98de  mov     al, 1
0x1800c98e0  lea     rsi, WPP_GLOBAL_Control
0x1800c98e7  mov     [rbp+57h+var_68], al
0x1800c98ea  test    al, al
0x1800c98ec  jz      loc_1800C9BD6
0x1800c98f2  cmp     byte ptr [rbp+57h+pv], 0
0x1800c98f6  jz      short loc_1800C9905
0x1800c98f8  mov     [rbp+57h+var_A0], 74h ; 't'
0x1800c9900  jmp     loc_1800C9B1B
0x1800c9905  mov     rdi, [r15+88h]
0x1800c990c  lea     rdx, [rbp+57h+arg_18]; unsigned __int16 *
0x1800c9910  mov     rcx, rbx; this
0x1800c9913  mov     [rbp+57h+arg_18], 0
0x1800c991a  call    ?MpIsAccountPasswordLess@ShieldProvider@@YAJPEAGPEAH@Z; ShieldProvider::MpIsAccountPasswordLess(ushort *,int *)
0x1800c991f  mov     r14d, eax
0x1800c9922  test    eax, eax
0x1800c9924  js      loc_1800C9B90
0x1800c992a  test    r13b, r13b
0x1800c992d  jz      loc_1800C9A29
0x1800c9933  cmp     [rbp+57h+arg_8], 0
0x1800c9937  jz      short loc_1800C9996
0x1800c9939  mov     eax, [r15+0C0h]
0x1800c9940  sub     eax, 4
0x1800c9943  test    eax, 0FFFFFFFDh
0x1800c9948  jnz     short loc_1800C9996
0x1800c994a  cmp     [rbp+57h+arg_18], 0
0x1800c994e  jz      short loc_1800C995C
0x1800c9950  mov     dword ptr [rbp+57h+var_A0], 76h ; 'v'
0x1800c9957  jmp     loc_1800C9A5D
0x1800c995c  lea     rdx, [rbp+57h+arg_10]
0x1800c9960  mov     byte ptr [rbp+57h+arg_10], 0
0x1800c9964  mov     ecx, 77h ; 'w'
0x1800c9969  call    ?GetWarningStateDismissal@ShieldProvider@@YAJW4PillarStatusFlag@@PEA_N@Z; ShieldProvider::GetWarningStateDismissal(PillarStatusFlag,bool *)
0x1800c996e  mov     edi, eax
0x1800c9970  test    eax, eax
0x1800c9972  js      loc_1800C9B48
0x1800c9978  cmp     byte ptr [rbp+57h+arg_10], 0
0x1800c997c  jnz     short loc_1800C998A
0x1800c997e  mov     dword ptr [rbp+57h+var_A0], 77h ; 'w'
0x1800c9985  jmp     loc_1800C9B04
0x1800c998a  mov     dword ptr [rbp+57h+var_A0], 78h ; 'x'
0x1800c9991  jmp     loc_1800C9B14
0x1800c9996  mov     dl, 1
0x1800c9998  mov     dword ptr [rbp+57h+var_A0], 70h ; 'p'
0x1800c999f  mov     ecx, 71h ; 'q'
0x1800c99a4  mov     dword ptr [rbp+57h+var_A0+4], 2
0x1800c99ab  call    ShieldProvider__SetOrRemoveWarningStateDismissal
0x1800c99b0  test    eax, eax
0x1800c99b2  jns     short loc_1800C99DE
0x1800c99b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c99bb  cmp     rcx, rsi
0x1800c99be  jz      short loc_1800C99DE
0x1800c99c0  test    byte ptr [rcx+1Ch], 2
0x1800c99c4  jz      short loc_1800C99DE
  ... truncated ...
```
