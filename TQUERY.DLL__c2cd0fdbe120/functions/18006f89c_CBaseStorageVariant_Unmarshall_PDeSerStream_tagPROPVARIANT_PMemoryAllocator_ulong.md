# CBaseStorageVariant::Unmarshall(PDeSerStream &,tagPROPVARIANT &,PMemoryAllocator &,ulong)

- ea: `0x18006f89c`
- end: `0x1800703eb`
- name: `?Unmarshall@CBaseStorageVariant@@SAJAEAVPDeSerStream@@AEAUtagPROPVARIANT@@AEAVPMemoryAllocator@@K@Z`
- size: `2895`
- prototype: `__int64 __fastcall(struct PDeSerStream *, struct tagPROPVARIANT *, struct PMemoryAllocator *, unsigned int)`
- caller_count: `5`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18006bdb8`
- `0x18006dca8`
- `0x18006f850`
- `0x18006f89c`
- `0x1801b3568`

## callees

- `0x18006f89c`
- `0x1800db68c`
- `0x180147238`
- `0x180189cce`
- `0x1801a9604`
- `0x1801b31bc`
- `0x1801b8020`
- `0x1802c0010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006f9d9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006ff88`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1802b9e71`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006f9d9`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18006ff88`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1802b9e71`
- `OLEAUT32!__imp_SafeArrayAllocData` at `0x18006fd9f`
- `OLEAUT32!__imp_SafeArrayAllocData` at `0x18006fd9f`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x18006fdb1`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x18007025c`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x18006fdb1`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x18007025c`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x18006fd1f`
- `OLEAUT32!__imp_SafeArrayAllocDescriptorEx` at `0x18006fd1f`

## string_xrefs

- `0x18006fb32`: `onecoreuap\base\appmodel\search\common\stgvar\stgvarb.cxx`

## pseudocode

```c
__int64 __fastcall CBaseStorageVariant::Unmarshall(
        struct PDeSerStream *a1,
        struct tagPROPVARIANT *a2,
        struct PMemoryAllocator *a3,
        unsigned int a4)
{
  void **p_pvData; // rbx
  unsigned int v8; // edi
  unsigned __int64 v9; // r15
  VARTYPE v10; // ax
  unsigned int v11; // r12d
  char v12; // r13
  __int16 v13; // cx
  BSTR v15; // rax
  unsigned int v16; // edx
  unsigned int v17; // edx
  unsigned int v18; // edx
  unsigned int v19; // edx
  const wchar_t *bstrVal; // rcx
  HRESULT v21; // eax
  unsigned int v22; // eax
  unsigned __int64 v23; // rcx
  unsigned int v24; // edx
  unsigned int v25; // edx
  __int64 jj; // rbx
  unsigned int v27; // eax
  unsigned int v28; // r15d
  __int64 v29; // rdx
  const wchar_t *v30; // rcx
  UINT v31; // r13d
  __int16 v32; // bx
  unsigned int v33; // ebx
  USHORT v34; // dx
  unsigned int vt; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  ULONG v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  __int64 v50; // r13
  ULONG v51; // eax
  LONG v52; // eax
  SAFEARRAY *v53; // rax
  BSTR v54; // r8
  unsigned __int64 v55; // rbx
  __int64 nn; // r9
  unsigned int v57; // edx
  unsigned int v58; // edx
  unsigned int v59; // edx
  unsigned int v60; // edx
  unsigned int v61; // edx
  unsigned int v62; // edx
  unsigned int v63; // edx
  __int64 v64; // r14
  unsigned int v65; // eax
  unsigned int v66; // r13d
  BSTR v67; // rdx
  const wchar_t *v68; // rcx
  bool v69; // zf
  __int64 v70; // r15
  __int64 i3; // r14
  bool v72; // zf
  unsigned int v73; // edx
  unsigned int v74; // edx
  unsigned int v75; // edx
  unsigned int v76; // edx
  unsigned int v77; // edx
  unsigned int v78; // edx
  unsigned int v79; // edx
  LONG v80; // eax
  unsigned int v81; // eax
  bool v82; // zf
  int v83; // ecx
  unsigned int v84; // edx
  LARGE_INTEGER hVal; // rdx
  int v86; // r8d
  BYTE *pData; // rdx
  __int64 ulVal; // r8
  unsigned int v89; // edx
  unsigned int v90; // edx
  unsigned int v91; // edx
  unsigned int v92; // edx
  unsigned int v93; // edx
  unsigned int mm; // ebx
  __int64 j; // rbx
  __int64 ii; // rbx
  bool v97; // zf
  unsigned int v98; // ecx
  bool v99; // zf
  __int64 v100; // r15
  __int64 i4; // r14
  __int64 v102; // r15
  __int64 i5; // r14
  __int64 v104; // r15
  __int64 i2; // r14
  __int64 v106; // r15
  unsigned int i1; // r14d
  __int64 v108; // r12
  __int64 v109; // r14
  int v110; // r15d
  struct tagPROPVARIANT *v111; // rax
  unsigned int v112; // r9d
  LARGE_INTEGER v113; // rax
  unsigned int v114; // eax
  __int64 v115; // r15
  unsigned int v116; // eax
  unsigned int v117; // eax
  unsigned int v118; // eax
  unsigned int v119; // eax
  unsigned int v120; // eax
  unsigned int v121; // edx
  unsigned int v122; // edx
  unsigned int v123; // edx
  unsigned int v124; // edx
  __int64 v125; // rbx
  int v126; // r15d
  __int64 m; // rbx
  unsigned int v128; // eax
  unsigned int v129; // r13d
  __int64 v130; // rdx
  unsigned int v131; // edx
  unsigned int v132; // edx
  __int64 i; // rbx
  __int64 k; // rbx
  __int64 n; // rbx
  unsigned int kk; // r15d
  unsigned int v137; // r13d
  __int64 v138; // rdx
  unsigned int v139; // eax
  unsigned int v140; // r15d
  __int64 v141; // rdx
  int v142; // [rsp+20h] [rbp-10h]
  UINT v143; // [rsp+24h] [rbp-Ch]
  SAFEARRAY *ppsaOut; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+38h]
  int v147; // [rsp+88h] [rbp+58h] BYREF

  v147 = a4;
  if ( a4 > 0x1000 )
  {
    v147 = 4096;
    SearchIndexerDiagnosticTelemetry::QueryParserRecursionLimitReach<int>(&v147);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\stgvar\\stgvarb.cxx",
      (const char *)0x8007000ELL,
      v142);
    return 3221225626LL;
  }
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  p_pvData = 0;
  v8 = 0;
  LODWORD(v9) = 0;
  v10 = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
  a2->vt = v10;
  v11 = -1073741811;
  if ( v10 > 0x1002u )
  {
    if ( v10 > 0x1040u )
    {
      if ( v10 > 0x200Au )
      {
        if ( v10 == 8203 || v10 == 8204 || v10 == 8206 || v10 == 8208 || v10 == 8209 || v10 == 8210 || v10 == 8211 )
          goto LABEL_80;
        v83 = v10 - 8214;
        v82 = v10 == 8214;
        goto LABEL_276;
      }
      if ( v10 == 8202 )
        goto LABEL_80;
      if ( v10 != 4167 )
      {
        if ( v10 == 4168 )
        {
          v119 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16, 8);
          a2->lVal = v119;
          v9 = 16LL * v119;
          goto LABEL_158;
        }
        if ( v10 == 8194 || v10 == 8195 || v10 == 8196 || v10 == 8197 || v10 == 8198 )
        {
LABEL_80:
          v31 = (*(unsigned __int16 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 56LL))(
                  a1,
                  16,
                  8);
          if ( v31 >= 0x32 )
            return v11;
          v32 = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 56LL))(a1);
          if ( (*(unsigned int (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1) > 0x40
            || (v32 & 0xF008) != 0 )
          {
            return v11;
          }
          ppsaOut = 0;
          v33 = v31;
          v143 = v31;
          if ( SafeArrayAllocDescriptorEx(a2->vt & 0xDFFF, v31, &ppsaOut) >= 0 )
          {
            v34 = 0;
            ppsaOut->pvData = 0;
            vt = a2->vt;
            if ( vt <= 0x200B )
            {
              if ( vt == 8203 || (v43 = vt - 8194) == 0 )
              {
LABEL_197:
                v42 = 2;
                goto LABEL_106;
              }
              v44 = v43 - 1;
              if ( !v44 || (v45 = v44 - 1) == 0 )
              {
LABEL_92:
                v42 = 4;
                goto LABEL_106;
              }
              v46 = v45 - 1;
              if ( v46 && (v47 = v46 - 1) != 0 && (v48 = v47 - 1) != 0 )
              {
                v49 = v48 - 1;
                if ( v49 )
                {
                  if ( v49 != 2 )
                    return v11;
                  goto LABEL_92;
                }
                v42 = 8;
                v34 = 256;
              }
              else
              {
                v42 = 8;
              }
            }
            else
            {
              v36 = vt - 8204;
              if ( v36 )
              {
                v37 = v36 - 2;
                if ( v37 )
                {
                  v38 = v37 - 2;
                  if ( !v38 || (v39 = v38 - 1) == 0 )
                  {
                    v42 = 1;
                    goto LABEL_106;
                  }
                  v40 = v39 - 1;
                  if ( v40 )
                  {
                    v41 = v40 - 1;
                    if ( v41 && v41 - 3 > 1 )
                      return v11;
                    goto LABEL_92;
                  }
                  goto LABEL_197;
                }
                v42 = 16;
              }
              else
              {
                v42 = 24;
                v34 = 2048;
              }
            }
LABEL_106:
            v50 = 0;
            ppsaOut->fFeatures = v34;
            ppsaOut->cbElements = v42;
            ppsaOut->cLocks = 0;
            while ( 1 )
            {
              if ( (unsigned int)v50 >= v33 )
              {
                v53 = ppsaOut;
                a2->hVal.QuadPart = (LONGLONG)ppsaOut;
                p_pvData = &v53->pvData;
                goto LABEL_111;
              }
              v51 = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
              if ( v51 >= 0xA00000 )
                break;
              ppsaOut->rgsabound[v50].cElements = v51;
              v52 = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 96LL))(a1);
              v33 = v143;
              ppsaOut->rgsabound[v50].lLbound = v52;
              v50 = (unsigned int)(v50 + 1);
            }
            SafeArrayDestroyDescriptor(ppsaOut);
LABEL_95:
            *(_OWORD *)&a2->vt = 0;
            a2->bstrblobVal.pData = 0;
            return v11;
          }
          return 3221225626LL;
        }
        v83 = v10 - 8199;
        v82 = v10 == 8199;
LABEL_276:
        if ( !v82 && v83 != 1 )
          return (unsigned int)-1073741811;
        goto LABEL_80;
      }
      v120 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16, 8);
      a2->lVal = v120;
      v9 = 16LL * v120;
LABEL_155:
      if ( v9 <= 0xFFFFFFFF )
      {
        p_pvData = (void **)&a2->bstrblobVal.pData;
      }
      else
      {
        LODWORD(v9) = -1;
        v8 = -1073741811;
      }
      v12 = 1;
LABEL_61:
      if ( (v8 & 0x80000000) != 0 )
        return v8;
      goto LABEL_11;
    }
    if ( v10 != 4160 )
    {
      if ( v10 > 0x100Cu )
      {
        switch ( v10 )
        {
          case 0x1010u:
          case 0x1011u:
            goto LABEL_168;
          case 0x1012u:
            goto LABEL_185;
          case 0x1013u:
            goto LABEL_265;
        }
        if ( v10 != 4116 && v10 != 4117 )
        {
          if ( (unsigned int)v10 - 4126 > 1 )
            return (unsigned int)-1073741811;
LABEL_264:
          v116 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16, 8);
          v115 = v116;
          a2->lVal = v116;
          goto LABEL_154;
        }
      }
      else
      {
        if ( v10 == 4108 )
        {
          v114 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16, 8);
          a2->lVal = v114;
          v115 = 3LL * v114;
LABEL_154:
          v9 = 8 * v115;
          goto LABEL_155;
        }
        if ( v10 == 4099 || v10 == 4100 )
          goto LABEL_265;
        if ( v10 != 4101 && v10 != 4102 && v10 != 4103 )
        {
          if ( v10 != 4104 )
          {
            if ( v10 != 4106 )
            {
              if ( v10 != 4107 )
                return (unsigned int)-1073741811;
              goto LABEL_185;
            }
LABEL_265:
            v117 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(
                     a1,
                     16,
                     8);
            a2->lVal = v117;
            v9 = 4LL * v117;
            goto LABEL_158;
          }
          goto LABEL_264;
        }
      }
    }
    v118 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16, 8);
    a2->lVal = v118;
    v9 = 8LL * v118;
    goto LABEL_158;
  }
  if ( v10 == 4098 )
  {
LABEL_185:
    v81 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16, 8);
    a2->lVal = v81;
    v9 = 2LL * v81;
LABEL_158:
    if ( v9 <= 0xFFFFFFFF )
    {
      p_pvData = (void **)&a2->bstrblobVal.pData;
    }
    else
    {
      LODWORD(v9) = -1;
      v8 = -1073741811;
    }
    v12 = 0;
    goto LABEL_61;
  }
  if ( v10 <= 0x13u )
  {
    if ( v10 == 19 )
      goto LABEL_45;
    if ( v10 > 8u )
    {
      if ( v10 != 10 )
      {
        if ( v10 != 11 )
        {
          switch ( v10 )
          {
            case 0xCu:
              v111 = (struct tagPROPVARIANT *)(**(__int64 (__fastcall ***)(struct PMemoryAllocator *, __int64))a3)(
                                                a3,
                                                24);
              v112 = v147 + 1;
              a2->hVal.QuadPart = (LONGLONG)v111;
              CBaseStorageVariant::Unmarshall(a1, v111, a3, v112);
              a2->vt = 12;
              goto LABEL_10;
            case 0xEu:
              (*(void (__fastcall **)(struct PDeSerStream *, struct tagPROPVARIANT *, __int64))(*(_QWORD *)a1 + 160LL))(
                a1,
                a2,
                16);
              a2->vt = 14;
              goto LABEL_10;
            case 0x10u:
            case 0x11u:
              a2->cVal = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64))(*(_QWORD *)a1 + 8LL))(a1, 16);
              goto LABEL_10;
          }
          if ( v10 != 18 )
            return (unsigned int)-1073741811;
        }
        goto LABEL_9;
      }
      goto LABEL_45;
    }
    if ( v10 != 8 )
    {
      switch ( v10 )
      {
        case 0u:
        case 1u:
          v12 = 0;
          goto LABEL_11;
        case 2u:
LABEL_9:
          a2->iVal = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64))(*(_QWORD *)a1 + 56LL))(a1, 16);
LABEL_10:
          v12 = 0;
          goto LABEL_11;
        case 3u:
        case 4u:
LABEL_45:
          a2->lVal = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(
                       a1,
                       16,
                       8);
          goto LABEL_10;
      }
      if ( v10 != 5 && v10 != 6 )
      {
        v72 = v10 == 7;
LABEL_144:
        if ( !v72 )
          return (unsigned int)-1073741811;
      }
LABEL_145:
      (*(void (__fastcall **)(struct PDeSerStream *, ULONG *, __int64))(*(_QWORD *)a1 + 160LL))(a1, &a2->ulVal, 8);
      goto LABEL_10;
    }
LABEL_167:
    v80 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16);
    p_pvData = (void **)&a2->puuid;
    goto LABEL_169;
  }
  if ( v10 <= 0x41u )
  {
    if ( v10 != 65 )
    {
      switch ( v10 )
      {
        case 0x14u:
        case 0x15u:
          goto LABEL_145;
        case 0x16u:
        case 0x17u:
          goto LABEL_45;
        case 0x1Eu:
          goto LABEL_167;
      }
      if ( v10 != 31 )
      {
        v72 = v10 == 64;
        goto LABEL_144;
      }
      v22 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16, 8);
      v23 = 2LL * v22;
      LODWORD(v9) = 2 * v22;
      if ( v23 > 0xFFFFFFFF )
        LODWORD(v9) = -1;
      p_pvData = (void **)&a2->puuid;
      v8 = v23 > 0xFFFFFFFF ? 0xC000000D : 0;
      v12 = 0;
      if ( v23 > 0xFFFFFFFF )
        p_pvData = 0;
      goto LABEL_61;
    }
LABEL_168:
    v80 = (*(__int64 (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 72LL))(a1, 16, 8);
    a2->lVal = v80;
    p_pvData = (void **)&a2->bstrblobVal.pData;
LABEL_169:
    LODWORD(v9) = v80;
LABEL_111:
    v12 = 0;
    goto LABEL_11;
  }
  switch ( v10 )
  {
    case 'B':
    case 'C':
    case 'D':
    case 'E':
      return (unsigned int)-1073741811;
    case 'F':
      goto LABEL_168;
    case 'G':
      v113.QuadPart = (**(__int64 (__fastcall ***)(struct PMemoryAllocator *, __int64, __int64))a3)(a3, 16, 8);
      a2->hVal = v113;
      if ( !v113.QuadPart )
        return (unsigned int)-1073741670;
      *a2->plVal = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
      LODWORD(v9) = *a2->plVal - 4;
      *(_DWORD *)(a2->hVal.QuadPart + 4) = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
      p_pvData = (void **)(a2->hVal.QuadPart + 8);
      break;
    case 'H':
      LODWORD(v9) = 16;
      p_pvData = (void **)&a2->puuid;
      break;
    default:
      return (unsigned int)-1073741811;
  }
  v12 = 0;
LABEL_11:
  v13 = a2->vt & 0x2000;
  if ( !v13 && (!(_DWORD)v9 || v8) )
  {
    if ( p_pvData )
      *p_pvData = 0;
    return v8;
  }
  if ( (unsigned int)v9 >= 0xA00000 )
    return v11;
  if ( a2->vt != 8 )
  {
    if ( !v13 )
    {
      v15 = (BSTR)(**(__int64 (__fastcall ***)(struct PMemoryAllocator *, _QWORD))a3)(a3, (unsigned int)v9);
      goto LABEL_21;
    }
    if ( SafeArrayAllocData(a2->parray) >= 0 )
    {
LABEL_22:
      if ( *p_pvData )
      {
        if ( v12 )
          memset_0(*p_pvData, 0, (unsigned int)v9);
        v16 = a2->vt;
        if ( v16 <= 0x1015 )
        {
          if ( v16 == 4117 )
            goto LABEL_215;
          if ( v16 <= 0x1006 )
          {
            if ( v16 == 4102 )
              goto LABEL_215;
            if ( v16 <= 0x47 )
            {
              if ( v16 == 71 )
              {
                hVal = a2->hVal;
                v86 = *(_DWORD *)hVal.QuadPart;
                pData = *(BYTE **)(hVal.QuadPart + 8);
                ulVal = (unsigned int)(v86 - 4);
              }
              else
              {
                v17 = v16 - 8;
                if ( !v17 )
                {
                  (*(void (__fastcall **)(struct PDeSerStream *, LARGE_INTEGER, _QWORD))(*(_QWORD *)a1 + 24LL))(
                    a1,
                    a2->hVal,
                    (unsigned int)v9);
                  goto LABEL_35;
                }
                v18 = v17 - 22;
                if ( !v18 )
                {
                  (*(void (__fastcall **)(struct PDeSerStream *, LARGE_INTEGER, _QWORD))(*(_QWORD *)a1 + 24LL))(
                    a1,
                    a2->hVal,
                    (unsigned int)v9);
                  v21 = StringCchLengthA(a2->pszVal, (unsigned int)v9, 0);
                  goto LABEL_37;
                }
                v19 = v18 - 1;
                if ( !v19 )
                {
                  (*(void (__fastcall **)(struct PDeSerStream *, LARGE_INTEGER, _QWORD))(*(_QWORD *)a1 + 40LL))(
                    a1,
                    a2->hVal,
                    (unsigned int)v9 >> 1);
LABEL_35:
                  bstrVal = a2->bstrVal;
                  if ( !bstrVal )
                    return (unsigned int)-1073741811;
                  v21 = StringLengthWorkerW(bstrVal, (unsigned __int64)(unsigned int)v9 >> 1, 0);
LABEL_37:
                  if ( v21 >= 0 )
                    return v8;
                  return (unsigned int)-1073741811;
                }
                v84 = v19 - 34;
                if ( v84 && v84 != 5 )
                  return (unsigned int)-1073741811;
                ulVal = a2->ulVal;
                pData = a2->bstrblobVal.pData;
              }
LABEL_283:
              (*(void (__fastcall **)(struct PDeSerStream *, BYTE *, __int64))(*(_QWORD *)a1 + 160LL))(a1, pData, ulVal);
              return v8;
            }
            v89 = v16 - 72;
            if ( !v89 )
            {
              pData = a2->pbVal;
              ulVal = 16;
              goto LABEL_283;
            }
            v90 = v89 - 4026;
            if ( v90 )
            {
              v91 = v90 - 1;
              if ( !v91 )
              {
LABEL_307:
                for ( i = 0; (unsigned int)i < a2->lVal; i = (unsigned int)(i + 1) )
                  *(_DWORD *)&a2->bstrblobVal.pData[4 * i] = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
                return v8;
              }
              goto LABEL_304;
            }
            goto LABEL_310;
          }
          if ( v16 > 0x1010 )
          {
            v131 = v16 - 4113;
            if ( v131 )
            {
              v91 = v131 - 1;
              if ( v91 )
              {
LABEL_304:
                v132 = v91 - 1;
                if ( !v132 )
                  goto LABEL_307;
                if ( v132 != 1 )
                  return (unsigned int)-1073741811;
LABEL_215:
                for ( j = 0; (unsigned int)j < a2->lVal; j = (unsigned int)(j + 1) )
                  (*(void (__fastcall **)(struct PDeSerStream *, BYTE *, __int64))(*(_QWORD *)a1 + 160LL))(
                    a1,
                    &a2->bstrblobVal.pData[8 * j],
                    8);
                return v8;
              }
LABEL_310:
              for ( k = 0; (unsigned int)k < a2->lVal; k = (unsigned int)(k + 1) )
                *(_WORD *)&a2->bstrblobVal.pData[2 * k] = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 56LL))(a1);
              return v8;
            }
          }
          else if ( v16 != 4112 )
          {
            v121 = v16 - 4103;
            if ( !v121 )
              goto LABEL_215;
            v122 = v121 - 1;
            if ( !v122 )
            {
              for ( m = 0; (unsigned int)m < a2->lVal; m = (unsigned int)(m + 1) )
              {
                v128 = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
                v129 = v128;
                if ( v128 - 2 > 0x9FFFFD )
                  return (unsigned int)-1073741811;
                *(_QWORD *)&a2->bstrblobVal.pData[8 * m] = SysAllocStringLen(0, ((unsigned __int64)v128 - 1) >> 1);
                v130 = *(_QWORD *)&a2->bstrblobVal.pData[8 * m];
                if ( !v130 )
                  return (unsigned int)-1073741670;
                (*(void (__fastcall **)(struct PDeSerStream *, __int64, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v130, v129);
                if ( (int)StringCchLengthW(
                            *(const wchar_t **)&a2->bstrblobVal.pData[8 * m],
                            (unsigned __int64)v129 >> 1,
                            0) < 0 )
                  return (unsigned int)-1073741811;
              }
              return v8;
            }
            v123 = v122 - 2;
            if ( !v123 )
              goto LABEL_307;
            v124 = v123 - 1;
            if ( v124 )
            {
              if ( v124 == 1 )
              {
                v125 = 0;
                if ( a2->lVal )
                {
                  v126 = v147;
                  do
                  {
                    v8 = CBaseStorageVariant::Unmarshall(
                           a1,
                           (struct tagPROPVARIANT *)&a2->bstrblobVal.pData[24 * v125],
                           a3,
                           v126 + 1);
                    if ( v8 )
                      break;
                    v125 = (unsigned int)(v125 + 1);
                  }
                  while ( (unsigned int)v125 < a2->lVal );
                }
                return v8;
              }
              return (unsigned int)-1073741811;
            }
            goto LABEL_310;
          }
          for ( n = 0; (unsigned int)n < a2->lVal; n = (unsigned int)(n + 1) )
            a2->bstrblobVal.pData[n] = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 8LL))(a1);
          return v8;
        }
        if ( (unsigned __int16)v16 > 0x2008u )
        {
          if ( (unsigned __int16)v16 <= 0x2011u )
          {
            if ( (_WORD)v16 == 8209 || v16 == 8202 || v16 == 8203 || v16 == 8204 || v16 == 8206 )
              goto LABEL_117;
            v99 = v16 == 8208;
LABEL_332:
            if ( !v99 )
              return (unsigned int)-1073741811;
            goto LABEL_117;
          }
          if ( v16 == 8210 || v16 == 8211 )
            goto LABEL_117;
          v98 = v16 - 8214;
          v97 = v16 == 8214;
        }
        else
        {
          if ( (_WORD)v16 == 8200 )
            goto LABEL_117;
          if ( (unsigned __int16)v16 <= 0x2002u )
          {
            if ( (_WORD)v16 != 8194 )
            {
              v24 = v16 - 4126;
              if ( !v24 )
              {
                for ( ii = 0; (unsigned int)ii < a2->lVal; ii = (unsigned int)(ii + 1) )
                {
                  v139 = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
                  v140 = v139;
                  if ( v139 - 1 > 0x9FFFFE )
                    return (unsigned int)-1073741811;
                  *(_QWORD *)&a2->bstrblobVal.pData[8 * ii] = (**(__int64 (__fastcall ***)(struct PMemoryAllocator *, _QWORD))a3)(
                                                                a3,
                                                                v139);
                  v141 = *(_QWORD *)&a2->bstrblobVal.pData[8 * ii];
                  if ( !v141 )
                    return (unsigned int)-1073741670;
                  (*(void (__fastcall **)(struct PDeSerStream *, __int64, _QWORD))(*(_QWORD *)a1 + 24LL))(
                    a1,
                    v141,
                    v140);
                  if ( (int)StringCchLengthA(*(const char **)&a2->bstrblobVal.pData[8 * ii], v140, 0) < 0 )
                    return (unsigned int)-1073741811;
                }
                return v8;
              }
              v25 = v24 - 1;
              if ( !v25 )
              {
                for ( jj = 0; (unsigned int)jj < a2->lVal; jj = (unsigned int)(jj + 1) )
                {
                  v27 = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
                  v28 = v27;
                  if ( v27 - 1 > 0x9FFFFE )
                    return (unsigned int)-1073741811;
                  *(_QWORD *)&a2->bstrblobVal.pData[8 * jj] = (**(__int64 (__fastcall ***)(struct PMemoryAllocator *, _QWORD))a3)(
                                                                a3,
                                                                2 * v27);
                  v29 = *(_QWORD *)&a2->bstrblobVal.pData[8 * jj];
                  if ( !v29 )
                    return (unsigned int)-1073741670;
                  (*(void (__fastcall **)(struct PDeSerStream *, __int64, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v29, v28);
                  v30 = *(const wchar_t **)&a2->bstrblobVal.pData[8 * jj];
                  if ( !v30 || StringLengthWorkerW(v30, v28, 0) < 0 )
                    return (unsigned int)-1073741811;
                }
                return v8;
              }
              v92 = v25 - 33;
              if ( v92 )
              {
                v93 = v92 - 7;
                if ( !v93 )
                {
                  for ( kk = 0; kk < a2->lVal; ++kk )
                  {
                    *(_DWORD *)&a2->bstrblobVal.pData[16 * kk] = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
                    v137 = *(_DWORD *)&a2->bstrblobVal.pData[16 * kk] - 4;
                    *(_DWORD *)&a2->bstrblobVal.pData[16 * kk + 4] = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
                    if ( v137 - 1 > 0x9FFFFE )
                      return (unsigned int)-1073741811;
                    *(_QWORD *)&a2->bstrblobVal.pData[16 * kk + 8] = (**(__int64 (__fastcall ***)(struct PMemoryAllocator *, _QWORD))a3)(
                                                                       a3,
                                                                       v137);
                    v138 = *(_QWORD *)&a2->bstrblobVal.pData[16 * kk + 8];
                    if ( !v138 )
                      return (unsigned int)-1073741670;
                    (*(void (__fastcall **)(struct PDeSerStream *, __int64, _QWORD))(*(_QWORD *)a1 + 160LL))(
                      a1,
                      v138,
                      v137);
                  }
                  return v8;
                }
                if ( v93 == 1 )
                {
                  for ( mm = 0; mm < a2->lVal; ++mm )
                    (*(void (__fastcall **)(struct PDeSerStream *, BYTE *, __int64))(*(_QWORD *)a1 + 160LL))(
                      a1,
                      &a2->bstrblobVal.pData[16 * mm],
                      16);
                  return v8;
                }
                return (unsigned int)-1073741811;
              }
              goto LABEL_215;
            }
LABEL_117:
            v54 = a2->bstrVal;
            LODWORD(v55) = 1;
            for ( nn = 0; (unsigned int)nn < *v54; nn = (unsigned int)(nn + 1) )
            {
              v55 = (unsigned int)v55 * (unsigned __int64)*(unsigned int *)&v54[4 * nn + 12];
              if ( v55 > 0xFFFFFFFF )
                return v11;
            }
            if ( (unsigned __int16)v16 > 0x200Bu )
            {
              v73 = v16 - 8204;
              if ( !v73 )
              {
                v108 = *((_QWORD *)v54 + 2);
                v109 = 0;
                if ( (_DWORD)v55 )
                {
                  v110 = v147;
                  do
                  {
                    v8 = CBaseStorageVariant::Unmarshall(a1, (struct tagPROPVARIANT *)(v108 + 24 * v109), a3, v110 + 1);
                    if ( v8 )
                      break;
                    v109 = (unsigned int)(v109 + 1);
                  }
                  while ( (unsigned int)v109 < (unsigned int)v55 );
                }
                return v8;
              }
              v74 = v73 - 2;
              if ( !v74 )
              {
                v106 = *((_QWORD *)v54 + 2);
                for ( i1 = 0; i1 < (unsigned int)v55; ++i1 )
                  (*(void (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 160LL))(
                    a1,
                    v106 + 16LL * i1,
                    16);
                return v8;
              }
              v75 = v74 - 2;
              if ( !v75 || (v76 = v75 - 1) == 0 )
              {
                v104 = *((_QWORD *)v54 + 2);
                for ( i2 = 0; (unsigned int)i2 < (unsigned int)v55; i2 = (unsigned int)(i2 + 1) )
                  *(_BYTE *)(i2 + v104) = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 8LL))(a1);
                return v8;
              }
              v77 = v76 - 1;
              if ( v77 )
              {
                v78 = v77 - 1;
                if ( !v78 )
                  goto LABEL_139;
                v79 = v78 - 3;
                if ( !v79 )
                  goto LABEL_139;
                v69 = v79 == 1;
LABEL_138:
                if ( !v69 )
                  return (unsigned int)-1073741811;
LABEL_139:
                v70 = *((_QWORD *)v54 + 2);
                for ( i3 = 0; (unsigned int)i3 < (unsigned int)v55; i3 = (unsigned int)(i3 + 1) )
                  *(_DWORD *)(v70 + 4 * i3) = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
                return v8;
              }
            }
            else if ( (_WORD)v16 != 8203 )
            {
              v57 = v16 - 8194;
              if ( v57 )
              {
                v58 = v57 - 1;
                if ( !v58 )
                  goto LABEL_139;
                v59 = v58 - 1;
                if ( !v59 )
                  goto LABEL_139;
                v60 = v59 - 1;
                if ( !v60 || (v61 = v60 - 1) == 0 || (v62 = v61 - 1) == 0 )
                {
                  v100 = *((_QWORD *)v54 + 2);
                  for ( i4 = 0; (unsigned int)i4 < (unsigned int)v55; i4 = (unsigned int)(i4 + 1) )
                    (*(void (__fastcall **)(struct PDeSerStream *, __int64, __int64))(*(_QWORD *)a1 + 160LL))(
                      a1,
                      v100 + 8 * i4,
                      8);
                  return v8;
                }
                v63 = v62 - 1;
                if ( !v63 )
                {
                  v64 = 0;
                  ppsaOut = (SAFEARRAY *)*((_QWORD *)v54 + 2);
                  while ( (unsigned int)v64 < (unsigned int)v55 )
                  {
                    v65 = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 72LL))(a1);
                    v66 = v65;
                    if ( v65 - 2 > 0x9FFFFD )
                      return (unsigned int)-1073741811;
                    v67 = SysAllocStringLen(0, ((unsigned __int64)v65 - 1) >> 1);
                    *((_QWORD *)&ppsaOut->cDims + v64) = v67;
                    if ( !v67 )
                      return (unsigned int)-1073741670;
                    (*(void (__fastcall **)(struct PDeSerStream *, BSTR, _QWORD))(*(_QWORD *)a1 + 24LL))(a1, v67, v66);
                    v68 = (const wchar_t *)*((_QWORD *)&ppsaOut->cDims + v64);
                    if ( !v68 || StringLengthWorkerW(v68, (unsigned __int64)v66 >> 1, 0) < 0 )
                      return (unsigned int)-1073741811;
                    v64 = (unsigned int)(v64 + 1);
                  }
                  return v8;
                }
                v69 = v63 == 2;
                goto LABEL_138;
              }
            }
            v102 = *((_QWORD *)v54 + 2);
            for ( i5 = 0; (unsigned int)i5 < (unsigned int)v55; i5 = (unsigned int)(i5 + 1) )
              *(_WORD *)(v102 + 2 * i5) = (*(__int64 (__fastcall **)(struct PDeSerStream *))(*(_QWORD *)a1 + 56LL))(a1);
            return v8;
          }
          if ( v16 == 8195 || v16 == 8196 || v16 == 8197 )
            goto LABEL_117;
          v98 = v16 - 8198;
          v97 = v16 == 8198;
        }
        if ( v97 )
          goto LABEL_117;
        v99 = v98 == 1;
        goto LABEL_332;
      }
      return 3221225626LL;
    }
    SafeArrayDestroyDescriptor(a2->parray);
    v11 = -1073741670;
    goto LABEL_95;
  }
  if ( (unsigned int)v9 >= 2 )
  {
    v15 = SysAllocStringLen(0, ((unsigned __int64)(unsigned int)v9 - 1) >> 1);
LABEL_21:
    *p_pvData = v15;
    goto LABEL_22;
  }
  return v11;
}

```

## disassembly

```asm
0x18006f89c  mov     [rsp-38h+arg_0], rbx
0x18006f8a1  mov     [rsp-38h+arg_18], r9d
0x18006f8a6  mov     [rsp-38h+arg_10], r8
0x18006f8ab  push    rbp
0x18006f8ac  push    rsi
0x18006f8ad  push    rdi
0x18006f8ae  push    r12
0x18006f8b0  push    r13
0x18006f8b2  push    r14
0x18006f8b4  push    r15
0x18006f8b6  mov     rbp, rsp
0x18006f8b9  sub     rsp, 30h
0x18006f8bd  mov     rsi, rcx
0x18006f8c0  mov     r13, r8
0x18006f8c3  mov     ecx, 1000h
0x18006f8c8  mov     r14, rdx
0x18006f8cb  cmp     r9d, ecx
0x18006f8ce  ja      loc_18006FB22
0x18006f8d4  xor     eax, eax
0x18006f8d6  xorps   xmm0, xmm0
0x18006f8d9  movups  xmmword ptr [rdx], xmm0
0x18006f8dc  mov     [rdx+10h], rax
0x18006f8e0  xor     ebx, ebx
0x18006f8e2  mov     rax, [rsi]
0x18006f8e5  mov     rcx, rsi
0x18006f8e8  xor     edi, edi
0x18006f8ea  mov     byte ptr [rbp+var_10], bl
0x18006f8ed  xor     r15d, r15d
0x18006f8f0  mov     rax, [rax+48h]
0x18006f8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f8f9  movzx   ecx, ax
0x18006f8fc  lea     edx, [rdi+10h]
0x18006f8ff  mov     r9d, 200Bh
0x18006f905  mov     [r14], ax
0x18006f909  mov     eax, 1002h
0x18006f90e  lea     r8d, [rdi+8]
0x18006f912  mov     r12d, 0C000000Dh
0x18006f918  lea     r10d, [r9-1]
0x18006f91c  cmp     ecx, eax
0x18006f91e  ja      loc_18006FC84
0x18006f924  jz      loc_1800701BC
0x18006f92a  cmp     ecx, 13h
0x18006f92d  ja      loc_18006FA91
0x18006f933  jz      loc_18006FAC0
0x18006f939  cmp     ecx, r8d
0x18006f93c  jbe     loc_18006FAF8
0x18006f942  sub     ecx, 0Ah
0x18006f945  jz      loc_18006FAC0
0x18006f94b  sub     ecx, 1
0x18006f94e  jnz     loc_180070139
0x18006f954  mov     rax, [rsi]
0x18006f957  mov     rcx, rsi
0x18006f95a  mov     rax, [rax+38h]
0x18006f95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f963  mov     [r14+8], ax
0x18006f968  mov     r13b, bl
0x18006f96b  mov     r8d, 8
0x18006f971  movzx   ecx, word ptr [r14]
0x18006f975  mov     eax, 2000h
0x18006f97a  and     cx, ax
0x18006f97d  xor     eax, eax
0x18006f97f  cmp     ax, cx
0x18006f982  jnz     short loc_18006F9AD
0x18006f984  test    r15d, r15d
0x18006f987  jnz     short loc_18006F9A9
0x18006f989  test    rbx, rbx
0x18006f98c  jnz     loc_180070267
0x18006f992  mov     eax, edi
0x18006f994  mov     rbx, [rsp+30h+arg_0]
0x18006f999  add     rsp, 30h
0x18006f99d  pop     r15
0x18006f99f  pop     r14
0x18006f9a1  pop     r13
0x18006f9a3  pop     r12
0x18006f9a5  pop     rdi
0x18006f9a6  pop     rsi
0x18006f9a7  pop     rbp
0x18006f9a8  retn
0x18006f9a9  test    edi, edi
0x18006f9ab  jnz     short loc_18006F989
0x18006f9ad  cmp     r15d, 0A00000h
0x18006f9b4  jnb     loc_18006FDCA
0x18006f9ba  cmp     [r14], r8w
0x18006f9be  jnz     loc_18006FAD8
0x18006f9c4  cmp     r15d, 2
0x18006f9c8  jb      loc_18006FDCA
0x18006f9ce  mov     edx, r15d
0x18006f9d1  xor     ecx, ecx; strIn
0x18006f9d3  dec     rdx
0x18006f9d6  shr     rdx, 1; ui
0x18006f9d9  call    cs:__imp_SysAllocStringLen
0x18006f9df  mov     [rbx], rax
0x18006f9e2  mov     rcx, [rbx]; void *
0x18006f9e5  test    rcx, rcx
0x18006f9e8  jz      loc_18006FB49
0x18006f9ee  test    r13b, r13b
0x18006f9f1  jz      short loc_18006F9FD
0x18006f9f3  mov     r8d, r15d; Size
0x18006f9f6  xor     edx, edx; Val
0x18006f9f8  call    memset_0
0x18006f9fd  movzx   edx, word ptr [r14]
0x18006fa01  mov     eax, 1015h
0x18006fa06  cmp     edx, eax
0x18006fa08  ja      loc_18006FBAF
0x18006fa0e  jz      loc_18007030F
0x18006fa14  mov     eax, 1006h
0x18006fa19  cmp     edx, eax
0x18006fa1b  ja      loc_1802B9DB2
0x18006fa21  jz      loc_18007030F
0x18006fa27  cmp     edx, 47h ; 'G'
0x18006fa2a  ja      loc_1800702C4
0x18006fa30  jz      loc_1800702B0
0x18006fa36  sub     edx, 8
0x18006fa39  jz      loc_18006FB13
0x18006fa3f  sub     edx, 16h
0x18006fa42  jz      loc_180070286
0x18006fa48  sub     edx, 1
0x18006fa4b  jnz     loc_18007026F
0x18006fa51  mov     rax, [rsi]
0x18006fa54  mov     r8d, r15d
0x18006fa57  shr     r8d, 1
0x18006fa5a  mov     rax, [rax+28h]
0x18006fa5e  mov     rdx, [r14+8]
0x18006fa62  mov     rcx, rsi
0x18006fa65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa6a  mov     rcx, [r14+8]; psz
0x18006fa6e  test    rcx, rcx
0x18006fa71  jz      short loc_18006FA89
0x18006fa73  mov     edx, r15d
0x18006fa76  xor     r8d, r8d; pcchLength
0x18006fa79  shr     rdx, 1; cchMax
0x18006fa7c  call    StringLengthWorkerW
0x18006fa81  test    eax, eax
0x18006fa83  jns     loc_18006F992
0x18006fa89  mov     edi, r12d
0x18006fa8c  jmp     loc_18006F992
0x18006fa91  cmp     ecx, 41h ; 'A'
0x18006fa94  ja      loc_18007016B
0x18006fa9a  jz      loc_18007011A
0x18006faa0  sub     ecx, 14h
0x18006faa3  jz      loc_18007002E
0x18006faa9  sub     ecx, 1
0x18006faac  jz      loc_18007002E
0x18006fab2  sub     ecx, 1
0x18006fab5  jz      short loc_18006FAC0
0x18006fab7  sub     ecx, 1
0x18006faba  jnz     loc_18006FB53
0x18006fac0  mov     rax, [rsi]
0x18006fac3  mov     rcx, rsi
0x18006fac6  mov     rax, [rax+48h]
0x18006faca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006facf  mov     [r14+8], eax
0x18006fad3  jmp     loc_18006F968
0x18006fad8  cmp     ax, cx
0x18006fadb  jnz     loc_18006FD9B
0x18006fae1  mov     rcx, [rbp+arg_10]
0x18006fae5  mov     edx, r15d
0x18006fae8  mov     rax, [rcx]
0x18006faeb  mov     rax, [rax]
0x18006faee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006faf3  jmp     loc_18006F9DF
0x18006faf8  jz      loc_180070105
0x18006fafe  test    ecx, ecx
0x18006fb00  jz      short loc_18006FB0B
0x18006fb02  sub     ecx, 1
0x18006fb05  jnz     loc_1800700D0
0x18006fb0b  mov     r13b, bl
0x18006fb0e  jmp     loc_18006F971
0x18006fb13  mov     rax, [rsi]
0x18006fb16  mov     r8d, r15d
0x18006fb19  mov     rax, [rax+18h]
0x18006fb1d  jmp     loc_18006FA5E
0x18006fb22  mov     [rbp+arg_18], ecx
0x18006fb25  lea     rcx, [rbp+arg_18]
0x18006fb29  call    ??$QueryParserRecursionLimitReach@H@SearchIndexerDiagnosticTelemetry@@SAX$$QEAH@Z; SearchIndexerDiagnosticTelemetry::QueryParserRecursionLimitReach<int>(int &&)
0x18006fb2e  mov     rcx, [rbp+38h]; this
0x18006fb32  lea     r8, aOnecoreuapBase_204; "onecoreuap\\base\\appmodel\\search\\com"...
0x18006fb39  mov     r9d, 8007000Eh; char *
0x18006fb3f  mov     edx, 0A1h; void *
0x18006fb44  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18006fb49  mov     eax, 0C000009Ah
0x18006fb4e  jmp     loc_18006F994
0x18006fb53  sub     ecx, 7
0x18006fb56  jz      loc_180070105
0x18006fb5c  sub     ecx, 1
0x18006fb5f  jnz     loc_180070025
0x18006fb65  mov     rax, [rsi]
0x18006fb68  mov     rcx, rsi
0x18006fb6b  mov     rax, [rax+48h]
0x18006fb6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fb74  mov     ecx, eax
0x18006fb76  mov     edx, 0FFFFFFFFh
0x18006fb7b  add     rcx, rcx
0x18006fb7e  mov     r15d, ecx
0x18006fb81  cmp     rcx, rdx
0x18006fb84  ja      loc_18006FD93
0x18006fb8a  cmp     rdx, rcx
0x18006fb8d  lea     rbx, [r14+8]
0x18006fb91  sbb     edi, edi
0x18006fb93  xor     eax, eax
0x18006fb95  and     edi, r12d
0x18006fb98  mov     r13b, al
0x18006fb9b  cmp     rcx, rdx
0x18006fb9e  cmova   rbx, rax
0x18006fba2  test    edi, edi
0x18006fba4  jns     loc_18006F96B
0x18006fbaa  jmp     loc_18006F992
0x18006fbaf  mov     eax, 2008h
0x18006fbb4  cmp     dx, ax
0x18006fbb7  ja      loc_18006FE91
0x18006fbbd  jz      loc_18006FEB9
0x18006fbc3  lea     ecx, [rax-6]
0x18006fbc6  cmp     dx, cx
0x18006fbc9  ja      loc_180070327
0x18006fbcf  jz      loc_18006FEB9
0x18006fbd5  sub     edx, 101Eh
0x18006fbdb  jz      loc_180070320
0x18006fbe1  sub     edx, 1
0x18006fbe4  jnz     loc_1800702E7
0x18006fbea  xor     ebx, ebx
0x18006fbec  cmp     ebx, [r14+8]
0x18006fbf0  jnb     loc_18006F992
0x18006fbf6  mov     rax, [rsi]
0x18006fbf9  mov     rcx, rsi
0x18006fbfc  mov     rax, [rax+48h]
0x18006fc00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc05  mov     r15d, eax
0x18006fc08  lea     ecx, [r15-1]
0x18006fc0c  cmp     ecx, 9FFFFEh
0x18006fc12  ja      loc_18006FA89
0x18006fc18  mov     r8, [rbp+arg_10]
0x18006fc1c  lea     edx, [r15+r15]
0x18006fc20  mov     rcx, [r8]
0x18006fc23  mov     rax, [rcx]
0x18006fc26  mov     rcx, r8
0x18006fc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc2e  mov     rcx, [r14+10h]
0x18006fc32  mov     [rcx+rbx*8], rax
0x18006fc36  mov     rax, [r14+10h]
0x18006fc3a  mov     rdx, [rax+rbx*8]
0x18006fc3e  test    rdx, rdx
0x18006fc41  jz      loc_1800701B2
0x18006fc47  mov     rax, [rsi]
0x18006fc4a  mov     r8d, r15d
0x18006fc4d  mov     rcx, rsi
0x18006fc50  mov     rax, [rax+28h]
0x18006fc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fc59  mov     rax, [r14+10h]
0x18006fc5d  mov     rcx, [rax+rbx*8]; psz
0x18006fc61  test    rcx, rcx
0x18006fc64  jz      loc_18006FA89
0x18006fc6a  mov     edx, r15d; cchMax
0x18006fc6d  xor     r8d, r8d; pcchLength
0x18006fc70  call    StringLengthWorkerW
0x18006fc75  test    eax, eax
0x18006fc77  js      loc_18006FA89
0x18006fc7d  inc     ebx
0x18006fc7f  jmp     loc_18006FBEC
0x18006fc84  mov     eax, 1040h
0x18006fc89  cmp     ecx, eax
0x18006fc8b  jbe     loc_1802B9BDF
0x18006fc91  cmp     ecx, r10d
0x18006fc94  jbe     loc_1802B9CEE
0x18006fc9a  sub     ecx, r9d
0x18006fc9d  jz      short loc_18006FCA8
0x18006fc9f  sub     ecx, 1
0x18006fca2  jnz     loc_1800701EC
0x18006fca8  mov     rax, [rsi]
0x18006fcab  mov     rcx, rsi
0x18006fcae  mov     rax, [rax+38h]
0x18006fcb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fcb7  movzx   r13d, ax
0x18006fcbb  cmp     r13d, 32h ; '2'
0x18006fcbf  jnb     loc_18006FDCA
0x18006fcc5  mov     rcx, [rsi]
0x18006fcc8  mov     rax, [rcx+38h]
0x18006fccc  mov     rcx, rsi
0x18006fccf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fcd4  mov     rcx, [rsi]
0x18006fcd7  movzx   ebx, ax
0x18006fcda  mov     rax, [rcx+48h]
0x18006fcde  mov     rcx, rsi
0x18006fce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fce6  cmp     eax, 40h ; '@'
0x18006fce9  ja      loc_18006FDCA
0x18006fcef  mov     eax, 0F008h
0x18006fcf4  xor     ecx, ecx
0x18006fcf6  and     bx, ax
0x18006fcf9  cmp     cx, bx
0x18006fcfc  jnz     loc_18006FDCA
0x18006fd02  mov     [rbp+ppsaOut], rcx
0x18006fd06  lea     r8, [rbp+ppsaOut]; ppsaOut
0x18006fd0a  movzx   ecx, word ptr [r14]
0x18006fd0e  mov     eax, 0DFFFh
0x18006fd13  mov     ebx, r13d
0x18006fd16  and     cx, ax; vt
0x18006fd19  mov     edx, r13d; cDims
0x18006fd1c  mov     [rbp+var_C], ebx
0x18006fd1f  call    cs:__imp_SafeArrayAllocDescriptorEx
0x18006fd25  test    eax, eax
  ... truncated ...
```
