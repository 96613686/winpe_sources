# BfeFilterConvertM2S

- ea: `0x180013480`
- end: `0x1800145cc`
- name: `BfeFilterConvertM2S`
- size: `4428`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800069d0`

## callees

- `0x180001800`
- `0x180005708`
- `0x18000cfb0`
- `0x18000e000`
- `0x18000ef6c`
- `0x18000f1a8`
- `0x18000fad0`
- `0x180010ad0`
- `0x180010ba0`
- `0x18001236c`
- `0x180012b54`
- `0x180013480`
- `0x180018b74`
- `0x180020f24`
- `0x1800219c4`
- `0x180022190`
- `0x180022730`
- `0x1800238b4`
- `0x180026ecc`
- `0x180033bd0`
- `0x18003ba68`
- `0x18004a5cc`
- `0x18004aa48`
- `0x18004b7f0`
- `0x18004e230`
- `0x1800540ec`
- `0x1800542bc`
- `0x1800575c4`
- `0x180058b30`
- `0x180066738`
- `0x180066db0`
- `0x180087db4`
- `0x180087dc0`

## import_xrefs

- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180014084`
- `ntdll!RtlGetOwnerSecurityDescriptor` at `0x180014084`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013608`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180013608`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013542`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180013542`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180013f48`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800144b8`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180014524`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180013f48`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x1800144b8`
- `api-ms-win-core-heap-l1-1-0!HeapSize` at `0x180014524`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013cf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013e8b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013cf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013e8b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180088b19`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180088b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013efd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013efd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001434a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18001434a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001436b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001436b`

## string_xrefs

- `0x1800143ec`: `RtlGetOwnerSecurityDescriptor`

## pseudocode

```c
LPCWCH __fastcall BfeFilterConvertM2S(_QWORD *a1, __int64 *a2, __int64 a3, __int64 a4, __int64 a5, _QWORD *a6)
{
  unsigned int v7; // esi
  unsigned __int64 v9; // r14
  __int64 v10; // r15
  __int64 v11; // r13
  unsigned int v12; // eax
  char *v13; // rax
  __int64 v14; // rcx
  char *v15; // rdi
  const WCHAR *v16; // rax
  __int64 v17; // rax
  __int64 i; // rcx
  BOOL v19; // ebx
  __int64 v20; // rdx
  _QWORD *v21; // rdx
  unsigned __int16 v22; // r12
  __int64 v23; // rax
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
  __int64 v34; // rbx
  unsigned int v35; // r12d
  _QWORD *v36; // r15
  __int64 v37; // rax
  __int64 *v38; // rbx
  int v39; // r8d
  LPCWCH v40; // r13
  __int64 v41; // r15
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 ConditionsForTrie; // rax
  BOOL v45; // r15d
  int v46; // eax
  __int64 v47; // rbx
  __int64 j; // r12
  _QWORD *v49; // r13
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
  int v94; // [rsp+30h] [rbp-D8h]
  __int64 v95; // [rsp+38h] [rbp-D0h]
  LPCWCH lpString2; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v97; // [rsp+60h] [rbp-A8h] BYREF
  char *v98; // [rsp+68h] [rbp-A0h]
  LPVOID lpMem; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v100; // [rsp+78h] [rbp-90h]
  unsigned int v101; // [rsp+80h] [rbp-88h] BYREF
  __int64 v102; // [rsp+88h] [rbp-80h]
  unsigned int v103; // [rsp+90h] [rbp-78h] BYREF
  BOOL v104; // [rsp+94h] [rbp-74h]
  _QWORD *v105; // [rsp+98h] [rbp-70h]
  int v106; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v107; // [rsp+A8h] [rbp-60h]
  char *v108; // [rsp+B0h] [rbp-58h] BYREF
  void *v109; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v110; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v111; // [rsp+C8h] [rbp-40h]
  _QWORD *v112; // [rsp+D0h] [rbp-38h]
  __int64 v113; // [rsp+D8h] [rbp-30h]
  __int64 v114; // [rsp+E0h] [rbp-28h]
  _QWORD *v115; // [rsp+E8h] [rbp-20h]
  HLOCAL hMem; // [rsp+F0h] [rbp-18h] BYREF
  HLOCAL v117; // [rsp+F8h] [rbp-10h] BYREF
  PSID Owner; // [rsp+100h] [rbp-8h] BYREF
  int v119; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int8 OwnerDefaulted[4]; // [rsp+10Ch] [rbp+4h] BYREF
  __int128 v121; // [rsp+110h] [rbp+8h] BYREF
  __int128 v122; // [rsp+120h] [rbp+18h]
  unsigned int *v123; // [rsp+130h] [rbp+28h] BYREF
  __int64 v124; // [rsp+138h] [rbp+30h]

  v7 = 0;
  v9 = 0;
  *a6 = 0;
  v10 = a5;
  v115 = a6;
  v114 = a4;
  v113 = a3;
  v11 = *(_QWORD *)(a5 + 120);
  v12 = *(_DWORD *)(a5 + 112);
  v107 = v11;
  v105 = a1;
  v111 = a5;
  v108 = 0;
  v106 = 0;
  v119 = 0;
  hMem = 0;
  v117 = 0;
  lpMem = 0;
  v109 = 0;
  v101 = 0;
  v102 = 0;
  v110 = 0;
  v103 = 0;
  v100 = v12;
  if ( (unsigned int)Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline() )
  {
    v16 = (const WCHAR *)WfpMemAlloc25B(0x40u);
    v15 = v108;
    v98 = v108;
    lpString2 = v16;
  }
  else
  {
    v13 = (char *)HeapAlloc(gWfpHeap, 8u, 0x40u);
    v98 = v13;
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
    goto LABEL_243;
  *(_QWORD *)v15 = *(_QWORD *)(a5 + 176);
  lpString2 = (LPCWCH)BfeFwpConditionValueCopyInner(a5 + 96, v15 + 8);
  if ( lpString2 )
    goto LABEL_243;
  v17 = *a2;
  v104 = 0;
  *((_WORD *)v15 + 12) = *(_WORD *)(v17 + 64);
  if ( (*(_BYTE *)(a5 + 32) & 8) != 0 )
    *((_WORD *)v15 + 13) |= 1u;
  if ( (*(_BYTE *)(a5 + 32) & 0x10) != 0 )
    *((_WORD *)v15 + 13) |= 2u;
  if ( *(char *)(a5 + 32) < 0 )
    *((_WORD *)v15 + 13) |= 8u;
  if ( (*(_DWORD *)(a5 + 32) & 0x400) != 0 )
    *((_WORD *)v15 + 13) |= 0x10u;
  if ( (*(_DWORD *)(a5 + 32) & 0x800) != 0 )
    *((_WORD *)v15 + 13) |= 0x20u;
  if ( (*(_DWORD *)(a5 + 32) & 0x1000) != 0 )
    *((_WORD *)v15 + 13) |= 0x40u;
  if ( (*(_DWORD *)(a5 + 32) & 0x2000) != 0 )
    *((_WORD *)v15 + 13) |= 0x80u;
  if ( (unsigned int)RtlGetCurrentServiceSessionId() )
  {
    i = 0;
    v19 = (*(_BYTE *)(*a1 + 32LL) & 1) != 0;
    v104 = v19;
  }
  else
  {
    v19 = 0;
  }
  v20 = a1[2];
  if ( !v20 )
  {
    v22 = 4;
    goto LABEL_30;
  }
  v21 = *(_QWORD **)(v20 + 8);
  v22 = 0;
  i = 4;
  while ( 1 )
  {
    if ( !v21 )
      goto LABEL_30;
    v23 = v21[1];
    if ( *(_DWORD *)v23 == 2 )
      break;
LABEL_28:
    v21 = (_QWORD *)*v21;
  }
  if ( v22 < 4u )
  {
    v42 = v22++;
    *(_WORD *)&OwnerDefaulted[2 * v42 - 4] = **(_WORD **)(v23 + 8);
    i = 4;
    goto LABEL_28;
  }
  lpString2 = (LPCWCH)WfpReportSysErrorAsNtStatus(4, "BfeIndicesHasTrie", 3221225507LL);
  if ( lpString2 )
    goto LABEL_243;
LABEL_30:
  if ( !v100 && !v19 )
  {
LABEL_146:
    v66 = v113;
    *((_DWORD *)v15 + 10) = *(_DWORD *)(v10 + 128);
    if ( v66 )
      v67 = *(_DWORD *)(*(_QWORD *)v66 + 80LL);
    else
      v67 = 0;
    v68 = v114;
    *((_DWORD *)v15 + 11) = v67;
    if ( v68 )
      *((_QWORD *)v15 + 6) = *(_QWORD *)(*(_QWORD *)v68 + 80LL);
    else
      *((_QWORD *)v15 + 6) = *(_QWORD *)(v10 + 152);
    if ( (*(_DWORD *)(v10 + 32) & 0x1000) == 0 && (!v66 || (*(_DWORD *)(*(_QWORD *)v66 + 32LL) & 0x20000) == 0)
      || !v68
      || (PublicStateFromPrivate = BfeObjectGetPublicStateFromPrivate(v68),
          (lpString2 = (LPCWCH)BfeFwpmProviderContextCopy(PublicStateFromPrivate, v15 + 56)) == 0) )
    {
      v40 = (LPCWCH)BfeValidateFilterConditionFieldKeys(v100, v11, &v106);
      if ( v106 )
        *((_WORD *)v15 + 13) |= 4u;
      *v115 = v15;
      v15 = v98;
      goto LABEL_155;
    }
LABEL_243:
    v40 = lpString2;
LABEL_63:
    v15 = v98;
    v41 = v102;
LABEL_64:
    if ( v15 )
      BfeDestroyInner_FWPS_FILTER3(v15);
    WfpMemFree(&v108);
    goto LABEL_156;
  }
  v24 = 0;
  v25 = 0;
  if ( v100 )
  {
    v26 = v107;
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
        if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
        {
          LODWORD(v97) = v32;
          v123 = (unsigned int *)&v97;
          *(_QWORD *)&v122 = "BfeLayerLookupConditionInfo";
          *((_QWORD *)&v122 + 1) = 28;
          v124 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v33,
            3,
            (__int64)&v121);
        }
        goto LABEL_51;
      }
LABEL_40:
      if ( *(_DWORD *)(v26 + 40 * v28 + 16) == 5 )
      {
        for ( i = 0; (int)i < v22; i = (unsigned int)(i + 1) )
        {
          if ( v24 == *(_WORD *)&OwnerDefaulted[2 * (int)i - 4] )
          {
            ++v7;
            break;
          }
        }
      }
LABEL_51:
      v34 = v100;
      v25 = (unsigned int)(v25 + 1);
    }
    while ( (unsigned int)v25 < v100 );
    v72 = v7 == 0;
    v7 = v101;
    v9 = v101;
    if ( v72 )
    {
      v15 = v98;
      v35 = v100;
      goto LABEL_54;
    }
    Feature_IndexTrie__private_ReportDeviceUsage();
    v43 = WfpMemAllocArray(v34, 8, 8, &v109);
    v9 = (unsigned __int64)v109;
    v40 = (LPCWCH)v43;
    if ( v43 )
      goto LABEL_63;
    v36 = v105;
    LODWORD(v97) = v34;
    lpMem = v109;
    ConditionsForTrie = BfeGenerateConditionsForTrie(
                          (unsigned int)&v119,
                          v22,
                          (_DWORD)v105,
                          v111,
                          (__int64)v109,
                          v94,
                          (__int64)&v97,
                          (__int64)&v110,
                          (__int64)&v103);
    v7 = v97;
    v40 = (LPCWCH)ConditionsForTrie;
    v15 = v98;
    if ( ConditionsForTrie )
    {
      v41 = v110;
      goto LABEL_64;
    }
    v35 = v103;
    v11 = v110;
    v102 = v110;
    v107 = v110;
    v100 = v103;
  }
  else
  {
    v35 = 0;
LABEL_54:
    v36 = v105;
    v11 = v107;
  }
  v37 = v35 + 1;
  v38 = (__int64 *)(v15 + 32);
  if ( !v104 )
    v37 = v35;
  v112 = v15 + 32;
  lpString2 = (LPCWCH)WfpMemAlloc(24 * v37, 8u);
  if ( lpString2 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v40 = lpString2;
    }
    else
    {
      v40 = lpString2;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v39, 0, (__int64)"WfpMemAllocArray", (char)lpString2);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
    {
      v101 = (unsigned int)v40;
      v123 = &v101;
      *(_QWORD *)&v122 = "WfpMemAllocArray";
      *((_QWORD *)&v122 + 1) = 17;
      v124 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v39,
        3,
        (__int64)&v121);
    }
    goto LABEL_63;
  }
  if ( !g_isEnabled_Feature_Firewall_042024 )
  {
    for ( j = 0; (unsigned int)j < v100; *((_DWORD *)v15 + 7) = j )
    {
      lpString2 = (LPCWCH)BfeFilterConditionConvertM2S(v36, v11 + 40 * j, 0, *v38 + 24 * j);
      if ( lpString2 )
        goto LABEL_243;
      j = (unsigned int)(j + 1);
    }
LABEL_144:
    if ( v104 )
    {
      v122 = 0u;
      v123 = 0;
      v86 = *v38;
      v121 = FWPM_CONDITION_COMPARTMENT_ID;
      lpString2 = (LPCWCH)BfeFilterConditionConvertM2S(v105, &v121, 0, v86 + 24 * j);
      if ( lpString2 )
        goto LABEL_243;
      *((_DWORD *)v15 + 7) = j + 1;
    }
    v10 = v111;
    goto LABEL_146;
  }
  v45 = 0;
  v46 = 0;
  v47 = 0;
  LODWORD(v97) = 0;
  v119 = 0;
  if ( !v35 )
    goto LABEL_91;
  while ( 2 )
  {
    if ( v46 )
      goto LABEL_86;
    if ( memcmp_0((const void *)(v11 + 40 * v47), &FWPM_CONDITION_ALE_PACKAGE_FAMILY_NAME, 0x10u)
      || (v84 = *(_QWORD *)(v11 + 40 * v47 + 32)) == 0
      || (v85 = *(void **)(v84 + 8)) == 0 )
    {
      v46 = v119;
LABEL_86:
      if ( v45 )
        goto LABEL_89;
      if ( !memcmp_0((const void *)(v11 + 40 * v47), &FWPM_CONDITION_ALE_PACKAGE_ID, 0x10u)
        && ConvertSidToStringSidW(*(PSID *)(v11 + 40 * v47 + 32), (LPWSTR *)&hMem) )
      {
        v45 = wcscmp_0((const wchar_t *)hMem, L"S-1-0-0") != 0;
      }
      goto LABEL_88;
    }
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(v85, 1u, 7u, (LPWSTR *)&v117, 0) )
    {
LABEL_88:
      v46 = v119;
      goto LABEL_89;
    }
    v46 = 1;
    v119 = 1;
LABEL_89:
    v47 = (unsigned int)(v47 + 1);
    if ( (unsigned int)v47 < v35 )
      continue;
    break;
  }
  v9 = (unsigned __int64)lpMem;
  v15 = v98;
  LODWORD(v97) = v45;
LABEL_91:
  for ( j = 0; ; *((_DWORD *)v15 + 7) = j )
  {
LABEL_92:
    if ( (unsigned int)j >= v100 )
    {
      v38 = (__int64 *)(v15 + 32);
      goto LABEL_144;
    }
    v49 = (_QWORD *)(v11 + 40 * j);
    if ( memcmp_0(v49, &FWPM_CONDITION_ALE_PACKAGE_ID, 0x10u) || !(_DWORD)v97 || v119 )
      break;
    lpMem = 0;
    if ( (int)PackageSidStringToPackageFamilyName((PCWSTR)hMem, &lpMem) < 0 )
      goto LABEL_235;
    v81 = (const wchar_t *)lpMem;
    if ( !lpMem )
      goto LABEL_235;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_ISS(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v80, *(_QWORD *)v15, (__int64)hMem, (__int64)lpMem);
    }
    v121 = 0;
    v123 = 0;
    v122 = 0;
    PfnCondition = BfeCreatePfnCondition(v81, (__int64)&v121);
    WfpMemFree(&lpMem);
    if ( PfnCondition )
    {
LABEL_235:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_IS(*((_QWORD *)WPP_GLOBAL_Control + 2), v79, v80, *(_QWORD *)v15, (__int64)hMem);
      }
LABEL_95:
      v50 = 3 * j;
      v51 = 0;
      lpMem = 0;
      v52 = 0;
      v53 = *v112 + 24 * j;
      while ( 1 )
      {
        if ( v52 >= *(_WORD *)(*v105 + 36LL) )
        {
          v54 = 0;
          v61 = (const WCHAR *)WfpReportSysErrorAsWinError(v50, "BfeLayerLookupConditionInfo", 2150760450LL);
          lpString2 = v61;
          if ( !v61 )
            goto LABEL_103;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              v62,
              0,
              (__int64)"BfeLayerLookupConditionInfo",
              (char)v61);
            LODWORD(v61) = (_DWORD)lpString2;
          }
          if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
          {
            v101 = (unsigned int)v61;
            *(_QWORD *)&v122 = "BfeLayerLookupConditionInfo";
            v123 = &v101;
            *((_QWORD *)&v122 + 1) = 28;
            v124 = 4;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
              (unsigned int)WFP_USERMODE_ERROR,
              v62,
              3,
              (__int64)&v121);
          }
          v40 = lpString2;
LABEL_125:
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
          if ( !v40 )
            goto LABEL_135;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_Ssd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              26,
              v63,
              0,
              (__int64)"BfeFilterConditionConvertM2S",
              (char)v40);
          }
          if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
          {
            v101 = (unsigned int)v40;
            v123 = &v101;
            *(_QWORD *)&v122 = "BfeFilterConditionConvertM2S";
            *((_QWORD *)&v122 + 1) = 29;
            v124 = 4;
            McGenEventWrite_EtwEventWriteTransfer(
              (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
              (unsigned int)WFP_USERMODE_ERROR,
              v63,
              3,
              (__int64)&v121);
          }
          goto LABEL_63;
        }
        v54 = *(_QWORD *)(*v105 + 40LL) + 16LL * v52;
        v50 = *(_QWORD *)v54;
        v55 = **(_QWORD **)v54 - *v49;
        if ( !v55 )
          v55 = *(_QWORD *)(v50 + 8) - v49[1];
        if ( !v55 )
          break;
        ++v52;
      }
      if ( v53 )
        *(_WORD *)v53 = v52;
LABEL_103:
      v56 = *((_DWORD *)v49 + 4);
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
          goto LABEL_140;
        }
LABEL_107:
        v59 = *(_DWORD *)(v54 + 12);
        v50 = *((unsigned int *)v49 + 6);
        if ( (_DWORD)v50 == 257 )
        {
          if ( v59 == 11 && v58 == 1 )
            goto LABEL_114;
        }
        else if ( (int)v50 > 15 )
        {
          if ( (_DWORD)v50 != 16 )
          {
            if ( (_DWORD)v50 == 256 )
            {
              if ( v59 != 3 )
                goto LABEL_139;
              v72 = v58 == 1;
            }
            else
            {
              if ( (_DWORD)v50 != 258 )
                goto LABEL_113;
              v72 = *(_DWORD *)v49[4] == v59;
            }
            if ( v72 )
              goto LABEL_114;
          }
        }
        else if ( (_DWORD)v50 != 15 )
        {
          switch ( (_DWORD)v50 )
          {
            case 0:
              goto LABEL_114;
            case 0xD:
              if ( v59 == 13 )
                goto LABEL_114;
              break;
            case 0xE:
              if ( v59 == 13 || (unsigned int)(v59 - 15) <= 1 )
                goto LABEL_114;
              break;
            default:
LABEL_113:
              if ( (_DWORD)v50 == v59 )
                goto LABEL_114;
              break;
          }
        }
LABEL_139:
        v64 = 2150760487LL;
        goto LABEL_140;
      }
      if ( !v57 )
        goto LABEL_107;
      v64 = 2150760486LL;
LABEL_140:
      v65 = (const WCHAR *)WfpReportSysErrorAsWinError(v50, "BfeFwpmFilterConditionAssocValidate", v64);
      lpString2 = v65;
      if ( v65 )
      {
        v40 = v65;
        WfpReportError(v65, "BfeFwpmFilterConditionAssocValidate");
        goto LABEL_125;
      }
LABEL_114:
      *(_WORD *)(v53 + 2) = 0;
      *(_DWORD *)(v53 + 4) = *((_DWORD *)v49 + 4);
      if ( *((_DWORD *)v49 + 6) != 14 )
      {
LABEL_115:
        v60 = BfeFwpConditionValueCopyInner(v49 + 3, v53 + 8);
        goto LABEL_116;
      }
      v73 = v49[4];
      Owner = 0;
      OwnerDefaulted[0] = 0;
      v74 = *(void **)(v73 + 8);
      OwnerSecurityDescriptor = RtlGetOwnerSecurityDescriptor(v74, &Owner, OwnerDefaulted);
      if ( OwnerSecurityDescriptor < 0 )
      {
        v60 = WfpReportSysErrorAsNtStatus(v76, "RtlGetOwnerSecurityDescriptor", (unsigned int)OwnerSecurityDescriptor);
LABEL_116:
        v40 = (LPCWCH)v60;
        if ( v60 )
        {
LABEL_117:
          v51 = lpMem;
          goto LABEL_125;
        }
LABEL_135:
        v15 = v98;
        goto LABEL_136;
      }
      if ( Owner || !v74 )
        goto LABEL_115;
      v103 = 0;
      v40 = (LPCWCH)CloneSecurityDescriptorWithOwner(v74);
      if ( v40 )
        goto LABEL_117;
      v40 = (LPCWCH)WfpMemAlloc(0x10u, 0);
      if ( v40 )
        goto LABEL_117;
      v77 = *(_QWORD *)(v53 + 16);
      j = (unsigned int)(j + 1);
      v78 = lpMem;
      v15 = v98;
      v11 = v107;
      *(_DWORD *)(v53 + 8) = 14;
      *(_QWORD *)(v77 + 8) = v78;
      **(_DWORD **)(v53 + 16) = v103;
      *((_DWORD *)v15 + 7) = j;
      goto LABEL_92;
    }
    v40 = (LPCWCH)BfeFilterConditionConvertM2S(v105, &v121, 0, *((_QWORD *)v15 + 4) + 24 * j);
    if ( v123 )
    {
      if ( *((_QWORD *)v123 + 1) )
        WfpMemFree(v123 + 2);
      WfpMemFree(&v123);
    }
    if ( v40 )
      goto LABEL_63;
    *((_WORD *)v15 + 13) |= 0x100u;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_136:
      j = (unsigned int)(j + 1);
      *((_DWORD *)v15 + 7) = j;
LABEL_137:
      v11 = v107;
      goto LABEL_92;
    }
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_0ac2aa085a863ed18a171940451ff39f_Traceguids, *(_QWORD *)v15);
    v11 = v107;
    j = (unsigned int)(j + 1);
  }
  if ( memcmp_0(v49, &FWPM_CONDITION_ALE_PACKAGE_ID, 0x10u) )
    goto LABEL_95;
  if ( !(_DWORD)v97 )
    goto LABEL_95;
  if ( !v119 )
    goto LABEL_95;
  lpString2 = 0;
  if ( (int)PackageSidStringToPackageFamilyName((PCWSTR)hMem, &lpString2) < 0 )
    goto LABEL_95;
  v88 = lpString2;
  if ( !lpString2 )
    goto LABEL_95;
  lpMem = 0;
  PfnFromSDDLString = BfeGetPfnFromSDDLString(v117, &lpMem);
  v92 = lpMem;
  if ( !PfnFromSDDLString && CompareStringOrdinal((LPCWCH)lpMem, -1, v88, -1, 1) == 2 )
  {
    v15 = v98;
    *((_WORD *)v98 + 13) |= 0x100u;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_ISS(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v91, *(_QWORD *)v15, (__int64)hMem, (__int64)v92);
    }
    WfpMemFree(&lpMem);
    WfpMemFree(&lpString2);
    j = (unsigned int)(j + 1);
    goto LABEL_137;
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
  {
    v15 = v98;
  }
  else
  {
    v95 = (__int64)v88;
    v15 = v98;
    WPP_SF_ISSS(*((_QWORD *)WPP_GLOBAL_Control + 2), v90, v91, *(_QWORD *)v98, (__int64)hMem, (__int64)v92, v95);
  }
  MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( v92 )
    WfpMemFree(&lpMem);
  WfpMemFree(&lpString2);
  v40 = (LPCWCH)WfpReportSysErrorAsHResult(v93, "\"BfeFilterConvertM2S\"", 2150760501LL, 1);
LABEL_155:
  v41 = v102;
  if ( v40 )
    goto LABEL_64;
LABEL_156:
  for ( k = 0; k < v7; *v70 = 0 )
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
  if ( v41 )
    WfpMemFree(&v110);
  if ( g_isEnabled_Feature_Firewall_042024 )
  {
    LocalFree(hMem);
    LocalFree(v117);
  }
  if ( v40 )
    WfpReportError(v40, "BfeFilterConvertM2S");
  return v40;
}

```

## disassembly

```asm
0x180013480  mov     r11, rsp
0x180013483  push    rbp
0x180013484  push    r13
0x180013486  lea     rbp, [r11-78h]
0x18001348a  sub     rsp, 168h
0x180013491  mov     rax, cs:__security_cookie
0x180013498  xor     rax, rsp
0x18001349b  mov     [rbp+70h+var_38], rax
0x18001349f  mov     rax, [rbp+70h+arg_28]
0x1800134a6  mov     [r11+10h], rbx
0x1800134aa  mov     rbx, rdx
0x1800134ad  xor     edx, edx
0x1800134af  mov     [r11-18h], rsi
0x1800134b3  mov     [r11-20h], rdi
0x1800134b7  mov     esi, edx
0x1800134b9  mov     [r11-28h], r12
0x1800134bd  mov     r12, rcx
0x1800134c0  mov     [r11-30h], r14
0x1800134c4  mov     r14d, edx
0x1800134c7  mov     [rax], rdx
0x1800134ca  mov     [r11-38h], r15
0x1800134ce  mov     r15, [rbp+70h+arg_20]
0x1800134d5  mov     [rbp+70h+var_90], rax
0x1800134d9  mov     [rbp+70h+var_98], r9
0x1800134dd  mov     [rbp+70h+var_A0], r8
0x1800134e1  mov     r13, [r15+78h]
0x1800134e5  mov     eax, [r15+70h]
0x1800134e9  mov     [rbp+70h+var_D0], r13
0x1800134ed  mov     [rbp+70h+var_E0], rcx
0x1800134f1  mov     [rbp+70h+var_B0], r15
0x1800134f5  mov     [rbp+70h+var_C8], rdx
0x1800134f9  mov     [rbp+70h+var_D8], edx
0x1800134fc  mov     [rbp+70h+var_70], edx
0x1800134ff  mov     [rbp+70h+hMem], rdx
0x180013503  mov     [rbp+70h+var_80], rdx
0x180013507  mov     [rsp+170h+lpMem], rdx
0x18001350c  mov     [rbp+70h+var_C0], rdx
0x180013510  mov     [rsp+170h+var_F8], edx
0x180013514  mov     [rbp+70h+var_F0], rdx
0x180013518  mov     [rbp+70h+var_B8], rdx
0x18001351c  mov     [rbp+70h+var_E8], edx
0x18001351f  mov     [rsp+170h+var_100], eax
0x180013523  call    Feature_BFE_MemAlloc_BugFixes_25B__private_IsEnabledDeviceUsageInline
0x180013528  mov     edx, 8; dwFlags
0x18001352d  test    eax, eax
0x18001352f  jnz     loc_1800138F2
0x180013535  mov     rcx, cs:gWfpHeap; hHeap
0x18001353c  mov     r8d, 40h ; '@'; dwBytes
0x180013542  call    cs:__imp_HeapAlloc
0x180013548  mov     [rsp+170h+var_110], rax
0x18001354d  mov     rdi, rax
0x180013550  mov     [rbp+70h+var_C8], rax
0x180013554  test    rax, rax
0x180013557  jz      loc_1800144D9
0x18001355d  cmp     cs:gWfpTrackHeapBytes, esi
0x180013563  mov     [rsp+170h+lpString2], rsi
0x180013568  jnz     loc_180014518
0x18001356e  mov     rax, [rsp+170h+lpString2]
0x180013573  test    rax, rax
0x180013576  jnz     loc_18001447B
0x18001357c  mov     rax, [r15+0B0h]
0x180013583  lea     rdx, [rdi+8]
0x180013587  lea     rcx, [r15+60h]
0x18001358b  mov     [rdi], rax
0x18001358e  call    BfeFwpConditionValueCopyInner
0x180013593  mov     [rsp+170h+lpString2], rax
0x180013598  test    rax, rax
0x18001359b  jnz     loc_18001447B
0x1800135a1  mov     rax, [rbx]
0x1800135a4  mov     [rbp+70h+var_E4], esi
0x1800135a7  movzx   ecx, word ptr [rax+40h]
0x1800135ab  mov     [rdi+18h], cx
0x1800135af  test    byte ptr [r15+20h], 8
0x1800135b4  jnz     loc_180014536
0x1800135ba  test    byte ptr [r15+20h], 10h
0x1800135bf  jnz     loc_180013A22
0x1800135c5  test    byte ptr [r15+20h], 80h
0x1800135ca  jnz     loc_180014540
0x1800135d0  test    dword ptr [r15+20h], 400h
0x1800135d8  jnz     loc_18001454A
0x1800135de  test    dword ptr [r15+20h], 800h
0x1800135e6  jnz     loc_180014554
0x1800135ec  test    dword ptr [r15+20h], 1000h
0x1800135f4  jnz     loc_1800139B0
0x1800135fa  test    dword ptr [r15+20h], 2000h
0x180013602  jnz     loc_18001455E
0x180013608  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18001360e  test    eax, eax
0x180013610  jnz     loc_18001456C
0x180013616  mov     ebx, esi
0x180013618  mov     rdx, [r12+10h]
0x18001361d  test    rdx, rdx
0x180013620  jz      loc_18001450D
0x180013626  mov     rdx, [rdx+8]
0x18001362a  xor     r12d, r12d
0x18001362d  mov     ecx, 4
0x180013632  test    rdx, rdx
0x180013635  jz      short loc_180013669
0x180013637  mov     rax, [rdx+8]
0x18001363b  cmp     dword ptr [rax], 2
0x18001363e  jz      loc_180013869
0x180013644  mov     rdx, [rdx]
0x180013647  jmp     short loc_180013632
0x180013649  mov     r8d, 0C0000023h
0x18001364f  lea     rdx, aBfeindiceshast; "BfeIndicesHasTrie"
0x180013656  call    WfpReportSysErrorAsNtStatus
0x18001365b  mov     [rsp+170h+lpString2], rax
0x180013660  test    rax, rax
0x180013663  jnz     loc_18001447B
0x180013669  mov     eax, [rsp+170h+var_100]
0x18001366d  test    eax, eax
0x18001366f  jz      loc_1800144CC
0x180013675  xor     r13d, r13d
0x180013678  xor     r15d, r15d
0x18001367b  test    eax, eax
0x18001367d  jz      loc_1800139C4
0x180013683  mov     r14, [rbp+70h+var_D0]
0x180013687  nop     word ptr [rax+rax+00000000h]
0x180013690  mov     rax, [rbp+70h+var_E0]
0x180013694  xor     edx, edx
0x180013696  mov     ebx, r15d
0x180013699  mov     r11, [rax]
0x18001369c  movzx   r10d, word ptr [r11+24h]
0x1800136a1  cmp     dx, r10w
0x1800136a5  jnb     short loc_18001370F
0x1800136a7  lea     rax, [r15+r15*4]
0x1800136ab  movzx   ecx, dx
0x1800136ae  lea     r8, [r14+rax*8]
0x1800136b2  mov     ebx, r15d
0x1800136b5  mov     rax, [r11+28h]
0x1800136b9  add     rcx, rcx
0x1800136bc  mov     r9, [rax+rcx*8]
0x1800136c0  mov     rax, [r9]
0x1800136c3  sub     rax, [r8]
0x1800136c6  jnz     short loc_1800136D0
0x1800136c8  mov     rax, [r9+8]
0x1800136cc  sub     rax, [r8+8]
0x1800136d0  test    rax, rax
0x1800136d3  jz      short loc_1800136DA
0x1800136d5  inc     dx
0x1800136d8  jmp     short loc_1800136A1
0x1800136da  movzx   r13d, dx
0x1800136de  lea     rax, [rbx+rbx*4]
0x1800136e2  cmp     dword ptr [r14+rax*8+10h], 5
0x1800136e8  jnz     loc_18001377E
0x1800136ee  xor     ecx, ecx
0x1800136f0  movzx   edx, r12w
0x1800136f4  cmp     ecx, edx
0x1800136f6  jge     loc_18001377E
0x1800136fc  movsxd  rax, ecx
0x1800136ff  cmp     r13w, word ptr [rbp+rax*2+70h+var_70]
0x180013705  jnz     loc_180013A2C
0x18001370b  inc     esi
0x18001370d  jmp     short loc_18001377E
0x18001370f  mov     r8d, 80320002h
0x180013715  lea     rdx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x18001371c  call    WfpReportSysErrorAsWinError
0x180013721  mov     rdi, rax
0x180013724  test    rax, rax
0x180013727  jz      short loc_1800136DE
0x180013729  mov     rcx, cs:WPP_GLOBAL_Control
0x180013730  lea     rax, WPP_GLOBAL_Control
0x180013737  cmp     rcx, rax
0x18001373a  jz      loc_180013891
0x180013740  cmp     byte ptr [rcx+19h], 2
0x180013744  jb      loc_180013891
0x18001374a  test    byte ptr [rcx+1Ch], 1
0x18001374e  lea     rbx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x180013755  jz      short loc_180013771
0x180013757  mov     rcx, [rcx+10h]
0x18001375b  mov     edx, 1Ah
0x180013760  mov     dword ptr [rsp+170h+var_148], edi
0x180013764  xor     r9d, r9d
0x180013767  mov     [rsp+170h+StringSecurityDescriptorLen], rbx
0x18001376c  call    WPP_SF_Ssd
0x180013771  cmp     cs:gWfpLogUserModeErrors, 0
0x180013778  jnz     loc_18001389D
0x18001377e  mov     ebx, [rsp+170h+var_100]
0x180013782  inc     r15d
0x180013785  cmp     r15d, ebx
0x180013788  jb      loc_180013690
0x18001378e  test    esi, esi
0x180013790  mov     esi, [rsp+170h+var_F8]
0x180013794  mov     r14d, esi
0x180013797  jnz     loc_180013913
0x18001379d  mov     rdi, [rsp+170h+var_110]
0x1800137a2  mov     r12d, [rsp+170h+var_100]
0x1800137a7  mov     r15, [rbp+70h+var_E0]
0x1800137ab  mov     r13, [rbp+70h+var_D0]
0x1800137af  cmp     [rbp+70h+var_E4], 0
0x1800137b3  lea     eax, [r12+1]
0x1800137b8  lea     rbx, [rdi+20h]
0x1800137bc  mov     edx, 8; dwFlags
0x1800137c1  cmovz   eax, r12d
0x1800137c5  mov     [rbp+70h+var_A8], rbx
0x1800137c9  mov     r8, rbx
0x1800137cc  lea     rcx, [rax+rax*2]
0x1800137d0  shl     rcx, 3; dwBytes
0x1800137d4  call    WfpMemAlloc
0x1800137d9  mov     [rsp+170h+lpString2], rax
0x1800137de  test    rax, rax
0x1800137e1  jz      loc_180013A33
0x1800137e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800137ee  lea     rax, WPP_GLOBAL_Control
0x1800137f5  lea     rbx, aWfpmemallocarr; "WfpMemAllocArray"
0x1800137fc  cmp     rcx, rax
0x1800137ff  jz      loc_1800139BA
0x180013805  cmp     byte ptr [rcx+19h], 2
0x180013809  jb      loc_1800139BA
0x18001380f  test    byte ptr [rcx+1Ch], 1
0x180013813  mov     r13, [rsp+170h+lpString2]
0x180013818  jz      short loc_180013835
0x18001381a  mov     rcx, [rcx+10h]
0x18001381e  mov     edx, 1Ah
0x180013823  mov     dword ptr [rsp+170h+var_148], r13d
0x180013828  xor     r9d, r9d
0x18001382b  mov     [rsp+170h+StringSecurityDescriptorLen], rbx
0x180013830  call    WPP_SF_Ssd
0x180013835  cmp     cs:gWfpLogUserModeErrors, 0
0x18001383c  jnz     loc_1800139CC
0x180013842  xor     r12d, r12d
0x180013845  mov     rdi, [rsp+170h+var_110]
0x18001384a  mov     r15, [rbp+70h+var_F0]
0x18001384e  test    rdi, rdi
0x180013851  jz      short loc_18001385B
0x180013853  mov     rcx, rdi
0x180013856  call    BfeDestroyInner_FWPS_FILTER3
0x18001385b  lea     rcx, [rbp+70h+var_C8]
0x18001385f  call    WfpMemFree
0x180013864  jmp     loc_180013E51
0x180013869  cmp     cx, r12w
0x18001386d  jbe     loc_180013649
0x180013873  mov     rax, [rax+8]
0x180013877  movzx   ecx, r12w
0x18001387b  inc     r12w
0x18001387f  movzx   eax, word ptr [rax]
0x180013882  mov     word ptr [rbp+rcx*2+70h+var_70], ax
0x180013887  mov     ecx, 4
0x18001388c  jmp     loc_180013644
0x180013891  lea     rbx, aBfelayerlookup; "BfeLayerLookupConditionInfo"
0x180013898  jmp     loc_180013771
0x18001389d  test    cs:byte_1800F30F5, 1
0x1800138a4  jz      loc_18001377E
0x1800138aa  lea     rax, [rsp+170h+var_118]
0x1800138af  mov     dword ptr [rsp+170h+var_118], edi
0x1800138b3  mov     [rbp+70h+var_48], rax
0x1800138b7  lea     rdx, WFP_USERMODE_ERROR
0x1800138be  lea     rax, [rbp+70h+var_68]
0x1800138c2  mov     qword ptr [rbp+70h+var_58], rbx
0x1800138c6  mov     r9d, 3
0x1800138cc  mov     [rsp+170h+StringSecurityDescriptorLen], rax
0x1800138d1  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x1800138d8  mov     qword ptr [rbp+70h+var_58+8], 1Ch
0x1800138e0  mov     [rbp+70h+var_40], 4
0x1800138e8  call    McGenEventWrite_EtwEventWriteTransfer
0x1800138ed  jmp     loc_18001377E
0x1800138f2  lea     r8, [rbp+70h+var_C8]
0x1800138f6  mov     ecx, 40h ; '@'; dwBytes
0x1800138fb  call    WfpMemAlloc25B
0x180013900  mov     rdi, [rbp+70h+var_C8]
0x180013904  mov     [rsp+170h+var_110], rdi
0x180013909  mov     [rsp+170h+lpString2], rax
0x18001390e  jmp     loc_180013573
0x180013913  call    Feature_IndexTrie__private_ReportDeviceUsage
0x180013918  mov     edx, 8
0x18001391d  lea     r9, [rbp+70h+var_C0]
0x180013921  mov     r8d, edx
0x180013924  mov     rcx, rbx
0x180013927  call    WfpMemAllocArray
0x18001392c  mov     r14, [rbp+70h+var_C0]
0x180013930  mov     r13, rax
0x180013933  test    rax, rax
0x180013936  jnz     loc_180013842
0x18001393c  mov     r15, [rbp+70h+var_E0]
0x180013940  lea     rax, [rbp+70h+var_E8]
0x180013944  mov     r9, [rbp+70h+var_B0]
0x180013948  lea     rcx, [rbp+70h+var_70]
0x18001394c  mov     [rsp+40h], rax
0x180013951  mov     r8, r15
0x180013954  lea     rax, [rbp+70h+var_B8]
0x180013958  mov     dword ptr [rsp+170h+var_118], ebx
0x18001395c  mov     [rsp+170h+var_138], rax
0x180013961  movzx   edx, r12w
0x180013965  lea     rax, [rsp+170h+var_118]
0x18001396a  mov     [rsp+170h+lpMem], r14
0x18001396f  mov     [rsp+170h+var_140], rax
0x180013974  mov     [rsp+170h+StringSecurityDescriptorLen], r14
0x180013979  call    BfeGenerateConditionsForTrie
0x18001397e  mov     esi, dword ptr [rsp+170h+var_118]
0x180013982  mov     r13, rax
0x180013985  mov     rdi, [rsp+170h+var_110]
0x18001398a  test    rax, rax
0x18001398d  jnz     loc_180014585
0x180013993  mov     rax, [rbp+70h+var_B8]
0x180013997  mov     r12d, [rbp+70h+var_E8]
0x18001399b  mov     r13, rax
0x18001399e  mov     [rbp+70h+var_F0], rax
0x1800139a2  mov     [rbp+70h+var_D0], rax
0x1800139a6  mov     [rsp+170h+var_100], r12d
0x1800139ab  jmp     loc_1800137AF
  ... truncated ...
```
