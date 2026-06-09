# Dr::DrawingSelection::GetViewElemSelectionInfo(void)

- ea: `0x1800e3730`
- end: `0x1800e416c`
- name: `?GetViewElemSelectionInfo@DrawingSelection@Dr@@MEAAPEAVViewElemSelectionInfo@Art@@XZ`
- size: `2620`
- prototype: `struct Art::ViewElemSelectionInfo *__fastcall(Dr::DrawingSelection *__hidden this)`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x18000e560`
- `0x18000fa20`
- `0x18002a690`
- `0x1800e3730`
- `0x1800e4170`
- `0x1800e8b40`
- `0x1800e8e20`
- `0x180112d6c`
- `0x180278e40`
- `0x180278e50`
- `0x180279050`
- `0x18028a5a0`
- `0x18028a9c0`
- `0x1802e56c0`
- `0x180566874`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806bcb10`
- `0x1806d19bc`
- `0x1806d19e4`
- `0x1806d235c`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3b05`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3b71`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3bdd`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3c4e`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3cbe`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3b05`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3b71`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3bdd`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3c4e`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800e3cbe`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800e3fe6`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800e3fe6`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e3871`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e38e2`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e3966`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e3994`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e3e8d`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e3871`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e38e2`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e3966`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e3994`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800e3e8d`

## pseudocode

```c
struct Art::ViewElemSelectionInfo *__fastcall Dr::DrawingSelection::GetViewElemSelectionInfo(
        struct Ofc::CProxyPtrImpl **this)
{
  char *v1; // rsi
  struct Ofc::CProxyPtrImpl *v2; // r12
  Dr::DrawingSelection *v3; // rdi
  int v4; // r15d
  struct Ofc::CProxyPtrImpl *v5; // rax
  struct Ofc::CProxyPtrImpl *v6; // rcx
  void *Checked; // rax
  struct Ofc::CProxyPtrImpl **v8; // rax
  struct Dr::DrawingSelectionInfo *v9; // r14
  unsigned int v10; // r8d
  unsigned int v11; // edi
  unsigned int v12; // r13d
  unsigned int v13; // ebx
  unsigned __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  char *v17; // rsi
  Mso::Memory *v18; // rdi
  __int64 v19; // rbx
  unsigned int v20; // edx
  void *v21; // rdx
  struct Ofc::CProxyPtrImpl **mm; // rbx
  unsigned __int64 v24; // rax
  Mso::Memory *v25; // rbx
  void *v26; // rdx
  Mso::Memory *v27; // rbx
  void *v28; // rdx
  struct Ofc::CProxyPtrImpl **v29; // rax
  __int64 v30; // rbx
  struct Ofc::CProxyPtrImpl **v31; // rax
  struct Ofc::CProxyPtrImpl *v32; // rax
  void *v33; // rax
  __int64 (__fastcall ***v34)(_QWORD); // rcx
  _QWORD *j; // rbx
  __int64 v36; // rcx
  struct Ofc::CProxyPtrImpl *v37; // rcx
  __int64 (__fastcall ***v38)(_QWORD); // rcx
  _QWORD *k; // rbx
  __int64 v40; // rcx
  struct Ofc::CProxyPtrImpl *v41; // rcx
  __int64 (__fastcall ***v42)(_QWORD); // rcx
  _QWORD *m; // rbx
  __int64 v44; // rcx
  struct Ofc::CProxyPtrImpl *v45; // rcx
  __int64 (__fastcall ***v46)(_QWORD); // rcx
  _QWORD *n; // rbx
  __int64 v48; // rcx
  struct Ofc::CProxyPtrImpl *v49; // rcx
  __int64 (__fastcall ***v50)(_QWORD); // rcx
  _QWORD *ii; // rbx
  __int64 v52; // rcx
  struct Ofc::CProxyPtrImpl *v53; // rcx
  char v54; // bl
  Ofc::CProxyPtrImpl *v55; // rcx
  char v56; // bl
  char v57; // bl
  struct Ofc::CProxyPtrImpl *v58; // rbx
  _QWORD *v59; // rax
  struct Ofc::CProxyPtrImpl **v60; // rax
  struct Ofc::CProxyPtrImpl *v61; // rax
  struct Ofc::CProxyPtrImpl *jj; // r8
  void *v63; // rdx
  Mso::Memory *v64; // rsi
  struct Ofc::CProxyPtrImpl **v65; // rbx
  struct Ofc::CProxyPtrImpl **i; // rbx
  struct Ofc::CProxyPtrImpl **v67; // rax
  struct Ofc::CProxyPtrImpl **v68; // rax
  struct Ofc::CProxyPtrImpl **v69; // rax
  struct Ofc::CProxyPtrImpl *v70; // rax
  struct Ofc::CProxyPtrImpl *kk; // r8
  void *v72; // rax
  struct Ofc::CProxyPtrImpl **v73; // rax
  void *v74; // rax
  void *v75; // rax
  __int64 v76; // r10
  __int64 v77; // r8
  __int64 v78; // r9
  char v79; // bl
  struct Ofc::CProxyPtrImpl **v80; // rax
  struct Ofc::CProxyPtrImpl *v81; // [rsp+20h] [rbp-A9h] BYREF
  unsigned __int64 v82; // [rsp+28h] [rbp-A1h] BYREF
  unsigned int v83; // [rsp+30h] [rbp-99h]
  unsigned int v84; // [rsp+34h] [rbp-95h]
  void *Src; // [rsp+38h] [rbp-91h] BYREF
  unsigned int v86; // [rsp+40h] [rbp-89h]
  unsigned int v87; // [rsp+44h] [rbp-85h]
  void *v88; // [rsp+48h] [rbp-81h] BYREF
  unsigned int v89; // [rsp+50h] [rbp-79h]
  unsigned int v90; // [rsp+54h] [rbp-75h]
  Ofc::CProxyPtrImpl *v91; // [rsp+58h] [rbp-71h] BYREF
  struct Ofc::CProxyPtrImpl *v92; // [rsp+60h] [rbp-69h] BYREF
  struct Ofc::CProxyPtrImpl *v93; // [rsp+68h] [rbp-61h] BYREF
  struct Ofc::CProxyPtrImpl *v94; // [rsp+70h] [rbp-59h] BYREF
  Ofc::CProxyPtrImpl *v95; // [rsp+78h] [rbp-51h] BYREF
  Ofc::CProxyPtrImpl *v96; // [rsp+80h] [rbp-49h] BYREF
  struct Ofc::CProxyPtrImpl *v97; // [rsp+88h] [rbp-41h] BYREF
  Ofc::CProxyPtrImpl *v98; // [rsp+90h] [rbp-39h] BYREF
  Ofc::CProxyPtrImpl *v99; // [rsp+98h] [rbp-31h] BYREF
  struct Ofc::CProxyPtrImpl *v100; // [rsp+A0h] [rbp-29h] BYREF
  struct Ofc::CProxyPtrImpl *v101; // [rsp+A8h] [rbp-21h] BYREF
  struct Ofc::CProxyPtrImpl *v102; // [rsp+B0h] [rbp-19h] BYREF
  struct Ofc::CProxyPtrImpl *v103; // [rsp+B8h] [rbp-11h] BYREF
  int v104; // [rsp+C0h] [rbp-9h] BYREF
  struct Ofc::CProxyPtrImpl *v105; // [rsp+C8h] [rbp-1h] BYREF
  struct Ofc::CProxyPtrImpl *v106; // [rsp+D0h] [rbp+7h] BYREF
  char v107; // [rsp+D8h] [rbp+Fh]
  Ofc::CProxyPtrImpl *v109; // [rsp+138h] [rbp+6Fh] BYREF
  struct Ofc::CProxyPtrImpl *v110; // [rsp+140h] [rbp+77h] BYREF
  struct Ofc::CProxyPtrImpl *v111; // [rsp+148h] [rbp+7Fh] BYREF

  v3 = (Dr::DrawingSelection *)this;
  v4 = 0;
  LODWORD(v109) = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0x80000000;
  v5 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v110 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v6 = this[117];
  if ( *((_QWORD *)v6 + 2) )
  {
    v109 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v6);
    Checked = Ofc::CProxyPtrImpl::GetChecked(v109);
    v8 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 120LL))(Checked);
    Ofc::CProxyPtrImpl::WeakAssign(&v110, *v8);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v109);
    v5 = v110;
  }
  if ( *((_QWORD *)v5 + 2) )
  {
    Src = 0;
    v86 = 0;
    v87 = 0x80000000;
    v88 = 0;
    v89 = 0;
    v90 = 0x80000000;
    v9 = (Dr::DrawingSelection *)((char *)v3 + 128);
    Dr::GetTopLevelSelectedElements((char *)v3 + 128, &Src);
    Dr::GetDrilldownSelectedElements((char *)v3 + 128, &v88);
    if ( v89 )
    {
      v11 = v86;
      v12 = v89 + v86;
      if ( v89 + v86 < v86 )
      {
        Ofc::COutOfRangeException::ThrowTag(0x22718588u);
        goto LABEL_146;
      }
      v13 = v87;
      if ( (v87 & 0x7FFFFFFF) >= v12 )
      {
        v2 = (struct Ofc::CProxyPtrImpl *)Src;
      }
      else
      {
        v111 = 0;
        v14 = 8;
        if ( v12 >> 2 > 8 )
          v14 = v12 >> 2;
        v15 = 0xFFFFFFFFLL;
        if ( v12 <= ~(_DWORD)v14 )
          v16 = (unsigned int)v14 + v12;
        else
          v16 = 0xFFFFFFFFLL;
        v24 = 8 * v16;
        if ( v24 <= 0xFFFFFFFF )
          v15 = (unsigned int)v24;
        v1 = (char *)((unsigned int)v15 >> 3);
        if ( (unsigned int)v1 < v12 )
        {
          Ofc::COutOfMemoryException::ThrowTag(0x1E318643u);
LABEL_144:
          v79 = 1;
          goto LABEL_135;
        }
        v2 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)v15, v14, v10);
        v111 = v2;
        v87 = (unsigned int)v1 | v13 & 0x80000000;
        v25 = (Mso::Memory *)Src;
        Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do(Src, v2);
        Src = v2;
        if ( v25 )
          Mso::Memory::Free(v25, v26);
      }
      v27 = (Mso::Memory *)v88;
      Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do(v88, (char *)v2 + 8 * v11);
      v86 = v12;
      if ( v27 )
        Mso::Memory::Free(v27, v28);
      v88 = 0;
      v90 &= 0x80000000;
      v89 = 0;
      v3 = (Dr::DrawingSelection *)this;
    }
    else
    {
      v12 = v86;
      v2 = (struct Ofc::CProxyPtrImpl *)Src;
    }
    v1 = (char *)v3 + 264;
    Dr::DrawingSelection::GetE2oInfo(v9, (Dr::DrawingSelection *)((char *)v3 + 264));
    v111 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v110);
    v29 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v111);
    v92 = Ofc::CProxyPtrImpl::WeakAddRef(v29[21]);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v111);
    v109 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v104 = 1;
    v105 = Ofc::CProxyPtrImpl::WeakAddRef(v92);
    v106 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    v107 = 1;
    Ofc::CProxyPtrImpl::WeakAssign(&v106, v92);
    v9 = (struct Dr::DrawingSelectionInfo *)&Ofc::TypeInfo::s_moduleTag;
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          v111 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
          Ofc::TNodeIterator<Art::ViewElement>::DoNext(&v104, &v111, 0);
          Ofc::CProxyPtrImpl::CheckedStrongAssign(&v109, v111);
          v30 = *((_QWORD *)v109 + 2);
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v111);
          if ( !v30 )
          {
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v106);
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v105);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v109);
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v92);
            v64 = (Mso::Memory *)v88;
            v65 = (struct Ofc::CProxyPtrImpl **)((char *)v88 + 8 * v89);
            if ( v65 > v88 )
            {
              do
                Ofc::CProxyPtrImpl::DtorWeakRelease(--v65);
              while ( v65 > (struct Ofc::CProxyPtrImpl **)v64 );
            }
            if ( v64 )
              Mso::Memory::Free(v64, v63);
            for ( i = (struct Ofc::CProxyPtrImpl **)((char *)v2 + 8 * v12);
                  i > (struct Ofc::CProxyPtrImpl **)v2;
                  Ofc::CProxyPtrImpl::DtorWeakRelease(i) )
            {
              --i;
            }
            if ( v2 )
              Mso::Memory::Free(v2, v63);
            v3 = (Dr::DrawingSelection *)this;
            goto LABEL_14;
          }
          v31 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v109);
          v32 = Ofc::CProxyPtrImpl::StrongAddRef(v31[9]);
          v81 = v32;
          if ( *((_QWORD *)v32 + 2) )
            break;
          MsoShipAssertTagProc(3737359);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v81);
        }
        v33 = Ofc::CProxyPtrImpl::GetChecked(v32);
        if ( !(*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)v33 + 280LL))(v33) )
          break;
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v81);
      }
      v34 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v81 + 2);
      if ( v34 )
      {
        for ( j = (_QWORD *)(**v34)(v34); j; j = (_QWORD *)*j )
        {
          v36 = j[1];
          if ( (const struct Dr::DrawingShapeViewElement ***)v36 == &Ofc::TypeInfoImpl<Dr::DrawingShapeViewElement const *>::c_typeInfo
            || *(struct Dr::DrawingSelectionInfo **)(v36 + 8) != v9
            && !(unsigned int)__std_type_info_compare(*(_QWORD *)v36 + 8LL, &qword_180E0A7A8) )
          {
            v37 = v81;
            goto LABEL_42;
          }
        }
      }
      v37 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_42:
      v99 = Ofc::CProxyPtrImpl::StrongAddRef(v37);
      v38 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v81 + 2);
      if ( v38 )
      {
        for ( k = (_QWORD *)(**v38)(v38); k; k = (_QWORD *)*k )
        {
          v40 = k[1];
          if ( (const struct Dr::InkViewElement ***)v40 == &Ofc::TypeInfoImpl<Dr::InkViewElement const *>::c_typeInfo
            || *(struct Dr::DrawingSelectionInfo **)(v40 + 8) != v9
            && !(unsigned int)__std_type_info_compare(*(_QWORD *)v40 + 8LL, &qword_180E0A818) )
          {
            v41 = v81;
            goto LABEL_51;
          }
        }
      }
      v41 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_51:
      v98 = Ofc::CProxyPtrImpl::StrongAddRef(v41);
      v42 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v81 + 2);
      if ( v42 )
      {
        for ( m = (_QWORD *)(**v42)(v42); m; m = (_QWORD *)*m )
        {
          v44 = m[1];
          if ( (const struct Dr::InkActionsViewElement ***)v44 == &Ofc::TypeInfoImpl<Dr::InkActionsViewElement const *>::c_typeInfo
            || *(struct Dr::DrawingSelectionInfo **)(v44 + 8) != v9
            && !(unsigned int)__std_type_info_compare(*(_QWORD *)v44 + 8LL, &qword_180E0A848) )
          {
            v45 = v81;
            goto LABEL_60;
          }
        }
      }
      v45 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_60:
      v97 = Ofc::CProxyPtrImpl::StrongAddRef(v45);
      v46 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v81 + 2);
      if ( v46 )
      {
        for ( n = (_QWORD *)(**v46)(v46); n; n = (_QWORD *)*n )
        {
          v48 = n[1];
          if ( (const struct Dr::DrawingGroupViewElement ***)v48 == &Ofc::TypeInfoImpl<Dr::DrawingGroupViewElement const *>::c_typeInfo
            || *(struct Dr::DrawingSelectionInfo **)(v48 + 8) != v9
            && !(unsigned int)__std_type_info_compare(*(_QWORD *)v48 + 8LL, &qword_180E0A7E0) )
          {
            v49 = v81;
            goto LABEL_69;
          }
        }
      }
      v49 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_69:
      v96 = Ofc::CProxyPtrImpl::StrongAddRef(v49);
      v50 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v81 + 2);
      if ( v50 )
      {
        for ( ii = (_QWORD *)(**v50)(v50); ii; ii = (_QWORD *)*ii )
        {
          v52 = ii[1];
          if ( (const struct Art::ACompatE2oShapeViewElement ***)v52 == &Ofc::TypeInfoImpl<Art::ACompatE2oShapeViewElement const *>::c_typeInfo
            || *(struct Dr::DrawingSelectionInfo **)(v52 + 8) != v9
            && !(unsigned int)__std_type_info_compare(*(_QWORD *)v52 + 8LL, &qword_180E0A648) )
          {
            v53 = v81;
            goto LABEL_78;
          }
        }
      }
      v53 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_78:
      v91 = Ofc::CProxyPtrImpl::StrongAddRef(v53);
      if ( *((_QWORD *)v99 + 2) )
      {
        v58 = v2;
        v59 = Ofc::CProxyPtrImpl::GetChecked(v99);
        while ( v58 != (struct Ofc::CProxyPtrImpl *)((char *)v2 + 8 * v12) )
        {
          if ( *(_QWORD *)(*(_QWORD *)v58 + 16LL) == *(_QWORD *)(v59[54] + 16LL) )
          {
            if ( v83 >= (v84 & 0x7FFFFFFF)
              && v82
              && v82 <= (unsigned __int64)&v81
              && (unsigned __int64)&v81 < v82 + 8 * v83 )
            {
              v93 = Ofc::CProxyPtrImpl::WeakAddRef(v81);
              v68 = (struct Ofc::CProxyPtrImpl **)Ofc::CArrayImpl::NewTop<Ofc::TWeakPtr<Dr::DrawingElement const>>(&v82);
              Ofc::CProxyPtrImpl::WeakMoveAssign(v68, &v93);
              Ofc::CProxyPtrImpl::DtorWeakRelease(&v93);
            }
            else
            {
              v67 = (struct Ofc::CProxyPtrImpl **)Ofc::CArrayImpl::NewTop<Ofc::TWeakPtr<Dr::DrawingElement const>>(&v82);
              Ofc::CProxyPtrImpl::WeakAssign(v67, v81);
            }
            goto LABEL_95;
          }
          v58 = (struct Ofc::CProxyPtrImpl *)((char *)v58 + 8);
        }
      }
      if ( *((_QWORD *)v96 + 2) )
      {
        v60 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v96);
        v61 = Ofc::CProxyPtrImpl::WeakAddRef(v60[53]);
        v100 = v61;
        v4 |= 1u;
        for ( jj = v2;
              jj != (struct Ofc::CProxyPtrImpl *)((char *)v2 + 8 * v12);
              jj = (struct Ofc::CProxyPtrImpl *)((char *)jj + 8) )
        {
          if ( *(_QWORD *)(*(_QWORD *)jj + 16LL) == *((_QWORD *)v61 + 2) )
          {
            v54 = 1;
            goto LABEL_81;
          }
        }
      }
      v54 = 0;
LABEL_81:
      if ( (v4 & 1) != 0 )
      {
        v4 &= ~1u;
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v100);
      }
      if ( v54 )
      {
LABEL_121:
        Ofc::TArray<Ofc::TWeakPtr<Dr::MovieDrawingElement>>::Add<Ofc::TReferringPtr<Dr::MovieDrawingElement>>(
          &v82,
          &v81);
        goto LABEL_95;
      }
      v55 = v97;
      if ( *((_QWORD *)v97 + 2) )
      {
LABEL_146:
        v80 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v55);
        v94 = Ofc::CProxyPtrImpl::WeakAddRef(v80[33]);
        v4 |= 2u;
        if ( (unsigned __int8)Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>>::FContains<Ofc::TWeakPtr<Dr::InkDrawingElement>>(
                                &Src,
                                &v94) )
        {
          v56 = 1;
          goto LABEL_86;
        }
      }
      v56 = 0;
LABEL_86:
      if ( (v4 & 2) != 0 )
      {
        v4 &= ~2u;
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v94);
      }
      if ( v56 )
        goto LABEL_121;
      if ( *((_QWORD *)v98 + 2) )
      {
        v69 = (struct Ofc::CProxyPtrImpl **)Ofc::CProxyPtrImpl::GetChecked(v98);
        v70 = Ofc::CProxyPtrImpl::WeakAddRef(v69[31]);
        v101 = v70;
        v4 |= 4u;
        for ( kk = v2;
              kk != (struct Ofc::CProxyPtrImpl *)((char *)v2 + 8 * v12);
              kk = (struct Ofc::CProxyPtrImpl *)((char *)kk + 8) )
        {
          if ( *(_QWORD *)(*(_QWORD *)kk + 16LL) == *((_QWORD *)v70 + 2) )
          {
            v57 = 1;
            goto LABEL_91;
          }
        }
      }
      v57 = 0;
LABEL_91:
      if ( (v4 & 4) != 0 )
      {
        v4 &= ~4u;
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v101);
      }
      if ( v57 )
        goto LABEL_121;
      if ( *((_QWORD *)v91 + 2) )
      {
        v72 = Ofc::CProxyPtrImpl::GetChecked(v91);
        v73 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)v72 + 1216LL))(
                                              v72,
                                              &v102);
        v95 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v73);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v102);
        if ( *((_QWORD *)v95 + 2) )
        {
          v74 = Ofc::CProxyPtrImpl::GetChecked(v95);
          if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)v74 + 88LL))(v74) )
          {
            v75 = Ofc::CProxyPtrImpl::GetChecked(v91);
            v76 = (*(__int64 (__fastcall **)(void *, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)v75 + 1216LL))(
                    v75,
                    &v103);
            v4 |= 8u;
            v77 = *((_QWORD *)v1 + 2);
            v78 = v77 + 8LL * *((unsigned int *)v1 + 6);
            while ( v77 != v78 )
            {
              if ( *(_QWORD *)(*(_QWORD *)v77 + 16LL) == *(_QWORD *)(*(_QWORD *)v76 + 16LL) )
                goto LABEL_144;
              v77 += 8;
            }
          }
        }
        v79 = 0;
LABEL_135:
        if ( (v4 & 8) != 0 )
        {
          v4 &= ~8u;
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v103);
        }
        if ( v79 )
          Ofc::TArray<Ofc::TWeakPtr<Dr::MovieDrawingElement>>::Add<Ofc::TReferringPtr<Dr::MovieDrawingElement>>(
            &v82,
            &v81);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v95);
      }
LABEL_95:
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v91);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v96);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v97);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v98);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v99);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v81);
    }
  }
LABEL_14:
  v17 = (char *)v3 + 96;
  v18 = (Mso::Memory *)*((_QWORD *)v3 + 12);
  *(_QWORD *)v17 = v82;
  v19 = *((unsigned int *)v17 + 2);
  *((_DWORD *)v17 + 2) = v83;
  v20 = *((_DWORD *)v17 + 3) & 0x7FFFFFFF | v84 & 0x80000000;
  *((_DWORD *)v17 + 3) = v20 ^ (v20 ^ (*((_DWORD *)v17 + 3) & 0x80000000 | v84 & 0x7FFFFFFF)) & 0x7FFFFFFF;
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v110);
  for ( mm = (struct Ofc::CProxyPtrImpl **)((char *)v18 + 8 * v19);
        mm > (struct Ofc::CProxyPtrImpl **)v18;
        Ofc::CProxyPtrImpl::DtorWeakRelease(mm) )
  {
    --mm;
  }
  if ( v18 )
    Mso::Memory::Free(v18, v21);
  return (struct Art::ViewElemSelectionInfo *)v17;
}

```

## disassembly

```asm
0x1800e3730  mov     [rsp-8+arg_0], rcx
0x1800e3735  push    rbp
0x1800e3736  push    rbx
0x1800e3737  push    rsi
0x1800e3738  push    rdi
0x1800e3739  push    r12
0x1800e373b  push    r13
0x1800e373d  push    r14
0x1800e373f  push    r15
0x1800e3741  lea     rbp, [rsp-1Fh]
0x1800e3746  sub     rsp, 0E8h
0x1800e374d  mov     rdi, rcx
0x1800e3750  xor     r15d, r15d
0x1800e3753  mov     dword ptr [rbp+57h+arg_8], r15d
0x1800e3757  mov     [rsp+120h+var_F8], r15
0x1800e375c  mov     [rsp+120h+var_F0], r15d
0x1800e3761  mov     [rsp+120h+var_EC], 80000000h
0x1800e3769  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1800e3770  mov     [rbp+57h+arg_10], rax
0x1800e3774  mov     rcx, [rcx+3A8h]; struct Ofc::CProxyPtrImpl *
0x1800e377b  cmp     [rcx+10h], r15
0x1800e377f  jz      short loc_1800E37BF
0x1800e3781  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1800e3786  mov     [rbp+57h+arg_8], rax
0x1800e378a  mov     rcx, rax; this
0x1800e378d  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800e3792  mov     rdx, rax
0x1800e3795  mov     rcx, [rax]
0x1800e3798  mov     rax, [rcx+78h]
0x1800e379c  mov     rcx, rdx
0x1800e379f  call    cs:__guard_dispatch_icall_fptr
0x1800e37a5  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x1800e37a8  lea     rcx, [rbp+57h+arg_10]; struct Ofc::CProxyPtrImpl **
0x1800e37ac  call    ?WeakAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1800e37b1  nop
0x1800e37b2  lea     rcx, [rbp+57h+arg_8]; struct Ofc::CProxyPtrImpl **
0x1800e37b6  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800e37bb  mov     rax, [rbp+57h+arg_10]
0x1800e37bf  cmp     qword ptr [rax+10h], 0
0x1800e37c4  jz      loc_1800E387B
0x1800e37ca  mov     [rsp+120h+Src], r15
0x1800e37cf  mov     [rsp+120h+var_E0], r15d
0x1800e37d4  mov     [rsp+120h+var_DC], 80000000h
0x1800e37dc  mov     [rsp+120h+var_D8], r15
0x1800e37e1  mov     [rbp+57h+var_D0], r15d
0x1800e37e5  mov     [rbp+57h+var_CC], 80000000h
0x1800e37ec  lea     r14, [rdi+80h]
0x1800e37f3  lea     rdx, [rsp+120h+Src]
0x1800e37f8  mov     rcx, r14
0x1800e37fb  call    ?GetTopLevelSelectedElements@Dr@@YAXAEAVDrawingSelectionInfo@1@AEAV?$TArray@V?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@@Ofc@@@Z; Dr::GetTopLevelSelectedElements(Dr::DrawingSelectionInfo &,Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>> &)
0x1800e3800  lea     rdx, [rsp+120h+var_D8]
0x1800e3805  mov     rcx, r14
0x1800e3808  call    ?GetDrilldownSelectedElements@Dr@@YAXAEAVDrawingSelectionInfo@1@AEAV?$TArray@V?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@@Ofc@@@Z; Dr::GetDrilldownSelectedElements(Dr::DrawingSelectionInfo &,Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>> &)
0x1800e380d  mov     ebx, [rbp+57h+var_D0]
0x1800e3810  test    ebx, ebx
0x1800e3812  jz      loc_1800E40D1
0x1800e3818  mov     edi, [rsp+120h+var_E0]
0x1800e381c  lea     r13d, [rbx+rdi]
0x1800e3820  cmp     r13d, edi
0x1800e3823  jb      loc_1800E4100
0x1800e3829  mov     ebx, [rsp+120h+var_DC]
0x1800e382d  mov     eax, ebx
0x1800e382f  btr     eax, 1Fh
0x1800e3833  cmp     eax, r13d
0x1800e3836  jnb     loc_1800E3F94
0x1800e383c  mov     [rbp+57h+arg_18], r15
0x1800e3840  mov     eax, r13d
0x1800e3843  shr     eax, 2
0x1800e3846  mov     edx, 8
0x1800e384b  cmp     eax, edx
0x1800e384d  cmova   edx, eax; unsigned __int64
0x1800e3850  mov     eax, edx
0x1800e3852  not     eax
0x1800e3854  mov     ecx, 0FFFFFFFFh
0x1800e3859  cmp     r13d, eax
0x1800e385c  jbe     loc_1800E3912
0x1800e3862  mov     eax, ecx
0x1800e3864  jmp     loc_1800E3916
0x1800e3869  test    r12, r12
0x1800e386c  jz      short loc_1800E3877
0x1800e386e  mov     rcx, r12
0x1800e3871  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e3877  mov     rdi, [rbp+57h+arg_0]
0x1800e387b  lea     rsi, [rdi+60h]
0x1800e387f  mov     rdi, [rsi]
0x1800e3882  mov     rax, [rsp+120h+var_F8]
0x1800e3887  mov     [rsi], rax
0x1800e388a  mov     ebx, [rsi+8]
0x1800e388d  mov     eax, [rsp+120h+var_F0]
0x1800e3891  mov     [rsi+8], eax
0x1800e3894  mov     ecx, [rsi+0Ch]
0x1800e3897  mov     edx, [rsp+120h+var_EC]
0x1800e389b  mov     r8d, edx
0x1800e389e  btr     r8d, 1Fh
0x1800e38a3  mov     eax, ecx
0x1800e38a5  and     eax, 80000000h
0x1800e38aa  or      r8d, eax
0x1800e38ad  and     edx, 80000000h
0x1800e38b3  btr     ecx, 1Fh
0x1800e38b7  or      edx, ecx
0x1800e38b9  xor     r8d, edx
0x1800e38bc  btr     r8d, 1Fh
0x1800e38c1  xor     r8d, edx
0x1800e38c4  mov     [rsi+0Ch], r8d
0x1800e38c8  lea     rcx, [rbp+57h+arg_10]; struct Ofc::CProxyPtrImpl **
0x1800e38cc  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1800e38d1  lea     rbx, [rdi+rbx*8]
0x1800e38d5  cmp     rbx, rdi
0x1800e38d8  ja      short loc_1800E38FF
0x1800e38da  test    rdi, rdi
0x1800e38dd  jz      short loc_1800E38E8
0x1800e38df  mov     rcx, rdi
0x1800e38e2  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e38e8  mov     rax, rsi
0x1800e38eb  add     rsp, 0E8h
0x1800e38f2  pop     r15
0x1800e38f4  pop     r14
0x1800e38f6  pop     r13
0x1800e38f8  pop     r12
0x1800e38fa  pop     rdi
0x1800e38fb  pop     rsi
0x1800e38fc  pop     rbx
0x1800e38fd  pop     rbp
0x1800e38fe  retn
0x1800e38ff  sub     rbx, 8
0x1800e3903  mov     rcx, rbx; struct Ofc::CProxyPtrImpl **
0x1800e3906  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1800e390b  cmp     rbx, rdi
0x1800e390e  ja      short loc_1800E38FF
0x1800e3910  jmp     short loc_1800E38DA
0x1800e3912  lea     eax, [rdx+r13]
0x1800e3916  shl     rax, 3
0x1800e391a  cmp     rax, rcx
0x1800e391d  cmovbe  ecx, eax; this
0x1800e3920  mov     esi, ecx
0x1800e3922  shr     esi, 3
0x1800e3925  cmp     esi, r13d
0x1800e3928  jb      loc_1800E40EE
0x1800e392e  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1800e3933  mov     r12, rax
0x1800e3936  mov     [rbp+57h+arg_18], rax
0x1800e393a  and     ebx, 80000000h
0x1800e3940  or      ebx, esi
0x1800e3942  mov     [rsp+120h+var_DC], ebx
0x1800e3946  mov     r8d, edi
0x1800e3949  mov     rdx, rax; void *
0x1800e394c  mov     rbx, [rsp+120h+Src]
0x1800e3951  mov     rcx, rbx; Src
0x1800e3954  call    ?Do@?$TMoveConstructRange@V?$TReferringPtr@UIInkDrawing@Art@@@Ofc@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do(uchar *,uchar *,ulong)
0x1800e3959  mov     [rsp+120h+Src], r12
0x1800e395e  test    rbx, rbx
0x1800e3961  jz      short loc_1800E396C
0x1800e3963  mov     rcx, rbx
0x1800e3966  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e396c  lea     edx, ds:0[rdi*8]
0x1800e3973  add     rdx, r12; void *
0x1800e3976  mov     r8d, [rbp+57h+var_D0]
0x1800e397a  mov     rbx, [rsp+120h+var_D8]
0x1800e397f  mov     rcx, rbx; Src
0x1800e3982  call    ?Do@?$TMoveConstructRange@V?$TReferringPtr@UIInkDrawing@Art@@@Ofc@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do(uchar *,uchar *,ulong)
0x1800e3987  mov     [rsp+120h+var_E0], r13d
0x1800e398c  test    rbx, rbx
0x1800e398f  jz      short loc_1800E399A
0x1800e3991  mov     rcx, rbx
0x1800e3994  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800e399a  mov     [rsp+120h+var_D8], r15
0x1800e399f  and     [rbp+57h+var_CC], 80000000h
0x1800e39a6  mov     [rbp+57h+var_D0], r15d
0x1800e39aa  mov     rdi, [rbp+57h+arg_0]
0x1800e39ae  lea     rsi, [rdi+108h]
0x1800e39b5  mov     rdx, rsi; struct Dr::GeneratedE2oSelectionInfo *
0x1800e39b8  mov     rcx, r14; struct Dr::DrawingSelectionInfo *
0x1800e39bb  call    ?GetE2oInfo@DrawingSelection@Dr@@KAXAEAVDrawingSelectionInfo@2@AEAVGeneratedE2oSelectionInfo@2@@Z; Dr::DrawingSelection::GetE2oInfo(Dr::DrawingSelectionInfo &,Dr::GeneratedE2oSelectionInfo &)
0x1800e39c0  mov     rcx, [rbp+57h+arg_10]; struct Ofc::CProxyPtrImpl *
0x1800e39c4  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x1800e39c9  mov     [rbp+57h+arg_18], rax
0x1800e39cd  mov     rcx, rax; this
0x1800e39d0  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800e39d5  mov     rcx, [rax+0A8h]; struct Ofc::CProxyPtrImpl *
0x1800e39dc  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x1800e39e1  mov     [rbp+57h+var_C0], rax
0x1800e39e5  lea     rcx, [rbp+57h+arg_18]; struct Ofc::CProxyPtrImpl **
0x1800e39e9  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800e39ee  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1800e39f5  mov     [rbp+57h+arg_8], rax
0x1800e39f9  mov     [rbp+57h+var_60], 1
0x1800e3a00  mov     rcx, [rbp+57h+var_C0]; struct Ofc::CProxyPtrImpl *
0x1800e3a04  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x1800e3a09  mov     [rbp+57h+var_58], rax
0x1800e3a0d  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1800e3a14  mov     [rbp+57h+var_50], rax
0x1800e3a18  mov     [rbp+57h+var_48], 1
0x1800e3a1c  mov     rdx, [rbp+57h+var_C0]; struct Ofc::CProxyPtrImpl *
0x1800e3a20  lea     rcx, [rbp+57h+var_50]; struct Ofc::CProxyPtrImpl **
0x1800e3a24  call    ?WeakAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1800e3a29  lea     r14, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x1800e3a30  lea     rdi, ?c_typeInfo@?$TypeInfoImpl@PEBVDrawingShapeViewElement@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::DrawingShapeViewElement const *>::c_typeInfo
0x1800e3a37  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1800e3a3e  mov     [rbp+57h+arg_18], rax
0x1800e3a42  xor     r8d, r8d
0x1800e3a45  lea     rdx, [rbp+57h+arg_18]
0x1800e3a49  lea     rcx, [rbp+57h+var_60]
0x1800e3a4d  call    ?DoNext@?$TNodeIterator@VViewElement@Art@@@Ofc@@AEAA_NAEAV?$TWeakPtr@V?$TTreeNode@VViewElement@Art@@@Ofc@@@2@_N@Z; Ofc::TNodeIterator<Art::ViewElement>::DoNext(Ofc::TWeakPtr<Ofc::TTreeNode<Art::ViewElement>> &,bool)
0x1800e3a52  mov     rdx, [rbp+57h+arg_18]; struct Ofc::CProxyPtrImpl *
0x1800e3a56  lea     rcx, [rbp+57h+arg_8]; struct Ofc::CProxyPtrImpl **
0x1800e3a5a  call    ?CheckedStrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x1800e3a5f  mov     rax, [rbp+57h+arg_8]
0x1800e3a63  mov     rbx, [rax+10h]
0x1800e3a67  lea     rcx, [rbp+57h+arg_18]; struct Ofc::CProxyPtrImpl **
0x1800e3a6b  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x1800e3a70  test    rbx, rbx
0x1800e3a73  jz      loc_1800E3E49
0x1800e3a79  mov     rcx, [rbp+57h+arg_8]; this
0x1800e3a7d  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800e3a82  mov     rcx, [rax+48h]; struct Ofc::CProxyPtrImpl *
0x1800e3a86  call    ?StrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAddRef(Ofc::CProxyPtrImpl *)
0x1800e3a8b  mov     [rsp+120h+var_100], rax
0x1800e3a90  cmp     qword ptr [rax+10h], 0
0x1800e3a95  jz      loc_1800E3FE1
0x1800e3a9b  mov     rcx, rax; this
0x1800e3a9e  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800e3aa3  mov     rdx, rax
0x1800e3aa6  mov     rcx, [rax]
0x1800e3aa9  mov     rax, [rcx+118h]
0x1800e3ab0  mov     rcx, rdx
0x1800e3ab3  call    cs:__guard_dispatch_icall_fptr
0x1800e3ab9  test    al, al
0x1800e3abb  jnz     loc_1800E3DF7
0x1800e3ac1  mov     rax, [rsp+120h+var_100]
0x1800e3ac6  mov     rcx, [rax+10h]
0x1800e3aca  test    rcx, rcx
0x1800e3acd  jz      short loc_1800E3B16
0x1800e3acf  mov     rax, [rcx]
0x1800e3ad2  mov     rax, [rax]
0x1800e3ad5  call    cs:__guard_dispatch_icall_fptr
0x1800e3adb  mov     rbx, rax
0x1800e3ade  test    rbx, rbx
0x1800e3ae1  jz      short loc_1800E3B16
0x1800e3ae3  mov     rcx, [rbx+8]
0x1800e3ae7  cmp     rcx, rdi
0x1800e3aea  jz      short loc_1800E3B0F
0x1800e3aec  cmp     [rcx+8], r14
0x1800e3af0  jnz     short loc_1800E3AF7
0x1800e3af2  mov     rbx, [rbx]
0x1800e3af5  jmp     short loc_1800E3ADE
0x1800e3af7  mov     rcx, [rcx]
0x1800e3afa  add     rcx, 8
0x1800e3afe  lea     rdx, qword_180E0A7A8
0x1800e3b05  call    cs:__imp___std_type_info_compare
0x1800e3b0b  test    eax, eax
0x1800e3b0d  jnz     short loc_1800E3AF2
0x1800e3b0f  mov     rcx, [rsp+120h+var_100]
0x1800e3b14  jmp     short loc_1800E3B1D
0x1800e3b16  mov     rcx, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; struct Ofc::CProxyPtrImpl *
0x1800e3b1d  call    ?StrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAddRef(Ofc::CProxyPtrImpl *)
0x1800e3b22  mov     [rbp+57h+var_88], rax
0x1800e3b26  mov     rax, [rsp+120h+var_100]
0x1800e3b2b  mov     rcx, [rax+10h]
0x1800e3b2f  test    rcx, rcx
0x1800e3b32  jz      short loc_1800E3B82
0x1800e3b34  mov     rax, [rcx]
0x1800e3b37  mov     rax, [rax]
0x1800e3b3a  call    cs:__guard_dispatch_icall_fptr
0x1800e3b40  mov     rbx, rax
0x1800e3b43  test    rbx, rbx
0x1800e3b46  jz      short loc_1800E3B82
0x1800e3b48  mov     rcx, [rbx+8]
0x1800e3b4c  lea     rax, ?c_typeInfo@?$TypeInfoImpl@PEBVInkViewElement@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::InkViewElement const *>::c_typeInfo
0x1800e3b53  cmp     rcx, rax
0x1800e3b56  jz      short loc_1800E3B7B
0x1800e3b58  cmp     [rcx+8], r14
0x1800e3b5c  jnz     short loc_1800E3B63
0x1800e3b5e  mov     rbx, [rbx]
0x1800e3b61  jmp     short loc_1800E3B43
0x1800e3b63  mov     rcx, [rcx]
0x1800e3b66  add     rcx, 8
0x1800e3b6a  lea     rdx, qword_180E0A818
0x1800e3b71  call    cs:__imp___std_type_info_compare
0x1800e3b77  test    eax, eax
0x1800e3b79  jnz     short loc_1800E3B5E
0x1800e3b7b  mov     rcx, [rsp+120h+var_100]
0x1800e3b80  jmp     short loc_1800E3B89
0x1800e3b82  mov     rcx, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; struct Ofc::CProxyPtrImpl *
0x1800e3b89  call    ?StrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAddRef(Ofc::CProxyPtrImpl *)
0x1800e3b8e  mov     [rbp+57h+var_90], rax
0x1800e3b92  mov     rax, [rsp+120h+var_100]
0x1800e3b97  mov     rcx, [rax+10h]
0x1800e3b9b  test    rcx, rcx
0x1800e3b9e  jz      short loc_1800E3BEE
0x1800e3ba0  mov     rax, [rcx]
0x1800e3ba3  mov     rax, [rax]
0x1800e3ba6  call    cs:__guard_dispatch_icall_fptr
0x1800e3bac  mov     rbx, rax
0x1800e3baf  test    rbx, rbx
0x1800e3bb2  jz      short loc_1800E3BEE
0x1800e3bb4  mov     rcx, [rbx+8]
0x1800e3bb8  lea     rax, ?c_typeInfo@?$TypeInfoImpl@PEBVInkActionsViewElement@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::InkActionsViewElement const *>::c_typeInfo
0x1800e3bbf  cmp     rcx, rax
0x1800e3bc2  jz      short loc_1800E3BE7
0x1800e3bc4  cmp     [rcx+8], r14
  ... truncated ...
```
