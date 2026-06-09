# BfeFilterConvertM2S

- ea: `0x180013f60`
- end: `0x1800150aa`
- name: `BfeFilterConvertM2S`
- size: `4426`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180006ed0`

## callees

- `0x1800017a4`
- `0x180006400`
- `0x18000d6e0`
- `0x18000e7e0`
- `0x18000ee04`
- `0x18000fb34`
- `0x180010480`
- `0x180011510`
- `0x1800115f0`
- `0x180012d8c`
- `0x1800135ac`
- `0x180013f60`
- `0x1800197d0`
- `0x1800235a0`
- `0x18002409c`
- `0x180024880`
- `0x180024e40`
- `0x180025fe4`
- `0x18002867c`
- `0x180032e80`
- `0x18003a180`
- `0x18004c424`
- `0x18004c878`
- `0x18004d670`
- `0x18004fb50`
- `0x180055f04`
- `0x1800560f8`
- `0x1800592f4`
- `0x18005aa60`
- `0x180068c74`
- `0x1800692a8`
- `0x18008ad54`
- `0x18008ad60`

## import_xrefs

- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180014b3b`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180014b3b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800140d6`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800140d6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014010`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180014010`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800149eb`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180014f6f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180014ffa`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800149eb`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180014f6f`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180014ffa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014795`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001493b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014795`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001493b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008b9f5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008b9f5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014989`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014979`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014989`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180014e03`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x180014e03`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014e2a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014e2a`

## string_xrefs

- `0x180014eb5`: `RtlGetOwnerSecurityDescriptor`

## pseudocode

```c
LPCWCH __fastcall BfeFilterConvertM2S(_QWORD *a1, __int64 *a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  __int64 v7; // rdi
  __int64 v9; // r14
  unsigned int v10; // esi
  __int64 v11; // r15
  unsigned int v12; // eax
  _QWORD *v13; // rax
  __int64 v14; // rcx
  _WORD *v15; // r13
  const WCHAR *v16; // rax
  __int64 v17; // rax
  __int64 i; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rdx
  unsigned __int16 v21; // r12
  __int64 v22; // rax
  __int64 v23; // rbx
  unsigned __int16 v24; // r13
  __int64 v25; // r15
  __int64 v26; // r14
  unsigned __int16 v27; // dx
  __int64 v28; // rbx
  _QWORD *v29; // r8
  _QWORD *v30; // r9
  __int64 v31; // rax
  __int64 v32; // rdi
  int v33; // r8d
  _QWORD *v34; // r15
  __int64 v35; // r12
  __int64 v36; // rax
  __int64 *v37; // rdi
  int v38; // r8d
  LPCWCH v39; // r13
  __int64 v40; // r15
  __int64 v41; // rcx
  __int64 v42; // rax
  __int64 ConditionsForTrie; // rax
  BOOL v44; // r15d
  int v45; // eax
  unsigned int v46; // ebx
  __int64 j; // r12
  _QWORD *v48; // r13
  __int64 v49; // rax
  __int64 v50; // rcx
  void *v51; // rdi
  unsigned __int16 v52; // dx
  __int64 v53; // r15
  __int64 v54; // rbx
  __int64 v55; // rax
  int v56; // edx
  BOOL v57; // eax
  int v58; // r9d
  int v59; // r8d
  __int64 v60; // rax
  const WCHAR *v61; // rax
  int v62; // r8d
  int v63; // r8d
  __int64 v64; // r8
  const WCHAR *v65; // rax
  __int64 v66; // rdx
  int v67; // ecx
  __int64 v68; // r8
  unsigned int k; // ebx
  LPCVOID *v70; // rdi
  bool v72; // zf
  __int64 v73; // rax
  void *v74; // rdi
  NTSTATUS OwnerSecurityDescriptor; // eax
  __int64 v76; // rcx
  __int64 v77; // rcx
  LPVOID v78; // rax
  int v79; // edx
  int v80; // r8d
  const wchar_t *v81; // rbx
  __int64 PfnCondition; // rbx
  __int64 PublicStateFromPrivate; // rax
  __int64 v84; // rax
  void *v85; // rcx
  __int64 v86; // rax
  const WCHAR *v87; // rax
  const WCHAR *v88; // rdi
  __int64 PfnFromSDDLString; // rax
  int v90; // edx
  int v91; // r8d
  LPVOID v92; // rbx
  __int64 v93; // rcx
  int v94; // [rsp+28h] [rbp-D8h]
  LPCWCH lpString2; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v96; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v97; // [rsp+60h] [rbp-A0h]
  unsigned int v98; // [rsp+68h] [rbp-98h] BYREF
  __int64 v99; // [rsp+70h] [rbp-90h]
  LPVOID lpMem; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v101; // [rsp+80h] [rbp-80h] BYREF
  BOOL v102; // [rsp+84h] [rbp-7Ch]
  _QWORD *v103; // [rsp+88h] [rbp-78h]
  __int64 v104; // [rsp+90h] [rbp-70h]
  _QWORD *v105; // [rsp+98h] [rbp-68h]
  int v106; // [rsp+A0h] [rbp-60h] BYREF
  __int64 *v107; // [rsp+A8h] [rbp-58h]
  _WORD *v108; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v109; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v110; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v111; // [rsp+C8h] [rbp-38h]
  __int64 v112; // [rsp+D0h] [rbp-30h]
  __int64 v113; // [rsp+D8h] [rbp-28h]
  _QWORD *v114; // [rsp+E0h] [rbp-20h]
  HLOCAL hMem; // [rsp+E8h] [rbp-18h] BYREF
  PSID Owner; // [rsp+F0h] [rbp-10h] BYREF
  HLOCAL v117; // [rsp+F8h] [rbp-8h] BYREF
  int v118; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 OwnerDefaulted[4]; // [rsp+104h] [rbp+4h] BYREF
  __int128 v120; // [rsp+108h] [rbp+8h] BYREF
  __int128 v121; // [rsp+118h] [rbp+18h]
  unsigned int *v122; // [rsp+128h] [rbp+28h] BYREF
  __int64 v123; // [rsp+130h] [rbp+30h]

  v7 = a5;
  v114 = a6;
  v113 = a4;
  v9 = 0;
  *a6 = 0;
  v10 = 0;
  v11 = *(_QWORD *)(a5 + 120);
  v12 = *(_DWORD *)(a5 + 112);
  v104 = v11;
  v112 = a3;
  v105 = a1;
  v111 = a5;
  v108 = 0;
  v106 = 0;
  v118 = 0;
  hMem = 0;
  v117 = 0;
  v109 = 0;
  v98 = 0;
  v99 = 0;
  v110 = 0;
  v101 = 0;
  v97 = v12;
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    v16 = (const WCHAR *)WfpMemAlloc25B(0x40u);
    v15 = v108;
    v103 = v108;
    lpString2 = v16;
  }
  else
  {
    v13 = HeapAlloc(gWfpHeap, 8u, 0x40u);
    v103 = v13;
    v15 = v13;
    v108 = v13;
    if ( v13 )
    {
      lpString2 = 0;
      if ( gWfpTrackHeapBytes )
        _InterlockedAdd(&gWfpHeapBytesAllocated, HeapSize(gWfpHeap, 0, v13));
    }
    else
    {
      v87 = (const WCHAR *)WfpReportSysErrorAsNtStatus(v14, "HeapAlloc", 3221225495LL);
      lpString2 = v87;
      if ( v87 )
        WfpReportError(v87, "WfpMemAlloc");
    }
    v16 = lpString2;
  }
  if ( v16 )
    goto LABEL_239;
  *(_QWORD *)v15 = *(_QWORD *)(a5 + 176);
  lpString2 = (LPCWCH)BfeFwpConditionValueCopyInner(a5 + 96, v15 + 4);
  if ( lpString2 )
    goto LABEL_239;
  v17 = *a2;
  v102 = 0;
  v15[12] = *(_WORD *)(v17 + 64);
  if ( (*(_BYTE *)(a5 + 32) & 8) != 0 )
    v15[13] |= 1u;
  if ( (*(_BYTE *)(a5 + 32) & 0x10) != 0 )
    v15[13] |= 2u;
  if ( *(char *)(a5 + 32) < 0 )
    v15[13] |= 8u;
  if ( (*(_DWORD *)(a5 + 32) & 0x400) != 0 )
    v15[13] |= 0x10u;
  if ( (*(_DWORD *)(a5 + 32) & 0x800) != 0 )
    v15[13] |= 0x20u;
  if ( (*(_DWORD *)(a5 + 32) & 0x1000) != 0 )
    v15[13] |= 0x40u;
  if ( (*(_DWORD *)(a5 + 32) & 0x2000) != 0 )
    v15[13] |= 0x80u;
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
  {
    i = 0;
    v102 = (*(_BYTE *)(*a1 + 32LL) & 1) != 0;
  }
  v19 = a1[2];
  if ( !v19 )
  {
    v21 = 4;
    goto LABEL_30;
  }
  v20 = *(_QWORD **)(v19 + 8);
  v21 = 0;
  i = 4;
  while ( 1 )
  {
    if ( !v20 )
      goto LABEL_30;
    v22 = v20[1];
    if ( *(_DWORD *)v22 == 2 )
      break;
LABEL_28:
    v20 = (_QWORD *)*v20;
  }
  if ( v21 < 4u )
  {
    v41 = v21++;
    *(_WORD *)&OwnerDefaulted[2 * v41 - 4] = **(_WORD **)(v22 + 8);
    i = 4;
    goto LABEL_28;
  }
  lpString2 = (LPCWCH)WfpReportSysErrorAsNtStatus(4, "BfeIndicesHasTrie", 3221225507LL);
  if ( lpString2 )
    goto LABEL_239;
LABEL_30:
  LODWORD(v23) = v97;
  if ( !v97 && !v102 )
    goto LABEL_141;
  v24 = 0;
  v25 = 0;
  if ( !v97 )
    goto LABEL_53;
  v26 = v104;
  do
  {
    v27 = 0;
    v28 = (unsigned int)v25;
    while ( v27 < *(_WORD *)(*v105 + 36LL) )
    {
      v29 = (_QWORD *)(v26 + 40 * v25);
      v28 = (unsigned int)v25;
      i = 2LL * v27;
      v30 = *(_QWORD **)(*(_QWORD *)(*v105 + 40LL) + 16LL * v27);
      v31 = *v30 - *v29;
      if ( *v30 == *v29 )
        v31 = v30[1] - v29[1];
      if ( !v31 )
      {
        v24 = v27;
        goto LABEL_40;
      }
      ++v27;
    }
    v32 = WfpReportSysErrorAsWinError(i, "BfeLayerLookupConditionInfo", 2150760450LL);
    if ( v32 )
    {
      i = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v33, 0, (__int64)"BfeLayerLookupConditionInfo", v32);
      }
      if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
      {
        v96 = v32;
        v122 = &v96;
        *(_QWORD *)&v121 = "BfeLayerLookupConditionInfo";
        *((_QWORD *)&v121 + 1) = 28;
        v123 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
          v33,
          3,
          (__int64)&v120);
      }
      goto LABEL_51;
    }
LABEL_40:
    if ( *(_DWORD *)(v26 + 40 * v28 + 16) == 5 )
    {
      for ( i = 0; (int)i < v21; i = (unsigned int)(i + 1) )
      {
        if ( v24 == *(_WORD *)&OwnerDefaulted[2 * (int)i - 4] )
        {
          ++v10;
          break;
        }
      }
    }
LABEL_51:
    v23 = v97;
    v25 = (unsigned int)(v25 + 1);
  }
  while ( (unsigned int)v25 < v97 );
  v72 = v10 == 0;
  v10 = v98;
  v9 = v98;
  if ( v72 )
  {
LABEL_53:
    v34 = v105;
    v35 = v104;
    goto LABEL_54;
  }
  Feature_IndexTrie__private_ReportDeviceUsage();
  v42 = WfpMemAllocArray(v23, 8, 8, &v109);
  v9 = v109;
  v39 = (LPCWCH)v42;
  if ( v42 )
  {
LABEL_62:
    v40 = v99;
LABEL_63:
    BfeDestroy_FWPS_FILTER3(&v108);
    goto LABEL_151;
  }
  v34 = v105;
  v96 = v23;
  ConditionsForTrie = BfeGenerateConditionsForTrie(
                        (unsigned int)&v118,
                        v21,
                        (_DWORD)v105,
                        v111,
                        v109,
                        v94,
                        (__int64)&v96,
                        (__int64)&v110,
                        (__int64)&v101);
  v10 = v96;
  v39 = (LPCWCH)ConditionsForTrie;
  if ( ConditionsForTrie )
  {
    v40 = v110;
    goto LABEL_63;
  }
  LODWORD(v23) = v101;
  v35 = v110;
  v99 = v110;
  v104 = v110;
  v97 = v101;
LABEL_54:
  v36 = (unsigned int)(v23 + 1);
  v15 = v103;
  if ( !v102 )
    v36 = (unsigned int)v23;
  v37 = v103 + 4;
  v107 = v103 + 4;
  lpString2 = (LPCWCH)WfpMemAlloc(24 * v36, 8u);
  if ( lpString2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v39 = lpString2;
    }
    else
    {
      v39 = lpString2;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v38, 0, (__int64)"WfpMemAllocArray", (char)lpString2);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v98 = (unsigned int)v39;
      v122 = &v98;
      *(_QWORD *)&v121 = "WfpMemAllocArray";
      *((_QWORD *)&v121 + 1) = 17;
      v123 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v38,
        3,
        (__int64)&v120);
    }
    goto LABEL_62;
  }
  if ( g_isEnabled_Feature_Firewall_042024 )
  {
    v44 = 0;
    v96 = 0;
    v45 = 0;
    v118 = 0;
    v46 = 0;
    if ( v97 )
    {
      while ( 1 )
      {
        if ( !v45 )
        {
          if ( !memcmp_0((const void *)(v35 + 40LL * v46), &FWPM_CONDITION_ALE_PACKAGE_FAMILY_NAME, 0x10u) )
          {
            v84 = *(_QWORD *)(v35 + 40LL * v46 + 32);
            if ( v84 )
            {
              v85 = *(void **)(v84 + 8);
              if ( v85 )
              {
                if ( ConvertSecurityDescriptorToStringSecurityDescriptorW(v85, 1u, 7u, (LPWSTR *)&v117, 0) )
                {
                  v45 = 1;
                  v118 = 1;
                  goto LABEL_85;
                }
                goto LABEL_84;
              }
            }
          }
          v45 = v118;
        }
        if ( !v44 )
        {
          if ( !memcmp_0((const void *)(v35 + 40LL * v46), &FWPM_CONDITION_ALE_PACKAGE_ID, 0x10u)
            && ConvertSidToStringSidW(*(PSID *)(v35 + 40LL * v46 + 32), (LPWSTR *)&hMem) )
          {
            v44 = wcscmp_0((const wchar_t *)hMem, L"S-1-0-0") != 0;
          }
LABEL_84:
          v45 = v118;
        }
LABEL_85:
        if ( ++v46 >= v97 )
        {
          v37 = v107;
          v15 = v103;
          v96 = v44;
          break;
        }
      }
    }
    LODWORD(j) = 0;
    while ( 1 )
    {
      while ( 1 )
      {
LABEL_88:
        LODWORD(v23) = v97;
        if ( (unsigned int)j >= v97 )
          goto LABEL_139;
        v48 = (_QWORD *)(v104 + 40LL * (unsigned int)j);
        if ( !memcmp_0(v48, &FWPM_CONDITION_ALE_PACKAGE_ID, 0x10u) && v96 && !v118 )
          break;
        if ( memcmp_0(v48, &FWPM_CONDITION_ALE_PACKAGE_ID, 0x10u) )
          goto LABEL_91;
        if ( !v96 )
          goto LABEL_91;
        if ( !v118 )
          goto LABEL_91;
        lpString2 = 0;
        if ( (int)PackageSidStringToPackageFamilyName((PCWSTR)hMem, &lpString2) < 0 )
          goto LABEL_91;
        v88 = lpString2;
        if ( !lpString2 )
        {
          v37 = v107;
          goto LABEL_91;
        }
        lpMem = 0;
        PfnFromSDDLString = BfeGetPfnFromSDDLString(v117, &lpMem);
        v92 = lpMem;
        if ( PfnFromSDDLString || CompareStringOrdinal((LPCWCH)lpMem, -1, v88, -1, 1) != 2 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_ISSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v90, v91, *v103, (__int64)hMem, (__int64)v92, (__int64)v88);
          }
          MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( v92 )
            WfpMemFree(&lpMem);
          WfpMemFree(&lpString2);
          v39 = (LPCWCH)WfpReportSysErrorAsHResult(v93, "\"BfeFilterConvertM2S\"", 2150760501LL, 1);
          goto LABEL_150;
        }
        v15 = v103;
        *((_WORD *)v103 + 13) |= 0x100u;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_ISS(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v91, *(_QWORD *)v15, (__int64)hMem, (__int64)v92);
        }
        WfpMemFree(&lpMem);
        WfpMemFree(&lpString2);
        v37 = v107;
        LODWORD(j) = j + 1;
      }
      lpMem = 0;
      if ( (int)PackageSidStringToPackageFamilyName((PCWSTR)hMem, &lpMem) < 0 )
        break;
      v81 = (const wchar_t *)lpMem;
      if ( !lpMem )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_ISS(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v80, *v103, (__int64)hMem, (__int64)lpMem);
      }
      v120 = 0;
      v122 = 0;
      v121 = 0;
      PfnCondition = BfeCreatePfnCondition(v81);
      WfpMemFree(&lpMem);
      if ( PfnCondition )
        break;
      v39 = (LPCWCH)BfeFilterConditionConvertM2S(v105, &v120, 0, *v37 + 24LL * (unsigned int)j);
      if ( v122 )
      {
        if ( *((_QWORD *)v122 + 1) )
          WfpMemFree(v122 + 2);
        WfpMemFree(&v122);
      }
      if ( v39 )
        goto LABEL_62;
      v15 = v103;
      *((_WORD *)v103 + 13) |= 0x100u;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_082cac24a57a3351f8a132228278c8a6_Traceguids,
          *(_QWORD *)v15);
      }
      LODWORD(j) = j + 1;
      *((_DWORD *)v15 + 7) = j;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_IS(*((_QWORD *)WPP_GLOBAL_Control + 2), v79, v80, *v103, (__int64)hMem);
    }
LABEL_91:
    v49 = *v37;
    v50 = 3LL * (unsigned int)j;
    v51 = 0;
    lpMem = 0;
    v52 = 0;
    v53 = v49 + 24LL * (unsigned int)j;
    while ( v52 < *(_WORD *)(*v105 + 36LL) )
    {
      v54 = *(_QWORD *)(*v105 + 40LL) + 16LL * v52;
      v50 = *(_QWORD *)v54;
      v55 = **(_QWORD **)v54 - *v48;
      if ( !v55 )
        v55 = *(_QWORD *)(v50 + 8) - v48[1];
      if ( !v55 )
      {
        if ( v53 )
          *(_WORD *)v53 = v52;
LABEL_99:
        v56 = *((_DWORD *)v48 + 4);
        v57 = 1;
        if ( v56 != 8 )
        {
          v50 = (unsigned int)(v56 - 6);
          if ( v56 != 6 && v56 != 7 )
            v57 = 0;
        }
        v58 = *(_DWORD *)(v54 + 8);
        if ( v58 == 2 )
        {
          if ( v56 && !v57 )
          {
            v64 = 2150760486LL;
            goto LABEL_134;
          }
LABEL_103:
          v59 = *(_DWORD *)(v54 + 12);
          v50 = *((unsigned int *)v48 + 6);
          if ( (_DWORD)v50 == 257 )
          {
            if ( v59 == 11 && v58 == 1 )
              goto LABEL_110;
          }
          else if ( (int)v50 > 15 )
          {
            if ( (_DWORD)v50 != 16 )
            {
              if ( (_DWORD)v50 == 256 )
              {
                if ( v59 != 3 )
                  goto LABEL_133;
                v72 = v58 == 1;
              }
              else
              {
                if ( (_DWORD)v50 != 258 )
                  goto LABEL_109;
                v72 = *(_DWORD *)v48[4] == v59;
              }
              if ( v72 )
                goto LABEL_110;
            }
          }
          else if ( (_DWORD)v50 != 15 )
          {
            switch ( (_DWORD)v50 )
            {
              case 0:
                goto LABEL_110;
              case 0xD:
                if ( v59 == 13 )
                  goto LABEL_110;
                break;
              case 0xE:
                if ( v59 == 13 || (unsigned int)(v59 - 15) <= 1 )
                  goto LABEL_110;
                break;
              default:
LABEL_109:
                if ( (_DWORD)v50 == v59 )
                  goto LABEL_110;
                break;
            }
          }
LABEL_133:
          v64 = 2150760487LL;
          goto LABEL_134;
        }
        if ( !v57 )
          goto LABEL_103;
        v64 = 2150760486LL;
LABEL_134:
        v65 = (const WCHAR *)WfpReportSysErrorAsWinError(v50, "BfeFwpmFilterConditionAssocValidate", v64);
        lpString2 = v65;
        if ( v65 )
        {
          v39 = v65;
          WfpReportError(v65, "BfeFwpmFilterConditionAssocValidate");
          goto LABEL_121;
        }
LABEL_110:
        *(_WORD *)(v53 + 2) = 0;
        *(_DWORD *)(v53 + 4) = *((_DWORD *)v48 + 4);
        if ( *((_DWORD *)v48 + 6) != 14 )
        {
LABEL_111:
          v60 = BfeFwpConditionValueCopyInner(v48 + 3, v53 + 8);
          goto LABEL_112;
        }
        v73 = v48[4];
        Owner = 0;
        OwnerDefaulted[0] = 0;
        v74 = *(void **)(v73 + 8);
        OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(v74, &Owner, OwnerDefaulted);
        if ( OwnerSecurityDescriptor < 0 )
        {
          v60 = WfpReportSysErrorAsNtStatus(v76, "RtlGetOwnerSecurityDescriptor", (unsigned int)OwnerSecurityDescriptor);
LABEL_112:
          v39 = (LPCWCH)v60;
          if ( v60 )
          {
LABEL_113:
            v51 = lpMem;
            goto LABEL_121;
          }
LABEL_131:
          v15 = v103;
          LODWORD(j) = j + 1;
          v37 = v107;
          *((_DWORD *)v103 + 7) = j;
          goto LABEL_88;
        }
        if ( Owner || !v74 )
          goto LABEL_111;
        v101 = 0;
        v39 = (LPCWCH)CloneSecurityDescriptorWithOwner(v74);
        if ( v39 )
          goto LABEL_113;
        v39 = (LPCWCH)WfpMemAlloc(0x10u, 0);
        if ( v39 )
          goto LABEL_113;
        v77 = *(_QWORD *)(v53 + 16);
        LODWORD(j) = j + 1;
        v78 = lpMem;
        v15 = v103;
        v37 = v107;
        *(_DWORD *)(v53 + 8) = 14;
        *(_QWORD *)(v77 + 8) = v78;
        **(_DWORD **)(v53 + 16) = v101;
        *((_DWORD *)v15 + 7) = j;
        goto LABEL_88;
      }
      ++v52;
    }
    v54 = 0;
    v61 = (const WCHAR *)WfpReportSysErrorAsWinError(v50, "BfeLayerLookupConditionInfo", 2150760450LL);
    lpString2 = v61;
    if ( !v61 )
      goto LABEL_99;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v62, 0, (__int64)"BfeLayerLookupConditionInfo", (char)v61);
      LODWORD(v61) = (_DWORD)lpString2;
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v98 = (unsigned int)v61;
      *(_QWORD *)&v121 = "BfeLayerLookupConditionInfo";
      v122 = &v98;
      *((_QWORD *)&v121 + 1) = 28;
      v123 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v62,
        3,
        (__int64)&v120);
    }
    v39 = lpString2;
LABEL_121:
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
    {
      WfpMemFree25B(&lpMem);
    }
    else
    {
      if ( gWfpTrackHeapBytes && v51 )
        _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, v51));
      HeapFree(gWfpHeap, 0, v51);
    }
    if ( !v39 )
      goto LABEL_131;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v63, 0, (__int64)"BfeFilterConditionConvertM2S", (char)v39);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v98 = (unsigned int)v39;
      v122 = &v98;
      *(_QWORD *)&v121 = "BfeFilterConditionConvertM2S";
      *((_QWORD *)&v121 + 1) = 29;
      v123 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v63,
        3,
        (__int64)&v120);
      v40 = v99;
      BfeDestroy_FWPS_FILTER3(&v108);
      goto LABEL_151;
    }
    goto LABEL_62;
  }
  for ( j = 0; (unsigned int)j < (unsigned int)v23; *((_DWORD *)v15 + 7) = j )
  {
    lpString2 = (LPCWCH)BfeFilterConditionConvertM2S(v34, v104 + 40 * j, 0, *v37 + 24 * j);
    if ( lpString2 )
      goto LABEL_239;
    j = (unsigned int)(j + 1);
  }
LABEL_139:
  if ( v102 )
  {
    v121 = 0u;
    v122 = 0;
    v86 = *v37;
    v120 = FWPM_CONDITION_COMPARTMENT_ID;
    lpString2 = (LPCWCH)BfeFilterConditionConvertM2S(v105, &v120, 0, v86 + 24LL * (unsigned int)j);
    if ( !lpString2 )
    {
      *((_DWORD *)v15 + 7) = j + 1;
      goto LABEL_140;
    }
LABEL_239:
    v39 = lpString2;
    goto LABEL_62;
  }
LABEL_140:
  v11 = v104;
  v7 = v111;
LABEL_141:
  v66 = v112;
  *((_DWORD *)v15 + 10) = *(_DWORD *)(v7 + 128);
  if ( v66 )
    v67 = *(_DWORD *)(*(_QWORD *)v66 + 80LL);
  else
    v67 = 0;
  v68 = v113;
  *((_DWORD *)v15 + 11) = v67;
  if ( v68 )
    *((_QWORD *)v15 + 6) = *(_QWORD *)(*(_QWORD *)v68 + 80LL);
  else
    *((_QWORD *)v15 + 6) = *(_QWORD *)(v7 + 152);
  if ( ((*(_DWORD *)(v7 + 32) & 0x1000) != 0 || v66 && (*(_DWORD *)(*(_QWORD *)v66 + 32LL) & 0x20000) != 0) && v68 )
  {
    PublicStateFromPrivate = BfeObjectGetPublicStateFromPrivate(v68);
    lpString2 = (LPCWCH)BfeFwpmProviderContextCopy(PublicStateFromPrivate, v15 + 28);
    if ( lpString2 )
    {
      v39 = lpString2;
      v40 = v99;
      BfeDestroy_FWPS_FILTER3(&v108);
      goto LABEL_151;
    }
    LODWORD(v23) = v97;
  }
  lpString2 = (LPCWCH)BfeValidateFilterConditionFieldKeys((unsigned int)v23, v11, &v106);
  if ( v106 )
    v15[13] |= 4u;
  *v114 = v15;
  v39 = lpString2;
LABEL_150:
  v40 = v99;
  if ( v39 )
    goto LABEL_63;
LABEL_151:
  for ( k = 0; k < v10; *v70 = 0 )
  {
    v70 = (LPCVOID *)(v9 + 8LL * k);
    if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
    {
      WfpMemFree25B(v9 + 8LL * k);
    }
    else
    {
      if ( gWfpTrackHeapBytes && *v70 )
        _InterlockedAdd(&gWfpHeapBytesAllocated, -(int)HeapSize(gWfpHeap, 0, *v70));
      HeapFree(gWfpHeap, 0, (LPVOID)*v70);
    }
    ++k;
  }
  if ( v9 )
    WfpMemFree(&v109);
  if ( v40 )
    WfpMemFree(&v110);
  if ( g_isEnabled_Feature_Firewall_042024 )
  {
    LocalFree(hMem);
    LocalFree(v117);
  }
  if ( v39 )
    WfpReportError(v39, "BfeFilterConvertM2S");
  return v39;
}

```

## disassembly

```asm
0x180013f60  mov     [rsp-8+arg_8], rbx
0x180013f65  push    rbp
0x180013f66  push    rsi
0x180013f67  push    rdi
0x180013f68  push    r12
0x180013f6a  push    r13
0x180013f6c  push    r14
0x180013f6e  push    r15
0x180013f70  lea     rbp, [rsp-40h]
0x180013f75  sub     rsp, 140h
0x180013f7c  mov     rax, cs:__security_cookie
0x180013f83  xor     rax, rsp
0x180013f86  mov     [rbp+70h+var_38], rax
0x180013f8a  mov     rax, [rbp+70h+arg_28]
0x180013f91  mov     rbx, rdx
0x180013f94  mov     rdi, [rbp+70h+arg_20]
0x180013f9b  xor     edx, edx
0x180013f9d  mov     [rbp+70h+var_90], rax
0x180013fa1  mov     r12, rcx
0x180013fa4  mov     [rbp+70h+var_98], r9
0x180013fa8  mov     r14d, edx
0x180013fab  mov     [rax], rdx
0x180013fae  mov     esi, edx
0x180013fb0  mov     r15, [rdi+78h]
0x180013fb4  mov     eax, [rdi+70h]
0x180013fb7  mov     [rbp+70h+var_E0], r15
0x180013fbb  mov     [rbp+70h+var_A0], r8
0x180013fbf  mov     [rbp+70h+var_D8], rcx
0x180013fc3  mov     [rbp+70h+var_A8], rdi
0x180013fc7  mov     [rbp+70h+var_C0], rdx
0x180013fcb  mov     [rbp+70h+var_D0], edx
0x180013fce  mov     [rbp+70h+var_70], edx
0x180013fd1  mov     [rbp+70h+hMem], rdx
0x180013fd5  mov     [rbp+70h+var_78], rdx
0x180013fd9  mov     [rbp+70h+var_B8], rdx
0x180013fdd  mov     [rsp+170h+var_108], edx
0x180013fe1  mov     [rsp+170h+var_100], rdx
0x180013fe6  mov     [rbp+70h+var_B0], rdx
0x180013fea  mov     [rbp+70h+var_F0], edx
0x180013fed  mov     [rsp+170h+var_110], eax
0x180013ff1  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180013ff6  mov     edx, 8; dwFlags
0x180013ffb  test    eax, eax
0x180013ffd  jnz     loc_1800143A8
0x180014003  mov     rcx, cs:gWfpHeap; hHeap
0x18001400a  mov     r8d, 40h ; '@'; dwBytes
0x180014010  call    cs:__imp_HeapAlloc
0x180014017  nop     dword ptr [rax+rax+00h]
0x18001401c  mov     [rbp+70h+var_E8], rax
0x180014020  mov     r13, rax
0x180014023  mov     [rbp+70h+var_C0], rax
0x180014027  test    rax, rax
0x18001402a  jz      loc_180014FAF
0x180014030  cmp     cs:gWfpTrackHeapBytes, esi
0x180014036  mov     [rsp+170h+lpString2], rsi
0x18001403b  jnz     loc_180014FEE
0x180014041  mov     rax, [rsp+170h+lpString2]
0x180014046  test    rax, rax
0x180014049  jnz     loc_180014F45
0x18001404f  mov     rax, [rdi+0B0h]
0x180014056  lea     rdx, [r13+8]
0x18001405a  lea     rcx, [rdi+60h]
0x18001405e  mov     [r13+0], rax
0x180014062  call    BfeFwpConditionValueCopyInner
0x180014067  mov     [rsp+170h+lpString2], rax
0x18001406c  test    rax, rax
0x18001406f  jnz     loc_180014F45
0x180014075  mov     rax, [rbx]
0x180014078  mov     [rbp+70h+var_EC], esi
0x18001407b  movzx   ecx, word ptr [rax+40h]
0x18001407f  mov     [r13+18h], cx
0x180014084  test    byte ptr [rdi+20h], 8
0x180014088  jnz     loc_180015012
0x18001408e  test    byte ptr [rdi+20h], 10h
0x180014092  jnz     loc_1800144C5
0x180014098  test    byte ptr [rdi+20h], 80h
0x18001409c  jnz     loc_18001501D
0x1800140a2  test    dword ptr [rdi+20h], 400h
0x1800140a9  jnz     loc_180015028
0x1800140af  test    dword ptr [rdi+20h], 800h
0x1800140b6  jnz     loc_180015033
0x1800140bc  test    dword ptr [rdi+20h], 1000h
0x1800140c3  jnz     loc_18001445A
0x1800140c9  test    dword ptr [rdi+20h], 2000h
0x1800140d0  jnz     loc_18001503E
0x1800140d6  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800140dd  nop     dword ptr [rax+rax+00h]
0x1800140e2  test    eax, eax
0x1800140e4  jnz     loc_18001504D
0x1800140ea  mov     rdx, [r12+10h]
0x1800140ef  test    rdx, rdx
0x1800140f2  jz      loc_180014FE3
0x1800140f8  mov     rdx, [rdx+8]
0x1800140fc  xor     r12d, r12d
0x1800140ff  mov     ecx, 4
0x180014104  test    rdx, rdx
0x180014107  jz      short loc_18001413B
0x180014109  mov     rax, [rdx+8]
0x18001410d  cmp     dword ptr [rax], 2
0x180014110  jz      loc_18001431F
0x180014116  mov     rdx, [rdx]
0x180014119  jmp     short loc_180014104
0x18001411b  mov     r8d, 0C0000023h
0x180014121  lea     rdx, aBfeindiceshast; "BfeIndicesHasTrie"
0x180014128  call    WfpReportSysErrorAsNtStatus
0x18001412d  mov     [rsp+170h+lpString2], rax
0x180014132  test    rax, rax
0x180014135  jnz     loc_180014F45
0x18001413b  mov     ebx, [rsp+170h+var_110]
0x18001413f  test    ebx, ebx
0x180014141  jz      loc_180014F89
0x180014147  xor     r13d, r13d
0x18001414a  xor     r15d, r15d
0x18001414d  test    ebx, ebx
0x18001414f  jz      loc_18001426D
0x180014155  mov     r14, [rbp+70h+var_E0]
0x180014159  nop     dword ptr [rax+00000000h]
0x180014160  mov     rax, [rbp+70h+var_D8]
0x180014164  xor     edx, edx
0x180014166  mov     ebx, r15d
0x180014169  mov     r11, [rax]
0x18001416c  movzx   r10d, word ptr [r11+24h]
0x180014171  cmp     dx, r10w
0x180014175  jnb     short loc_1800141DF
0x180014177  lea     rax, [r15+r15*4]
0x18001417b  movzx   ecx, dx
0x18001417e  lea     r8, [r14+rax*8]
0x180014182  mov     ebx, r15d
0x180014185  mov     rax, [r11+28h]
0x180014189  add     rcx, rcx
0x18001418c  mov     r9, [rax+rcx*8]
0x180014190  mov     rax, [r9]
0x180014193  sub     rax, [r8]
0x180014196  jnz     short loc_1800141A0
0x180014198  mov     rax, [r9+8]
0x18001419c  sub     rax, [r8+8]
0x1800141a0  test    rax, rax
0x1800141a3  jz      short loc_1800141AA
0x1800141a5  inc     dx
0x1800141a8  jmp     short loc_180014171
0x1800141aa  movzx   r13d, dx
0x1800141ae  lea     rax, [rbx+rbx*4]
0x1800141b2  cmp     dword ptr [r14+rax*8+10h], 5
0x1800141b8  jnz     loc_18001424E
0x1800141be  xor     ecx, ecx
0x1800141c0  movzx   edx, r12w
0x1800141c4  cmp     ecx, edx
0x1800141c6  jge     loc_18001424E
0x1800141cc  movsxd  rax, ecx
0x1800141cf  cmp     r13w, word ptr [rbp+rax*2+70h+var_70]
0x1800141d5  jnz     loc_1800144D0
0x1800141db  inc     esi
0x1800141dd  jmp     short loc_18001424E
0x1800141df  mov     r8d, 80320002h
0x1800141e5  lea     rdx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x1800141ec  call    WfpReportSysErrorAsWinError
0x1800141f1  mov     rdi, rax
0x1800141f4  test    rax, rax
0x1800141f7  jz      short loc_1800141AE
0x1800141f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180014200  lea     rax, WPP_GLOBAL_Control
0x180014207  cmp     rcx, rax
0x18001420a  jz      loc_180014347
0x180014210  cmp     byte ptr [rcx+19h], 2
0x180014214  jb      loc_180014347
0x18001421a  test    byte ptr [rcx+1Ch], 1
0x18001421e  lea     rbx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x180014225  jz      short loc_180014241
0x180014227  mov     rcx, [rcx+10h]
0x18001422b  mov     edx, 1Ah
0x180014230  mov     dword ptr [rsp+170h+var_148], edi
0x180014234  xor     r9d, r9d
0x180014237  mov     [rsp+170h+StringSecurityDescriptorLen], rbx
0x18001423c  call    WPP_SF_Ssd
0x180014241  cmp     cs:gWfpLogUserModeErrors, 0
0x180014248  jnz     loc_180014353
0x18001424e  mov     ebx, [rsp+170h+var_110]
0x180014252  inc     r15d
0x180014255  cmp     r15d, ebx
0x180014258  jb      loc_180014160
0x18001425e  test    esi, esi
0x180014260  mov     esi, [rsp+170h+var_108]
0x180014264  mov     r14d, esi
0x180014267  jnz     loc_1800143C8
0x18001426d  mov     r15, [rbp+70h+var_D8]
0x180014271  mov     r12, [rbp+70h+var_E0]
0x180014275  cmp     [rbp+70h+var_EC], 0
0x180014279  lea     eax, [rbx+1]
0x18001427c  mov     r13, [rbp+70h+var_E8]
0x180014280  mov     edx, 8; dwFlags
0x180014285  cmovz   eax, ebx
0x180014288  lea     rdi, [r13+20h]
0x18001428c  lea     rcx, [rax+rax*2]
0x180014290  mov     [rbp+70h+var_C8], rdi
0x180014294  shl     rcx, 3; dwBytes
0x180014298  mov     r8, rdi
0x18001429b  call    WfpMemAlloc
0x1800142a0  mov     [rsp+170h+lpString2], rax
0x1800142a5  test    rax, rax
0x1800142a8  jz      loc_1800144D7
0x1800142ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800142b5  lea     rax, WPP_GLOBAL_Control
0x1800142bc  lea     rbx, aWfpmemallocarr; "WfpMemAllocArray"
0x1800142c3  cmp     rcx, rax
0x1800142c6  jz      loc_180014465
0x1800142cc  cmp     byte ptr [rcx+19h], 2
0x1800142d0  jb      loc_180014465
0x1800142d6  test    byte ptr [rcx+1Ch], 1
0x1800142da  mov     r13, [rsp+170h+lpString2]
0x1800142df  jz      short loc_1800142FC
0x1800142e1  mov     rcx, [rcx+10h]
0x1800142e5  mov     edx, 1Ah
0x1800142ea  mov     dword ptr [rsp+170h+var_148], r13d
0x1800142ef  xor     r9d, r9d
0x1800142f2  mov     [rsp+170h+StringSecurityDescriptorLen], rbx
0x1800142f7  call    WPP_SF_Ssd
0x1800142fc  cmp     cs:gWfpLogUserModeErrors, 0
0x180014303  jnz     loc_18001446F
0x180014309  mov     r15, [rsp+170h+var_100]
0x18001430e  xor     r12d, r12d
0x180014311  lea     rcx, [rbp+70h+var_C0]
0x180014315  call    BfeDestroy_FWPS_FILTER3
0x18001431a  jmp     loc_180014908
0x18001431f  cmp     cx, r12w
0x180014323  jbe     loc_18001411B
0x180014329  mov     rax, [rax+8]
0x18001432d  movzx   ecx, r12w
0x180014331  inc     r12w
0x180014335  movzx   eax, word ptr [rax]
0x180014338  mov     word ptr [rbp+rcx*2+70h+var_70], ax
0x18001433d  mov     ecx, 4
0x180014342  jmp     loc_180014116
0x180014347  lea     rbx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x18001434e  jmp     loc_180014241
0x180014353  test    cs:byte_1800F6115, 1
0x18001435a  jz      loc_18001424E
0x180014360  lea     rax, [rsp+170h+var_118]
0x180014365  mov     [rsp+170h+var_118], edi
0x180014369  mov     [rbp+70h+var_48], rax
0x18001436d  lea     rdx, WFP_USERMODE_ERROR
0x180014374  lea     rax, [rbp+70h+var_68]
0x180014378  mov     qword ptr [rbp+70h+var_58], rbx
0x18001437c  mov     r9d, 3
0x180014382  mov     [rsp+170h+StringSecurityDescriptorLen], rax
0x180014387  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18001438e  mov     qword ptr [rbp+70h+var_58+8], 1Ch
0x180014396  mov     [rbp+70h+var_40], 4
0x18001439e  call    McGenEventWrite_EtwEventWriteTransfer
0x1800143a3  jmp     loc_18001424E
0x1800143a8  lea     r8, [rbp+70h+var_C0]
0x1800143ac  mov     ecx, 40h ; '@'; dwBytes
0x1800143b1  call    WfpMemAlloc25B
0x1800143b6  mov     r13, [rbp+70h+var_C0]
0x1800143ba  mov     [rbp+70h+var_E8], r13
0x1800143be  mov     [rsp+170h+lpString2], rax
0x1800143c3  jmp     loc_180014046
0x1800143c8  call    Feature_IndexTrie__private_ReportDeviceUsage
0x1800143cd  mov     edx, 8
0x1800143d2  lea     r9, [rbp+70h+var_B8]
0x1800143d6  mov     r8d, edx
0x1800143d9  mov     rcx, rbx
0x1800143dc  call    WfpMemAllocArray
0x1800143e1  mov     r14, [rbp+70h+var_B8]
0x1800143e5  mov     r13, rax
0x1800143e8  test    rax, rax
0x1800143eb  jnz     loc_180014309
0x1800143f1  mov     r15, [rbp+70h+var_D8]
0x1800143f5  lea     rax, [rbp+70h+var_F0]
0x1800143f9  mov     r9, [rbp+70h+var_A8]
0x1800143fd  lea     rcx, [rbp+70h+var_70]
0x180014401  mov     [rsp+170h+var_130], rax
0x180014406  mov     r8, r15
0x180014409  lea     rax, [rbp+70h+var_B0]
0x18001440d  mov     [rsp+170h+var_118], ebx
0x180014411  mov     [rsp+170h+var_138], rax
0x180014416  movzx   edx, r12w
0x18001441a  lea     rax, [rsp+170h+var_118]
0x18001441f  mov     [rsp+170h+var_140], rax
0x180014424  mov     [rsp+170h+StringSecurityDescriptorLen], r14
0x180014429  call    BfeGenerateConditionsForTrie
0x18001442e  mov     esi, [rsp+170h+var_118]
0x180014432  mov     r13, rax
0x180014435  test    rax, rax
0x180014438  jnz     loc_180015066
0x18001443e  mov     rax, [rbp+70h+var_B0]
0x180014442  mov     ebx, [rbp+70h+var_F0]
0x180014445  mov     r12, rax
0x180014448  mov     [rsp+170h+var_100], rax
0x18001444d  mov     [rbp+70h+var_E0], rax
0x180014451  mov     [rsp+170h+var_110], ebx
0x180014455  jmp     loc_180014275
0x18001445a  or      word ptr [r13+1Ah], 40h
0x180014460  jmp     loc_1800140C9
0x180014465  mov     r13, [rsp+170h+lpString2]
0x18001446a  jmp     loc_1800142FC
0x18001446f  test    cs:byte_1800F6115, 1
0x180014476  jz      loc_180014309
0x18001447c  lea     rax, [rsp+170h+var_108]
0x180014481  mov     [rsp+170h+var_108], r13d
0x180014486  mov     [rbp+70h+var_48], rax
  ... truncated ...
```
