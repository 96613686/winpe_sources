# GetPackageDetail(void *,ushort const *,tagPACKAGEDETAIL *)

- ea: `0x180026fd0`
- end: `0x180027a50`
- name: `?GetPackageDetail@@YAJPEAXPEBGPEAUtagPACKAGEDETAIL@@@Z`
- size: `2688`
- prototype: `__int64 __fastcall(void *, const unsigned __int16 *, struct tagPACKAGEDETAIL *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180022610`
- `0x1800226f0`

## callees

- `0x180002024`
- `0x180002aa0`
- `0x18001bf20`
- `0x18001e754`
- `0x18001e82c`
- `0x180024218`
- `0x180024b90`
- `0x180024ea0`
- `0x180024f20`
- `0x180026fd0`
- `0x180027e90`
- `0x18002ada8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180027502`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800277e3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800278e9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180027502`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800277e3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x1800278e9`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800278d1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800278d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027631`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002795e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027a02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027631`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002795e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027a02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002704a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027470`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027558`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800275d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002768e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002778e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800278a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002790a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800279c3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002704a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027470`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027558`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800275d1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002768e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002778e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800278a6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002790a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800279c3`
- `adsldpc!ADSIGetObjectAttributes` at `0x180027033`
- `adsldpc!ADSIGetObjectAttributes` at `0x180027033`
- `adsldpc!FreeADsMem` at `0x180027a30`
- `adsldpc!FreeADsMem` at `0x180027a30`
- `KERNEL32!lstrcmpW` at `0x18002771e`
- `KERNEL32!lstrcmpW` at `0x18002771e`

## string_xrefs

- `0x1800271bc`: `lastUpdateSequence`
- `0x1800276b4`: `cOMClassID`
- `0x1800270af`: `msiScriptPath`
- `0x1800273a3`: `installUiLevel`
- `0x18002783f`: `msiFileList`
- `0x180027134`: `setupCommand`
- `0x1800270f8`: `msiScriptSize`

## pseudocode

```c
__int64 __fastcall GetPackageDetail(void *a1, const unsigned __int16 *a2, struct tagPACKAGEDETAIL *a3)
{
  _DWORD *v5; // r14
  __int64 result; // rax
  char *v7; // rax
  char *v8; // rdi
  int v9; // ebx
  unsigned int PropertyFromAttr; // eax
  __int64 v11; // rax
  int v12; // ecx
  unsigned int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // rcx
  __int128 v16; // xmm1
  unsigned int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // edx
  __int64 v21; // rcx
  __int128 v22; // xmm1
  unsigned int v23; // eax
  unsigned int v24; // edx
  __int64 v25; // rcx
  __int128 v26; // xmm1
  unsigned int v27; // eax
  __int64 v28; // rax
  const unsigned __int16 *v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rdx
  unsigned int v32; // eax
  __int64 v33; // rdx
  unsigned int v34; // eax
  __int64 v35; // rdx
  unsigned int v36; // eax
  __int64 v37; // rax
  unsigned int v38; // eax
  __int64 v39; // rax
  unsigned int v40; // eax
  __int64 v41; // rax
  unsigned int v42; // ecx
  int v43; // ebx
  unsigned int v44; // eax
  __int64 v45; // rax
  unsigned int v46; // eax
  __int64 v47; // rax
  int v48; // ecx
  unsigned int v49; // eax
  unsigned int *v50; // r14
  __int64 v51; // rcx
  __int128 v52; // xmm1
  void *v53; // rcx
  unsigned int v54; // r15d
  _QWORD *v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r12
  __int64 v58; // rcx
  __int64 v59; // r13
  __int64 v60; // rbx
  unsigned int *v61; // rax
  unsigned int *v62; // rbx
  unsigned int v63; // eax
  __int64 v64; // rcx
  __int128 v65; // xmm1
  HLOCAL v66; // rax
  unsigned int i; // r10d
  __int64 v68; // r8
  __int64 v69; // rax
  __int64 v70; // r9
  unsigned int v71; // edx
  unsigned int v72; // eax
  __int64 v73; // rcx
  __int128 v74; // xmm1
  _DWORD *v75; // rax
  _DWORD *v76; // rdi
  unsigned int v77; // eax
  __int64 v78; // rax
  __int128 v79; // xmm1
  unsigned int v80; // eax
  unsigned int v81; // ebx
  __int64 v82; // rcx
  __int128 v83; // xmm1
  HLOCAL v84; // rax
  unsigned int j; // r14d
  __int64 v86; // rax
  __int64 v87; // rdx
  __int64 v88; // r15
  __int64 v89; // r8
  unsigned int v90; // eax
  unsigned int v91; // eax
  __int64 v92; // rcx
  __int128 v93; // xmm1
  unsigned int v94; // eax
  unsigned int v95; // edx
  _DWORD *v96; // rbx
  __int64 v97; // rcx
  __int128 v98; // xmm1
  const wchar_t **v99; // r15
  HLOCAL v100; // rax
  int v101; // r14d
  wchar_t *v102; // rbx
  __int64 v103; // rdi
  __int64 v104; // rdx
  unsigned __int16 *v105; // rcx
  __int64 v106; // rdx
  unsigned int v107; // eax
  __int64 v108; // rcx
  __int128 v109; // xmm1
  unsigned int v110; // ebx
  HLOCAL v111; // rax
  const unsigned __int16 **v112; // r14
  unsigned int v113; // edi
  LPVOID pMem; // [rsp+30h] [rbp-40h] BYREF
  HLOCAL v115; // [rsp+38h] [rbp-38h] BYREF
  wchar_t *EndPtr; // [rsp+40h] [rbp-30h] BYREF
  wchar_t *v117; // [rsp+48h] [rbp-28h] BYREF
  __int128 v118; // [rsp+50h] [rbp-20h] BYREF
  __int128 v119; // [rsp+60h] [rbp-10h]
  unsigned int v120; // [rsp+B8h] [rbp+48h] BYREF
  int v121; // [rsp+BCh] [rbp+4Ch]
  HLOCAL hMem; // [rsp+C8h] [rbp+58h] BYREF

  v121 = HIDWORD(a2);
  v117 = 0;
  v115 = 0;
  pMem = 0;
  v120 = 0;
  v5 = 0;
  memset_0(a3, 0, 0x48u);
  result = ADSIGetObjectAttributes(a1, &pszPackageDetailAttrNames, 22, &pMem, &v120);
  if ( (int)result < 0 )
    return result;
  v7 = (char *)LocalAlloc(0, 0x88u);
  *((_QWORD *)a3 + 8) = v7;
  v8 = v7;
  if ( !v7 )
    goto LABEL_3;
  memset_0(v7, 0, 0x88u);
  PropertyFromAttr = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"packageFlags");
  if ( PropertyFromAttr >= v120 )
    goto LABEL_110;
  v11 = 32LL * PropertyFromAttr;
  if ( *(_DWORD *)((char *)pMem + v11 + 24) )
    v12 = *(_DWORD *)(*(_QWORD *)((char *)pMem + v11 + 16) + 8LL);
  else
    v12 = 0;
  *(_DWORD *)v8 = v12;
  v13 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"msiScriptPath");
  v14 = v120;
  if ( v13 < v120 )
  {
    v15 = 32LL * v13;
    v16 = *(_OWORD *)((char *)pMem + v15 + 16);
    v118 = *(_OWORD *)((char *)pMem + v15);
    v119 = v16;
    UnpackStrAllocFrom<_ads_attr_info>((__int64)&v118, (HLOCAL *)v8 + 1);
    v14 = v120;
  }
  v17 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v14, L"msiScriptSize");
  if ( v17 < v120 )
  {
    v18 = 32LL * v17;
    if ( *(_DWORD *)((char *)pMem + v18 + 24) )
      *((_DWORD *)v8 + 32) = *(_DWORD *)(*(_QWORD *)((char *)pMem + v18 + 16) + 8LL);
    else
      *((_DWORD *)v8 + 32) = 0;
  }
  v19 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"setupCommand");
  v20 = v120;
  if ( v19 < v120 )
  {
    v21 = 32LL * v19;
    v22 = *(_OWORD *)((char *)pMem + v21 + 16);
    v118 = *(_OWORD *)((char *)pMem + v21);
    v119 = v22;
    UnpackStrAllocFrom<_ads_attr_info>((__int64)&v118, (HLOCAL *)v8 + 2);
    v20 = v120;
  }
  v23 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v20, L"url");
  v24 = v120;
  if ( v23 < v120 )
  {
    v25 = 32LL * v23;
    v26 = *(_OWORD *)((char *)pMem + v25 + 16);
    v118 = *(_OWORD *)((char *)pMem + v25);
    v119 = v26;
    UnpackStrAllocFrom<_ads_attr_info>((__int64)&v118, (HLOCAL *)v8 + 3);
    v24 = v120;
  }
  v27 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v24, L"lastUpdateSequence");
  if ( v27 >= v120 )
    goto LABEL_110;
  v28 = 32LL * v27;
  if ( *(_DWORD *)((char *)pMem + v28 + 24) )
    v29 = *(const unsigned __int16 **)(*(_QWORD *)((char *)pMem + v28 + 16) + 8LL);
  else
    v29 = 0;
  TimeToUsn(v29, (struct _FILETIME *)v8 + 4);
  v30 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"productCode");
  if ( v30 < v120 )
  {
    v31 = 32LL * v30;
    if ( *(_DWORD *)((char *)pMem + v31 + 24) )
      memcpy_0(
        v8 + 56,
        *(const void **)(*(_QWORD *)((char *)pMem + v31 + 16) + 16LL),
        *(unsigned int *)(*(_QWORD *)((char *)pMem + v31 + 16) + 8LL));
    else
      *(_OWORD *)(v8 + 56) = 0;
  }
  v32 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"upgradeProductCode");
  if ( v32 < v120 )
  {
    v33 = 32LL * v32;
    if ( *(_DWORD *)((char *)pMem + v33 + 24) )
      memcpy_0(
        v8 + 88,
        *(const void **)(*(_QWORD *)((char *)pMem + v33 + 16) + 16LL),
        *(unsigned int *)(*(_QWORD *)((char *)pMem + v33 + 16) + 8LL));
    else
      *(_OWORD *)(v8 + 88) = 0;
  }
  v34 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"objectGUID");
  if ( v34 < v120 )
  {
    v35 = 32LL * v34;
    if ( *(_DWORD *)((char *)pMem + v35 + 24) )
      memcpy_0(
        v8 + 72,
        *(const void **)(*(_QWORD *)((char *)pMem + v35 + 16) + 16LL),
        *(unsigned int *)(*(_QWORD *)((char *)pMem + v35 + 16) + 8LL));
    else
      *(_OWORD *)(v8 + 72) = 0;
  }
  v36 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"versionNumberHi");
  if ( v36 < v120 )
  {
    v37 = 32LL * v36;
    if ( *(_DWORD *)((char *)pMem + v37 + 24) )
      *((_DWORD *)v8 + 26) = *(_DWORD *)(*(_QWORD *)((char *)pMem + v37 + 16) + 8LL);
    else
      *((_DWORD *)v8 + 26) = 0;
  }
  v38 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"versionNumberLo");
  if ( v38 < v120 )
  {
    v39 = 32LL * v38;
    if ( *(_DWORD *)((char *)pMem + v39 + 24) )
      *((_DWORD *)v8 + 27) = *(_DWORD *)(*(_QWORD *)((char *)pMem + v39 + 16) + 8LL);
    else
      *((_DWORD *)v8 + 27) = 0;
  }
  v40 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"revision");
  if ( v40 < v120 )
  {
    v41 = 32LL * v40;
    if ( *(_DWORD *)((char *)pMem + v41 + 24) )
      *((_DWORD *)v8 + 28) = *(_DWORD *)(*(_QWORD *)((char *)pMem + v41 + 16) + 8LL);
    else
      *((_DWORD *)v8 + 28) = 0;
  }
  v42 = *(_DWORD *)v8;
  if ( (*(_DWORD *)v8 & 0x10) != 0 )
  {
    *((_DWORD *)v8 + 1) = v42 >> 29;
    v43 = (v42 & 0x80000) != 0 ? 3 : 5;
  }
  else
  {
    v43 = 0;
    v44 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"installUiLevel");
    if ( v44 < v120 )
    {
      v45 = 32LL * v44;
      if ( *(_DWORD *)((char *)pMem + v45 + 24) )
        v43 = *(_DWORD *)(*(_QWORD *)((char *)pMem + v45 + 16) + 8LL);
    }
    v46 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"packageType");
    if ( v46 >= v120 )
      goto LABEL_110;
    v47 = 32LL * v46;
    v48 = *(_DWORD *)((char *)pMem + v47 + 24) ? *(_DWORD *)(*(_QWORD *)((char *)pMem + v47 + 16) + 8LL) : 0;
    *((_DWORD *)v8 + 1) = v48;
  }
  *((_DWORD *)v8 + 10) = v43;
  v49 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"canUpgradeScript");
  if ( v49 < v120 )
  {
    v50 = (unsigned int *)(v8 + 116);
    v51 = 32LL * v49;
    hMem = 0;
    v52 = *(_OWORD *)((char *)pMem + v51 + 16);
    v118 = *(_OWORD *)((char *)pMem + v51);
    v119 = v52;
    UnpackStrArrAllocFrom<ads_search_column>(&v118, &hMem, v8 + 116);
    if ( *((_DWORD *)v8 + 29) )
      *((_QWORD *)v8 + 15) = LocalAlloc(0, 48LL * *v50);
    v53 = (void *)*((_QWORD *)v8 + 15);
    if ( !v53 )
      goto LABEL_3;
    memset_0(v53, 0, 48LL * *v50);
    v54 = 0;
    if ( *v50 )
    {
      v55 = hMem;
      do
      {
        v56 = *((_QWORD *)v8 + 15);
        EndPtr = 0;
        v57 = 48LL * v54;
        *(_QWORD *)(v57 + v56) = v55[v54];
        v58 = -1;
        v59 = *(_QWORD *)(v57 + *((_QWORD *)v8 + 15));
        do
          ++v58;
        while ( *(_WORD *)(v59 + 2 * v58) );
        if ( (unsigned int)v58 > 0x29 )
        {
          v60 = (unsigned int)v58;
          *(_WORD *)(v59 + 2LL * (unsigned int)v58 - 6) = 0;
          *(_DWORD *)(v57 + *((_QWORD *)v8 + 15) + 40) = wcstoul(
                                                           (const wchar_t *)(v59 + 2LL * (unsigned int)(v58 - 2)),
                                                           &EndPtr,
                                                           16);
          *(_WORD *)(v59 + 2 * v60 - 82) = 0;
          GUIDFromString(
            (const unsigned __int16 *)(v59 + 2 * v60 - 78),
            (struct _GUID *)(v57 + *((_QWORD *)v8 + 15) + 8LL));
          v55 = hMem;
        }
        ++v54;
      }
      while ( v54 < *v50 );
    }
    *v50 = v54;
    v5 = v117;
  }
  v61 = (unsigned int *)LocalAlloc(0, 0x20u);
  *((_QWORD *)a3 + 7) = v61;
  v62 = v61;
  if ( !v61 )
    goto LABEL_3;
  *(_OWORD *)v61 = 0;
  *((_OWORD *)v61 + 1) = 0;
  v63 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"machineArchitecture");
  if ( v63 < v120 )
  {
    v64 = 32LL * v63;
    LODWORD(hMem) = 0;
    v65 = *(_OWORD *)((char *)pMem + v64 + 16);
    v118 = *(_OWORD *)((char *)pMem + v64);
    v119 = v65;
    UnpackDWArrFrom<ads_search_column>(&v118, &v115, &hMem);
    v5 = v115;
    *v62 = (unsigned int)hMem;
  }
  v66 = LocalAlloc(0, 16LL * *v62);
  *((_QWORD *)v62 + 1) = v66;
  if ( !v66 )
    goto LABEL_3;
  for ( i = 0; i < *v62; *(_DWORD *)(v68 + 8 * v70 + 12) = HIBYTE(v71) )
  {
    v68 = *((_QWORD *)v62 + 1);
    v69 = i;
    v70 = i++;
    v70 *= 2;
    v71 = v5[v69];
    *(_DWORD *)(v68 + 8 * v70) = (unsigned __int8)v71;
    *(_DWORD *)(v68 + 8 * v70 + 4) = BYTE1(v71);
    *(_DWORD *)(v68 + 8 * v70 + 8) = BYTE2(v71);
  }
  LocalFree(v5);
  v72 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"localeID");
  if ( v72 < v120 )
  {
    v73 = 32LL * v72;
    LODWORD(hMem) = 0;
    v74 = *(_OWORD *)((char *)pMem + v73 + 16);
    v118 = *(_OWORD *)((char *)pMem + v73);
    v119 = v74;
    UnpackDWArrFrom<ads_search_column>(&v118, v62 + 6, &hMem);
    v62[4] = (unsigned int)hMem;
  }
  v75 = LocalAlloc(0, 0x50u);
  *((_QWORD *)a3 + 6) = v75;
  v76 = v75;
  if ( !v75 )
    goto LABEL_3;
  memset_0(v75, 0, 0x50u);
  v77 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"cOMClassID");
  v76[18] = 1;
  if ( v77 < v120 && *((_DWORD *)pMem + 6) == 1 )
  {
    v78 = 32LL * v77;
    v115 = 0;
    v79 = *(_OWORD *)((char *)pMem + v78 + 16);
    v118 = *(_OWORD *)((char *)pMem + v78);
    v119 = v79;
    v9 = UnpackStrArrFrom<_ads_attr_info>((__int64)&v118, &v115, (unsigned int *)&hMem);
    if ( v9 < 0 )
      goto LABEL_111;
    if ( !lstrcmpW(*(LPCWSTR *)v115, L"00000000-0000-0000-0000-000000000000:0") )
      v76[18] = 0;
  }
  v80 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"fileExtPriority");
  v81 = 0;
  LODWORD(hMem) = 0;
  if ( v80 < v120 )
  {
    v82 = 32LL * v80;
    v83 = *(_OWORD *)((char *)pMem + v82 + 16);
    v118 = *(_OWORD *)((char *)pMem + v82);
    v119 = v83;
    UnpackStrArrAllocFrom<ads_search_column>(&v118, v76 + 6, &hMem);
    v81 = (unsigned int)hMem;
  }
  v76[4] = v81;
  if ( v81 )
  {
    v84 = LocalAlloc(0, 4LL * v81);
    *((_QWORD *)v76 + 4) = v84;
    if ( !v84 )
      goto LABEL_3;
    for ( j = 0; j < v81; ++j )
    {
      v86 = *((_QWORD *)v76 + 3);
      v87 = -1;
      v88 = j;
      hMem = 0;
      v89 = *(_QWORD *)(v86 + 8LL * j);
      do
        ++v87;
      while ( *(_WORD *)(v89 + 2 * v87) );
      *(_WORD *)(v89 + 2LL * (unsigned int)(v87 - 3)) = 0;
      v90 = wcstoul(
              (const wchar_t *)(*(_QWORD *)(*((_QWORD *)v76 + 3) + 8LL * j) + 2LL * (unsigned int)(v87 - 2)),
              (wchar_t **)&hMem,
              10);
      *(_DWORD *)(*((_QWORD *)v76 + 4) + 4 * v88) = v90;
    }
  }
  v91 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"packageName");
  if ( v91 >= v120 )
  {
LABEL_110:
    v9 = -2147221143;
    goto LABEL_111;
  }
  v92 = 32LL * v91;
  v93 = *(_OWORD *)((char *)pMem + v92 + 16);
  v118 = *(_OWORD *)((char *)pMem + v92);
  v119 = v93;
  UnpackStrAllocFrom<_ads_attr_info>((__int64)&v118, (HLOCAL *)a3);
  v94 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v120, L"msiFileList");
  v95 = v120;
  if ( v94 < v120 )
  {
    v96 = (_DWORD *)((char *)a3 + 16);
    v97 = 32LL * v94;
    v117 = 0;
    hMem = 0;
    v98 = *(_OWORD *)((char *)pMem + v97 + 16);
    v118 = *(_OWORD *)((char *)pMem + v97);
    v119 = v98;
    UnpackStrArrFrom<_ads_attr_info>((__int64)&v118, &hMem, (unsigned int *)a3 + 4);
    v99 = (const wchar_t **)hMem;
    if ( *((_DWORD *)a3 + 4) )
    {
      v100 = LocalAlloc(0, 8LL * (unsigned int)*v96);
      *((_QWORD *)a3 + 3) = v100;
      if ( !v100 )
        goto LABEL_3;
      v101 = 0;
      if ( *v96 )
      {
        do
        {
          v102 = wcschr(v99[v101], 0x3Au);
          *v102 = 0;
          v103 = wcstoul(v99[v101], &v117, 10);
          v104 = -1;
          do
            ++v104;
          while ( v102[v104 + 1] );
          *(_QWORD *)(*((_QWORD *)a3 + 3) + 8 * v103) = LocalAlloc(0, 2 * v104 + 2);
          v105 = *(unsigned __int16 **)(*((_QWORD *)a3 + 3) + 8 * v103);
          if ( !v105 )
            goto LABEL_3;
          v106 = -1;
          do
            ++v106;
          while ( v102[v106 + 1] );
          v9 = StringCchCopyW(v105, v106 + 1, v102 + 1);
          if ( v9 < 0 )
            goto LABEL_111;
        }
        while ( (unsigned int)++v101 < *((_DWORD *)a3 + 4) );
      }
    }
    LocalFree(v99);
    v95 = v120;
  }
  v107 = GetPropertyFromAttr((struct _ads_attr_info *)pMem, v95, L"categories");
  LODWORD(hMem) = 0;
  v115 = 0;
  if ( v107 >= v120 )
    return 0;
  v108 = 32LL * v107;
  v109 = *(_OWORD *)((char *)pMem + v108 + 16);
  v118 = *(_OWORD *)((char *)pMem + v108);
  v119 = v109;
  UnpackStrArrFrom<_ads_attr_info>((__int64)&v118, &v115, (unsigned int *)&hMem);
  v110 = (unsigned int)hMem;
  if ( !(_DWORD)hMem )
    return 0;
  v111 = LocalAlloc(0, 16LL * (unsigned int)hMem);
  *((_QWORD *)a3 + 5) = v111;
  if ( v111 )
  {
    v112 = (const unsigned __int16 **)v115;
    v113 = 0;
    for ( *((_DWORD *)a3 + 8) = v110; v113 < v110; ++v113 )
      GUIDFromString(v112[v113], (struct _GUID *)(*((_QWORD *)a3 + 5) + 16LL * v113));
    LocalFree(v112);
    return 0;
  }
LABEL_3:
  v9 = -2147024882;
LABEL_111:
  ReleasePackageDetail(a3);
  memset_0(a3, 0, 0x48u);
  if ( pMem )
    FreeADsMem(pMem);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180026fd0  mov     [rsp-38h+arg_0], rbx
0x180026fd5  mov     qword ptr [rsp-38h+arg_8], rdx
0x180026fda  push    rbp
0x180026fdb  push    rsi
0x180026fdc  push    rdi
0x180026fdd  push    r12
0x180026fdf  push    r13
0x180026fe1  push    r14
0x180026fe3  push    r15
0x180026fe5  mov     rbp, rsp
0x180026fe8  sub     rsp, 70h
0x180026fec  xor     r12d, r12d
0x180026fef  mov     rsi, r8
0x180026ff2  mov     rbx, rcx
0x180026ff5  mov     [rbp+var_28], r12
0x180026ff9  xor     edx, edx; Val
0x180026ffb  mov     [rbp+var_38], r12
0x180026fff  mov     rcx, rsi; void *
0x180027002  mov     [rbp+pMem], r12
0x180027006  lea     r8d, [r12+48h]; Size
0x18002700b  mov     [rbp+arg_8], r12d
0x18002700f  mov     r14d, r12d
0x180027012  call    memset_0
0x180027017  lea     rax, [rbp+arg_8]
0x18002701b  mov     rcx, rbx
0x18002701e  lea     r9, [rbp+pMem]
0x180027022  mov     [rsp+70h+var_50], rax
0x180027027  lea     r8d, [r12+16h]
0x18002702c  lea     rdx, ?pszPackageDetailAttrNames@@3PAPEAGA; ushort * near * pszPackageDetailAttrNames
0x180027033  call    cs:__imp_ADSIGetObjectAttributes
0x180027039  test    eax, eax
0x18002703b  js      loc_180027A38
0x180027041  mov     ebx, 88h
0x180027046  xor     ecx, ecx; uFlags
0x180027048  mov     edx, ebx; uBytes
0x18002704a  call    cs:__imp_LocalAlloc
0x180027050  mov     [rsi+40h], rax
0x180027054  mov     rdi, rax
0x180027057  test    rax, rax
0x18002705a  jnz     short loc_180027066
0x18002705c  mov     ebx, 8007000Eh
0x180027061  jmp     loc_180027A11
0x180027066  mov     r8, rbx; Size
0x180027069  xor     edx, edx; Val
0x18002706b  mov     rcx, rdi; void *
0x18002706e  call    memset_0
0x180027073  mov     edx, [rbp+arg_8]; unsigned int
0x180027076  lea     r8, aPackageflags; "packageFlags"
0x18002707d  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x180027081  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180027086  cmp     eax, [rbp+arg_8]
0x180027089  jnb     loc_180027A0C
0x18002708f  mov     rcx, [rbp+pMem]
0x180027093  mov     eax, eax
0x180027095  shl     rax, 5
0x180027099  cmp     [rax+rcx+18h], r12d
0x18002709e  jz      short loc_1800270AA
0x1800270a0  mov     rax, [rax+rcx+10h]
0x1800270a5  mov     ecx, [rax+8]
0x1800270a8  jmp     short loc_1800270AD
0x1800270aa  mov     ecx, r12d
0x1800270ad  mov     [rdi], ecx
0x1800270af  lea     r8, aMsiscriptpath; "msiScriptPath"
0x1800270b6  mov     edx, [rbp+arg_8]; unsigned int
0x1800270b9  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x1800270bd  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x1800270c2  mov     edx, [rbp+arg_8]
0x1800270c5  cmp     eax, edx
0x1800270c7  jnb     short loc_1800270F4
0x1800270c9  mov     ecx, eax
0x1800270cb  lea     rdx, [rdi+8]
0x1800270cf  mov     rax, [rbp+pMem]
0x1800270d3  shl     rcx, 5
0x1800270d7  movups  xmm0, xmmword ptr [rcx+rax]
0x1800270db  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x1800270e0  lea     rcx, [rbp+var_20]
0x1800270e4  movaps  [rbp+var_20], xmm0
0x1800270e8  movaps  [rbp+var_10], xmm1
0x1800270ec  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x1800270f1  mov     edx, [rbp+arg_8]; unsigned int
0x1800270f4  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x1800270f8  lea     r8, aMsiscriptsize; "msiScriptSize"
0x1800270ff  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180027104  cmp     eax, [rbp+arg_8]
0x180027107  jnb     short loc_180027131
0x180027109  mov     rcx, [rbp+pMem]
0x18002710d  mov     eax, eax
0x18002710f  shl     rax, 5
0x180027113  cmp     [rax+rcx+18h], r12d
0x180027118  jz      short loc_18002712A
0x18002711a  mov     rax, [rax+rcx+10h]
0x18002711f  mov     ecx, [rax+8]
0x180027122  mov     [rdi+80h], ecx
0x180027128  jmp     short loc_180027131
0x18002712a  mov     [rdi+80h], r12d
0x180027131  mov     edx, [rbp+arg_8]; unsigned int
0x180027134  lea     r8, aSetupcommand; "setupCommand"
0x18002713b  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x18002713f  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180027144  mov     edx, [rbp+arg_8]
0x180027147  cmp     eax, edx
0x180027149  jnb     short loc_180027176
0x18002714b  mov     ecx, eax
0x18002714d  lea     rdx, [rdi+10h]
0x180027151  mov     rax, [rbp+pMem]
0x180027155  shl     rcx, 5
0x180027159  movups  xmm0, xmmword ptr [rcx+rax]
0x18002715d  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x180027162  lea     rcx, [rbp+var_20]
0x180027166  movaps  [rbp+var_20], xmm0
0x18002716a  movaps  [rbp+var_10], xmm1
0x18002716e  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x180027173  mov     edx, [rbp+arg_8]; unsigned int
0x180027176  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x18002717a  lea     r8, aUrl; "url"
0x180027181  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180027186  mov     edx, [rbp+arg_8]
0x180027189  cmp     eax, edx
0x18002718b  jnb     short loc_1800271B8
0x18002718d  mov     ecx, eax
0x18002718f  lea     rdx, [rdi+18h]
0x180027193  mov     rax, [rbp+pMem]
0x180027197  shl     rcx, 5
0x18002719b  movups  xmm0, xmmword ptr [rcx+rax]
0x18002719f  movups  xmm1, xmmword ptr [rcx+rax+10h]
0x1800271a4  lea     rcx, [rbp+var_20]
0x1800271a8  movaps  [rbp+var_20], xmm0
0x1800271ac  movaps  [rbp+var_10], xmm1
0x1800271b0  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x1800271b5  mov     edx, [rbp+arg_8]; unsigned int
0x1800271b8  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x1800271bc  lea     r8, aLastupdatesequ; "lastUpdateSequence"
0x1800271c3  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x1800271c8  cmp     eax, [rbp+arg_8]
0x1800271cb  jnb     loc_180027A0C
0x1800271d1  mov     rcx, [rbp+pMem]
0x1800271d5  mov     eax, eax
0x1800271d7  shl     rax, 5
0x1800271db  cmp     [rax+rcx+18h], r12d
0x1800271e0  jz      short loc_1800271ED
0x1800271e2  mov     rax, [rax+rcx+10h]
0x1800271e7  mov     rcx, [rax+8]
0x1800271eb  jmp     short loc_1800271F0
0x1800271ed  mov     rcx, r12; unsigned __int16 *
0x1800271f0  lea     rdx, [rdi+20h]; struct _FILETIME *
0x1800271f4  call    ?TimeToUsn@@YAXPEBGPEAU_FILETIME@@@Z; TimeToUsn(ushort const *,_FILETIME *)
0x1800271f9  mov     edx, [rbp+arg_8]; unsigned int
0x1800271fc  lea     r8, aProductcode; "productCode"
0x180027203  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x180027207  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18002720c  cmp     eax, [rbp+arg_8]
0x18002720f  jnb     short loc_180027241
0x180027211  mov     rcx, [rbp+pMem]
0x180027215  mov     edx, eax
0x180027217  shl     rdx, 5
0x18002721b  cmp     [rdx+rcx+18h], r12d
0x180027220  jz      short loc_18002723A
0x180027222  mov     rdx, [rdx+rcx+10h]
0x180027227  lea     rcx, [rdi+38h]; void *
0x18002722b  mov     r8d, [rdx+8]; Size
0x18002722f  mov     rdx, [rdx+10h]; Src
0x180027233  call    memcpy_0
0x180027238  jmp     short loc_180027241
0x18002723a  xorps   xmm0, xmm0
0x18002723d  movups  xmmword ptr [rdi+38h], xmm0
0x180027241  mov     edx, [rbp+arg_8]; unsigned int
0x180027244  lea     r8, aUpgradeproduct; "upgradeProductCode"
0x18002724b  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x18002724f  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180027254  cmp     eax, [rbp+arg_8]
0x180027257  jnb     short loc_180027289
0x180027259  mov     rcx, [rbp+pMem]
0x18002725d  mov     edx, eax
0x18002725f  shl     rdx, 5
0x180027263  cmp     [rdx+rcx+18h], r12d
0x180027268  jz      short loc_180027282
0x18002726a  mov     rdx, [rdx+rcx+10h]
0x18002726f  lea     rcx, [rdi+58h]; void *
0x180027273  mov     r8d, [rdx+8]; Size
0x180027277  mov     rdx, [rdx+10h]; Src
0x18002727b  call    memcpy_0
0x180027280  jmp     short loc_180027289
0x180027282  xorps   xmm0, xmm0
0x180027285  movups  xmmword ptr [rdi+58h], xmm0
0x180027289  mov     edx, [rbp+arg_8]; unsigned int
0x18002728c  lea     r8, aObjectguid; "objectGUID"
0x180027293  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x180027297  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18002729c  cmp     eax, [rbp+arg_8]
0x18002729f  jnb     short loc_1800272D1
0x1800272a1  mov     rcx, [rbp+pMem]
0x1800272a5  mov     edx, eax
0x1800272a7  shl     rdx, 5
0x1800272ab  cmp     [rdx+rcx+18h], r12d
0x1800272b0  jz      short loc_1800272CA
0x1800272b2  mov     rdx, [rdx+rcx+10h]
0x1800272b7  lea     rcx, [rdi+48h]; void *
0x1800272bb  mov     r8d, [rdx+8]; Size
0x1800272bf  mov     rdx, [rdx+10h]; Src
0x1800272c3  call    memcpy_0
0x1800272c8  jmp     short loc_1800272D1
0x1800272ca  xorps   xmm0, xmm0
0x1800272cd  movups  xmmword ptr [rdi+48h], xmm0
0x1800272d1  mov     edx, [rbp+arg_8]; unsigned int
0x1800272d4  lea     r8, aVersionnumberh; "versionNumberHi"
0x1800272db  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x1800272df  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x1800272e4  cmp     eax, [rbp+arg_8]
0x1800272e7  jnb     short loc_18002730B
0x1800272e9  mov     rcx, [rbp+pMem]
0x1800272ed  mov     eax, eax
0x1800272ef  shl     rax, 5
0x1800272f3  cmp     [rax+rcx+18h], r12d
0x1800272f8  jz      short loc_180027307
0x1800272fa  mov     rax, [rax+rcx+10h]
0x1800272ff  mov     ecx, [rax+8]
0x180027302  mov     [rdi+68h], ecx
0x180027305  jmp     short loc_18002730B
0x180027307  mov     [rdi+68h], r12d
0x18002730b  mov     edx, [rbp+arg_8]; unsigned int
0x18002730e  lea     r8, aVersionnumberl; "versionNumberLo"
0x180027315  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x180027319  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x18002731e  cmp     eax, [rbp+arg_8]
0x180027321  jnb     short loc_180027345
0x180027323  mov     rcx, [rbp+pMem]
0x180027327  mov     eax, eax
0x180027329  shl     rax, 5
0x18002732d  cmp     [rax+rcx+18h], r12d
0x180027332  jz      short loc_180027341
0x180027334  mov     rax, [rax+rcx+10h]
0x180027339  mov     ecx, [rax+8]
0x18002733c  mov     [rdi+6Ch], ecx
0x18002733f  jmp     short loc_180027345
0x180027341  mov     [rdi+6Ch], r12d
0x180027345  mov     edx, [rbp+arg_8]; unsigned int
0x180027348  lea     r8, aRevision_0; "revision"
0x18002734f  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x180027353  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180027358  cmp     eax, [rbp+arg_8]
0x18002735b  jnb     short loc_18002737F
0x18002735d  mov     rcx, [rbp+pMem]
0x180027361  mov     eax, eax
0x180027363  shl     rax, 5
0x180027367  cmp     [rax+rcx+18h], r12d
0x18002736c  jz      short loc_18002737B
0x18002736e  mov     rax, [rax+rcx+10h]
0x180027373  mov     ecx, [rax+8]
0x180027376  mov     [rdi+70h], ecx
0x180027379  jmp     short loc_18002737F
0x18002737b  mov     [rdi+70h], r12d
0x18002737f  mov     ecx, [rdi]
0x180027381  test    cl, 10h
0x180027384  jz      short loc_1800273A0
0x180027386  mov     eax, ecx
0x180027388  and     ecx, 80000h
0x18002738e  shr     eax, 1Dh
0x180027391  neg     ecx
0x180027393  mov     [rdi+4], eax
0x180027396  sbb     ebx, ebx
0x180027398  and     ebx, 0FFFFFFFEh
0x18002739b  add     ebx, 5
0x18002739e  jmp     short loc_18002740C
0x1800273a0  mov     edx, [rbp+arg_8]; unsigned int
0x1800273a3  lea     r8, aInstalluilevel; "installUiLevel"
0x1800273aa  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x1800273ae  mov     ebx, r12d
0x1800273b1  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x1800273b6  mov     edx, [rbp+arg_8]; unsigned int
0x1800273b9  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x1800273bd  cmp     eax, edx
0x1800273bf  jnb     short loc_1800273D6
0x1800273c1  mov     eax, eax
0x1800273c3  shl     rax, 5
0x1800273c7  cmp     [rax+rcx+18h], r12d
0x1800273cc  jz      short loc_1800273D6
0x1800273ce  mov     rax, [rax+rcx+10h]
0x1800273d3  mov     ebx, [rax+8]
0x1800273d6  lea     r8, aPackagetype; "packageType"
0x1800273dd  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x1800273e2  cmp     eax, [rbp+arg_8]
0x1800273e5  jnb     loc_180027A0C
0x1800273eb  mov     rcx, [rbp+pMem]
0x1800273ef  mov     eax, eax
0x1800273f1  shl     rax, 5
0x1800273f5  cmp     [rax+rcx+18h], r12d
0x1800273fa  jz      short loc_180027406
0x1800273fc  mov     rax, [rax+rcx+10h]
0x180027401  mov     ecx, [rax+8]
0x180027404  jmp     short loc_180027409
0x180027406  mov     ecx, r12d
0x180027409  mov     [rdi+4], ecx
0x18002740c  mov     [rdi+28h], ebx
0x18002740f  lea     r8, aCanupgradescri; "canUpgradeScript"
0x180027416  mov     edx, [rbp+arg_8]; unsigned int
0x180027419  mov     rcx, [rbp+pMem]; struct _ads_attr_info *
0x18002741d  call    ?GetPropertyFromAttr@@YAKPEAU_ads_attr_info@@KPEBG@Z; GetPropertyFromAttr(_ads_attr_info *,ulong,ushort const *)
0x180027422  cmp     eax, [rbp+arg_8]
0x180027425  jnb     loc_180027551
0x18002742b  mov     ecx, eax
  ... truncated ...
```
