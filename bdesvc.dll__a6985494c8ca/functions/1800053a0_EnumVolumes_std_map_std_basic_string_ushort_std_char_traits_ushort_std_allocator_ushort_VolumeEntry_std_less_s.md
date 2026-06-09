# EnumVolumes(std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,VolumeEntry,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,VolumeEntry>>> *,bool,unsigned __int64 *,bool,bool)

- ea: `0x1800053a0`
- end: `0x18000624b`
- name: `?EnumVolumes@@YAKPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UVolumeEntry@@@std@@@2@@std@@_NPEA_K11@Z`
- size: `3755`
- prototype: `__int64 __fastcall(__int64, char, _QWORD *, char, char)`
- caller_count: `8`
- callee_count: `28`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1800062d0`
- `0x1800065b8`
- `0x180007d90`
- `0x18002d020`
- `0x18003c780`
- `0x180045640`
- `0x1800478d0`
- `0x180054634`

## callees

- `0x1800053a0`
- `0x180006260`
- `0x180009f30`
- `0x180009f60`
- `0x18000bc10`
- `0x18000f1a0`
- `0x18000f290`
- `0x18000f7e0`
- `0x18001b890`
- `0x18001c8b0`
- `0x18001d1b0`
- `0x18001d2a0`
- `0x18001de10`
- `0x18001dea0`
- `0x18001e320`
- `0x18001f910`
- `0x180020580`
- `0x180029df0`
- `0x18002a2e0`
- `0x18002a774`
- `0x18002cac4`
- `0x180034070`
- `0x180034d28`
- `0x180046560`
- `0x180046fb8`
- `0x180047e6c`
- `0x18006a088`
- `0x18006c39c`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x180005c25`
- `ntdll!NtQuerySystemInformation` at `0x180005c25`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000595b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000595b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ad3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800059bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005ad3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000564b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000565e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000564b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000565e`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180005637`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180005637`
- `FVEAPI!FveInitializeDeviceEncryption3` at `0x180005dc8`
- `FVEAPI!FveInitializeDeviceEncryption3` at `0x180005dc8`
- `FVEAPI!FveUpdateBandIdBcd` at `0x180005cc3`
- `FVEAPI!FveUpdateBandIdBcd` at `0x180005cc3`
- `FVEAPI!FveRegenerateNbpSessionKey` at `0x180005c60`
- `FVEAPI!FveRegenerateNbpSessionKey` at `0x180005c60`
- `FVEAPI!FveGenerateNkpSessionKeys` at `0x180005bbe`
- `FVEAPI!FveGenerateNkpSessionKeys` at `0x180005bbe`
- `FVEAPI!FveSysSetUserFlags` at `0x180005a83`
- `FVEAPI!FveSysSetUserFlags` at `0x180005a83`
- `FVEAPI!FveSysClearUserFlags` at `0x180005a14`
- `FVEAPI!FveSysClearUserFlags` at `0x180005a14`
- `FVEAPI!FveSysGetUserFlags` at `0x180005977`
- `FVEAPI!FveSysGetUserFlags` at `0x180005977`
- `FVEAPI!FveGetFveMethod` at `0x180005857`
- `FVEAPI!FveGetFveMethod` at `0x180005857`
- `FVEAPI!FveSysCloseVolume` at `0x180005586`
- `FVEAPI!FveSysCloseVolume` at `0x1800061d9`
- `FVEAPI!FveSysCloseVolume` at `0x180005586`
- `FVEAPI!FveSysCloseVolume` at `0x1800061d9`
- `FVEAPI!FveGetIdentity` at `0x180005b61`
- `FVEAPI!FveGetIdentity` at `0x180005b61`
- `FVEAPI!FveGetVolumeNameW` at `0x1800055df`
- `FVEAPI!FveGetVolumeNameW` at `0x1800055df`
- `FVEAPI!FveIsVolumeEncryptable` at `0x180005af1`
- `FVEAPI!FveIsVolumeEncryptable` at `0x180005af1`
- `FVEAPI!FveGetStatus` at `0x1800057a8`
- `FVEAPI!FveGetStatus` at `0x1800057a8`
- `FVEAPI!FveOpenVolumeByHandle` at `0x180005764`
- `FVEAPI!FveOpenVolumeByHandle` at `0x180005920`
- `FVEAPI!FveOpenVolumeByHandle` at `0x180005764`
- `FVEAPI!FveOpenVolumeByHandle` at `0x180005920`
- `FVEAPI!FveCloseVolume` at `0x180005565`
- `FVEAPI!FveCloseVolume` at `0x180006189`
- `FVEAPI!FveCloseVolume` at `0x1800061b1`
- `FVEAPI!FveCloseVolume` at `0x180005565`
- `FVEAPI!FveCloseVolume` at `0x180006189`
- `FVEAPI!FveCloseVolume` at `0x1800061b1`
- `FVEAPI!FveFindNextVolume` at `0x18000610c`
- `FVEAPI!FveFindNextVolume` at `0x18000610c`
- `FVEAPI!FveFindFirstVolume` at `0x18000553e`
- `FVEAPI!FveFindFirstVolume` at `0x18000553e`

## pseudocode

```c
__int64 __fastcall EnumVolumes(__int64 a1, char a2, _QWORD *a3, char a4, char a5)
{
  _QWORD *v5; // rsi
  PVOID *v7; // rbx
  unsigned int v8; // r12d
  int i; // eax
  int VolumeNameW; // eax
  int Status; // eax
  _QWORD *v12; // rcx
  int v13; // edx
  int v14; // esi
  char v15; // bl
  int v16; // ebx
  __int16 v17; // ax
  int v18; // eax
  int UserFlags; // eax
  _QWORD *v20; // rcx
  int v21; // edx
  char v22; // al
  int v23; // eax
  int IsRawVolume; // eax
  int Identity; // eax
  int v26; // ebx
  int NkpSessionKeys; // eax
  unsigned int v28; // ebx
  NTSTATUS v29; // eax
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  int updated; // eax
  int v33; // eax
  int v34; // eax
  PVOID *v35; // rcx
  bool v36; // zf
  int PersistentRequestsFolder; // eax
  int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // ebx
  int v42; // esi
  __int64 v44; // [rsp+20h] [rbp-508h]
  bool v45; // [rsp+30h] [rbp-4F8h] BYREF
  int v46; // [rsp+34h] [rbp-4F4h]
  int v47; // [rsp+38h] [rbp-4F0h]
  unsigned int v48; // [rsp+3Ch] [rbp-4ECh]
  unsigned int v49; // [rsp+40h] [rbp-4E8h]
  BOOL v50; // [rsp+44h] [rbp-4E4h]
  int v51; // [rsp+48h] [rbp-4E0h]
  int v52; // [rsp+4Ch] [rbp-4DCh]
  int IsVolumeEncryptable; // [rsp+50h] [rbp-4D8h]
  int v54; // [rsp+54h] [rbp-4D4h]
  __int64 v55; // [rsp+58h] [rbp-4D0h]
  _QWORD *v56; // [rsp+60h] [rbp-4C8h]
  __int64 v57; // [rsp+68h] [rbp-4C0h]
  BOOL v58; // [rsp+70h] [rbp-4B8h]
  __int64 v59; // [rsp+78h] [rbp-4B0h]
  __int64 v60; // [rsp+80h] [rbp-4A8h]
  __int64 v61; // [rsp+88h] [rbp-4A0h]
  _QWORD *v62; // [rsp+90h] [rbp-498h]
  char v63[5]; // [rsp+98h] [rbp-490h] BYREF
  char v64[11]; // [rsp+9Dh] [rbp-48Bh] BYREF
  _BYTE v65[32]; // [rsp+A8h] [rbp-480h] BYREF
  char v66[16]; // [rsp+C8h] [rbp-460h] BYREF
  void *v67; // [rsp+D8h] [rbp-450h] BYREF
  __int64 v68; // [rsp+E0h] [rbp-448h] BYREF
  __int64 v69; // [rsp+E8h] [rbp-440h] BYREF
  unsigned int v70; // [rsp+F0h] [rbp-438h] BYREF
  DWORD cchReturnLength; // [rsp+F4h] [rbp-434h] BYREF
  int v72; // [rsp+F8h] [rbp-430h] BYREF
  int v73; // [rsp+FCh] [rbp-42Ch] BYREF
  unsigned __int64 v74; // [rsp+100h] [rbp-428h] BYREF
  GUID v75; // [rsp+108h] [rbp-420h] BYREF
  _DWORD SystemInformation[10]; // [rsp+118h] [rbp-410h] BYREF
  _DWORD v77[4]; // [rsp+140h] [rbp-3E8h] BYREF
  __int64 v78; // [rsp+150h] [rbp-3D8h]
  int v79; // [rsp+158h] [rbp-3D0h]
  BOOL v80; // [rsp+15Ch] [rbp-3CCh]
  BOOL v81; // [rsp+160h] [rbp-3C8h]
  _BYTE v82[32]; // [rsp+168h] [rbp-3C0h] BYREF
  int v83; // [rsp+188h] [rbp-3A0h]
  int v84; // [rsp+18Ch] [rbp-39Ch]
  int v85; // [rsp+190h] [rbp-398h]
  __int64 v86; // [rsp+198h] [rbp-390h]
  GUID v87; // [rsp+1A0h] [rbp-388h]
  _DWORD v88[2]; // [rsp+1B0h] [rbp-378h] BYREF
  char v89[4]; // [rsp+1B8h] [rbp-370h] BYREF
  unsigned int v90; // [rsp+1BCh] [rbp-36Ch]
  int v91; // [rsp+1C8h] [rbp-360h]
  __int64 v92; // [rsp+1D0h] [rbp-358h]
  int v93; // [rsp+1E0h] [rbp-348h]
  __int64 v94; // [rsp+1E8h] [rbp-340h]
  _BYTE v95[32]; // [rsp+240h] [rbp-2E8h] BYREF
  char v96[112]; // [rsp+260h] [rbp-2C8h] BYREF
  WCHAR szVolumeName[264]; // [rsp+2D0h] [rbp-258h] BYREF

  v5 = a3;
  v56 = a3;
  v60 = a1;
  v61 = a1;
  v62 = a3;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v74 = 0;
  v69 = -1;
  v73 = 0;
  memset_0(szVolumeName, 0, 0x208u);
  v70 = 0;
  cchReturnLength = 0;
  v55 = 0;
  memset_0(v88, 0, 0x90u);
  v67 = (void *)-1LL;
  v68 = -1;
  v72 = 0;
  v75 = 0;
  memset(SystemInformation, 0, 32);
  v45 = 0;
  if ( v5 )
  {
    *v5 = 0;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a1 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 )
    {
      WPP_SF_(v7[2], 57, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    v8 = 87;
    goto LABEL_180;
  }
  v49 = 0;
  v51 = 0;
  IsVolumeEncryptable = 0;
  v48 = 0;
  v74 = 0xFFFFFFFF00000001uLL;
  for ( i = FveFindFirstVolume(&v69, &v74); i >= 0; i = FveFindNextVolume(v69, &v74) )
  {
    if ( v67 != (void *)-1LL )
    {
      FveCloseVolume();
      v67 = (void *)-1LL;
    }
    if ( v68 != -1 )
    {
      FveSysCloseVolume();
      v68 = -1;
    }
    v70 = 0;
    v54 = 0;
    cchReturnLength = 0;
    v75 = GUID_NULL;
    v73 = 260;
    VolumeNameW = FveGetVolumeNameW(v69, &v73, szVolumeName);
    if ( VolumeNameW < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
          (unsigned int)VolumeNameW);
      continue;
    }
    if ( GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, &cchReturnLength) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, szVolumeName);
    }
    else if ( GetLastError() == 234 )
    {
      v14 = 0;
      v47 = 0;
      v50 = 0;
      v59 = 0;
      v52 = 0;
      v57 = 0;
      v58 = cchReturnLength > 1;
      memset_0(v89, 0, 0x88u);
      v88[0] = 144;
      v88[1] = 10;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, szVolumeName);
      if ( !a4 )
        goto LABEL_196;
      LODWORD(v44) = 1;
      Status = FveOpenVolumeByHandle(v69, 0, 0, 0xFFFFFFFFLL, v44, &v67);
      if ( Status >= 0 )
      {
        Status = FveGetStatus(v67, v88);
        if ( Status >= 0 )
        {
          v15 = v90;
          v46 = v90;
          v51 = v93;
          v59 = v92;
          v52 = v91;
          v57 = v94;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_Li(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
              v90,
              v92);
          v16 = v15 & 1;
          if ( v16 && (int)FveGetFveMethod(v67, &v72) >= 0 )
          {
            v17 = v46;
            if ( (unsigned int)(v72 - 1) <= 1 )
            {
              if ( (v46 & 0x4000) != 0 )
              {
                v48 |= 1u;
              }
              else if ( (v46 & 0x400000) != 0 )
              {
                v48 |= 4u;
              }
              else
              {
                v48 |= 2u;
              }
            }
          }
          else
          {
            v17 = v46;
          }
          if ( (v17 & 0x4200) == 0x4200 || *(_BYTE *)(CBdeSvcDE::GetSupportLevel(v63) + 3) )
          {
            v18 = WinRENotificationListener::EnsureRegistered();
            if ( v18 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                65,
                WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                (unsigned int)v18);
          }
          if ( !a2 )
            goto LABEL_84;
          LODWORD(v44) = 1;
          Status = FveOpenVolumeByHandle(v69, 0, 1, 1, v44, &v68);
          if ( Status >= 0 )
          {
            EnterCriticalSection(&stru_18009BA00);
            UserFlags = FveSysGetUserFlags(v68, &v70);
            if ( UserFlags < 0 )
            {
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v21 = 67;
                goto LABEL_66;
              }
              goto LABEL_67;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v70);
            v22 = v70;
            if ( (v70 & 4) != 0 )
            {
              v14 = 1;
              v23 = FveSysClearUserFlags(v68, 4);
              if ( v23 < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_SD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  69,
                  (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                  (unsigned int)szVolumeName,
                  v23);
              }
              v22 = v70 & 0xFB;
              v70 &= ~4u;
            }
            if ( (v22 & 1) == 0 )
            {
              v50 = (v46 & 0x800) == 0;
              UserFlags = FveSysSetUserFlags(v68, 1);
              if ( UserFlags < 0 )
              {
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v21 = 70;
LABEL_66:
                  WPP_SF_SD(
                    v20[2],
                    v21,
                    (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                    (unsigned int)szVolumeName,
                    UserFlags);
                }
LABEL_67:
                LeaveCriticalSection(&stru_18009BA00);
                continue;
              }
              v47 = 1;
              v70 |= 1u;
              ++v55;
            }
            LeaveCriticalSection(&stru_18009BA00);
LABEL_84:
            if ( a5 )
            {
              IsVolumeEncryptable = FveIsVolumeEncryptable(v67);
              if ( IsVolumeEncryptable == -2144272365 )
              {
                IsRawVolume = NgscbIsRawVolume(szVolumeName);
                if ( IsRawVolume < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_Sd(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    71,
                    (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                    (unsigned int)szVolumeName,
                    IsRawVolume);
                }
              }
            }
            if ( v16 )
            {
              Identity = FveGetIdentity(v67, &v75);
              if ( Identity < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  72,
                  WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                  (unsigned int)Identity);
              }
            }
            v26 = v47;
            if ( v47 )
            {
              if ( v50 )
                MountFileSystem(szVolumeName);
              NkpSessionKeys = FveGenerateNkpSessionKeys(v67);
              v28 = NkpSessionKeys;
              if ( NkpSessionKeys < 0
                && NkpSessionKeys != -2144272344
                && NkpSessionKeys != -2144272228
                && NkpSessionKeys != (unsigned int)FromNtStatus(-1071579135)
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, v28);
              }
              v29 = NtQuerySystemInformation(SystemBootEnvironmentInformation, SystemInformation, 0x20u, 0);
              if ( v29 >= 0 )
              {
                if ( (SystemInformation[6] & 4) != 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
                }
                else
                {
                  v29 = FveRegenerateNbpSessionKey(v67);
                  if ( v29 < 0 )
                  {
                    v30 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v31 = 75;
LABEL_114:
                      WPP_SF_d(v30[2], v31, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids, (unsigned int)v29);
                    }
                  }
                }
              }
              else
              {
                v30 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v31 = 74;
                  goto LABEL_114;
                }
              }
              updated = FveUpdateBandIdBcd(v67);
              if ( updated < 0
                && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  77,
                  WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                  (unsigned int)updated);
              }
              v14 = v46;
              if ( (v46 & 0x2004400) == 0x4400 )
              {
                v33 = TryResumeOSVolumeProtection(v67, szVolumeName);
                if ( v33 < 0
                  && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    78,
                    WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                    (unsigned int)v33);
                }
              }
              v26 = v47;
LABEL_128:
              if ( *(_BYTE *)(CBdeSvcDE::GetSupportLevel(v64) + 3)
                && (v14 & 0x4001) == 0x4000
                && (v57 & 0x80u) == 0LL
                && (unsigned int)FveCanProvisionDE(&FVE_GUID_PROV_SCENARIO_AUTODE, 0)
                && ((int)IsVolumeVirtual(szVolumeName, &v45) < 0 || !v45) )
              {
                v34 = FveInitializeDeviceEncryption3(v67, 0, &FVE_GUID_PROV_SCENARIO_AUTODE);
                if ( v34 < 0 )
                {
                  v35 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      79,
                      WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                      (unsigned int)v34);
                    goto LABEL_142;
                  }
LABEL_143:
                  if ( v26 )
                  {
                    if ( (v14 & 0x400000) != 0 )
                    {
                      if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 8) != 0 )
                        WPP_SF_(v35[2], 84, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
                    }
                    else
                    {
                      PersistentRequestsFolder = FveCreatePersistentRequestsFolder(szVolumeName);
                      if ( PersistentRequestsFolder < 0
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        WPP_SF_SD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          81,
                          (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                          (unsigned int)szVolumeName,
                          PersistentRequestsFolder);
                      }
                      wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADRecoveryPasswordDeletion>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_AADRecoveryPasswordDeletion>::GetImpl'::`2'::impl);
                      v38 = FveSetACLsByReqTypeAndUserType(szVolumeName);
                      if ( v38 < 0
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        WPP_SF_SD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          82,
                          (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                          (unsigned int)szVolumeName,
                          v38);
                      }
                    }
                    if ( (v14 & 0x4000) != 0 )
                    {
                      v39 = WorkerThreadLauncher((unsigned int (*)(void *))BdeSvcAADBackupReliabilityCheckAndRPStatWorkerThread);
                      if ( v39
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          85,
                          WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                          v39);
                      }
                      v40 = WorkerThreadLauncher((unsigned int (*)(void *))BdeSvcPcrMonitorWorkerThread);
                      v49 = v40;
                      if ( v40
                        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          86,
                          WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                          v40);
                      }
                    }
                  }
LABEL_196:
                  try
                  {
                    v41 = v70;
                    std::wstring::wstring(v65, szVolumeName);
                    v77[0] = v14;
                    v77[1] = v41;
                    v77[2] = v51;
                    v78 = v59;
                    v79 = v47;
                    v80 = v50;
                    v81 = v58;
                    std::wstring::wstring(v82, v65);
                    v83 = v52;
                    v84 = IsVolumeEncryptable;
                    v85 = v54;
                    v86 = v57;
                    v87 = v75;
                    std::wstring::~wstring(v65);
                    std::wstring::wstring(v95, szVolumeName);
                    VolumeEntry::VolumeEntry(v96, v77);
                    std::_Tree<std::_Tmap_traits<std::wstring,VolumeEntry,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,VolumeEntry>>,0>>::emplace<std::pair<std::wstring const,VolumeEntry> &>(
                      v60,
                      v66,
                      v95);
                    std::pair<std::wstring const,VolumeEntry>::~pair<std::wstring const,VolumeEntry>(v95);
                    std::wstring::~wstring(v82);
                  }
                  catch ( ... )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      WPP_SF_S(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        87,
                        WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
                        szVolumeName);
                    v60 = v61;
                    v56 = v62;
                    continue;
                  }
                  continue;
                }
                v35 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  goto LABEL_143;
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
              }
LABEL_142:
              v35 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_143;
            }
            v36 = v14 == 0;
            v14 = v46;
            if ( !v36 )
              goto LABEL_128;
            goto LABEL_196;
          }
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v13 = 66;
            goto LABEL_26;
          }
        }
        else
        {
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v13 = 63;
            goto LABEL_26;
          }
        }
      }
      else
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v13 = 62;
          goto LABEL_26;
        }
      }
    }
    else
    {
      LOBYTE(Status) = GetLastError();
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v13 = 59;
LABEL_26:
        WPP_SF_SD(
          v12[2],
          v13,
          (unsigned int)WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
          (unsigned int)szVolumeName,
          Status);
        continue;
      }
    }
  }
  v42 = 0;
  if ( i != -2147024878 )
    v42 = i;
  if ( a4 && v55 )
    BdeSvcSQMDiffuserVolume(v48);
  if ( v42 >= 0 )
  {
LABEL_178:
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  else
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        WPP_09423e3e68a53bdf96979f905547dd55_Traceguids,
        (unsigned int)v42);
      goto LABEL_178;
    }
  }
  v5 = v56;
  v8 = v49;
LABEL_180:
  if ( v69 != -1 )
  {
    FveCloseVolume();
    v69 = -1;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v67 != (void *)-1LL )
  {
    FveCloseVolume();
    v67 = (void *)-1LL;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v68 != -1 )
  {
    FveSysCloseVolume();
    v68 = -1;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    *v5 = v55;
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x20) != 0 )
    WPP_SF_(v7[2], 89, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids);
  return v8;
}

```

## disassembly

```asm
0x1800053a0  mov     [rsp+arg_18], r9b
0x1800053a5  mov     [rsp+arg_8], dl
0x1800053a9  push    rbx
0x1800053aa  push    rsi
0x1800053ab  push    rdi
0x1800053ac  push    r12
0x1800053ae  push    r13
0x1800053b0  push    r14
0x1800053b2  push    r15
0x1800053b4  sub     rsp, 4F0h
0x1800053bb  mov     rax, cs:__security_cookie
0x1800053c2  xor     rax, rsp
0x1800053c5  mov     [rsp+528h+var_48], rax
0x1800053cd  mov     rsi, r8
0x1800053d0  mov     [rsp+528h+var_4C8], r8
0x1800053d5  mov     r12, rcx
0x1800053d8  mov     [rsp+528h+var_4A8], rcx
0x1800053e0  mov     [rsp+528h+var_4A0], rcx
0x1800053e8  mov     [rsp+528h+var_498], r8
0x1800053f0  lea     r15, WPP_GLOBAL_Control
0x1800053f7  mov     rbx, cs:WPP_GLOBAL_Control
0x1800053fe  lea     r14, WPP_09423e3e68a53bdf96979f905547dd55_Traceguids
0x180005405  cmp     rbx, r15
0x180005408  jz      short loc_180005428
0x18000540a  test    byte ptr [rbx+1Ch], 20h
0x18000540e  jz      short loc_180005428
0x180005410  mov     edx, 38h ; '8'
0x180005415  mov     r8, r14
0x180005418  mov     rcx, [rbx+10h]
0x18000541c  call    WPP_SF_
0x180005421  mov     rbx, cs:WPP_GLOBAL_Control
0x180005428  xor     edi, edi
0x18000542a  mov     [rsp+528h+var_428], rdi
0x180005432  or      r13, 0FFFFFFFFFFFFFFFFh
0x180005436  mov     [rsp+528h+var_440], r13
0x18000543e  mov     [rsp+528h+var_42C], edi
0x180005445  xor     edx, edx; Val
0x180005447  mov     r8d, 208h; Size
0x18000544d  lea     rcx, [rsp+528h+szVolumeName]; void *
0x180005455  call    memset_0
0x18000545a  mov     [rsp+528h+var_438], edi
0x180005461  mov     [rsp+528h+cchReturnLength], edi
0x180005468  mov     [rsp+528h+var_4D0], rdi
0x18000546d  xor     edx, edx; Val
0x18000546f  mov     r8d, 90h; Size
0x180005475  lea     rcx, [rsp+528h+var_378]; void *
0x18000547d  call    memset_0
0x180005482  mov     [rsp+528h+var_450], r13
0x18000548a  mov     [rsp+528h+var_448], r13
0x180005492  mov     [rsp+528h+var_430], edi
0x180005499  xorps   xmm0, xmm0
0x18000549c  movups  [rsp+528h+var_420], xmm0
0x1800054a4  mov     [rsp+528h+SystemInformation], edi
0x1800054ab  xorps   xmm1, xmm1
0x1800054ae  movups  [rsp+528h+var_40C], xmm1
0x1800054b6  movups  [rsp+528h+var_40C+0Ch], xmm1
0x1800054be  mov     [rsp+528h+var_4F8], dil
0x1800054c3  test    rsi, rsi
0x1800054c6  jz      short loc_1800054D2
0x1800054c8  mov     [rsi], rdi
0x1800054cb  mov     rbx, cs:WPP_GLOBAL_Control
0x1800054d2  test    r12, r12
0x1800054d5  jnz     short loc_18000550B
0x1800054d7  cmp     rbx, r15
0x1800054da  jz      short loc_180005500
0x1800054dc  mov     r12d, 2
0x1800054e2  test    [rbx+1Ch], r12b
0x1800054e6  jz      short loc_180005500
0x1800054e8  lea     edx, [r12+37h]
0x1800054ed  mov     r8, r14
0x1800054f0  mov     rcx, [rbx+10h]
0x1800054f4  call    WPP_SF_
0x1800054f9  mov     rbx, cs:WPP_GLOBAL_Control
0x180005500  mov     r12d, 57h ; 'W'
0x180005506  jmp     loc_18000617C
0x18000550b  mov     [rsp+528h+var_4E8], edi
0x18000550f  mov     [rsp+528h+var_4E0], edi
0x180005513  mov     [rsp+528h+var_4D8], edi
0x180005517  mov     [rsp+528h+var_4EC], edi
0x18000551b  mov     dword ptr [rsp+528h+var_428], 1
0x180005526  mov     dword ptr [rsp+528h+var_428+4], r13d
0x18000552e  lea     rdx, [rsp+528h+var_428]
0x180005536  lea     rcx, [rsp+528h+var_440]
0x18000553e  call    cs:__imp_FveFindFirstVolume
0x180005545  nop     dword ptr [rax+rax+00h]
0x18000554a  mov     r12d, 2
0x180005550  test    eax, eax
0x180005552  js      loc_18000611D
0x180005558  mov     rcx, [rsp+528h+var_450]
0x180005560  cmp     rcx, r13
0x180005563  jz      short loc_180005579
0x180005565  call    cs:__imp_FveCloseVolume
0x18000556c  nop     dword ptr [rax+rax+00h]
0x180005571  mov     [rsp+528h+var_450], r13
0x180005579  mov     rcx, [rsp+528h+var_448]
0x180005581  cmp     rcx, r13
0x180005584  jz      short loc_18000559A
0x180005586  call    cs:__imp_FveSysCloseVolume
0x18000558d  nop     dword ptr [rax+rax+00h]
0x180005592  mov     [rsp+528h+var_448], r13
0x18000559a  mov     [rsp+528h+var_438], edi
0x1800055a1  mov     [rsp+528h+var_4D4], edi
0x1800055a5  mov     [rsp+528h+cchReturnLength], edi
0x1800055ac  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800055b3  movdqu  [rsp+528h+var_420], xmm0
0x1800055bc  mov     [rsp+528h+var_42C], 104h
0x1800055c7  lea     r8, [rsp+528h+szVolumeName]
0x1800055cf  lea     rdx, [rsp+528h+var_42C]
0x1800055d7  mov     rcx, [rsp+528h+var_440]
0x1800055df  call    cs:__imp_FveGetVolumeNameW
0x1800055e6  nop     dword ptr [rax+rax+00h]
0x1800055eb  test    eax, eax
0x1800055ed  jns     short loc_180005622
0x1800055ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800055f6  cmp     rcx, r15
0x1800055f9  jz      loc_1800060FC
0x1800055ff  test    [rcx+1Ch], r12b
0x180005603  jz      loc_1800060FC
0x180005609  mov     edx, 3Ah ; ':'
0x18000560e  mov     r9d, eax
0x180005611  mov     r8, r14
0x180005614  mov     rcx, [rcx+10h]
0x180005618  call    WPP_SF_d
0x18000561d  jmp     loc_1800060FC
0x180005622  lea     r9, [rsp+528h+cchReturnLength]; lpcchReturnLength
0x18000562a  xor     r8d, r8d; cchBufferLength
0x18000562d  xor     edx, edx; lpszVolumePathNames
0x18000562f  lea     rcx, [rsp+528h+szVolumeName]; lpszVolumeName
0x180005637  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18000563e  nop     dword ptr [rax+rax+00h]
0x180005643  test    eax, eax
0x180005645  jnz     loc_1800060D1
0x18000564b  call    cs:__imp_GetLastError
0x180005652  nop     dword ptr [rax+rax+00h]
0x180005657  cmp     eax, 0EAh
0x18000565c  jz      short loc_1800056B2
0x18000565e  call    cs:__imp_GetLastError
0x180005665  nop     dword ptr [rax+rax+00h]
0x18000566a  test    eax, eax
0x18000566c  jle     short loc_180005676
0x18000566e  movzx   eax, ax
0x180005671  or      eax, 80070000h
0x180005676  mov     rcx, cs:WPP_GLOBAL_Control
0x18000567d  cmp     rcx, r15
0x180005680  jz      loc_1800060FC
0x180005686  test    [rcx+1Ch], r12b
0x18000568a  jz      loc_1800060FC
0x180005690  mov     edx, 3Bh ; ';'
0x180005695  mov     dword ptr [rsp+528h+var_508], eax
0x180005699  lea     r9, [rsp+528h+szVolumeName]
0x1800056a1  mov     r8, r14
0x1800056a4  mov     rcx, [rcx+10h]
0x1800056a8  call    WPP_SF_SD
0x1800056ad  jmp     loc_1800060FC
0x1800056b2  mov     esi, edi
0x1800056b4  mov     [rsp+528h+var_4F0], edi
0x1800056b8  mov     [rsp+528h+var_4E4], edi
0x1800056bc  mov     [rsp+528h+var_4B0], rdi
0x1800056c1  mov     [rsp+528h+var_4DC], edi
0x1800056c5  mov     [rsp+528h+var_4C0], rdi
0x1800056ca  mov     eax, edi
0x1800056cc  cmp     [rsp+528h+cchReturnLength], 1
0x1800056d4  setnbe  al
0x1800056d7  mov     [rsp+528h+var_4B8], eax
0x1800056db  xor     edx, edx; Val
0x1800056dd  mov     r8d, 88h; Size
0x1800056e3  lea     rcx, [rsp+528h+var_370]; void *
0x1800056eb  call    memset_0
0x1800056f0  mov     [rsp+528h+var_378], 90h
0x1800056fb  mov     [rsp+528h+var_374], 0Ah
0x180005706  mov     rcx, cs:WPP_GLOBAL_Control
0x18000570d  cmp     rcx, r15
0x180005710  jz      short loc_180005731
0x180005712  test    byte ptr [rcx+1Ch], 8
0x180005716  jz      short loc_180005731
0x180005718  mov     edx, 3Dh ; '='
0x18000571d  lea     r9, [rsp+528h+szVolumeName]
0x180005725  mov     r8, r14
0x180005728  mov     rcx, [rcx+10h]
0x18000572c  call    WPP_SF_S
0x180005731  cmp     [rsp+528h+arg_18], dil
0x180005739  jz      loc_180005F6E
0x18000573f  lea     rax, [rsp+528h+var_450]
0x180005747  mov     [rsp+528h+var_500], rax
0x18000574c  mov     dword ptr [rsp+528h+var_508], 1
0x180005754  mov     r9d, r13d
0x180005757  xor     r8d, r8d
0x18000575a  xor     edx, edx
0x18000575c  mov     rcx, [rsp+528h+var_440]
0x180005764  call    cs:__imp_FveOpenVolumeByHandle
0x18000576b  nop     dword ptr [rax+rax+00h]
0x180005770  test    eax, eax
0x180005772  jns     short loc_180005798
0x180005774  mov     rcx, cs:WPP_GLOBAL_Control
0x18000577b  cmp     rcx, r15
0x18000577e  jz      loc_1800060FC
0x180005784  test    [rcx+1Ch], r12b
0x180005788  jz      loc_1800060FC
0x18000578e  mov     edx, 3Eh ; '>'
0x180005793  jmp     loc_180005695
0x180005798  lea     rdx, [rsp+528h+var_378]
0x1800057a0  mov     rcx, [rsp+528h+var_450]
0x1800057a8  call    cs:__imp_FveGetStatus
0x1800057af  nop     dword ptr [rax+rax+00h]
0x1800057b4  test    eax, eax
0x1800057b6  jns     short loc_1800057DC
0x1800057b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800057bf  cmp     rcx, r15
0x1800057c2  jz      loc_1800060FC
0x1800057c8  test    [rcx+1Ch], r12b
0x1800057cc  jz      loc_1800060FC
0x1800057d2  mov     edx, 3Fh ; '?'
0x1800057d7  jmp     loc_180005695
0x1800057dc  mov     ebx, [rsp+528h+var_36C]
0x1800057e3  mov     [rsp+528h+var_4F4], ebx
0x1800057e7  mov     eax, [rsp+528h+var_348]
0x1800057ee  mov     [rsp+528h+var_4E0], eax
0x1800057f2  mov     r8, [rsp+528h+var_358]
0x1800057fa  mov     [rsp+528h+var_4B0], r8
0x1800057ff  mov     eax, [rsp+528h+var_360]
0x180005806  mov     [rsp+528h+var_4DC], eax
0x18000580a  mov     rax, [rsp+528h+var_340]
0x180005812  mov     [rsp+528h+var_4C0], rax
0x180005817  mov     rcx, cs:WPP_GLOBAL_Control
0x18000581e  cmp     rcx, r15
0x180005821  jz      short loc_180005842
0x180005823  test    byte ptr [rcx+1Ch], 8
0x180005827  jz      short loc_180005842
0x180005829  mov     edx, 40h ; '@'
0x18000582e  mov     [rsp+528h+var_508], r8
0x180005833  mov     r9d, ebx
0x180005836  mov     r8, r14
0x180005839  mov     rcx, [rcx+10h]
0x18000583d  call    WPP_SF_Li
0x180005842  and     ebx, 1
0x180005845  jz      short loc_18000589A
0x180005847  lea     rdx, [rsp+528h+var_430]
0x18000584f  mov     rcx, [rsp+528h+var_450]
0x180005857  call    cs:__imp_FveGetFveMethod
0x18000585e  nop     dword ptr [rax+rax+00h]
0x180005863  test    eax, eax
0x180005865  js      short loc_18000589A
0x180005867  mov     eax, [rsp+528h+var_430]
0x18000586e  dec     eax
0x180005870  cmp     eax, 1
0x180005873  mov     eax, [rsp+528h+var_4F4]
0x180005877  ja      short loc_18000589E
0x180005879  bt      eax, 0Eh
0x18000587d  jnb     short loc_180005886
0x18000587f  or      [rsp+528h+var_4EC], 1
0x180005884  jmp     short loc_18000589E
0x180005886  bt      eax, 16h
0x18000588a  jnb     short loc_180005893
0x18000588c  or      [rsp+528h+var_4EC], 4
0x180005891  jmp     short loc_18000589E
0x180005893  or      [rsp+528h+var_4EC], r12d
0x180005898  jmp     short loc_18000589E
0x18000589a  mov     eax, [rsp+528h+var_4F4]
0x18000589e  and     eax, 4200h
0x1800058a3  cmp     eax, 4200h
0x1800058a8  jz      short loc_1800058BD
0x1800058aa  lea     rcx, [rsp+528h+var_490]
0x1800058b2  call    ?GetSupportLevel@CBdeSvcDE@@SA?AVDeviceEncryptionSupportLevel@@XZ; CBdeSvcDE::GetSupportLevel(void)
0x1800058b7  cmp     [rax+3], dil
0x1800058bb  jz      short loc_1800058EC
0x1800058bd  call    ?EnsureRegistered@WinRENotificationListener@@SAJXZ; WinRENotificationListener::EnsureRegistered(void)
0x1800058c2  test    eax, eax
0x1800058c4  jns     short loc_1800058EC
0x1800058c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058cd  cmp     rcx, r15
0x1800058d0  jz      short loc_1800058EC
0x1800058d2  test    [rcx+1Ch], r12b
0x1800058d6  jz      short loc_1800058EC
0x1800058d8  mov     edx, 41h ; 'A'
0x1800058dd  mov     r9d, eax
0x1800058e0  mov     r8, r14
0x1800058e3  mov     rcx, [rcx+10h]
0x1800058e7  call    WPP_SF_d
0x1800058ec  cmp     [rsp+528h+arg_8], dil
0x1800058f4  jz      loc_180005ADF
0x1800058fa  lea     rax, [rsp+528h+var_448]
0x180005902  mov     [rsp+528h+var_500], rax
0x180005907  mov     dword ptr [rsp+528h+var_508], 1
0x18000590f  xor     edx, edx
0x180005911  lea     r9d, [rdx+1]
0x180005915  mov     r8d, r9d
0x180005918  mov     rcx, [rsp+528h+var_440]
0x180005920  call    cs:__imp_FveOpenVolumeByHandle
0x180005927  nop     dword ptr [rax+rax+00h]
0x18000592c  test    eax, eax
0x18000592e  jns     short loc_180005954
0x180005930  mov     rcx, cs:WPP_GLOBAL_Control
0x180005937  cmp     rcx, r15
0x18000593a  jz      loc_1800060FC
0x180005940  test    [rcx+1Ch], r12b
0x180005944  jz      loc_1800060FC
0x18000594a  mov     edx, 42h ; 'B'
0x18000594f  jmp     loc_180005695
0x180005954  lea     rcx, stru_18009BA00; lpCriticalSection
0x18000595b  call    cs:__imp_EnterCriticalSection
  ... truncated ...
```
