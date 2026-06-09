# FwAdvPolicyEncodeRuleInt

- ea: `0x18000a328`
- end: `0x18000c2bd`
- name: `FwAdvPolicyEncodeRuleInt`
- size: `8085`
- prototype: `__int64 __fastcall(struct _tag_FW_RULE *)`
- caller_count: `2`
- callee_count: `35`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009300`
- `0x180009310`

## callees

- `0x1800042c4`
- `0x1800090fc`
- `0x180009260`
- `0x180009324`
- `0x180009a3c`
- `0x180009ce8`
- `0x180009d7c`
- `0x180009e60`
- `0x180009f80`
- `0x18000a070`
- `0x18000a174`
- `0x18000a1f0`
- `0x18000a328`
- `0x18000cff0`
- `0x18000d250`
- `0x18000de3c`
- `0x18000e350`
- `0x18000e4c4`
- `0x18000e684`
- `0x18000e844`
- `0x18000e964`
- `0x18000eb5c`
- `0x18000ec70`
- `0x18000ed84`
- `0x18000ee90`
- `0x18001515c`
- `0x1800151e8`
- `0x18001569c`
- `0x180017a78`
- `0x18001ab10`
- `0x18001e0cc`
- `0x18001e9ac`
- `0x18001f650`
- `0x1800354d4`
- `0x180035680`

## import_xrefs

- `fwbase!FwAlloc` at `0x18000aa4a`
- `fwbase!FwAlloc` at `0x18000aa4a`
- `fwbase!FwSizeTMultiply` at `0x18000aa36`
- `fwbase!FwSizeTMultiply` at `0x18000aa36`

## string_xrefs

- `0x18000b2dc`: `SecurityRealmId=`
- `0x18000c1cf`: `ComptId=`

## pseudocode

```c
__int64 __fastcall FwAdvPolicyEncodeRuleInt(wchar_t *a1, wchar_t **a2, int a3)
{
  STRSAFE_LPWSTR v3; // r14
  int v4; // eax
  int v5; // ecx
  unsigned int v6; // r15d
  __int64 AddressSize; // rsi
  __int64 v8; // rdi
  unsigned int v9; // edx
  unsigned int v10; // ecx
  __int64 Address2_20Size; // rbx
  unsigned int v12; // edx
  unsigned int v13; // ecx
  __int64 v14; // r9
  int v15; // edi
  __int64 v16; // r9
  unsigned int v17; // ecx
  unsigned int v18; // r15d
  unsigned int v19; // esi
  struct _tag_FW_ENUM_ENTRY near *v20; // r12
  unsigned int v21; // ebx
  __int64 i; // r13
  int AppSize; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdi
  LPCOLESTR v26; // rcx
  const wchar_t *v28; // rcx
  unsigned int v29; // eax
  HRESULT v30; // eax
  const wchar_t *v31; // rcx
  __int64 v32; // rdi
  unsigned int v33; // eax
  HRESULT v34; // eax
  const unsigned __int16 *v35; // rdx
  __int64 v36; // rsi
  const wchar_t *v37; // rcx
  __int64 v38; // rdi
  unsigned int v39; // eax
  HRESULT v40; // eax
  const wchar_t *v41; // rcx
  __int64 v42; // rdi
  unsigned int v43; // eax
  HRESULT v44; // eax
  const wchar_t *v45; // rcx
  __int64 v46; // rdi
  unsigned int v47; // eax
  __int64 v48; // r15
  HRESULT v49; // eax
  const wchar_t *v50; // rcx
  unsigned int v51; // ebx
  __int64 v52; // rdi
  HRESULT v53; // eax
  int v54; // eax
  __int64 v55; // rsi
  wchar_t v56; // ax
  __int64 PortSize; // rbx
  unsigned __int16 **const v58; // rcx
  __int64 v59; // rdi
  unsigned int PlatformValiditySize; // eax
  wchar_t v61; // bx
  int v62; // ecx
  int v63; // eax
  int v64; // ecx
  unsigned int v65; // esi
  __int64 v66; // r12
  int v67; // edx
  unsigned __int64 v68; // r13
  int EnumFlagsSize; // eax
  int v70; // edx
  int v71; // eax
  int v72; // edx
  unsigned int v73; // eax
  int v74; // edx
  const wchar_t *v75; // rcx
  unsigned __int64 v76; // rsi
  unsigned int v77; // eax
  __int64 v78; // rsi
  HRESULT v79; // eax
  wchar_t v80; // di
  __int64 v81; // r15
  __int64 v82; // r12
  __int64 v83; // r13
  __int64 v84; // rdi
  unsigned int v85; // r13d
  unsigned int v86; // ecx
  __int64 v87; // rax
  unsigned int v88; // r8d
  __int64 v89; // rsi
  const wchar_t *v90; // rcx
  HRESULT v91; // eax
  size_t v92; // rdi
  wchar_t *v93; // rax
  unsigned int v94; // ecx
  wchar_t v95; // ax
  int v96; // esi
  wchar_t *v97; // rbx
  size_t v98; // rdi
  int v99; // esi
  int v100; // esi
  __int64 v101; // rax
  int v102; // esi
  __int64 v103; // rax
  int v104; // esi
  __int64 v105; // rax
  int v106; // esi
  __int64 v107; // rax
  int v108; // esi
  wchar_t *v109; // rbx
  size_t v110; // rdi
  int v111; // esi
  bool v112; // zf
  wchar_t *v113; // rcx
  size_t v114; // rdx
  unsigned int v115; // r12d
  int v116; // r15d
  wchar_t *v117; // rbx
  unsigned int v118; // esi
  size_t v119; // rdi
  int v120; // ecx
  struct _tag_FW_ENUM_ENTRY near *v121; // r13
  unsigned int v122; // r12d
  int v123; // r15d
  int v124; // ecx
  unsigned int v125; // esi
  struct _tag_FW_ENUM_ENTRY near *v126; // r13
  unsigned int v127; // r12d
  int v128; // r15d
  int v129; // ecx
  unsigned int v130; // esi
  struct _tag_FW_ENUM_ENTRY near *v131; // r13
  unsigned int v132; // r12d
  int v133; // r15d
  int v134; // ecx
  unsigned int v135; // esi
  struct _tag_FW_ENUM_ENTRY near *v136; // r13
  int v137; // r15d
  __int64 v138; // rsi
  __int64 v139; // rax
  int v140; // esi
  wchar_t *v141; // rbx
  size_t v142; // rdi
  int v143; // r15d
  __int64 v144; // rsi
  __int64 v145; // rax
  int v146; // ebx
  wchar_t *v147; // rdi
  size_t v148; // rsi
  int v149; // eax
  __int64 v150; // rdx
  int v151; // ecx
  int v152; // eax
  const unsigned __int16 *v153; // rcx
  unsigned int v154; // esi
  __int64 v155; // r9
  const unsigned __int16 *v156; // [rsp+20h] [rbp-B9h]
  const unsigned __int16 *v157; // [rsp+20h] [rbp-B9h]
  const unsigned __int16 *v158; // [rsp+20h] [rbp-B9h]
  const unsigned __int16 *v159; // [rsp+20h] [rbp-B9h]
  const unsigned __int16 *v160; // [rsp+20h] [rbp-B9h]
  struct _tag_FW_ICMP_TYPE_CODE_LIST *v161; // [rsp+28h] [rbp-B1h]
  struct _tag_FW_ICMP_TYPE_CODE_LIST *v162; // [rsp+28h] [rbp-B1h]
  __int64 v163; // [rsp+38h] [rbp-A1h]
  size_t v164; // [rsp+50h] [rbp-89h] BYREF
  size_t pcchLength; // [rsp+58h] [rbp-81h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+60h] [rbp-79h] BYREF
  unsigned int v167; // [rsp+68h] [rbp-71h] BYREF
  int v168; // [rsp+6Ch] [rbp-6Dh]
  STRSAFE_LPWSTR v169; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v170[2]; // [rsp+78h] [rbp-61h] BYREF
  int v171; // [rsp+80h] [rbp-59h]
  int v172; // [rsp+84h] [rbp-55h]
  _BYTE v173[12]; // [rsp+88h] [rbp-51h] BYREF
  int v174; // [rsp+94h] [rbp-45h]
  unsigned int v175; // [rsp+98h] [rbp-41h]
  unsigned int v176; // [rsp+9Ch] [rbp-3Dh]
  wchar_t *v177; // [rsp+A0h] [rbp-39h]
  wchar_t **v178; // [rsp+A8h] [rbp-31h]
  unsigned __int16 *v179[4]; // [rsp+B0h] [rbp-29h] BYREF
  unsigned __int16 *v180[2]; // [rsp+D0h] [rbp-9h] BYREF
  __int128 v181; // [rsp+E0h] [rbp+7h]
  __int64 v182; // [rsp+F0h] [rbp+17h] BYREF

  v168 = a3;
  *a2 = 0;
  v3 = a1;
  v4 = *((_DWORD *)a1 + 72);
  v178 = a2;
  v169 = a1;
  v167 = 0;
  v182 = 0;
  if ( v4 == 3 || v4 == 2 )
  {
    v5 = 16;
  }
  else
  {
    v5 = 0;
    if ( v4 == 1 )
      v5 = 17;
  }
  v6 = v5 + ((v3[146] & 1) == 0) + 15;
  if ( *((_DWORD *)v3 + 11) == 1 )
  {
    v6 += 10;
  }
  else if ( *((_DWORD *)v3 + 11) == 2 )
  {
    v6 += 11;
  }
  if ( v3[24] != 256 )
    v6 += 18;
  AddressSize = FwRuleGetAddressSize(5u, 5u, (struct _tag_FW_ADDRESSES *)(v3 + 52));
  v8 = FwRuleGetAddressSize(5u, 5u, (struct _tag_FW_ADDRESSES *)(v3 + 88));
  Address2_20Size = FwRuleGetAddress2_20Size(v10, v9, (struct _tag_FW_ADDRESSES *)(v3 + 88));
  v14 = v8
      + Address2_20Size
      + FwRuleGetAddress2_30Size(v13, v12, (struct _tag_FW_ADDRESSES *)(v3 + 88))
      + (unsigned __int64)(unsigned int)(51 * *((_DWORD *)v3 + 120))
      + v6;
  v15 = *((_DWORD *)v3 + 66);
  v16 = AddressSize + v14;
  if ( v15 )
  {
    v151 = (*((_DWORD *)v3 + 66) & 1) + 1;
    if ( (v15 & 2) == 0 )
      v151 = *((_DWORD *)v3 + 66) & 1;
    v152 = v151 + 1;
    if ( (v15 & 4) == 0 )
      v152 = v151;
    v17 = 45 * *((_DWORD *)v3 + 62) + 23 * v152;
  }
  else
  {
    v17 = 45 * *((_DWORD *)v3 + 62);
  }
  v18 = InterfaceTypeEnum2_23;
  v19 = 0;
  v20 = off_18004CD38;
  v21 = 0;
  for ( i = v16 + v17 + 24LL; v21 < v18; ++v21 )
  {
    if ( (v15 & *((_DWORD *)v20 + 4 * v21 + 2)) != 0 )
    {
      v153 = (const unsigned __int16 *)*((_QWORD *)v20 + 2 * v21);
      pcchLength = 0;
      v154 = v19 + 12;
      if ( (int)StringCchLengthW(v153, 260, &pcchLength) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      v19 = pcchLength + 3 + v154;
    }
  }
  AppSize = FwRuleGetAppSize((struct _tag_FW_RULE *)v3, &v167);
  v24 = AppSize;
  if ( AppSize < 0 )
  {
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return v24;
    v150 = 46;
    goto LABEL_240;
  }
  v25 = v19 + i + v167;
  if ( v168 )
  {
LABEL_20:
    v28 = (const wchar_t *)*((_QWORD *)v3 + 37);
    v29 = 0;
    pcchLength = 0;
    if ( v28 )
    {
      v30 = StringLengthWorkerW(v28, 0x2710u, &pcchLength);
      v24 = v30;
      if ( v30 < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          return v24;
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
            (unsigned int)v30);
          v26 = WPP_GLOBAL_Control;
        }
        if ( v26 == (LPCOLESTR)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
          return v24;
        v150 = 48;
        goto LABEL_241;
      }
      v29 = pcchLength + 10;
    }
    v31 = (const wchar_t *)*((_QWORD *)v3 + 38);
    v32 = v29 + v25;
    v33 = 0;
    pcchLength = 0;
    if ( v31 )
    {
      v34 = StringLengthWorkerW(v31, 0x2710u, &pcchLength);
      v24 = v34;
      if ( v34 < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
          return v24;
        if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            14,
            WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
            (unsigned int)v34);
          v26 = WPP_GLOBAL_Control;
        }
        if ( v26 == (LPCOLESTR)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
          return v24;
        v150 = 49;
        goto LABEL_241;
      }
      v33 = pcchLength + 10;
    }
    v35 = (const unsigned __int16 *)*((_QWORD *)v3 + 46);
    v167 = v33;
    v36 = v33;
    if ( (v3[146] & 0x1000) != 0 )
    {
      AppSize = FwRuleGetEncodedStringFieldSize((unsigned int)v31, v35, &v167);
      v24 = AppSize;
      if ( AppSize < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v150 = 50;
          goto LABEL_240;
        }
        return v24;
      }
      goto LABEL_28;
    }
    AppSize = FwRuleGetStringFieldSize(8, v35, &v167);
    v24 = AppSize;
    if ( AppSize >= 0 )
    {
LABEL_28:
      v37 = (const wchar_t *)*((_QWORD *)v3 + 48);
      v38 = v36 + v167 + v32;
      v39 = 0;
      pcchLength = 0;
      if ( v37 )
      {
        v40 = StringLengthWorkerW(v37, 0x2710u, &pcchLength);
        v24 = v40;
        if ( v40 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            return v24;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
              (unsigned int)v40);
            v26 = WPP_GLOBAL_Control;
          }
          if ( v26 == (LPCOLESTR)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
            return v24;
          v150 = 52;
          goto LABEL_241;
        }
        v39 = pcchLength + 9;
      }
      v41 = (const wchar_t *)*((_QWORD *)v3 + 47);
      v42 = v39 + v38;
      v43 = 0;
      pcchLength = 0;
      if ( v41 )
      {
        v44 = StringLengthWorkerW(v41, 0x2710u, &pcchLength);
        v24 = v44;
        if ( v44 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            return v24;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
              (unsigned int)v44);
            v26 = WPP_GLOBAL_Control;
          }
          if ( v26 == (LPCOLESTR)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
            return v24;
          v150 = 53;
          goto LABEL_241;
        }
        v43 = pcchLength + 12;
      }
      v45 = (const wchar_t *)*((_QWORD *)v3 + 39);
      v46 = v43 + v42;
      v47 = 0;
      pcchLength = 0;
      v48 = 13;
      if ( v45 )
      {
        v49 = StringLengthWorkerW(v45, 0x2710u, &pcchLength);
        v24 = v49;
        if ( v49 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            return v24;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
              (unsigned int)v49);
            v26 = WPP_GLOBAL_Control;
          }
          if ( v26 == (LPCOLESTR)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
            return v24;
          v150 = 54;
          goto LABEL_241;
        }
        v47 = pcchLength + 13;
      }
      v50 = (const wchar_t *)*((_QWORD *)v3 + 62);
      v51 = 0;
      v52 = v47 + v46;
      pcchLength = 0;
      if ( v50 )
      {
        v53 = StringLengthWorkerW(v50, 0x2710u, &pcchLength);
        v24 = v53;
        if ( v53 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            return v24;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
              (unsigned int)v53);
            v26 = WPP_GLOBAL_Control;
          }
          if ( v26 == (LPCOLESTR)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
            return v24;
          v150 = 55;
          goto LABEL_241;
        }
        v51 = pcchLength + 7;
      }
      v54 = 0;
      v167 = v51;
      if ( *((_DWORD *)v3 + 10) != 0x7FFFFFFF )
        v54 = *((_DWORD *)v3 + 10);
      LODWORD(pcchLength) = v54;
      v55 = v52 + (unsigned int)FwRuleGetEnumFlagsSize(9, v54, (struct _tag_FW_ENUM *)&ProfileEnum) + v51;
      v170[1] = 11;
      v171 = 11;
      v179[0] = L"LPort=";
      v172 = 11;
      v179[1] = L"LPort2_10=";
      *(_QWORD *)&v173[4] = 11;
      v179[2] = L"LPort2_20=";
      v170[0] = 7;
      v179[3] = L"LPort2_24=";
      v180[0] = L"RPort=";
      v180[1] = L"RPort2_10=";
      v174 = 0;
      v56 = v3[24];
      *(_DWORD *)v173 = 7;
      v181 = 0;
      if ( v56 == 6 || v56 == 17 )
      {
        PortSize = FwRuleGetPortSize((unsigned __int16 **const)6, v170, (struct _tag_FW_PORTS *)(v3 + 28));
        v59 = PortSize + v55 + FwRuleGetPortSize(v58, (unsigned int *)v173, (struct _tag_FW_PORTS *)(v3 + 40));
      }
      else if ( v56 == 1 || v56 == 58 )
      {
        v59 = v55 + (unsigned int)(17 * *((_DWORD *)v3 + 14));
      }
      else
      {
        v59 = v55;
      }
      PlatformValiditySize = FwRuleGetPlatformValiditySize((struct _tag_FW_OS_PLATFORM_LIST *)(v3 + 160));
      v61 = v3[146];
      LODWORD(v164) = PlatformValiditySize;
      v62 = (v61 & 2) != 0 ? 57 : 32;
      if ( (v61 & 4) == 0 )
        v62 = (v61 & 2) != 0 ? 0x19 : 0;
      v63 = v62 + 22;
      if ( (v61 & 0x40) == 0 )
        v63 = v62;
      v64 = v63 + 26;
      if ( (v61 & 0x20) == 0 )
        v64 = v63;
      v65 = v64 + 22;
      if ( (v61 & 0x200) == 0 )
        v65 = v64;
      v66 = -(__int64)((v61 & 8) != 0) & 0xD;
      if ( (v61 & 0x80u) == 0 )
        v48 = (v61 & 0x100) != 0 ? 0xE : 0;
      v67 = *((_DWORD *)v3 + 98);
      *(_QWORD *)v170 = (~v61 & 0x800 | 0x6000uLL) >> 11;
      v68 = (~(_BYTE)v61 & 0x10 | 0xC0uLL) >> 4;
      EnumFlagsSize = FwRuleGetEnumFlagsSize(5, v67, (struct _tag_FW_ENUM *)&TrustTupleKeywordEnum);
      v70 = *((_DWORD *)v3 + 98);
      LODWORD(pszDest) = EnumFlagsSize;
      v71 = FwRuleGetEnumFlagsSize(9, v70, (struct _tag_FW_ENUM *)&TrustTupleKeywordEnum2_22);
      v72 = *((_DWORD *)v3 + 98);
      LODWORD(v177) = v71;
      v73 = FwRuleGetEnumFlagsSize(9, v72, (struct _tag_FW_ENUM *)&TrustTupleKeywordEnum2_27);
      v74 = *((_DWORD *)v3 + 98);
      v176 = v73;
      v175 = FwRuleGetEnumFlagsSize(9, v74, (struct _tag_FW_ENUM *)&TrustTupleKeywordEnum2_28);
      *(_QWORD *)v173 = (v61 & 0x400) != 0 ? 0x1E : 0;
      AppSize = FwRuleGetOnNetworkNamesSize(5u, (struct _tag_FW_NETWORK_NAMES *)(v3 + 200), &v167);
      v24 = AppSize;
      if ( AppSize < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v150 = 56;
          goto LABEL_240;
        }
        return v24;
      }
      v75 = (const wchar_t *)*((_QWORD *)v3 + 52);
      v76 = (unsigned int)pszDest
          + (unsigned int)v177
          + v176
          + v175
          + (unsigned __int64)v65
          + *(_QWORD *)v173
          + (unsigned int)v164
          + v167;
      v77 = 0;
      v164 = 0;
      v78 = v59 + v48 + v66 + v68 + *(_QWORD *)v170 + v76;
      if ( v75 )
      {
        v79 = StringLengthWorkerW(v75, 0x2710u, &v164);
        v24 = v79;
        if ( v79 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            return v24;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
              (unsigned int)v79);
            v26 = WPP_GLOBAL_Control;
          }
          if ( v26 == (LPCOLESTR)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
            return v24;
          v150 = 57;
          goto LABEL_241;
        }
        v77 = v164 + 19;
      }
      v80 = v3[212];
      v167 = v77;
      *(_QWORD *)v170 = v77;
      v81 = (v3[146] & 0x2000) != 0 ? 0xE : 0;
      v82 = (v80 & 1) != 0 ? 0x15 : 0;
      v83 = -(__int64)((v80 & 2) != 0);
      v84 = v80 & 4;
      v85 = v83 & 0x13;
      AppSize = FwRuleGetOnNetworkNamesSize(6u, (struct _tag_FW_NETWORK_NAMES *)(v3 + 216), &v167);
      v24 = AppSize;
      if ( AppSize < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v150 = 58;
          goto LABEL_240;
        }
        return v24;
      }
      v86 = (v3[212] & 0x10) != 0 ? 0xE : 0;
      v87 = v86 + 14;
      if ( (v3[212] & 0x20) == 0 )
        v87 = v86;
      v88 = 0;
      v164 = 0;
      v89 = *(_QWORD *)v170 + v81 + v82 + v85 + v87 + 4 * v84 + v167 + v78;
      v90 = (const wchar_t *)*((_QWORD *)v3 + 56);
      if ( v90 )
      {
        v91 = StringLengthWorkerW(v90, 0x2710u, &v164);
        v24 = v91;
        if ( v91 < 0 )
        {
          v26 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control )
            return v24;
          if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              14,
              WPP_2ae8fc773187333ea3a9c6f2eccd9ab1_Traceguids,
              (unsigned int)v91);
            v26 = WPP_GLOBAL_Control;
          }
          if ( v26 == (LPCOLESTR)&WPP_GLOBAL_Control || (v26[14] & 1) == 0 )
            return v24;
          v150 = 59;
          goto LABEL_241;
        }
        v88 = v164 + 8;
      }
      v92 = ((v3[212] & 0x80u) != 0 ? 32LL : 17LL) + ((v3[212] & 0x100) != 0 ? 15LL : 1LL) + v89 + v88;
      v164 = v92;
      AppSize = FwSizeTMultiply(v92, 2, &v182);
      v24 = AppSize;
      if ( AppSize < 0 )
      {
        v26 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v150 = 60;
          goto LABEL_240;
        }
        return v24;
      }
      v93 = (wchar_t *)FwAlloc(v182);
      v177 = v93;
      if ( v93 )
      {
        v94 = v3[4];
        pszDest = v93;
        if ( (int)StringCchPrintfExW(
                    v93,
                    v92,
                    &pszDest,
                    &v164,
                    0x800u,
                    (wchar_t *)L"v%d.%d%s",
                    v94 >> 8,
                    (unsigned __int8)v94,
                    L"|") < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeAADirProt(pszDest, v164, &pszDest, &v164, (struct _tag_FW_RULE *)v3) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeProfiles(pszDest, v164, &pszDest, &v164, v156, pcchLength) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v95 = v3[24];
        if ( v95 == 6 || v95 == 17 )
        {
          if ( (int)FwRuleSerializePort(pszDest, v164, &pszDest, &v164, v179, (struct _tag_FW_PORTS *)(v3 + 28)) < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          if ( (int)FwRuleSerializePort(pszDest, v164, &pszDest, &v164, v180, (struct _tag_FW_PORTS *)(v3 + 40)) >= 0 )
            goto LABEL_77;
        }
        else if ( v95 == 1 )
        {
          if ( (int)FwRuleSerializeICMP(
                      pszDest,
                      v164,
                      &pszDest,
                      &v164,
                      5u,
                      (struct _tag_FW_ICMP_TYPE_CODE_LIST *)(v3 + 28)) >= 0 )
            goto LABEL_77;
        }
        else if ( v95 != 58
               || (int)FwRuleSerializeICMP(
                         pszDest,
                         v164,
                         &pszDest,
                         &v164,
                         6u,
                         (struct _tag_FW_ICMP_TYPE_CODE_LIST *)(v3 + 28)) >= 0 )
        {
          goto LABEL_77;
        }
        MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_77:
        if ( (int)FwRuleSerializeAddress(
                    pszDest,
                    v164,
                    &pszDest,
                    &v164,
                    L"LA4=",
                    L"LA6=",
                    (struct _tag_FW_ADDRESSES *)(v3 + 52)) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeAddress(
                    pszDest,
                    v164,
                    &pszDest,
                    &v164,
                    L"RA4=",
                    L"RA6=",
                    (struct _tag_FW_ADDRESSES *)(v3 + 88)) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeAddress2_20(
                    pszDest,
                    v164,
                    &pszDest,
                    &v164,
                    v157,
                    (const unsigned __int16 *)v161,
                    (struct _tag_FW_ADDRESSES *)(v3 + 88)) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeAddress2_30(
                    pszDest,
                    v164,
                    &pszDest,
                    &v164,
                    v158,
                    (const unsigned __int16 *)v162,
                    (struct _tag_FW_ADDRESSES *)(v3 + 88)) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeDynamicKeywordAddress(
                    pszDest,
                    v164,
                    &pszDest,
                    &v164,
                    v159,
                    (struct _tag_FW_DYNAMIC_KEYWORD_ADDRESS_ID_LIST *)(v3 + 240)) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeInterfaceTypesAndLUIDs(
                    pszDest,
                    v164,
                    &pszDest,
                    &v164,
                    (struct _tag_FW_INTERFACE_LUIDS *)(v3 + 124),
                    *((_DWORD *)v3 + 66)) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeInterfaceTypes2_23(pszDest, v164, &pszDest, &v164, *((_DWORD *)v3 + 66)) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeApp(pszDest, v164, &pszDest, &v164, v3) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( !v168 && (int)FwRuleSerializeNameDesc(pszDest, v164, &pszDest, &v164, (struct _tag_FW_RULE *)v3) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( *((_QWORD *)v3 + 37) )
        {
          HIDWORD(v163) = HIDWORD(*((_QWORD *)v3 + 37));
          pcchLength = (size_t)pszDest;
          v96 = StringCchPrintfExW(pszDest, v164, (unsigned __int16 **)&pcchLength, &v164, 0x800u, (wchar_t *)L"%s%s%s");
          if ( v96 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v97 = (wchar_t *)pcchLength;
          v98 = v164;
          pszDest = (STRSAFE_LPWSTR)pcchLength;
          if ( v96 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        else
        {
          v98 = v164;
          v97 = pszDest;
        }
        if ( *((_QWORD *)v3 + 38) )
        {
          HIDWORD(v163) = HIDWORD(*((_QWORD *)v3 + 38));
          pcchLength = (size_t)v97;
          v164 = v98;
          v99 = StringCchPrintfExW(v97, v98, (unsigned __int16 **)&pcchLength, &v164, 0x800u, (wchar_t *)L"%s%s%s");
          if ( v99 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v97 = (wchar_t *)pcchLength;
          v98 = v164;
          pszDest = (STRSAFE_LPWSTR)pcchLength;
          if ( v99 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        if ( *((_QWORD *)v3 + 62) )
        {
          HIDWORD(v163) = HIDWORD(*((_QWORD *)v3 + 62));
          pcchLength = (size_t)v97;
          v164 = v98;
          v100 = StringCchPrintfExW(v97, v98, (unsigned __int16 **)&pcchLength, &v164, 0x800u, (wchar_t *)L"%s%s%s");
          if ( v100 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v97 = (wchar_t *)pcchLength;
          v98 = v164;
          pszDest = (STRSAFE_LPWSTR)pcchLength;
          if ( v100 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v101 = *((_QWORD *)v3 + 46);
        if ( (v3[146] & 0x1000) != 0 )
        {
          if ( (int)FwRuleSerializeEncodedStringField(
                      v97,
                      v98,
                      &pszDest,
                      &v164,
                      v160,
                      *((const unsigned __int16 **)v3 + 46)) < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v98 = v164;
          v97 = pszDest;
        }
        else if ( v101 )
        {
          pcchLength = (size_t)v97;
          v164 = v98;
          v102 = StringCchPrintfExW(
                   v97,
                   v98,
                   (unsigned __int16 **)&pcchLength,
                   &v164,
                   0x800u,
                   (wchar_t *)L"%s%s%s",
                   L"LUAuth=",
                   v101,
                   L"|");
          if ( v102 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v97 = (wchar_t *)pcchLength;
          v98 = v164;
          pszDest = (STRSAFE_LPWSTR)pcchLength;
          if ( v102 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v103 = *((_QWORD *)v3 + 48);
        if ( v103 )
        {
          pcchLength = (size_t)v97;
          v164 = v98;
          v104 = StringCchPrintfExW(
                   v97,
                   v98,
                   (unsigned __int16 **)&pcchLength,
                   &v164,
                   0x800u,
                   (wchar_t *)L"%s%s%s",
                   L"LUOwn=",
                   v103,
                   L"|");
          if ( v104 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v97 = (wchar_t *)pcchLength;
          v98 = v164;
          pszDest = (STRSAFE_LPWSTR)pcchLength;
          if ( v104 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v105 = *((_QWORD *)v3 + 47);
        if ( v105 )
        {
          pcchLength = (size_t)v97;
          v164 = v98;
          v106 = StringCchPrintfExW(
                   v97,
                   v98,
                   (unsigned __int16 **)&pcchLength,
                   &v164,
                   0x800u,
                   (wchar_t *)L"%s%s%s",
                   L"AppPkgId=",
                   v105,
                   L"|");
          if ( v106 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v97 = (wchar_t *)pcchLength;
          v98 = v164;
          pszDest = (STRSAFE_LPWSTR)pcchLength;
          if ( v106 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v107 = *((_QWORD *)v3 + 39);
        if ( v107 )
        {
          pcchLength = (size_t)v97;
          v164 = v98;
          v108 = StringCchPrintfExW(
                   v97,
                   v98,
                   (unsigned __int16 **)&pcchLength,
                   &v164,
                   0x800u,
                   (wchar_t *)L"%s%s%s",
                   L"EmbedCtxt=",
                   v107,
                   L"|");
          if ( v108 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v97 = (wchar_t *)pcchLength;
          v98 = v164;
          pszDest = (STRSAFE_LPWSTR)pcchLength;
          if ( v108 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        if ( (int)FwRuleSerializePlatformValidity(
                    v97,
                    v98,
                    &pszDest,
                    &v164,
                    (struct _tag_FW_OS_PLATFORM_LIST *)(v3 + 160)) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeFlag(pszDest, v164, &pszDest, &v164, (struct _tag_FW_RULE *)v3) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v109 = pszDest;
        v110 = v164;
        v111 = 0;
        v112 = (v3[146] & 8) == 0;
        pcchLength = (size_t)pszDest;
        if ( !v112 )
        {
          v111 = StringCchPrintfExW(
                   pszDest,
                   v164,
                   (unsigned __int16 **)&pcchLength,
                   &v164,
                   0x800u,
                   (wchar_t *)L"%s%s%s",
                   L"Edge=",
                   L"TRUE",
                   L"|");
          if ( v111 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v110 = v164;
          v109 = (wchar_t *)pcchLength;
        }
        pszDest = v109;
        v164 = v110;
        if ( v111 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeDeferFlag(v109, v110, &pszDest, &v164, (struct _tag_FW_RULE *)v3) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v112 = (v3[146] & 0x10) == 0;
        v113 = pszDest;
        v114 = v164;
        pcchLength = (size_t)pszDest;
        if ( !v112 )
        {
          if ( (int)StringCchPrintfExW(
                      pszDest,
                      v164,
                      (unsigned __int16 **)&pcchLength,
                      &v164,
                      0x800u,
                      (wchar_t *)L"%s%s%s",
                      L"LSM=",
                      L"TRUE",
                      L"|") < 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v114 = v164;
          v113 = (wchar_t *)pcchLength;
        }
        pcchLength = (size_t)v113;
        v164 = v114;
        if ( (v3[146] & 0x800) != 0 )
        {
          if ( (int)StringCchPrintfExW(
                      v113,
                      v114,
                      (unsigned __int16 **)&pcchLength,
                      &v164,
                      0x800u,
                      (wchar_t *)L"%s%s%s",
                      L"LOM=",
                      L"TRUE",
                      L"|") < 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v114 = v164;
          v113 = (wchar_t *)pcchLength;
        }
        pcchLength = (size_t)v113;
        v164 = v114;
        if ( (v3[146] & 0x400) != 0
          && (int)StringCchPrintfExW(
                    v113,
                    v114,
                    (unsigned __int16 **)&pcchLength,
                    &v164,
                    0x800u,
                    (wchar_t *)L"%s%s%s",
                    L"PCross=",
                    L"TRUE",
                    L"|") < 0 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v115 = TrustTupleKeywordEnum;
        v116 = 0;
        v117 = (wchar_t *)pcchLength;
        v118 = 0;
        v119 = v164;
        v120 = *((_DWORD *)v3 + 98);
        v121 = off_18004CB28;
        v168 = v120;
        if ( TrustTupleKeywordEnum )
        {
          do
          {
            if ( (v120 & *((_DWORD *)v121 + 4 * v118 + 2)) != 0 )
            {
              v116 = StringCchPrintfExW(
                       v117,
                       v119,
                       (unsigned __int16 **)&pcchLength,
                       &v164,
                       0x800u,
                       (wchar_t *)L"%s%s%s",
                       L"TTK=",
                       *((_QWORD *)v121 + 2 * v118),
                       L"|");
              if ( v116 < 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              v120 = v168;
              v119 = v164;
              v117 = (wchar_t *)pcchLength;
            }
            ++v118;
          }
          while ( v118 < v115 );
          v3 = v169;
        }
        if ( v116 < 0 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v122 = TrustTupleKeywordEnum2_22;
        v123 = 0;
        v124 = *((_DWORD *)v3 + 98);
        v125 = 0;
        v126 = off_18004CAE8;
        v168 = v124;
        pcchLength = (size_t)v117;
        v164 = v119;
        if ( TrustTupleKeywordEnum2_22 )
        {
          do
          {
            if ( (v124 & *((_DWORD *)v126 + 4 * v125 + 2)) != 0 )
            {
              v123 = StringCchPrintfExW(
                       v117,
                       v119,
                       (unsigned __int16 **)&pcchLength,
                       &v164,
                       0x800u,
                       (wchar_t *)L"%s%s%s",
                       L"TTK2_22=",
                       *((_QWORD *)v126 + 2 * v125),
                       L"|");
              if ( v123 < 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              v124 = v168;
              v119 = v164;
              v117 = (wchar_t *)pcchLength;
            }
            ++v125;
          }
          while ( v125 < v122 );
          v3 = v169;
        }
        if ( v123 < 0 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v127 = TrustTupleKeywordEnum2_27;
        v128 = 0;
        v129 = *((_DWORD *)v3 + 98);
        v130 = 0;
        v131 = off_18004CAB8;
        v168 = v129;
        pcchLength = (size_t)v117;
        v164 = v119;
        if ( TrustTupleKeywordEnum2_27 )
        {
          do
          {
            if ( (v129 & *((_DWORD *)v131 + 4 * v130 + 2)) != 0 )
            {
              v128 = StringCchPrintfExW(
                       v117,
                       v119,
                       (unsigned __int16 **)&pcchLength,
                       &v164,
                       0x800u,
                       (wchar_t *)L"%s%s%s",
                       L"TTK2_27=",
                       *((_QWORD *)v131 + 2 * v130),
                       L"|");
              if ( v128 < 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              v129 = v168;
              v119 = v164;
              v117 = (wchar_t *)pcchLength;
            }
            ++v130;
          }
          while ( v130 < v127 );
          v3 = v169;
        }
        if ( v128 < 0 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v132 = TrustTupleKeywordEnum2_28;
        v133 = 0;
        v134 = *((_DWORD *)v3 + 98);
        v135 = 0;
        v136 = off_18004CA98;
        v168 = v134;
        pcchLength = (size_t)v117;
        v164 = v119;
        if ( TrustTupleKeywordEnum2_28 )
        {
          do
          {
            if ( (v134 & *((_DWORD *)v136 + 4 * v135 + 2)) != 0 )
            {
              v133 = StringCchPrintfExW(
                       v117,
                       v119,
                       (unsigned __int16 **)&pcchLength,
                       &v164,
                       0x800u,
                       (wchar_t *)L"%s%s%s",
                       L"TTK2_28=",
                       *((_QWORD *)v136 + 2 * v135),
                       L"|");
              if ( v133 < 0 )
                MicrosoftTelemetryAssertTriggeredNoArgs();
              v134 = v168;
              v119 = v164;
              v117 = (wchar_t *)pcchLength;
            }
            ++v135;
          }
          while ( v135 < v132 );
          v3 = v169;
        }
        if ( v133 < 0 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v137 = 0;
        pcchLength = (size_t)v117;
        v138 = 0;
        v164 = v119;
        if ( *((_DWORD *)v3 + 100) )
        {
          do
          {
            v137 = StringCchPrintfExW(
                     v117,
                     v119,
                     (unsigned __int16 **)&pcchLength,
                     &v164,
                     0x800u,
                     (wchar_t *)L"%s%s%s",
                     L"NNm=",
                     *(_QWORD *)(*((_QWORD *)v3 + 51) + 8 * v138),
                     L"|");
            if ( v137 < 0 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v117 = (wchar_t *)pcchLength;
            v138 = (unsigned int)(v138 + 1);
            v119 = v164;
          }
          while ( (unsigned int)v138 < *((_DWORD *)v3 + 100) );
          v3 = v169;
        }
        if ( v137 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v139 = *((_QWORD *)v3 + 52);
        if ( v139 )
        {
          pcchLength = (size_t)v117;
          v164 = v119;
          v140 = StringCchPrintfExW(
                   v117,
                   v119,
                   (unsigned __int16 **)&pcchLength,
                   &v164,
                   0x800u,
                   (wchar_t *)L"%s%s%s",
                   L"SecurityRealmId=",
                   v139,
                   L"|");
          if ( v140 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v117 = (wchar_t *)pcchLength;
          v119 = v164;
          if ( v140 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        pcchLength = (size_t)v117;
        v164 = v119;
        if ( (v3[146] & 0x2000) != 0 )
        {
          if ( (int)StringCchPrintfExW(
                      v117,
                      v119,
                      (unsigned __int16 **)&pcchLength,
                      &v164,
                      0x800u,
                      (wchar_t *)L"%s%s%s",
                      L"BtoIf=",
                      L"TRUE",
                      L"|") < 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v119 = v164;
          v117 = (wchar_t *)pcchLength;
        }
        pcchLength = (size_t)v117;
        v164 = v119;
        if ( (v3[212] & 1) != 0 )
        {
          if ( (int)StringCchPrintfExW(
                      v117,
                      v119,
                      (unsigned __int16 **)&pcchLength,
                      &v164,
                      0x800u,
                      (wchar_t *)L"%s%s%s",
                      L"SytesmOSOnly=",
                      L"TRUE",
                      L"|") < 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v119 = v164;
          v117 = (wchar_t *)pcchLength;
        }
        v112 = (v3[212] & 2) == 0;
        pcchLength = (size_t)v117;
        v164 = v119;
        if ( !v112 )
        {
          if ( (int)StringCchPrintfExW(
                      v117,
                      v119,
                      (unsigned __int16 **)&pcchLength,
                      &v164,
                      0x800u,
                      (wchar_t *)L"%s%s%s",
                      L"GameOSOnly=",
                      L"TRUE",
                      L"|") < 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v119 = v164;
          v117 = (wchar_t *)pcchLength;
        }
        v112 = (v3[212] & 4) == 0;
        pcchLength = (size_t)v117;
        v164 = v119;
        if ( !v112
          && (int)StringCchPrintfExW(
                    v117,
                    v119,
                    (unsigned __int16 **)&pcchLength,
                    &v164,
                    0x800u,
                    (wchar_t *)L"%s%s%s",
                    L"DevMode=",
                    L"TRUE",
                    L"|") < 0 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v141 = (wchar_t *)pcchLength;
        v142 = v164;
        v143 = 0;
        v144 = 0;
        if ( *((_DWORD *)v3 + 108) )
        {
          do
          {
            v143 = StringCchPrintfExW(
                     v141,
                     v142,
                     (unsigned __int16 **)&pcchLength,
                     &v164,
                     0x800u,
                     (wchar_t *)L"%s%s%s",
                     L"RsNm=",
                     *(_QWORD *)(*((_QWORD *)v3 + 55) + 8 * v144),
                     L"|");
            if ( v143 < 0 )
              MicrosoftTelemetryAssertTriggeredNoArgs();
            v141 = (wchar_t *)pcchLength;
            v144 = (unsigned int)(v144 + 1);
            v142 = v164;
          }
          while ( (unsigned int)v144 < *((_DWORD *)v3 + 108) );
          v3 = v169;
        }
        pszDest = v141;
        v164 = v142;
        if ( v143 < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        if ( (int)FwRuleSerializeRemoteNamesFlags(v141, v142, &pszDest, &v164, (struct _tag_FW_RULE *)v3) < 0 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v145 = *((_QWORD *)v3 + 56);
        if ( v145 )
        {
          v169 = pszDest;
          pcchLength = v164;
          v146 = StringCchPrintfExW(
                   pszDest,
                   v164,
                   &v169,
                   &pcchLength,
                   0x800u,
                   (wchar_t *)L"%s%s%s",
                   L"Fqbn=",
                   v145,
                   L"|");
          if ( v146 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
          v147 = v169;
          v148 = pcchLength;
          if ( v146 < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        else
        {
          v148 = v164;
          v147 = pszDest;
        }
        v149 = *((_DWORD *)v3 + 114);
        v169 = v147;
        pcchLength = v148;
        if ( v149 )
        {
          LODWORD(v163) = v149;
          if ( (int)StringCchPrintfExW(
                      v147,
                      v148,
                      &v169,
                      &pcchLength,
                      0x800u,
                      (wchar_t *)L"%s%d%s",
                      L"ComptId=",
                      v163,
                      L"|") < 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v148 = pcchLength;
          v147 = v169;
        }
        v112 = *((_BYTE *)v3 + 424) >= 0;
        v169 = v147;
        pcchLength = v148;
        if ( !v112 )
        {
          if ( (int)StringCchPrintfExW(
                      v147,
                      v148,
                      &v169,
                      &pcchLength,
                      0x800u,
                      (wchar_t *)L"%s%s%s",
                      L"CAudit=",
                      L"TRUE",
                      L"|") < 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
          v148 = pcchLength;
          v147 = v169;
        }
        v24 = 0;
        *(_QWORD *)v173 = v147;
        *(_QWORD *)v170 = v148;
        if ( (v3[212] & 0x100) != 0 )
        {
          v24 = StringCchPrintfExW(
                  v147,
                  v148,
                  (unsigned __int16 **)v173,
                  (unsigned __int64 *)v170,
                  0x800u,
                  (wchar_t *)L"%s%s%s",
                  L"AppLb=",
                  L"TRUE",
                  L"|");
          if ( (v24 & 0x80000000) != 0 )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            MicrosoftTelemetryAssertTriggeredNoArgs();
          }
        }
        *v178 = v177;
        return v24;
      }
      v24 = -2147024882;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        return v24;
      v150 = 61;
LABEL_241:
      v155 = v24;
      goto LABEL_242;
    }
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LPCOLESTR)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      return v24;
    v150 = 51;
LABEL_240:
    v155 = (unsigned int)AppSize;
LABEL_242:
    WPP_SF_d(*((_QWORD *)v26 + 2), v150, WPP_ed13f2d10b38367cf036ad7a217bcc04_Traceguids, v155);
    return v24;
  }
  AppSize = FwRuleGetNameDescSize((struct _tag_FW_RULE *)v3, &v167);
  v24 = AppSize;
  if ( AppSize >= 0 )
  {
    v25 += v167;
    goto LABEL_20;
  }
  v26 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v150 = 47;
    goto LABEL_240;
  }
  return v24;
}

```

## disassembly

```asm
0x18000a328  mov     [rsp-8+arg_10], rbx
0x18000a32d  push    rbp
0x18000a32e  push    rsi
0x18000a32f  push    rdi
0x18000a330  push    r12
0x18000a332  push    r13
0x18000a334  push    r14
0x18000a336  push    r15
0x18000a338  lea     rbp, [rsp-27h]
0x18000a33d  sub     rsp, 100h
0x18000a344  mov     rax, cs:__security_cookie
0x18000a34b  xor     rax, rsp
0x18000a34e  mov     [rbp+57h+var_38], rax
0x18000a352  xor     r13d, r13d
0x18000a355  mov     [rbp+57h+var_C4], r8d
0x18000a359  mov     [rdx], r13
0x18000a35c  mov     r14, rcx
0x18000a35f  mov     eax, [rcx+120h]
0x18000a365  mov     [rbp+57h+var_88], rdx
0x18000a369  mov     [rbp+57h+var_C0], rcx
0x18000a36d  lea     edx, [r13+1]
0x18000a371  mov     [rbp+57h+var_C8], r13d
0x18000a375  lea     r8d, [r13+11h]
0x18000a379  mov     [rbp+57h+var_40], r13
0x18000a37d  cmp     eax, 3
0x18000a380  jnz     loc_18000B4C7
0x18000a386  mov     ecx, 10h
0x18000a38b  movzx   eax, word ptr [r14+124h]
0x18000a393  not     ax
0x18000a396  and     eax, edx
0x18000a398  lea     r15d, [rax+0Fh]
0x18000a39c  add     r15d, ecx
0x18000a39f  cmp     [r14+2Ch], edx
0x18000a3a3  jnz     loc_18000A4E1
0x18000a3a9  add     r15d, 0Ah
0x18000a3ad  mov     eax, 100h
0x18000a3b2  cmp     [r14+30h], ax
0x18000a3b7  jz      short loc_18000A3BD
0x18000a3b9  add     r15d, 12h
0x18000a3bd  mov     ebx, 5
0x18000a3c2  lea     r8, [r14+68h]; struct _tag_FW_ADDRESSES *
0x18000a3c6  mov     edx, ebx; unsigned int
0x18000a3c8  mov     ecx, ebx; unsigned int
0x18000a3ca  call    ?FwRuleGetAddressSize@@YAKKKPEAU_tag_FW_ADDRESSES@@@Z; FwRuleGetAddressSize(ulong,ulong,_tag_FW_ADDRESSES *)
0x18000a3cf  lea     r12, [r14+0B0h]
0x18000a3d6  mov     esi, eax
0x18000a3d8  mov     r8, r12; struct _tag_FW_ADDRESSES *
0x18000a3db  mov     edx, ebx; unsigned int
0x18000a3dd  mov     ecx, ebx; unsigned int
0x18000a3df  call    ?FwRuleGetAddressSize@@YAKKKPEAU_tag_FW_ADDRESSES@@@Z; FwRuleGetAddressSize(ulong,ulong,_tag_FW_ADDRESSES *)
0x18000a3e4  mov     r8, r12; struct _tag_FW_ADDRESSES *
0x18000a3e7  mov     edi, eax
0x18000a3e9  call    ?FwRuleGetAddress2_20Size@@YAKKKPEAU_tag_FW_ADDRESSES@@@Z; FwRuleGetAddress2_20Size(ulong,ulong,_tag_FW_ADDRESSES *)
0x18000a3ee  mov     r8, r12; struct _tag_FW_ADDRESSES *
0x18000a3f1  mov     ebx, eax
0x18000a3f3  call    ?FwRuleGetAddress2_30Size@@YAKKKPEAU_tag_FW_ADDRESSES@@@Z; FwRuleGetAddress2_30Size(ulong,ulong,_tag_FW_ADDRESSES *)
0x18000a3f8  mov     edx, eax
0x18000a3fa  imul    eax, [r14+1E0h], 33h ; '3'
0x18000a402  mov     r9d, r15d
0x18000a405  add     rax, rdx
0x18000a408  imul    edx, [r14+0F8h], 2Dh ; '-'
0x18000a410  add     r9, rax
0x18000a413  add     r9, rbx
0x18000a416  add     r9, rdi
0x18000a419  mov     edi, [r14+108h]
0x18000a420  add     r9, rsi
0x18000a423  test    edi, edi
0x18000a425  jnz     loc_18000B819
0x18000a42b  mov     ecx, edx
0x18000a42d  mov     r15d, cs:?InterfaceTypeEnum2_23@@3U_tag_FW_ENUM@@A; _tag_FW_ENUM InterfaceTypeEnum2_23
0x18000a434  xor     esi, esi
0x18000a436  mov     r12, cs:off_18004CD38
0x18000a43d  xor     ebx, ebx
0x18000a43f  mov     r13d, ecx
0x18000a442  add     r13, 18h
0x18000a446  add     r13, r9
0x18000a449  test    r15d, r15d
0x18000a44c  jz      short loc_18000A465
0x18000a44e  mov     ecx, ebx
0x18000a450  add     rcx, rcx
0x18000a453  test    [r12+rcx*8+8], edi
0x18000a458  jnz     loc_18000B83C
0x18000a45e  inc     ebx
0x18000a460  cmp     ebx, r15d
0x18000a463  jb      short loc_18000A44E
0x18000a465  lea     rdx, [rbp+57h+var_C8]; unsigned int *
0x18000a469  mov     rcx, r14; struct _tag_FW_RULE *
0x18000a46c  call    ?FwRuleGetAppSize@@YAJPEAU_tag_FW_RULE@@PEAK@Z; FwRuleGetAppSize(_tag_FW_RULE *,ulong *)
0x18000a471  mov     ebx, eax
0x18000a473  test    eax, eax
0x18000a475  js      loc_18000B872
0x18000a47b  mov     edi, [rbp+57h+var_C8]
0x18000a47e  add     rdi, r13
0x18000a481  mov     ecx, esi
0x18000a483  add     rdi, rcx
0x18000a486  cmp     [rbp+57h+var_C4], 0
0x18000a48a  mov     rsi, rdi
0x18000a48d  jnz     short loc_18000A4FB
0x18000a48f  lea     rdx, [rbp+57h+var_C8]; unsigned int *
0x18000a493  mov     rcx, r14; struct _tag_FW_RULE *
0x18000a496  call    ?FwRuleGetNameDescSize@@YAJPEAU_tag_FW_RULE@@PEAK@Z; FwRuleGetNameDescSize(_tag_FW_RULE *,ulong *)
0x18000a49b  mov     ebx, eax
0x18000a49d  test    eax, eax
0x18000a49f  jns     short loc_18000A4F5
0x18000a4a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4a8  lea     rdi, WPP_GLOBAL_Control
0x18000a4af  cmp     rcx, rdi
0x18000a4b2  jnz     loc_18000B8C1
0x18000a4b8  mov     eax, ebx
0x18000a4ba  mov     rcx, [rbp+57h+var_38]
0x18000a4be  xor     rcx, rsp; StackCookie
0x18000a4c1  call    __security_check_cookie
0x18000a4c6  mov     rbx, [rsp+130h+arg_10]
0x18000a4ce  add     rsp, 100h
0x18000a4d5  pop     r15
0x18000a4d7  pop     r14
0x18000a4d9  pop     r13
0x18000a4db  pop     r12
0x18000a4dd  pop     rdi
0x18000a4de  pop     rsi
0x18000a4df  pop     rbp
0x18000a4e0  retn
0x18000a4e1  cmp     dword ptr [r14+2Ch], 2
0x18000a4e6  jnz     loc_18000A3AD
0x18000a4ec  add     r15d, 0Bh
0x18000a4f0  jmp     loc_18000A3AD
0x18000a4f5  mov     edi, [rbp+57h+var_C8]
0x18000a4f8  add     rdi, rsi
0x18000a4fb  mov     rcx, [r14+128h]; psz
0x18000a502  xor     eax, eax
0x18000a504  mov     [rsp+130h+pcchLength], rax
0x18000a509  mov     r12d, 2710h
0x18000a50f  test    rcx, rcx
0x18000a512  jz      short loc_18000A534
0x18000a514  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x18000a519  mov     edx, r12d; cchMax
0x18000a51c  call    StringLengthWorkerW
0x18000a521  mov     ebx, eax
0x18000a523  test    eax, eax
0x18000a525  js      loc_18000B8D2
0x18000a52b  mov     rax, [rsp+130h+pcchLength]
0x18000a530  add     rax, 0Ah
0x18000a534  mov     rcx, [r14+130h]; psz
0x18000a53b  mov     eax, eax
0x18000a53d  add     rdi, rax
0x18000a540  xor     eax, eax
0x18000a542  mov     [rsp+130h+pcchLength], rax
0x18000a547  test    rcx, rcx
0x18000a54a  jz      short loc_18000A56C
0x18000a54c  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x18000a551  mov     rdx, r12; cchMax
0x18000a554  call    StringLengthWorkerW
0x18000a559  mov     ebx, eax
0x18000a55b  test    eax, eax
0x18000a55d  js      loc_18000B923
0x18000a563  mov     rax, [rsp+130h+pcchLength]
0x18000a568  add     rax, 0Ah
0x18000a56c  mov     rdx, [r14+170h]; unsigned __int16 *
0x18000a573  lea     r8, [rbp+57h+var_C8]; unsigned int *
0x18000a577  mov     [rbp+57h+var_C8], eax
0x18000a57a  mov     esi, eax
0x18000a57c  mov     eax, 1000h
0x18000a581  test    [r14+124h], ax
0x18000a589  jz      loc_18000B4DE
0x18000a58f  call    ?FwRuleGetEncodedStringFieldSize@@YAJKPEBGPEAK@Z; FwRuleGetEncodedStringFieldSize(ulong,ushort const *,ulong *)
0x18000a594  mov     ebx, eax
0x18000a596  test    eax, eax
0x18000a598  js      loc_18000B97C
0x18000a59e  mov     eax, [rbp+57h+var_C8]
0x18000a5a1  mov     rcx, [r14+180h]; psz
0x18000a5a8  add     rax, rsi
0x18000a5ab  add     rdi, rax
0x18000a5ae  xor     eax, eax
0x18000a5b0  mov     [rsp+130h+pcchLength], rax
0x18000a5b5  test    rcx, rcx
0x18000a5b8  jz      short loc_18000A5DA
0x18000a5ba  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x18000a5bf  mov     rdx, r12; cchMax
0x18000a5c2  call    StringLengthWorkerW
0x18000a5c7  mov     ebx, eax
0x18000a5c9  test    eax, eax
0x18000a5cb  js      loc_18000B9A7
0x18000a5d1  mov     rax, [rsp+130h+pcchLength]
0x18000a5d6  add     rax, 9
0x18000a5da  mov     rcx, [r14+178h]; psz
0x18000a5e1  mov     eax, eax
0x18000a5e3  add     rdi, rax
0x18000a5e6  xor     eax, eax
0x18000a5e8  mov     [rsp+130h+pcchLength], rax
0x18000a5ed  test    rcx, rcx
0x18000a5f0  jz      short loc_18000A612
0x18000a5f2  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x18000a5f7  mov     rdx, r12; cchMax
0x18000a5fa  call    StringLengthWorkerW
0x18000a5ff  mov     ebx, eax
0x18000a601  test    eax, eax
0x18000a603  js      loc_18000BA00
0x18000a609  mov     rax, [rsp+130h+pcchLength]
0x18000a60e  add     rax, 0Ch
0x18000a612  mov     rcx, [r14+138h]; psz
0x18000a619  mov     eax, eax
0x18000a61b  add     rdi, rax
0x18000a61e  xor     eax, eax
0x18000a620  mov     [rsp+130h+pcchLength], rax
0x18000a625  lea     r15d, [rax+0Dh]
0x18000a629  test    rcx, rcx
0x18000a62c  jz      short loc_18000A64D
0x18000a62e  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x18000a633  mov     rdx, r12; cchMax
0x18000a636  call    StringLengthWorkerW
0x18000a63b  mov     ebx, eax
0x18000a63d  test    eax, eax
0x18000a63f  js      loc_18000BA45
0x18000a645  mov     rax, [rsp+130h+pcchLength]
0x18000a64a  add     rax, r15
0x18000a64d  mov     rcx, [r14+1F0h]; psz
0x18000a654  xor     ebx, ebx
0x18000a656  mov     eax, eax
0x18000a658  add     rdi, rax
0x18000a65b  mov     [rsp+130h+pcchLength], rbx
0x18000a660  test    rcx, rcx
0x18000a663  jz      short loc_18000A685
0x18000a665  lea     r8, [rsp+130h+pcchLength]; pcchLength
0x18000a66a  mov     rdx, r12; cchMax
0x18000a66d  call    StringLengthWorkerW
0x18000a672  mov     ebx, eax
0x18000a674  test    eax, eax
0x18000a676  js      loc_18000BA9E
0x18000a67c  mov     rbx, [rsp+130h+pcchLength]
0x18000a681  add     rbx, 7
0x18000a685  xor     eax, eax
0x18000a687  mov     [rbp+57h+var_C8], ebx
0x18000a68a  cmp     dword ptr [r14+28h], 7FFFFFFFh
0x18000a692  lea     r8, ?ProfileEnum@@3U_tag_FW_ENUM@@A; struct _tag_FW_ENUM *
0x18000a699  mov     ecx, 9; unsigned int
0x18000a69e  cmovnz  eax, [r14+28h]
0x18000a6a3  mov     edx, eax; unsigned int
0x18000a6a5  mov     dword ptr [rsp+130h+pcchLength], eax
0x18000a6a9  call    ?FwRuleGetEnumFlagsSize@@YAKKKPEAU_tag_FW_ENUM@@@Z; FwRuleGetEnumFlagsSize(ulong,ulong,_tag_FW_ENUM *)
0x18000a6ae  mov     eax, eax
0x18000a6b0  mov     ecx, 0Bh
0x18000a6b5  add     rax, rdi
0x18000a6b8  mov     esi, ebx
0x18000a6ba  add     rsi, rax
0x18000a6bd  mov     [rbp+57h+var_B8+4], ecx
0x18000a6c0  lea     rax, aLport; "LPort="
0x18000a6c7  mov     [rbp+57h+var_B0], ecx
0x18000a6ca  mov     [rbp+57h+var_80], rax
0x18000a6ce  lea     edx, [rcx+2Fh]
0x18000a6d1  lea     rax, aLport210; "LPort2_10="
0x18000a6d8  mov     [rbp+57h+var_AC], ecx
0x18000a6db  mov     [rbp+57h+var_78], rax
0x18000a6df  xorps   xmm0, xmm0
0x18000a6e2  lea     rax, aLport220; "LPort2_20="
0x18000a6e9  mov     qword ptr [rbp+57h+var_A8+4], rcx
0x18000a6ed  mov     [rbp+57h+var_70], rax
0x18000a6f1  lea     ecx, [rdx-34h]; unsigned __int16 **
0x18000a6f4  lea     rax, aLport224; "LPort2_24="
0x18000a6fb  mov     [rbp+57h+var_B8], 7
0x18000a702  mov     [rbp+57h+var_68], rax
0x18000a706  lea     rax, aRport; "RPort="
0x18000a70d  mov     [rbp+57h+var_60], rax
0x18000a711  lea     rax, aRport210; "RPort2_10="
0x18000a718  mov     [rbp+57h+var_58], rax
0x18000a71c  xor     eax, eax
0x18000a71e  mov     [rbp+57h+var_9C], eax
0x18000a721  movzx   eax, word ptr [r14+30h]
0x18000a726  mov     dword ptr [rbp+57h+var_A8], 7
0x18000a72d  movdqu  [rbp+57h+var_50], xmm0
0x18000a732  cmp     ax, cx
0x18000a735  jnz     loc_18000B51D
0x18000a73b  lea     r8, [r14+38h]; struct _tag_FW_PORTS *
0x18000a73f  lea     rdx, [rbp+57h+var_B8]; unsigned int *
0x18000a743  call    ?FwRuleGetPortSize@@YAKQEAPEAGPEAKPEAU_tag_FW_PORTS@@@Z; FwRuleGetPortSize(ushort * * const,ulong *,_tag_FW_PORTS *)
0x18000a748  lea     r8, [r14+50h]; struct _tag_FW_PORTS *
0x18000a74c  mov     ebx, eax
0x18000a74e  lea     rdx, [rbp+57h+var_A8]; unsigned int *
0x18000a752  call    ?FwRuleGetPortSize@@YAKQEAPEAGPEAKPEAU_tag_FW_PORTS@@@Z; FwRuleGetPortSize(ushort * * const,ulong *,_tag_FW_PORTS *)
0x18000a757  mov     edi, eax
0x18000a759  add     rdi, rsi
0x18000a75c  add     rdi, rbx
0x18000a75f  lea     rcx, [r14+140h]; struct _tag_FW_OS_PLATFORM_LIST *
0x18000a766  call    ?FwRuleGetPlatformValiditySize@@YAKPEAU_tag_FW_OS_PLATFORM_LIST@@@Z; FwRuleGetPlatformValiditySize(_tag_FW_OS_PLATFORM_LIST *)
0x18000a76b  movzx   ebx, word ptr [r14+124h]
0x18000a773  mov     dword ptr [rsp+130h+var_E0], eax
0x18000a777  mov     cl, bl
0x18000a779  and     cl, 2
0x18000a77c  neg     cl
0x18000a77e  sbb     edx, edx
0x18000a780  and     edx, 19h
0x18000a783  test    bl, 4
0x18000a786  lea     ecx, [rdx+20h]
0x18000a789  cmovz   ecx, edx
0x18000a78c  test    bl, 40h
0x18000a78f  lea     eax, [rcx+16h]
0x18000a792  cmovz   eax, ecx
0x18000a795  test    bl, 20h
0x18000a798  lea     ecx, [rax+1Ah]
0x18000a79b  cmovz   ecx, eax
0x18000a79e  mov     eax, 200h
  ... truncated ...
```
