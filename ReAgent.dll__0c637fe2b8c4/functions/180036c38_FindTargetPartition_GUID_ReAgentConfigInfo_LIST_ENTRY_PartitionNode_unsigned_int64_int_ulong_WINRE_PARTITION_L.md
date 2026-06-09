# FindTargetPartition(_GUID *,ReAgentConfigInfo *,_LIST_ENTRY *,PartitionNode *,unsigned __int64,int,ulong,_WINRE_PARTITION_LOCATION,ushort const *,PartitionNode *,int *)

- ea: `0x180036c38`
- end: `0x180037779`
- name: `?FindTargetPartition@@YAKPEAU_GUID@@PEAUReAgentConfigInfo@@PEAU_LIST_ENTRY@@PEAUPartitionNode@@_KHKW4_WINRE_PARTITION_LOCATION@@PEBG3PEAH@Z`
- size: `2881`
- prototype: `__int64 __fastcall(struct _GUID *, __int64, __int64 **, struct PartitionNode *, unsigned __int64, int, int, unsigned int, const WCHAR *, void *, _DWORD *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180017248`

## callees

- `0x180002786`
- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18000edec`
- `0x1800103f4`
- `0x1800106d4`
- `0x1800109d0`
- `0x18001a170`
- `0x18001e4c8`
- `0x180030c54`
- `0x180031814`
- `0x180031a00`
- `0x180031fa4`
- `0x1800320e4`
- `0x18003211c`
- `0x18003214c`
- `0x180036b64`
- `0x180036c38`
- `0x180037780`
- `0x180037cb8`
- `0x180037eb4`
- `0x1800380ac`
- `0x1800385b8`
- `0x18003e728`
- `0x1800448b8`
- `0x180044d84`
- `0x180045eac`
- `0x18004c820`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800373cc`
- `KERNEL32!GetLastError` at `0x1800373cc`
- `KERNEL32!DeleteFileW` at `0x180037184`
- `KERNEL32!DeleteFileW` at `0x180037184`
- `ole32!CoTaskMemFree` at `0x1800376ae`
- `ole32!CoTaskMemFree` at `0x1800376ae`

## string_xrefs

- `0x180036dc5`: `Failed to get config path`
- `0x180036d49`: `Failed to get config path from os guid`
- `0x180036d50`: `base\diagnosis\srt\reagent2\reagent\install.cpp`
- `0x180036dfd`: ` Error 0X%X while detecting OS install type`
- `0x180037003`: ` skip partition because it is the os install location partition`
- `0x180037060`: `Complete looping through each partition`
- `0x180037195`: ` Could not delete %s`
- `0x1800373d5`: `Failed to save offset of new partition to undo directory [%s]. Err: 0x%08x`
- `0x180037590`: ` Attempting to create a new partition for WinRE`
- `0x1800375cf`: ` New WinRE partition created`
- `0x180037629`: ` Failed to create the new WinRE partition`

## pseudocode

```c
__int64 __fastcall FindTargetPartition(
        struct _GUID *a1,
        __int64 a2,
        __int64 **a3,
        struct PartitionNode *a4,
        unsigned __int64 a5,
        int a6,
        int a7,
        unsigned int a8,
        const WCHAR *a9,
        void *a10,
        _DWORD *a11)
{
  WCHAR *v14; // r14
  __int64 v15; // r8
  unsigned int VolumeFromOffset; // eax
  const void *v17; // rsi
  unsigned int v18; // r12d
  unsigned int ConfigFilePathFromOsGuid; // ebx
  const wchar_t *v20; // r8
  unsigned int v21; // eax
  __int64 *v22; // r15
  __int64 *v23; // rdi
  __int64 v24; // rsi
  int v25; // r12d
  unsigned __int64 v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // r11
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  const unsigned __int16 *v31; // r8
  unsigned __int64 v32; // r14
  __int64 v33; // r8
  const wchar_t *v34; // rdx
  int v35; // edi
  ULONG v36; // edx
  BOOL (__stdcall *v37)(const PVOID, PVOID); // r8
  int v38; // eax
  __int64 v39; // rax
  unsigned __int64 v40; // r9
  unsigned __int64 v41; // r14
  unsigned __int64 v42; // r9
  struct PartitionNode *v43; // r14
  LPCWSTR v44; // rdi
  DWORD LastError; // eax
  struct PartitionNode *v46; // rdi
  struct PartitionNode *v47; // rdi
  __int64 v48; // rax
  struct PartitionNode *v49; // r9
  unsigned __int64 v50; // rdi
  __int64 v51; // r8
  unsigned int v52; // eax
  unsigned __int64 *v54; // [rsp+28h] [rbp-D8h]
  int v55; // [rsp+30h] [rbp-D0h] BYREF
  int v56; // [rsp+34h] [rbp-CCh] BYREF
  int v57; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v58; // [rsp+40h] [rbp-C0h] BYREF
  struct PartitionNode *v59; // [rsp+48h] [rbp-B8h]
  unsigned int v60; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v61; // [rsp+58h] [rbp-A8h] BYREF
  struct PartitionNode *v62; // [rsp+60h] [rbp-A0h] BYREF
  struct PartitionNode *v63; // [rsp+68h] [rbp-98h]
  __int64 *v64; // [rsp+70h] [rbp-90h]
  struct _GUID *v65; // [rsp+78h] [rbp-88h]
  void *v66; // [rsp+80h] [rbp-80h]
  __int64 v67; // [rsp+88h] [rbp-78h]
  struct _GUID v68; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD *v70; // [rsp+B0h] [rbp-50h]
  LPVOID pv; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR VolumeName[4]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v73[1320]; // [rsp+C8h] [rbp-38h] BYREF
  _DWORD UserData[4]; // [rsp+5F0h] [rbp+4F0h] BYREF
  WCHAR FileName; // [rsp+600h] [rbp+500h] BYREF
  _BYTE v76[606]; // [rsp+602h] [rbp+502h] BYREF

  lpFileName[0] = a9;
  v58 = (unsigned __int64)a3;
  v67 = a2;
  v65 = a1;
  v66 = a10;
  v59 = a4;
  v70 = a11;
  v56 = 0;
  v57 = 0;
  *(_QWORD *)VolumeName = 0;
  memset_0(v73, 0, sizeof(v73));
  pv = 0;
  v14 = 0;
  UnattendLogW(0, L"Entering FindTargetPartition");
  if ( a11 )
    *a11 = 0;
  if ( *(_WORD *)(a2 + 6232) )
  {
    VolumeFromOffset = winreFindVolumeFromOffset((int)a2 + 6232, 0, (unsigned int)VolumeName, 0, 0);
    if ( VolumeFromOffset == 3 )
    {
      UnattendLogW(0, L" Downlevel winre.wim not found");
    }
    else
    {
      if ( VolumeFromOffset )
      {
        UnattendLogW(1, L" Error 0X%X while searching for downlevel winre.wim", VolumeFromOffset);
        goto LABEL_126;
      }
      UnattendLogW(0, L" Downlevel winre.wim found");
      v14 = VolumeName;
    }
  }
  *(_QWORD *)&v68.Data1 = 0;
  v17 = 0;
  v18 = 6;
  if ( a1 )
  {
    ConfigFilePathFromOsGuid = winreGetConfigFilePathFromOsGuid(a1);
    if ( ConfigFilePathFromOsGuid )
    {
      LODWORD(v54) = 898;
      v20 = L"Failed to get config path from os guid";
LABEL_9:
      UnattendLogW(
        2,
        L"FindTargetPartition %s (0x%x) in file %S line %d",
        v20,
        ConfigFilePathFromOsGuid,
        "base\\diagnosis\\srt\\reagent2\\reagent\\install.cpp",
        v54);
      goto LABEL_120;
    }
  }
  else
  {
    ConfigFilePathFromOsGuid = winreGetConfigFilePathFromWinDir(0, 0, v15, &pv);
    if ( ConfigFilePathFromOsGuid )
    {
      LODWORD(v54) = 907;
      v20 = L"Failed to get config path";
      goto LABEL_9;
    }
  }
  UserData[0] = WinReIsWimBootEnabledInternal((LPCWSTR)pv);
  v55 = 0;
  v21 = IsClientEdition(a1, &v55);
  LODWORD(v61) = v21;
  ConfigFilePathFromOsGuid = v21;
  if ( v21 )
  {
    UnattendLogW(1, L" Error 0X%X while detecting OS install type", v21);
    goto LABEL_120;
  }
  v22 = 0;
  v63 = 0;
  v62 = 0;
  v64 = 0;
  v60 = 0;
  if ( !a6 )
    UnattendLogW(0, L" Not allowed to repartition the disk");
  memset_0(v66, 0, 0x530u);
  UnattendLogW(
    0,
    L"Start looping through each partition and initialize os partition, recovery partition and system partition for MBR");
  v23 = *a3;
  if ( v23 != (__int64 *)v58 )
  {
    v24 = v67;
    v25 = UserData[0];
    v26 = v58;
    while ( 1 )
    {
      UnattendLogW(
        0,
        L" Checking partition at offset %I64u, partition number: %d",
        v23[158],
        *((unsigned int *)v23 + 325));
      if ( (unsigned int)winreIsSameDisk(v59, v23) )
      {
        ++v60;
        if ( v14 && (unsigned int)winreIsSamePartition(v14, v27) )
        {
          UnattendLogW(0, L" skip partition because it is downlevel WinRe partition");
        }
        else if ( *((_DWORD *)v23 + 329) )
        {
          v63 = (struct PartitionNode *)v23;
          UnattendLogW(0, L" find OS partition");
        }
        else if ( *((_DWORD *)v23 + 327) )
        {
          if ( *((_DWORD *)v23 + 328) )
          {
            v62 = (struct PartitionNode *)v23;
            UnattendLogW(0, L" NOTE: find system partition and not OS partition for MBR");
          }
          else
          {
            if ( *((_BYTE *)v23 + 16) == 39 )
              goto LABEL_35;
            UnattendLogW(0, L" skip MBR Partition which type is not MSFT_RECOVERY");
          }
        }
        else
        {
          if ( v23[2] == *(_QWORD *)&PARTITION_MSFT_RECOVERY_GUID.Data1
            && v23[3] == *(_QWORD *)PARTITION_MSFT_RECOVERY_GUID.Data4 )
          {
LABEL_35:
            if ( !(unsigned int)winreDoesFileExist((unsigned __int16 *)v23 + 328, L"$WINRE_BACKUP_PARTITION.MARKER")
              || (UnattendLogW(0, L" partition contains winre backup partition marker"), *((_DWORD *)v23 + 329)) )
            {
              if ( v64 && v23[158] > (unsigned __int64)v64[158] )
              {
                UnattendLogW(0, L" skip partition beyond current candidate partition on disk");
              }
              else if ( (unsigned int)MeetPartitionRequirements((struct PartitionNode *)v23, v59, a5, v55, &v56, &v57) )
              {
                UnattendLogW(0, L" partition meets requirements");
                if ( v25 || !(unsigned int)winreIsSamePartition2(v23, v24 + 2496) )
                {
                  if ( (unsigned int)IsPartitionInUse(v23) )
                  {
                    UnattendLogW(0, L" skip partition because it is in use");
                  }
                  else
                  {
                    v64 = v23;
                    UnattendLogW(0, L" NOTE: select partition because it meets WinRE requirements");
                  }
                }
                else
                {
                  UnattendLogW(0, L" skip partition because it is the os install location partition");
                }
              }
              else
              {
                UnattendLogW(0, L" skip partition because it does not meet WinRE requirements");
              }
            }
            else
            {
              v22 = v23;
              UnattendLogW(0, L" NOTE: find existing WinRE partition and continue");
            }
            goto LABEL_50;
          }
          UnattendLogW(0, L" skip GPT Partition which type is not PARTITION_MSFT_RECOVERY_GUID");
        }
      }
      else
      {
        UnattendLogW(0, L" skip partition because it is not on the same disk as staging partition");
      }
LABEL_50:
      v23 = (__int64 *)*v23;
      if ( v23 == (__int64 *)v26 )
      {
        ConfigFilePathFromOsGuid = v61;
        v18 = 6;
        v17 = *(const void **)&v68.Data1;
        break;
      }
    }
  }
  UnattendLogW(0, L"Complete looping through each partition");
  UnattendLogW(0, L"----Search target partition option #1: try existing WinRE partition");
  if ( !v22 )
    goto LABEL_95;
  FileName = 0;
  memset_0(v76, 0, 0x25Au);
  v58 = 0;
  if ( v22 == (__int64 *)-656LL )
  {
    ConfigFilePathFromOsGuid = 87;
LABEL_94:
    LODWORD(v54) = 1107;
    v20 = L"failed to append WinRE backup part marker";
    goto LABEL_9;
  }
  ConfigFilePathFromOsGuid = StringCchLengthW((const unsigned __int16 *)v22 + 328, 0x7FFFFFFFu, &v58);
  if ( (ConfigFilePathFromOsGuid & 0x80000000) == 0 )
  {
    if ( !v58 || (v31 = L"%s\\%s", *(_WORD *)(v28 + 2 * v58 - 2) == 92) )
      v31 = L"%s%s";
    ConfigFilePathFromOsGuid = StringCchPrintfW(&FileName, 0x12Eu, v31, v28, L"$WINRE_BACKUP_PARTITION.MARKER");
    if ( (ConfigFilePathFromOsGuid & 0x80000000) == 0 )
    {
      ConfigFilePathFromOsGuid = 0;
      goto LABEL_69;
    }
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v30 = 15;
      goto LABEL_65;
    }
  }
  else
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v30 = 14;
LABEL_65:
      WPP_SF_d(v29[2], v30, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, ConfigFilePathFromOsGuid);
    }
  }
  ConfigFilePathFromOsGuid = (unsigned __int16)ConfigFilePathFromOsGuid;
  if ( (_WORD)ConfigFilePathFromOsGuid )
    goto LABEL_94;
LABEL_69:
  if ( !DeleteFileW(&FileName) )
    UnattendLogW(2, L" Could not delete %s", &FileName);
  v32 = a5;
  if ( (unsigned int)MeetPartitionRequirements((struct PartitionNode *)v22, v59, a5, v55, &v56, &v57) )
  {
    v33 = v22[158];
    v34 = L"Found target partition: use the existing WinRE partition, offset: %I64u";
LABEL_73:
    v17 = v22;
    UnattendLogW(0, v34, v33);
    v18 = 0;
    goto LABEL_121;
  }
  UnattendLogW(0, L"Existing WinRE partition does not have enough free space to meet the requirements");
  if ( v56 && a6 )
  {
    v35 = 0;
    memset_0(VolumeName, 0, 0x25Cu);
    if ( !v65
      || (unsigned int)winreGetWinDir(v65, VolumeName)
      || (UserData[0] = 0, WofEnumEntries(VolumeName, v36, v37, UserData), (v35 = UserData[0]) == 0) )
    {
      if ( (unsigned int)ExistingWinReFullPartitionMeetRequirements((struct PartitionNode *)v22, v59, a5, v55) )
      {
        UnattendLogW(0, L"Formatting the existing WinRE partition because its total size is big enough");
        v38 = winreFormatPartition(*((_DWORD *)v22 + 324), v22[158]);
        v33 = v22[158];
        if ( v38 )
        {
          v34 = L"Found target partition: use the existing WinRE partition and format it, offset: %I64u";
          goto LABEL_73;
        }
        UnattendLogW(2, L"Failed to format the existing WinRE partition, offset: %I64u", v33);
      }
    }
    v39 = winreEstimateBufferNeededOnPartition(0, a5, 1, 0, v55);
    v61 = v40;
    v58 = v40;
    v68 = GUID_NULL;
    v41 = v39 + a5;
    UnattendLogW(0, L"Trying to expand the existing WinRE partition while it doesn't meet because no disk space");
    if ( v41 < 0x1C200000 )
      v41 = 471859200;
    if ( !v35 )
    {
      v42 = v41 + 0xFFFFF;
      v43 = v63;
      if ( winreRecreateTargetPartition(v65, (struct PartitionNode *)v22, v63, v42 & 0xFFFFFFFFFFF00000uLL, &v68, &v61) )
      {
        UnattendLogW(0, L" WinRE partition expanded");
        PrivateFreePartitionList(0);
        if ( (unsigned int)winreFindPartitionByOffset(v61, &v58) )
        {
          v17 = (const void *)v58;
          UnattendLogW(
            0,
            L"Found target partition: use the existing WinRE partition after expansion, offset: %I64u",
            *(_QWORD *)(v58 + 1264));
          v18 = 1;
        }
        v44 = lpFileName[0];
        if ( lpFileName[0] && !(unsigned int)SaveNewOffsetToBackup(lpFileName[0], v61, L"New Partition offset") )
        {
          LastError = GetLastError();
          UnattendLogW(2, L"Failed to save offset of new partition to undo directory [%s]. Err: 0x%08x", v44, LastError);
        }
        goto LABEL_120;
      }
      UnattendLogW(2, L"Failed to expand the WinRE partition");
      goto LABEL_96;
    }
  }
LABEL_95:
  v43 = v63;
LABEL_96:
  UnattendLogW(0, L"----Search target partition option #2: try first recovery partition");
  if ( !v64 )
  {
    UnattendLogW(0, L"----Search target partition option #3: try system partition for MBR");
    v46 = v62;
    if ( v62 && (unsigned int)MeetPartitionRequirements(v62, v59, a5, v55, &v56, &v57) )
    {
      v17 = v46;
      UnattendLogW(0, L"Found target partition: use system partition for MBR, offset: %I64u", *((_QWORD *)v46 + 158));
      v18 = 4;
      v32 = a5;
      goto LABEL_121;
    }
    UnattendLogW(0, L"----Search target partition option #4: try new recovery partition if allowed");
    v47 = v59;
    if ( a6 && (!*((_DWORD *)v59 + 327) || v60 <= 3) )
    {
      v48 = winreEstimateBufferNeededOnPartition(0, a5, 1, 0, v55);
      v62 = v49;
      v58 = (unsigned __int64)v49;
      v50 = v48 + a5;
      *(GUID *)lpFileName = GUID_NULL;
      if ( v48 + a5 < 0x1C200000 )
        v50 = 471859200;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_OnlineWinREProvisioning>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_OnlineWinREProvisioning>::GetImpl'::`2'::impl) )
      {
        v52 = a7 << 20;
        v51 = (unsigned int)(a7 << 20);
        if ( a7 << 20 )
        {
          if ( v50 > v52 )
          {
            UnattendLogW(
              2,
              L" User provided partition size %I64u bytes is too small. The minimum required size is %I64u bytes",
              v52,
              v50);
            ConfigFilePathFromOsGuid = 87;
            goto LABEL_120;
          }
          v50 = v52;
          UnattendLogW(0, L" User provided partition size %I64u bytes is used");
        }
      }
      UnattendLogW(0, L" Attempting to create a new partition for WinRE", v51);
      if ( (unsigned int)winreGetNewPartitionWithCoInit(
                           v65,
                           (v50 + 0xFFFFF) & 0xFFFFFFFFFFF00000uLL,
                           a8,
                           lpFileName,
                           &v62) )
      {
        UnattendLogW(0, L" New WinRE partition created");
        if ( v70 )
          *v70 = 1;
        PrivateFreePartitionList(0);
        if ( (unsigned int)winreFindPartitionByOffset(v62, &v58) )
        {
          v17 = (const void *)v58;
          UnattendLogW(
            0,
            L"Found target partition: use the new WinRE partition, offset: %I64u",
            *(_QWORD *)(v58 + 1264));
          v18 = 2;
        }
        goto LABEL_120;
      }
      UnattendLogW(2, L" Failed to create the new WinRE partition");
      v47 = v59;
    }
    UnattendLogW(0, L"----Search target partition option #5: try target OS partition");
    if ( v43 && (unsigned int)MeetPartitionRequirements(v43, v47, a5, v55, &v56, &v57) )
    {
      v17 = v43;
      UnattendLogW(0, L"Found target partition: use target OS partition, offset: %I64u", *((_QWORD *)v43 + 158));
      v18 = 5;
    }
    goto LABEL_120;
  }
  v17 = v64;
  UnattendLogW(0, L"Found target partition: use the first recovery partition, offset: %I64u", v64[158]);
  v18 = 3;
LABEL_120:
  v32 = a5;
LABEL_121:
  if ( pv )
    CoTaskMemFree(pv);
  if ( !ConfigFilePathFromOsGuid && v17 )
  {
    TraceFindTargetPartitionResult(v32, v17, v18);
    memcpy_0(v66, v17, 0x530u);
    goto LABEL_133;
  }
LABEL_126:
  if ( v56 )
  {
    ConfigFilePathFromOsGuid = 112;
    UnattendLogW(0, L" No disk space");
  }
  else
  {
    ConfigFilePathFromOsGuid = 2;
    UnattendLogW(0, L" Partition not found ");
  }
  if ( v57 && !ReAgentError )
    ReAgentError = 17;
  AsmWinREFindTargetPartitionFailed(a5);
  UnattendLogW(1, L"failed to find target partition: 0x%x", ConfigFilePathFromOsGuid);
LABEL_133:
  UnattendLogW(0, L"Exit FindTargetPartition returns with status code: 0x%x", ConfigFilePathFromOsGuid);
  return ConfigFilePathFromOsGuid;
}

```

## disassembly

```asm
0x180036c38  push    rbp
0x180036c3a  push    rbx
0x180036c3b  push    rsi
0x180036c3c  push    rdi
0x180036c3d  push    r12
0x180036c3f  push    r13
0x180036c41  push    r14
0x180036c43  push    r15
0x180036c45  lea     rbp, [rsp-778h]
0x180036c4d  sub     rsp, 878h
0x180036c54  mov     rax, cs:__security_cookie
0x180036c5b  xor     rax, rsp
0x180036c5e  mov     [rbp+7B0h+var_50], rax
0x180036c65  mov     rax, [rbp+7B0h+arg_40]
0x180036c6c  xor     r12d, r12d
0x180036c6f  mov     rsi, [rbp+7B0h+arg_50]
0x180036c76  mov     rdi, r8
0x180036c79  mov     [rbp+7B0h+lpFileName], rax
0x180036c7d  mov     rbx, rdx
0x180036c80  mov     rax, [rbp+7B0h+arg_48]
0x180036c87  mov     r15, rcx
0x180036c8a  mov     [rsp+8B0h+var_870], r8
0x180036c8f  mov     r8d, 528h; Size
0x180036c95  mov     [rbp+7B0h+var_828], rdx
0x180036c99  xor     edx, edx; Val
0x180036c9b  mov     [rsp+8B0h+var_838], rcx
0x180036ca0  lea     rcx, [rbp+7B0h+var_7E8]; void *
0x180036ca4  mov     [rbp+7B0h+var_830], rax
0x180036ca8  mov     [rsp+8B0h+var_868], r9
0x180036cad  mov     [rbp+7B0h+var_800], rsi
0x180036cb1  mov     [rsp+8B0h+var_87C], r12d
0x180036cb6  mov     [rsp+8B0h+var_878], r12d
0x180036cbb  mov     qword ptr [rbp+7B0h+VolumeName], r12
0x180036cbf  call    memset_0
0x180036cc4  lea     rdx, aEnteringFindta; "Entering FindTargetPartition"
0x180036ccb  mov     [rbp+7B0h+pv], r12
0x180036ccf  xor     ecx, ecx
0x180036cd1  mov     r14d, r12d
0x180036cd4  call    UnattendLogW
0x180036cd9  test    rsi, rsi
0x180036cdc  jz      short loc_180036CE1
0x180036cde  mov     [rsi], r12d
0x180036ce1  lea     rcx, [rbx+1858h]
0x180036ce8  cmp     [rcx], r12w
0x180036cec  jz      short loc_180036D14
0x180036cee  xor     r9d, r9d
0x180036cf1  mov     dword ptr [rsp+8B0h+var_890], r12d
0x180036cf6  lea     r8, [rbp+7B0h+VolumeName]
0x180036cfa  xor     edx, edx
0x180036cfc  call    winreFindVolumeFromOffset
0x180036d01  cmp     eax, 3
0x180036d04  jnz     short loc_180036D75
0x180036d06  lea     rdx, aDownlevelWinre_2; " Downlevel winre.wim not found"
0x180036d0d  xor     ecx, ecx
0x180036d0f  call    UnattendLogW
0x180036d14  mov     qword ptr [rbp+7B0h+var_820.Data1], r12
0x180036d18  mov     rsi, r12
0x180036d1b  mov     r12d, 6
0x180036d21  lea     r13d, [r12-5]
0x180036d26  test    r15, r15
0x180036d29  jz      short loc_180036DAA
0x180036d2b  lea     r8, [rbp+7B0h+pv]
0x180036d2f  mov     rcx, r15
0x180036d32  call    winreGetConfigFilePathFromOsGuid
0x180036d37  mov     ebx, eax
0x180036d39  test    eax, eax
0x180036d3b  jz      loc_180036DCE
0x180036d41  mov     dword ptr [rsp+8B0h+var_888], 382h
0x180036d49  lea     r8, aFailedToGetCon_2; "Failed to get config path from os guid"
0x180036d50  lea     rax, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180036d57  mov     r9d, ebx
0x180036d5a  lea     rdx, aFindtargetpart; "FindTargetPartition %s (0x%x) in file %"...
0x180036d61  mov     [rsp+8B0h+var_890], rax
0x180036d66  mov     ecx, 2
0x180036d6b  call    UnattendLogW
0x180036d70  jmp     loc_18003769B
0x180036d75  test    eax, eax
0x180036d77  jnz     short loc_180036D8D
0x180036d79  lea     rdx, aDownlevelWinre_0; " Downlevel winre.wim found"
0x180036d80  xor     ecx, ecx
0x180036d82  call    UnattendLogW
0x180036d87  lea     r14, [rbp+7B0h+VolumeName]
0x180036d8b  jmp     short loc_180036D14
0x180036d8d  mov     r13d, 1
0x180036d93  lea     rdx, aError0xXWhileS; " Error 0X%X while searching for downlev"...
0x180036d9a  mov     ecx, r13d
0x180036d9d  mov     r8d, eax
0x180036da0  call    UnattendLogW
0x180036da5  jmp     loc_1800376E2
0x180036daa  lea     r9, [rbp+7B0h+pv]
0x180036dae  xor     edx, edx
0x180036db0  xor     ecx, ecx
0x180036db2  call    winreGetConfigFilePathFromWinDir
0x180036db7  mov     ebx, eax
0x180036db9  test    eax, eax
0x180036dbb  jz      short loc_180036DCE
0x180036dbd  mov     dword ptr [rsp+8B0h+var_888], 38Bh
0x180036dc5  lea     r8, aFailedToGetCon_1; "Failed to get config path"
0x180036dcc  jmp     short loc_180036D50
0x180036dce  mov     rcx, [rbp+7B0h+pv]; lpFileName
0x180036dd2  call    ?WinReIsWimBootEnabledInternal@@YAHPEAG@Z; WinReIsWimBootEnabledInternal(ushort *)
0x180036dd7  lea     rdx, [rsp+8B0h+var_880]; int *
0x180036ddc  mov     [rbp+7B0h+UserData], eax
0x180036de2  mov     rcx, r15; struct _GUID *
0x180036de5  mov     [rsp+8B0h+var_880], esi
0x180036de9  call    ?IsClientEdition@@YAKPEAU_GUID@@PEAH@Z; IsClientEdition(_GUID *,int *)
0x180036dee  xor     ecx, ecx
0x180036df0  mov     dword ptr [rsp+8B0h+var_858], eax
0x180036df4  mov     ebx, eax
0x180036df6  test    eax, eax
0x180036df8  jz      short loc_180036E11
0x180036dfa  mov     r8d, eax
0x180036dfd  lea     rdx, aError0xXWhileD; " Error 0X%X while detecting OS install "...
0x180036e04  mov     ecx, r13d
0x180036e07  call    UnattendLogW
0x180036e0c  jmp     loc_18003769B
0x180036e11  mov     r15, rcx
0x180036e14  mov     [rsp+8B0h+var_848], rcx
0x180036e19  mov     [rsp+8B0h+var_850], rcx
0x180036e1e  mov     [rsp+8B0h+var_840], rcx
0x180036e23  mov     [rsp+8B0h+var_860], ecx
0x180036e27  cmp     [rbp+7B0h+arg_28], ecx
0x180036e2d  jnz     short loc_180036E3B
0x180036e2f  lea     rdx, aNotAllowedToRe; " Not allowed to repartition the disk"
0x180036e36  call    UnattendLogW
0x180036e3b  mov     rcx, [rbp+7B0h+var_830]; void *
0x180036e3f  xor     edx, edx; Val
0x180036e41  mov     r8d, 530h; Size
0x180036e47  call    memset_0
0x180036e4c  lea     rdx, aStartLoopingTh; "Start looping through each partition an"...
0x180036e53  xor     ecx, ecx
0x180036e55  call    UnattendLogW
0x180036e5a  mov     rdi, [rdi]
0x180036e5d  cmp     rdi, [rsp+8B0h+var_870]
0x180036e62  jz      loc_180037060
0x180036e68  mov     rsi, [rbp+7B0h+var_828]
0x180036e6c  mov     r12d, [rbp+7B0h+UserData]
0x180036e73  mov     rbx, [rsp+8B0h+var_870]
0x180036e78  mov     r9d, [rdi+514h]
0x180036e7f  lea     rdx, aCheckingPartit; " Checking partition at offset %I64u, pa"...
0x180036e86  mov     r8, [rdi+4F0h]
0x180036e8d  xor     ecx, ecx
0x180036e8f  call    UnattendLogW
0x180036e94  mov     rcx, [rsp+8B0h+var_868]
0x180036e99  mov     rdx, rdi
0x180036e9c  call    winreIsSameDisk
0x180036ea1  test    eax, eax
0x180036ea3  jnz     short loc_180036EB1
0x180036ea5  lea     rdx, aSkipPartitionB_2; " skip partition because it is not on th"...
0x180036eac  jmp     loc_18003703F
0x180036eb1  add     [rsp+8B0h+var_860], r13d
0x180036eb6  test    r14, r14
0x180036eb9  jz      short loc_180036ED3
0x180036ebb  mov     rcx, r14
0x180036ebe  call    winreIsSamePartition
0x180036ec3  test    eax, eax
0x180036ec5  jz      short loc_180036ED3
0x180036ec7  lea     rdx, aSkipPartitionB; " skip partition because it is downlevel"...
0x180036ece  jmp     loc_18003703F
0x180036ed3  cmp     dword ptr [rdi+524h], 0
0x180036eda  jz      short loc_180036EED
0x180036edc  mov     [rsp+8B0h+var_848], rdi
0x180036ee1  lea     rdx, aFindOsPartitio; " find OS partition"
0x180036ee8  jmp     loc_18003703F
0x180036eed  mov     eax, [rdi+51Ch]
0x180036ef3  test    eax, eax
0x180036ef5  jz      short loc_180036F27
0x180036ef7  cmp     dword ptr [rdi+520h], 0
0x180036efe  jz      short loc_180036F11
0x180036f00  mov     [rsp+8B0h+var_850], rdi
0x180036f05  lea     rdx, aNoteFindSystem; " NOTE: find system partition and not OS"...
0x180036f0c  jmp     loc_18003703F
0x180036f11  test    eax, eax
0x180036f13  jz      short loc_180036F27
0x180036f15  cmp     byte ptr [rdi+10h], 27h ; '''
0x180036f19  jz      short loc_180036F49
0x180036f1b  lea     rdx, aSkipMbrPartiti; " skip MBR Partition which type is not M"...
0x180036f22  jmp     loc_18003703F
0x180036f27  mov     rax, [rdi+10h]
0x180036f2b  cmp     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data1
0x180036f32  jnz     loc_180037038
0x180036f38  mov     rax, [rdi+18h]
0x180036f3c  cmp     rax, qword ptr cs:PARTITION_MSFT_RECOVERY_GUID.Data4
0x180036f43  jnz     loc_180037038
0x180036f49  lea     rcx, [rdi+290h]; unsigned __int16 *
0x180036f50  lea     rdx, aWinreBackupPar; "$WINRE_BACKUP_PARTITION.MARKER"
0x180036f57  call    winreDoesFileExist
0x180036f5c  test    eax, eax
0x180036f5e  jz      short loc_180036F86
0x180036f60  lea     rdx, aPartitionConta; " partition contains winre backup partit"...
0x180036f67  xor     ecx, ecx
0x180036f69  call    UnattendLogW
0x180036f6e  cmp     dword ptr [rdi+524h], 0
0x180036f75  jnz     short loc_180036F86
0x180036f77  mov     r15, rdi
0x180036f7a  lea     rdx, aNoteFindExisti; " NOTE: find existing WinRE partition an"...
0x180036f81  jmp     loc_18003703F
0x180036f86  mov     rax, [rsp+8B0h+var_840]
0x180036f8b  test    rax, rax
0x180036f8e  jz      short loc_180036FAC
0x180036f90  mov     rax, [rax+4F0h]
0x180036f97  cmp     [rdi+4F0h], rax
0x180036f9e  jbe     short loc_180036FAC
0x180036fa0  lea     rdx, aSkipPartitionB_3; " skip partition beyond current candidat"...
0x180036fa7  jmp     loc_18003703F
0x180036fac  mov     r9d, [rsp+8B0h+var_880]; int
0x180036fb1  lea     rax, [rsp+8B0h+var_878]
0x180036fb6  mov     r8, [rbp+7B0h+arg_20]; unsigned __int64
0x180036fbd  mov     rcx, rdi; struct PartitionNode *
0x180036fc0  mov     rdx, [rsp+8B0h+var_868]; struct PartitionNode *
0x180036fc5  mov     [rsp+8B0h+var_888], rax; int *
0x180036fca  lea     rax, [rsp+8B0h+var_87C]
0x180036fcf  mov     [rsp+8B0h+var_890], rax; int *
0x180036fd4  call    ?MeetPartitionRequirements@@YAHPEAUPartitionNode@@0_KHPEAH2@Z; MeetPartitionRequirements(PartitionNode *,PartitionNode *,unsigned __int64,int,int *,int *)
0x180036fd9  test    eax, eax
0x180036fdb  jz      short loc_18003702F
0x180036fdd  lea     rdx, aPartitionMeets; " partition meets requirements"
0x180036fe4  xor     ecx, ecx
0x180036fe6  call    UnattendLogW
0x180036feb  test    r12d, r12d
0x180036fee  jnz     short loc_18003700C
0x180036ff0  lea     rdx, [rsi+9C0h]
0x180036ff7  mov     rcx, rdi
0x180036ffa  call    winreIsSamePartition2
0x180036fff  test    eax, eax
0x180037001  jz      short loc_18003700C
0x180037003  lea     rdx, aSkipPartitionB_1; " skip partition because it is the os in"...
0x18003700a  jmp     short loc_18003703F
0x18003700c  mov     rcx, rdi
0x18003700f  call    IsPartitionInUse
0x180037014  test    eax, eax
0x180037016  jz      short loc_180037021
0x180037018  lea     rdx, aSkipPartitionB_0; " skip partition because it is in use"
0x18003701f  jmp     short loc_18003703F
0x180037021  mov     [rsp+8B0h+var_840], rdi
0x180037026  lea     rdx, aNoteSelectPart; " NOTE: select partition because it meet"...
0x18003702d  jmp     short loc_18003703F
0x18003702f  lea     rdx, aSkipPartitionB_4; " skip partition because it does not mee"...
0x180037036  jmp     short loc_18003703F
0x180037038  lea     rdx, aSkipGptPartiti; " skip GPT Partition which type is not P"...
0x18003703f  xor     ecx, ecx
0x180037041  call    UnattendLogW
0x180037046  mov     rdi, [rdi]
0x180037049  cmp     rdi, rbx
0x18003704c  jnz     loc_180036E78
0x180037052  mov     ebx, dword ptr [rsp+8B0h+var_858]
0x180037056  mov     r12d, 6
0x18003705c  mov     rsi, qword ptr [rbp+7B0h+var_820.Data1]
0x180037060  lea     rdx, aCompleteLoopin; "Complete looping through each partition"
0x180037067  xor     ecx, ecx
0x180037069  call    UnattendLogW
0x18003706e  lea     rdx, aSearchTargetPa_1; "----Search target partition option #1: "...
0x180037075  xor     ecx, ecx
0x180037077  call    UnattendLogW
0x18003707c  test    r15, r15
0x18003707f  jz      loc_18003741A
0x180037085  xor     eax, eax
0x180037087  lea     rcx, [rbp+7B0h+var_2AE]; void *
0x18003708e  xor     edx, edx; Val
0x180037090  mov     [rbp+7B0h+FileName], ax
0x180037097  mov     r8d, 25Ah; Size
0x18003709d  call    memset_0
0x1800370a2  lea     r11, [r15+290h]
0x1800370a9  mov     [rsp+8B0h+var_870], 0
0x1800370b2  test    r11, r11
0x1800370b5  jz      loc_180037401
0x1800370bb  lea     r8, [rsp+8B0h+var_870]; unsigned __int64 *
0x1800370c0  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800370c5  mov     rcx, r11; unsigned __int16 *
0x1800370c8  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800370cd  mov     ebx, eax
0x1800370cf  test    eax, eax
0x1800370d1  jns     short loc_1800370F7
0x1800370d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800370da  lea     rax, WPP_GLOBAL_Control
0x1800370e1  cmp     rcx, rax
0x1800370e4  jz      loc_18003716F
0x1800370ea  test    byte ptr [rcx+1Ch], 2
0x1800370ee  jz      short loc_18003716F
0x1800370f0  mov     edx, 0Eh
0x1800370f5  jmp     short loc_18003715C
0x1800370f7  mov     rax, [rsp+8B0h+var_870]
0x1800370fc  test    rax, rax
0x1800370ff  jz      short loc_180037111
0x180037101  cmp     word ptr [r11+rax*2-2], 5Ch ; '\'
0x180037108  lea     r8, aSS_1; "%s\\%s"
0x18003710f  jnz     short loc_180037118
0x180037111  lea     r8, aSS_2; "%s%s"
0x180037118  lea     rax, aWinreBackupPar; "$WINRE_BACKUP_PARTITION.MARKER"
0x18003711f  mov     r9, r11
0x180037122  mov     edx, 12Eh; unsigned __int64
0x180037127  mov     [rsp+8B0h+var_890], rax
0x18003712c  lea     rcx, [rbp+7B0h+FileName]; unsigned __int16 *
0x180037133  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037138  mov     ebx, eax
0x18003713a  test    eax, eax
0x18003713c  jns     short loc_18003717B
0x18003713e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037145  lea     rax, WPP_GLOBAL_Control
0x18003714c  cmp     rcx, rax
  ... truncated ...
```
