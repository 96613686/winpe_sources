# FveEnableEAS::BackupRecoveryPassword(ushort const *)

- ea: `0x180075754`
- end: `0x1800771a2`
- name: `?BackupRecoveryPassword@FveEnableEAS@@QEAAJPEBG@Z`
- size: `6734`
- prototype: `__int64 __fastcall(FveEasUtil **this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180079374`

## callees

- `0x180001fe8`
- `0x180003864`
- `0x180009f30`
- `0x180009f60`
- `0x18000dba8`
- `0x18000dc4c`
- `0x180024468`
- `0x18002b6ac`
- `0x180034070`
- `0x180034d28`
- `0x18006a26c`
- `0x18006a4bc`
- `0x18006a594`
- `0x180071a28`
- `0x180072150`
- `0x1800730f0`
- `0x180075754`
- `0x1800771a8`
- `0x180079b08`
- `0x180079cb8`
- `0x180079d1c`
- `0x180079df4`
- `0x180079ee4`
- `0x18007e010`

## import_xrefs

- `FVEAPI!FveBackupRecoveryInformationToADEx` at `0x180075f22`
- `FVEAPI!FveBackupRecoveryInformationToADEx` at `0x180075f22`
- `FVEAPI!FveGetIdentity` at `0x1800759de`
- `FVEAPI!FveGetIdentity` at `0x1800759de`
- `FVEAPI!FveGetVolumeNameW` at `0x180075a40`
- `FVEAPI!FveGetVolumeNameW` at `0x180075a40`
- `FVESKYBACKUP!FveBackupRecoveryPasswordToCloudDomain` at `0x1800760b4`
- `FVESKYBACKUP!FveBackupRecoveryPasswordToCloudDomain` at `0x1800760b4`

## string_xrefs

- `0x1800762ff`: `VolumePath`
- `0x180076542`: `VolumePath`
- `0x1800766d8`: `VolumePath`
- `0x1800768aa`: `VolumePath`
- `0x180076b77`: `VolumePath`
- `0x180076d40`: `VolumePath`
- `0x180076ee6`: `VolumePath`
- `0x1800770c8`: `VolumePath`
- `0x1800758a3`: `GetFveVolumePath`
- `0x180075ed5`: `GetReadWriteVolumeHandle`
- `0x18007596e`: `GetReadOnlyVolumeHandle`
- `0x18007591d`: `CreateVolumeRecoveryPassword`
- `0x180075ad7`: `GetVolumeMountPoint`
- `0x180075e18`: `ADBackupStatusCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FveEnableEAS::BackupRecoveryPassword(FveEasUtil **this, const unsigned __int16 *a2)
{
  __int64 v4; // r14
  unsigned int v5; // r8d
  unsigned int FveVolumePath; // eax
  int v7; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // r8
  unsigned int FVEVolumeHandle; // eax
  unsigned int StatusFlags; // eax
  unsigned int Identity; // eax
  unsigned int VolumeNameW; // eax
  unsigned int v16; // r8d
  unsigned int VolumeMountPoint; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  PVOID *v20; // r10
  unsigned __int8 v21; // r13
  unsigned __int8 v22; // r12
  unsigned int v23; // r14d
  FveEasUtil *v24; // rcx
  unsigned __int64 v25; // r9
  const char *v26; // rax
  __int64 v27; // rdx
  FveEasUtil *v28; // rcx
  unsigned __int64 v29; // r9
  const char *v30; // rax
  __int64 v31; // rdx
  FveEasUtil *v32; // rcx
  unsigned __int64 v33; // r9
  const char *v34; // rax
  __int64 v35; // rdx
  unsigned int v36; // eax
  const char *v37; // rax
  __int64 v38; // rdx
  int v39; // eax
  PVOID *v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // r8
  __int64 v43; // r9
  int v44; // eax
  const unsigned __int16 *v45; // rdx
  const unsigned __int16 *v46; // rdx
  const char *v47; // rax
  __int64 v48; // rdx
  const unsigned __int16 *v49; // rdx
  const wchar_t *v50; // rdx
  const unsigned __int16 *v51; // rdx
  __int64 v52; // rdx
  const char *v53; // rax
  const unsigned __int16 *v54; // rdx
  _BYTE *v55; // rax
  const unsigned __int16 *v57; // rdx
  const unsigned __int16 *v58; // rdx
  const unsigned __int16 *v59; // rdx
  const wchar_t *v60; // rdx
  const unsigned __int16 *v61; // rdx
  const unsigned __int16 *v62; // rdx
  const unsigned __int16 *v63; // rdx
  struct _GUID *v64; // [rsp+20h] [rbp-E0h]
  unsigned int v65; // [rsp+20h] [rbp-E0h]
  unsigned int v66; // [rsp+20h] [rbp-E0h]
  unsigned int v67; // [rsp+20h] [rbp-E0h]
  unsigned int v68; // [rsp+20h] [rbp-E0h]
  unsigned int v69; // [rsp+20h] [rbp-E0h]
  unsigned int v70; // [rsp+20h] [rbp-E0h]
  struct _GUID *v71; // [rsp+20h] [rbp-E0h]
  unsigned int v72; // [rsp+20h] [rbp-E0h]
  unsigned int v73; // [rsp+20h] [rbp-E0h]
  unsigned int v74; // [rsp+20h] [rbp-E0h]
  unsigned int v75; // [rsp+20h] [rbp-E0h]
  unsigned int v76; // [rsp+20h] [rbp-E0h]
  unsigned int v77; // [rsp+20h] [rbp-E0h]
  char *v78; // [rsp+28h] [rbp-D8h]
  unsigned __int16 v79[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v80; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v81; // [rsp+70h] [rbp-90h]
  _QWORD ***v82; // [rsp+78h] [rbp-88h] BYREF
  _QWORD **v83; // [rsp+80h] [rbp-80h]
  __int64 v84; // [rsp+88h] [rbp-78h] BYREF
  __int64 v85; // [rsp+90h] [rbp-70h]
  __int64 v86; // [rsp+98h] [rbp-68h]
  _QWORD **v87; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD **v88; // [rsp+A8h] [rbp-58h]
  const wchar_t *v89; // [rsp+B0h] [rbp-50h]
  const wchar_t *v90; // [rsp+B8h] [rbp-48h]
  struct _GUID *v91; // [rsp+C0h] [rbp-40h]
  __int64 v92; // [rsp+C8h] [rbp-38h]
  _QWORD **v93; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD **v94; // [rsp+D8h] [rbp-28h]
  const wchar_t *v95; // [rsp+E0h] [rbp-20h]
  const wchar_t *v96; // [rsp+E8h] [rbp-18h]
  struct _GUID *v97; // [rsp+F0h] [rbp-10h]
  __int64 v98; // [rsp+F8h] [rbp-8h]
  char *v99; // [rsp+100h] [rbp+0h] BYREF
  _QWORD *v100; // [rsp+108h] [rbp+8h] BYREF
  _QWORD **v101; // [rsp+110h] [rbp+10h]
  __int128 v102; // [rsp+118h] [rbp+18h]
  __int128 v103; // [rsp+128h] [rbp+28h]
  _QWORD *v104; // [rsp+138h] [rbp+38h] BYREF
  _QWORD *v105; // [rsp+140h] [rbp+40h]
  __int128 v106; // [rsp+148h] [rbp+48h]
  __int128 v107; // [rsp+158h] [rbp+58h]
  char v108[8]; // [rsp+168h] [rbp+68h] BYREF
  char *v109; // [rsp+170h] [rbp+70h] BYREF
  void **v110; // [rsp+178h] [rbp+78h] BYREF
  void *v111; // [rsp+180h] [rbp+80h]
  _QWORD *v112; // [rsp+188h] [rbp+88h] BYREF
  _QWORD *v113; // [rsp+190h] [rbp+90h]
  __int128 v114; // [rsp+198h] [rbp+98h]
  __int128 v115; // [rsp+1A8h] [rbp+A8h]
  int v116; // [rsp+1B8h] [rbp+B8h] BYREF
  char v117[8]; // [rsp+1C0h] [rbp+C0h] BYREF
  struct _GUID v118; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v119; // [rsp+1D8h] [rbp+D8h] BYREF
  _BYTE v120[592]; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v121[4]; // [rsp+440h] [rbp+340h] BYREF
  __int64 v122; // [rsp+448h] [rbp+348h]
  WCHAR szVolumeName[264]; // [rsp+450h] [rbp+350h] BYREF
  char v124[2]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v125[264]; // [rsp+870h] [rbp+770h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AC8h] [rbp+9C8h]

  v99 = 0;
  *(_QWORD *)v108 = 0;
  LODWORD(v109) = 0;
  *(_QWORD *)v117 = 0;
  memset_0(szVolumeName, 0, 0x208u);
  v116 = 260;
  memset_0(v125, 0, 0x208u);
  v119 = 0;
  memset_0(v124, 0, 0x208u);
  v118 = 0;
  v4 = 584;
  memset_0(v120, 0, 0x248u);
  v110 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v111 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
  FveVolumePath = CFveDriveType::GetFveVolumePath(a2, v125, v5);
  v7 = FveVolumePath;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, FveVolumePath);
  if ( v7 >= 0 )
  {
    v10 = FveEasUtil::CreateVolumeRecoveryPassword(this[1], v125, &v118, (struct _FVE_AUTH_ELEMENT *)v120);
    v7 = v10;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v10);
    if ( v7 < 0 )
    {
      v8 = "CreateVolumeRecoveryPassword";
      v9 = 679;
      goto LABEL_9;
    }
    LOBYTE(v11) = 1;
    FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(v125, &v110, v11);
    v7 = FVEVolumeHandle;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
        FVEVolumeHandle);
    if ( v7 < 0 )
    {
      v8 = "GetReadOnlyVolumeHandle";
      v9 = 686;
      goto LABEL_9;
    }
    StatusFlags = CFveApiWrapper::GetStatusFlags(v111, (unsigned int *)&v99 + 1);
    v7 = StatusFlags;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, StatusFlags);
    if ( v7 < 0 )
    {
      v8 = "GetStatusFlags";
      v9 = 688;
      goto LABEL_9;
    }
    Identity = FveGetIdentity(v111, &v119);
    v7 = Identity;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, Identity);
    if ( v7 < 0 )
    {
      v8 = "FveGetIdentity";
      v9 = 689;
      goto LABEL_9;
    }
    VolumeNameW = FveGetVolumeNameW(v111, &v116, szVolumeName);
    v7 = VolumeNameW;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, VolumeNameW);
    if ( v7 < 0 )
    {
      v8 = "FveGetVolumeNameW";
      v9 = 693;
      goto LABEL_9;
    }
    VolumeMountPoint = FveEasUtil::GetVolumeMountPoint(szVolumeName, (unsigned __int16 *)v124, v16);
    v7 = VolumeMountPoint;
    v20 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
        VolumeMountPoint);
      v20 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 < 0 )
    {
      v8 = "GetVolumeMountPoint";
      v9 = 696;
      goto LABEL_9;
    }
    v21 = 0;
    v22 = 0;
    if ( (WORD2(v99) & 0x4000) != 0 )
      v23 = 0;
    else
      v23 = ((HIDWORD(v99) & 0x400000) != 0) + 1;
    v24 = this[2];
    if ( !v24 )
    {
LABEL_53:
      v28 = this[4];
      if ( !v28 )
        goto LABEL_63;
      v7 = (*(__int64 (__fastcall **)(FveEasUtil *, _QWORD, __int128 *, struct _GUID *, char **, char *))(*(_QWORD *)v28 + 8LL))(
             v28,
             v23,
             &v119,
             &v118,
             &v109,
             v117);
      v29 = (unsigned int)v109;
      if ( v7 < 0 )
      {
        if ( v7 != -2147024894 )
        {
          v30 = "GetRecoveryPasswordBackupStatusMSA";
          v29 = (unsigned int)v7;
          v31 = 737;
          goto LABEL_61;
        }
      }
      else if ( !(_DWORD)v109 )
      {
        v22 = 1;
LABEL_62:
        v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_63:
        v32 = this[6];
        if ( !v32 )
          goto LABEL_75;
        v7 = (*(__int64 (__fastcall **)(FveEasUtil *, _QWORD, __int128 *, struct _GUID *, char **, char *))(*(_QWORD *)v32 + 8LL))(
               v32,
               v23,
               &v119,
               &v118,
               &v99,
               v108);
        v33 = (unsigned int)v99;
        if ( v7 < 0 )
        {
          if ( v7 != -2147024894 )
          {
            v34 = "GetRecoveryPasswordBackupStatusAD";
            v33 = (unsigned int)v7;
            v35 = 759;
            goto LABEL_73;
          }
        }
        else if ( !(_DWORD)v99 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF__guid_SSi(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124, v108[0]);
          goto LABEL_165;
        }
        if ( (_DWORD)v99 == -2147024894 )
        {
LABEL_74:
          v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_75:
          if ( v21 )
          {
            if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 )
            {
              WPP_SF__guid_SSi((TRACEHANDLE)v20[2], (__int64)szVolumeName, (__int64)v124, v108[0]);
              v20 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( !this[4] )
              goto LABEL_165;
            if ( v22 )
            {
              if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 )
                WPP_SF__guid_SSi((TRACEHANDLE)v20[2], (__int64)szVolumeName, (__int64)v124, v117[0]);
              goto LABEL_165;
            }
          }
          else if ( v22 && !this[2] )
          {
            goto LABEL_165;
          }
          if ( *((_BYTE *)this + 5) )
          {
            if ( !this[6] )
            {
              v7 = -2144272145;
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x33F,
                (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
                (const char *)0x803100EFLL,
                (int)"ADBackupStatusCache",
                v78);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids);
              goto LABEL_165;
            }
            *(_QWORD *)v121 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
            v122 = 0;
            v36 = FveEasUtil::I_GetFVEVolumeHandle(v125, v121, 0);
            v7 = v36;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v36);
            if ( v7 < 0 )
            {
              v37 = "GetReadWriteVolumeHandle";
              v38 = 847;
              goto LABEL_96;
            }
            v7 = FveBackupRecoveryInformationToADEx(v122, &v118, 8);
            if ( v7 == 1 )
            {
              v7 = -2144272171;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  78,
                  &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
                  2150695125LL);
            }
            v39 = (**(__int64 (__fastcall ***)(FveEasUtil *, _QWORD, __int128 *, struct _GUID *, int))this[6])(
                    this[6],
                    v23,
                    &v119,
                    &v118,
                    v7);
            if ( v39 < 0 )
            {
              v40 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              {
LABEL_110:
                if ( v7 >= 0 )
                {
                  if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 8) != 0 )
                    WPP_SF__guid_SS((TRACEHANDLE)v40[2], (__int64)szVolumeName, (__int64)v124);
                  goto LABEL_97;
                }
                v37 = "FveBackupRecoveryInformationToADEx";
                v38 = 864;
LABEL_96:
                wil::details::in1diag3::Log_HrMsg(
                  retaddr,
                  (void *)v38,
                  (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
                  (const char *)(unsigned int)v7,
                  (int)v37,
                  v78);
LABEL_97:
                *(_QWORD *)v121 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
                Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(v121);
LABEL_165:
                v4 = 584;
                goto LABEL_166;
              }
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              {
LABEL_107:
                if ( v40 != &WPP_GLOBAL_Control && (*((_BYTE *)v40 + 28) & 0x40) != 0 )
                {
                  WPP_SF_d(v40[2], 80, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, (unsigned int)v7);
                  v40 = (PVOID *)WPP_GLOBAL_Control;
                }
                goto LABEL_110;
              }
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                79,
                &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
                (unsigned int)v39);
            }
            v40 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_107;
          }
          if ( !*((_BYTE *)this + 6) )
          {
            v78 = v120;
            v71 = &v118;
            v7 = FveEnableEAS::BackupRecoveryPasswordWithRetry(this, v111, v23, &v119);
            if ( v7 >= 0 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetImpl'::`2'::impl) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF__guid_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124);
                v80 = 0;
                v84 = 0;
                v85 = 0;
                v86 = 0;
                *(_QWORD *)v121 = 0x5200440050LL;
                v95 = L"IdentityGuid";
                v96 = L"GUID";
                v97 = (struct _GUID *)&v119;
                v98 = 16;
                v94 = &v82;
                v82 = &v93;
                v106 = 0;
                v107 = 0;
                FveApiEventLogDeclareWSTRING(
                  (struct _FVEAPI_EVENT_DATA *)&v104,
                  L"GUID",
                  L"VolumePath",
                  szVolumeName,
                  (unsigned int)v71);
                v105 = &v93;
                v93 = &v104;
                v102 = 0;
                v103 = 0;
                FveApiEventLogDeclareWSTRING(
                  (struct _FVEAPI_EVENT_DATA *)&v100,
                  v57,
                  L"VolumeDriveLetter",
                  (const unsigned __int16 *)v124,
                  v72);
                v101 = &v104;
                v104 = &v100;
                v89 = L"ProtectorGUID";
                v90 = v58;
                v91 = &v118;
                v92 = 16;
                v88 = &v100;
                v100 = &v87;
                v114 = 0;
                v115 = 0;
                FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v112, v58, L"BackendName", v121, v73);
                v112 = &v82;
                v113 = &v87;
                v87 = &v112;
                v83 = &v112;
                v81 = FVE_OP_PDR_BACKUP_SUCCESS;
                FveEventLogHandle::LogFveApiEvent(
                  (FveEventLogHandle *)&v84,
                  (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v80);
                FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v84);
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF__guid_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124);
                v80 = 0;
                v84 = 0;
                v85 = 0;
                v86 = 0;
                v95 = L"IdentityGuid";
                v96 = L"GUID";
                v97 = (struct _GUID *)&v119;
                v98 = 16;
                v94 = &v82;
                v82 = &v93;
                v106 = 0;
                v107 = 0;
                FveApiEventLogDeclareWSTRING(
                  (struct _FVEAPI_EVENT_DATA *)&v104,
                  L"GUID",
                  L"VolumePath",
                  szVolumeName,
                  (unsigned int)v71);
                v105 = &v93;
                v93 = &v104;
                v102 = 0;
                v103 = 0;
                FveApiEventLogDeclareWSTRING(
                  (struct _FVEAPI_EVENT_DATA *)&v100,
                  v59,
                  L"VolumeDriveLetter",
                  (const unsigned __int16 *)v124,
                  v74);
                v101 = &v104;
                v104 = &v100;
                v89 = L"ProtectorGUID";
                v90 = v60;
                v91 = &v118;
                v92 = 16;
                v87 = &v82;
                v88 = &v100;
                v100 = &v87;
                v83 = &v87;
                v81 = FVE_OP_SKYDRIVE_BACKUP_SUCCESS;
                FveEventLogHandle::LogFveApiEvent(
                  (FveEventLogHandle *)&v84,
                  (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v80);
                FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v84);
              }
              goto LABEL_165;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetImpl'::`2'::impl) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF__guid_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124, v7);
              v80 = 0;
              v84 = 0;
              v85 = 0;
              v86 = 0;
              *(_QWORD *)v121 = 0x5200440050LL;
              v95 = L"IdentityGuid";
              v96 = L"GUID";
              v97 = (struct _GUID *)&v119;
              v98 = 16;
              v94 = &v82;
              v82 = &v93;
              v106 = 0;
              v107 = 0;
              FveApiEventLogDeclareWSTRING(
                (struct _FVEAPI_EVENT_DATA *)&v104,
                L"GUID",
                L"VolumePath",
                szVolumeName,
                (unsigned int)v71);
              v105 = &v93;
              v93 = &v104;
              v102 = 0;
              v103 = 0;
              FveApiEventLogDeclareWSTRING(
                (struct _FVEAPI_EVENT_DATA *)&v100,
                v61,
                L"VolumeDriveLetter",
                (const unsigned __int16 *)v124,
                v75);
              v101 = &v104;
              v104 = &v100;
              *(_DWORD *)v79 = v7;
              v89 = L"hr";
              v90 = L"HRESULT";
              v91 = (struct _GUID *)v79;
              v92 = 4;
              v88 = &v100;
              v100 = &v87;
              v114 = 0;
              v115 = 0;
              FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v112, v62, L"BackendName", v121, v76);
              v112 = &v82;
              v113 = &v87;
              v87 = &v112;
              v83 = &v112;
              v81 = FVE_OP_PDR_BACKUP_FAILED;
              FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v84, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v80);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v84);
              v47 = "BackupRecoveryPasswordWithRetryPDR2";
              v48 = 1083;
            }
            else
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF__guid_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124, v7);
              v80 = 0;
              v84 = 0;
              v85 = 0;
              v86 = 0;
              v95 = L"IdentityGuid";
              v96 = L"GUID";
              v97 = (struct _GUID *)&v119;
              v98 = 16;
              v94 = &v82;
              v82 = &v93;
              v106 = 0;
              v107 = 0;
              FveApiEventLogDeclareWSTRING(
                (struct _FVEAPI_EVENT_DATA *)&v104,
                L"GUID",
                L"VolumePath",
                szVolumeName,
                (unsigned int)v71);
              v105 = &v93;
              v93 = &v104;
              v102 = 0;
              v103 = 0;
              FveApiEventLogDeclareWSTRING(
                (struct _FVEAPI_EVENT_DATA *)&v100,
                v63,
                L"VolumeDriveLetter",
                (const unsigned __int16 *)v124,
                v77);
              v101 = &v104;
              v104 = &v100;
              *(_DWORD *)v79 = v7;
              v89 = L"hr";
              v90 = L"HRESULT";
              v91 = (struct _GUID *)v79;
              v92 = 4;
              v87 = &v82;
              v88 = &v100;
              v100 = &v87;
              v83 = &v87;
              v81 = FVE_OP_SKYDRIVE_BACKUP_FAILED;
              FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v84, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v80);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v84);
              v47 = "BackupRecoveryPasswordWithRetryOneDrive2";
              v48 = 1099;
            }
            goto LABEL_146;
          }
          if ( !this[2] || v21 )
          {
LABEL_131:
            if ( this[4] && !v22 )
            {
              v78 = v120;
              v64 = &v118;
              v7 = FveEnableEAS::BackupRecoveryPasswordWithRetry(this, v111, v23, &v119);
              if ( v7 < 0 )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetImpl'::`2'::impl) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF__guid_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124, v7);
                  v80 = 0;
                  v84 = 0;
                  v85 = 0;
                  v86 = 0;
                  *(_QWORD *)v121 = 0x5200440050LL;
                  v95 = L"IdentityGuid";
                  v96 = L"GUID";
                  v97 = (struct _GUID *)&v119;
                  v98 = 16;
                  v94 = &v82;
                  v82 = &v93;
                  v106 = 0;
                  v107 = 0;
                  FveApiEventLogDeclareWSTRING(
                    (struct _FVEAPI_EVENT_DATA *)&v104,
                    L"GUID",
                    L"VolumePath",
                    szVolumeName,
                    (unsigned int)v64);
                  v105 = &v93;
                  v93 = &v104;
                  v102 = 0;
                  v103 = 0;
                  FveApiEventLogDeclareWSTRING(
                    (struct _FVEAPI_EVENT_DATA *)&v100,
                    v51,
                    L"VolumeDriveLetter",
                    (const unsigned __int16 *)v124,
                    v68);
                  v101 = &v104;
                  v104 = &v100;
                  *(_DWORD *)v79 = v7;
                  v89 = L"hr";
                  v90 = L"HRESULT";
                  v91 = (struct _GUID *)v79;
                  v92 = 4;
                  v88 = &v100;
                  v100 = &v87;
                  v114 = 0;
                  v115 = 0;
                  FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v112, v79, L"BackendName", v121, v69);
                  v112 = &v82;
                  v113 = &v87;
                  v87 = &v112;
                  v83 = &v112;
                  v81 = FVE_OP_PDR_BACKUP_FAILED;
                  FveEventLogHandle::LogFveApiEvent(
                    (FveEventLogHandle *)&v84,
                    (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v80);
                  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v84);
                  v52 = 995;
                  v53 = "BackupRecoveryPasswordWithRetryPDR1";
                }
                else
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    WPP_SF__guid_SSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124, v7);
                  v80 = 0;
                  v84 = 0;
                  v85 = 0;
                  v86 = 0;
                  v95 = L"IdentityGuid";
                  v96 = L"GUID";
                  v97 = (struct _GUID *)&v119;
                  v98 = 16;
                  v94 = &v82;
                  v82 = &v93;
                  v106 = 0;
                  v107 = 0;
                  FveApiEventLogDeclareWSTRING(
                    (struct _FVEAPI_EVENT_DATA *)&v104,
                    L"GUID",
                    L"VolumePath",
                    szVolumeName,
                    (unsigned int)v64);
                  v105 = &v93;
                  v93 = &v104;
                  v102 = 0;
                  v103 = 0;
                  FveApiEventLogDeclareWSTRING(
                    (struct _FVEAPI_EVENT_DATA *)&v100,
                    v54,
                    L"VolumeDriveLetter",
                    (const unsigned __int16 *)v124,
                    v70);
                  v101 = &v104;
                  v104 = &v100;
                  *(_DWORD *)v79 = v7;
                  v89 = L"hr";
                  v90 = L"HRESULT";
                  v91 = (struct _GUID *)v79;
                  v92 = 4;
                  v87 = &v82;
                  v88 = &v100;
                  v100 = &v87;
                  v83 = &v87;
                  v81 = FVE_OP_SKYDRIVE_BACKUP_FAILED;
                  FveEventLogHandle::LogFveApiEvent(
                    (FveEventLogHandle *)&v84,
                    (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v80);
                  FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v84);
                  v52 = 1013;
                  v53 = "BackupRecoveryPasswordWithRetryOneDrive1";
                }
                wil::details::in1diag3::Log_HrMsg(
                  retaddr,
                  (void *)v52,
                  (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
                  (const char *)(unsigned int)v7,
                  (int)v53,
                  v78);
              }
              else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_BackupToPDR>::GetImpl'::`2'::impl) )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF__guid_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124);
                v80 = 0;
                v84 = 0;
                v85 = 0;
                v86 = 0;
                *(_QWORD *)v121 = 0x5200440050LL;
                v89 = L"IdentityGuid";
                v90 = L"GUID";
                v91 = (struct _GUID *)&v119;
                v92 = 16;
                v88 = &v82;
                v82 = &v87;
                v114 = 0;
                v115 = 0;
                FveApiEventLogDeclareWSTRING(
                  (struct _FVEAPI_EVENT_DATA *)&v112,
                  L"GUID",
                  L"VolumePath",
                  szVolumeName,
                  (unsigned int)v64);
                v113 = &v87;
                v87 = &v112;
                v102 = 0;
                v103 = 0;
                FveApiEventLogDeclareWSTRING(
                  (struct _FVEAPI_EVENT_DATA *)&v100,
                  v45,
                  L"VolumeDriveLetter",
                  (const unsigned __int16 *)v124,
                  v65);
                v101 = &v112;
                v112 = &v100;
                v95 = L"ProtectorGUID";
                v96 = v46;
                v97 = &v118;
                v98 = 16;
                v94 = &v100;
                v100 = &v93;
                v106 = 0;
                v107 = 0;
                FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v104, v46, L"BackendName", v121, v66);
                v104 = &v82;
                v105 = &v93;
                v93 = &v104;
                v83 = &v104;
                v81 = FVE_OP_PDR_BACKUP_SUCCESS;
                FveEventLogHandle::LogFveApiEvent(
                  (FveEventLogHandle *)&v84,
                  (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v80);
                FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v84);
              }
              else
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                  WPP_SF__guid_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)szVolumeName, (__int64)v124);
                v80 = 0;
                v84 = 0;
                v85 = 0;
                v86 = 0;
                v95 = L"IdentityGuid";
                v96 = L"GUID";
                v97 = (struct _GUID *)&v119;
                v98 = 16;
                v94 = &v82;
                v82 = &v93;
                v106 = 0;
                v107 = 0;
                FveApiEventLogDeclareWSTRING(
                  (struct _FVEAPI_EVENT_DATA *)&v104,
                  L"GUID",
                  L"VolumePath",
                  szVolumeName,
                  (unsigned int)v64);
                v105 = &v93;
                v93 = &v104;
                v102 = 0;
                v103 = 0;
                FveApiEventLogDeclareWSTRING(
                  (struct _FVEAPI_EVENT_DATA *)&v100,
                  v49,
                  L"VolumeDriveLetter",
                  (const unsigned __int16 *)v124,
                  v67);
                v101 = &v104;
                v104 = &v100;
                v89 = L"ProtectorGUID";
                v90 = v50;
                v91 = &v118;
                v92 = 16;
                v87 = &v82;
                v88 = &v100;
                v100 = &v87;
                v83 = &v87;
                v81 = FVE_OP_SKYDRIVE_BACKUP_SUCCESS;
                FveEventLogHandle::LogFveApiEvent(
                  (FveEventLogHandle *)&v84,
                  (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v80);
                FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v84);
              }
              v20 = (PVOID *)WPP_GLOBAL_Control;
              v22 = 1;
            }
            if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 )
            {
              LODWORD(v78) = v7;
              WPP_SF_DDd(v20[2], v18, v19, v21, v22, v78);
            }
            goto LABEL_165;
          }
          v7 = FveBackupRecoveryPasswordToCloudDomain(v111, 0, 0, v23, &v119, &v118, v120, v124, 1, 1, 1);
          if ( (unsigned int)dword_18009A548 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18009A548, 0x400000000000LL) )
          {
            HIDWORD(v99) = v23;
            *(_QWORD *)v121 = &v119;
            *(_DWORD *)v79 = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
              v41,
              (int)&byte_18008E9EF,
              v42,
              v43,
              (__int64)v79,
              (__int64 *)v121,
              (__int64)&v99 + 4);
          }
          v44 = (**(__int64 (__fastcall ***)(FveEasUtil *, _QWORD, __int128 *, struct _GUID *, int))this[2])(
                  this[2],
                  v23,
                  &v119,
                  &v118,
                  v7);
          if ( v44 < 0 )
          {
            v20 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
              goto LABEL_126;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              82,
              &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
              (unsigned int)v44);
          }
          v20 = (PVOID *)WPP_GLOBAL_Control;
LABEL_126:
          if ( v7 >= 0 )
          {
            if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 8) != 0 )
            {
              WPP_SF__guid_SS((TRACEHANDLE)v20[2], (__int64)szVolumeName, (__int64)v124);
              v20 = (PVOID *)WPP_GLOBAL_Control;
            }
            v21 = 1;
            goto LABEL_131;
          }
          if ( v20 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v20 + 28) & 2) != 0 )
            {
              WPP_SF__guid_SSd((TRACEHANDLE)v20[2], (__int64)szVolumeName, (__int64)v124, v7);
              v20 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 0x40) != 0 )
              WPP_SF_d(v20[2], 85, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, (unsigned int)v7);
          }
          v47 = "FveBackupRecoveryPasswordToCloudDomain";
          v48 = 932;
LABEL_146:
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v48,
            (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
            (const char *)(unsigned int)v7,
            (int)v47,
            v78);
          goto LABEL_165;
        }
        v34 = "LastBackupResultAD";
        v35 = 761;
LABEL_73:
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)v35,
          (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
          (const char *)v33,
          (int)v34,
          v78);
        goto LABEL_74;
      }
      if ( (_DWORD)v109 == -2147024894 )
        goto LABEL_62;
      v30 = "LastBackupResultMSA";
      v31 = 739;
LABEL_61:
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v31,
        (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
        (const char *)v29,
        (int)v30,
        v78);
      goto LABEL_62;
    }
    v7 = (*(__int64 (__fastcall **)(FveEasUtil *, _QWORD, __int128 *, struct _GUID *, char **, char *))(*(_QWORD *)v24 + 8LL))(
           v24,
           v23,
           &v119,
           &v118,
           &v99,
           v108);
    v25 = (unsigned int)v99;
    if ( v7 < 0 )
    {
      if ( v7 != -2147024894 )
      {
        v26 = "GetRecoveryPasswordBackupStatusAAD";
        v25 = (unsigned int)v7;
        v27 = 715;
        goto LABEL_51;
      }
    }
    else if ( !(_DWORD)v99 )
    {
      v21 = 1;
LABEL_52:
      v20 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_53;
    }
    if ( (_DWORD)v99 == -2147024894 )
      goto LABEL_52;
    v26 = "LastBackupResultAAD";
    v27 = 717;
LABEL_51:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v27,
      (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)v25,
      (int)v26,
      v78);
    goto LABEL_52;
  }
  v8 = "GetFveVolumePath";
  v9 = 670;
LABEL_9:
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)v9,
    (unsigned int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
    (const char *)(unsigned int)v7,
    (int)v8,
    v78);
LABEL_166:
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v110);
  v55 = v120;
  do
  {
    *v55++ = 0;
    --v4;
  }
  while ( v4 );
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      95,
      &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
      (unsigned int)v7);
  v110 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v110);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180075754  mov     [rsp-8+arg_10], rbx
0x180075759  push    rbp
0x18007575a  push    rsi
0x18007575b  push    rdi
0x18007575c  push    r12
0x18007575e  push    r13
0x180075760  push    r14
0x180075762  push    r15
0x180075764  lea     rbp, [rsp-990h]
0x18007576c  sub     rsp, 0A90h
0x180075773  mov     rax, cs:__security_cookie
0x18007577a  xor     rax, rsp
0x18007577d  mov     [rbp+9C0h+var_40], rax
0x180075784  mov     rbx, rdx
0x180075787  mov     rsi, rcx
0x18007578a  mov     dword ptr [rbp+9C0h+var_9C0+4], 0
0x180075791  mov     dword ptr [rbp+9C0h+var_9C0], 0
0x180075798  mov     qword ptr [rbp+9C0h+var_958], 0
0x1800757a0  mov     dword ptr [rbp+9C0h+var_950], 0
0x1800757a7  mov     qword ptr [rbp+9C0h+var_900], 0
0x1800757b2  mov     edi, 208h
0x1800757b7  mov     r8d, edi; Size
0x1800757ba  xor     edx, edx; Val
0x1800757bc  lea     rcx, [rbp+9C0h+szVolumeName]; void *
0x1800757c3  call    memset_0
0x1800757c8  mov     [rbp+9C0h+var_908], 104h
0x1800757d2  mov     r8d, edi; Size
0x1800757d5  xor     edx, edx; Val
0x1800757d7  lea     rcx, [rbp+9C0h+var_250]; void *
0x1800757de  call    memset_0
0x1800757e3  xorps   xmm0, xmm0
0x1800757e6  movups  [rbp+9C0h+var_8E8], xmm0
0x1800757ed  mov     r8d, edi; Size
0x1800757f0  xor     edx, edx; Val
0x1800757f2  lea     rcx, [rbp+9C0h+var_460]; void *
0x1800757f9  call    memset_0
0x1800757fe  xorps   xmm0, xmm0
0x180075801  movups  xmmword ptr [rbp+9C0h+var_8F8.Data1], xmm0
0x180075808  lea     r14d, [rdi+40h]
0x18007580c  mov     r8d, r14d; Size
0x18007580f  xor     edx, edx; Val
0x180075811  lea     rcx, [rbp+9C0h+var_8D0]; void *
0x180075818  call    memset_0
0x18007581d  lea     r12, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x180075824  mov     [rbp+9C0h+var_948], r12
0x180075828  mov     [rbp+9C0h+var_940], 0
0x180075833  lea     r13, WPP_GLOBAL_Control
0x18007583a  mov     rcx, cs:WPP_GLOBAL_Control
0x180075841  cmp     rcx, r13
0x180075844  jz      short loc_180075861
0x180075846  test    byte ptr [rcx+1Ch], 20h
0x18007584a  jz      short loc_180075861
0x18007584c  mov     edx, 41h ; 'A'
0x180075851  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180075858  mov     rcx, [rcx+10h]
0x18007585c  call    WPP_SF_
0x180075861  lea     rdx, [rbp+9C0h+var_250]; unsigned __int16 *
0x180075868  mov     rcx, rbx; unsigned __int16 *
0x18007586b  call    ?GetFveVolumePath@CFveDriveType@@SAJPEBGPEAGK@Z; CFveDriveType::GetFveVolumePath(ushort const *,ushort *,ulong)
0x180075870  mov     ebx, eax
0x180075872  mov     dil, 40h ; '@'
0x180075875  mov     rcx, cs:WPP_GLOBAL_Control
0x18007587c  cmp     rcx, r13
0x18007587f  jz      short loc_18007589F
0x180075881  test    [rcx+1Ch], dil
0x180075885  jz      short loc_18007589F
0x180075887  mov     edx, 42h ; 'B'
0x18007588c  mov     r9d, eax
0x18007588f  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180075896  mov     rcx, [rcx+10h]
0x18007589a  call    WPP_SF_d
0x18007589f  test    ebx, ebx
0x1800758a1  jns     short loc_1800758CF
0x1800758a3  lea     rax, aGetfvevolumepa; "GetFveVolumePath"
0x1800758aa  mov     edx, 29Eh; void *
0x1800758af  mov     rcx, [rbp+9C8h]; this
0x1800758b6  mov     qword ptr [rsp+0AC0h+var_AA0], rax; int
0x1800758bb  mov     r9d, ebx; char *
0x1800758be  lea     r8, aBaseNgscbCorne_2; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x1800758c5  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800758ca  jmp     loc_1800769DE
0x1800758cf  lea     r9, [rbp+9C0h+var_8D0]; struct _FVE_AUTH_ELEMENT *
0x1800758d6  lea     r8, [rbp+9C0h+var_8F8]; struct _GUID *
0x1800758dd  lea     rdx, [rbp+9C0h+var_250]; unsigned __int16 *
0x1800758e4  mov     rcx, [rsi+8]; this
0x1800758e8  call    ?CreateVolumeRecoveryPassword@FveEasUtil@@QEBAJPEBGPEAU_GUID@@PEAU_FVE_AUTH_ELEMENT@@@Z; FveEasUtil::CreateVolumeRecoveryPassword(ushort const *,_GUID *,_FVE_AUTH_ELEMENT *)
0x1800758ed  mov     ebx, eax
0x1800758ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800758f6  cmp     rcx, r13
0x1800758f9  jz      short loc_180075919
0x1800758fb  test    [rcx+1Ch], dil
0x1800758ff  jz      short loc_180075919
0x180075901  mov     edx, 43h ; 'C'
0x180075906  mov     r9d, eax
0x180075909  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180075910  mov     rcx, [rcx+10h]
0x180075914  call    WPP_SF_d
0x180075919  test    ebx, ebx
0x18007591b  jns     short loc_18007592B
0x18007591d  lea     rax, aCreatevolumere; "CreateVolumeRecoveryPassword"
0x180075924  mov     edx, 2A7h
0x180075929  jmp     short loc_1800758AF
0x18007592b  mov     r8b, 1
0x18007592e  lea     rdx, [rbp+9C0h+var_948]
0x180075932  lea     rcx, [rbp+9C0h+var_250]
0x180075939  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x18007593e  mov     ebx, eax
0x180075940  mov     rcx, cs:WPP_GLOBAL_Control
0x180075947  cmp     rcx, r13
0x18007594a  jz      short loc_18007596A
0x18007594c  test    [rcx+1Ch], dil
0x180075950  jz      short loc_18007596A
0x180075952  mov     edx, 44h ; 'D'
0x180075957  mov     r9d, eax
0x18007595a  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180075961  mov     rcx, [rcx+10h]
0x180075965  call    WPP_SF_d
0x18007596a  test    ebx, ebx
0x18007596c  jns     short loc_18007597F
0x18007596e  lea     rax, aGetreadonlyvol; "GetReadOnlyVolumeHandle"
0x180075975  mov     edx, 2AEh
0x18007597a  jmp     loc_1800758AF
0x18007597f  lea     rdx, [rbp+9C0h+var_9C0+4]; unsigned int *
0x180075983  mov     rcx, [rbp+9C0h+var_940]; void *
0x18007598a  call    ?GetStatusFlags@CFveApiWrapper@@SAJPEAXPEAK@Z; CFveApiWrapper::GetStatusFlags(void *,ulong *)
0x18007598f  mov     ebx, eax
0x180075991  mov     rcx, cs:WPP_GLOBAL_Control
0x180075998  cmp     rcx, r13
0x18007599b  jz      short loc_1800759BB
0x18007599d  test    [rcx+1Ch], dil
0x1800759a1  jz      short loc_1800759BB
0x1800759a3  mov     edx, 45h ; 'E'
0x1800759a8  mov     r9d, eax
0x1800759ab  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x1800759b2  mov     rcx, [rcx+10h]
0x1800759b6  call    WPP_SF_d
0x1800759bb  test    ebx, ebx
0x1800759bd  jns     short loc_1800759D0
0x1800759bf  lea     rax, aGetstatusflags; "GetStatusFlags"
0x1800759c6  mov     edx, 2B0h
0x1800759cb  jmp     loc_1800758AF
0x1800759d0  lea     rdx, [rbp+9C0h+var_8E8]
0x1800759d7  mov     rcx, [rbp+9C0h+var_940]
0x1800759de  call    cs:__imp_FveGetIdentity
0x1800759e5  nop     dword ptr [rax+rax+00h]
0x1800759ea  mov     ebx, eax
0x1800759ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800759f3  cmp     rcx, r13
0x1800759f6  jz      short loc_180075A16
0x1800759f8  test    [rcx+1Ch], dil
0x1800759fc  jz      short loc_180075A16
0x1800759fe  mov     edx, 46h ; 'F'
0x180075a03  mov     r9d, eax
0x180075a06  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180075a0d  mov     rcx, [rcx+10h]
0x180075a11  call    WPP_SF_d
0x180075a16  test    ebx, ebx
0x180075a18  jns     short loc_180075A2B
0x180075a1a  lea     rax, aFvegetidentity; "FveGetIdentity"
0x180075a21  mov     edx, 2B1h
0x180075a26  jmp     loc_1800758AF
0x180075a2b  lea     r8, [rbp+9C0h+szVolumeName]
0x180075a32  lea     rdx, [rbp+9C0h+var_908]
0x180075a39  mov     rcx, [rbp+9C0h+var_940]
0x180075a40  call    cs:__imp_FveGetVolumeNameW
0x180075a47  nop     dword ptr [rax+rax+00h]
0x180075a4c  mov     ebx, eax
0x180075a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180075a55  cmp     rcx, r13
0x180075a58  jz      short loc_180075A78
0x180075a5a  test    [rcx+1Ch], dil
0x180075a5e  jz      short loc_180075A78
0x180075a60  mov     edx, 47h ; 'G'
0x180075a65  mov     r9d, eax
0x180075a68  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180075a6f  mov     rcx, [rcx+10h]
0x180075a73  call    WPP_SF_d
0x180075a78  test    ebx, ebx
0x180075a7a  jns     short loc_180075A8D
0x180075a7c  lea     rax, aFvegetvolumena; "FveGetVolumeNameW"
0x180075a83  mov     edx, 2B5h
0x180075a88  jmp     loc_1800758AF
0x180075a8d  lea     rdx, [rbp+9C0h+var_460]; unsigned __int16 *
0x180075a94  lea     rcx, [rbp+9C0h+szVolumeName]; lpszVolumeName
0x180075a9b  call    ?GetVolumeMountPoint@FveEasUtil@@SAJPEBGPEAGK@Z; FveEasUtil::GetVolumeMountPoint(ushort const *,ushort *,ulong)
0x180075aa0  mov     ebx, eax
0x180075aa2  mov     r10, cs:WPP_GLOBAL_Control
0x180075aa9  cmp     r10, r13
0x180075aac  jz      short loc_180075AD3
0x180075aae  test    [r10+1Ch], dil
0x180075ab2  jz      short loc_180075AD3
0x180075ab4  mov     edx, 48h ; 'H'
0x180075ab9  mov     r9d, eax
0x180075abc  lea     r8, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x180075ac3  mov     rcx, [r10+10h]
0x180075ac7  call    WPP_SF_d
0x180075acc  mov     r10, cs:WPP_GLOBAL_Control
0x180075ad3  test    ebx, ebx
0x180075ad5  jns     short loc_180075AE8
0x180075ad7  lea     rax, aGetvolumemount; "GetVolumeMountPoint"
0x180075ade  mov     edx, 2B8h
0x180075ae3  jmp     loc_1800758AF
0x180075ae8  xor     r13b, r13b
0x180075aeb  xor     r12b, r12b
0x180075aee  mov     eax, dword ptr [rbp+9C0h+var_9C0+4]
0x180075af1  bt      eax, 0Eh
0x180075af5  jnb     short loc_180075AFC
0x180075af7  xor     r14d, r14d
0x180075afa  jmp     short loc_180075B0C
0x180075afc  and     eax, 400000h
0x180075b01  neg     eax
0x180075b03  sbb     r14d, r14d
0x180075b06  neg     r14d
0x180075b09  inc     r14d
0x180075b0c  mov     rcx, [rsi+10h]
0x180075b10  lea     rdi, aBaseNgscbCorne_2; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180075b17  mov     r15d, 80070002h
0x180075b1d  test    rcx, rcx
0x180075b20  jz      loc_180075BAB
0x180075b26  mov     rax, [rcx]
0x180075b29  lea     rdx, [rbp+9C0h+var_958]
0x180075b2d  mov     [rsp+0AC0h+var_A98], rdx; char *
0x180075b32  lea     rdx, [rbp+9C0h+var_9C0]
0x180075b36  mov     qword ptr [rsp+0AC0h+var_AA0], rdx
0x180075b3b  lea     r9, [rbp+9C0h+var_8F8]
0x180075b42  lea     r8, [rbp+9C0h+var_8E8]
0x180075b49  mov     edx, r14d
0x180075b4c  mov     rax, [rax+8]
0x180075b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b55  mov     ebx, eax
0x180075b57  mov     r9d, dword ptr [rbp+9C0h+var_9C0]; char *
0x180075b5b  test    eax, eax
0x180075b5d  js      short loc_180075B69
0x180075b5f  test    r9d, r9d
0x180075b62  jnz     short loc_180075B7F
0x180075b64  mov     r13b, 1
0x180075b67  jmp     short loc_180075BA4
0x180075b69  cmp     ebx, r15d
0x180075b6c  jz      short loc_180075B7F
0x180075b6e  lea     rax, aGetrecoverypas_0; "GetRecoveryPasswordBackupStatusAAD"
0x180075b75  mov     r9d, ebx
0x180075b78  mov     edx, 2CBh
0x180075b7d  jmp     short loc_180075B90
0x180075b7f  cmp     r9d, r15d
0x180075b82  jz      short loc_180075BA4
0x180075b84  lea     rax, aLastbackupresu_0; "LastBackupResultAAD"
0x180075b8b  mov     edx, 2CDh; void *
0x180075b90  mov     qword ptr [rsp+0AC0h+var_AA0], rax; int
0x180075b95  mov     r8, rdi; unsigned int
0x180075b98  mov     rcx, [rbp+9C8h]; this
0x180075b9f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180075ba4  mov     r10, cs:WPP_GLOBAL_Control
0x180075bab  mov     rcx, [rsi+20h]
0x180075baf  test    rcx, rcx
0x180075bb2  jz      loc_180075C40
0x180075bb8  mov     rax, [rcx]
0x180075bbb  lea     rdx, [rbp+9C0h+var_900]
0x180075bc2  mov     [rsp+0AC0h+var_A98], rdx; char *
0x180075bc7  lea     rdx, [rbp+9C0h+var_950]
0x180075bcb  mov     qword ptr [rsp+0AC0h+var_AA0], rdx
0x180075bd0  lea     r9, [rbp+9C0h+var_8F8]
0x180075bd7  lea     r8, [rbp+9C0h+var_8E8]
0x180075bde  mov     edx, r14d
0x180075be1  mov     rax, [rax+8]
0x180075be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075bea  mov     ebx, eax
0x180075bec  mov     r9d, dword ptr [rbp+9C0h+var_950]; char *
0x180075bf0  test    eax, eax
0x180075bf2  js      short loc_180075BFE
0x180075bf4  test    r9d, r9d
0x180075bf7  jnz     short loc_180075C14
0x180075bf9  mov     r12b, 1
0x180075bfc  jmp     short loc_180075C39
0x180075bfe  cmp     ebx, r15d
0x180075c01  jz      short loc_180075C14
0x180075c03  lea     rax, aGetrecoverypas; "GetRecoveryPasswordBackupStatusMSA"
0x180075c0a  mov     r9d, ebx
0x180075c0d  mov     edx, 2E1h
0x180075c12  jmp     short loc_180075C25
0x180075c14  cmp     r9d, r15d
0x180075c17  jz      short loc_180075C39
0x180075c19  lea     rax, aLastbackupresu_1; "LastBackupResultMSA"
0x180075c20  mov     edx, 2E3h; void *
0x180075c25  mov     qword ptr [rsp+0AC0h+var_AA0], rax; int
0x180075c2a  mov     r8, rdi; unsigned int
0x180075c2d  mov     rcx, [rbp+9C8h]; this
0x180075c34  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180075c39  mov     r10, cs:WPP_GLOBAL_Control
0x180075c40  mov     rcx, [rsi+30h]
0x180075c44  test    rcx, rcx
0x180075c47  jz      loc_180075D35
0x180075c4d  mov     rax, [rcx]
0x180075c50  lea     rdx, [rbp+9C0h+var_958]
0x180075c54  mov     [rsp+0AC0h+var_A98], rdx; char *
0x180075c59  lea     rdx, [rbp+9C0h+var_9C0]
0x180075c5d  mov     qword ptr [rsp+0AC0h+var_AA0], rdx
0x180075c62  lea     r9, [rbp+9C0h+var_8F8]
0x180075c69  lea     r8, [rbp+9C0h+var_8E8]
0x180075c70  mov     edx, r14d
0x180075c73  mov     rax, [rax+8]
  ... truncated ...
```
