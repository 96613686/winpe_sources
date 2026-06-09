# StructuredQuery1::Solution::ResolveBasic(int,ICondition2 *,STRUCTURED_QUERY_RESOLVE_OPTION,_tagpropertykey,tagCONDITION_OPERATION,wchar_t const *,tagPROPVARIANT const &,wchar_t const *,IRichChunk *,IRichChunk *,IRichChunk *,ICondition2 * *)

- ea: `0x18000f7cc`
- end: `0x18001019d`
- name: `?ResolveBasic@Solution@StructuredQuery1@@AEAAJHPEAUICondition2@@W4STRUCTURED_QUERY_RESOLVE_OPTION@@U_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_WAEBUtagPROPVARIANT@@4PEAUIRichChunk@@66PEAPEAU3@@Z`
- size: `2513`
- prototype: `__int64 __usercall@<rax>(StructuredQuery1::Solution *__hidden this@<rcx>, int@<edx>, struct ICondition2 *@<r8>, enum STRUCTURED_QUERY_RESOLVE_OPTION@<r9d>, struct _tagpropertykey *, tagCONDITION_OPERATION, PCNZWCH lpString1, const struct tagPROPVARIANT *, const wchar_t *, struct IRichChunk *, struct IRichChunk *, struct IRichChunk *, struct ICondition2 **)`
- caller_count: `1`
- callee_count: `21`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ef3c`

## callees

- `0x18000903c`
- `0x1800090c0`
- `0x180009a40`
- `0x18000b180`
- `0x18000c9c4`
- `0x18000ea6c`
- `0x18000f7cc`
- `0x180010620`
- `0x18001079c`
- `0x180010804`
- `0x180010904`
- `0x1800115d4`
- `0x18003174c`
- `0x180045298`
- `0x18004531c`
- `0x18005546c`
- `0x18005daf0`
- `0x18005f7fd`
- `0x18006dc70`
- `0x18006f930`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fad7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000feb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000fad7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000feb8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fe90`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000fe90`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::Solution::ResolveBasic(
        StructuredQuery1::Solution *this,
        int a2,
        struct ICondition2 *a3,
        unsigned int a4,
        struct _tagpropertykey *a5,
        tagCONDITION_OPERATION a6,
        struct _GUID *lpString1,
        const struct tagPROPVARIANT *a8,
        wchar_t *a9,
        struct IRichChunk *a10,
        struct IRichChunk *a11,
        struct IRichChunk *a12,
        struct ICondition2 **a13)
{
  char v14; // r12
  struct IRichChunk *v15; // r15
  const struct tagPROPVARIANT *v16; // r14
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned int v19; // ecx
  unsigned int v20; // r8d
  __int64 v21; // rdx
  wchar_t *v22; // rax
  StructuredQuery1::QueryExpressionCustomization *v23; // rcx
  int CustomHandler; // edi
  int v25; // ecx
  int v26; // edx
  int v27; // r8d
  int v28; // eax
  unsigned int v29; // esi
  int v30; // eax
  struct IRichChunk *v31; // r12
  StructuredQuery1::QueryExpressionCustomization *v32; // rcx
  struct IObjectArray *v33; // r15
  __int64 v34; // r14
  wchar_t **v35; // r8
  LPVOID v36; // rsi
  enum tagCONDITION_OPERATION v37; // r14d
  GUID fmtid; // xmm0
  int v39; // eax
  unsigned __int16 v40; // dx
  int v41; // r10d
  const wchar_t *v42; // rax
  char v43; // di
  DWORD pid; // esi
  GUID v45; // xmm0
  struct IRichChunk *v46; // rcx
  struct IRichChunk v47; // rax
  unsigned __int16 v48; // dx
  char v49; // al
  unsigned int v50; // ecx
  __int64 v51; // rax
  void *v52; // rdx
  const wchar_t *v54; // r12
  const struct _tagpropertykey *v55; // rdx
  wchar_t *v56; // rcx
  const wchar_t *v57; // r9
  struct _GUID *v58; // rbx
  StructuredQuery1::Solution *v59; // rcx
  struct IObjectArray *v60; // rbx
  wchar_t *v61; // rdx
  BSTR *pElems; // rax
  BSTR v63; // rcx
  __int64 v64; // rax
  const wchar_t *v65; // r9
  const wchar_t *v66; // rax
  int v67; // r10d
  const wchar_t *v68; // rax
  __int64 v69; // r8
  int v70; // edi
  unsigned int v71; // eax
  bool v72; // cf
  wchar_t v73; // ax
  struct _GUID *v74; // [rsp+20h] [rbp-E0h]
  const struct _GUID *v75; // [rsp+20h] [rbp-E0h]
  wchar_t *Src; // [rsp+70h] [rbp-90h] BYREF
  enum STRUCTURED_QUERY_RESOLVE_OPTION v77; // [rsp+78h] [rbp-88h]
  BOOL v78; // [rsp+7Ch] [rbp-84h]
  void *v79; // [rsp+80h] [rbp-80h] BYREF
  int v80; // [rsp+88h] [rbp-78h] BYREF
  struct IObjectArray *v81; // [rsp+90h] [rbp-70h] BYREF
  int v82; // [rsp+98h] [rbp-68h] BYREF
  int v83; // [rsp+9Ch] [rbp-64h]
  int v84; // [rsp+A0h] [rbp-60h]
  int v85; // [rsp+A4h] [rbp-5Ch]
  void *v86; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID *v87; // [rsp+B0h] [rbp-50h] BYREF
  struct IRichChunk *v88; // [rsp+B8h] [rbp-48h]
  struct IRichChunk *v89; // [rsp+C0h] [rbp-40h]
  __int64 v90; // [rsp+C8h] [rbp-38h]
  LPVOID pv; // [rsp+D0h] [rbp-30h] BYREF
  int v92; // [rsp+D8h] [rbp-28h]
  int v93; // [rsp+DCh] [rbp-24h]
  struct tagPROPVARIANT v94; // [rsp+E0h] [rbp-20h] BYREF
  BSTR v95; // [rsp+F8h] [rbp-8h]
  LARGE_INTEGER hVal; // [rsp+100h] [rbp+0h]
  wchar_t *v97; // [rsp+108h] [rbp+8h]
  struct _GUID *v98; // [rsp+110h] [rbp+10h] BYREF
  struct tagPROPVARIANT v99; // [rsp+120h] [rbp+20h] BYREF
  struct tagPROPVARIANT pvar; // [rsp+138h] [rbp+38h] BYREF
  struct IRichChunk *v101; // [rsp+150h] [rbp+50h]
  struct ICondition2 **v102; // [rsp+158h] [rbp+58h]
  _QWORD Buf1[3]; // [rsp+160h] [rbp+60h] BYREF

  v14 = a2;
  v15 = a12;
  v16 = a8;
  v97 = a9;
  v89 = a10;
  v93 = a2;
  v17 = *((_QWORD *)this + 5);
  v88 = a11;
  v77 = a4;
  v102 = a13;
  v87 = lpString1;
  v101 = a12;
  v98 = 0;
  if ( !v17 )
  {
    CustomHandler = ((__int64 (__fastcall *)(struct ICondition2 *, GUID *, struct _GUID **))a3->lpVtbl->QueryInterface)(
                      a3,
                      &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                      &v98);
    goto LABEL_56;
  }
  v18 = *(_QWORD *)(v17 + 8);
  v19 = a4 >> 2;
  LOBYTE(v19) = (a4 & 4) == 0;
  v20 = *(_DWORD *)(v18 + 32);
  v21 = *(_QWORD *)(v18 + 40);
  v78 = v19;
  v22 = (wchar_t *)SemanticsUM::FindElementByName<SemanticsUM::Entity>((PCNZWCH)lpString1, v21, v20);
  v23 = (StructuredQuery1::QueryExpressionCustomization *)*((_QWORD *)this + 4);
  Src = v22;
  CustomHandler = StructuredQuery1::QueryExpressionCustomization::ReplacePseudoProperty(v23, a5, &a6);
  if ( CustomHandler >= 0 )
  {
    v85 = 0;
    v25 = 0;
    v80 = 0;
    v84 = 0;
    v26 = v14 & 3;
    v82 = 0;
    v92 = v26;
    v27 = 0;
    v86 = 0;
    if ( v15 )
    {
      v74 = 0;
      v28 = ((__int64 (__fastcall *)(struct IRichChunk *, int *, int *))v15->lpVtbl->GetData)(v15, &v80, &v82);
      v27 = v80;
      CustomHandler = v28;
      v25 = v82;
      v26 = v92;
      v85 = v80;
      v84 = v82;
    }
    else
    {
      CustomHandler = 0;
    }
    if ( CustomHandler >= 0 )
    {
      v94.vt = 3;
      memset(&v94.decVal.scale, 0, 22);
      v94.lVal = v93 & 0xFFFFFFBF;
      v29 = v27 + v25 + (v26 == 2);
      if ( v29 >= (**((unsigned int (__fastcall ***)(char *))this + 7))((char *)this + 56) )
        v29 = (**((__int64 (__fastcall ***)(char *))this + 7))((char *)this + 56);
      v30 = StructuredQuery1::TokenInformation::CreateInstance(v80, v29, this, &v94, v74, &v86);
      v31 = (struct IRichChunk *)v86;
      CustomHandler = v30;
      v85 = v80;
      v84 = v82;
      if ( v30 >= 0 )
      {
        if ( v16->vt == 31 )
        {
          hVal = v16->hVal;
          v95 = 0;
        }
        else
        {
          if ( v16->vt != 4127 )
          {
            CustomHandler = -2147024809;
LABEL_55:
            ((void (__fastcall *)(struct IRichChunk *))v31->lpVtbl->Release)(v31);
            goto LABEL_56;
          }
          pElems = v16->cabstr.pElems;
          v63 = *pElems;
          v95 = pElems[1];
          hVal.QuadPart = (LONGLONG)v63;
        }
        v32 = (StructuredQuery1::QueryExpressionCustomization *)*((_QWORD *)this + 4);
        v79 = 0;
        v33 = 0;
        v81 = 0;
        v34 = 0;
        v90 = 0;
        v83 = 0;
        pv = 0;
        CustomHandler = StructuredQuery1::QueryExpressionCustomization::GetCustomHandler(
                          v32,
                          (const struct IEntity *)Src,
                          (struct IConditionGenerator **)&pv);
        if ( CustomHandler < 0 )
        {
LABEL_49:
          v52 = v79;
          if ( v79 )
          {
            v79 = 0;
            (*(void (__fastcall **)(void *))(*(_QWORD *)v52 + 16LL))(v52);
          }
          if ( v33 )
            ((void (__fastcall *)(struct IObjectArray *))v33->lpVtbl->Release)(v33);
          if ( v34 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          goto LABEL_55;
        }
        v36 = pv;
        v37 = a6;
        if ( pv )
        {
          fmtid = a5->fmtid;
          LODWORD(Buf1[2]) = a5->pid;
          *(GUID *)Buf1 = fmtid;
          if ( !LODWORD(Buf1[2]) && !memcmp_0(Buf1, &PKEY_Null, 0x10u) )
            StructuredQuery1::QueryExpressionCustomization::LookupDefaultProperty(
              *((StructuredQuery1::QueryExpressionCustomization **)this + 4),
              (const struct IEntity *)Src,
              (struct _tagpropertykey *)Buf1);
          pv = 0;
          CustomHandler = StructuredQuery1::GetConditionPropertyNameFromKey(
                            (PROPERTYKEY *)Buf1,
                            (const struct _tagpropertykey *)&pv,
                            v35);
          if ( CustomHandler >= 0 )
          {
            v75 = v87;
            CustomHandler = (*(__int64 (__fastcall **)(LPVOID, char *, LPVOID, _QWORD))(*(_QWORD *)v36 + 40LL))(
                              v36,
                              (char *)this + 8,
                              pv,
                              (unsigned int)v37);
            CoTaskMemFree(pv);
          }
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v36 + 16LL))(v36);
          if ( CustomHandler < 0 )
            goto LABEL_57;
        }
        if ( Src
          && (*(unsigned int (__fastcall **)(wchar_t *))(*(_QWORD *)Src + 72LL))(Src)
          && (a5->pid || memcmp_0(a5, &PKEY_Null, 0x10u)) )
        {
          v39 = StructuredQuery1::InheritsFrom(Src, *(_QWORD *)(*((_QWORD *)this + 5) + 32LL));
          v41 = 0;
          if ( v39 > 0 )
          {
            v94.vt = 31;
            *(_QWORD *)&v94.decVal.scale = 0;
            *(_OWORD *)&v94.decVal.Lo32 = (unsigned __int64)hVal.QuadPart;
            if ( v95 )
            {
              *(_QWORD *)&v99.decVal.scale = 0;
              *(_OWORD *)&v99.decVal.Lo32 = (unsigned __int64)v95;
              v99.vt = 31;
              memset((char *)Buf1 + 2, 0, 22);
              strcpy((char *)Buf1, "\r");
              CustomHandler = StructuredQuery1::Interval::CreateInstance(
                                ILK_EXPLICIT_INCLUDED,
                                &v94,
                                ILK_EXPLICIT_INCLUDED,
                                &v99,
                                v75,
                                (void **)&Buf1[1]);
              if ( CustomHandler >= 0 )
              {
                v66 = StructuredQuery1::_SemanticTypeFromVarType(
                        (StructuredQuery1 *)(unsigned int)v77,
                        SQRO_DONT_RESOLVE_RANGES|SQRO_DONT_MAP_RELATIONS|SQRO_DONT_SIMPLIFY_CONDITION_TREES|SQRO_ALWAYS_ONE_INTERVAL|SQRO_DONT_RESOLVE_DATETIME,
                        0,
                        v65);
                CustomHandler = StructuredQuery1::Solution::MakePredicate(
                                  (__int64)this,
                                  a5,
                                  (enum tagCONDITION_OPERATION)(v67 + 1),
                                  v66,
                                  (PROPVARIANT *)Buf1,
                                  v97,
                                  v67,
                                  v89,
                                  v88,
                                  v31,
                                  v67,
                                  v78,
                                  &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                  &v79);
                (*(void (__fastcall **)(_QWORD))(*(_QWORD *)Buf1[1] + 16LL))(Buf1[1]);
              }
            }
            else
            {
              v42 = (v77 & 0x100) != 0 ? StructuredQuery1::_SemanticTypeFromVarType((StructuredQuery1 *)0x1F, v40) : 0LL;
              CustomHandler = StructuredQuery1::Solution::MakePredicate(
                                (__int64)this,
                                a5,
                                COP_WORD_EQUAL,
                                v42,
                                (PROPVARIANT *)&v94,
                                v97,
                                v41,
                                v89,
                                v88,
                                v31,
                                v41,
                                v78,
                                &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                                &v79);
            }
            v83 = 1;
            if ( CustomHandler < 0 )
            {
LABEL_57:
              v34 = v90;
              goto LABEL_49;
            }
          }
        }
        if ( v79 && (a5->pid || memcmp_0(a5, &PKEY_Null, 0x10u) || v83) )
          goto LABEL_40;
        if ( Src && (int)StructuredQuery1::InheritsFrom(Src, *(_QWORD *)(*((_QWORD *)this + 5) + 80LL)) >= 0 )
        {
          v43 = 1;
        }
        else
        {
          v43 = 0;
          Src = *(wchar_t **)(*((_QWORD *)this + 5) + 80LL);
        }
        pid = a5->pid;
        v45 = a5->fmtid;
        LODWORD(Buf1[2]) = pid;
        *(GUID *)Buf1 = v45;
        if ( !pid && !memcmp_0(Buf1, &PKEY_Null, 0x10u) )
        {
          StructuredQuery1::QueryExpressionCustomization::LookupDefaultProperty(
            *((StructuredQuery1::QueryExpressionCustomization **)this + 4),
            (const struct IEntity *)Src,
            (struct _tagpropertykey *)Buf1);
          pid = Buf1[2];
          if ( !LODWORD(Buf1[2]) && !memcmp_0(Buf1, &PKEY_Null, 0x10u) )
          {
            pid = 6;
            LODWORD(Buf1[2]) = 6;
            *(GUID *)Buf1 = PKEY_FullText.fmtid;
          }
        }
        if ( v95 && v43 )
        {
          *(_QWORD *)&v99.decVal.scale = 0;
          *(_OWORD *)&v99.decVal.Lo32 = (unsigned __int64)v95;
          *(_QWORD *)&pvar.decVal.scale = 0;
          v94.vt = 13;
          memset(&v94.decVal.scale, 0, 22);
          *(_OWORD *)&pvar.decVal.Lo32 = (unsigned __int64)hVal.QuadPart;
          pvar.vt = 31;
          v99.vt = 31;
          CustomHandler = StructuredQuery1::Interval::CreateInstance(
                            ILK_EXPLICIT_INCLUDED,
                            &pvar,
                            ILK_EXPLICIT_INCLUDED,
                            &v99,
                            v75,
                            (void **)&v94.puuid);
          if ( CustomHandler < 0 )
          {
LABEL_73:
            v34 = v90;
            goto LABEL_49;
          }
          v68 = StructuredQuery1::_SemanticTypeFromVarType(
                  (StructuredQuery1 *)(unsigned int)v77,
                  SQRO_DONT_RESOLVE_RANGES|SQRO_DONT_MAP_RELATIONS|SQRO_DONT_SIMPLIFY_CONDITION_TREES|SQRO_ALWAYS_ONE_INTERVAL|SQRO_DONT_RESOLVE_DATETIME,
                  0,
                  v57);
          CustomHandler = StructuredQuery1::Solution::MakePredicate(
                            (__int64)this,
                            (const struct _tagpropertykey *)Buf1,
                            v37,
                            v68,
                            (PROPVARIANT *)&v94,
                            v97,
                            0,
                            v89,
                            v88,
                            v31,
                            0,
                            v78,
                            &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                            (void **)&v81);
          (*((void (__fastcall **)(LARGE_INTEGER))*v94.pbstrVal + 2))(v94.hVal);
          v33 = v81;
LABEL_40:
          if ( CustomHandler >= 0 )
          {
            v50 = 0;
            memset(Buf1, 0, sizeof(Buf1));
            if ( v79 )
            {
              Buf1[0] = v79;
              v50 = 1;
            }
            v34 = v90;
            if ( v90 )
            {
              v64 = v50++;
              Buf1[v64] = v90;
            }
            if ( v33 )
            {
              v51 = v50++;
              Buf1[v51] = v33;
            }
            if ( v50 == 1 )
            {
              CustomHandler = (**(__int64 (__fastcall ***)(_QWORD, GUID *, struct _GUID **))Buf1[0])(
                                Buf1[0],
                                &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                &v98);
            }
            else
            {
              v58 = 0;
              v81 = 0;
              v87 = 0;
              CustomHandler = FixedCapacityObjectCollection::CreateInstance<ICondition>(
                                v50,
                                (__int64)Buf1,
                                (__int64)v35,
                                &v81);
              if ( CustomHandler >= 0 )
              {
                v60 = v81;
                CustomHandler = StructuredQuery1::Solution::MakeCompound(
                                  v59,
                                  CT_OR_CONDITION,
                                  v81,
                                  1,
                                  0,
                                  &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
                                  (void **)&v87);
                ((void (__fastcall *)(struct IObjectArray *))v60->lpVtbl->Release)(v60);
                v58 = v87;
              }
              v98 = v58;
            }
            goto LABEL_49;
          }
          goto LABEL_73;
        }
        Src = 0;
        if ( v37 && v92 == 2 )
        {
          CustomHandler = ((__int64 (__fastcall *)(struct IRichChunk *, _QWORD, _QWORD, wchar_t **, _QWORD))v31->lpVtbl->GetData)(
                            v31,
                            0,
                            0,
                            &Src,
                            0);
          if ( CustomHandler < 0 )
          {
LABEL_108:
            v56 = Src;
            goto LABEL_69;
          }
        }
        else
        {
          v46 = v101;
          if ( v101 )
          {
            v47.lpVtbl = v101->lpVtbl;
          }
          else
          {
            v47.lpVtbl = v31->lpVtbl;
            v46 = v31;
          }
          CustomHandler = ((__int64 (__fastcall *)(struct IRichChunk *, _QWORD, _QWORD, wchar_t **, _QWORD))v47.lpVtbl->GetData)(
                            v46,
                            0,
                            0,
                            &Src,
                            0);
          if ( CustomHandler < 0 )
            goto LABEL_67;
          if ( v37 == COP_IMPLICIT )
          {
            v49 = 0;
            if ( (v93 & 4) != 0 )
            {
              if ( (v93 & 2) != 0 )
              {
                v49 = 1;
              }
              else if ( (v93 & 1) == 0
                     || (v70 = v84) == 0
                     || (v71 = (**((__int64 (__fastcall ***)(char *))this + 7))((char *)this + 56),
                         v72 = v70 + v85 < v71,
                         v49 = 0,
                         !v72) )
              {
                v49 = *((_BYTE *)this + 48);
              }
            }
            v37 = (v49 != 0) + 12;
          }
        }
        if ( (v77 & 0x100) != 0 )
          v54 = StructuredQuery1::_SemanticTypeFromVarType((StructuredQuery1 *)0x1F, v48);
        else
          v54 = 0;
        v81 = 0;
        v33 = 0;
        memset(&pvar, 0, sizeof(pvar));
        CustomHandler = InitPropVariantFromString(Src, &pvar);
        if ( CustomHandler >= 0 )
        {
          CustomHandler = StructuredQuery1::Solution::MakePredicate(
                            (__int64)this,
                            (const struct _tagpropertykey *)Buf1,
                            v37,
                            v54,
                            (PROPVARIANT *)&pvar,
                            v97,
                            0,
                            v89,
                            v88,
                            (struct IRichChunk *)v86,
                            0,
                            v78,
                            &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                            (void **)&v81);
          PropVariantClear((PROPVARIANT *)&pvar);
          pid = Buf1[2];
          v33 = v81;
        }
        if ( CustomHandler >= 0
          && (v77 & 0x200) != 0
          && (StructuredQuery1::IsAnywhereProperty((StructuredQuery1 *)Buf1, v55)
           || pid == 10 && !memcmp_0(Buf1, &PKEY_ItemNameDisplay, 0x10u))
          && (unsigned int)(v37 - 12) <= 1 )
        {
          v56 = Src;
          if ( Src )
          {
            v61 = Src;
            while ( 1 )
            {
              v73 = *v61;
              if ( !*v61 )
                break;
              ++v61;
              if ( v73 == 45 && (unsigned __int16)(*v61 - 48) <= 9u )
              {
                v31 = (struct IRichChunk *)v86;
                v69 = 1;
                if ( v37 == COP_WORD_STARTSWITH )
                  v69 = 7;
                CustomHandler = StructuredQuery1::Solution::MakePredicate(
                                  this,
                                  &PKEY_ItemNameDisplay,
                                  v69,
                                  0,
                                  Src,
                                  &cchOriginalDestLength);
                goto LABEL_108;
              }
            }
          }
          goto LABEL_68;
        }
LABEL_67:
        v56 = Src;
LABEL_68:
        v31 = (struct IRichChunk *)v86;
LABEL_69:
        CoTaskMemFree(v56);
        goto LABEL_40;
      }
    }
  }
LABEL_56:
  *v102 = (struct ICondition2 *)v98;
  return (unsigned int)CustomHandler;
}

```

## disassembly

```asm
0x18000f7cc  push    rbp
0x18000f7ce  push    rbx
0x18000f7cf  push    rsi
0x18000f7d0  push    rdi
0x18000f7d1  push    r12
0x18000f7d3  push    r13
0x18000f7d5  push    r14
0x18000f7d7  push    r15
0x18000f7d9  lea     rbp, [rsp-88h]
0x18000f7e1  sub     rsp, 188h
0x18000f7e8  mov     rax, cs:__security_cookie
0x18000f7ef  xor     rax, rsp
0x18000f7f2  mov     [rbp+0C0h+var_48], rax
0x18000f7f6  mov     rax, [rbp+0C0h+lpString1]
0x18000f7fd  mov     rbx, rcx
0x18000f800  mov     rcx, [rbp+0C0h+arg_40]
0x18000f807  mov     r12d, edx
0x18000f80a  mov     r15, [rbp+0C0h+arg_58]
0x18000f811  mov     r10d, r9d
0x18000f814  mov     r14, [rbp+0C0h+arg_38]
0x18000f81b  mov     r13, [rbp+0C0h+arg_20]
0x18000f822  mov     [rbp+0C0h+var_B8], rcx
0x18000f826  mov     rcx, [rbp+0C0h+arg_48]
0x18000f82d  mov     [rbp+0C0h+var_100], rcx
0x18000f831  mov     rcx, [rbp+0C0h+arg_50]
0x18000f838  mov     [rbp+0C0h+var_E4], edx
0x18000f83b  mov     rdx, [rbx+28h]
0x18000f83f  mov     [rbp+0C0h+var_108], rcx
0x18000f843  mov     rcx, [rbp+0C0h+arg_60]
0x18000f84a  mov     dword ptr [rsp+1C0h+var_148], r9d
0x18000f84f  mov     r9, r8
0x18000f852  mov     [rbp+0C0h+var_68], rcx
0x18000f856  mov     [rbp+0C0h+var_110], rax
0x18000f85a  mov     [rbp+0C0h+var_70], r15
0x18000f85e  mov     [rbp+0C0h+var_B0], 0
0x18000f866  test    rdx, rdx
0x18000f869  jz      loc_18000FEC3
0x18000f86f  mov     rdx, [rdx+8]
0x18000f873  mov     ecx, r10d
0x18000f876  shr     ecx, 2
0x18000f879  not     cl
0x18000f87b  and     cl, 1
0x18000f87e  mov     r8d, [rdx+20h]
0x18000f882  mov     rdx, [rdx+28h]
0x18000f886  mov     dword ptr [rsp+1C0h+var_148+4], ecx
0x18000f88a  mov     rcx, rax; lpString1
0x18000f88d  call    ??$FindElementByName@VEntity@SemanticsUM@@@SemanticsUM@@YAPEBVEntity@0@PEB_WPEBV10@K@Z; SemanticsUM::FindElementByName<SemanticsUM::Entity>(wchar_t const *,SemanticsUM::Entity const *,ulong)
0x18000f892  mov     rcx, [rbx+20h]; this
0x18000f896  lea     r8, [rbp+0C0h+arg_28]; enum tagCONDITION_OPERATION *
0x18000f89d  mov     rdx, r13; struct _tagpropertykey *
0x18000f8a0  mov     [rsp+1C0h+Src], rax
0x18000f8a5  mov     rsi, rax
0x18000f8a8  call    ?ReplacePseudoProperty@QueryExpressionCustomization@StructuredQuery1@@QEBAJPEAU_tagpropertykey@@PEAW4tagCONDITION_OPERATION@@@Z; StructuredQuery1::QueryExpressionCustomization::ReplacePseudoProperty(_tagpropertykey *,tagCONDITION_OPERATION *)
0x18000f8ad  xor     r9d, r9d
0x18000f8b0  mov     edi, eax
0x18000f8b2  test    eax, eax
0x18000f8b4  js      loc_18000FD7D
0x18000f8ba  mov     edx, r12d
0x18000f8bd  mov     [rbp+0C0h+var_11C], r9d
0x18000f8c1  mov     ecx, r9d
0x18000f8c4  mov     [rbp+0C0h+var_138], r9d
0x18000f8c8  lea     eax, [r9+3]
0x18000f8cc  mov     [rbp+0C0h+var_120], ecx
0x18000f8cf  and     edx, eax
0x18000f8d1  mov     [rbp+0C0h+var_128], ecx
0x18000f8d4  mov     [rbp+0C0h+var_E8], edx
0x18000f8d7  mov     r8d, r9d
0x18000f8da  mov     [rbp+0C0h+var_118], r9
0x18000f8de  mov     r12d, r9d
0x18000f8e1  test    r15, r15
0x18000f8e4  jz      loc_18000FF7C
0x18000f8ea  mov     rax, [r15]
0x18000f8ed  lea     r8, [rbp+0C0h+var_128]
0x18000f8f1  lea     rdx, [rbp+0C0h+var_138]
0x18000f8f5  mov     [rsp+1C0h+var_1A0], r9; struct _GUID *
0x18000f8fa  mov     rcx, r15
0x18000f8fd  mov     rax, [rax+18h]
0x18000f901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f906  mov     r8d, [rbp+0C0h+var_138]
0x18000f90a  mov     edi, eax
0x18000f90c  mov     ecx, [rbp+0C0h+var_128]
0x18000f90f  lea     eax, [r12+3]
0x18000f914  mov     edx, [rbp+0C0h+var_E8]
0x18000f917  xor     r9d, r9d
0x18000f91a  mov     [rbp+0C0h+var_11C], r8d
0x18000f91e  mov     [rbp+0C0h+var_120], ecx
0x18000f921  test    edi, edi
0x18000f923  js      loc_18000FD7D
0x18000f929  mov     word ptr [rbp+0C0h+var_E0], ax
0x18000f92d  lea     rdi, [rbx+38h]
0x18000f931  xor     eax, eax
0x18000f933  xorps   xmm0, xmm0
0x18000f936  movups  xmmword ptr [rbp+0C0h+var_E0+2], xmm0
0x18000f93a  mov     qword ptr [rbp+0C0h+var_E0+10h], rax
0x18000f93e  mov     eax, [rbp+0C0h+var_E4]
0x18000f941  and     eax, 0FFFFFFBFh
0x18000f944  mov     dword ptr [rbp+0C0h+var_E0+8], eax
0x18000f947  cmp     edx, 2
0x18000f94a  mov     eax, r9d
0x18000f94d  setz    al
0x18000f950  lea     esi, [rcx+rax]
0x18000f953  mov     rax, [rdi]
0x18000f956  mov     rcx, rdi
0x18000f959  add     esi, r8d
0x18000f95c  mov     rax, [rax]
0x18000f95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f964  cmp     esi, eax
0x18000f966  jb      short loc_18000F978
0x18000f968  mov     rax, [rdi]
0x18000f96b  mov     rcx, rdi
0x18000f96e  mov     rax, [rax]
0x18000f971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f976  mov     esi, eax
0x18000f978  mov     ecx, [rbp+0C0h+var_138]; int
0x18000f97b  lea     rax, [rbp+0C0h+var_118]
0x18000f97f  lea     r9, [rbp+0C0h+var_E0]; struct tagPROPVARIANT *
0x18000f983  mov     [rsp+1C0h+var_198], rax; void **
0x18000f988  mov     r8, rbx; struct StructuredQuery1::Solution *
0x18000f98b  mov     edx, esi; int
0x18000f98d  call    ?CreateInstance@TokenInformation@StructuredQuery1@@SAJJJPEAVSolution@2@PEAUtagPROPVARIANT@@AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::TokenInformation::CreateInstance(long,long,StructuredQuery1::Solution *,tagPROPVARIANT *,_GUID const &,void * *)
0x18000f992  mov     r12, [rbp+0C0h+var_118]
0x18000f996  mov     edi, eax
0x18000f998  mov     eax, [rbp+0C0h+var_138]
0x18000f99b  xor     r9d, r9d
0x18000f99e  mov     rsi, [rsp+1C0h+Src]
0x18000f9a3  mov     [rbp+0C0h+var_11C], eax
0x18000f9a6  mov     eax, [rbp+0C0h+var_128]
0x18000f9a9  mov     [rbp+0C0h+var_120], eax
0x18000f9ac  test    edi, edi
0x18000f9ae  js      loc_18000FD7D
0x18000f9b4  lea     eax, [r9+1Fh]
0x18000f9b8  cmp     [r14], ax
0x18000f9bc  jnz     loc_18001014C
0x18000f9c2  mov     rax, [r14+8]
0x18000f9c6  mov     [rbp+0C0h+var_C0], rax
0x18000f9ca  mov     [rbp+0C0h+var_C8], r9
0x18000f9ce  mov     rcx, [rbx+20h]; this
0x18000f9d2  lea     r8, [rbp+0C0h+pv]; struct IConditionGenerator **
0x18000f9d6  mov     rdx, rsi; struct IEntity *
0x18000f9d9  mov     [rbp+0C0h+var_140], r9
0x18000f9dd  mov     r15, r9
0x18000f9e0  mov     [rbp+0C0h+var_130], r9
0x18000f9e4  mov     r14, r9
0x18000f9e7  mov     [rbp+0C0h+var_F8], r9
0x18000f9eb  mov     [rbp+0C0h+var_124], r9d
0x18000f9ef  mov     [rbp+0C0h+pv], r9
0x18000f9f3  call    ?GetCustomHandler@QueryExpressionCustomization@StructuredQuery1@@QEBAJPEBVIEntity@SemanticsUM@@PEAPEAUIConditionGenerator@@@Z; StructuredQuery1::QueryExpressionCustomization::GetCustomHandler(SemanticsUM::IEntity const *,IConditionGenerator * *)
0x18000f9f8  xor     r10d, r10d
0x18000f9fb  mov     edi, eax
0x18000f9fd  test    eax, eax
0x18000f9ff  js      loc_18000FDAE
0x18000fa05  mov     rsi, [rbp+0C0h+pv]
0x18000fa09  mov     r14d, [rbp+0C0h+arg_28]
0x18000fa10  test    rsi, rsi
0x18000fa13  jz      loc_18000FAF7
0x18000fa19  mov     eax, [r13+10h]
0x18000fa1d  movaps  xmm0, xmmword ptr [r13+0]
0x18000fa22  mov     dword ptr [rbp+0C0h+var_50], eax
0x18000fa25  movups  [rbp+0C0h+Buf1], xmm0
0x18000fa29  test    eax, eax
0x18000fa2b  jz      loc_1800100E0
0x18000fa31  lea     rdx, [rbp+0C0h+pv]; struct _tagpropertykey *
0x18000fa35  mov     [rbp+0C0h+pv], r10
0x18000fa39  lea     rcx, [rbp+0C0h+Buf1]; propkey
0x18000fa3d  call    ?GetConditionPropertyNameFromKey@StructuredQuery1@@YAJAEBU_tagpropertykey@@PEAPEA_W@Z; StructuredQuery1::GetConditionPropertyNameFromKey(_tagpropertykey const &,wchar_t * *)
0x18000fa42  mov     edi, eax
0x18000fa44  test    eax, eax
0x18000fa46  js      loc_18000FADD
0x18000fa4c  mov     rax, [rsi]
0x18000fa4f  lea     r8, [rbp+0C0h+var_140]
0x18000fa53  mov     [rsp+1C0h+var_160], r8
0x18000fa58  lea     rdx, [rbx+8]
0x18000fa5c  xor     ecx, ecx
0x18000fa5e  lea     r8, [rbp+0C0h+var_124]
0x18000fa62  cmp     [rbx+30h], cl
0x18000fa65  mov     r9d, r14d
0x18000fa68  mov     rax, [rax+28h]
0x18000fa6c  mov     [rsp+1C0h+var_168], r8
0x18000fa71  setnz   cl
0x18000fa74  mov     r8, [rbp+0C0h+pv]
0x18000fa78  mov     [rsp+1C0h+var_170], ecx
0x18000fa7c  mov     rcx, [rbp+0C0h+var_108]
0x18000fa80  mov     [rsp+1C0h+var_178], r12
0x18000fa85  mov     [rsp+1C0h+var_180], rcx
0x18000fa8a  mov     rcx, [rbp+0C0h+var_100]
0x18000fa8e  mov     [rsp+1C0h+var_188], rcx
0x18000fa93  mov     rcx, [rbp+0C0h+var_C8]
0x18000fa97  mov     [rsp+1C0h+var_190], rcx
0x18000fa9c  mov     rcx, [rbp+0C0h+var_C0]
0x18000faa0  mov     [rsp+1C0h+var_198], rcx
0x18000faa5  mov     rcx, [rbp+0C0h+var_110]
0x18000faa9  mov     [rsp+1C0h+var_1A0], rcx; struct _GUID *
0x18000faae  mov     rcx, rsi
0x18000fab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fab6  mov     edi, eax
0x18000fab8  test    eax, eax
0x18000faba  js      short loc_18000FAD3
0x18000fabc  mov     rcx, [rbp+0C0h+var_140]
0x18000fac0  test    rcx, rcx
0x18000fac3  jz      short loc_18000FAD3
0x18000fac5  test    dword ptr [rsp+1C0h+var_148], 100h
0x18000facd  jnz     loc_180087E76
0x18000fad3  mov     rcx, [rbp+0C0h+pv]; pv
0x18000fad7  call    cs:__imp_CoTaskMemFree
0x18000fadd  mov     rax, [rsi]
0x18000fae0  mov     rcx, rsi
0x18000fae3  mov     rax, [rax+10h]
0x18000fae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faec  xor     r10d, r10d
0x18000faef  test    edi, edi
0x18000faf1  js      loc_18000FDAA
0x18000faf7  mov     rsi, [rsp+1C0h+Src]
0x18000fafc  cmp     [rbp+0C0h+var_140], r10
0x18000fb00  jnz     loc_18000FCB4
0x18000fb06  test    rsi, rsi
0x18000fb09  jz      loc_18000FC01
0x18000fb0f  mov     rax, [rsi]
0x18000fb12  mov     rcx, rsi
0x18000fb15  mov     rax, [rax+48h]
0x18000fb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb1e  xor     r10d, r10d
0x18000fb21  test    eax, eax
0x18000fb23  jz      loc_18000FC01
0x18000fb29  cmp     [r13+10h], r10d
0x18000fb2d  jz      loc_180010127
0x18000fb33  mov     rdx, [rbx+28h]
0x18000fb37  mov     rcx, rsi
0x18000fb3a  mov     rdx, [rdx+20h]
0x18000fb3e  call    StructuredQuery1__InheritsFrom
0x18000fb43  xor     r10d, r10d
0x18000fb46  test    eax, eax
0x18000fb48  jle     loc_18000FC01
0x18000fb4e  xor     eax, eax
0x18000fb50  lea     ecx, [r10+1Fh]; this
0x18000fb54  xorps   xmm0, xmm0
0x18000fb57  mov     word ptr [rbp+0C0h+var_E0], cx
0x18000fb5b  movups  xmmword ptr [rbp+0C0h+var_E0+2], xmm0
0x18000fb5f  mov     qword ptr [rbp+0C0h+var_E0+10h], rax
0x18000fb63  mov     rax, [rbp+0C0h+var_C0]
0x18000fb67  mov     qword ptr [rbp+0C0h+var_E0+8], rax
0x18000fb6b  mov     rax, [rbp+0C0h+var_C8]
0x18000fb6f  test    rax, rax
0x18000fb72  jnz     loc_180087EE8
0x18000fb78  test    dword ptr [rsp+1C0h+var_148], 100h
0x18000fb80  jnz     loc_180010173
0x18000fb86  mov     eax, r10d
0x18000fb89  lea     rcx, [rbp+0C0h+var_140]
0x18000fb8d  mov     r9, rax
0x18000fb90  mov     [rsp+1C0h+var_158], rcx
0x18000fb95  mov     r8d, 0Ch
0x18000fb9b  lea     rcx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18000fba2  mov     rdx, r13
0x18000fba5  mov     [rsp+1C0h+var_160], rcx
0x18000fbaa  mov     ecx, dword ptr [rsp+1C0h+var_148+4]
0x18000fbae  mov     byte ptr [rsp+1C0h+var_168], cl
0x18000fbb2  mov     rcx, [rbp+0C0h+var_108]
0x18000fbb6  mov     byte ptr [rsp+1C0h+var_170], r10b
0x18000fbbb  mov     [rsp+1C0h+var_178], r12
0x18000fbc0  mov     [rsp+1C0h+var_180], rcx
0x18000fbc5  mov     rcx, [rbp+0C0h+var_100]
0x18000fbc9  mov     [rsp+1C0h+var_188], rcx
0x18000fbce  mov     rcx, [rbp+0C0h+var_B8]
0x18000fbd2  mov     dword ptr [rsp+1C0h+var_190], r10d
0x18000fbd7  mov     [rsp+1C0h+var_198], rcx
0x18000fbdc  lea     rcx, [rbp+0C0h+var_E0]
0x18000fbe0  mov     [rsp+1C0h+var_1A0], rcx; struct _GUID *
0x18000fbe5  mov     rcx, rbx
0x18000fbe8  call    ?MakePredicate@Solution@StructuredQuery1@@QEAAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_WAEBUtagPROPVARIANT@@2W4LANGUAGE_OVERRIDE_CHECK@2@PEAUIRichChunk@@55_N6AEBU_GUID@@PEAPEAX@Z; StructuredQuery1::Solution::MakePredicate(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,tagPROPVARIANT const &,wchar_t const *,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK,IRichChunk *,IRichChunk *,IRichChunk *,bool,bool,_GUID const &,void * *)
0x18000fbed  mov     edi, eax
0x18000fbef  xor     r10d, r10d
0x18000fbf2  mov     [rbp+0C0h+var_124], 1
0x18000fbf9  test    edi, edi
0x18000fbfb  js      loc_18000FDAA
0x18000fc01  cmp     [rbp+0C0h+var_140], r10
0x18000fc05  jnz     loc_18000FCB4
0x18000fc0b  test    rsi, rsi
0x18000fc0e  jnz     loc_18000FF59
0x18000fc14  mov     rax, [rbx+28h]
0x18000fc18  mov     dil, r10b
0x18000fc1b  mov     rax, [rax+50h]
0x18000fc1f  mov     [rsp+1C0h+Src], rax
0x18000fc24  mov     esi, [r13+10h]
0x18000fc28  movaps  xmm0, xmmword ptr [r13+0]
0x18000fc2d  xor     r13d, r13d
0x18000fc30  mov     dword ptr [rbp+0C0h+var_50], esi
0x18000fc33  movups  [rbp+0C0h+Buf1], xmm0
0x18000fc37  test    esi, esi
0x18000fc39  jz      loc_180010043
0x18000fc3f  mov     rax, [rbp+0C0h+var_C8]
0x18000fc43  test    rax, rax
0x18000fc46  jnz     loc_18000FEE3
0x18000fc4c  mov     [rsp+1C0h+Src], r13
0x18000fc51  test    r14d, r14d
0x18000fc54  jnz     loc_18000FDB6
0x18000fc5a  mov     rcx, [rbp+0C0h+var_70]
0x18000fc5e  lea     r9, [rsp+1C0h+Src]
0x18000fc63  xor     r8d, r8d
0x18000fc66  mov     [rsp+1C0h+var_1A0], r13
0x18000fc6b  xor     edx, edx
0x18000fc6d  test    rcx, rcx
  ... truncated ...
```
