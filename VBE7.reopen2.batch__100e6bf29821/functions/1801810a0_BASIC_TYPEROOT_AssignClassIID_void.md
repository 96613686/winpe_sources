# BASIC_TYPEROOT::AssignClassIID(void)

- ea: `0x1801810a0`
- end: `0x180181ebe`
- name: `?AssignClassIID@BASIC_TYPEROOT@@QEAAJXZ`
- size: `3614`
- prototype: `__int64 __fastcall(BASIC_TYPEROOT *__hidden this)`
- caller_count: `3`
- callee_count: `27`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18012abcc`
- `0x18017ee30`
- `0x18029eb6c`

## callees

- `0x18000452c`
- `0x1800e64cc`
- `0x1800fd648`
- `0x18011d9fc`
- `0x18011fd94`
- `0x1801258a0`
- `0x1801258d0`
- `0x1801330a4`
- `0x1801331a8`
- `0x1801331dc`
- `0x180134fe8`
- `0x1801426d8`
- `0x18014273c`
- `0x18014275c`
- `0x18014f0b0`
- `0x18017a42c`
- `0x18017a534`
- `0x18017a9a0`
- `0x18017af80`
- `0x18017cf30`
- `0x180181080`
- `0x1801810a0`
- `0x180181ff4`
- `0x1801dc1ac`
- `0x180288228`
- `0x1802bdbf8`
- `0x180379520`

## import_xrefs

- `ole32!CoCreateGuid` at `0x1801812ac`
- `ole32!CoCreateGuid` at `0x180181599`
- `ole32!CoCreateGuid` at `0x180181698`
- `ole32!CoCreateGuid` at `0x1801818a4`
- `ole32!CoCreateGuid` at `0x180181beb`
- `ole32!CoCreateGuid` at `0x180181c7e`
- `ole32!CoCreateGuid` at `0x180181d11`
- `ole32!CoCreateGuid` at `0x180181dbf`
- `ole32!CoCreateGuid` at `0x180181e6c`
- `ole32!CoCreateGuid` at `0x1801812ac`
- `ole32!CoCreateGuid` at `0x180181599`
- `ole32!CoCreateGuid` at `0x180181698`
- `ole32!CoCreateGuid` at `0x1801818a4`
- `ole32!CoCreateGuid` at `0x180181beb`
- `ole32!CoCreateGuid` at `0x180181c7e`
- `ole32!CoCreateGuid` at `0x180181d11`
- `ole32!CoCreateGuid` at `0x180181dbf`
- `ole32!CoCreateGuid` at `0x180181e6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180181546`
- `OLEAUT32!__imp_SysFreeString` at `0x180181546`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18018142f`
- `OLEAUT32!__imp_LoadTypeLib` at `0x18018142f`

## pseudocode

```c
__int64 __fastcall BASIC_TYPEROOT::AssignClassIID(BASIC_TYPEROOT *this)
{
  struct INSTMGR *v2; // rax
  struct INSTMGR *v3; // rax
  struct INSTMGR *v4; // rax
  struct _GUID *v5; // rax
  struct INSTMGR *v6; // rax
  struct _GUID *CLSID; // rax
  struct INSTMGR *v8; // rax
  struct INSTMGR *v9; // rax
  struct INSTMGR *v10; // rax
  struct _GUID *Guid; // rax
  struct INSTMGR *v12; // rax
  struct INSTMGR *v13; // rax
  struct INSTMGR *v14; // rax
  struct INSTMGR *v15; // rax
  struct INSTMGR *v16; // rax
  struct INSTMGR *v17; // rax
  struct INSTMGR *v18; // rax
  struct INSTMGR *v19; // rax
  struct INSTMGR *v20; // rax
  struct INSTMGR *v21; // rax
  struct INSTMGR *v22; // rax
  struct INSTMGR *v23; // rax
  struct INSTMGR *v24; // rax
  struct _GUID *v25; // rax
  int ImpMgr; // [rsp+30h] [rbp-260h]
  int CLSIDorIIDofBaseCoClass; // [rsp+30h] [rbp-260h]
  int v28; // [rsp+30h] [rbp-260h]
  int Dtmbrs; // [rsp+30h] [rbp-260h]
  HRESULT v30; // [rsp+30h] [rbp-260h]
  HRESULT v31; // [rsp+30h] [rbp-260h]
  HRESULT v32; // [rsp+30h] [rbp-260h]
  HRESULT v33; // [rsp+30h] [rbp-260h]
  _DWORD *v34; // [rsp+38h] [rbp-258h]
  _DWORD *v35; // [rsp+38h] [rbp-258h]
  _DWORD *v36; // [rsp+38h] [rbp-258h]
  _DWORD *v37; // [rsp+38h] [rbp-258h]
  _DWORD *v38; // [rsp+38h] [rbp-258h]
  __int64 v39; // [rsp+40h] [rbp-250h]
  _DWORD *v40; // [rsp+40h] [rbp-250h]
  __int64 v41; // [rsp+40h] [rbp-250h]
  _DWORD *v42; // [rsp+40h] [rbp-250h]
  _DWORD *v43; // [rsp+40h] [rbp-250h]
  unsigned int i; // [rsp+48h] [rbp-248h]
  unsigned int j; // [rsp+48h] [rbp-248h]
  int v46; // [rsp+4Ch] [rbp-244h]
  __int16 v47; // [rsp+50h] [rbp-240h] BYREF
  __int64 v48; // [rsp+58h] [rbp-238h] BYREF
  int IsProjectIncompatible; // [rsp+60h] [rbp-230h]
  TYPE_DATA *v50; // [rsp+68h] [rbp-228h]
  ITypeLib *pptlib; // [rsp+70h] [rbp-220h] BYREF
  IMPMGR *v52; // [rsp+78h] [rbp-218h] BYREF
  REC_TYPEINFO *v53; // [rsp+80h] [rbp-210h]
  _DWORD *v54; // [rsp+88h] [rbp-208h]
  struct EBTHREAD *v55; // [rsp+90h] [rbp-200h]
  struct REC_TYPEBIND *v56; // [rsp+98h] [rbp-1F8h]
  __int64 v57; // [rsp+A0h] [rbp-1F0h]
  struct EBTHREAD *v58; // [rsp+A8h] [rbp-1E8h]
  struct EBTHREAD *v59; // [rsp+B0h] [rbp-1E0h]
  _DWORD *v60; // [rsp+B8h] [rbp-1D8h]
  struct EBTHREAD *v61; // [rsp+C0h] [rbp-1D0h]
  struct REC_TYPEBIND *v62; // [rsp+C8h] [rbp-1C8h]
  struct EBTHREAD *v63; // [rsp+D0h] [rbp-1C0h]
  _DWORD *v64; // [rsp+D8h] [rbp-1B8h]
  struct EBTHREAD *v65; // [rsp+E0h] [rbp-1B0h]
  _DWORD *v66; // [rsp+E8h] [rbp-1A8h]
  GEN_PROJECT *v67; // [rsp+F0h] [rbp-1A0h]
  _DWORD *v68; // [rsp+F8h] [rbp-198h]
  _DWORD *v69; // [rsp+100h] [rbp-190h]
  _DWORD *v70; // [rsp+108h] [rbp-188h]
  _BYTE v71[16]; // [rsp+110h] [rbp-180h] BYREF
  _BYTE v72[16]; // [rsp+120h] [rbp-170h] BYREF
  _BYTE v73[16]; // [rsp+130h] [rbp-160h] BYREF
  _BYTE v74[16]; // [rsp+140h] [rbp-150h] BYREF
  _BYTE v75[16]; // [rsp+150h] [rbp-140h] BYREF
  GUID pguid; // [rsp+160h] [rbp-130h] BYREF
  GUID v77; // [rsp+170h] [rbp-120h] BYREF
  _BYTE v78[16]; // [rsp+180h] [rbp-110h] BYREF
  GUID v79; // [rsp+190h] [rbp-100h] BYREF
  _BYTE v80[16]; // [rsp+1A0h] [rbp-F0h] BYREF
  struct _GUID v81; // [rsp+1B0h] [rbp-E0h] BYREF
  struct _GUID v82; // [rsp+1C0h] [rbp-D0h] BYREF
  struct _GUID v83; // [rsp+1D0h] [rbp-C0h] BYREF
  struct _GUID v84; // [rsp+1E0h] [rbp-B0h] BYREF
  int v85; // [rsp+1F0h] [rbp-A0h] BYREF
  REC_TYPEINFO *v86; // [rsp+1F8h] [rbp-98h]
  const void *v87; // [rsp+200h] [rbp-90h] BYREF
  _WORD *v88; // [rsp+208h] [rbp-88h]
  char *v89; // [rsp+210h] [rbp-80h]
  _WORD *v90; // [rsp+218h] [rbp-78h]
  MEMBER_DEFN *v91; // [rsp+220h] [rbp-70h]
  serProcTemplate *v92; // [rsp+228h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+230h] [rbp-60h] BYREF
  MEMBER_DEFN *v94; // [rsp+238h] [rbp-58h]
  GEN_PROJECT *v95; // [rsp+240h] [rbp-50h]
  _DWORD *v96; // [rsp+248h] [rbp-48h]
  GEN_PROJECT *v97; // [rsp+250h] [rbp-40h]
  struct INSTMGR *v98; // [rsp+258h] [rbp-38h]
  GEN_PROJECT *v99; // [rsp+260h] [rbp-30h]
  struct INSTMGR *v100; // [rsp+268h] [rbp-28h]
  GEN_PROJECT *v101; // [rsp+270h] [rbp-20h]

  qmemcpy(&pguid, &GUID_NULL, sizeof(pguid));
  qmemcpy(v80, &GUID_NULL, sizeof(v80));
  v55 = EXFRAME::Pebthread(this);
  v97 = (GEN_PROJECT *)*((_QWORD *)v55 + 19);
  IsProjectIncompatible = GEN_PROJECT::IsProjectIncompatible(v97);
  ImpMgr = BASIC_TYPEROOT::GetImpMgr(this, &v52);
  if ( ImpMgr < 0 )
    return (unsigned int)ImpMgr;
  v2 = BASIC_TYPEROOT::Pinstmgr(this);
  CLSIDorIIDofBaseCoClass = IMPMGR::GetCLSIDorIIDofBaseCoClass(v52, 1, 0, (struct _GUID *)((char *)v2 + 312));
  if ( CLSIDorIIDofBaseCoClass < 0 )
    return (unsigned int)CLSIDorIIDofBaseCoClass;
  if ( IMPMGR::GetBaseCount(v52) == 2 )
  {
    v3 = BASIC_TYPEROOT::Pinstmgr(this);
    v28 = IMPMGR::GetCLSIDorIIDofBaseCoClass(v52, 1, 1u, (struct _GUID *)((char *)v3 + 328));
    if ( v28 < 0 )
      return (unsigned int)v28;
  }
  Dtmbrs = BASIC_TYPEROOT::GetDtmbrs(this, &v92);
  if ( Dtmbrs < 0 )
    return (unsigned int)Dtmbrs;
  v46 = BASIC_TYPEROOT::FHasSource(this);
  if ( !v46 && *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 148) )
  {
    v4 = BASIC_TYPEROOT::Pinstmgr(this);
    ProfMemFree(*((_QWORD *)v4 + 38) - 4LL);
    *((_QWORD *)BASIC_TYPEROOT::Pinstmgr(this) + 38) = 0;
    *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 148) = 0;
  }
  if ( !(unsigned int)BASIC_TYPEROOT::IsClassIdentical(this)
    || IsProjectIncompatible
    || (v58 = EXFRAME::Pebthread(this),
        v99 = (GEN_PROJECT *)*((_QWORD *)v58 + 19),
        !(unsigned int)GEN_PROJECT::MakeCompatibleServer(v99)) )
  {
    v30 = CoCreateGuid(&pguid);
    if ( v30 < 0 )
      return (unsigned int)v30;
    qmemcpy(v71, (char *)this + 860, sizeof(v71));
    qmemcpy(v78, v71, sizeof(v78));
    qmemcpy((char *)this + 860, &pguid, 0x10u);
    if ( IsProjectIncompatible
      || (v5 = BASIC_TYPEROOT::GetCLSID(this, &v83), (unsigned int)_(v5, &GUID_NULL))
      && (unsigned int)_(v78, &GUID_NULL)
      || (v59 = EXFRAME::Pebthread(this),
          v101 = (GEN_PROJECT *)*((_QWORD *)v59 + 19),
          !(unsigned int)GEN_PROJECT::MakeCompatibleServer(v101))
      || !(unsigned int)BASIC_TYPEROOT::Access(this) )
    {
      v61 = EXFRAME::Pebthread(this);
      v95 = (GEN_PROJECT *)*((_QWORD *)v61 + 19);
      if ( (unsigned int)GEN_PROJECT::FKeepTlibGuid(v95) )
      {
        qmemcpy(&pguid, &GUID_NULL, sizeof(pguid));
        v63 = EXFRAME::Pebthread(this);
        v57 = *((_QWORD *)v63 + 19);
        if ( LoadTypeLib(*(LPCOLESTR *)(v57 + 5760), &pptlib) >= 0 )
        {
          v89 = (char *)EXFRAME::Pebthread(this) + 16;
          if ( (*(int (__fastcall **)(char *, BSTR *))(*(_QWORD *)v89 + 32LL))(v89, &bstrString) >= 0 )
          {
            v47 = 1;
            if ( ((int (__fastcall *)(ITypeLib *, BSTR, _QWORD, __int64 *, int *, __int16 *))pptlib->lpVtbl->FindName)(
                   pptlib,
                   bstrString,
                   0,
                   &v48,
                   &v85,
                   &v47) >= 0
              && v47 )
            {
              if ( v85 == -1 && (*(int (__fastcall **)(__int64, const void **))(*(_QWORD *)v48 + 24LL))(v48, &v87) >= 0 )
              {
                qmemcpy(v72, v87, sizeof(v72));
                qmemcpy(&pguid, v72, sizeof(pguid));
                (*(void (__fastcall **)(__int64, const void *))(*(_QWORD *)v48 + 152LL))(v48, v87);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
            }
            SysFreeString(bstrString);
          }
          ((void (__fastcall *)(ITypeLib *))pptlib->lpVtbl->Release)(pptlib);
        }
        if ( (unsigned int)_(&pguid, &GUID_NULL) )
        {
          if ( (unsigned int)_((char *)this + 876, &GUID_NULL) )
          {
            v31 = CoCreateGuid(&pguid);
            if ( v31 < 0 )
              return (unsigned int)v31;
          }
          else
          {
            qmemcpy(v73, (char *)this + 876, sizeof(v73));
            qmemcpy(&pguid, v73, sizeof(pguid));
          }
        }
        qmemcpy((char *)this + 876, &pguid, 0x10u);
        v6 = BASIC_TYPEROOT::Pinstmgr(this);
        qmemcpy((char *)v6 + 248, &pguid, 0x10u);
      }
      else
      {
        v65 = EXFRAME::Pebthread(this);
        v67 = (GEN_PROJECT *)*((_QWORD *)v65 + 19);
        if ( !(unsigned int)GEN_PROJECT::MakeCompatibleServer(v67)
          || (CLSID = BASIC_TYPEROOT::GetCLSID(this, &v81), (unsigned int)_(CLSID, &GUID_NULL)) )
        {
          v32 = CoCreateGuid(&pguid);
          if ( v32 < 0 )
            return (unsigned int)v32;
          qmemcpy((char *)this + 876, &pguid, 0x10u);
          v8 = BASIC_TYPEROOT::Pinstmgr(this);
          qmemcpy((char *)v8 + 248, &pguid, 0x10u);
        }
      }
      if ( *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 140) )
      {
        v39 = *((_QWORD *)BASIC_TYPEROOT::Pinstmgr(this) + 36) - 4LL;
        v34 = (_DWORD *)ProfMemRealloc(v39, 20);
        if ( !v34 )
          return 2147942414LL;
        *v34 = 16;
        v60 = v34 + 1;
        v9 = BASIC_TYPEROOT::Pinstmgr(this);
        *((_QWORD *)v9 + 36) = v60;
        *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 140) = 1;
      }
      else
      {
        v40 = (_DWORD *)ProfMemAlloc(20);
        if ( !v40 )
          return 2147942414LL;
        *v40 = 16;
        v68 = v40 + 1;
        v10 = BASIC_TYPEROOT::Pinstmgr(this);
        *((_QWORD *)v10 + 36) = v68;
        *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 140) = 1;
      }
      v50 = (TYPE_DATA *)serProcTemplate::PvTemplate(v92);
      for ( i = TYPE_DATA::HdefnFirstTypeDefn(v50); i != -1; i = MEMBER_DEFN::DwHelpContext(v91) )
      {
        v91 = TYPE_DATA::QvfdefnOfHvfdefn(v50, i, 0);
        if ( (unsigned int)RECTYPE_DEFN::Access(v91) == 1 )
        {
          v62 = BASIC_TYPEROOT::PrtbindOfHrtdefn(this, i);
          v53 = (REC_TYPEINFO *)*((_QWORD *)v62 + 8);
          Guid = REC_TYPEINFO::GetGuid(v53, &v82);
          if ( (unsigned int)_(Guid, &GUID_NULL) )
          {
            CoCreateGuid(&v77);
            (*(void (__fastcall **)(REC_TYPEINFO *, GUID *))(*(_QWORD *)v53 + 176LL))(v53, &v77);
          }
        }
      }
      if ( v46 )
      {
        if ( *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 148) )
        {
          v41 = *((_QWORD *)BASIC_TYPEROOT::Pinstmgr(this) + 38) - 4LL;
          v35 = (_DWORD *)ProfMemRealloc(v41, 20);
          if ( !v35 )
            return 2147942414LL;
          *v35 = 16;
          v70 = v35 + 1;
          v12 = BASIC_TYPEROOT::Pinstmgr(this);
          *((_QWORD *)v12 + 38) = v70;
          *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 148) = 1;
        }
        else
        {
          v42 = (_DWORD *)ProfMemAlloc(20);
          if ( !v42 )
            return 2147942414LL;
          *v42 = 16;
          v64 = v42 + 1;
          v13 = BASIC_TYPEROOT::Pinstmgr(this);
          *((_QWORD *)v13 + 38) = v64;
          *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 148) = 1;
        }
      }
    }
    else
    {
      v14 = BASIC_TYPEROOT::Pinstmgr(this);
      v36 = (_DWORD *)ProfMemRealloc(
                        *((_QWORD *)v14 + 36) - 4LL,
                        (unsigned int)(*(_DWORD *)(*((_QWORD *)v14 + 36) - 4LL) + 20));
      if ( !v36 )
        return 2147942414LL;
      *v36 += 16;
      v69 = v36 + 1;
      v15 = BASIC_TYPEROOT::Pinstmgr(this);
      *((_QWORD *)v15 + 36) = v69;
      v88 = (_WORD *)((char *)BASIC_TYPEROOT::Pinstmgr(this) + 280);
      ++*v88;
      if ( v46 )
      {
        if ( *((_QWORD *)BASIC_TYPEROOT::Pinstmgr(this) + 38) )
        {
          v16 = BASIC_TYPEROOT::Pinstmgr(this);
          v37 = (_DWORD *)ProfMemRealloc(
                            *((_QWORD *)v16 + 38) - 4LL,
                            (unsigned int)(*(_DWORD *)(*((_QWORD *)v16 + 38) - 4LL) + 20));
          if ( !v37 )
            return 2147942414LL;
          *v37 += 16;
          v66 = v37 + 1;
          v17 = BASIC_TYPEROOT::Pinstmgr(this);
          *((_QWORD *)v17 + 38) = v66;
          v90 = (_WORD *)((char *)BASIC_TYPEROOT::Pinstmgr(this) + 296);
          ++*v90;
        }
        else
        {
          v38 = (_DWORD *)ProfMemAlloc(20);
          if ( !v38 )
            return 2147942414LL;
          *v38 = 16;
          v96 = v38 + 1;
          v18 = BASIC_TYPEROOT::Pinstmgr(this);
          *((_QWORD *)v18 + 38) = v96;
          *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 148) = 1;
          v19 = BASIC_TYPEROOT::Pinstmgr(this);
          CoCreateGuid(*((GUID **)v19 + 38));
        }
      }
    }
    qmemcpy(v75, (char *)this + 860, sizeof(v75));
    v98 = BASIC_TYPEROOT::Pinstmgr(this);
    v20 = BASIC_TYPEROOT::Pinstmgr(this);
    qmemcpy((void *)(*((_QWORD *)v98 + 36) + 16LL * (*((unsigned __int16 *)v20 + 140) - 1)), v75, 0x10u);
    if ( (unsigned int)_((char *)this + 876, &GUID_NULL) )
    {
      v33 = CoCreateGuid((GUID *)((char *)this + 876));
      if ( v33 < 0 )
        return (unsigned int)v33;
      qmemcpy(v74, (char *)this + 876, sizeof(v74));
      v21 = BASIC_TYPEROOT::Pinstmgr(this);
      qmemcpy((char *)v21 + 248, v74, 0x10u);
    }
    if ( v46 )
    {
      v100 = BASIC_TYPEROOT::Pinstmgr(this);
      v22 = BASIC_TYPEROOT::Pinstmgr(this);
      CoCreateGuid((GUID *)(*((_QWORD *)v100 + 38) + 16LL * (*((unsigned __int16 *)v22 + 148) - 1)));
    }
    BASIC_TYPEROOT::SetClassIdentical(this, 0);
  }
  if ( v46 && !*((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 148) )
  {
    v43 = (_DWORD *)ProfMemAlloc(20);
    if ( !v43 )
      return 2147942414LL;
    *v43 = 16;
    v54 = v43 + 1;
    v23 = BASIC_TYPEROOT::Pinstmgr(this);
    *((_QWORD *)v23 + 38) = v54;
    *((_WORD *)BASIC_TYPEROOT::Pinstmgr(this) + 148) = 1;
    v24 = BASIC_TYPEROOT::Pinstmgr(this);
    CoCreateGuid(*((GUID **)v24 + 38));
  }
  v50 = (TYPE_DATA *)serProcTemplate::PvTemplate(v92);
  for ( j = TYPE_DATA::HdefnFirstTypeDefn(v50); j != -1; j = MEMBER_DEFN::DwHelpContext(v94) )
  {
    v94 = TYPE_DATA::QvfdefnOfHvfdefn(v50, j, 0);
    if ( (unsigned int)RECTYPE_DEFN::Access(v94) == 1 )
    {
      v56 = BASIC_TYPEROOT::PrtbindOfHrtdefn(this, j);
      v86 = (REC_TYPEINFO *)*((_QWORD *)v56 + 8);
      v25 = REC_TYPEINFO::GetGuid(v86, &v84);
      if ( (unsigned int)_(v25, &GUID_NULL) )
      {
        CoCreateGuid(&v79);
        (*(void (__fastcall **)(REC_TYPEINFO *, GUID *))(*(_QWORD *)v86 + 176LL))(v86, &v79);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1801810a0  mov     [rsp-8+arg_0], rcx
0x1801810a5  push    rbp
0x1801810a6  mov     rbp, rsp
0x1801810a9  push    rsi
0x1801810aa  push    rdi
0x1801810ab  sub     rsp, 280h
0x1801810b2  mov     rax, cs:__security_cookie
0x1801810b9  xor     rax, rsp
0x1801810bc  mov     [rbp+var_18], rax
0x1801810c0  lea     rax, [rsp+290h+pguid]
0x1801810c8  lea     rcx, GUID_NULL
0x1801810cf  mov     rdi, rax
0x1801810d2  mov     rsi, rcx
0x1801810d5  mov     ecx, 10h
0x1801810da  rep movsb
0x1801810dc  lea     rax, [rsp+290h+var_F0]
0x1801810e4  lea     rcx, GUID_NULL
0x1801810eb  mov     rdi, rax
0x1801810ee  mov     rsi, rcx
0x1801810f1  mov     ecx, 10h
0x1801810f6  rep movsb
0x1801810f8  mov     rcx, [rbp+arg_0]; this
0x1801810fc  call    ?Pebthread@EXFRAME@@QEAAPEAVEBTHREAD@@XZ; EXFRAME::Pebthread(void)
0x180181101  mov     [rsp+290h+var_200], rax
0x180181109  mov     rax, [rsp+290h+var_200]
0x180181111  mov     rax, [rax+98h]
0x180181118  mov     [rbp+var_40], rax
0x18018111c  mov     rcx, [rbp+var_40]; this
0x180181120  call    ?IsProjectIncompatible@GEN_PROJECT@@QEAAHXZ; GEN_PROJECT::IsProjectIncompatible(void)
0x180181125  mov     [rsp+290h+var_230], eax
0x180181129  lea     rdx, [rsp+290h+var_218]; struct IMPMGR **
0x18018112e  mov     rcx, [rbp+arg_0]; this
0x180181132  call    ?GetImpMgr@BASIC_TYPEROOT@@QEAAJPEAPEAVIMPMGR@@@Z; BASIC_TYPEROOT::GetImpMgr(IMPMGR * *)
0x180181137  mov     [rsp+290h+var_260], eax
0x18018113b  cmp     [rsp+290h+var_260], 0
0x180181140  jge     short loc_18018114B
0x180181142  mov     eax, [rsp+290h+var_260]
0x180181146  jmp     loc_180181EA7
0x18018114b  mov     rcx, [rbp+arg_0]; this
0x18018114f  call    ?Pinstmgr@BASIC_TYPEROOT@@QEAAPEAVINSTMGR@@XZ; BASIC_TYPEROOT::Pinstmgr(void)
0x180181154  add     rax, 138h
0x18018115a  mov     r9, rax; struct _GUID *
0x18018115d  xor     r8d, r8d; unsigned int
0x180181160  mov     edx, 1; int
0x180181165  mov     rcx, [rsp+290h+var_218]; this
0x18018116a  call    ?GetCLSIDorIIDofBaseCoClass@IMPMGR@@QEAAJHKPEAU_GUID@@@Z; IMPMGR::GetCLSIDorIIDofBaseCoClass(int,ulong,_GUID *)
0x18018116f  mov     [rsp+290h+var_260], eax
0x180181173  cmp     [rsp+290h+var_260], 0
0x180181178  jge     short loc_180181183
0x18018117a  mov     eax, [rsp+290h+var_260]
0x18018117e  jmp     loc_180181EA7
0x180181183  mov     rcx, [rsp+290h+var_218]; this
0x180181188  call    ?GetBaseCount@IMPMGR@@QEAAGXZ; IMPMGR::GetBaseCount(void)
0x18018118d  movzx   eax, ax
0x180181190  cmp     eax, 2
0x180181193  jnz     short loc_1801811D0
0x180181195  mov     rcx, [rbp+arg_0]; this
0x180181199  call    ?Pinstmgr@BASIC_TYPEROOT@@QEAAPEAVINSTMGR@@XZ; BASIC_TYPEROOT::Pinstmgr(void)
0x18018119e  add     rax, 148h
0x1801811a4  mov     r9, rax; struct _GUID *
0x1801811a7  mov     r8d, 1; unsigned int
0x1801811ad  mov     edx, 1; int
0x1801811b2  mov     rcx, [rsp+290h+var_218]; this
0x1801811b7  call    ?GetCLSIDorIIDofBaseCoClass@IMPMGR@@QEAAJHKPEAU_GUID@@@Z; IMPMGR::GetCLSIDorIIDofBaseCoClass(int,ulong,_GUID *)
0x1801811bc  mov     [rsp+290h+var_260], eax
0x1801811c0  cmp     [rsp+290h+var_260], 0
0x1801811c5  jge     short loc_1801811D0
0x1801811c7  mov     eax, [rsp+290h+var_260]
0x1801811cb  jmp     loc_180181EA7
0x1801811d0  lea     rdx, [rbp+var_68]; struct DYN_TYPEMEMBERS **
0x1801811d4  mov     rcx, [rbp+arg_0]; this
0x1801811d8  call    ?GetDtmbrs@BASIC_TYPEROOT@@QEAAJPEAPEAVDYN_TYPEMEMBERS@@@Z; BASIC_TYPEROOT::GetDtmbrs(DYN_TYPEMEMBERS * *)
0x1801811dd  mov     [rsp+290h+var_260], eax
0x1801811e1  cmp     [rsp+290h+var_260], 0
0x1801811e6  jge     short loc_1801811F1
0x1801811e8  mov     eax, [rsp+290h+var_260]
0x1801811ec  jmp     loc_180181EA7
0x1801811f1  mov     rcx, [rbp+arg_0]; this
0x1801811f5  call    ?FHasSource@BASIC_TYPEROOT@@QEAAHXZ; BASIC_TYPEROOT::FHasSource(void)
0x1801811fa  mov     [rsp+290h+var_244], eax
0x1801811fe  cmp     [rsp+290h+var_244], 0
0x180181203  jnz     short loc_18018125B
0x180181205  mov     rcx, [rbp+arg_0]; this
0x180181209  call    ?Pinstmgr@BASIC_TYPEROOT@@QEAAPEAVINSTMGR@@XZ; BASIC_TYPEROOT::Pinstmgr(void)
0x18018120e  movzx   eax, word ptr [rax+128h]
0x180181215  test    eax, eax
0x180181217  jle     short loc_18018125B
0x180181219  mov     rcx, [rbp+arg_0]; this
0x18018121d  call    ?Pinstmgr@BASIC_TYPEROOT@@QEAAPEAVINSTMGR@@XZ; BASIC_TYPEROOT::Pinstmgr(void)
0x180181222  mov     rax, [rax+130h]
0x180181229  sub     rax, 4
0x18018122d  mov     rcx, rax
0x180181230  call    ProfMemFree
0x180181235  mov     rcx, [rbp+arg_0]; this
0x180181239  call    ?Pinstmgr@BASIC_TYPEROOT@@QEAAPEAVINSTMGR@@XZ; BASIC_TYPEROOT::Pinstmgr(void)
0x18018123e  mov     qword ptr [rax+130h], 0
0x180181249  mov     rcx, [rbp+arg_0]; this
0x18018124d  call    ?Pinstmgr@BASIC_TYPEROOT@@QEAAPEAVINSTMGR@@XZ; BASIC_TYPEROOT::Pinstmgr(void)
0x180181252  xor     ecx, ecx
0x180181254  mov     [rax+128h], cx
0x18018125b  mov     rcx, [rbp+arg_0]; this
0x18018125f  call    ?IsClassIdentical@BASIC_TYPEROOT@@QEAAHXZ; BASIC_TYPEROOT::IsClassIdentical(void)
0x180181264  test    eax, eax
0x180181266  jz      short loc_1801812A4
0x180181268  cmp     [rsp+290h+var_230], 0
0x18018126d  jnz     short loc_1801812A4
0x18018126f  mov     rcx, [rbp+arg_0]; this
0x180181273  call    ?Pebthread@EXFRAME@@QEAAPEAVEBTHREAD@@XZ; EXFRAME::Pebthread(void)
0x180181278  mov     [rsp+290h+var_1E8], rax
0x180181280  mov     rax, [rsp+290h+var_1E8]
0x180181288  mov     rax, [rax+98h]
0x18018128f  mov     [rbp+var_30], rax
0x180181293  mov     rcx, [rbp+var_30]; this
0x180181297  call    ?MakeCompatibleServer@GEN_PROJECT@@QEAAHXZ; GEN_PROJECT::MakeCompatibleServer(void)
0x18018129c  test    eax, eax
0x18018129e  jnz     loc_180181D22
0x1801812a4  lea     rcx, [rsp+290h+pguid]; pguid
0x1801812ac  call    cs:__imp_CoCreateGuid
0x1801812b2  mov     [rsp+290h+var_260], eax
0x1801812b6  cmp     [rsp+290h+var_260], 0
0x1801812bb  jge     short loc_1801812C6
0x1801812bd  mov     eax, [rsp+290h+var_260]
0x1801812c1  jmp     loc_180181EA7
0x1801812c6  lea     rax, [rsp+290h+var_180]
0x1801812ce  mov     rcx, [rbp+arg_0]
0x1801812d2  mov     rdi, rax
0x1801812d5  lea     rsi, [rcx+35Ch]
0x1801812dc  mov     ecx, 10h
0x1801812e1  rep movsb
0x1801812e3  lea     rax, [rsp+290h+var_110]
0x1801812eb  lea     rcx, [rsp+290h+var_180]
0x1801812f3  mov     rdi, rax
0x1801812f6  mov     rsi, rcx
0x1801812f9  mov     ecx, 10h
0x1801812fe  rep movsb
0x180181300  mov     rax, [rbp+arg_0]
0x180181304  lea     rcx, [rsp+290h+pguid]
0x18018130c  lea     rdi, [rax+35Ch]
0x180181313  mov     rsi, rcx
0x180181316  mov     ecx, 10h
0x18018131b  rep movsb
0x18018131d  cmp     [rsp+290h+var_230], 0
0x180181322  jnz     short loc_1801813A2
0x180181324  lea     rdx, [rsp+290h+var_C0]; retstr
0x18018132c  mov     rcx, [rbp+arg_0]; this
0x180181330  call    ?GetCLSID@BASIC_TYPEROOT@@QEAA?AU_GUID@@XZ; BASIC_TYPEROOT::GetCLSID(void)
0x180181335  lea     rdx, GUID_NULL
0x18018133c  mov     rcx, rax
0x18018133f  call    __
0x180181344  test    eax, eax
0x180181346  jz      short loc_180181360
0x180181348  lea     rdx, GUID_NULL
0x18018134f  lea     rcx, [rsp+290h+var_110]
0x180181357  call    __
0x18018135c  test    eax, eax
0x18018135e  jnz     short loc_1801813A2
0x180181360  mov     rcx, [rbp+arg_0]; this
0x180181364  call    ?Pebthread@EXFRAME@@QEAAPEAVEBTHREAD@@XZ; EXFRAME::Pebthread(void)
0x180181369  mov     [rsp+290h+var_1E0], rax
0x180181371  mov     rax, [rsp+290h+var_1E0]
0x180181379  mov     rax, [rax+98h]
0x180181380  mov     [rbp+var_20], rax
0x180181384  mov     rcx, [rbp+var_20]; this
0x180181388  call    ?MakeCompatibleServer@GEN_PROJECT@@QEAAHXZ; GEN_PROJECT::MakeCompatibleServer(void)
0x18018138d  test    eax, eax
0x18018138f  jz      short loc_1801813A2
0x180181391  mov     rcx, [rbp+arg_0]
0x180181395  call    ?Access@BASIC_TYPEROOT@@QEBA?AW4ACCESS@@XZ; BASIC_TYPEROOT::Access(void)
0x18018139a  test    eax, eax
0x18018139c  jnz     loc_1801819F9
0x1801813a2  mov     rcx, [rbp+arg_0]; this
0x1801813a6  call    ?Pebthread@EXFRAME@@QEAAPEAVEBTHREAD@@XZ; EXFRAME::Pebthread(void)
0x1801813ab  mov     [rsp+290h+var_1D0], rax
0x1801813b3  mov     rax, [rsp+290h+var_1D0]
0x1801813bb  mov     rax, [rax+98h]
0x1801813c2  mov     [rbp+var_50], rax
0x1801813c6  mov     rcx, [rbp+var_50]; this
0x1801813ca  call    ?FKeepTlibGuid@GEN_PROJECT@@QEAAHXZ; GEN_PROJECT::FKeepTlibGuid(void)
0x1801813cf  test    eax, eax
0x1801813d1  jz      loc_180181633
0x1801813d7  lea     rax, [rsp+290h+pguid]
0x1801813df  lea     rcx, GUID_NULL
0x1801813e6  mov     rdi, rax
0x1801813e9  mov     rsi, rcx
0x1801813ec  mov     ecx, 10h
0x1801813f1  rep movsb
0x1801813f3  mov     rcx, [rbp+arg_0]; this
0x1801813f7  call    ?Pebthread@EXFRAME@@QEAAPEAVEBTHREAD@@XZ; EXFRAME::Pebthread(void)
0x1801813fc  mov     [rsp+290h+var_1C0], rax
0x180181404  mov     rax, [rsp+290h+var_1C0]
0x18018140c  mov     rax, [rax+98h]
0x180181413  mov     [rsp+290h+var_1F0], rax
0x18018141b  lea     rdx, [rsp+290h+pptlib]; pptlib
0x180181420  mov     rax, [rsp+290h+var_1F0]
0x180181428  mov     rcx, [rax+1680h]; szFile
0x18018142f  call    cs:__imp_LoadTypeLib
0x180181435  test    eax, eax
0x180181437  jl      loc_18018155C
0x18018143d  mov     rcx, [rbp+arg_0]; this
0x180181441  call    ?Pebthread@EXFRAME@@QEAAPEAVEBTHREAD@@XZ; EXFRAME::Pebthread(void)
0x180181446  add     rax, 10h
0x18018144a  mov     [rbp+var_80], rax
0x18018144e  mov     rax, [rbp+var_80]
0x180181452  mov     rax, [rax]
0x180181455  lea     rdx, [rbp+bstrString]
0x180181459  mov     rcx, [rbp+var_80]
0x18018145d  call    qword ptr [rax+20h]
0x180181460  test    eax, eax
0x180181462  jl      loc_18018154C
0x180181468  mov     eax, 1
0x18018146d  mov     [rsp+290h+var_240], ax
0x180181472  mov     rax, [rsp+290h+pptlib]
0x180181477  mov     rax, [rax]
0x18018147a  lea     rcx, [rsp+290h+var_240]
0x18018147f  mov     [rsp+290h+var_268], rcx
0x180181484  lea     rcx, [rsp+290h+var_A0]
0x18018148c  mov     [rsp+290h+var_270], rcx
0x180181491  lea     r9, [rsp+290h+var_238]
0x180181496  xor     r8d, r8d
0x180181499  mov     rdx, [rbp+bstrString]
0x18018149d  mov     rcx, [rsp+290h+pptlib]
0x1801814a2  call    qword ptr [rax+58h]
0x1801814a5  test    eax, eax
0x1801814a7  jl      loc_180181542
0x1801814ad  movzx   eax, [rsp+290h+var_240]
0x1801814b2  test    eax, eax
0x1801814b4  jz      loc_180181542
0x1801814ba  cmp     [rsp+290h+var_A0], 0FFFFFFFFh
0x1801814c2  jnz     short loc_180181532
0x1801814c4  mov     rax, [rsp+290h+var_238]
0x1801814c9  mov     rax, [rax]
0x1801814cc  lea     rdx, [rsp+290h+var_90]
0x1801814d4  mov     rcx, [rsp+290h+var_238]
0x1801814d9  call    qword ptr [rax+18h]
0x1801814dc  test    eax, eax
0x1801814de  jl      short loc_180181532
0x1801814e0  lea     rax, [rsp+290h+var_170]
0x1801814e8  mov     rdi, rax
0x1801814eb  mov     rsi, [rsp+290h+var_90]
0x1801814f3  mov     ecx, 10h
0x1801814f8  rep movsb
0x1801814fa  lea     rax, [rsp+290h+pguid]
0x180181502  lea     rcx, [rsp+290h+var_170]
0x18018150a  mov     rdi, rax
0x18018150d  mov     rsi, rcx
0x180181510  mov     ecx, 10h
0x180181515  rep movsb
0x180181517  mov     rax, [rsp+290h+var_238]
0x18018151c  mov     rax, [rax]
0x18018151f  mov     rdx, [rsp+290h+var_90]
0x180181527  mov     rcx, [rsp+290h+var_238]
0x18018152c  call    qword ptr [rax+98h]
0x180181532  mov     rax, [rsp+290h+var_238]
0x180181537  mov     rax, [rax]
0x18018153a  mov     rcx, [rsp+290h+var_238]
0x18018153f  call    qword ptr [rax+10h]
0x180181542  mov     rcx, [rbp+bstrString]; bstrString
0x180181546  call    cs:__imp_SysFreeString
0x18018154c  mov     rax, [rsp+290h+pptlib]
0x180181551  mov     rax, [rax]
0x180181554  mov     rcx, [rsp+290h+pptlib]
0x180181559  call    qword ptr [rax+10h]
0x18018155c  lea     rdx, GUID_NULL
0x180181563  lea     rcx, [rsp+290h+pguid]
0x18018156b  call    __
0x180181570  test    eax, eax
0x180181572  jz      short loc_1801815EF
0x180181574  mov     rax, [rbp+arg_0]
0x180181578  add     rax, 36Ch
0x18018157e  lea     rdx, GUID_NULL
0x180181585  mov     rcx, rax
0x180181588  call    __
0x18018158d  test    eax, eax
0x18018158f  jz      short loc_1801815B5
0x180181591  lea     rcx, [rsp+290h+pguid]; pguid
0x180181599  call    cs:__imp_CoCreateGuid
0x18018159f  mov     [rsp+290h+var_260], eax
0x1801815a3  cmp     [rsp+290h+var_260], 0
0x1801815a8  jge     short loc_1801815B3
0x1801815aa  mov     eax, [rsp+290h+var_260]
0x1801815ae  jmp     loc_180181EA7
0x1801815b3  jmp     short loc_1801815EF
0x1801815b5  lea     rax, [rsp+290h+var_160]
0x1801815bd  mov     rcx, [rbp+arg_0]
0x1801815c1  mov     rdi, rax
0x1801815c4  lea     rsi, [rcx+36Ch]
0x1801815cb  mov     ecx, 10h
0x1801815d0  rep movsb
0x1801815d2  lea     rax, [rsp+290h+pguid]
0x1801815da  lea     rcx, [rsp+290h+var_160]
0x1801815e2  mov     rdi, rax
0x1801815e5  mov     rsi, rcx
0x1801815e8  mov     ecx, 10h
0x1801815ed  rep movsb
0x1801815ef  mov     rax, [rbp+arg_0]
0x1801815f3  lea     rcx, [rsp+290h+pguid]
0x1801815fb  lea     rdi, [rax+36Ch]
0x180181602  mov     rsi, rcx
0x180181605  mov     ecx, 10h
0x18018160a  rep movsb
  ... truncated ...
```
