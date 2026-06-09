# FetchInstallData(void *,void *,tagQUERYCONTEXT *,__MIDL___MIDL_itf_wtypes_0000_0001_0001 *,ushort const *,ulong,ulong *,tagPACKAGEDISPINFO *,uint *,int,_GUID *,ushort const *)

- ea: `0x180025378`
- end: `0x180026039`
- name: `?FetchInstallData@@YAJPEAX0PEAUtagQUERYCONTEXT@@PEAU__MIDL___MIDL_itf_wtypes_0000_0001_0001@@PEBGKPEAKPEAUtagPACKAGEDISPINFO@@PEAIHPEAU_GUID@@3@Z`
- size: `3265`
- prototype: `__int64 __fastcall(void *, void *, struct tagQUERYCONTEXT *, struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *, wchar_t *, unsigned int, unsigned int *, struct tagPACKAGEDISPINFO *, unsigned int *, int, struct _GUID *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18001d240`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180002b14`
- `0x18001b1a0`
- `0x18001c0e0`
- `0x18001c204`
- `0x18001e71c`
- `0x18001e754`
- `0x1800234b0`
- `0x180024b90`
- `0x180024e04`
- `0x180024ea0`
- `0x180024f20`
- `0x180025094`
- `0x180025378`
- `0x180027a58`
- `0x180027e1c`
- `0x180027e90`
- `0x18002ad84`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18002571e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180025b38`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180025eb8`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18002571e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180025b38`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x180025eb8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800256d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025afc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ba8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800256d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025afc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180025ba8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025e2b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180025e2b`
- `adsldpc!ADSIGetNextRow` at `0x18002591d`
- `adsldpc!ADSIGetNextRow` at `0x18002591d`
- `adsldpc!ADSIGetFirstRow` at `0x18002542c`
- `adsldpc!ADSIGetFirstRow` at `0x18002542c`
- `adsldpc!ADSIFreeColumn` at `0x1800254b3`
- `adsldpc!ADSIFreeColumn` at `0x180025522`
- `adsldpc!ADSIFreeColumn` at `0x1800256cd`
- `adsldpc!ADSIFreeColumn` at `0x1800257b1`
- `adsldpc!ADSIFreeColumn` at `0x18002599e`
- `adsldpc!ADSIFreeColumn` at `0x180025a05`
- `adsldpc!ADSIFreeColumn` at `0x180025b5a`
- `adsldpc!ADSIFreeColumn` at `0x180025bbb`
- `adsldpc!ADSIFreeColumn` at `0x180025c1b`
- `adsldpc!ADSIFreeColumn` at `0x180025c79`
- `adsldpc!ADSIFreeColumn` at `0x180025cc4`
- `adsldpc!ADSIFreeColumn` at `0x180025d0a`
- `adsldpc!ADSIFreeColumn` at `0x180025d50`
- `adsldpc!ADSIFreeColumn` at `0x180025dab`
- `adsldpc!ADSIFreeColumn` at `0x180025f12`
- `adsldpc!ADSIFreeColumn` at `0x1800254b3`
- `adsldpc!ADSIFreeColumn` at `0x180025522`
- `adsldpc!ADSIFreeColumn` at `0x1800256cd`
- `adsldpc!ADSIFreeColumn` at `0x1800257b1`
- `adsldpc!ADSIFreeColumn` at `0x18002599e`
- `adsldpc!ADSIFreeColumn` at `0x180025a05`
- `adsldpc!ADSIFreeColumn` at `0x180025b5a`
- `adsldpc!ADSIFreeColumn` at `0x180025bbb`
- `adsldpc!ADSIFreeColumn` at `0x180025c1b`
- `adsldpc!ADSIFreeColumn` at `0x180025c79`
- `adsldpc!ADSIFreeColumn` at `0x180025cc4`
- `adsldpc!ADSIFreeColumn` at `0x180025d0a`
- `adsldpc!ADSIFreeColumn` at `0x180025d50`
- `adsldpc!ADSIFreeColumn` at `0x180025dab`
- `adsldpc!ADSIFreeColumn` at `0x180025f12`

## string_xrefs

- `0x180025bd7`: `lastUpdateSequence`
- `0x180025f94`: `lastUpdateSequence`
- `0x180025a2a`: `cOMClassID`
- `0x1800259b7`: `msiScriptPath`

## pseudocode

```c
__int64 __fastcall FetchInstallData(
        void *a1,
        void *a2,
        struct tagQUERYCONTEXT *a3,
        struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *a4,
        wchar_t *a5,
        unsigned int a6,
        unsigned int *a7,
        struct tagPACKAGEDISPINFO *a8,
        unsigned int *a9,
        int a10,
        struct _GUID *a11,
        unsigned __int16 *a12)
{
  struct tagPACKAGEDISPINFO *v12; // rdi
  unsigned int *v13; // rbx
  void *v14; // r12
  unsigned int *v15; // r14
  void *v16; // r15
  unsigned __int16 *v17; // r13
  int Row; // esi
  __int64 result; // rax
  int v20; // eax
  int v21; // ebx
  ADS_BOOLEAN Boolean; // ecx
  __int64 v23; // r9
  unsigned int v24; // edx
  wchar_t *v25; // rdx
  __int64 v26; // rbx
  unsigned int v27; // r12d
  int v28; // esi
  _QWORD *v29; // r13
  wchar_t *v30; // rcx
  __int64 v31; // r14
  __int64 v32; // rax
  unsigned int v33; // eax
  struct tagQUERYCONTEXT *v34; // rsi
  __int16 Locale; // bx
  int v36; // eax
  unsigned int v37; // r9d
  unsigned __int16 v38; // si
  unsigned int LanguagePriority; // ebx
  bool v40; // zf
  int RsopSpecificAttributes; // eax
  unsigned int v42; // r14d
  unsigned int v43; // ebx
  __int64 v44; // r13
  struct tagCSPLATFORM *p_Platform; // r12
  BOOL v46; // r9d
  unsigned int v47; // r10d
  int v48; // r8d
  unsigned int v49; // esi
  unsigned int v50; // eax
  int v51; // r10d
  struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *v52; // rbx
  int v53; // eax
  unsigned int v54; // r14d
  const wchar_t **v55; // r12
  unsigned int v56; // ebx
  unsigned int v57; // ecx
  const wchar_t *v58; // rdx
  unsigned __int64 v59; // rax
  int v60; // ecx
  int v61; // eax
  int v62; // eax
  const unsigned __int16 *DNString; // rcx
  ADS_BOOLEAN v64; // ecx
  ADS_BOOLEAN v65; // ecx
  ADS_BOOLEAN v66; // ecx
  unsigned int *v67; // r14
  void *v68; // rcx
  unsigned int v69; // r12d
  wchar_t *v70; // r15
  __int64 v71; // rcx
  __int64 v72; // r13
  __int64 v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // rbx
  __int64 v76; // rcx
  unsigned __int16 *v77; // rcx
  unsigned __int16 *v78; // rax
  __int64 v79; // r9
  const unsigned __int16 *v80; // r8
  int v81; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v82; // [rsp+38h] [rbp-C8h]
  struct ads_search_column v83; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v84; // [rsp+68h] [rbp-98h]
  void *v85; // [rsp+70h] [rbp-90h]
  wchar_t *EndPtr; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL v87; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v89; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *String2; // [rsp+98h] [rbp-68h]
  struct tagQUERYCONTEXT *v91; // [rsp+A0h] [rbp-60h]
  void *v92; // [rsp+A8h] [rbp-58h]
  struct __MIDL___MIDL_itf_wtypes_0000_0001_0001 *v93; // [rsp+B0h] [rbp-50h]
  struct tagCSPLATFORM v94; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v95; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v96; // [rsp+D0h] [rbp-30h]
  struct ads_search_column v97[2]; // [rsp+E0h] [rbp-20h] BYREF

  v12 = a8;
  v13 = a7;
  v14 = a2;
  v15 = a9;
  v16 = a1;
  String2 = a5;
  v17 = 0;
  v96 = a12;
  v91 = a3;
  v85 = a2;
  v92 = a1;
  v93 = a4;
  v84 = a7;
  v82 = a9;
  hMem = 0;
  v87 = 0;
  v89 = 0;
  memset(&v83, 0, sizeof(v83));
  v94 = 0;
  memset_0(a8, 0, 0xD0u);
  *a7 = 0;
  Row = ADSIGetFirstRow(v16, v14);
  ReleasePackageInfo(a8);
  result = 1;
  if ( Row < 0 )
    goto LABEL_151;
  while ( Row != 20498 )
  {
    v20 = DSGetAndValidateColumn(v16, v14, ADSTYPE_CASE_IGNORE_STRING, L"packageName", &v83);
    if ( v20 < 0 )
    {
      if ( !gDebug )
        goto LABEL_70;
      v79 = (unsigned int)v20;
      v80 = L"packageName";
      goto LABEL_145;
    }
    v97[0] = v83;
    v21 = UnpackStrAllocFrom<_ads_attr_info>((__int64)v97, (HLOCAL *)v12);
    ADSIFreeColumn(v16, &v83);
    if ( gDebug )
      _DebugMsg(2, 0xC9Cu, *(_QWORD *)v12);
    if ( v21 < 0 || (v21 = DSGetAndValidateColumn(v16, v14, ADSTYPE_INTEGER, L"packageFlags", &v83), v21 < 0) )
    {
      if ( gDebug )
      {
        v79 = (unsigned int)v21;
        v80 = L"packageFlags";
LABEL_145:
        _DebugMsg(2, 0xC93u, v80, v79);
        goto LABEL_70;
      }
      goto LABEL_70;
    }
    if ( v83.dwNumValues )
      Boolean = v83.pADsValues->Boolean;
    else
      Boolean = 0;
    *((_DWORD *)v12 + 2) = Boolean;
    ADSIFreeColumn(v16, &v83);
    if ( v93->tyspec == 6 )
      goto LABEL_23;
    if ( !a10 || (*((_BYTE *)v12 + 8) & 0x40) != 0 )
    {
      if ( (*((_DWORD *)v12 + 2) & 0x408) == 0 )
      {
        if ( !gDebug )
          goto LABEL_70;
        v23 = 1024;
        goto LABEL_16;
      }
      if ( (*((_DWORD *)v12 + 2) & 0x180) != 0 )
      {
        if ( !gDebug )
          goto LABEL_70;
        v23 = 256;
        goto LABEL_16;
      }
LABEL_23:
      v24 = *((_DWORD *)v12 + 2);
      if ( (v24 & 0x10) == 0 )
      {
        if ( gDebug )
          _DebugMsg(2, 0xCA4u);
        goto LABEL_70;
      }
      *((_DWORD *)v12 + 3) = v24 >> 29;
      *((_DWORD *)v12 + 10) = (v24 & 0x80000) != 0 ? 3 : 5;
      *v15 = 0;
      if ( String2 )
      {
        Row = DSGetAndValidateColumn(v16, v14, ADSTYPE_CASE_IGNORE_STRING, L"fileExtPriority", &v83);
        v81 = 0;
        if ( Row < 0 )
          goto LABEL_149;
        v97[0] = v83;
        Row = UnpackStrArrFrom<ads_search_column>(v97, &hMem, &v81);
        if ( Row < 0 )
          goto LABEL_149;
        v25 = String2;
        v26 = -1;
        do
          ++v26;
        while ( String2[v26] );
        v27 = v81;
        v28 = 0;
        v29 = hMem;
        if ( v81 )
        {
          v30 = (wchar_t *)(unsigned int)(v26 + 3);
          EndPtr = v30;
          while ( 1 )
          {
            hMem = 0;
            v31 = v29[v28];
            v32 = -1;
            do
              ++v32;
            while ( *(_WORD *)(v31 + 2 * v32) );
            if ( (wchar_t *)v32 == v30 )
            {
              if ( !wcsncmp_0((const wchar_t *)v29[v28], v25, (unsigned int)v26) )
              {
                v33 = wcstoul((const wchar_t *)(v31 + 2LL * (unsigned int)(v26 + 1)), (wchar_t **)&hMem, 10);
                v15 = v82;
                *v82 = v33;
                break;
              }
              v30 = EndPtr;
              v25 = String2;
            }
            if ( ++v28 >= v27 )
            {
              v15 = v82;
              break;
            }
          }
        }
        ADSIFreeColumn(v16, &v83);
        LocalFree(v29);
        hMem = 0;
        if ( v28 == v27 )
        {
          if ( gDebug )
            _DebugMsg(2, 0xCA0u, *(_QWORD *)v12);
          v14 = v85;
          v17 = (unsigned __int16 *)v87;
          goto LABEL_70;
        }
        v14 = v85;
        v17 = (unsigned __int16 *)v87;
      }
      v34 = v91;
      if ( v91->Locale )
      {
        Locale = v91->Locale;
        v36 = DSGetAndValidateColumn(v16, v14, ADSTYPE_INTEGER, L"localeID", &v83);
        v37 = 0;
        if ( v36 >= 0 )
        {
          v81 = 0;
          v97[0] = v83;
          UnpackDWArrFrom<ads_search_column>(v97, &v89, &v81);
          ADSIFreeColumn(v16, &v83);
          v17 = v89;
          v37 = 0;
        }
        v38 = *v17;
        if ( Locale == 2048 )
        {
          LanguagePriority = GetLanguagePriority(v38, *((_DWORD *)v12 + 2));
        }
        else
        {
          v40 = Locale == (__int16)v38;
          LanguagePriority = 2048;
          if ( !v40 )
            LanguagePriority = 0;
        }
        if ( !LanguagePriority )
          LanguagePriority = v37;
        LocalFree(v17);
        v87 = 0;
        v17 = 0;
        v89 = 0;
        if ( !LanguagePriority )
          goto LABEL_70;
        *v15 += LanguagePriority;
        *((_WORD *)v12 + 64) = v38;
        v34 = v91;
      }
      RsopSpecificAttributes = GetRsopSpecificAttributes(v16, v14, 0, v12, 0);
      if ( RsopSpecificAttributes < 0 )
      {
        if ( gDebug )
          _DebugMsg(2, 0xCA2u, (unsigned int)RsopSpecificAttributes);
        goto LABEL_70;
      }
      v42 = *((_DWORD *)v12 + 41);
      v43 = 0;
      v44 = *((_QWORD *)v12 + 21);
      *((_DWORD *)v12 + 40) = 0xFFFF;
      if ( v42 )
      {
        p_Platform = &v34->Platform;
        v46 = *((_DWORD *)v12 + 3) == 6;
        v47 = 0;
        v48 = *((_DWORD *)v12 + 2) & 0x10000;
        do
        {
          v49 = *(_DWORD *)(v44 + 4LL * v47);
          v94.dwPlatformId = (unsigned __int8)v49;
          v94.dwVersionHi = BYTE1(v49);
          v94.dwVersionLo = BYTE2(v49);
          v94.dwProcessorArch = HIBYTE(v49);
          v50 = PlatformWt(p_Platform, &v94, v48, v46);
          if ( v50 > v43 )
          {
            *((_DWORD *)v12 + 40) = v49;
            v43 = v50;
          }
          v47 = v51 + 1;
        }
        while ( v47 < v42 );
        v16 = v92;
        v14 = v85;
      }
      v87 = 0;
      v17 = 0;
      v89 = 0;
      if ( !v43 )
      {
        if ( gDebug )
          _DebugMsg(2, 0xC9Eu, *(_QWORD *)v12);
        goto LABEL_69;
      }
      *v82 += v43;
      if ( (int)DSGetAndValidateColumn(v16, v14, ADSTYPE_OCTET_STRING, L"objectGUID", &v83) >= 0 )
      {
        v97[0] = v83;
        UnpackGUIDFrom<ads_search_column>(v97, (char *)v12 + 60);
        ADSIFreeColumn(v16, &v83);
      }
      if ( (int)DSGetAndValidateColumn(v16, v14, ADSTYPE_CASE_IGNORE_STRING, L"msiScriptPath", &v83) >= 0 )
      {
        v97[0] = v83;
        Row = UnpackStrAllocFrom<_ads_attr_info>((__int64)v97, (HLOCAL *)v12 + 2);
        ADSIFreeColumn(v16, &v83);
        if ( Row < 0 )
          goto LABEL_149;
        v52 = v93;
        if ( !v93->tyspec )
        {
          v81 = 0;
          if ( (int)DSGetAndValidateColumn(v16, v14, ADSTYPE_CASE_IGNORE_STRING, L"cOMClassID", &v83) >= 0 )
          {
            v97[0] = v83;
            v53 = UnpackStrArrFrom<ads_search_column>(v97, &hMem, &v81);
            v54 = v81;
            Row = v53;
            if ( v81 )
            {
              EndPtr = 0;
              StringFromGUID(&v52->tagged_union.clsid, (unsigned __int16 *)v97);
              v55 = (const wchar_t **)hMem;
              v56 = 0;
              do
              {
                if ( !wcsncmp_0(v55[v56], (const wchar_t *)v97, 0x24u) )
                  break;
                ++v56;
              }
              while ( v56 < v54 );
              v16 = v92;
              v17 = (unsigned __int16 *)v87;
              if ( v56 == v54 )
              {
                if ( gDebug )
                  _DebugMsg(2, 0xC9Fu, *(_QWORD *)v12);
                LocalFree(v55);
LABEL_86:
                v14 = v85;
LABEL_69:
                v15 = v82;
                goto LABEL_70;
              }
              v57 = 0;
              v58 = v55[v56];
              v59 = -1;
              do
                ++v59;
              while ( v58[v59] );
              if ( v59 > 0x24 )
                v57 = wcstoul(v58 + 37, &EndPtr, 16);
              v60 = v91->dwContext & v57;
              if ( !v60 )
              {
                LocalFree(v55);
                ADSIFreeColumn(v16, &v83);
                if ( gDebug )
                  _DebugMsg(2, 0xC9Fu, *(_QWORD *)v12);
                goto LABEL_86;
              }
              if ( (v60 & 1) != 0 )
              {
                v61 = 384;
              }
              else if ( (v60 & 4) != 0 )
              {
                v61 = 256;
              }
              else
              {
                v61 = 8 * (v60 & 0x10);
              }
              *v82 += v61;
              LocalFree(v55);
              v14 = v85;
            }
            ADSIFreeColumn(v16, &v83);
            if ( Row < 0 )
              goto LABEL_149;
          }
        }
      }
      v62 = DSGetAndValidateColumn(v16, v14, ADSTYPE_CASE_IGNORE_STRING, L"lastUpdateSequence", &v83);
      if ( v62 < 0 )
      {
        if ( gDebug )
          _DebugMsg(2, 0xC93u, L"lastUpdateSequence", (unsigned int)v62);
        goto LABEL_69;
      }
      if ( v83.dwNumValues )
        DNString = v83.pADsValues->DNString;
      else
        DNString = 0;
      TimeToUsn(DNString, (struct _FILETIME *)v12 + 10);
      ADSIFreeColumn(v16, &v83);
      if ( (int)DSGetAndValidateColumn(v16, v14, ADSTYPE_OCTET_STRING, L"productCode", &v83) >= 0 )
      {
        v97[0] = v83;
        UnpackGUIDFrom<ads_search_column>(v97, (char *)v12 + 44);
        ADSIFreeColumn(v16, &v83);
      }
      if ( (int)DSGetAndValidateColumn(v16, v14, ADSTYPE_INTEGER, L"versionNumberHi", &v83) >= 0 )
      {
        if ( v83.dwNumValues )
          v64 = v83.pADsValues->Boolean;
        else
          v64 = 0;
        *((_DWORD *)v12 + 22) = v64;
        ADSIFreeColumn(v16, &v83);
      }
      if ( (int)DSGetAndValidateColumn(v16, v14, ADSTYPE_INTEGER, L"versionNumberLo", &v83) >= 0 )
      {
        if ( v83.dwNumValues )
          v65 = v83.pADsValues->Boolean;
        else
          v65 = 0;
        *((_DWORD *)v12 + 23) = v65;
        ADSIFreeColumn(v16, &v83);
      }
      if ( (int)DSGetAndValidateColumn(v16, v14, ADSTYPE_INTEGER, L"revision", &v83) >= 0 )
      {
        if ( v83.dwNumValues )
          v66 = v83.pADsValues->Boolean;
        else
          v66 = 0;
        *((_DWORD *)v12 + 24) = v66;
        ADSIFreeColumn(v16, &v83);
      }
      if ( (int)DSGetAndValidateColumn(v16, v14, ADSTYPE_CASE_IGNORE_STRING, L"url", &v83) >= 0 )
      {
        v97[0] = v83;
        UnpackStrAllocFrom<_ads_attr_info>((__int64)v97, (HLOCAL *)v12 + 4);
        ADSIFreeColumn(v16, &v83);
      }
      Row = DSGetAndValidateColumn(v16, v14, ADSTYPE_CASE_IGNORE_STRING, L"canUpgradeScript", &v83);
      if ( Row >= 0 )
      {
        v67 = (unsigned int *)((char *)v12 + 116);
        EndPtr = 0;
        v97[0] = v83;
        Row = UnpackStrArrAllocFrom<ads_search_column>(v97, &EndPtr, (char *)v12 + 116);
        v81 = Row;
        if ( *((_DWORD *)v12 + 29) )
          *((_QWORD *)v12 + 15) = LocalAlloc(0, 48LL * *v67);
        v68 = (void *)*((_QWORD *)v12 + 15);
        if ( v68 )
        {
          memset_0(v68, 0, 48LL * *v67);
          v69 = 0;
          if ( *v67 )
          {
            v70 = EndPtr;
            do
            {
              v71 = *((_QWORD *)v12 + 15);
              EndPtr = 0;
              v72 = 48LL * v69;
              *(_QWORD *)(v71 + v72) = *(_QWORD *)&v70[4 * v69];
              v73 = -1;
              v74 = *(_QWORD *)(*((_QWORD *)v12 + 15) + v72);
              v95 = v74;
              do
                ++v73;
              while ( *(_WORD *)(v74 + 2 * v73) );
              if ( (unsigned int)v73 > 0x29 )
              {
                v75 = (unsigned int)v73;
                *(_WORD *)(v74 + 2LL * (unsigned int)v73 - 6) = 0;
                *(_DWORD *)(*((_QWORD *)v12 + 15) + v72 + 40) = wcstoul(
                                                                  (const wchar_t *)(v74 + 2LL * (unsigned int)(v73 - 2)),
                                                                  &EndPtr,
                                                                  16);
                v76 = v95;
                *(_WORD *)(v95 + 2 * v75 - 82) = 0;
                GUIDFromString(
                  (const unsigned __int16 *)(v76 + 2 * v75 - 78),
                  (struct _GUID *)(v72 + *((_QWORD *)v12 + 15) + 8LL));
              }
              ++v69;
            }
            while ( v69 < *v67 );
            Row = v81;
            v16 = v92;
            v17 = (unsigned __int16 *)v87;
          }
          *v67 = v69;
          v14 = v85;
        }
        ADSIFreeColumn(v16, &v83);
        if ( Row < 0 )
        {
LABEL_149:
          result = 1;
          break;
        }
      }
      v77 = v96;
      *(struct _GUID *)((char *)v12 + 100) = *a11;
      v78 = StringDuplicate(v77);
      v13 = v84;
      v40 = v78 == 0;
      *((_QWORD *)v12 + 19) = v78;
      result = 1;
      if ( v40 )
      {
        Row = -2147024882;
        goto LABEL_151;
      }
      if ( ++*v13 == 10 )
        goto LABEL_151;
      v12 = (struct tagPACKAGEDISPINFO *)((char *)v12 + 208);
      v15 = ++v82;
      memset_0(v12, 0, 0xD0u);
      goto LABEL_70;
    }
    if ( gDebug )
    {
      v23 = 64;
LABEL_16:
      _DebugMsg(2, 0xC94u, *(_QWORD *)v12, v23);
    }
LABEL_70:
    Row = ADSIGetNextRow(v16, v14);
    ReleasePackageInfo(v12);
    result = 1;
    if ( Row < 0 )
      break;
  }
  v13 = v84;
LABEL_151:
  if ( *v13 )
    return *v13 != 10;
  if ( Row < 0 )
    return (unsigned int)Row;
  return result;
}

```

## disassembly

```asm
0x180025378  push    rbp
0x18002537a  push    rbx
0x18002537b  push    rsi
0x18002537c  push    rdi
0x18002537d  push    r12
0x18002537f  push    r13
0x180025381  push    r14
0x180025383  push    r15
0x180025385  lea     rbp, [rsp-48h]
0x18002538a  sub     rsp, 148h
0x180025391  mov     rax, cs:__security_cookie
0x180025398  xor     rax, rsp
0x18002539b  mov     [rbp+80h+var_50], rax
0x18002539f  mov     rax, [rbp+80h+arg_20]
0x1800253a6  xor     esi, esi
0x1800253a8  mov     rdi, [rbp+80h+arg_38]
0x1800253af  xorps   xmm0, xmm0
0x1800253b2  mov     rbx, [rbp+80h+arg_30]
0x1800253b9  mov     r12, rdx
0x1800253bc  mov     r14, [rbp+80h+arg_40]
0x1800253c3  mov     r15, rcx
0x1800253c6  mov     [rbp+80h+String2], rax
0x1800253ca  mov     r13d, esi
0x1800253cd  mov     rax, [rbp+80h+arg_58]
0x1800253d4  mov     [rbp+80h+var_B0], rax
0x1800253d8  xor     eax, eax
0x1800253da  mov     [rbp+80h+var_E0], r8
0x1800253de  mov     r8d, 0D0h; Size
0x1800253e4  mov     [rsp+180h+var_110], rdx
0x1800253e9  xor     edx, edx; Val
0x1800253eb  mov     [rbp+80h+var_D8], rcx
0x1800253ef  mov     rcx, rdi; void *
0x1800253f2  mov     [rsp+180h+var_140.hReserved], rax
0x1800253f7  mov     [rbp+80h+var_D0], r9
0x1800253fb  mov     [rsp+180h+var_118], rbx
0x180025400  mov     [rsp+180h+var_148], r14
0x180025405  mov     [rbp+80h+hMem], rsi
0x180025409  mov     [rbp+80h+var_100], rsi
0x18002540d  mov     [rbp+80h+var_F0], rsi
0x180025411  movups  xmmword ptr [rsp+180h+var_140.pszAttrName], xmm0
0x180025416  movups  xmmword ptr [rsp+180h+var_140.pADsValues], xmm0
0x18002541b  movups  xmmword ptr [rbp+80h+var_C8.dwPlatformId], xmm0
0x18002541f  call    memset_0
0x180025424  mov     rdx, r12
0x180025427  mov     [rbx], esi
0x180025429  mov     rcx, r15
0x18002542c  call    cs:__imp_ADSIGetFirstRow
0x180025432  mov     rcx, rdi; void *
0x180025435  mov     esi, eax
0x180025437  call    ReleasePackageInfo
0x18002543c  lea     eax, [r13+1]
0x180025440  test    esi, esi
0x180025442  js      loc_180026004
0x180025448  cmp     esi, 5012h
0x18002544e  jz      loc_180025FFD
0x180025454  lea     rax, [rsp+180h+var_140]
0x180025459  mov     r8d, 3; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x18002545f  lea     r9, aPackagename_0; "packageName"
0x180025466  mov     [rsp+180h+var_160], rax; struct ads_search_column *
0x18002546b  mov     rdx, r12; void *
0x18002546e  mov     rcx, r15; void *
0x180025471  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180025476  xor     esi, esi
0x180025478  test    eax, eax
0x18002547a  js      loc_180025FD9
0x180025480  movups  xmm0, xmmword ptr [rsp+180h+var_140.pszAttrName]
0x180025485  mov     rdx, rdi
0x180025488  lea     rcx, [rbp+80h+var_A0]
0x18002548c  movups  xmm1, xmmword ptr [rsp+180h+var_140.pADsValues]
0x180025491  movaps  xmmword ptr [rbp+80h+var_A0], xmm0
0x180025495  movsd   xmm0, [rsp+180h+var_140.hReserved]
0x18002549b  movsd   [rbp+80h+var_80], xmm0
0x1800254a0  movaps  [rbp+80h+var_90], xmm1
0x1800254a4  call    ??$UnpackStrAllocFrom@U_ads_attr_info@@@@YAJU_ads_attr_info@@PEAPEAG@Z; UnpackStrAllocFrom<_ads_attr_info>(_ads_attr_info,ushort * *)
0x1800254a9  lea     rdx, [rsp+180h+var_140]
0x1800254ae  mov     rcx, r15
0x1800254b1  mov     ebx, eax
0x1800254b3  call    cs:__imp_ADSIFreeColumn
0x1800254b9  cmp     cs:?gDebug@@3KA, esi; ulong gDebug
0x1800254bf  jz      short loc_1800254D1
0x1800254c1  mov     r8, [rdi]
0x1800254c4  lea     ecx, [rsi+2]; unsigned int
0x1800254c7  mov     edx, 0C9Ch; unsigned int
0x1800254cc  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800254d1  test    ebx, ebx
0x1800254d3  js      loc_180025FAF
0x1800254d9  lea     rax, [rsp+180h+var_140]
0x1800254de  mov     r8d, 7; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x1800254e4  lea     r9, aPackageflags; "packageFlags"
0x1800254eb  mov     [rsp+180h+var_160], rax; struct ads_search_column *
0x1800254f0  mov     rdx, r12; void *
0x1800254f3  mov     rcx, r15; void *
0x1800254f6  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x1800254fb  mov     ebx, eax
0x1800254fd  test    eax, eax
0x1800254ff  js      loc_180025FAF
0x180025505  cmp     [rsp+180h+var_140.dwNumValues], esi
0x180025509  jz      short loc_180025515
0x18002550b  mov     rax, [rsp+180h+var_140.pADsValues]
0x180025510  mov     ecx, [rax+8]
0x180025513  jmp     short loc_180025517
0x180025515  mov     ecx, esi
0x180025517  mov     [rdi+8], ecx
0x18002551a  lea     rdx, [rsp+180h+var_140]
0x18002551f  mov     rcx, r15
0x180025522  call    cs:__imp_ADSIFreeColumn
0x180025528  mov     rax, [rbp+80h+var_D0]
0x18002552c  cmp     dword ptr [rax], 6
0x18002552f  jz      short loc_180025598
0x180025531  cmp     [rbp+80h+arg_48], esi
0x180025537  jz      short loc_18002555E
0x180025539  test    byte ptr [rdi+8], 40h
0x18002553d  jnz     short loc_18002555E
0x18002553f  cmp     cs:?gDebug@@3KA, esi; ulong gDebug
0x180025545  jz      loc_180025917
0x18002554b  mov     r9d, 40h ; '@'
0x180025551  mov     r8, [rdi]
0x180025554  mov     edx, 0C94h
0x180025559  jmp     loc_180025FCA
0x18002555e  test    dword ptr [rdi+8], 408h
0x180025565  jnz     short loc_18002557B
0x180025567  cmp     cs:?gDebug@@3KA, esi; ulong gDebug
0x18002556d  jz      loc_180025917
0x180025573  mov     r9d, 400h
0x180025579  jmp     short loc_180025551
0x18002557b  test    dword ptr [rdi+8], 180h
0x180025582  jz      short loc_180025598
0x180025584  cmp     cs:?gDebug@@3KA, esi; ulong gDebug
0x18002558a  jz      loc_180025917
0x180025590  mov     r9d, 100h
0x180025596  jmp     short loc_180025551
0x180025598  mov     edx, [rdi+8]
0x18002559b  test    dl, 10h
0x18002559e  jnz     short loc_1800255C0
0x1800255a0  cmp     cs:?gDebug@@3KA, esi; ulong gDebug
0x1800255a6  jz      loc_180025917
0x1800255ac  mov     edx, 0CA4h; unsigned int
0x1800255b1  mov     ecx, 2; unsigned int
0x1800255b6  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800255bb  jmp     loc_180025917
0x1800255c0  mov     eax, edx
0x1800255c2  and     eax, 80000h
0x1800255c7  neg     eax
0x1800255c9  sbb     ecx, ecx
0x1800255cb  shr     edx, 1Dh
0x1800255ce  and     ecx, 0FFFFFFFEh
0x1800255d1  mov     [rdi+0Ch], edx
0x1800255d4  add     ecx, 5
0x1800255d7  mov     [rdi+28h], ecx
0x1800255da  mov     [r14], esi
0x1800255dd  cmp     [rbp+80h+String2], rsi
0x1800255e1  jz      loc_180025739
0x1800255e7  lea     rax, [rsp+180h+var_140]
0x1800255ec  mov     r8d, 3; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x1800255f2  lea     r9, aFileextpriorit; "fileExtPriority"
0x1800255f9  mov     [rsp+180h+var_160], rax; struct ads_search_column *
0x1800255fe  mov     rdx, r12; void *
0x180025601  mov     rcx, r15; void *
0x180025604  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x180025609  mov     esi, eax
0x18002560b  xor     eax, eax
0x18002560d  mov     [rsp+180h+var_150], eax
0x180025611  test    esi, esi
0x180025613  js      loc_180025FF8
0x180025619  movups  xmm0, xmmword ptr [rsp+180h+var_140.pszAttrName]
0x18002561e  lea     r8, [rsp+180h+var_150]
0x180025623  movups  xmm1, xmmword ptr [rsp+180h+var_140.pADsValues]
0x180025628  lea     rdx, [rbp+80h+hMem]
0x18002562c  movaps  xmmword ptr [rbp+80h+var_A0], xmm0
0x180025630  lea     rcx, [rbp+80h+var_A0]
0x180025634  movsd   xmm0, [rsp+180h+var_140.hReserved]
0x18002563a  movsd   [rbp+80h+var_80], xmm0
0x18002563f  movaps  [rbp+80h+var_90], xmm1
0x180025643  call    ??$UnpackStrArrFrom@Uads_search_column@@@@YAJUads_search_column@@PEAPEAPEAGPEAK@Z; UnpackStrArrFrom<ads_search_column>(ads_search_column,ushort * * *,ulong *)
0x180025648  mov     esi, eax
0x18002564a  xor     eax, eax
0x18002564c  test    esi, esi
0x18002564e  js      loc_180025FF8
0x180025654  mov     rdx, [rbp+80h+String2]; String2
0x180025658  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002565c  inc     rbx
0x18002565f  cmp     [rdx+rbx*2], ax
0x180025663  jnz     short loc_18002565C
0x180025665  mov     r12d, [rsp+180h+var_150]
0x18002566a  mov     esi, eax
0x18002566c  mov     r13, [rbp+80h+hMem]
0x180025670  test    r12d, r12d
0x180025673  jz      short loc_1800256C5
0x180025675  lea     ecx, [rbx+3]
0x180025678  xor     r8d, r8d
0x18002567b  mov     [rsp+180h+EndPtr], rcx
0x180025680  mov     eax, esi
0x180025682  mov     [rbp+80h+hMem], r8
0x180025686  mov     r14, [r13+rax*8+0]
0x18002568b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002568f  inc     rax
0x180025692  cmp     [r14+rax*2], r8w
0x180025697  jnz     short loc_18002568F
0x180025699  cmp     rax, rcx
0x18002569c  jnz     short loc_1800256B9
0x18002569e  mov     r8d, ebx; MaxCount
0x1800256a1  mov     rcx, r14; String1
0x1800256a4  call    wcsncmp_0
0x1800256a9  xor     r8d, r8d
0x1800256ac  test    eax, eax
0x1800256ae  jz      short loc_18002570D
0x1800256b0  mov     rcx, [rsp+180h+EndPtr]
0x1800256b5  mov     rdx, [rbp+80h+String2]
0x1800256b9  inc     esi
0x1800256bb  cmp     esi, r12d
0x1800256be  jb      short loc_180025680
0x1800256c0  mov     r14, [rsp+180h+var_148]
0x1800256c5  lea     rdx, [rsp+180h+var_140]
0x1800256ca  mov     rcx, r15
0x1800256cd  call    cs:__imp_ADSIFreeColumn
0x1800256d3  mov     rcx, r13; hMem
0x1800256d6  call    cs:__imp_LocalFree
0x1800256dc  xor     eax, eax
0x1800256de  mov     [rbp+80h+hMem], rax
0x1800256e2  cmp     esi, r12d
0x1800256e5  jnz     short loc_18002572E
0x1800256e7  cmp     cs:?gDebug@@3KA, eax; ulong gDebug
0x1800256ed  jz      short loc_1800256FF
0x1800256ef  mov     r8, [rdi]
0x1800256f2  lea     ecx, [rax+2]; unsigned int
0x1800256f5  mov     edx, 0CA0h; unsigned int
0x1800256fa  call    ?_DebugMsg@@YAXKKZZ; _DebugMsg(ulong,ulong,...)
0x1800256ff  mov     r12, [rsp+180h+var_110]
0x180025704  mov     r13, [rbp+80h+var_100]
0x180025708  jmp     loc_180025917
0x18002570d  lea     eax, [rbx+1]
0x180025710  mov     r8d, 0Ah; Radix
0x180025716  lea     rcx, [r14+rax*2]; String
0x18002571a  lea     rdx, [rbp+80h+hMem]; EndPtr
0x18002571e  call    cs:__imp_wcstoul
0x180025724  mov     r14, [rsp+180h+var_148]
0x180025729  mov     [r14], eax
0x18002572c  jmp     short loc_1800256C5
0x18002572e  mov     r12, [rsp+180h+var_110]
0x180025733  mov     r13, [rbp+80h+var_100]
0x180025737  jmp     short loc_18002573B
0x180025739  xor     eax, eax
0x18002573b  mov     rsi, [rbp+80h+var_E0]
0x18002573f  cmp     [rsi+14h], eax
0x180025742  jz      loc_180025818
0x180025748  movzx   ebx, word ptr [rsi+14h]
0x18002574c  lea     rax, [rsp+180h+var_140]
0x180025751  lea     r9, aLocaleid; "localeID"
0x180025758  mov     [rsp+180h+var_160], rax; struct ads_search_column *
0x18002575d  mov     r8d, 7; enum __MIDL___MIDL_itf_ads_0000_0000_0001
0x180025763  mov     rdx, r12; void *
0x180025766  mov     rcx, r15; void *
0x180025769  call    ?DSGetAndValidateColumn@@YAJPEAX0W4__MIDL___MIDL_itf_ads_0000_0000_0001@@PEBGPEAUads_search_column@@@Z; DSGetAndValidateColumn(void *,void *,__MIDL___MIDL_itf_ads_0000_0000_0001,ushort const *,ads_search_column *)
0x18002576e  xor     r9d, r9d
0x180025771  test    eax, eax
0x180025773  js      short loc_1800257BE
0x180025775  movups  xmm0, xmmword ptr [rsp+180h+var_140.pszAttrName]
0x18002577a  lea     r8, [rsp+180h+var_150]
0x18002577f  mov     [rsp+180h+var_150], r9d
0x180025784  movups  xmm1, xmmword ptr [rsp+180h+var_140.pADsValues]
0x180025789  lea     rdx, [rbp+80h+var_F0]
0x18002578d  movaps  xmmword ptr [rbp+80h+var_A0], xmm0
0x180025791  lea     rcx, [rbp+80h+var_A0]
0x180025795  movsd   xmm0, [rsp+180h+var_140.hReserved]
0x18002579b  movsd   [rbp+80h+var_80], xmm0
0x1800257a0  movaps  [rbp+80h+var_90], xmm1
0x1800257a4  call    ??$UnpackDWArrFrom@Uads_search_column@@@@YAJUads_search_column@@PEAPEAKPEAK@Z; UnpackDWArrFrom<ads_search_column>(ads_search_column,ulong * *,ulong *)
0x1800257a9  lea     rdx, [rsp+180h+var_140]
0x1800257ae  mov     rcx, r15
0x1800257b1  call    cs:__imp_ADSIFreeColumn
0x1800257b7  mov     r13, [rbp+80h+var_F0]
0x1800257bb  xor     r9d, r9d
0x1800257be  movzx   esi, word ptr [r13+0]
0x1800257c3  mov     eax, 800h
0x1800257c8  cmp     ax, bx
0x1800257cb  jnz     short loc_1800257DC
0x1800257cd  mov     edx, [rdi+8]; unsigned int
0x1800257d0  movzx   ecx, si; unsigned __int16
0x1800257d3  call    ?GetLanguagePriority@@YAKGK@Z; GetLanguagePriority(ushort,ulong)
0x1800257d8  mov     ebx, eax
0x1800257da  jmp     short loc_1800257E6
0x1800257dc  cmp     bx, si
0x1800257df  mov     ebx, eax
0x1800257e1  jz      short loc_1800257E6
0x1800257e3  mov     ebx, r9d
0x1800257e6  test    ebx, ebx
0x1800257e8  mov     rcx, r13; hMem
0x1800257eb  cmovz   ebx, r9d
0x1800257ef  call    cs:__imp_LocalFree
0x1800257f5  xor     eax, eax
0x1800257f7  mov     [rbp+80h+var_100], rax
0x1800257fb  mov     r13d, eax
0x1800257fe  mov     [rbp+80h+var_F0], rax
0x180025802  test    ebx, ebx
0x180025804  jz      loc_180025917
0x18002580a  add     [r14], ebx
0x18002580d  mov     [rdi+80h], si
0x180025814  mov     rsi, [rbp+80h+var_E0]
0x180025818  mov     r9, rdi; struct tagPACKAGEDISPINFO *
0x18002581b  mov     [rsp+180h+var_160], rax; int *
  ... truncated ...
```
