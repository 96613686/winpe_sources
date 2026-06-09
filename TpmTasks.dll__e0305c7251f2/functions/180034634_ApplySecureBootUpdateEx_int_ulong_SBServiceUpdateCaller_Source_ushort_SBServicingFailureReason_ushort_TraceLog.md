# ApplySecureBootUpdateEx(int,ulong *,SBServiceUpdateCaller::Source,ushort *,SBServicingFailureReason *,ushort *,TraceLoggingCorrelationVector *)

- ea: `0x180034634`
- end: `0x180035867`
- name: `?ApplySecureBootUpdateEx@@YAJHPEAKW4Source@SBServiceUpdateCaller@@PEAGPEAW4SBServicingFailureReason@@2PEAVTraceLoggingCorrelationVector@@@Z`
- size: `4659`
- prototype: `__int64 __fastcall(int, unsigned int *, unsigned int, unsigned __int16 *, enum SBServicingFailureReason *, unsigned __int16 *, struct TraceLoggingCorrelationVector *)`
- caller_count: `2`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e5d0`
- `0x1800340c0`

## callees

- `0x1800078b0`
- `0x18001bddc`
- `0x180034418`
- `0x180034634`
- `0x180035870`
- `0x180035e98`
- `0x180036a98`
- `0x180037050`
- `0x180037244`
- `0x180037338`
- `0x18003772c`
- `0x180037a04`
- `0x180037fac`
- `0x18003820c`
- `0x180038660`
- `0x180038784`
- `0x180038c00`
- `0x1800391c8`
- `0x1800393bc`
- `0x180039d00`
- `0x180039d70`
- `0x180039de0`
- `0x180039e50`
- `0x18003a538`
- `0x18003c0b8`
- `0x18003d8e0`
- `0x18003e6ac`
- `0x18003ec28`
- `0x18003ee78`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800356e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800356e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034804`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180034804`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003570a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035835`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003570a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035835`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800356fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035827`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800356fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035827`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034816`

## string_xrefs

- `0x1800347e9`: `ShouldSecurebootSkipAnyUpdateFailed`
- `0x1800347a6`: `IsRebootRequiredBeforeUpdate`
- `0x180034f28`: `DBXUpdate.bin`
- `0x18003526e`: `DBXUpdateSVN.bin`
- `0x180034f21`: `DBXUpdateLegacy.bin`
- `0x180035267`: `DBXUpdateSVNLegacy.bin`
- `0x1800347f7`: `fveapi.dll`
- `0x1800346a3`: `Entering ApplySecureBootUpdateEx for update %d Caller %d`
- `0x180034794`: `IsRebootRequiredBeforeUpdateFailed`
- `0x180034917`: `ApplySecureBootUpdateFveActionWithVolumeNameBefore`
- `0x18003483a`: `Applying secure boot update %d without Bitlocker reseal`
- `0x18003485e`: `ShouldSecurebootSkipAnyUpdateDB`
- `0x18003492e`: `\SecureBootUpdates\DBUpdate.bin`
- `0x180034943`: `GetSecureBootUpdateFilePathDb`
- `0x1800349fc`: `DBAlreadyContainsPCA2023`
- `0x180034a18`: `ShouldSecurebootSkipAnyUpdateDb2024`
- `0x180034a35`: `\SecureBootUpdates\DBUpdate2024.bin`
- `0x180034a4a`: `GetSecureBootUpdateFilePathDb2024`
- `0x180034b35`: `DBAlreadyContains3POROM2023`
- `0x180034b4d`: `ShouldSecurebootSkipAnyUpdate3POROM`
- `0x180034ba8`: `\SecureBootUpdates\DBUpdateOROM2023.bin`
- `0x180034bbd`: `GetSecureBootUpdateFilePath3POROM`
- `0x180034cae`: `DBAlreadyContains3PUEFI2023`
- `0x180034cc6`: `ShouldSecurebootSkipAnyUpdate3PUEFI`
- `0x180034d2b`: `\SecureBootUpdates\DBUpdate3P2023.bin`
- `0x180034d40`: `GetSecureBootUpdateFilePath3PUEFI`
- `0x180034fd4`: `KEKAlreadyContainsKEK2023`
- `0x180034fc6`: `ShouldSecurebootSkipAnyUpdateKEK`
- `0x180034e41`: `\SecureBootUpdates\KEKUpdateCombined.bin`
- `0x180034fba`: `GetSecureBootUpdateFilePathKEKUpdate`
- `0x180034f67`: `IsKEKUpdatePresent`
- `0x180034f57`: `ApplySecureBootUpdateDBXNotApplicable`
- `0x180034fe9`: `ShouldSecurebootSkipAnyUpdateDBX`
- `0x18003501a`: `GetUpdateFilePathWithHotpatchFallbackDbx`
- `0x180035663`: `SetUpdateTriggerRegistryHotPatch`
- `0x18003514f`: `GetUpdateFilePathWithHotpatchFallbackSkuSiPolicy`
- `0x18003516a`: `CopySkuSiPolicyToEFI`
- `0x1800351b6`: `BootMgrAlreadySignedWithPCA2023`
- `0x180035297`: `GetUpdateFilePathWithHotpatchFallbackSVN`
- `0x1800353d1`: `ResetAvailableUpdatesVariableMask`
- `0x18003540a`: `\SecureBootUpdates\DBXUpdate2024Legacy.bin`
- `0x180035411`: `\SecureBootUpdates\DBXUpdate2024.bin`
- `0x180035438`: `ApplySecureBootUpdateDBX2024NotApplicable`
- `0x18003545a`: `GetSecureBootUpdateFilePathPCA2011RevokeDBX`
- `0x1800355a8`: `ShouldSBATSkipUpdateFailed`
- `0x1800355b7`: `Supplemental SBAT details: OptOut:%d FoundLinuxSHIM:%d OptIn:%d UpdateStatus:%u SBATLevel:%s numBytesSBATLevel:%d`
- `0x1800355e8`: `SkipSBATUpdate`
- `0x180035620`: `GetUpdateFilePathWithHotpatchFallbackSBAT`
- `0x1800356aa`: `Failed to reseal BitLocker after applying Secure Boot updatehrBL: %x hr: %x actionString:%ls`
- `0x1800356bd`: `ApplySecureBootUpdateFveActionWithVolumeNameAfter`
- `0x1800356c6`: `Successfully Resealed to BitLocker after applying Secure Boot update`
- `0x18003579e`: `Exiting ApplySecureBootUpdateEx with Status:%x InVariableMask:%d OutVariableMask:%d sbUpdateCaller:%d Action:%ls Reason:%d isResealNeeded:%d SkipReason:%ls willResealSucceed:%d, KEKPairedContentVersion:%u SBATOptOut:%d, SBATFoundLinuxSHIM:%d SBATOptIn:%d SBATUpdateStatus:%x SBATLevel:%ls FailedFunction:%ls FailedAction:%ls`

## pseudocode

```c
__int64 __fastcall ApplySecureBootUpdateEx(
        int a1,
        unsigned int *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        enum SBServicingFailureReason *a5,
        unsigned __int16 *a6,
        struct TraceLoggingCorrelationVector *a7)
{
  unsigned int v7; // r14d
  unsigned int v9; // r12d
  unsigned __int16 *v10; // r15
  int refreshed; // edi
  const unsigned __int16 *v12; // rsi
  int v13; // r12d
  signed int LastError; // eax
  __int64 v15; // r8
  int v16; // r12d
  int v17; // r11d
  int v18; // r15d
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // r8
  unsigned int v22; // ebx
  int v23; // r15d
  __int64 v24; // r8
  const WCHAR *v25; // rbx
  __int64 v26; // r8
  unsigned __int16 *v27; // r15
  int v28; // eax
  __int64 v29; // r8
  unsigned int v30; // ebx
  int v31; // eax
  unsigned int v32; // ecx
  __int64 v33; // r8
  bool v34; // zf
  const WCHAR *v35; // rcx
  int v36; // eax
  const WCHAR *v37; // rbx
  __int64 v38; // r8
  unsigned int v39; // ebx
  char *v40; // r15
  __int64 v41; // r8
  int v42; // eax
  int updated; // eax
  int v44; // ebx
  void *v45; // rbx
  HANDLE ProcessHeap; // rax
  unsigned int v47; // ebx
  unsigned int *v48; // rbx
  char *v49; // rbx
  HANDLE v50; // rax
  enum _SBAT_UPDATE_STATUS *v52; // [rsp+20h] [rbp-F0h]
  enum _SBAT_UPDATE_STATUS *v53; // [rsp+20h] [rbp-F0h]
  enum SBServicingFailureReason *v54; // [rsp+30h] [rbp-E0h]
  enum SBServicingFailureReason *v55; // [rsp+30h] [rbp-E0h]
  unsigned int *v56; // [rsp+38h] [rbp-D8h]
  __int64 v57; // [rsp+48h] [rbp-C8h]
  __int64 v58; // [rsp+50h] [rbp-C0h]
  __int64 v59; // [rsp+58h] [rbp-B8h]
  __int64 v60; // [rsp+60h] [rbp-B0h]
  char *v61; // [rsp+68h] [rbp-A8h]
  unsigned __int16 *v62; // [rsp+70h] [rbp-A0h]
  int v63; // [rsp+90h] [rbp-80h]
  int v64; // [rsp+94h] [rbp-7Ch] BYREF
  _BYTE SourceSize[12]; // [rsp+98h] [rbp-78h] BYREF
  int v66; // [rsp+A8h] [rbp-68h] BYREF
  unsigned int v67; // [rsp+ACh] [rbp-64h]
  int v68; // [rsp+B0h] [rbp-60h] BYREF
  int v69; // [rsp+B4h] [rbp-5Ch] BYREF
  int v70; // [rsp+B8h] [rbp-58h] BYREF
  __int128 v71; // [rsp+C0h] [rbp-50h] BYREF
  int v72; // [rsp+D0h] [rbp-40h] BYREF
  unsigned int v73; // [rsp+D4h] [rbp-3Ch] BYREF
  int v74; // [rsp+D8h] [rbp-38h] BYREF
  int v75; // [rsp+DCh] [rbp-34h] BYREF
  int v76; // [rsp+E0h] [rbp-30h] BYREF
  unsigned int v77; // [rsp+E4h] [rbp-2Ch] BYREF
  char *Source; // [rsp+E8h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+F0h] [rbp-20h] BYREF
  unsigned int v80; // [rsp+F8h] [rbp-18h] BYREF
  unsigned __int16 *v81; // [rsp+100h] [rbp-10h]
  unsigned __int16 *v82; // [rsp+108h] [rbp-8h] BYREF
  unsigned int *v83; // [rsp+110h] [rbp+0h]
  unsigned __int16 *v84; // [rsp+118h] [rbp+8h]
  struct TraceLoggingCorrelationVector *v85; // [rsp+120h] [rbp+10h]
  WCHAR ExistingFileName[264]; // [rsp+130h] [rbp+20h] BYREF

  v7 = *a2;
  v9 = a3;
  v84 = a6;
  v85 = a7;
  v83 = a2;
  v10 = 0;
  v63 = 1;
  v68 = 1;
  v69 = 1;
  v70 = 0;
  v66 = 0;
  v72 = 0;
  *(_DWORD *)SourceSize = 0;
  v82 = 0;
  v64 = 0;
  lpMem = 0;
  v76 = 0;
  v75 = 0;
  v74 = 0;
  v73 = 0;
  Source = 0;
  v77 = 0;
  v80 = 0;
  *(_DWORD *)a5 = 0;
  v81 = a4;
  v67 = a3;
  *(_DWORD *)&SourceSize[8] = 2;
  *(_DWORD *)&SourceSize[4] = v7;
  SBServicingLogMessage((wchar_t *)L"Entering ApplySecureBootUpdateEx for update %d Caller %d", v7);
  if ( (v7 & 0x19FE7) == 0 )
  {
    refreshed = -2147024809;
    v12 = L"ParameterCheck";
    goto LABEL_241;
  }
  v12 = L"Passed";
  if ( (v7 & 0x8000) != 0 )
  {
    refreshed = RefreshDriverRevocationPolicies();
    if ( refreshed >= 0 )
      v7 &= ~0x8000u;
    else
      v12 = L"RefreshDriverRevocationPolicies";
    goto LABEL_241;
  }
  refreshed = IsSecureBootEnabled((enum SBServicingState::State *)&SourceSize[8]);
  if ( refreshed < 0 )
  {
    v12 = L"IsSecureBootEnabledFailed";
    goto LABEL_241;
  }
  if ( *(_DWORD *)&SourceSize[8] == 2 )
  {
    v12 = L"SecureBootNotSupported";
    refreshed = 0;
    goto LABEL_241;
  }
  if ( *(_DWORD *)&SourceSize[8] == 1 )
  {
    v12 = L"SecureBootNotEnabled";
    refreshed = -2147020471;
    goto LABEL_241;
  }
  refreshed = IsRebootRequiredBeforeUpdate(v7, &v64);
  if ( refreshed < 0 )
  {
    v12 = L"IsRebootRequiredBeforeUpdateFailed";
    goto LABEL_241;
  }
  if ( v64 )
  {
    v12 = L"IsRebootRequiredBeforeUpdate";
    *(_DWORD *)a5 = 3;
    refreshed = -2147024546;
    goto LABEL_241;
  }
  v13 = 0;
  v64 = 0;
  refreshed = ShouldSecurebootSkipAnyUpdate(
                v7,
                (unsigned int *)SourceSize,
                (const unsigned __int16 **)&v82,
                (unsigned __int16 **)&SourceSize[8],
                &v80);
  if ( refreshed < 0 )
  {
    v12 = L"ShouldSecurebootSkipAnyUpdateFailed";
LABEL_231:
    v17 = v63;
    goto LABEL_232;
  }
  fveapiDll = LoadLibraryExW(L"fveapi.dll", 0, 0x800u);
  if ( !fveapiDll )
  {
    LastError = GetLastError();
    refreshed = LastError;
    if ( LastError > 0 )
      refreshed = (unsigned __int16)LastError | 0x80070000;
    if ( refreshed != -2147024770 )
    {
      v12 = L"LibraryLoad";
      goto LABEL_231;
    }
    v63 = 0;
    goto LABEL_24;
  }
  refreshed = InitFve();
  if ( refreshed < 0 )
  {
    v12 = L"InitFve";
    goto LABEL_231;
  }
  refreshed = IsBitLockerResealNeededAllVolumes(&v68, (unsigned __int16 **)&lpMem);
  if ( refreshed < 0 )
  {
    v17 = v68;
    v12 = L"IsBitLockerResealNeededAllVolumes";
    v63 = v68;
    goto LABEL_232;
  }
  v63 = v68;
  if ( !v68 )
  {
LABEL_24:
    SBServicingLogMessage((wchar_t *)L"Applying secure boot update %d without Bitlocker reseal", v7);
    goto LABEL_25;
  }
  refreshed = WillBitLockerResealSucceed(&v72);
  if ( refreshed < 0 )
  {
    v12 = L"WillBitLockerResealSucceed";
    goto LABEL_231;
  }
  if ( !v72 )
  {
    refreshed = -2144272152;
    v12 = L"WillBitLockerResealSucceedFalse";
    goto LABEL_231;
  }
  refreshed = ApplySecureBootUpdateFveActionWithVolumeName((unsigned __int16 *)lpMem);
  if ( refreshed < 0 )
  {
    v12 = L"ApplySecureBootUpdateFveActionWithVolumeNameBefore";
    goto LABEL_231;
  }
LABEL_25:
  v16 = *(_DWORD *)SourceSize;
  if ( (v7 & 1) != 0 )
  {
    if ( (SourceSize[0] & 1) != 0 )
    {
      v12 = L"ShouldSecurebootSkipAnyUpdateDB";
      *(_DWORD *)a5 = 7;
      refreshed = -2147467259;
      v13 = 0;
      goto LABEL_231;
    }
    v18 = v67;
    refreshed = GetSecureBootUpdateFilePath(L"\\SecureBootUpdates\\DBUpdate.bin", ExistingFileName, v15, v67);
    if ( refreshed < 0 )
    {
      v12 = L"GetSecureBootUpdateFilePathDb";
      v13 = 0;
      goto LABEL_231;
    }
    refreshed = InsertSecureBootEntry(ExistingFileName, L"db", 1u, 0, 0, &v66, a5, 0, 0);
    if ( refreshed < 0 )
    {
      if ( v66 )
      {
        *(_DWORD *)a5 = 8;
        v13 = 1;
      }
      else
      {
        v13 = v64;
      }
      v12 = L"InsertSecureBootEntryDb";
      goto LABEL_231;
    }
    v7 &= ~1u;
    v64 = 1;
    *(_DWORD *)&SourceSize[4] = v7;
    SetRestartRequiredForVSMRegistryBFSVCAI();
  }
  else
  {
    v18 = v67;
  }
  if ( (v7 & 0x40) != 0 )
  {
    *(_DWORD *)&SourceSize[8] = 0;
    v71 = *(_OWORD *)byte_18005F400;
    IsCertificateInDB(&SourceSize[8], &v71);
    if ( *(_DWORD *)&SourceSize[8] )
    {
      v12 = L"DBAlreadyContainsPCA2023";
      v7 &= ~0x40u;
LABEL_52:
      refreshed = 0;
LABEL_53:
      v13 = v64;
      goto LABEL_231;
    }
    if ( (v16 & 0x40) != 0 )
    {
      v12 = L"ShouldSecurebootSkipAnyUpdateDb2024";
LABEL_56:
      refreshed = -2147467259;
      *(_DWORD *)a5 = 7;
      goto LABEL_53;
    }
    refreshed = GetSecureBootUpdateFilePath(L"\\SecureBootUpdates\\DBUpdate2024.bin", ExistingFileName, v19, v18);
    if ( refreshed < 0 )
    {
      v12 = L"GetSecureBootUpdateFilePathDb2024";
      goto LABEL_53;
    }
    refreshed = InsertSecureBootEntry(ExistingFileName, L"db", 0x40u, 0, 0, &v66, a5, 0, 0);
    if ( refreshed < 0 )
    {
      if ( v66 )
      {
        *(_DWORD *)a5 = 8;
        v13 = 1;
      }
      else
      {
        v13 = v64;
      }
      v12 = L"InsertSecureBootEntryDb2024";
      goto LABEL_231;
    }
    v64 = 1;
    SetRestartRequiredForVSMRegistryBFSVCAI();
    SetRestartRequiredBeforeDBXRegistry();
    *(_DWORD *)&SourceSize[8] = 0;
    v71 = *(_OWORD *)byte_18005F400;
    refreshed = IsCertificateInDB(&SourceSize[8], &v71);
    if ( refreshed < 0 )
    {
      v12 = L"IsCertificateInDB2024";
      goto LABEL_53;
    }
    if ( *(_DWORD *)&SourceSize[8] )
    {
      v7 &= ~0x40u;
      *(_DWORD *)&SourceSize[4] = v7;
    }
  }
  if ( (v7 & 0x800) != 0 )
  {
    *(_DWORD *)&SourceSize[8] = 0;
    v71 = *(_OWORD *)byte_18005F410;
    IsCertificateInDB(&SourceSize[8], &v71);
    if ( *(_DWORD *)&SourceSize[8] )
    {
      v12 = L"DBAlreadyContains3POROM2023";
      v7 &= ~0x800u;
      goto LABEL_52;
    }
    if ( (v16 & 0x800) != 0 )
    {
      v12 = L"ShouldSecurebootSkipAnyUpdate3POROM";
      goto LABEL_56;
    }
    *(_DWORD *)SourceSize = 1;
    if ( a1 )
    {
      v71 = *(_OWORD *)byte_18005F3F0;
      refreshed = IsCertificateInDB(SourceSize, &v71);
      if ( refreshed < 0 )
      {
        v12 = L"Is3PUEFICA2011FoundInDbFailed3PROM";
        goto LABEL_53;
      }
      if ( !*(_DWORD *)SourceSize )
      {
        v12 = L"Skipped3POROM_3PPCA2011_NotFound";
LABEL_88:
        v7 &= ~0x800u;
        *(_DWORD *)&SourceSize[4] = v7;
        goto LABEL_89;
      }
    }
    refreshed = GetSecureBootUpdateFilePath(L"\\SecureBootUpdates\\DBUpdateOROM2023.bin", ExistingFileName, v20, v18);
    if ( refreshed < 0 )
    {
      v12 = L"GetSecureBootUpdateFilePath3POROM";
      goto LABEL_53;
    }
    refreshed = InsertSecureBootEntry(ExistingFileName, L"db", 0x800u, 0, 0, &v66, a5, 0, 0);
    if ( refreshed < 0 )
    {
      if ( v66 )
      {
        *(_DWORD *)a5 = 8;
        v13 = 1;
      }
      else
      {
        v13 = v64;
      }
      v12 = L"InsertSecureBootEntry3POROM";
      goto LABEL_231;
    }
    v64 = 1;
    SetRestartRequiredForVSMRegistryBFSVCAI();
    SetRestartRequiredBeforeDBXRegistry();
    *(_DWORD *)&SourceSize[8] = 0;
    v71 = *(_OWORD *)byte_18005F410;
    refreshed = IsCertificateInDB(&SourceSize[8], &v71);
    if ( refreshed < 0 )
    {
      v12 = L"Is3POROM2023InDBFailed";
      goto LABEL_53;
    }
    if ( *(_DWORD *)&SourceSize[8] )
      goto LABEL_88;
  }
LABEL_89:
  if ( (v7 & 0x1000) != 0 )
  {
    *(_DWORD *)&SourceSize[8] = 0;
    v71 = *(_OWORD *)byte_18005F3E0;
    IsCertificateInDB(&SourceSize[8], &v71);
    if ( *(_DWORD *)&SourceSize[8] )
    {
      v12 = L"DBAlreadyContains3PUEFI2023";
      v7 &= ~0x1000u;
      goto LABEL_52;
    }
    if ( (v16 & 0x1000) != 0 )
    {
      v12 = L"ShouldSecurebootSkipAnyUpdate3PUEFI";
      goto LABEL_56;
    }
    *(_DWORD *)SourceSize = 1;
    if ( !a1 )
      goto LABEL_100;
    v71 = *(_OWORD *)byte_18005F3F0;
    refreshed = IsCertificateInDB(SourceSize, &v71);
    if ( refreshed < 0 )
    {
      v12 = L"Is3PUEFICA2011FoundInDbFailed3PUEFI";
      goto LABEL_53;
    }
    refreshed = 0;
    if ( *(_DWORD *)SourceSize )
    {
LABEL_100:
      refreshed = GetSecureBootUpdateFilePath(L"\\SecureBootUpdates\\DBUpdate3P2023.bin", ExistingFileName, v21, v18);
      if ( refreshed < 0 )
      {
        v12 = L"GetSecureBootUpdateFilePath3PUEFI";
        goto LABEL_53;
      }
      refreshed = InsertSecureBootEntry(ExistingFileName, L"db", 0x1000u, 0, 0, &v66, a5, 0, 0);
      if ( refreshed < 0 )
      {
        if ( v66 )
        {
          *(_DWORD *)a5 = 8;
          v13 = 1;
        }
        else
        {
          v13 = v64;
        }
        v12 = L"InsertSecureBootEntry3PUEFI";
        goto LABEL_231;
      }
      v64 = 1;
      SetRestartRequiredForVSMRegistryBFSVCAI();
      SetRestartRequiredBeforeDBXRegistry();
      *(_DWORD *)&SourceSize[8] = 0;
      v71 = *(_OWORD *)byte_18005F3E0;
      refreshed = IsCertificateInDB(&SourceSize[8], &v71);
      if ( refreshed < 0 )
      {
        v12 = L"Is3PUEFICA2023InDBFailed";
        goto LABEL_53;
      }
      refreshed = 0;
      if ( !*(_DWORD *)&SourceSize[8] )
        goto LABEL_112;
    }
    else
    {
      v12 = L"Skipped3PUEFICA_3PPCA2011_NotFound";
    }
    v7 &= ~0x1000u;
    *(_DWORD *)&SourceSize[4] = v7;
  }
  else
  {
    refreshed = 0;
  }
LABEL_112:
  v22 = 4;
  v23 = 0;
  while ( 1 )
  {
    if ( v23 == 1 )
      v22 = 0x10000;
    if ( (v22 & v7) != 0 )
      break;
LABEL_123:
    if ( ++v23 > 2 )
    {
      if ( (v7 & 2) != 0 )
      {
        *(_DWORD *)SourceSize = 0;
        *(_DWORD *)&SourceSize[8] = 1;
        v68 = 0;
        IsKEKPresent((int *)SourceSize, (int *)&SourceSize[8]);
        v25 = L"DBXUpdate.bin";
        if ( !*(_DWORD *)SourceSize )
          v25 = L"DBXUpdateLegacy.bin";
        v71 = *(_OWORD *)byte_18005F3F0;
        IsCertificateInDB(&v68, &v71);
        if ( !v68 && !*(_DWORD *)&SourceSize[8] )
        {
          v12 = L"ApplySecureBootUpdateDBXNotApplicable";
          v7 &= ~2u;
          goto LABEL_53;
        }
        if ( (v16 & 2) != 0 )
        {
          v12 = L"ShouldSecurebootSkipAnyUpdateDBX";
          goto LABEL_56;
        }
        *(_DWORD *)SourceSize = 0;
        refreshed = GetUpdateFilePathWithHotpatchFallback(v25, ExistingFileName, v26, v67, SourceSize);
        if ( refreshed < 0 )
        {
          v12 = L"GetUpdateFilePathWithHotpatchFallbackDbx";
          goto LABEL_53;
        }
        v27 = v81;
        refreshed = InsertSecureBootEntry(ExistingFileName, L"dbx", 2u, &v70, v81, &v66, a5, 0, 0);
        if ( refreshed < 0 )
        {
          if ( v66 )
          {
            *(_DWORD *)a5 = 8;
            v13 = 1;
          }
          else
          {
            v13 = v64;
          }
          v12 = L"InsertSecureBootEntryDbx";
          goto LABEL_231;
        }
        refreshed = 0;
        v13 = 1;
        if ( v70 )
        {
          refreshed = -2147467259;
          *(_DWORD *)a5 = 1;
          v12 = L"BootMgrRevokedDBX";
          goto LABEL_231;
        }
        *(_DWORD *)&SourceSize[4] = v7 & 0xFFFFFFFD;
        SetRestartRequiredForVSMRegistryBFSVCAI();
        SetRestartRequiredBeforeKeyRollingRegistry();
        v28 = ResetAvailableUpdatesVariableMask((unsigned int *)&SourceSize[4], *(int *)SourceSize, 2u);
        v7 = *(_DWORD *)&SourceSize[4];
        if ( v28 < 0 )
          goto LABEL_230;
      }
      else
      {
        v13 = v64;
        v27 = v81;
      }
      if ( (v7 & 0x20) != 0 )
      {
        *(_DWORD *)SourceSize = 0;
        refreshed = IsNonDesktopSkuPolicyPublisherActive((int *)SourceSize);
        if ( refreshed < 0 )
        {
          v12 = L"IsNonDesktopSkuPolicyPublisherActive";
          goto LABEL_231;
        }
        if ( *(_DWORD *)SourceSize )
        {
          v12 = L"SKUPolicyNonDesktopPublisher";
          refreshed = 0;
          goto LABEL_231;
        }
        v30 = v67;
        *(_DWORD *)SourceSize = 0;
        refreshed = GetUpdateFilePathWithHotpatchFallback(L"SKUSiPolicy.p7b", ExistingFileName, v29, v67, SourceSize);
        if ( refreshed < 0 )
        {
          v12 = L"GetUpdateFilePathWithHotpatchFallbackSkuSiPolicy";
          goto LABEL_231;
        }
        refreshed = CopySkuSiPolicyToEFI(ExistingFileName);
        if ( refreshed < 0 )
        {
          v12 = L"CopySkuSiPolicyToEFI";
          goto LABEL_231;
        }
        v31 = ResetAvailableUpdatesVariableMask((unsigned int *)&SourceSize[4], *(int *)SourceSize, 0x20u);
        v7 = *(_DWORD *)&SourceSize[4];
        refreshed = 0;
        if ( v31 < 0 )
          goto LABEL_230;
      }
      else
      {
        v30 = v67;
      }
      if ( (v7 & 0x100) != 0 )
      {
        *(_DWORD *)SourceSize = 0;
        IsBootManagerSignedWithPCA2023((int *)SourceSize);
        if ( *(_DWORD *)SourceSize )
        {
          v12 = L"BootMgrAlreadySignedWithPCA2023";
          v7 &= ~0x100u;
          goto LABEL_231;
        }
        v64 = 0;
        v71 = *(_OWORD *)byte_18005F400;
        refreshed = IsCertificateInDB(&v64, &v71);
        if ( refreshed < 0 )
        {
          v12 = L"IsPCA2023InDBInvokeBFSVCAI";
          goto LABEL_231;
        }
        if ( !v64 )
        {
          v12 = L"PCA2023CertificateNotFoundInvokeBFSVCAI";
          *(_DWORD *)a5 = 4;
LABEL_172:
          refreshed = -2147467259;
          goto LABEL_231;
        }
        v68 = 0;
        refreshed = InvokeBFSVCAI(v32, &v68);
        if ( refreshed < 0 )
        {
          v12 = L"InvokeBFSVCAI";
          goto LABEL_231;
        }
        refreshed = 0;
        if ( v68 )
        {
          v7 &= ~0x100u;
          *(_DWORD *)&SourceSize[4] = v7;
          SetRestartRequiredForVSMRegistry();
        }
      }
      if ( (v7 & 0x200) != 0 )
      {
        *(_DWORD *)SourceSize = 0;
        IsKEKPresent((int *)SourceSize, 0);
        v34 = *(_DWORD *)SourceSize == 0;
        v35 = L"DBXUpdateSVN.bin";
        *(_DWORD *)SourceSize = 0;
        if ( v34 )
          v35 = L"DBXUpdateSVNLegacy.bin";
        refreshed = GetUpdateFilePathWithHotpatchFallback(v35, ExistingFileName, v33, v30, SourceSize);
        if ( refreshed < 0 )
        {
          v12 = L"GetUpdateFilePathWithHotpatchFallbackSVN";
          goto LABEL_231;
        }
        v64 = 0;
        v71 = *(_OWORD *)byte_18005F400;
        refreshed = IsCertificateInDB(&v64, &v71);
        if ( refreshed < 0 )
        {
          v12 = L"IsCertificateInDBDbxSVN";
          goto LABEL_231;
        }
        if ( !v64 )
        {
          v12 = L"PCA2023CertificateNotFoundDbxSVN";
          *(_DWORD *)a5 = 4;
          refreshed = -2147467259;
          goto LABEL_231;
        }
        refreshed = IsBootManagerSignedWithPCA2023(&v69);
        if ( refreshed < 0 )
        {
          v12 = L"VerifyBootmanagerCertificateDbxSVN";
          goto LABEL_231;
        }
        if ( !v69 )
        {
          v12 = L"BootManagerNotSignedWithPCA2023DbxSVN";
          *(_DWORD *)a5 = 5;
          refreshed = -2147467259;
          goto LABEL_231;
        }
        refreshed = InsertSecureBootEntry(ExistingFileName, L"dbx", 0x200u, &v70, v27, &v66, a5, 0, 0);
        if ( refreshed < 0 )
        {
          if ( v66 )
          {
            *(_DWORD *)a5 = 8;
            v13 = 1;
          }
          v12 = L"InsertSecureBootEntryDbxSVN";
          goto LABEL_231;
        }
        refreshed = 0;
        v13 = 1;
        if ( v70 )
        {
          refreshed = -2147467259;
          v12 = L"BootMgrRevokedDbxSVN";
          goto LABEL_231;
        }
        *(_DWORD *)&SourceSize[4] = v7 & 0xFFFFFDFF;
        SetRestartRequiredForVSMRegistryBFSVCAI();
        v36 = ResetAvailableUpdatesVariableMask((unsigned int *)&SourceSize[4], *(int *)SourceSize, 0x200u);
        v7 = *(_DWORD *)&SourceSize[4];
        if ( v36 < 0 )
        {
          v12 = L"ResetAvailableUpdatesVariableMask";
          goto LABEL_231;
        }
      }
      if ( (v7 & 0x80u) != 0 )
      {
        *(_QWORD *)SourceSize = 0x100000000LL;
        *(_DWORD *)&SourceSize[8] = 0;
        IsKEKPresent((int *)SourceSize, (int *)&SourceSize[4]);
        v37 = L"\\SecureBootUpdates\\DBXUpdate2024.bin";
        if ( !*(_DWORD *)SourceSize )
          v37 = L"\\SecureBootUpdates\\DBXUpdate2024Legacy.bin";
        v71 = *(_OWORD *)byte_18005F420;
        IsCertificateInDB(&SourceSize[8], &v71);
        if ( !*(_QWORD *)&SourceSize[4] )
        {
          v12 = L"ApplySecureBootUpdateDBX2024NotApplicable";
          goto LABEL_231;
        }
        refreshed = GetSecureBootUpdateFilePath(v37, ExistingFileName, v38, v67);
        if ( refreshed < 0 )
        {
          v12 = L"GetSecureBootUpdateFilePathPCA2011RevokeDBX";
          goto LABEL_231;
        }
        v64 = 0;
        v71 = *(_OWORD *)byte_18005F400;
        refreshed = IsCertificateInDB(&v64, &v71);
        if ( refreshed < 0 )
        {
          v12 = L"IsCertificateInDBPCA2011RevokeDBX";
          goto LABEL_231;
        }
        if ( !v64 )
        {
          v12 = L"PCA2023CertificateNotFound";
          goto LABEL_172;
        }
        refreshed = IsBootManagerSignedWithPCA2023(&v69);
        if ( refreshed < 0 )
        {
          v12 = L"VerifyBootmanagerCertificate";
          goto LABEL_231;
        }
        if ( !v69 )
        {
          v12 = L"BootManagerNotSignedWithPCA2023";
          goto LABEL_172;
        }
        refreshed = InsertSecureBootEntry(ExistingFileName, L"dbx", 0x80u, &v70, v27, &v66, a5, 0, 0);
        if ( refreshed < 0 )
        {
          if ( v66 )
          {
            *(_DWORD *)a5 = 8;
            v13 = 1;
          }
          v12 = L"InsertSecureBootEntryDbxPca2011";
          goto LABEL_231;
        }
        refreshed = 0;
        v13 = 1;
        if ( v70 )
        {
          refreshed = -2147467259;
          v12 = L"BootMgrRevokedDBX2024";
          goto LABEL_231;
        }
        v7 &= ~0x80u;
        *(_DWORD *)&SourceSize[4] = v7;
        SetRestartRequiredForVSMRegistryBFSVCAI();
      }
      if ( (v7 & 0x400) == 0 )
        goto LABEL_231;
      v69 = 0;
      *(_DWORD *)SourceSize = 0;
      refreshed = ShouldSBATSkipUpdate(
                    &v69,
                    &v76,
                    &v75,
                    &v74,
                    (enum _SBAT_UPDATE_STATUS *)&v73,
                    &Source,
                    (unsigned int *)SourceSize);
      if ( refreshed < 0 )
      {
        v12 = L"ShouldSBATSkipUpdateFailed";
        goto LABEL_231;
      }
      v39 = *(_DWORD *)SourceSize;
      v40 = Source;
      LODWORD(v54) = *(_DWORD *)SourceSize;
      LODWORD(v52) = v73;
      SBServicingLogMessage(
        (wchar_t *)L"Supplemental SBAT details: OptOut:%d FoundLinuxSHIM:%d OptIn:%d UpdateStatus:%u SBATLevel:%s numBytesSBATLevel:%d",
        (unsigned int)v76,
        (unsigned int)v75,
        (unsigned int)v74,
        v52,
        Source,
        v54);
      if ( v69 )
      {
        v12 = L"SkipSBATUpdate";
        v7 &= ~0x400u;
        goto LABEL_231;
      }
      *(_DWORD *)SourceSize = 0;
      refreshed = GetUpdateFilePathWithHotpatchFallback(L"SbatLevel.txt", ExistingFileName, v41, v67, SourceSize);
      if ( refreshed < 0 )
      {
        v12 = L"GetUpdateFilePathWithHotpatchFallbackSBAT";
        goto LABEL_231;
      }
      refreshed = DeliverSBATPayload(ExistingFileName, v40, v39);
      if ( refreshed < 0 )
      {
        v12 = L"DeliverSBATPayload";
        goto LABEL_231;
      }
      v42 = ResetAvailableUpdatesVariableMask((unsigned int *)&SourceSize[4], *(int *)SourceSize, 0x400u);
      v7 = *(_DWORD *)&SourceSize[4];
      refreshed = 0;
      if ( v42 >= 0 )
        goto LABEL_231;
LABEL_230:
      v12 = L"SetUpdateTriggerRegistryHotPatch";
      goto LABEL_231;
    }
  }
  *(_DWORD *)&SourceSize[8] = 0;
  IsKEKPresent((int *)&SourceSize[8], 0);
  if ( *(_DWORD *)&SourceSize[8] )
  {
    v12 = L"KEKAlreadyContainsKEK2023";
    v7 &= ~v22;
    goto LABEL_53;
  }
  if ( (v22 & v16) != 0 )
  {
    v12 = L"ShouldSecurebootSkipAnyUpdateKEK";
    goto LABEL_56;
  }
  refreshed = GetSecureBootUpdateFilePath(L"\\SecureBootUpdates\\KEKUpdateCombined.bin", ExistingFileName, v24, v67);
  if ( refreshed < 0 )
  {
    v12 = L"GetSecureBootUpdateFilePathKEKUpdate";
    goto LABEL_53;
  }
  *(_DWORD *)SourceSize = 1;
  refreshed = InsertSecureBootEntry(ExistingFileName, L"KEK", v22, 0, 0, &v66, a5, &v77, (int *)SourceSize);
  if ( refreshed >= 0 )
  {
    v64 = 1;
    SetRestartRequiredForVSMRegistryBFSVCAI();
    SetRestartRequiredBeforeDBXRegistry();
    *(_DWORD *)&SourceSize[8] = 0;
    refreshed = IsKEKPresent((int *)&SourceSize[8], 0);
    if ( refreshed < 0 )
    {
      v12 = L"IsKEKUpdatePresent";
      goto LABEL_53;
    }
    refreshed = 0;
    if ( *(_DWORD *)&SourceSize[8] )
    {
      v7 &= ~v22;
      *(_DWORD *)&SourceSize[4] = v7;
    }
    goto LABEL_123;
  }
  if ( !*(_DWORD *)SourceSize )
  {
    *(_DWORD *)a5 = 9;
    v12 = L"MissingKEKInPackage";
    goto LABEL_53;
  }
  v12 = L"InsertSecureBootEntryKEK";
  v17 = v63;
  if ( v66 )
  {
    *(_DWORD *)a5 = 8;
    v13 = 1;
  }
  else
  {
    v13 = v64;
  }
LABEL_232:
  v10 = v82;
  if ( v82 )
    StringCchCopyW(v84, 0x104u, v82);
  if ( v17 && v72 && v13 )
  {
    updated = ApplySecureBootUpdateFveActionWithVolumeName((unsigned __int16 *)lpMem);
    v44 = updated;
    if ( updated >= 0 )
    {
      SBServicingLogMessage((wchar_t *)L"Successfully Resealed to BitLocker after applying Secure Boot update");
    }
    else
    {
      SBServicingLogMessage(
        (wchar_t *)L"Failed to reseal BitLocker after applying Secure Boot updatehrBL: %x hr: %x actionString:%ls",
        (unsigned int)updated,
        (unsigned int)refreshed,
        v12);
      refreshed = v44;
      v12 = L"ApplySecureBootUpdateFveActionWithVolumeNameAfter";
    }
  }
  v9 = v67;
LABEL_241:
  if ( fveapiDll )
  {
    FreeLibrary(fveapiDll);
    fveapiDll = 0;
  }
  v45 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v45);
  }
  v47 = v77;
  SBServicingCoreTelemetryProvider::ApplySecureBootUpdateCompleted(
    refreshed,
    v7,
    v9,
    v63,
    v72,
    v12,
    *(_DWORD *)a5,
    *v83,
    v77,
    v76,
    v75,
    v74,
    v73,
    Source,
    v10,
    g_FailedFunction,
    g_FailedAction,
    v85);
  LODWORD(v62) = v73;
  LODWORD(v61) = v74;
  LODWORD(v60) = v75;
  LODWORD(v59) = v76;
  LODWORD(v58) = v47;
  v48 = v83;
  LODWORD(v57) = v72;
  LODWORD(v56) = v63;
  LODWORD(v55) = *(_DWORD *)a5;
  LODWORD(v53) = v9;
  SBServicingLogMessage(
    (wchar_t *)L"Exiting ApplySecureBootUpdateEx with Status:%x InVariableMask:%d OutVariableMask:%d sbUpdateCaller:%d Act"
                "ion:%ls Reason:%d isResealNeeded:%d SkipReason:%ls willResealSucceed:%d, KEKPairedContentVersion:%u SBAT"
                "OptOut:%d, SBATFoundLinuxSHIM:%d SBATOptIn:%d SBATUpdateStatus:%x SBATLevel:%ls FailedFunction:%ls FailedAction:%ls",
    (unsigned int)refreshed,
    *v83,
    v7,
    v53,
    v12,
    v55,
    v56,
    v10,
    v57,
    v58,
    v59,
    v60,
    v61,
    v62,
    Source,
    g_FailedFunction,
    g_FailedAction);
  *v48 = v7;
  v49 = Source;
  if ( Source )
  {
    v50 = GetProcessHeap();
    HeapFree(v50, 0, v49);
  }
  return (unsigned int)refreshed;
}

```

## disassembly

```asm
0x180034634  mov     [rsp-8+arg_0], rbx
0x180034639  push    rbp
0x18003463a  push    rsi
0x18003463b  push    rdi
0x18003463c  push    r12
0x18003463e  push    r13
0x180034640  push    r14
0x180034642  push    r15
0x180034644  lea     rbp, [rsp-240h]
0x18003464c  sub     rsp, 350h
0x180034653  mov     rax, cs:__security_cookie
0x18003465a  xor     rax, rsp
0x18003465d  mov     [rbp+270h+var_40], rax
0x180034664  mov     r14d, [rdx]
0x180034667  mov     ebx, ecx
0x180034669  mov     rax, [rbp+270h+arg_28]
0x180034670  mov     ecx, 1
0x180034675  mov     r13, [rbp+270h+arg_20]
0x18003467c  mov     r12d, r8d
0x18003467f  mov     [rbp+270h+var_268], rax
0x180034683  mov     rax, [rbp+270h+arg_30]
0x18003468a  mov     [rbp+270h+var_260], rax
0x18003468e  xor     eax, eax
0x180034690  mov     [rbp+270h+var_270], rdx
0x180034694  mov     r15d, eax
0x180034697  mov     [rbp+270h+var_2F0], ecx
0x18003469a  mov     edx, r14d
0x18003469d  mov     [rbp+270h+var_2D0], ecx
0x1800346a0  mov     [rbp+270h+var_2CC], ecx
0x1800346a3  lea     rcx, aEnteringApplys; "Entering ApplySecureBootUpdateEx for up"...
0x1800346aa  mov     [rbp+270h+var_2C8], eax
0x1800346ad  mov     [rbp+270h+var_2D8], eax
0x1800346b0  mov     [rbp+270h+var_2B0], eax
0x1800346b3  mov     dword ptr [rbp+270h+SourceSize], eax
0x1800346b6  mov     [rbp+270h+var_278], rax
0x1800346ba  mov     [rbp+270h+var_2EC], eax
0x1800346bd  mov     [rbp+270h+lpMem], rax
0x1800346c1  mov     [rbp+270h+var_2A0], eax
0x1800346c4  mov     [rbp+270h+var_2A4], eax
0x1800346c7  mov     [rbp+270h+var_2A8], eax
0x1800346ca  mov     [rbp+270h+var_2AC], eax
0x1800346cd  mov     [rbp+270h+Source], rax
0x1800346d1  mov     [rbp+270h+var_29C], eax
0x1800346d4  mov     [rbp+270h+var_288], eax
0x1800346d7  mov     [r13+0], eax
0x1800346db  mov     [rbp+270h+var_280], r9
0x1800346df  mov     [rbp+270h+var_2D4], r8d
0x1800346e3  mov     dword ptr [rbp+270h+var_2E0], 2
0x1800346ea  mov     dword ptr [rbp+270h+SourceSize+4], r14d
0x1800346ee  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x1800346f3  test    r14d, 19FE7h
0x1800346fa  jnz     short loc_18003470D
0x1800346fc  mov     edi, 80070057h
0x180034701  lea     rsi, aParametercheck; "ParameterCheck"
0x180034708  jmp     loc_1800356D6
0x18003470d  lea     rsi, aPassed; "Passed"
0x180034714  bt      r14d, 0Fh
0x180034719  jnb     short loc_18003473C
0x18003471b  call    ?RefreshDriverRevocationPolicies@@YAJXZ; RefreshDriverRevocationPolicies(void)
0x180034720  mov     edi, eax
0x180034722  test    eax, eax
0x180034724  jns     short loc_180034732
0x180034726  lea     rsi, aRefreshdriverr; "RefreshDriverRevocationPolicies"
0x18003472d  jmp     loc_1800356D6
0x180034732  btr     r14d, 0Fh
0x180034737  jmp     loc_1800356D6
0x18003473c  lea     rcx, [rbp+270h+var_2E0]; enum SBServicingState::State *
0x180034740  call    ?IsSecureBootEnabled@@YAJPEAW4State@SBServicingState@@@Z; IsSecureBootEnabled(SBServicingState::State *)
0x180034745  mov     edi, eax
0x180034747  test    eax, eax
0x180034749  jns     short loc_180034757
0x18003474b  lea     rsi, aIssecurebooten; "IsSecureBootEnabledFailed"
0x180034752  jmp     loc_1800356D6
0x180034757  cmp     dword ptr [rbp+270h+var_2E0], 2
0x18003475b  jnz     short loc_18003476B
0x18003475d  lea     rsi, aSecurebootnots; "SecureBootNotSupported"
0x180034764  xor     edi, edi
0x180034766  jmp     loc_1800356D6
0x18003476b  cmp     dword ptr [rbp+270h+var_2E0], 1
0x18003476f  jnz     short loc_180034782
0x180034771  lea     rsi, aSecurebootnote; "SecureBootNotEnabled"
0x180034778  mov     edi, 80071149h
0x18003477d  jmp     loc_1800356D6
0x180034782  lea     rdx, [rbp+270h+var_2EC]; int *
0x180034786  mov     ecx, r14d; unsigned int
0x180034789  call    ?IsRebootRequiredBeforeUpdate@@YAJKPEAH@Z; IsRebootRequiredBeforeUpdate(ulong,int *)
0x18003478e  mov     edi, eax
0x180034790  test    eax, eax
0x180034792  jns     short loc_1800347A0
0x180034794  lea     rsi, aIsrebootrequir; "IsRebootRequiredBeforeUpdateFailed"
0x18003479b  jmp     loc_1800356D6
0x1800347a0  cmp     [rbp+270h+var_2EC], r15d
0x1800347a4  jz      short loc_1800347BF
0x1800347a6  lea     rsi, aIsrebootrequir_0; "IsRebootRequiredBeforeUpdate"
0x1800347ad  mov     dword ptr [r13+0], 3
0x1800347b5  mov     edi, 8007015Eh
0x1800347ba  jmp     loc_1800356D6
0x1800347bf  lea     rax, [rbp+270h+var_288]
0x1800347c3  xor     r12d, r12d
0x1800347c6  lea     r9, [rbp+270h+var_2E0]; unsigned __int16 **
0x1800347ca  mov     [rbp+270h+var_2EC], r12d
0x1800347ce  lea     r8, [rbp+270h+var_278]; unsigned __int16 **
0x1800347d2  mov     [rsp+380h+var_360], rax; unsigned int *
0x1800347d7  lea     rdx, [rbp+270h+SourceSize]; unsigned int *
0x1800347db  mov     ecx, r14d; unsigned int
0x1800347de  call    ?ShouldSecurebootSkipAnyUpdate@@YAJKPEAKPEAPEBGPEAPEAG0@Z; ShouldSecurebootSkipAnyUpdate(ulong,ulong *,ushort const * *,ushort * *,ulong *)
0x1800347e3  mov     edi, eax
0x1800347e5  test    eax, eax
0x1800347e7  jns     short loc_1800347F5
0x1800347e9  lea     rsi, aShouldsecurebo_15; "ShouldSecurebootSkipAnyUpdateFailed"
0x1800347f0  jmp     loc_18003566A
0x1800347f5  xor     edx, edx; hFile
0x1800347f7  lea     rcx, aFveapiDll_0; "fveapi.dll"
0x1800347fe  mov     r8d, 800h; dwFlags
0x180034804  call    cs:__imp_LoadLibraryExW
0x18003480a  mov     cs:?fveapiDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * fveapiDll
0x180034811  test    rax, rax
0x180034814  jnz     short loc_180034886
0x180034816  call    cs:__imp_GetLastError
0x18003481c  mov     edi, eax
0x18003481e  test    eax, eax
0x180034820  jle     short loc_18003482B
0x180034822  movzx   edi, ax
0x180034825  or      edi, 80070000h
0x18003482b  cmp     edi, 8007007Eh
0x180034831  jnz     short loc_18003487A
0x180034833  mov     [rbp+270h+var_2F0], r12d
0x180034837  mov     edx, r14d
0x18003483a  lea     rcx, aApplyingSecure; "Applying secure boot update %d without "...
0x180034841  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x180034846  mov     r12d, dword ptr [rbp+270h+SourceSize]
0x18003484a  test    r14b, 1
0x18003484e  jz      loc_1800349C8
0x180034854  test    r12b, 1
0x180034858  jz      loc_180034923
0x18003485e  lea     rsi, aShouldsecurebo_16; "ShouldSecurebootSkipAnyUpdateDB"
0x180034865  mov     dword ptr [r13+0], 7
0x18003486d  mov     edi, 80004005h
0x180034872  mov     r12d, r15d
0x180034875  jmp     loc_18003566A
0x18003487a  lea     rsi, aLibraryload; "LibraryLoad"
0x180034881  jmp     loc_18003566A
0x180034886  call    ?InitFve@@YAJXZ; InitFve(void)
0x18003488b  mov     edi, eax
0x18003488d  test    eax, eax
0x18003488f  jns     short loc_18003489D
0x180034891  lea     rsi, aInitfve; "InitFve"
0x180034898  jmp     loc_18003566A
0x18003489d  lea     rdx, [rbp+270h+lpMem]; unsigned __int16 **
0x1800348a1  lea     rcx, [rbp+270h+var_2D0]; int *
0x1800348a5  call    ?IsBitLockerResealNeededAllVolumes@@YAJPEAHPEAPEAG@Z; IsBitLockerResealNeededAllVolumes(int *,ushort * *)
0x1800348aa  mov     edi, eax
0x1800348ac  test    eax, eax
0x1800348ae  jns     short loc_1800348C4
0x1800348b0  mov     r11d, [rbp+270h+var_2D0]
0x1800348b4  lea     rsi, aIsbitlockerres_0; "IsBitLockerResealNeededAllVolumes"
0x1800348bb  mov     [rbp+270h+var_2F0], r11d
0x1800348bf  jmp     loc_18003566E
0x1800348c4  mov     edi, [rbp+270h+var_2D0]
0x1800348c7  mov     [rbp+270h+var_2F0], edi
0x1800348ca  test    edi, edi
0x1800348cc  jz      loc_180034837
0x1800348d2  lea     rcx, [rbp+270h+var_2B0]; int *
0x1800348d6  call    ?WillBitLockerResealSucceed@@YAJPEAH@Z; WillBitLockerResealSucceed(int *)
0x1800348db  mov     edi, eax
0x1800348dd  test    eax, eax
0x1800348df  jns     short loc_1800348ED
0x1800348e1  lea     rsi, aWillbitlockerr_1; "WillBitLockerResealSucceed"
0x1800348e8  jmp     loc_18003566A
0x1800348ed  cmp     [rbp+270h+var_2B0], r12d
0x1800348f1  jnz     short loc_180034904
0x1800348f3  mov     edi, 803100E8h
0x1800348f8  lea     rsi, aWillbitlockerr; "WillBitLockerResealSucceedFalse"
0x1800348ff  jmp     loc_18003566A
0x180034904  mov     rcx, [rbp+270h+lpMem]; unsigned __int16 *
0x180034908  call    ?ApplySecureBootUpdateFveActionWithVolumeName@@YAJPEAG@Z; ApplySecureBootUpdateFveActionWithVolumeName(ushort *)
0x18003490d  mov     edi, eax
0x18003490f  test    eax, eax
0x180034911  jns     loc_180034846
0x180034917  lea     rsi, aApplysecureboo_5; "ApplySecureBootUpdateFveActionWithVolum"...
0x18003491e  jmp     loc_18003566A
0x180034923  mov     r15d, [rbp+270h+var_2D4]
0x180034927  lea     rdx, [rbp+270h+ExistingFileName]
0x18003492b  mov     r9d, r15d
0x18003492e  lea     rcx, aSecurebootupda_1; "\\SecureBootUpdates\\DBUpdate.bin"
0x180034935  call    ?GetSecureBootUpdateFilePath@@YAJPEBGPEAGKW4Source@SBServiceUpdateCaller@@@Z; GetSecureBootUpdateFilePath(ushort const *,ushort *,ulong,SBServiceUpdateCaller::Source)
0x18003493a  xor     r11d, r11d
0x18003493d  mov     edi, eax
0x18003493f  test    eax, eax
0x180034941  jns     short loc_180034952
0x180034943  lea     rsi, aGetsecurebootu_1; "GetSecureBootUpdateFilePathDb"
0x18003494a  mov     r12d, r11d
0x18003494d  jmp     loc_18003566A
0x180034952  mov     [rsp+380h+var_340], r11; int *
0x180034957  lea     rax, [rbp+270h+var_2D8]
0x18003495b  mov     [rsp+380h+var_348], r11; unsigned int *
0x180034960  lea     rdx, aDb; "db"
0x180034967  xor     r9d, r9d; int *
0x18003496a  mov     [rsp+380h+var_350], r13; enum SBServicingFailureReason *
0x18003496f  mov     [rsp+380h+var_358], rax; int *
0x180034974  lea     rcx, [rbp+270h+ExistingFileName]; unsigned __int16 *
0x180034978  mov     [rsp+380h+var_360], r11; unsigned __int16 *
0x18003497d  lea     r8d, [r9+1]; unsigned int
0x180034981  call    ?InsertSecureBootEntry@@YAJPEBG0KPEAHPEAG1PEAW4SBServicingFailureReason@@PEAI1@Z; InsertSecureBootEntry(ushort const *,ushort const *,ulong,int *,ushort *,int *,SBServicingFailureReason *,uint *,int *)
0x180034986  mov     edi, eax
0x180034988  test    eax, eax
0x18003498a  jns     short loc_1800349B2
0x18003498c  cmp     [rbp+270h+var_2D8], 0
0x180034990  jz      short loc_1800349A2
0x180034992  mov     dword ptr [r13+0], 8
0x18003499a  mov     r12d, 1
0x1800349a0  jmp     short loc_1800349A6
0x1800349a2  mov     r12d, [rbp+270h+var_2EC]
0x1800349a6  lea     rsi, aInsertsecurebo_9; "InsertSecureBootEntryDb"
0x1800349ad  jmp     loc_18003566A
0x1800349b2  and     r14d, 0FFFFFFFEh
0x1800349b6  mov     [rbp+270h+var_2EC], 1
0x1800349bd  mov     dword ptr [rbp+270h+SourceSize+4], r14d
0x1800349c1  call    ?SetRestartRequiredForVSMRegistryBFSVCAI@@YAXXZ; SetRestartRequiredForVSMRegistryBFSVCAI(void)
0x1800349c6  jmp     short loc_1800349CC
0x1800349c8  mov     r15d, [rbp+270h+var_2D4]
0x1800349cc  test    r14b, 40h
0x1800349d0  jz      loc_180034B04
0x1800349d6  movups  xmm0, xmmword ptr cs:byte_18005F400
0x1800349dd  lea     rdx, [rbp+270h+var_2C0]
0x1800349e1  mov     dword ptr [rbp+270h+var_2E0], 0
0x1800349e8  lea     rcx, [rbp+270h+var_2E0]
0x1800349ec  movdqu  [rbp+270h+var_2C0], xmm0
0x1800349f1  call    ?IsCertificateInDB@@YAJPEAHUSB_HASH@@@Z; IsCertificateInDB(int *,SB_HASH)
0x1800349f6  cmp     dword ptr [rbp+270h+var_2E0], 0
0x1800349fa  jz      short loc_180034A12
0x1800349fc  lea     rsi, aDbalreadyconta; "DBAlreadyContainsPCA2023"
0x180034a03  and     r14d, 0FFFFFFBFh
0x180034a07  xor     edi, edi
0x180034a09  mov     r12d, [rbp+270h+var_2EC]
0x180034a0d  jmp     loc_18003566A
0x180034a12  test    r12b, 40h
0x180034a16  jz      short loc_180034A2E
0x180034a18  lea     rsi, aShouldsecurebo_9; "ShouldSecurebootSkipAnyUpdateDb2024"
0x180034a1f  mov     edi, 80004005h
0x180034a24  mov     dword ptr [r13+0], 7
0x180034a2c  jmp     short loc_180034A09
0x180034a2e  mov     r9d, r15d
0x180034a31  lea     rdx, [rbp+270h+ExistingFileName]
0x180034a35  lea     rcx, aSecurebootupda_5; "\\SecureBootUpdates\\DBUpdate2024.bin"
0x180034a3c  call    ?GetSecureBootUpdateFilePath@@YAJPEBGPEAGKW4Source@SBServiceUpdateCaller@@@Z; GetSecureBootUpdateFilePath(ushort const *,ushort *,ulong,SBServiceUpdateCaller::Source)
0x180034a41  xor     r11d, r11d
0x180034a44  mov     edi, eax
0x180034a46  test    eax, eax
0x180034a48  jns     short loc_180034A53
0x180034a4a  lea     rsi, aGetsecurebootu_2; "GetSecureBootUpdateFilePathDb2024"
0x180034a51  jmp     short loc_180034A09
0x180034a53  mov     [rsp+380h+var_340], r11; int *
0x180034a58  lea     rax, [rbp+270h+var_2D8]
0x180034a5c  mov     [rsp+380h+var_348], r11; unsigned int *
0x180034a61  lea     rdx, aDb; "db"
0x180034a68  xor     r9d, r9d; int *
0x180034a6b  mov     [rsp+380h+var_350], r13; enum SBServicingFailureReason *
0x180034a70  mov     [rsp+380h+var_358], rax; int *
0x180034a75  lea     rcx, [rbp+270h+ExistingFileName]; unsigned __int16 *
0x180034a79  mov     [rsp+380h+var_360], r11; unsigned __int16 *
0x180034a7e  lea     r8d, [r9+40h]; unsigned int
0x180034a82  call    ?InsertSecureBootEntry@@YAJPEBG0KPEAHPEAG1PEAW4SBServicingFailureReason@@PEAI1@Z; InsertSecureBootEntry(ushort const *,ushort const *,ulong,int *,ushort *,int *,SBServicingFailureReason *,uint *,int *)
0x180034a87  mov     edi, eax
0x180034a89  test    eax, eax
0x180034a8b  jns     short loc_180034AB3
0x180034a8d  cmp     [rbp+270h+var_2D8], 0
0x180034a91  jz      short loc_180034AA3
0x180034a93  mov     dword ptr [r13+0], 8
0x180034a9b  mov     r12d, 1
0x180034aa1  jmp     short loc_180034AA7
0x180034aa3  mov     r12d, [rbp+270h+var_2EC]
0x180034aa7  lea     rsi, aInsertsecurebo_8; "InsertSecureBootEntryDb2024"
0x180034aae  jmp     loc_18003566A
0x180034ab3  mov     [rbp+270h+var_2EC], 1
0x180034aba  call    ?SetRestartRequiredForVSMRegistryBFSVCAI@@YAXXZ; SetRestartRequiredForVSMRegistryBFSVCAI(void)
0x180034abf  call    ?SetRestartRequiredBeforeDBXRegistry@@YAXXZ; SetRestartRequiredBeforeDBXRegistry(void)
0x180034ac4  movups  xmm0, xmmword ptr cs:byte_18005F400
0x180034acb  lea     rdx, [rbp+270h+var_2C0]
0x180034acf  mov     dword ptr [rbp+270h+var_2E0], 0
0x180034ad6  lea     rcx, [rbp+270h+var_2E0]
0x180034ada  movdqu  [rbp+270h+var_2C0], xmm0
0x180034adf  call    ?IsCertificateInDB@@YAJPEAHUSB_HASH@@@Z; IsCertificateInDB(int *,SB_HASH)
0x180034ae4  mov     edi, eax
0x180034ae6  test    eax, eax
0x180034ae8  jns     short loc_180034AF6
0x180034aea  lea     rsi, aIscertificatei; "IsCertificateInDB2024"
0x180034af1  jmp     loc_180034A09
0x180034af6  cmp     dword ptr [rbp+270h+var_2E0], 0
0x180034afa  jz      short loc_180034B04
0x180034afc  and     r14d, 0FFFFFFBFh
0x180034b00  mov     dword ptr [rbp+270h+SourceSize+4], r14d
0x180034b04  bt      r14d, 0Bh
0x180034b09  jnb     loc_180034C7D
0x180034b0f  movups  xmm0, xmmword ptr cs:byte_18005F410
0x180034b16  lea     rdx, [rbp+270h+var_2C0]
0x180034b1a  mov     dword ptr [rbp+270h+var_2E0], 0
0x180034b21  lea     rcx, [rbp+270h+var_2E0]
0x180034b25  movdqu  [rbp+270h+var_2C0], xmm0
0x180034b2a  call    ?IsCertificateInDB@@YAJPEAHUSB_HASH@@@Z; IsCertificateInDB(int *,SB_HASH)
  ... truncated ...
```
