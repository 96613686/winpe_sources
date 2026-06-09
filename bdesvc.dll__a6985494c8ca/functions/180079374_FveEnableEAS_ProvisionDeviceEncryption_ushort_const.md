# FveEnableEAS::ProvisionDeviceEncryption(ushort const *)

- ea: `0x180079374`
- end: `0x1800797b8`
- name: `?ProvisionDeviceEncryption@FveEnableEAS@@QEAAJPEBG@Z`
- size: `1092`
- prototype: `__int64 __fastcall(FveEnableEAS *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180056580`
- `0x180075180`

## callees

- `0x180006260`
- `0x180009f60`
- `0x18000dba8`
- `0x18000dc4c`
- `0x18000f7e0`
- `0x1800282b8`
- `0x18002b6ac`
- `0x180034070`
- `0x180034d28`
- `0x1800717fc`
- `0x180071a28`
- `0x180072548`
- `0x180072908`
- `0x180075754`
- `0x180077798`
- `0x180079374`
- `0x180079b44`

## import_xrefs

- `FVEAPI!FveCommitChangesEx` at `0x1800796d9`
- `FVEAPI!FveCommitChangesEx` at `0x1800796d9`
- `FVEAPI!FveCommitChanges` at `0x18007971f`
- `FVEAPI!FveCommitChanges` at `0x18007971f`

## string_xrefs

- `0x18007941d`: `GetFveVolumePath`
- `0x1800795c9`: `GetReadWriteVolumeHandle`
- `0x1800796ae`: `FvepCreateTPMProtector`
- `0x180079757`: `FveCommitChanges`
- `0x180079711`: `FveCommitChangesEx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FveEnableEAS::ProvisionDeviceEncryption(FveEasUtil **this, const unsigned __int16 *a2)
{
  unsigned int v4; // r8d
  unsigned int FveVolumePath; // eax
  int v6; // ebx
  const char *v7; // rax
  __int64 v8; // rdx
  unsigned int RequiredProvisioningSteps; // eax
  PVOID *v10; // rcx
  char v11; // al
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int FVEVolumeHandle; // eax
  unsigned int v15; // eax
  char v16; // al
  unsigned int v17; // eax
  unsigned int TPMProtector; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  const char *v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  void **v24; // [rsp+38h] [rbp-C8h] BYREF
  void *v25; // [rsp+40h] [rbp-C0h]
  unsigned __int16 v26[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  memset_0(v26, 0, 0x208u);
  v23 = 0;
  v24 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v25 = 0;
  FveVolumePath = CFveDriveType::GetFveVolumePath(a2, v26, v4);
  v6 = FveVolumePath;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, FveVolumePath);
  if ( v6 < 0 )
  {
    v7 = "GetFveVolumePath";
    v8 = 363;
LABEL_67:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v8,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)(unsigned int)v6,
      (int)v7,
      v22);
    goto LABEL_68;
  }
  RequiredProvisioningSteps = FveEasUtil::GetRequiredProvisioningSteps(
                                this[1],
                                v26,
                                (enum RequiredProvisioningSteps *)&v23);
  v6 = RequiredProvisioningSteps;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
      RequiredProvisioningSteps);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 < 0 )
  {
    v7 = "GetRequiredProvisioningSteps";
    v8 = 370;
    goto LABEL_67;
  }
  v11 = v23;
  if ( v23 )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
    {
      WPP_SF_SD(
        (unsigned int)v10[2],
        45,
        (unsigned int)&WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
        (unsigned int)v26,
        v23);
      v11 = v23;
    }
    if ( (v11 & 3) != 0 )
    {
      v12 = FveEnableEAS::BackupRecoveryPassword(this, v26);
      v6 = v12;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v12);
      if ( v6 < 0 )
      {
        v7 = "BackupRecoveryPassword";
        v8 = 389;
        goto LABEL_67;
      }
      v11 = v23;
    }
    if ( (v11 & 8) != 0 )
    {
      v13 = FveEasUtil::EnableAutoUnlock(v26);
      v6 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v13);
      if ( v6 < 0 )
      {
        v7 = "EnableAutoUnlock";
        v8 = 394;
        goto LABEL_67;
      }
      v11 = v23;
    }
    if ( (v11 & 0x14) != 0 )
    {
      FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(v26, &v24, 0);
      v6 = FVEVolumeHandle;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
          FVEVolumeHandle);
      if ( v6 < 0 )
      {
        v7 = "GetReadWriteVolumeHandle";
        v8 = 401;
        goto LABEL_67;
      }
      v15 = FveEasUtil::EnsureVolumeDEManaged(&v24);
      v6 = v15;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v15);
      if ( v6 < 0 )
      {
        v7 = "EnsureVolumeDEManaged";
        v8 = 403;
        goto LABEL_67;
      }
      v16 = v23;
      if ( (v23 & 0x10) != 0 )
      {
        v17 = CFveApiWrapper::DeleteClearKey(v25);
        v6 = v17;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v17);
        if ( v6 < 0 )
        {
          v7 = "EnsureVolumeDEManaged";
          v8 = 413;
          goto LABEL_67;
        }
        v16 = v23;
      }
      if ( (v16 & 4) != 0 )
      {
        TPMProtector = FvepCreateTPMProtector(v25);
        v6 = TPMProtector;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            TPMProtector);
        if ( v6 < 0 )
        {
          v7 = "FvepCreateTPMProtector";
          v8 = 417;
          goto LABEL_67;
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::GetImpl'::`2'::impl) )
      {
        v19 = FveCommitChangesEx(v25, 10);
        v6 = v19;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v19);
        if ( v6 < 0 )
        {
          v7 = "FveCommitChangesEx";
          v8 = 421;
          goto LABEL_67;
        }
      }
      else
      {
        v20 = FveCommitChanges(v25);
        v6 = v20;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v20);
        if ( v6 < 0 )
        {
          v7 = "FveCommitChanges";
          v8 = 423;
          goto LABEL_67;
        }
      }
    }
  }
  else if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 )
  {
    WPP_SF_S(v10[2], (unsigned int)(v23 + 44), &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v26);
  }
LABEL_68:
  v24 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v24);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180079374  mov     [rsp-8+arg_10], rbx
0x180079379  push    rbp
0x18007937a  push    rdi
0x18007937b  push    r12
0x18007937d  push    r14
0x18007937f  push    r15
0x180079381  lea     rbp, [rsp-170h]
0x180079389  sub     rsp, 270h
0x180079390  mov     rax, cs:__security_cookie
0x180079397  xor     rax, rsp
0x18007939a  mov     [rbp+190h+var_30], rax
0x1800793a1  mov     rbx, rdx
0x1800793a4  mov     rdi, rcx
0x1800793a7  xor     edx, edx; Val
0x1800793a9  mov     r8d, 208h; Size
0x1800793af  lea     rcx, [rsp+290h+var_240]; void *
0x1800793b4  call    memset_0
0x1800793b9  mov     [rsp+290h+var_260], 0
0x1800793c1  lea     r12, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x1800793c8  mov     [rsp+290h+var_258], r12
0x1800793cd  mov     [rsp+290h+var_250], 0
0x1800793d6  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x1800793db  mov     rcx, rbx; unsigned __int16 *
0x1800793de  call    ?GetFveVolumePath@CFveDriveType@@SAJPEBGPEAGK@Z; CFveDriveType::GetFveVolumePath(ushort const *,ushort *,ulong)
0x1800793e3  mov     ebx, eax
0x1800793e5  lea     r14, WPP_GLOBAL_Control
0x1800793ec  lea     r15, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x1800793f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800793fa  cmp     rcx, r14
0x1800793fd  jz      short loc_180079419
0x1800793ff  test    byte ptr [rcx+1Ch], 40h
0x180079403  jz      short loc_180079419
0x180079405  mov     edx, 2Ah ; '*'
0x18007940a  mov     r9d, eax
0x18007940d  mov     r8, r15
0x180079410  mov     rcx, [rcx+10h]
0x180079414  call    WPP_SF_d
0x180079419  test    ebx, ebx
0x18007941b  jns     short loc_18007942E
0x18007941d  lea     rax, aGetfvevolumepa; "GetFveVolumePath"
0x180079424  mov     edx, 16Bh
0x180079429  jmp     loc_180079763
0x18007942e  lea     r8, [rsp+290h+var_260]; enum RequiredProvisioningSteps *
0x180079433  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x180079438  mov     rcx, [rdi+8]; this
0x18007943c  call    ?GetRequiredProvisioningSteps@FveEasUtil@@QEBAJPEBGPEAW4RequiredProvisioningSteps@@@Z; FveEasUtil::GetRequiredProvisioningSteps(ushort const *,RequiredProvisioningSteps *)
0x180079441  mov     ebx, eax
0x180079443  mov     rcx, cs:WPP_GLOBAL_Control
0x18007944a  cmp     rcx, r14
0x18007944d  jz      short loc_180079470
0x18007944f  test    byte ptr [rcx+1Ch], 40h
0x180079453  jz      short loc_180079470
0x180079455  mov     edx, 2Bh ; '+'
0x18007945a  mov     r9d, eax
0x18007945d  mov     r8, r15
0x180079460  mov     rcx, [rcx+10h]
0x180079464  call    WPP_SF_d
0x180079469  mov     rcx, cs:WPP_GLOBAL_Control
0x180079470  test    ebx, ebx
0x180079472  jns     short loc_180079485
0x180079474  lea     rax, aGetrequiredpro; "GetRequiredProvisioningSteps"
0x18007947b  mov     edx, 172h
0x180079480  jmp     loc_180079763
0x180079485  mov     eax, [rsp+290h+var_260]
0x180079489  test    eax, eax
0x18007948b  jnz     short loc_1800794B9
0x18007948d  cmp     rcx, r14
0x180079490  jz      loc_18007977F
0x180079496  test    byte ptr [rcx+1Ch], 8
0x18007949a  jz      loc_18007977F
0x1800794a0  lea     edx, [rax+2Ch]
0x1800794a3  lea     r9, [rsp+290h+var_240]
0x1800794a8  mov     r8, r15
0x1800794ab  mov     rcx, [rcx+10h]
0x1800794af  call    WPP_SF_S
0x1800794b4  jmp     loc_18007977F
0x1800794b9  cmp     rcx, r14
0x1800794bc  jz      short loc_1800794E2
0x1800794be  test    byte ptr [rcx+1Ch], 8
0x1800794c2  jz      short loc_1800794E2
0x1800794c4  mov     edx, 2Dh ; '-'
0x1800794c9  mov     [rsp+290h+var_270], eax
0x1800794cd  lea     r9, [rsp+290h+var_240]
0x1800794d2  mov     r8, r15
0x1800794d5  mov     rcx, [rcx+10h]
0x1800794d9  call    WPP_SF_SD
0x1800794de  mov     eax, [rsp+290h+var_260]
0x1800794e2  test    al, 3
0x1800794e4  jz      short loc_180079534
0x1800794e6  lea     rdx, [rsp+290h+var_240]; unsigned __int16 *
0x1800794eb  mov     rcx, rdi; this
0x1800794ee  call    ?BackupRecoveryPassword@FveEnableEAS@@QEAAJPEBG@Z; FveEnableEAS::BackupRecoveryPassword(ushort const *)
0x1800794f3  mov     ebx, eax
0x1800794f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800794fc  cmp     rcx, r14
0x1800794ff  jz      short loc_18007951B
0x180079501  test    byte ptr [rcx+1Ch], 40h
0x180079505  jz      short loc_18007951B
0x180079507  mov     edx, 2Eh ; '.'
0x18007950c  mov     r9d, eax
0x18007950f  mov     r8, r15
0x180079512  mov     rcx, [rcx+10h]
0x180079516  call    WPP_SF_d
0x18007951b  test    ebx, ebx
0x18007951d  jns     short loc_180079530
0x18007951f  lea     rax, aBackuprecovery_1; "BackupRecoveryPassword"
0x180079526  mov     edx, 185h
0x18007952b  jmp     loc_180079763
0x180079530  mov     eax, [rsp+290h+var_260]
0x180079534  test    al, 8
0x180079536  jz      short loc_180079583
0x180079538  lea     rcx, [rsp+290h+var_240]; unsigned __int16 *
0x18007953d  call    ?EnableAutoUnlock@FveEasUtil@@SAJPEBG@Z; FveEasUtil::EnableAutoUnlock(ushort const *)
0x180079542  mov     ebx, eax
0x180079544  mov     rcx, cs:WPP_GLOBAL_Control
0x18007954b  cmp     rcx, r14
0x18007954e  jz      short loc_18007956A
0x180079550  test    byte ptr [rcx+1Ch], 40h
0x180079554  jz      short loc_18007956A
0x180079556  mov     edx, 2Fh ; '/'
0x18007955b  mov     r9d, eax
0x18007955e  mov     r8, r15
0x180079561  mov     rcx, [rcx+10h]
0x180079565  call    WPP_SF_d
0x18007956a  test    ebx, ebx
0x18007956c  jns     short loc_18007957F
0x18007956e  lea     rax, aEnableautounlo; "EnableAutoUnlock"
0x180079575  mov     edx, 18Ah
0x18007957a  jmp     loc_180079763
0x18007957f  mov     eax, [rsp+290h+var_260]
0x180079583  test    al, 14h
0x180079585  jz      loc_18007977F
0x18007958b  xor     r8d, r8d
0x18007958e  lea     rdx, [rsp+290h+var_258]
0x180079593  lea     rcx, [rsp+290h+var_240]
0x180079598  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x18007959d  mov     ebx, eax
0x18007959f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800795a6  cmp     rcx, r14
0x1800795a9  jz      short loc_1800795C5
0x1800795ab  test    byte ptr [rcx+1Ch], 40h
0x1800795af  jz      short loc_1800795C5
0x1800795b1  mov     edx, 30h ; '0'
0x1800795b6  mov     r9d, eax
0x1800795b9  mov     r8, r15
0x1800795bc  mov     rcx, [rcx+10h]
0x1800795c0  call    WPP_SF_d
0x1800795c5  test    ebx, ebx
0x1800795c7  jns     short loc_1800795DA
0x1800795c9  lea     rax, aGetreadwritevo; "GetReadWriteVolumeHandle"
0x1800795d0  mov     edx, 191h
0x1800795d5  jmp     loc_180079763
0x1800795da  lea     rcx, [rsp+290h+var_258]
0x1800795df  call    ?EnsureVolumeDEManaged@FveEasUtil@@SAJAEBV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@@Z; FveEasUtil::EnsureVolumeDEManaged(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> const &)
0x1800795e4  mov     ebx, eax
0x1800795e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800795ed  cmp     rcx, r14
0x1800795f0  jz      short loc_18007960C
0x1800795f2  test    byte ptr [rcx+1Ch], 40h
0x1800795f6  jz      short loc_18007960C
0x1800795f8  mov     edx, 31h ; '1'
0x1800795fd  mov     r9d, eax
0x180079600  mov     r8, r15
0x180079603  mov     rcx, [rcx+10h]
0x180079607  call    WPP_SF_d
0x18007960c  test    ebx, ebx
0x18007960e  jns     short loc_180079621
0x180079610  lea     rax, aEnsurevolumede; "EnsureVolumeDEManaged"
0x180079617  mov     edx, 193h
0x18007961c  jmp     loc_180079763
0x180079621  mov     eax, [rsp+290h+var_260]
0x180079625  test    al, 10h
0x180079627  jz      short loc_180079674
0x180079629  mov     rcx, [rsp+290h+var_250]; void *
0x18007962e  call    ?DeleteClearKey@CFveApiWrapper@@SAJPEAX@Z; CFveApiWrapper::DeleteClearKey(void *)
0x180079633  mov     ebx, eax
0x180079635  mov     rcx, cs:WPP_GLOBAL_Control
0x18007963c  cmp     rcx, r14
0x18007963f  jz      short loc_18007965B
0x180079641  test    byte ptr [rcx+1Ch], 40h
0x180079645  jz      short loc_18007965B
0x180079647  mov     edx, 32h ; '2'
0x18007964c  mov     r9d, eax
0x18007964f  mov     r8, r15
0x180079652  mov     rcx, [rcx+10h]
0x180079656  call    WPP_SF_d
0x18007965b  test    ebx, ebx
0x18007965d  jns     short loc_180079670
0x18007965f  lea     rax, aEnsurevolumede; "EnsureVolumeDEManaged"
0x180079666  mov     edx, 19Dh
0x18007966b  jmp     loc_180079763
0x180079670  mov     eax, [rsp+290h+var_260]
0x180079674  test    al, 4
0x180079676  jz      short loc_1800796BF
0x180079678  mov     rcx, [rsp+290h+var_250]; void *
0x18007967d  call    ?FvepCreateTPMProtector@@YAJPEAX@Z; FvepCreateTPMProtector(void *)
0x180079682  mov     ebx, eax
0x180079684  mov     rcx, cs:WPP_GLOBAL_Control
0x18007968b  cmp     rcx, r14
0x18007968e  jz      short loc_1800796AA
0x180079690  test    byte ptr [rcx+1Ch], 40h
0x180079694  jz      short loc_1800796AA
0x180079696  mov     edx, 33h ; '3'
0x18007969b  mov     r9d, eax
0x18007969e  mov     r8, r15
0x1800796a1  mov     rcx, [rcx+10h]
0x1800796a5  call    WPP_SF_d
0x1800796aa  test    ebx, ebx
0x1800796ac  jns     short loc_1800796BF
0x1800796ae  lea     rax, aFvepcreatetpmp; "FvepCreateTPMProtector"
0x1800796b5  mov     edx, 1A1h
0x1800796ba  jmp     loc_180079763
0x1800796bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::GetImpl(void)'::`2'::impl
0x1800796c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::__private_IsEnabled(void)
0x1800796cb  mov     rcx, [rsp+290h+var_250]
0x1800796d0  test    al, al
0x1800796d2  jz      short loc_18007971F
0x1800796d4  mov     edx, 0Ah
0x1800796d9  call    cs:__imp_FveCommitChangesEx
0x1800796e0  nop     dword ptr [rax+rax+00h]
0x1800796e5  mov     ebx, eax
0x1800796e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796ee  cmp     rcx, r14
0x1800796f1  jz      short loc_18007970D
0x1800796f3  test    byte ptr [rcx+1Ch], 40h
0x1800796f7  jz      short loc_18007970D
0x1800796f9  mov     edx, 34h ; '4'
0x1800796fe  mov     r9d, eax
0x180079701  mov     r8, r15
0x180079704  mov     rcx, [rcx+10h]
0x180079708  call    WPP_SF_d
0x18007970d  test    ebx, ebx
0x18007970f  jns     short loc_18007977F
0x180079711  lea     rax, aFvecommitchang; "FveCommitChangesEx"
0x180079718  mov     edx, 1A5h
0x18007971d  jmp     short loc_180079763
0x18007971f  call    cs:__imp_FveCommitChanges
0x180079726  nop     dword ptr [rax+rax+00h]
0x18007972b  mov     ebx, eax
0x18007972d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079734  cmp     rcx, r14
0x180079737  jz      short loc_180079753
0x180079739  test    byte ptr [rcx+1Ch], 40h
0x18007973d  jz      short loc_180079753
0x18007973f  mov     edx, 35h ; '5'
0x180079744  mov     r9d, eax
0x180079747  mov     r8, r15
0x18007974a  mov     rcx, [rcx+10h]
0x18007974e  call    WPP_SF_d
0x180079753  test    ebx, ebx
0x180079755  jns     short loc_18007977F
0x180079757  lea     rax, aFvecommitchang_0; "FveCommitChanges"
0x18007975e  mov     edx, 1A7h; void *
0x180079763  mov     qword ptr [rsp+290h+var_270], rax; int
0x180079768  mov     r9d, ebx; char *
0x18007976b  lea     r8, aBaseNgscbCorne_2; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180079772  mov     rcx, [rbp+198h]; this
0x180079779  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007977e  nop
0x18007977f  mov     [rsp+290h+var_258], r12
0x180079784  lea     rcx, [rsp+290h+var_258]
0x180079789  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x18007978e  mov     eax, ebx
0x180079790  mov     rcx, [rbp+190h+var_30]
0x180079797  xor     rcx, rsp; StackCookie
0x18007979a  call    __security_check_cookie
0x18007979f  mov     rbx, [rsp+290h+arg_10]
0x1800797a7  add     rsp, 270h
0x1800797ae  pop     r15
0x1800797b0  pop     r14
0x1800797b2  pop     r12
0x1800797b4  pop     rdi
0x1800797b5  pop     rbp
0x1800797b6  retn
```
