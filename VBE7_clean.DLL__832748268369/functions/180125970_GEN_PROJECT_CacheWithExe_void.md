# GEN_PROJECT::CacheWithExe(void)

- ea: `0x180125970`
- end: `0x1801272ab`
- name: `?CacheWithExe@GEN_PROJECT@@QEAAJXZ`
- size: `6459`
- prototype: `__int64 __fastcall(wchar_t **this)`
- caller_count: `1`
- callee_count: `58`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801272b4`

## callees

- `0x18000452c`
- `0x180024510`
- `0x18002be9c`
- `0x18008392c`
- `0x1800e62d4`
- `0x1800e64cc`
- `0x1800e64dc`
- `0x1800e8904`
- `0x1800ec670`
- `0x1800f0a7c`
- `0x180107250`
- `0x180119008`
- `0x18011d9b0`
- `0x18011d9e8`
- `0x18011d9fc`
- `0x18011da14`
- `0x18011da24`
- `0x18011da30`
- `0x18011da5c`
- `0x18011db08`
- `0x18011fd14`
- `0x18011fda8`
- `0x180125970`
- `0x180129f84`
- `0x18013307c`
- `0x180133090`
- `0x1801330a4`
- `0x1801330b8`
- `0x1801330f4`
- `0x180133130`
- `0x18013316c`
- `0x1801331a8`
- `0x1801331bc`
- `0x1801331cc`
- `0x180134fe8`
- `0x1801426d8`
- `0x18014275c`
- `0x180144cb0`
- `0x180144e00`
- `0x1801487bc`
- `0x180148de0`
- `0x18014f0b0`
- `0x18014fae4`
- `0x18015e6e0`
- `0x180164328`
- `0x180164a18`
- `0x1801653d0`
- `0x1801658ec`
- `0x18017a42c`
- `0x18017ea20`

## import_xrefs

- `MSVCR100!_mbscpy_s` at `0x180126292`
- `MSVCR100!_mbscpy_s` at `0x1801269ca`
- `MSVCR100!_mbscpy_s` at `0x180126292`
- `MSVCR100!_mbscpy_s` at `0x1801269ca`
- `KERNEL32!_lread` at `0x1801263e2`
- `KERNEL32!_lread` at `0x18012647f`
- `KERNEL32!_lread` at `0x180126a86`
- `KERNEL32!_lread` at `0x180126b33`
- `KERNEL32!_lread` at `0x1801263e2`
- `KERNEL32!_lread` at `0x18012647f`
- `KERNEL32!_lread` at `0x180126a86`
- `KERNEL32!_lread` at `0x180126b33`
- `KERNEL32!_llseek` at `0x1801263c5`
- `KERNEL32!_llseek` at `0x180126a65`
- `KERNEL32!_llseek` at `0x1801263c5`
- `KERNEL32!_llseek` at `0x180126a65`
- `KERNEL32!WideCharToMultiByte` at `0x180126232`
- `KERNEL32!WideCharToMultiByte` at `0x1801262d2`
- `KERNEL32!WideCharToMultiByte` at `0x18012696a`
- `KERNEL32!WideCharToMultiByte` at `0x180126a0a`
- `KERNEL32!WideCharToMultiByte` at `0x180126232`
- `KERNEL32!WideCharToMultiByte` at `0x1801262d2`
- `KERNEL32!WideCharToMultiByte` at `0x18012696a`
- `KERNEL32!WideCharToMultiByte` at `0x180126a0a`
- `KERNEL32!_lclose` at `0x180127091`
- `KERNEL32!_lclose` at `0x1801271cc`
- `KERNEL32!_lclose` at `0x180127091`
- `KERNEL32!_lclose` at `0x1801271cc`
- `OLEAUT32!__imp_SysFreeString` at `0x180126263`
- `OLEAUT32!__imp_SysFreeString` at `0x1801262e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18012699b`
- `OLEAUT32!__imp_SysFreeString` at `0x180126a18`
- `OLEAUT32!__imp_SysFreeString` at `0x180127040`
- `OLEAUT32!__imp_SysFreeString` at `0x180127176`
- `OLEAUT32!__imp_SysFreeString` at `0x1801271ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1801271bb`
- `OLEAUT32!__imp_SysFreeString` at `0x180126263`
- `OLEAUT32!__imp_SysFreeString` at `0x1801262e0`
- `OLEAUT32!__imp_SysFreeString` at `0x18012699b`
- `OLEAUT32!__imp_SysFreeString` at `0x180126a18`
- `OLEAUT32!__imp_SysFreeString` at `0x180127040`
- `OLEAUT32!__imp_SysFreeString` at `0x180127176`
- `OLEAUT32!__imp_SysFreeString` at `0x1801271ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1801271bb`

## pseudocode

```c
__int64 __fastcall GEN_PROJECT::CacheWithExe(wchar_t **this)
{
  const wchar_t *v1; // rdx
  const wchar_t *v2; // r8
  unsigned int v3; // r9d
  GENPROJ_TYPEBIND *v4; // rax
  unsigned int v5; // eax
  void **v6; // rdx
  void **v7; // r8
  int v8; // r9d
  struct INSTMGR *v9; // rax
  serProcTemplate *v10; // rax
  RESDESC *v11; // rax
  unsigned int v12; // eax
  struct IMPMGR *v13; // rax
  struct _GUID *Guid; // rax
  struct _GUID *v15; // rax
  unsigned int v17; // eax
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-430h]
  LPSTR lpMultiByteStra; // [rsp+20h] [rbp-430h]
  struct _msotcr *lpDefaultChar; // [rsp+30h] [rbp-420h]
  struct IMsoToolbar *lpUsedDefaultChar; // [rsp+38h] [rbp-418h]
  int GdtiOfItyp; // [rsp+40h] [rbp-410h]
  int v23; // [rsp+40h] [rbp-410h]
  unsigned int v24; // [rsp+44h] [rbp-40Ch]
  unsigned int v25; // [rsp+44h] [rbp-40Ch]
  HFILE hFile; // [rsp+48h] [rbp-408h] BYREF
  struct BASIC_TYPEINFO *v27; // [rsp+50h] [rbp-400h] BYREF
  struct ITypeInfo *v28; // [rsp+58h] [rbp-3F8h] BYREF
  unsigned int j; // [rsp+60h] [rbp-3F0h]
  struct ITypeLib *v30; // [rsp+68h] [rbp-3E8h] BYREF
  __int64 v31; // [rsp+70h] [rbp-3E0h] BYREF
  struct INSTMGR *v32; // [rsp+78h] [rbp-3D8h]
  UINT uBytes; // [rsp+80h] [rbp-3D0h] BYREF
  BOOL v34; // [rsp+84h] [rbp-3CCh]
  int v35; // [rsp+88h] [rbp-3C8h]
  BOOL v36; // [rsp+8Ch] [rbp-3C4h]
  LPCWCH v37; // [rsp+90h] [rbp-3C0h] BYREF
  BOOL v38; // [rsp+98h] [rbp-3B8h]
  int v39; // [rsp+9Ch] [rbp-3B4h]
  LPCWCH lpWideCharStr; // [rsp+A0h] [rbp-3B0h] BYREF
  REC_TYPEINFO *v41; // [rsp+A8h] [rbp-3A8h]
  unsigned __int64 v42; // [rsp+B0h] [rbp-3A0h]
  TYPE_DATA *v43; // [rsp+B8h] [rbp-398h]
  unsigned __int64 v44; // [rsp+C0h] [rbp-390h]
  __int64 v45; // [rsp+C8h] [rbp-388h] BYREF
  __int64 v46; // [rsp+D0h] [rbp-380h] BYREF
  DEFN *v47; // [rsp+D8h] [rbp-378h]
  LONG lOffset; // [rsp+E0h] [rbp-370h] BYREF
  unsigned int v49; // [rsp+E4h] [rbp-36Ch]
  unsigned int v50; // [rsp+E8h] [rbp-368h]
  unsigned int v51; // [rsp+ECh] [rbp-364h] BYREF
  unsigned int v52; // [rsp+F0h] [rbp-360h]
  LONG v53; // [rsp+F4h] [rbp-35Ch] BYREF
  unsigned int v55; // [rsp+FCh] [rbp-354h]
  unsigned int v56; // [rsp+100h] [rbp-350h]
  NAMMGR *v57; // [rsp+108h] [rbp-348h]
  GENPROJ_BINDNAME_TABLE *v58; // [rsp+110h] [rbp-340h]
  BASIC_TYPEROOT *v59; // [rsp+118h] [rbp-338h]
  struct DEFN_TYPEBIND *v60; // [rsp+120h] [rbp-330h] BYREF
  GENPROJ_BIND_DESC *v61; // [rsp+128h] [rbp-328h]
  __int64 v62; // [rsp+130h] [rbp-320h] BYREF
  LPCWCH v63; // [rsp+138h] [rbp-318h]
  struct GEN_PROJECT *v64; // [rsp+140h] [rbp-310h]
  wchar_t *v65; // [rsp+148h] [rbp-308h]
  __int64 v66; // [rsp+150h] [rbp-300h]
  BSTR v67; // [rsp+158h] [rbp-2F8h]
  __int64 v68; // [rsp+160h] [rbp-2F0h]
  BSTR v69; // [rsp+168h] [rbp-2E8h]
  BASIC_TYPEROOT *v70; // [rsp+170h] [rbp-2E0h]
  __int64 v71; // [rsp+178h] [rbp-2D8h]
  __int64 v72; // [rsp+180h] [rbp-2D0h]
  BASIC_TYPEROOT *v73; // [rsp+188h] [rbp-2C8h]
  BASIC_TYPEROOT *v74; // [rsp+190h] [rbp-2C0h]
  __int64 v75; // [rsp+198h] [rbp-2B8h]
  BASIC_TYPEROOT *v76; // [rsp+1A0h] [rbp-2B0h]
  BASIC_TYPEROOT *v77; // [rsp+1A8h] [rbp-2A8h]
  __int64 v78; // [rsp+1B0h] [rbp-2A0h]
  struct BASIC_TYPEINFO *v79; // [rsp+1B8h] [rbp-298h]
  BASIC_TYPEROOT *v80; // [rsp+1C0h] [rbp-290h]
  BASIC_TYPEROOT *v81; // [rsp+1C8h] [rbp-288h]
  BASIC_TYPEROOT *v82; // [rsp+1D0h] [rbp-280h]
  __int64 v83; // [rsp+1D8h] [rbp-278h]
  BASIC_TYPEROOT *v84; // [rsp+1E0h] [rbp-270h]
  BASIC_TYPEROOT *v85; // [rsp+1E8h] [rbp-268h]
  CMsoToolbarUser *v86; // [rsp+1F0h] [rbp-260h]
  BASIC_TYPEROOT *v87; // [rsp+1F8h] [rbp-258h]
  BASIC_TYPEROOT *v88; // [rsp+200h] [rbp-250h]
  BASIC_TYPEROOT *v89; // [rsp+208h] [rbp-248h]
  LPCWCH v90; // [rsp+210h] [rbp-240h]
  BASIC_TYPEROOT *v91; // [rsp+218h] [rbp-238h]
  struct ITypeInfo *v92; // [rsp+220h] [rbp-230h] BYREF
  BASIC_TYPEROOT *v93; // [rsp+228h] [rbp-228h]
  BASIC_TYPEROOT *v94; // [rsp+230h] [rbp-220h]
  BASIC_TYPEROOT *v95; // [rsp+238h] [rbp-218h]
  BASIC_TYPEROOT *v96; // [rsp+240h] [rbp-210h]
  __int64 v97; // [rsp+248h] [rbp-208h]
  struct _GUID v98; // [rsp+250h] [rbp-200h] BYREF
  struct _GUID v99; // [rsp+260h] [rbp-1F0h]
  __int64 v100; // [rsp+270h] [rbp-1E0h]
  struct _GUID v101; // [rsp+278h] [rbp-1D8h]
  struct _GUID v102; // [rsp+290h] [rbp-1C0h] BYREF
  struct _GUID v103; // [rsp+2A0h] [rbp-1B0h] BYREF
  struct _GUID v104; // [rsp+2B0h] [rbp-1A0h] BYREF
  _BYTE v105[32]; // [rsp+2C0h] [rbp-190h] BYREF
  struct _GUID v106; // [rsp+2E0h] [rbp-170h]
  __int64 v107; // [rsp+2F0h] [rbp-160h]
  struct _GUID v108; // [rsp+2F8h] [rbp-158h]
  __int128 v109; // [rsp+308h] [rbp-148h]
  __int16 v110; // [rsp+318h] [rbp-138h] BYREF
  int v111; // [rsp+320h] [rbp-130h]
  _BYTE v112[32]; // [rsp+330h] [rbp-120h] BYREF
  struct _GUID v113; // [rsp+350h] [rbp-100h] BYREF
  struct _GUID v114; // [rsp+360h] [rbp-F0h] BYREF
  struct _GUID v115; // [rsp+370h] [rbp-E0h] BYREF
  _IMAGE_DOS_HEADER v116; // [rsp+380h] [rbp-D0h] BYREF
  int v117; // [rsp+3C0h] [rbp-90h]
  BSTR bstrString; // [rsp+3C8h] [rbp-88h] BYREF
  UINT Buffer; // [rsp+3D0h] [rbp-80h] BYREF
  int v120; // [rsp+3D4h] [rbp-7Ch]
  UINT *v121; // [rsp+3D8h] [rbp-78h]
  char *v122; // [rsp+3E0h] [rbp-70h] BYREF
  struct INSTMGR *v123; // [rsp+3E8h] [rbp-68h]
  BASIC_TYPEINFO *v124; // [rsp+3F0h] [rbp-60h] BYREF
  unsigned int i; // [rsp+3F8h] [rbp-58h]
  unsigned int m; // [rsp+3FCh] [rbp-54h]
  unsigned int k; // [rsp+400h] [rbp-50h]
  struct BASIC_TYPEINFO *v128; // [rsp+408h] [rbp-48h] BYREF
  unsigned __int8 *Dst; // [rsp+410h] [rbp-40h]
  REC_TYPEINFO *v130; // [rsp+418h] [rbp-38h] BYREF
  char *v131; // [rsp+420h] [rbp-30h]
  int v132; // [rsp+428h] [rbp-28h]
  int v133; // [rsp+42Ch] [rbp-24h]
  int cbMultiByte; // [rsp+430h] [rbp-20h]
  unsigned int v135; // [rsp+434h] [rbp-1Ch]
  unsigned int v136; // [rsp+438h] [rbp-18h]
  int v137; // [rsp+43Ch] [rbp-14h]
  int v138; // [rsp+440h] [rbp-10h]
  size_t SizeInBytes; // [rsp+444h] [rbp-Ch]

  v67 = 0;
  v69 = 0;
  v122 = 0;
  v117 = 0;
  hFile = -1;
  v49 = (*((__int64 (__fastcall **)(wchar_t **))*this + 3))(this);
  for ( i = 0; i < v49; ++i )
  {
    GdtiOfItyp = GEN_PROJECT::GetGdtiOfItyp((GEN_PROJECT *)this, i, &v128);
    if ( GdtiOfItyp < 0 )
      goto LABEL_162;
    v79 = v128;
    BASIC_TYPEROOT::EnsureInSemiDeclaredState(*((BASIC_TYPEROOT **)v128 + 5), 0);
    v82 = (BASIC_TYPEROOT *)*((_QWORD *)v128 + 5);
    if ( BASIC_TYPEROOT::Typekind(v82) == TKIND_MAX )
    {
      v66 = *((_QWORD *)v128 + 5);
      if ( (int)BASIC_TYPEROOT::CompState(v66) < 2 )
      {
        v103 = GUID_NULL;
        v84 = (BASIC_TYPEROOT *)*((_QWORD *)v128 + 5);
        BASIC_TYPEROOT::SetCLSID(v84, &v103);
      }
    }
    (*(void (__fastcall **)(struct BASIC_TYPEINFO *))(*(_QWORD *)v128 + 16LL))(v128);
  }
  CMsoDropdownUser::Dropping((const wchar_t *)this, v1, v2, v3, (uintptr_t)lpMultiByteStr);
  v57 = GEN_PROJECT::Pnammgr((GEN_PROJECT *)this);
  v4 = GEN_PROJECT::Pgptbind((GEN_PROJECT *)this);
  v58 = GENPROJ_TYPEBIND::Pgbindnametbl(v4);
  if ( (unsigned int)ErrOpen(this[720], &hFile) )
  {
    GdtiOfItyp = -2146787930;
LABEL_162:
    if ( hFile != -1 )
      _lclose(hFile);
LABEL_164:
    for ( j = 0; ; ++j )
    {
      v17 = (*((__int64 (__fastcall **)(wchar_t **))*this + 3))(this);
      if ( j >= v17 )
        break;
      if ( *((_QWORD *)GEN_PROJECT::Qte((GEN_PROJECT *)this, j) + 1) )
      {
        v71 = *((_QWORD *)GEN_PROJECT::Qte((GEN_PROJECT *)this, j) + 1);
        v73 = *(BASIC_TYPEROOT **)(v71 + 40);
        BASIC_TYPEROOT::SetPtinfoEquiv(v73, 0);
        v75 = *((_QWORD *)GEN_PROJECT::Qte((GEN_PROJECT *)this, j) + 1);
        v77 = *(BASIC_TYPEROOT **)(v75 + 40);
        BASIC_TYPEROOT::SetPtinfoEquivCoclass(v77, 0);
      }
    }
    return (unsigned int)GdtiOfItyp;
  }
  if ( !(unsigned int)FIsExe(hFile, &v116) )
  {
    GdtiOfItyp = -2146787930;
    goto LABEL_162;
  }
  if ( !(unsigned int)IsVBExe(hFile, "_IID_", &v116) )
  {
    GdtiOfItyp = -2146787930;
    goto LABEL_162;
  }
  GdtiOfItyp = LoadTypeLibExWrap(this[720], 2, &v30);
  if ( GdtiOfItyp < 0 )
    goto LABEL_162;
  *((_DWORD *)this + 1486) = 0;
  if ( ((__int64 (__fastcall *)(struct ITypeLib *, GUID *, __int64 *))v30->lpVtbl->QueryInterface)(
         v30,
         &IID_ITypeLib2,
         &v46) >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, GUID *, __int16 *))(*(_QWORD *)v46 + 104LL))(
           v46,
           &GUID_FuncCustDataReturnErrors,
           &v110) >= 0
      && v110 == 3 )
    {
      *((_DWORD *)this + 1486) = v111;
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v36 = *((_DWORD *)this + 1486) == 0;
  *((_DWORD *)this + 78) = (v36 << 7) | (_DWORD)this[39] & 0xFFFFFF7F;
  v52 = ((__int64 (__fastcall *)(struct ITypeLib *))v30->lpVtbl->GetTypeInfoCount)(v30);
  for ( j = 0; j < v52; ++j )
  {
    v56 = 0;
    GdtiOfItyp = ((__int64 (__fastcall *)(struct ITypeLib *, _QWORD, struct ITypeInfo **))v30->lpVtbl->GetTypeInfo)(
                   v30,
                   j,
                   &v28);
    if ( GdtiOfItyp < 0 )
      goto LABEL_161;
    HIDWORD(lpMultiByteStra) = 0;
    GdtiOfItyp = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, BSTR *, _QWORD))v28->lpVtbl->GetDocumentation)(
                   v28,
                   0xFFFFFFFFLL,
                   &bstrString,
                   0);
    if ( GdtiOfItyp < 0 )
      goto LABEL_160;
    GdtiOfItyp = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64 *))v28->lpVtbl->GetTypeAttr)(v28, &v31);
    if ( GdtiOfItyp < 0 )
      goto LABEL_159;
    if ( *(_DWORD *)(v31 + 44) == 4
      && (*bstrString == 95 || (unsigned int)GEN_PROJECT::FOldCompatExe((GEN_PROJECT *)this)) )
    {
      if ( *bstrString == 95 && bstrString[1] == 95 )
      {
        v120 = 1;
        v117 = 0;
        GdtiOfItyp = ConvertStringToA(bstrString + 2, &v122);
        if ( GdtiOfItyp < 0 )
          goto LABEL_159;
      }
      else if ( (*(_WORD *)(v31 + 58) & 0x10) != 0 )
      {
        v120 = 0;
        v117 = 1;
        GdtiOfItyp = ConvertStringToA(bstrString + 1, &v122);
        if ( GdtiOfItyp < 0 )
          goto LABEL_159;
      }
      else
      {
        v38 = *(_DWORD *)(v31 + 44) == 5
           || *bstrString != 95 && (unsigned int)GEN_PROJECT::FOldCompatExe((GEN_PROJECT *)this);
        v117 = v38;
        v120 = 0;
        GdtiOfItyp = ConvertStringToA(bstrString, &v122);
        if ( GdtiOfItyp < 0 )
          goto LABEL_159;
      }
    }
    else
    {
      v34 = *(_DWORD *)(v31 + 44) == 5;
      v117 = v34;
      v120 = 0;
      GdtiOfItyp = ConvertStringToA(bstrString, &v122);
      if ( GdtiOfItyp < 0 )
        goto LABEL_159;
    }
    v24 = NAMMGR::HlnamOfStrIfExist(v57, v122);
    if ( v24 != 0xFFFF )
    {
      v135 = GENPROJ_BINDNAME_TABLE::IndexOfHlnam(v58, v24);
      if ( v135 == 0xFFFF )
      {
        v24 = 0xFFFF;
      }
      else
      {
        v61 = GENPROJ_BINDNAME_TABLE::QgpbinddescOfIndex(v58, v135);
        if ( (unsigned int)GENPROJ_BIND_DESC::IsTypeInfo(v61) )
        {
          LOWORD(v5) = TYPE_DEFN::CchFixedString(v61);
          GdtiOfItyp = GEN_PROJECT::GetGdtiOfItyp((GEN_PROJECT *)this, v5, &v27);
          if ( GdtiOfItyp < 0 )
            goto LABEL_158;
          if ( BASIC_TYPEINFO::GetTypeKind(v27) == TKIND_MAX
            && (v68 = *((_QWORD *)v27 + 5), (unsigned int)BASIC_TYPEROOT::Access(v68) == 1) )
          {
            v86 = (CMsoToolbarUser *)*((_QWORD *)v27 + 5);
            v35 = CMsoToolbarUser::FCtlCustomized(v86, v6, v7, v8, 0, 0, lpDefaultChar, lpUsedDefaultChar, GdtiOfItyp);
            v70 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
            v56 = BASIC_TYPEROOT::GetTypeFlags(v70) & 1;
            if ( *(_DWORD *)(v31 + 44) == 5 && v35 && !v120 || (v39 = v117 == 0, v137 = v35 == 0, v39 == v137) )
            {
              if ( *(_DWORD *)(v31 + 44) == 4 )
              {
                v88 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                v32 = BASIC_TYPEROOT::Pinstmgr(v88);
                v72 = *((_QWORD *)v27 + 5);
                BASIC_TYPEROOT::DecompileModule(v72, 1, 0);
                if ( *((_QWORD *)v32 + 36) )
                {
                  ProfMemFree(*((_QWORD *)v32 + 36) - 4LL);
                  *((_QWORD *)v32 + 36) = 0;
                  *((_WORD *)v32 + 140) = 0;
                }
                GdtiOfItyp = (*(__int64 (__fastcall **)(struct BASIC_TYPEINFO *, __int64, LPCWCH *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v27 + 96LL))(
                               v27,
                               0xFFFFFFFFLL,
                               &lpWideCharStr,
                               0,
                               0,
                               0);
                if ( GdtiOfItyp < 0 )
                  goto LABEL_157;
                v90 = lpWideCharStr;
                v44 = -1;
                do
                  ++v44;
                while ( v90[v44] );
                v133 = INT32FromUINT64(v44);
                cbMultiByte = WideCharToMultiByte(0, 0, lpWideCharStr, v133 + 1, 0, 0, 0, 0);
                LODWORD(SizeInBytes) = cbMultiByte + 6;
                Dst = (unsigned __int8 *)ProfMemAlloc((unsigned int)(cbMultiByte + 6));
                if ( !Dst )
                {
                  SysFreeString((BSTR)lpWideCharStr);
                  GdtiOfItyp = -2147024882;
LABEL_157:
                  (*(void (__fastcall **)(struct BASIC_TYPEINFO *))(*(_QWORD *)v27 + 16LL))(v27);
LABEL_158:
                  ((void (__fastcall *)(struct ITypeInfo *, __int64))v28->lpVtbl->ReleaseTypeAttr)(v28, v31);
LABEL_159:
                  SysFreeString(bstrString);
                  ConvertStringFree(v122);
LABEL_160:
                  ((void (__fastcall *)(struct ITypeInfo *))v28->lpVtbl->Release)(v28);
LABEL_161:
                  ((void (__fastcall *)(struct ITypeLib *))v30->lpVtbl->Release)(v30);
                  SysFreeString(v67);
                  SysFreeString(v69);
                  goto LABEL_162;
                }
                _mbscpy_s(Dst, (unsigned int)SizeInBytes, "_IID_");
                WideCharToMultiByte(0, 0, lpWideCharStr, v133 + 1, (LPSTR)Dst + 5, cbMultiByte, 0, 0);
                SysFreeString((BSTR)lpWideCharStr);
                if ( (unsigned int)_((char *)v32 + 248, &GUID_NULL)
                  && (*bstrString == 95 || !(unsigned int)GEN_PROJECT::FOldCompatExe((GEN_PROJECT *)this)) )
                {
                  v102 = *(struct _GUID *)v31;
                  v74 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                  BASIC_TYPEROOT::SetCLSID(v74, &v102);
                  v106 = *(struct _GUID *)v31;
                  *(struct _GUID *)((char *)v32 + 248) = v106;
                }
                if ( (unsigned int)GetOffsetOfResource(hFile, (char *)Dst, 1, &v116, &lOffset) )
                {
                  ProfMemFree(Dst);
LABEL_156:
                  GdtiOfItyp = -2146787930;
                  goto LABEL_157;
                }
                ProfMemFree(Dst);
                if ( _llseek(hFile, lOffset, 0) == -1 || _lread(hFile, &Buffer, 4u) == -1 )
                  goto LABEL_156;
                *((_WORD *)v32 + 140) = Buffer / 0x10;
                if ( Buffer )
                {
                  v121 = (UINT *)ProfMemAlloc(Buffer + 4LL);
                  if ( !v121 )
                  {
                    *((_WORD *)v32 + 140) = 0;
                    GdtiOfItyp = -2147024882;
                    goto LABEL_157;
                  }
                  *((_QWORD *)v32 + 36) = v121 + 1;
                  *v121 = Buffer;
                  if ( _lread(hFile, *((LPVOID *)v32 + 36), Buffer) == -1 )
                    goto LABEL_156;
                  v108 = *(struct _GUID *)v31;
                  *(struct _GUID *)(*((_QWORD *)v32 + 36) + 16LL * (*((unsigned __int16 *)v32 + 140) - 1)) = v108;
                }
                if ( (*(_WORD *)(v31 + 58) & 0x40) != 0 )
                {
                  GdtiOfItyp = ((__int64 (__fastcall *)(struct ITypeInfo *, __int64, unsigned int *))v28->lpVtbl->GetRefTypeOfImplType)(
                                 v28,
                                 0xFFFFFFFFLL,
                                 &v51);
                  if ( GdtiOfItyp < 0 )
                    goto LABEL_157;
                  GdtiOfItyp = ((__int64 (__fastcall *)(struct ITypeInfo *, _QWORD, struct ITypeInfo **))v28->lpVtbl->GetRefTypeInfo)(
                                 v28,
                                 v51,
                                 &v92);
                  if ( GdtiOfItyp < 0 )
                    goto LABEL_157;
                  v76 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                  BASIC_TYPEROOT::SetPtinfoEquiv(v76, v92);
                }
                else
                {
                  v94 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                  BASIC_TYPEROOT::SetPtinfoEquiv(v94, v28);
                  ((void (__fastcall *)(struct ITypeInfo *))v28->lpVtbl->AddRef)(v28);
                }
                v78 = *((_QWORD *)v27 + 5);
                if ( (int)BASIC_TYPEROOT::CompState(v78) < 2
                  || (v96 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5), (unsigned int)BASIC_TYPEROOT::IsClassIdentical(v96)) )
                {
                  v104 = *(struct _GUID *)v31;
                  v95 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                  BASIC_TYPEROOT::SetIID(v95, &v104);
                }
                if ( !*((_WORD *)v32 + 140) )
                {
                  v121 = (UINT *)ProfMemAlloc(20);
                  if ( !v121 )
                  {
                    GdtiOfItyp = -2147024882;
                    goto LABEL_157;
                  }
                  *v121 = 16;
                  *((_QWORD *)v32 + 36) = v121 + 1;
                  v81 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                  v109 = (__int128)*BASIC_TYPEROOT::GetIID(v81, &v113);
                  *(_OWORD *)*((_QWORD *)v32 + 36) = v109;
                  ++*((_WORD *)v32 + 140);
                }
              }
              else
              {
                v97 = 0;
                v107 = 0;
                v100 = 0;
                v89 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                BASIC_TYPEROOT::SetPtinfoEquivCoclass(v89, v28);
                ((void (__fastcall *)(struct ITypeInfo *))v28->lpVtbl->AddRef)(v28);
                v83 = *((_QWORD *)v27 + 5);
                if ( (int)BASIC_TYPEROOT::CompState(v83) < 2
                  || (v93 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5), (unsigned int)BASIC_TYPEROOT::IsClassIdentical(v93)) )
                {
                  v98 = *(struct _GUID *)v31;
                  v85 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                  BASIC_TYPEROOT::SetCLSID(v85, &v98);
                  v91 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
                  v99 = *(struct _GUID *)v31;
                  v9 = BASIC_TYPEROOT::Pinstmgr(v91);
                  *(struct _GUID *)((char *)v9 + 248) = v99;
                }
              }
            }
            else if ( v120 )
            {
              v87 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
              v123 = BASIC_TYPEROOT::Pinstmgr(v87);
              if ( *((_QWORD *)v123 + 38) )
              {
                ProfMemFree(*((_QWORD *)v123 + 38) - 4LL);
                *((_QWORD *)v123 + 38) = 0;
                *((_WORD *)v123 + 148) = 0;
              }
              GdtiOfItyp = (*(__int64 (__fastcall **)(struct BASIC_TYPEINFO *, __int64, LPCWCH *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v27 + 96LL))(
                             v27,
                             0xFFFFFFFFLL,
                             &v37,
                             0,
                             0,
                             0);
              if ( GdtiOfItyp < 0 )
                goto LABEL_157;
              v63 = v37;
              v42 = -1;
              do
                ++v42;
              while ( v63[v42] );
              v138 = INT32FromUINT64(v42);
              v132 = WideCharToMultiByte(0, 0, v37, v138 + 1, 0, 0, 0, 0);
              v136 = v132 + 9;
              v131 = (char *)ProfMemAlloc((unsigned int)(v132 + 9));
              if ( !v131 )
              {
                SysFreeString((BSTR)v37);
                GdtiOfItyp = -2147024882;
                goto LABEL_157;
              }
              _mbscpy_s((unsigned __int8 *)v131, v136, "_SRCIID_");
              WideCharToMultiByte(0, 0, v37, v138 + 1, v131 + 8, v132, 0, 0);
              SysFreeString((BSTR)v37);
              if ( (unsigned int)GetOffsetOfResource(hFile, v131, 1, &v116, &v53) )
              {
                ProfMemFree(v131);
                goto LABEL_156;
              }
              ProfMemFree(v131);
              if ( _llseek(hFile, v53, 0) == -1 || _lread(hFile, &uBytes, 4u) == -1 )
                goto LABEL_156;
              *((_WORD *)v123 + 148) = uBytes / 0x10;
              if ( uBytes )
              {
                v121 = (UINT *)ProfMemAlloc(uBytes + 4LL);
                if ( !v121 )
                {
                  *((_WORD *)v123 + 148) = 0;
                  GdtiOfItyp = -2147024882;
                  goto LABEL_157;
                }
                *((_QWORD *)v123 + 38) = v121 + 1;
                *v121 = uBytes;
                if ( _lread(hFile, *((LPVOID *)v123 + 38), uBytes) == -1 )
                  goto LABEL_156;
                v101 = *(struct _GUID *)v31;
                *(struct _GUID *)(*((_QWORD *)v123 + 38) + 16LL * (*((unsigned __int16 *)v123 + 148) - 1)) = v101;
              }
              v80 = (BASIC_TYPEROOT *)*((_QWORD *)v27 + 5);
              BASIC_TYPEROOT::SetPtinfoEvent(v80, v28);
              ((void (__fastcall *)(struct ITypeInfo *))v28->lpVtbl->AddRef)(v28);
            }
            else
            {
              v24 = 0xFFFF;
            }
          }
          else
          {
            v24 = 0xFFFF;
          }
          (*(void (__fastcall **)(struct BASIC_TYPEINFO *))(*(_QWORD *)v27 + 16LL))(v27);
        }
        else
        {
          v24 = 0xFFFF;
        }
      }
    }
    if ( v24 == 0xFFFF && !*(_DWORD *)(v31 + 44) )
    {
      EXBIND::EXBIND((EXBIND *)v112);
      v24 = NAMMGR::HlnamOfStrIfExist(v57, v122);
      if ( v24 != 0xFFFF )
      {
        v55 = (*((__int64 (__fastcall **)(wchar_t **))*this + 3))(this);
        for ( k = 0; k < v55; ++k )
        {
          GdtiOfItyp = (*((__int64 (__fastcall **)(wchar_t **, _QWORD, BASIC_TYPEINFO **))*this + 4))(this, k, &v124);
          if ( GdtiOfItyp < 0 )
            goto LABEL_162;
          v59 = (BASIC_TYPEROOT *)*((_QWORD *)v124 + 5);
          if ( BASIC_TYPEINFO::GetTypeKind(v124) == TKIND_MAX && (unsigned int)BASIC_TYPEROOT::Access(v59) == 1 )
          {
            v10 = BASIC_TYPEROOT::Pdtmbrs(v59);
            v43 = (TYPE_DATA *)serProcTemplate::PvTemplate(v10);
            for ( m = TYPE_DATA::HdefnFirstTypeDefn(v43); m != -1; m = MEMBER_DEFN::DwHelpContext(v47) )
            {
              v47 = TYPE_DATA::QvfdefnOfHvfdefn(v43, m, 0);
              if ( (unsigned int)RECTYPE_DEFN::Access(v47) == 1
                && (unsigned int)RECTYPE_DEFN::IsEnum(v47)
                && DEFN::Hlnam(v47) == v24 )
              {
                v11 = TYPE_DATA::QvfdefnOfHvfdefn(v43, m, 0);
                LOWORD(v12) = RESDESC::CchFxStr(v11);
                v50 = v12;
                v13 = TYPE_DATA::Pimpmgr(v43);
                IMPMGR::GetTypeInfo(v13, v50, 0, &v45);
                GdtiOfItyp = (**(__int64 (__fastcall ***)(__int64, GUID *, REC_TYPEINFO **))v45)(
                               v45,
                               &IID_REC_TYPEINFO,
                               &v130);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
                Guid = REC_TYPEINFO::GetGuid(v130, &v114);
                if ( (unsigned int)_(Guid, &GUID_NULL) )
                  (*(void (__fastcall **)(REC_TYPEINFO *, __int64))(*(_QWORD *)v130 + 176LL))(v130, v31);
                BASIC_TYPEROOT::SetPtypelibExe(*((BASIC_TYPEROOT **)v130 + 3), v30);
                (*(void (__fastcall **)(REC_TYPEINFO *))(*(_QWORD *)v130 + 16LL))(v130);
                ((void (__fastcall *)(struct ITypeLib *))v30->lpVtbl->AddRef)(v30);
                if ( v124 )
                {
                  (*(void (__fastcall **)(BASIC_TYPEINFO *))(*(_QWORD *)v124 + 16LL))(v124);
                  v124 = 0;
                }
                goto LABEL_142;
              }
            }
          }
          if ( v124 )
          {
            (*(void (__fastcall **)(BASIC_TYPEINFO *))(*(_QWORD *)v124 + 16LL))(v124);
            v124 = 0;
          }
        }
        v24 = 0xFFFF;
      }
    }
LABEL_142:
    if ( v24 == 0xFFFF && *(_DWORD *)(v31 + 44) == 1 )
    {
      EXBIND::EXBIND((EXBIND *)v105);
      v25 = NAMMGR::HlnamOfStrIfExist(v57, v122);
      if ( v25 != 0xFFFF )
      {
        GEN_PROJECT::GetDefnTypeBind((GEN_PROJECT *)this, &v60);
        LODWORD(lpMultiByteStra) = 1;
        GdtiOfItyp = (*(__int64 (__fastcall **)(struct DEFN_TYPEBIND *, __int64, _QWORD, _QWORD, LPSTR, _BYTE *))(*(_QWORD *)v60 + 144LL))(
                       v60,
                       1,
                       v25,
                       0,
                       lpMultiByteStra,
                       v105);
        if ( (unsigned int)EXBIND::BindKind(v105) == 6 )
        {
          v64 = NAMMGR::Pgenproj((NAMMGR *)v105);
          v41 = (REC_TYPEINFO *)*((_QWORD *)v64 + 8);
          v15 = REC_TYPEINFO::GetGuid(v41, &v115);
          if ( (unsigned int)_(v15, &GUID_NULL) )
            (*(void (__fastcall **)(REC_TYPEINFO *, __int64))(*(_QWORD *)v41 + 176LL))(v41, v31);
          BASIC_TYPEROOT::SetPtypelibExe(*((BASIC_TYPEROOT **)v41 + 3), v30);
          ((void (__fastcall *)(struct ITypeLib *))v30->lpVtbl->AddRef)(v30);
        }
      }
    }
    SysFreeString(bstrString);
    ConvertStringFree(v122);
    v122 = 0;
    ((void (__fastcall *)(struct ITypeInfo *, __int64))v28->lpVtbl->ReleaseTypeAttr)(v28, v31);
    ((void (__fastcall *)(struct ITypeInfo *))v28->lpVtbl->Release)(v28);
    if ( GdtiOfItyp < 0 )
      break;
  }
  _lclose(hFile);
  if ( GdtiOfItyp < 0 )
  {
    ((void (__fastcall *)(struct ITypeLib *))v30->lpVtbl->Release)(v30);
    goto LABEL_164;
  }
  v23 = ((__int64 (__fastcall *)(struct ITypeLib *, __int64 *))v30->lpVtbl->GetLibAttr)(v30, &v62);
  if ( v23 >= 0 )
  {
    v65 = this[1];
    (*((void (__fastcall **)(char *, __int64))v65 + 6))((char *)this + 8, v62);
    ((void (__fastcall *)(struct ITypeLib *, __int64))v30->lpVtbl->ReleaseTLibAttr)(v30, v62);
  }
  ((void (__fastcall *)(struct ITypeLib *))v30->lpVtbl->Release)(v30);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x180125970  mov     [rsp-8+arg_0], rcx
0x180125975  push    rbp
0x180125976  mov     rbp, rsp
0x180125979  sub     rsp, 450h
0x180125980  mov     rax, cs:__security_cookie
0x180125987  xor     rax, rsp
0x18012598a  mov     [rbp+SizeInBytes+4], rax
0x18012598e  mov     [rsp+450h+var_2F8], 0
0x18012599a  mov     [rsp+450h+var_2E8], 0
0x1801259a6  mov     [rbp+var_70], 0
0x1801259ae  mov     [rsp+450h+var_90], 0
0x1801259b9  mov     [rsp+450h+hFile], 0FFFFFFFFh
0x1801259c1  mov     rax, [rbp+arg_0]
0x1801259c5  mov     rax, [rax]
0x1801259c8  mov     rcx, [rbp+arg_0]
0x1801259cc  call    qword ptr [rax+18h]
0x1801259cf  mov     [rsp+450h+var_36C], eax
0x1801259d6  mov     [rbp+var_58], 0
0x1801259dd  jmp     short loc_1801259E7
0x1801259df  mov     eax, [rbp+var_58]
0x1801259e2  inc     eax
0x1801259e4  mov     [rbp+var_58], eax
0x1801259e7  mov     eax, [rsp+450h+var_36C]
0x1801259ee  cmp     [rbp+var_58], eax
0x1801259f1  jnb     loc_180125AC7
0x1801259f7  lea     r8, [rbp+var_48]; struct BASIC_TYPEINFO **
0x1801259fb  mov     edx, [rbp+var_58]; unsigned int
0x1801259fe  mov     rcx, [rbp+arg_0]; this
0x180125a02  call    ?GetGdtiOfItyp@GEN_PROJECT@@QEAAJIPEAPEAVBASIC_TYPEINFO@@@Z; GEN_PROJECT::GetGdtiOfItyp(uint,BASIC_TYPEINFO * *)
0x180125a07  mov     [rsp+450h+var_410], eax
0x180125a0b  cmp     [rsp+450h+var_410], 0
0x180125a10  jge     short loc_180125A1C
0x180125a12  jmp     loc_1801271C1
0x180125a17  jmp     loc_1801271C1
0x180125a1c  mov     rax, [rbp+var_48]
0x180125a20  mov     [rsp+450h+var_298], rax
0x180125a28  xor     edx, edx; int
0x180125a2a  mov     rax, [rsp+450h+var_298]
0x180125a32  mov     rcx, [rax+28h]; this
0x180125a36  call    ?EnsureInSemiDeclaredState@BASIC_TYPEROOT@@QEAAJH@Z; BASIC_TYPEROOT::EnsureInSemiDeclaredState(int)
0x180125a3b  mov     rax, [rbp+var_48]
0x180125a3f  mov     rax, [rax+28h]
0x180125a43  mov     [rsp+450h+var_280], rax
0x180125a4b  mov     rcx, [rsp+450h+var_280]; this
0x180125a53  call    ?Typekind@BASIC_TYPEROOT@@QEBA?AW4tagTYPEKIND@@XZ; BASIC_TYPEROOT::Typekind(void)
0x180125a58  cmp     eax, 8
0x180125a5b  jnz     short loc_180125AB4
0x180125a5d  mov     rax, [rbp+var_48]
0x180125a61  mov     rax, [rax+28h]
0x180125a65  mov     [rsp+450h+var_300], rax
0x180125a6d  mov     rcx, [rsp+450h+var_300]
0x180125a75  call    ?CompState@BASIC_TYPEROOT@@QEBA?AW4COMPSTATE@@XZ; BASIC_TYPEROOT::CompState(void)
0x180125a7a  cmp     eax, 2
0x180125a7d  jge     short loc_180125AB4
0x180125a7f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180125a86  movdqu  xmmword ptr [rsp+450h+var_1B0.Data1], xmm0
0x180125a8f  mov     rax, [rbp+var_48]
0x180125a93  mov     rax, [rax+28h]
0x180125a97  mov     [rsp+450h+var_270], rax
0x180125a9f  lea     rdx, [rsp+450h+var_1B0]; struct _GUID
0x180125aa7  mov     rcx, [rsp+450h+var_270]; this
0x180125aaf  call    ?SetCLSID@BASIC_TYPEROOT@@QEAAXU_GUID@@@Z; BASIC_TYPEROOT::SetCLSID(_GUID)
0x180125ab4  mov     rax, [rbp+var_48]
0x180125ab8  mov     rax, [rax]
0x180125abb  mov     rcx, [rbp+var_48]
0x180125abf  call    qword ptr [rax+10h]
0x180125ac2  jmp     loc_1801259DF
0x180125ac7  mov     rcx, [rbp+arg_0]; wchar_t *
0x180125acb  call    ?Dropping@CMsoDropdownUser@@UEAAXPEAUIMsoControl@@PEAPEAXPEAUHFONT__@@@Z; CMsoDropdownUser::Dropping(IMsoControl *,void * *,HFONT__ *)
0x180125ad0  mov     rcx, [rbp+arg_0]; this
0x180125ad4  call    ?Pnammgr@GEN_PROJECT@@QEAAPEAVNAMMGR@@XZ; GEN_PROJECT::Pnammgr(void)
0x180125ad9  mov     [rsp+450h+var_348], rax
0x180125ae1  mov     rcx, [rbp+arg_0]; this
0x180125ae5  call    ?Pgptbind@GEN_PROJECT@@QEAAPEAVGENPROJ_TYPEBIND@@XZ; GEN_PROJECT::Pgptbind(void)
0x180125aea  mov     rcx, rax; this
0x180125aed  call    ?Pgbindnametbl@GENPROJ_TYPEBIND@@QEAAPEAVGENPROJ_BINDNAME_TABLE@@XZ; GENPROJ_TYPEBIND::Pgbindnametbl(void)
0x180125af2  mov     [rsp+450h+var_340], rax
0x180125afa  lea     rdx, [rsp+450h+hFile]; int *
0x180125aff  mov     rax, [rbp+arg_0]
0x180125b03  mov     rcx, [rax+1680h]; wchar_t *
0x180125b0a  call    ?ErrOpen@@YAJPEA_WPEAH@Z; ErrOpen(wchar_t *,int *)
0x180125b0f  test    eax, eax
0x180125b11  jz      short loc_180125B25
0x180125b13  mov     [rsp+450h+var_410], 800A9DA6h
0x180125b1b  jmp     loc_1801271C1
0x180125b20  jmp     loc_1801271C1
0x180125b25  lea     rdx, [rsp+450h+var_D0]; struct _IMAGE_DOS_HEADER *
0x180125b2d  mov     ecx, [rsp+450h+hFile]; int
0x180125b31  call    ?FIsExe@@YAHHPEAU_IMAGE_DOS_HEADER@@@Z; FIsExe(int,_IMAGE_DOS_HEADER *)
0x180125b36  mov     [rsp+450h+var_358], eax
0x180125b3d  cmp     [rsp+450h+var_358], 0
0x180125b45  jnz     short loc_180125B59
0x180125b47  mov     [rsp+450h+var_410], 800A9DA6h
0x180125b4f  jmp     loc_1801271C1
0x180125b54  jmp     loc_1801271C1
0x180125b59  lea     r8, [rsp+450h+var_D0]; struct _IMAGE_DOS_HEADER *
0x180125b61  lea     rdx, aIid; "_IID_"
0x180125b68  mov     ecx, [rsp+450h+hFile]; int
0x180125b6c  call    ?IsVBExe@@YAHHPEADPEAU_IMAGE_DOS_HEADER@@@Z; IsVBExe(int,char *,_IMAGE_DOS_HEADER *)
0x180125b71  test    eax, eax
0x180125b73  jnz     short loc_180125B87
0x180125b75  mov     [rsp+450h+var_410], 800A9DA6h
0x180125b7d  jmp     loc_1801271C1
0x180125b82  jmp     loc_1801271C1
0x180125b87  lea     r8, [rsp+450h+var_3E8]
0x180125b8c  mov     edx, 2
0x180125b91  mov     rax, [rbp+arg_0]
0x180125b95  mov     rcx, [rax+1680h]
0x180125b9c  call    LoadTypeLibExWrap
0x180125ba1  mov     [rsp+450h+var_410], eax
0x180125ba5  cmp     [rsp+450h+var_410], 0
0x180125baa  jge     short loc_180125BB6
0x180125bac  jmp     loc_1801271C1
0x180125bb1  jmp     loc_1801271C1
0x180125bb6  mov     rax, [rbp+arg_0]
0x180125bba  mov     dword ptr [rax+1738h], 0
0x180125bc4  mov     rax, [rsp+450h+var_3E8]
0x180125bc9  mov     rax, [rax]
0x180125bcc  lea     r8, [rsp+450h+var_380]
0x180125bd4  lea     rdx, IID_ITypeLib2
0x180125bdb  mov     rcx, [rsp+450h+var_3E8]
0x180125be0  call    qword ptr [rax]
0x180125be2  test    eax, eax
0x180125be4  jl      short loc_180125C43
0x180125be6  mov     rax, [rsp+450h+var_380]
0x180125bee  mov     rax, [rax]
0x180125bf1  lea     r8, [rsp+450h+var_138]
0x180125bf9  lea     rdx, GUID_FuncCustDataReturnErrors
0x180125c00  mov     rcx, [rsp+450h+var_380]
0x180125c08  call    qword ptr [rax+68h]
0x180125c0b  test    eax, eax
0x180125c0d  jl      short loc_180125C2D
0x180125c0f  movzx   eax, [rsp+450h+var_138]
0x180125c17  cmp     eax, 3
0x180125c1a  jnz     short loc_180125C2D
0x180125c1c  mov     rax, [rbp+arg_0]
0x180125c20  mov     ecx, [rsp+450h+var_130]
0x180125c27  mov     [rax+1738h], ecx
0x180125c2d  mov     rax, [rsp+450h+var_380]
0x180125c35  mov     rax, [rax]
0x180125c38  mov     rcx, [rsp+450h+var_380]
0x180125c40  call    qword ptr [rax+10h]
0x180125c43  mov     rax, [rbp+arg_0]
0x180125c47  cmp     dword ptr [rax+1738h], 0
0x180125c4e  jnz     short loc_180125C5D
0x180125c50  mov     [rsp+450h+var_3C4], 1
0x180125c5b  jmp     short loc_180125C68
0x180125c5d  mov     [rsp+450h+var_3C4], 0
0x180125c68  mov     eax, [rsp+450h+var_3C4]
0x180125c6f  and     eax, 1
0x180125c72  shl     eax, 7
0x180125c75  mov     rcx, [rbp+arg_0]
0x180125c79  mov     ecx, [rcx+138h]
0x180125c7f  btr     ecx, 7
0x180125c83  or      ecx, eax
0x180125c85  mov     eax, ecx
0x180125c87  mov     rcx, [rbp+arg_0]
0x180125c8b  mov     [rcx+138h], eax
0x180125c91  mov     rax, [rsp+450h+var_3E8]
0x180125c96  mov     rax, [rax]
0x180125c99  mov     rcx, [rsp+450h+var_3E8]
0x180125c9e  call    qword ptr [rax+18h]
0x180125ca1  mov     [rsp+450h+var_360], eax
0x180125ca8  mov     [rsp+450h+var_3F0], 0
0x180125cb0  jmp     short loc_180125CBC
0x180125cb2  mov     eax, [rsp+450h+var_3F0]
0x180125cb6  inc     eax
0x180125cb8  mov     [rsp+450h+var_3F0], eax
0x180125cbc  mov     eax, [rsp+450h+var_360]
0x180125cc3  cmp     [rsp+450h+var_3F0], eax
0x180125cc7  jnb     loc_18012708D
0x180125ccd  mov     [rsp+450h+var_350], 0
0x180125cd8  mov     rax, [rsp+450h+var_3E8]
0x180125cdd  mov     rax, [rax]
0x180125ce0  lea     r8, [rsp+450h+var_3F8]
0x180125ce5  mov     edx, [rsp+450h+var_3F0]
0x180125ce9  mov     rcx, [rsp+450h+var_3E8]
0x180125cee  call    qword ptr [rax+20h]
0x180125cf1  mov     [rsp+450h+var_410], eax
0x180125cf5  cmp     [rsp+450h+var_410], 0
0x180125cfa  jge     short loc_180125D06
0x180125cfc  jmp     loc_180127195
0x180125d01  jmp     loc_180127195
0x180125d06  mov     rax, [rsp+450h+var_3F8]
0x180125d0b  mov     rax, [rax]
0x180125d0e  mov     qword ptr [rsp+450h+cbMultiByte], 0; int
0x180125d17  mov     [rsp+450h+lpMultiByteStr], 0; int
0x180125d20  xor     r9d, r9d
0x180125d23  lea     r8, [rsp+450h+bstrString]
0x180125d2b  mov     edx, 0FFFFFFFFh
0x180125d30  mov     rcx, [rsp+450h+var_3F8]
0x180125d35  call    qword ptr [rax+60h]
0x180125d38  mov     [rsp+450h+var_410], eax
0x180125d3c  cmp     [rsp+450h+var_410], 0
0x180125d41  jge     short loc_180125D4D
0x180125d43  jmp     loc_180127185
0x180125d48  jmp     loc_180127185
0x180125d4d  mov     rax, [rsp+450h+var_3F8]
0x180125d52  mov     rax, [rax]
0x180125d55  lea     rdx, [rsp+450h+var_3E0]
0x180125d5a  mov     rcx, [rsp+450h+var_3F8]
0x180125d5f  call    qword ptr [rax+18h]
0x180125d62  mov     [rsp+450h+var_410], eax
0x180125d66  cmp     [rsp+450h+var_410], 0
0x180125d6b  jge     short loc_180125D77
0x180125d6d  jmp     loc_18012716E
0x180125d72  jmp     loc_18012716E
0x180125d77  mov     rax, [rsp+450h+var_3E0]
0x180125d7c  cmp     dword ptr [rax+2Ch], 4
0x180125d80  jnz     loc_180125EDA
0x180125d86  mov     rax, [rsp+450h+bstrString]
0x180125d8e  movzx   eax, word ptr [rax]
0x180125d91  cmp     eax, 5Fh ; '_'
0x180125d94  jz      short loc_180125DA7
0x180125d96  mov     rcx, [rbp+arg_0]; this
0x180125d9a  call    ?FOldCompatExe@GEN_PROJECT@@QEAAHXZ; GEN_PROJECT::FOldCompatExe(void)
0x180125d9f  test    eax, eax
0x180125da1  jz      loc_180125EDA
0x180125da7  mov     rax, [rsp+450h+bstrString]
0x180125daf  movzx   eax, word ptr [rax]
0x180125db2  cmp     eax, 5Fh ; '_'
0x180125db5  jnz     short loc_180125E0C
0x180125db7  mov     rax, [rsp+450h+bstrString]
0x180125dbf  movzx   eax, word ptr [rax+2]
0x180125dc3  cmp     eax, 5Fh ; '_'
0x180125dc6  jnz     short loc_180125E0C
0x180125dc8  mov     [rbp+var_7C], 1
0x180125dcf  mov     [rsp+450h+var_90], 0
0x180125dda  mov     rax, [rsp+450h+bstrString]
0x180125de2  add     rax, 4
0x180125de6  lea     rdx, [rbp+var_70]; char **
0x180125dea  mov     rcx, rax; wchar_t *
0x180125ded  call    ?ConvertStringToA@@YAJPEB_WPEAPEAD@Z; ConvertStringToA(wchar_t const *,char * *)
0x180125df2  mov     [rsp+450h+var_410], eax
0x180125df6  cmp     [rsp+450h+var_410], 0
0x180125dfb  jge     short loc_180125E07
0x180125dfd  jmp     loc_18012716E
0x180125e02  jmp     loc_18012716E
0x180125e07  jmp     loc_180125ED8
0x180125e0c  mov     rax, [rsp+450h+var_3E0]
0x180125e11  movzx   eax, word ptr [rax+3Ah]
0x180125e15  and     eax, 10h
0x180125e18  test    eax, eax
0x180125e1a  jz      short loc_180125E5D
0x180125e1c  mov     [rbp+var_7C], 0
0x180125e23  mov     [rsp+450h+var_90], 1
0x180125e2e  mov     rax, [rsp+450h+bstrString]
0x180125e36  add     rax, 2
0x180125e3a  lea     rdx, [rbp+var_70]; char **
0x180125e3e  mov     rcx, rax; wchar_t *
0x180125e41  call    ?ConvertStringToA@@YAJPEB_WPEAPEAD@Z; ConvertStringToA(wchar_t const *,char * *)
0x180125e46  mov     [rsp+450h+var_410], eax
0x180125e4a  cmp     [rsp+450h+var_410], 0
0x180125e4f  jge     short loc_180125E5B
0x180125e51  jmp     loc_18012716E
0x180125e56  jmp     loc_18012716E
0x180125e5b  jmp     short loc_180125ED8
0x180125e5d  mov     rax, [rsp+450h+var_3E0]
0x180125e62  cmp     dword ptr [rax+2Ch], 5
0x180125e66  jz      short loc_180125E92
0x180125e68  mov     rax, [rsp+450h+bstrString]
0x180125e70  movzx   eax, word ptr [rax]
0x180125e73  cmp     eax, 5Fh ; '_'
0x180125e76  jz      short loc_180125E85
0x180125e78  mov     rcx, [rbp+arg_0]; this
0x180125e7c  call    ?FOldCompatExe@GEN_PROJECT@@QEAAHXZ; GEN_PROJECT::FOldCompatExe(void)
0x180125e81  test    eax, eax
0x180125e83  jnz     short loc_180125E92
0x180125e85  mov     [rsp+450h+var_3B8], 0
0x180125e90  jmp     short loc_180125E9D
0x180125e92  mov     [rsp+450h+var_3B8], 1
0x180125e9d  mov     eax, [rsp+450h+var_3B8]
0x180125ea4  mov     [rsp+450h+var_90], eax
0x180125eab  mov     [rbp+var_7C], 0
0x180125eb2  lea     rdx, [rbp+var_70]; char **
0x180125eb6  mov     rcx, [rsp+450h+bstrString]; wchar_t *
0x180125ebe  call    ?ConvertStringToA@@YAJPEB_WPEAPEAD@Z; ConvertStringToA(wchar_t const *,char * *)
0x180125ec3  mov     [rsp+450h+var_410], eax
0x180125ec7  cmp     [rsp+450h+var_410], 0
0x180125ecc  jge     short loc_180125ED8
0x180125ece  jmp     loc_18012716E
0x180125ed3  jmp     loc_18012716E
0x180125ed8  jmp     short loc_180125F38
0x180125eda  mov     rax, [rsp+450h+var_3E0]
0x180125edf  cmp     dword ptr [rax+2Ch], 5
0x180125ee3  jnz     short loc_180125EF2
0x180125ee5  mov     [rsp+450h+var_3CC], 1
0x180125ef0  jmp     short loc_180125EFD
0x180125ef2  mov     [rsp+450h+var_3CC], 0
0x180125efd  mov     eax, [rsp+450h+var_3CC]
0x180125f04  mov     [rsp+450h+var_90], eax
0x180125f0b  mov     [rbp+var_7C], 0
0x180125f12  lea     rdx, [rbp+var_70]; char **
0x180125f16  mov     rcx, [rsp+450h+bstrString]; wchar_t *
0x180125f1e  call    ?ConvertStringToA@@YAJPEB_WPEAPEAD@Z; ConvertStringToA(wchar_t const *,char * *)
0x180125f23  mov     [rsp+450h+var_410], eax
0x180125f27  cmp     [rsp+450h+var_410], 0
0x180125f2c  jge     short loc_180125F38
0x180125f2e  jmp     loc_18012716E
0x180125f33  jmp     loc_18012716E
  ... truncated ...
```
