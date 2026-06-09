# Art::PCPath2D::InitFrom(Art::CGuideNameList const &,Art::Path2D const &)

- ea: `0x18010b490`
- end: `0x18010c032`
- name: `?InitFrom@PCPath2D@Art@@QEAAXAEBVCGuideNameList@2@AEBVPath2D@2@@Z`
- size: `2978`
- prototype: `void(Art::PCPath2D *__hidden this, const struct Art::CGuideNameList *, const struct Art::Path2D *)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1801ee350`

## callees

- `0x1800902e8`
- `0x18010b490`
- `0x18010c034`
- `0x18010c0a4`
- `0x18010c0c4`
- `0x18010ced4`
- `0x18010d0e0`
- `0x1801e8e70`
- `0x1801e9fc8`
- `0x1801ed268`
- `0x1801ed590`
- `0x1801f1e38`
- `0x18052f200`
- `0x1808c1790`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x18010b696`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b804`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b827`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b84a`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b86d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b890`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b696`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b804`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b827`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b84a`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b86d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18010b890`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010b906`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010b9b3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010b9c3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bbbd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bbcd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bdba`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bdca`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bf99`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bfa9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010b906`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010b9b3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010b9c3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bbbd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bbcd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bdba`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bdca`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bf99`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18010bfa9`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010b559`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010b7d0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bac4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bcbf`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010b559`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010b7d0`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bac4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010bcbf`

## pseudocode

```c
void __fastcall Art::PCPath2D::InitFrom(
        Art::PCPath2D *this,
        const struct Art::CGuideNameList *a2,
        const struct Art::Path2D *a3)
{
  __int64 v6; // rbp
  _DWORD *v7; // r14
  unsigned int v8; // r8d
  _DWORD *v9; // rdx
  __int64 v10; // rbx
  __int64 *v11; // rcx
  __int64 v12; // rcx
  char v13; // al
  __int64 v14; // rax
  _QWORD *v15; // rbx
  double *v16; // rdi
  void ****v17; // rcx
  void ****v18; // rcx
  void ****v19; // rcx
  void ****v20; // rcx
  __int64 *v21; // rcx
  __int64 v22; // rcx
  char v23; // al
  __int64 *v24; // rcx
  __int64 v25; // rcx
  char v26; // al
  __int64 *v27; // rcx
  __int64 v28; // rcx
  char v29; // al
  __int64 *v30; // rcx
  __int64 v31; // rcx
  char v32; // al
  __int64 *v33; // rcx
  __int64 v34; // rcx
  char v35; // al
  __int64 v36; // rax
  double *v37; // rdi
  const struct Art::AdjPoint2D *v38; // rax
  const struct Art::Path2DArcTo *v39; // rax
  _QWORD *v40; // rbx
  void ****v41; // rcx
  void ****v42; // rcx
  void ****v43; // rcx
  void ****v44; // rcx
  _DWORD *v45; // rbx
  void ****v46; // rcx
  void ****v47; // rcx
  void ****v48; // rcx
  void ****v49; // rcx
  _QWORD *v50; // rdi
  void ****v51; // rcx
  void ****v52; // rcx
  void ****v53; // rcx
  void ****v54; // rcx
  const struct Art::Path2DQuadBezierTo *v55; // rax
  unsigned int v56; // [rsp+50h] [rbp+8h]

  *((_DWORD *)this + 2) = *((_DWORD *)a3 + 10);
  *((_BYTE *)this + 12) = *((_BYTE *)a3 + 44);
  *((_BYTE *)this + 13) = *((_BYTE *)a3 + 45);
  *((_QWORD *)this + 2) = *((_QWORD *)a3 + 3);
  *((_QWORD *)this + 3) = *((_QWORD *)a3 + 4);
  *((_BYTE *)this + 14) = *((_BYTE *)a3 + 56);
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v56 = 0;
  if ( *(_DWORD *)this )
  {
    while ( 1 )
    {
      if ( v7 )
      {
        v9 = (_DWORD *)v6;
        if ( *v7 < 2u )
        {
          v9 = v7 + 6;
          goto LABEL_9;
        }
        if ( *v7 == 2 || *v7 == 3 )
        {
          v9 = v7 + 10;
          goto LABEL_9;
        }
        if ( *v7 != 4 )
        {
          if ( *v7 == 5 )
            v9 = v7 + 2;
          goto LABEL_9;
        }
        goto LABEL_13;
      }
      v7 = (_DWORD *)((char *)this + 32);
      while ( v8 >= *((_DWORD *)a3 + 4) )
      {
        CrashWithRecovery(0x1E892498u, 0);
LABEL_13:
        v9 = v7 + 14;
LABEL_9:
        v7 = v9;
        if ( (char *)v9 - (char *)this - 32 >= *((unsigned int *)this + 1) )
          v7 = (_DWORD *)v6;
      }
      v10 = *((_QWORD *)a3 + 1) + 16LL * v8;
      v11 = *(__int64 **)(v10 + 8);
      if ( (unsigned __int64)v11 <= 1
        || (v12 = *v11, (struct Art::Path2DData::LineTo **)v12 != &Ofc::TypeInfoImpl<Art::Path2DData::LineTo>::c_typeInfo)
        && (*(const int **)(v12 + 8) == &Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v12 + 8LL, &qword_180E1AF50)) )
      {
        v13 = v6;
      }
      else
      {
        v13 = 1;
      }
      if ( v13 )
        break;
      v21 = *(__int64 **)(v10 + 8);
      if ( (unsigned __int64)v21 <= 1
        || (v22 = *v21, (struct Art::Path2DData::MoveTo **)v22 != &Ofc::TypeInfoImpl<Art::Path2DData::MoveTo>::c_typeInfo)
        && (*(const int **)(v22 + 8) == &Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v22 + 8LL, &qword_180E1AF80)) )
      {
        v23 = v6;
      }
      else
      {
        v23 = 1;
      }
      if ( v23 )
        goto LABEL_62;
      v24 = *(__int64 **)(v10 + 8);
      if ( (unsigned __int64)v24 > 1
        && (v25 = *v24, (struct Art::Path2DData::Close **)v25 != &Ofc::TypeInfoImpl<Art::Path2DData::Close>::c_typeInfo)
        && (*(const int **)(v25 + 8) == &Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v25 + 8LL, &qword_180E1AFB0)) )
      {
        v26 = v6;
      }
      else
      {
        v26 = 1;
      }
      if ( v26 )
      {
        if ( Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::Close>(v10) )
        {
          *v7 = 5;
          goto LABEL_31;
        }
LABEL_195:
        Ofc::CInvalidParamException::ThrowTag(0x66356D62u);
        __debugbreak();
      }
      v27 = *(__int64 **)(v10 + 8);
      if ( (unsigned __int64)v27 <= 1
        || (v28 = *v27, (struct Art::Path2DData::ArcTo **)v28 != &Ofc::TypeInfoImpl<Art::Path2DData::ArcTo>::c_typeInfo)
        && (*(const int **)(v28 + 8) == &Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v28 + 8LL, &qword_180E1AFE0)) )
      {
        v29 = v6;
      }
      else
      {
        v29 = 1;
      }
      if ( v29 )
      {
        v39 = (const struct Art::Path2DArcTo *)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::ArcTo>(v10);
        Art::PCPath2DArcTo::InitFrom((Art::PCPath2DArcTo *)v7, a2, v39);
        goto LABEL_31;
      }
      v30 = *(__int64 **)(v10 + 8);
      if ( (unsigned __int64)v30 <= 1
        || (v31 = *v30,
            (struct Art::Path2DData::QuadBezierTo **)v31 != &Ofc::TypeInfoImpl<Art::Path2DData::QuadBezierTo>::c_typeInfo)
        && (*(const int **)(v31 + 8) == &Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v31 + 8LL, &qword_180E1B010)) )
      {
        v32 = v6;
      }
      else
      {
        v32 = 1;
      }
      if ( v32 )
      {
        v55 = (const struct Art::Path2DQuadBezierTo *)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::QuadBezierTo>(v10);
        Art::PCPath2DQuadBezierTo::InitFrom((Art::PCPath2DQuadBezierTo *)v7, a2, v55);
        goto LABEL_31;
      }
      v33 = *(__int64 **)(v10 + 8);
      if ( (unsigned __int64)v33 <= 1
        || (v34 = *v33,
            (struct Art::Path2DData::CubicBezierTo **)v34 != &Ofc::TypeInfoImpl<Art::Path2DData::CubicBezierTo>::c_typeInfo)
        && (*(const int **)(v34 + 8) == &Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*(_QWORD *)v34 + 8LL, &qword_180E1AF18)) )
      {
        v35 = v6;
      }
      else
      {
        v35 = 1;
      }
      if ( v35 )
      {
        v36 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::CubicBezierTo>(v10);
        v6 = v36;
        *v7 = 4;
        v37 = (double *)(v7 + 2);
        if ( !*(_DWORD *)(v36 + 16) )
        {
          CrashWithRecovery(0x1E892498u, 0);
LABEL_62:
          v38 = (const struct Art::AdjPoint2D *)Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::MoveTo>(v10);
          *v7 = v6;
          Art::PCAdjPoint2D::InitFrom((Art::PCAdjPoint2D *)(v7 + 2), a2, v38);
          goto LABEL_31;
        }
        v40 = *(_QWORD **)(v36 + 8);
        v41 = (void ****)v40[1];
        if ( !v41 )
        {
          MsoShipAssertTagProc(895891042);
          goto LABEL_111;
        }
        if ( v41 != &off_180A9B1C0 )
          goto LABEL_110;
        while ( 2 )
        {
          v42 = (void ****)v40[1];
          if ( !v42 )
            goto LABEL_79;
          if ( v42 != &off_180A9B1C0
            && (v42[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
             || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                    *v42,
                                    &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
          {
LABEL_80:
            Ofc::CInvalidParamException::ThrowTag(0x65747234u);
            __debugbreak();
          }
          *v37 = (double)(int)*v40;
LABEL_103:
          v43 = (void ****)v40[3];
          if ( v43 )
          {
            if ( v43 == &off_180A9B1C0
              || v43[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
              && (unsigned __int8)Ofc::TypeInfo::operator==(
                                    *v43,
                                    &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
            {
              v44 = (void ****)v40[3];
              if ( !v44 )
                goto LABEL_79;
              if ( v44 != &off_180A9B1C0
                && (v44[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
                 || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                        *v44,
                                        &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
              {
                goto LABEL_80;
              }
              v37[1] = (double)(int)v40[2];
              goto LABEL_108;
            }
          }
          else
          {
            MsoShipAssertTagProc(895891042);
          }
          if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v40 + 2) )
            goto LABEL_80;
          Art::PCGeomGuideName::InitFrom(
            (Art::PCGeomGuideName *)(v37 + 1),
            a2,
            (const struct Art::GeomGuideName *)(v40 + 2));
          *((_DWORD *)v37 + 3) = -1;
          if ( *((_DWORD *)v37 + 2) == 0x7FFFFFFF )
            v37[1] = 0.0;
LABEL_108:
          v37 = (double *)(v7 + 6);
          if ( *(_DWORD *)(v6 + 16) > 1u )
          {
            v45 = *(_DWORD **)(v6 + 8);
            v46 = (void ****)*((_QWORD *)v45 + 5);
            if ( v46 )
            {
              if ( v46 != &off_180A9B1C0 )
                goto LABEL_142;
LABEL_132:
              v47 = (void ****)*((_QWORD *)v45 + 5);
              if ( !v47 )
                goto LABEL_79;
              if ( v47 == &off_180A9B1C0
                || v47[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
                && (unsigned __int8)Ofc::TypeInfo::operator==(
                                      *v47,
                                      &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
              {
                *v37 = (double)(int)*((_QWORD *)v45 + 4);
                goto LABEL_135;
              }
              goto LABEL_80;
            }
            MsoShipAssertTagProc(895891042);
            while ( 2 )
            {
              if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v45 + 8) )
                goto LABEL_80;
              Art::PCGeomGuideName::InitFrom(
                (Art::PCGeomGuideName *)(v7 + 6),
                a2,
                (const struct Art::GeomGuideName *)(v45 + 8));
              v7[7] = -1;
              if ( *(_DWORD *)v37 == 0x7FFFFFFF )
                *v37 = 0.0;
LABEL_135:
              v48 = (void ****)*((_QWORD *)v45 + 7);
              if ( v48 )
              {
                if ( v48 == &off_180A9B1C0
                  || v48[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
                  && (unsigned __int8)Ofc::TypeInfo::operator==(
                                        *v48,
                                        &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
                {
                  v49 = (void ****)*((_QWORD *)v45 + 7);
                  if ( !v49 )
                    goto LABEL_79;
                  if ( v49 != &off_180A9B1C0
                    && (v49[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
                     || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                            *v49,
                                            &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
                  {
                    goto LABEL_80;
                  }
                  *((double *)v7 + 4) = (double)(int)*((_QWORD *)v45 + 6);
                  goto LABEL_140;
                }
              }
              else
              {
                MsoShipAssertTagProc(895891042);
              }
              if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v45 + 12) )
                goto LABEL_80;
              Art::PCGeomGuideName::InitFrom(
                (Art::PCGeomGuideName *)(v7 + 8),
                a2,
                (const struct Art::GeomGuideName *)(v45 + 12));
              v7[9] = -1;
              if ( v7[8] == 0x7FFFFFFF )
                *((_QWORD *)v7 + 4) = 0;
LABEL_140:
              v45 = v7 + 10;
              if ( *(_DWORD *)(v6 + 16) > 2u )
              {
                v50 = *(_QWORD **)(v6 + 8);
                v51 = (void ****)v50[9];
                v6 = 0;
                if ( v51 )
                {
                  if ( v51 == &off_180A9B1C0
                    || v51[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
                    && (unsigned __int8)Ofc::TypeInfo::operator==(
                                          *v51,
                                          &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
                  {
                    v52 = (void ****)v50[9];
                    if ( !v52 )
                      goto LABEL_79;
                    if ( v52 != &off_180A9B1C0
                      && (v52[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
                       || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                              *v52,
                                              &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
                    {
                      goto LABEL_80;
                    }
                    *(double *)v45 = (double)(int)v50[8];
LABEL_167:
                    v53 = (void ****)v50[11];
                    if ( v53 )
                    {
                      if ( v53 == &off_180A9B1C0
                        || v53[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
                        && (unsigned __int8)Ofc::TypeInfo::operator==(
                                              *v53,
                                              &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
                      {
                        v54 = (void ****)v50[11];
                        if ( v54 )
                        {
                          if ( v54 != &off_180A9B1C0
                            && (v54[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
                             || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                                    *v54,
                                                    &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
                          {
                            goto LABEL_80;
                          }
                          *((double *)v7 + 6) = (double)(int)v50[10];
                          goto LABEL_31;
                        }
LABEL_79:
                        MsoShipAssertTagProc(895891042);
                        goto LABEL_80;
                      }
                    }
                    else
                    {
                      MsoShipAssertTagProc(895891042);
                    }
                    if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v50 + 10) )
                      goto LABEL_80;
                    Art::PCGeomGuideName::InitFrom(
                      (Art::PCGeomGuideName *)(v7 + 12),
                      a2,
                      (const struct Art::GeomGuideName *)(v50 + 10));
                    v7[13] = -1;
                    if ( v7[12] == 0x7FFFFFFF )
                      *((_QWORD *)v7 + 6) = 0;
                    goto LABEL_31;
                  }
                }
                else
                {
                  MsoShipAssertTagProc(895891042);
                }
                if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v50 + 8) )
                  goto LABEL_80;
                Art::PCGeomGuideName::InitFrom(
                  (Art::PCGeomGuideName *)(v7 + 10),
                  a2,
                  (const struct Art::GeomGuideName *)(v50 + 8));
                v7[11] = -1;
                if ( *v45 == 0x7FFFFFFF )
                  *(_QWORD *)v45 = 0;
                goto LABEL_167;
              }
              CrashWithRecovery(0x1E892498u, 0);
LABEL_142:
              if ( v46[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
                && (unsigned __int8)Ofc::TypeInfo::operator==(
                                      *v46,
                                      &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
              {
                goto LABEL_132;
              }
              continue;
            }
          }
          CrashWithRecovery(0x1E892498u, 0);
LABEL_110:
          if ( v41[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
            && (unsigned __int8)Ofc::TypeInfo::operator==(
                                  *v41,
                                  &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
          {
            continue;
          }
          break;
        }
LABEL_111:
        if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v40) )
          goto LABEL_80;
        Art::PCGeomGuideName::InitFrom((Art::PCGeomGuideName *)v37, a2, (const struct Art::GeomGuideName *)v40);
        *((_DWORD *)v37 + 1) = -1;
        if ( *(_DWORD *)v37 == 0x7FFFFFFF )
          *v37 = 0.0;
        goto LABEL_103;
      }
LABEL_31:
      v8 = v56 + 1;
      v56 = v8;
      if ( v8 >= *(_DWORD *)this )
        return;
    }
    v14 = Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::LineTo>(v10);
    v15 = (_QWORD *)v14;
    if ( !v14 )
      goto LABEL_195;
    *v7 = 1;
    v16 = (double *)(v7 + 2);
    v17 = *(void *****)(v14 + 8);
    if ( v17 )
    {
      if ( v17 == &off_180A9B1C0
        || v17[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
        && (unsigned __int8)Ofc::TypeInfo::operator==(
                              *v17,
                              &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
      {
        v18 = (void ****)v15[1];
        if ( !v18 )
          goto LABEL_79;
        if ( v18 != &off_180A9B1C0
          && (v18[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
           || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                  *v18,
                                  &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
        {
          goto LABEL_80;
        }
        *v16 = (double)(int)*v15;
LABEL_26:
        v19 = (void ****)v15[3];
        if ( v19 )
        {
          if ( v19 == &off_180A9B1C0
            || v19[6] != (void ***)&Ofc::TypeInfo::s_moduleTag
            && (unsigned __int8)Ofc::TypeInfo::operator==(
                                  *v19,
                                  &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo) )
          {
            v20 = (void ****)v15[3];
            if ( v20 )
            {
              if ( v20 != &off_180A9B1C0
                && (v20[6] == (void ***)&Ofc::TypeInfo::s_moduleTag
                 || !(unsigned __int8)Ofc::TypeInfo::operator==(
                                        *v20,
                                        &Ofc::TypeInfoImpl<Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>>::c_typeInfo)) )
              {
                goto LABEL_80;
              }
              *((double *)v7 + 2) = (double)(int)v15[2];
              goto LABEL_31;
            }
            goto LABEL_79;
          }
        }
        else
        {
          MsoShipAssertTagProc(895891042);
        }
        if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v15 + 2) )
          goto LABEL_80;
        Art::PCGeomGuideName::InitFrom(
          (Art::PCGeomGuideName *)(v7 + 4),
          a2,
          (const struct Art::GeomGuideName *)(v15 + 2));
        v7[5] = -1;
        if ( v7[4] == 0x7FFFFFFF )
          *((_QWORD *)v7 + 2) = v6;
        goto LABEL_31;
      }
    }
    else
    {
      MsoShipAssertTagProc(895891042);
    }
    if ( !(unsigned __int8)Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(v15) )
      goto LABEL_80;
    Art::PCGeomGuideName::InitFrom((Art::PCGeomGuideName *)(v7 + 2), a2, (const struct Art::GeomGuideName *)v15);
    v7[3] = -1;
    if ( *(_DWORD *)v16 == 0x7FFFFFFF )
      *(_QWORD *)v16 = v6;
    goto LABEL_26;
  }
}

```

## disassembly

```asm
0x18010b490  mov     [rsp+arg_8], rbx
0x18010b495  mov     [rsp+arg_10], rbp
0x18010b49a  mov     [rsp+arg_18], rsi
0x18010b49f  push    rdi
0x18010b4a0  push    r12
0x18010b4a2  push    r13
0x18010b4a4  push    r14
0x18010b4a6  push    r15
0x18010b4a8  sub     rsp, 20h
0x18010b4ac  mov     r13, r8
0x18010b4af  mov     r12, rdx
0x18010b4b2  mov     r15, rcx
0x18010b4b5  mov     eax, [r8+28h]
0x18010b4b9  mov     [rcx+8], eax
0x18010b4bc  mov     al, [r8+2Ch]
0x18010b4c0  mov     [rcx+0Ch], al
0x18010b4c3  mov     al, [r8+2Dh]
0x18010b4c7  mov     [rcx+0Dh], al
0x18010b4ca  mov     rax, [r8+18h]
0x18010b4ce  mov     [rcx+10h], rax
0x18010b4d2  mov     rax, [r8+20h]
0x18010b4d6  mov     [rcx+18h], rax
0x18010b4da  mov     al, [r8+38h]
0x18010b4de  mov     [rcx+0Eh], al
0x18010b4e1  xor     ebp, ebp
0x18010b4e3  mov     r14d, ebp
0x18010b4e6  mov     r8d, ebp
0x18010b4e9  mov     [rsp+48h+arg_0], ebp
0x18010b4ed  cmp     [rcx], ebp
0x18010b4ef  jbe     loc_18010B66B
0x18010b4f5  lea     rsi, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18010b4fc  test    r14, r14
0x18010b4ff  jz      short loc_18010B566
0x18010b501  mov     rdx, rbp
0x18010b504  mov     ecx, [r14]
0x18010b507  test    ecx, ecx
0x18010b509  jz      loc_18010C003
0x18010b50f  sub     ecx, 1
0x18010b512  jz      loc_18010C003
0x18010b518  sub     ecx, 1
0x18010b51b  jz      loc_18010BFFA
0x18010b521  sub     ecx, 1
0x18010b524  jz      loc_18010BFFA
0x18010b52a  sub     ecx, 1
0x18010b52d  jz      short loc_18010B560
0x18010b52f  cmp     ecx, 1
0x18010b532  jz      short loc_18010B56C
0x18010b534  mov     rcx, rdx
0x18010b537  sub     rcx, r15
0x18010b53a  sub     rcx, 20h ; ' '
0x18010b53e  mov     eax, [r15+4]
0x18010b542  mov     r14, rdx
0x18010b545  cmp     rcx, rax
0x18010b548  cmovge  r14, rbp
0x18010b54c  cmp     r8d, [r13+10h]
0x18010b550  jb      short loc_18010B572
0x18010b552  xor     edx, edx
0x18010b554  mov     ecx, 1E892498h
0x18010b559  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18010b55f  nop
0x18010b560  lea     rdx, [r14+38h]
0x18010b564  jmp     short loc_18010B534
0x18010b566  lea     r14, [r15+20h]
0x18010b56a  jmp     short loc_18010B54C
0x18010b56c  lea     rdx, [r14+8]
0x18010b570  jmp     short loc_18010B534
0x18010b572  mov     ebx, r8d
0x18010b575  shl     rbx, 4
0x18010b579  add     rbx, [r13+8]
0x18010b57d  mov     rcx, [rbx+8]
0x18010b581  cmp     rcx, 1
0x18010b585  jbe     short loc_18010B5A4
0x18010b587  mov     rcx, [rcx]
0x18010b58a  lea     rax, ?c_typeInfo@?$TypeInfoImpl@ULineTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::LineTo>::c_typeInfo
0x18010b591  cmp     rcx, rax
0x18010b594  jz      loc_18010B6A4
0x18010b59a  cmp     [rcx+8], rsi
0x18010b59e  jnz     loc_18010B688
0x18010b5a4  mov     al, bpl
0x18010b5a7  test    al, al
0x18010b5a9  jz      loc_18010B6AB
0x18010b5af  mov     rcx, rbx
0x18010b5b2  call    ??$GetPtr@ULineTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAPEAVPath2DLineTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::LineTo>(void)
0x18010b5b7  mov     rbx, rax
0x18010b5ba  test    rax, rax
0x18010b5bd  jz      loc_18010C027
0x18010b5c3  mov     dword ptr [r14], 1
0x18010b5ca  lea     rdi, [r14+8]
0x18010b5ce  mov     rcx, [rax+8]
0x18010b5d2  test    rcx, rcx
0x18010b5d5  jz      loc_18010B9AE
0x18010b5db  lea     rax, off_180A9B1C0
0x18010b5e2  cmp     rcx, rax
0x18010b5e5  jnz     loc_18010B8C2
0x18010b5eb  mov     rcx, [rbx+8]
0x18010b5ef  test    rcx, rcx
0x18010b5f2  jz      loc_18010B901
0x18010b5f8  cmp     rcx, rax
0x18010b5fb  jnz     loc_18010B969
0x18010b601  xorps   xmm0, xmm0
0x18010b604  cvtsi2sd xmm0, qword ptr [rbx]
0x18010b609  movsd   qword ptr [rdi], xmm0
0x18010b60d  mov     rcx, [rbx+18h]
0x18010b611  test    rcx, rcx
0x18010b614  jz      loc_18010B9BE
0x18010b61a  lea     rax, off_180A9B1C0
0x18010b621  cmp     rcx, rax
0x18010b624  jnz     loc_18010B917
0x18010b62a  mov     rcx, [rbx+18h]
0x18010b62e  test    rcx, rcx
0x18010b631  jz      loc_18010B901
0x18010b637  lea     rsi, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18010b63e  cmp     rcx, rax
0x18010b641  jnz     loc_18010B988
0x18010b647  xorps   xmm0, xmm0
0x18010b64a  cvtsi2sd xmm0, qword ptr [rbx+10h]
0x18010b650  movsd   qword ptr [rdi+8], xmm0
0x18010b655  mov     r8d, [rsp+48h+arg_0]
0x18010b65a  inc     r8d
0x18010b65d  mov     [rsp+48h+arg_0], r8d
0x18010b662  cmp     r8d, [r15]
0x18010b665  jb      loc_18010B4FC
0x18010b66b  mov     rbx, [rsp+48h+arg_8]
0x18010b670  mov     rbp, [rsp+48h+arg_10]
0x18010b675  mov     rsi, [rsp+48h+arg_18]
0x18010b67a  add     rsp, 20h
0x18010b67e  pop     r15
0x18010b680  pop     r14
0x18010b682  pop     r13
0x18010b684  pop     r12
0x18010b686  pop     rdi
0x18010b687  retn
0x18010b688  mov     rcx, [rcx]
0x18010b68b  add     rcx, 8
0x18010b68f  lea     rdx, qword_180E1AF50
0x18010b696  call    cs:__imp___std_type_info_compare
0x18010b69c  test    eax, eax
0x18010b69e  jnz     loc_18010B5A4
0x18010b6a4  mov     al, 1
0x18010b6a6  jmp     loc_18010B5A7
0x18010b6ab  mov     rcx, [rbx+8]
0x18010b6af  cmp     rcx, 1
0x18010b6b3  jbe     short loc_18010B6D2
0x18010b6b5  mov     rcx, [rcx]
0x18010b6b8  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UMoveTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::MoveTo>::c_typeInfo
0x18010b6bf  cmp     rcx, rax
0x18010b6c2  jz      loc_18010B858
0x18010b6c8  cmp     [rcx+8], rsi
0x18010b6cc  jnz     loc_18010B83C
0x18010b6d2  mov     al, bpl
0x18010b6d5  test    al, al
0x18010b6d7  jnz     loc_18010B7D7
0x18010b6dd  mov     rcx, [rbx+8]
0x18010b6e1  cmp     rcx, 1
0x18010b6e5  jbe     loc_18010B87B
0x18010b6eb  mov     rcx, [rcx]
0x18010b6ee  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UClose@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::Close>::c_typeInfo
0x18010b6f5  cmp     rcx, rax
0x18010b6f8  jz      loc_18010B87B
0x18010b6fe  cmp     [rcx+8], rsi
0x18010b702  jnz     loc_18010B85F
0x18010b708  mov     al, bpl
0x18010b70b  test    al, al
0x18010b70d  jnz     loc_18010B8A5
0x18010b713  mov     rcx, [rbx+8]
0x18010b717  cmp     rcx, 1
0x18010b71b  jbe     short loc_18010B73A
0x18010b71d  mov     rcx, [rcx]
0x18010b720  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UArcTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::ArcTo>::c_typeInfo
0x18010b727  cmp     rcx, rax
0x18010b72a  jz      loc_18010B835
0x18010b730  cmp     [rcx+8], rsi
0x18010b734  jnz     loc_18010B819
0x18010b73a  mov     al, bpl
0x18010b73d  test    al, al
0x18010b73f  jnz     loc_18010B9CE
0x18010b745  mov     rcx, [rbx+8]
0x18010b749  cmp     rcx, 1
0x18010b74d  jbe     short loc_18010B76C
0x18010b74f  mov     rcx, [rcx]
0x18010b752  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UQuadBezierTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::QuadBezierTo>::c_typeInfo
0x18010b759  cmp     rcx, rax
0x18010b75c  jz      loc_18010B812
0x18010b762  cmp     [rcx+8], rsi
0x18010b766  jnz     loc_18010B7F6
0x18010b76c  mov     al, bpl
0x18010b76f  test    al, al
0x18010b771  jnz     loc_18010C00C
0x18010b777  mov     rcx, [rbx+8]
0x18010b77b  cmp     rcx, 1
0x18010b77f  jbe     short loc_18010B79E
0x18010b781  mov     rcx, [rcx]
0x18010b784  lea     rax, ?c_typeInfo@?$TypeInfoImpl@UCubicBezierTo@Path2DData@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::Path2DData::CubicBezierTo>::c_typeInfo
0x18010b78b  cmp     rcx, rax
0x18010b78e  jz      loc_18010B89E
0x18010b794  cmp     [rcx+8], rsi
0x18010b798  jnz     loc_18010B882
0x18010b79e  mov     al, bpl
0x18010b7a1  test    al, al
0x18010b7a3  jz      loc_18010B655
0x18010b7a9  mov     rcx, rbx
0x18010b7ac  call    ??$Get@UCubicBezierTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DCubicBezierTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::CubicBezierTo>(void)
0x18010b7b1  mov     rbp, rax
0x18010b7b4  mov     dword ptr [r14], 4
0x18010b7bb  lea     rdi, [r14+8]
0x18010b7bf  cmp     dword ptr [rax+10h], 0
0x18010b7c3  ja      loc_18010BA2F
0x18010b7c9  xor     edx, edx
0x18010b7cb  mov     ecx, 1E892498h
0x18010b7d0  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18010b7d6  nop
0x18010b7d7  mov     rcx, rbx
0x18010b7da  call    ??$Get@UMoveTo@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAAEAVPath2DMoveTo@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::Get<Art::Path2DData::MoveTo>(void)
0x18010b7df  mov     [r14], ebp
0x18010b7e2  lea     rcx, [r14+8]; this
0x18010b7e6  mov     r8, rax; struct Art::AdjPoint2D *
0x18010b7e9  mov     rdx, r12; struct Art::CGuideNameList *
0x18010b7ec  call    ?InitFrom@PCAdjPoint2D@Art@@QEAAXAEBVCGuideNameList@2@AEBVAdjPoint2D@2@@Z; Art::PCAdjPoint2D::InitFrom(Art::CGuideNameList const &,Art::AdjPoint2D const &)
0x18010b7f1  jmp     loc_18010B655
0x18010b7f6  mov     rcx, [rcx]
0x18010b7f9  add     rcx, 8
0x18010b7fd  lea     rdx, qword_180E1B010
0x18010b804  call    cs:__imp___std_type_info_compare
0x18010b80a  test    eax, eax
0x18010b80c  jnz     loc_18010B76C
0x18010b812  mov     al, 1
0x18010b814  jmp     loc_18010B76F
0x18010b819  mov     rcx, [rcx]
0x18010b81c  add     rcx, 8
0x18010b820  lea     rdx, qword_180E1AFE0
0x18010b827  call    cs:__imp___std_type_info_compare
0x18010b82d  test    eax, eax
0x18010b82f  jnz     loc_18010B73A
0x18010b835  mov     al, 1
0x18010b837  jmp     loc_18010B73D
0x18010b83c  mov     rcx, [rcx]
0x18010b83f  add     rcx, 8
0x18010b843  lea     rdx, qword_180E1AF80
0x18010b84a  call    cs:__imp___std_type_info_compare
0x18010b850  test    eax, eax
0x18010b852  jnz     loc_18010B6D2
0x18010b858  mov     al, 1
0x18010b85a  jmp     loc_18010B6D5
0x18010b85f  mov     rcx, [rcx]
0x18010b862  add     rcx, 8
0x18010b866  lea     rdx, qword_180E1AFB0
0x18010b86d  call    cs:__imp___std_type_info_compare
0x18010b873  test    eax, eax
0x18010b875  jnz     loc_18010B708
0x18010b87b  mov     al, 1
0x18010b87d  jmp     loc_18010B70B
0x18010b882  mov     rcx, [rcx]
0x18010b885  add     rcx, 8
0x18010b889  lea     rdx, qword_180E1AF18
0x18010b890  call    cs:__imp___std_type_info_compare
0x18010b896  test    eax, eax
0x18010b898  jnz     loc_18010B79E
0x18010b89e  mov     al, 1
0x18010b8a0  jmp     loc_18010B7A1
0x18010b8a5  mov     rcx, rbx
0x18010b8a8  call    ??$GetPtr@UClose@Path2DData@Art@@@?$TChoice@VSegmentChoiceIDsImpl@Path2DData@Art@@@Ofc@@QEAAPEAVPath2DClose@Art@@XZ; Ofc::TChoice<Art::Path2DData::SegmentChoiceIDsImpl>::GetPtr<Art::Path2DData::Close>(void)
0x18010b8ad  test    rax, rax
0x18010b8b0  jz      loc_18010C027
0x18010b8b6  mov     dword ptr [r14], 5
0x18010b8bd  jmp     loc_18010B655
0x18010b8c2  cmp     [rcx+30h], rsi
0x18010b8c6  jnz     loc_18010B9E9
0x18010b8cc  mov     rcx, rbx
0x18010b8cf  call    ??$Is@VGeomGuideName@Art@@@?$TVariant@VAdjCoordDataIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(void)
0x18010b8d4  test    al, al
0x18010b8d6  jz      short loc_18010B90C
0x18010b8d8  mov     r8, rbx; struct Art::GeomGuideName *
0x18010b8db  mov     rdx, r12; struct Art::CGuideNameList *
0x18010b8de  mov     rcx, rdi; this
0x18010b8e1  call    ?InitFrom@PCGeomGuideName@Art@@QEAAXAEBVCGuideNameList@2@AEBVGeomGuideName@2@@Z; Art::PCGeomGuideName::InitFrom(Art::CGuideNameList const &,Art::GeomGuideName const &)
0x18010b8e6  mov     dword ptr [rdi+4], 0FFFFFFFFh
0x18010b8ed  cmp     dword ptr [rdi], 7FFFFFFFh
0x18010b8f3  jnz     loc_18010B60D
0x18010b8f9  mov     [rdi], rbp
0x18010b8fc  jmp     loc_18010B60D
0x18010b901  mov     ecx, 35663662h
0x18010b906  call    cs:__imp_MsoShipAssertTagProc
0x18010b90c  mov     ecx, 65747234h; unsigned int
0x18010b911  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x18010b916  int     3; Trap to Debugger
0x18010b917  lea     rax, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18010b91e  cmp     [rcx+30h], rax
0x18010b922  jnz     loc_18010BA0C
0x18010b928  lea     rcx, [rbx+10h]
0x18010b92c  call    ??$Is@VGeomGuideName@Art@@@?$TVariant@VAdjCoordDataIDsImpl@Art@@@Ofc@@QEBA_NXZ; Ofc::TVariant<Art::AdjCoordDataIDsImpl>::Is<Art::GeomGuideName>(void)
0x18010b931  test    al, al
0x18010b933  jz      short loc_18010B90C
0x18010b935  lea     r8, [rbx+10h]; struct Art::GeomGuideName *
0x18010b939  mov     rdx, r12; struct Art::CGuideNameList *
0x18010b93c  lea     rcx, [rdi+8]; this
0x18010b940  call    ?InitFrom@PCGeomGuideName@Art@@QEAAXAEBVCGuideNameList@2@AEBVGeomGuideName@2@@Z; Art::PCGeomGuideName::InitFrom(Art::CGuideNameList const &,Art::GeomGuideName const &)
0x18010b945  mov     dword ptr [rdi+0Ch], 0FFFFFFFFh
0x18010b94c  lea     rsi, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18010b953  cmp     dword ptr [rdi+8], 7FFFFFFFh
0x18010b95a  jnz     loc_18010B655
  ... truncated ...
```
