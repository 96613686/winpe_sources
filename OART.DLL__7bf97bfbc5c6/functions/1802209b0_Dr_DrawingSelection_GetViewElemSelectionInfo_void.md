# Dr::DrawingSelection::GetViewElemSelectionInfo(void)

- ea: `0x1802209b0`
- end: `0x180221495`
- name: `?GetViewElemSelectionInfo@DrawingSelection@Dr@@MEAAPEAVViewElemSelectionInfo@Art@@XZ`
- size: `2789`
- prototype: `struct Art::ViewElemSelectionInfo *__fastcall(Dr::DrawingSelection *__hidden this)`
- caller_count: `0`
- callee_count: `21`
- tags: `broker_com_uri`

## callees

- `0x180001504`
- `0x180001810`
- `0x18001e0d0`
- `0x1800458fc`
- `0x1800659a0`
- `0x18006a2b0`
- `0x180071720`
- `0x1800c0e8c`
- `0x1800cbb90`
- `0x1800ed700`
- `0x1800edb5c`
- `0x1802209b0`
- `0x18053c554`
- `0x1805ef130`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806a5c90`
- `0x1806bce1c`
- `0x1806bd790`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x180220da7`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220e1e`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220e92`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220f0e`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220f82`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220da7`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220e1e`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220e92`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220f0e`
- `VCRUNTIME140!__std_type_info_compare` at `0x180220f82`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802212c8`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802212c8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180220af1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180220b74`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180220be5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180220c13`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18022116a`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180220af1`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180220b74`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180220be5`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180220c13`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18022116a`

## pseudocode

```c
const struct Dr::DrawingShapeViewElement ***__fastcall Dr::DrawingSelection::GetViewElemSelectionInfo(
        const struct Dr::DrawingShapeViewElement ***this)
{
  Ofc::CProxyPtrImpl *v1; // rsi
  struct Ofc::CProxyPtrImpl *v2; // r12
  const struct Dr::DrawingShapeViewElement ***v3; // rdi
  int v4; // r15d
  struct Ofc::CProxyPtrImpl *v5; // rax
  struct Ofc::CProxyPtrImpl *v6; // rcx
  void *Checked; // rax
  struct Ofc::CProxyPtrImpl **v8; // rax
  struct Dr::DrawingSelectionInfo *v9; // r14
  unsigned int v10; // r8d
  unsigned int v11; // r13d
  unsigned int v12; // ebx
  unsigned __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  const struct Dr::DrawingShapeViewElement ***v16; // rsi
  Mso::Memory *v17; // rdi
  __int64 v18; // rbx
  void *v19; // rdx
  struct Ofc::CProxyPtrImpl **mm; // rbx
  unsigned __int64 v22; // rax
  unsigned int v23; // esi
  Mso::Memory *v24; // rbx
  void *v25; // rdx
  Mso::Memory *v26; // rbx
  void *v27; // rdx
  volatile signed __int32 *v28; // rcx
  struct Ofc::CProxyPtrImpl *v29; // rcx
  __int64 v30; // rbx
  volatile signed __int32 *v31; // rcx
  void *v32; // rax
  __int64 (__fastcall ***v33)(_QWORD); // rcx
  _QWORD *i; // rbx
  const struct Dr::DrawingShapeViewElement ***v35; // rcx
  struct Ofc::CProxyPtrImpl *v36; // rcx
  __int64 (__fastcall ***v37)(_QWORD); // rcx
  _QWORD *j; // rbx
  __int64 v39; // rcx
  struct Ofc::CProxyPtrImpl *v40; // rcx
  __int64 (__fastcall ***v41)(_QWORD); // rcx
  _QWORD *k; // rbx
  __int64 v43; // rcx
  struct Ofc::CProxyPtrImpl *v44; // rcx
  __int64 (__fastcall ***v45)(_QWORD); // rcx
  _QWORD *m; // rbx
  __int64 v47; // rcx
  struct Ofc::CProxyPtrImpl *v48; // rcx
  __int64 (__fastcall ***v49)(_QWORD); // rcx
  _QWORD *n; // rbx
  __int64 v51; // rcx
  struct Ofc::CProxyPtrImpl *v52; // rcx
  char v53; // bl
  bool v54; // bl
  char v55; // bl
  struct Ofc::CProxyPtrImpl *v56; // rbx
  _QWORD *v57; // rax
  __int64 v58; // r8
  struct Ofc::CProxyPtrImpl *ii; // rdx
  void *v60; // rdx
  Mso::Memory *v61; // rsi
  struct Ofc::CProxyPtrImpl **v62; // rbx
  struct Ofc::CProxyPtrImpl **kk; // rbx
  struct Ofc::CProxyPtrImpl **v64; // rax
  struct Ofc::CProxyPtrImpl *v65; // rcx
  struct Ofc::CProxyPtrImpl **v66; // rax
  __int64 v67; // r8
  struct Ofc::CProxyPtrImpl *jj; // rdx
  void *v69; // rax
  struct Ofc::CProxyPtrImpl **v70; // rax
  void *v71; // rax
  void *v72; // rax
  __int64 v73; // r9
  __int64 v74; // rdx
  __int64 v75; // r8
  char v76; // bl
  void *v77; // rax
  __int64 InkDrawingElement; // rax
  struct Ofc::CProxyPtrImpl *v79; // [rsp+20h] [rbp-A9h] BYREF
  const struct Dr::DrawingShapeViewElement **v80; // [rsp+28h] [rbp-A1h] BYREF
  unsigned int v81; // [rsp+30h] [rbp-99h]
  unsigned int v82; // [rsp+34h] [rbp-95h]
  void *Src; // [rsp+38h] [rbp-91h] BYREF
  unsigned int v84; // [rsp+40h] [rbp-89h]
  unsigned int v85; // [rsp+44h] [rbp-85h]
  void *v86; // [rsp+48h] [rbp-81h] BYREF
  unsigned int v87; // [rsp+50h] [rbp-79h]
  unsigned int v88; // [rsp+54h] [rbp-75h]
  Ofc::CProxyPtrImpl *v89; // [rsp+58h] [rbp-71h] BYREF
  Ofc::CProxyPtrImpl *v90; // [rsp+60h] [rbp-69h] BYREF
  struct Ofc::CProxyPtrImpl *v91; // [rsp+68h] [rbp-61h] BYREF
  struct Ofc::CProxyPtrImpl *v92; // [rsp+70h] [rbp-59h] BYREF
  Ofc::CProxyPtrImpl *v93; // [rsp+78h] [rbp-51h] BYREF
  Ofc::CProxyPtrImpl *v94; // [rsp+80h] [rbp-49h] BYREF
  Ofc::CProxyPtrImpl *v95; // [rsp+88h] [rbp-41h] BYREF
  Ofc::CProxyPtrImpl *v96; // [rsp+90h] [rbp-39h] BYREF
  struct Ofc::CProxyPtrImpl *v97; // [rsp+98h] [rbp-31h] BYREF
  struct Ofc::CProxyPtrImpl *v98; // [rsp+A0h] [rbp-29h] BYREF
  struct Ofc::CProxyPtrImpl *v99; // [rsp+A8h] [rbp-21h] BYREF
  struct Ofc::CProxyPtrImpl *v100; // [rsp+B0h] [rbp-19h] BYREF
  struct Ofc::CProxyPtrImpl *v101; // [rsp+B8h] [rbp-11h] BYREF
  int v102; // [rsp+C0h] [rbp-9h] BYREF
  struct Ofc::CProxyPtrImpl *v103; // [rsp+C8h] [rbp-1h] BYREF
  struct Ofc::CProxyPtrImpl *v104; // [rsp+D0h] [rbp+7h] BYREF
  char v105; // [rsp+D8h] [rbp+Fh]
  Ofc::CProxyPtrImpl *v107; // [rsp+138h] [rbp+6Fh] BYREF
  struct Ofc::CProxyPtrImpl *v108; // [rsp+140h] [rbp+77h] BYREF
  struct Ofc::CProxyPtrImpl *v109; // [rsp+148h] [rbp+7Fh] BYREF

  v3 = this;
  v4 = 0;
  LODWORD(v107) = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0x80000000;
  v5 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v108 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v6 = (struct Ofc::CProxyPtrImpl *)this[117];
  if ( *((_QWORD *)v6 + 2) )
  {
    v107 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v6);
    Checked = Ofc::CProxyPtrImpl::GetChecked(v107);
    v8 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 120LL))(Checked);
    Ofc::CProxyPtrImpl::WeakAssign(&v108, *v8);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v107);
    v5 = v108;
  }
  if ( !*((_QWORD *)v5 + 2) )
    goto LABEL_14;
  Src = 0;
  v84 = 0;
  v85 = 0x80000000;
  v86 = 0;
  v87 = 0;
  v88 = 0x80000000;
  v9 = (struct Dr::DrawingSelectionInfo *)(v3 + 16);
  Dr::GetTopLevelSelectedElements(v3 + 16, &Src);
  Dr::GetDrilldownSelectedElements(v3 + 16, &v86);
  if ( v87 )
  {
    v3 = (const struct Dr::DrawingShapeViewElement ***)v84;
    v11 = v87 + v84;
    if ( v87 + v84 < v84 )
    {
      Ofc::COutOfRangeException::ThrowTag(0x22718588u);
      goto LABEL_165;
    }
    v12 = v85;
    if ( (v85 & 0x7FFFFFFF) >= v11 )
    {
      v2 = (struct Ofc::CProxyPtrImpl *)Src;
LABEL_25:
      v26 = (Mso::Memory *)v86;
      Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do(
        v86,
        (char *)v2 + (unsigned int)(8 * (_DWORD)v3));
      v84 = v11;
      if ( v26 )
        Mso::Memory::Free(v26, v27);
      v86 = 0;
      v88 &= 0x80000000;
      v87 = 0;
      v3 = this;
      goto LABEL_28;
    }
    v109 = 0;
    v13 = 8;
    if ( v11 >> 2 > 8 )
      v13 = v11 >> 2;
    v14 = 0xFFFFFFFFLL;
    if ( v11 <= ~(_DWORD)v13 )
      v15 = (unsigned int)v13 + v11;
    else
      v15 = 0xFFFFFFFFLL;
    v22 = 8 * v15;
    if ( v22 <= 0xFFFFFFFF )
      v14 = (unsigned int)v22;
    v23 = (unsigned int)v14 >> 3;
    if ( (unsigned int)v14 >> 3 >= v11 )
    {
      v2 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)v14, v13, v10);
      v109 = v2;
      v85 = v23 | v12 & 0x80000000;
      v24 = (Mso::Memory *)Src;
      Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do(Src, v2);
      Src = v2;
      if ( v24 )
        Mso::Memory::Free(v24, v25);
      goto LABEL_25;
    }
    Ofc::COutOfMemoryException::ThrowTag(0x1E318643u);
  }
  v11 = v84;
  v2 = (struct Ofc::CProxyPtrImpl *)Src;
LABEL_28:
  v89 = (Ofc::CProxyPtrImpl *)(v3 + 33);
  Dr::DrawingSelection::GetE2oInfo(v9, (struct Dr::GeneratedE2oSelectionInfo *)(v3 + 33));
  v109 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(v108);
  v28 = (volatile signed __int32 *)*((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v109) + 21);
  if ( *((_DWORD *)v28 + 1) != 0x80000000 )
    _InterlockedIncrement(v28 + 1);
  v91 = (struct Ofc::CProxyPtrImpl *)v28;
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v109);
  v107 = (Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v102 = 1;
  v29 = v91;
  if ( *((_DWORD *)v91 + 1) != 0x80000000 )
    _InterlockedIncrement((volatile signed __int32 *)v91 + 1);
  v103 = v29;
  v104 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
  v105 = 1;
  Ofc::CProxyPtrImpl::WeakAssign(&v104, v91);
  v9 = (struct Dr::DrawingSelectionInfo *)&Ofc::TypeInfo::s_moduleTag;
  v1 = v89;
LABEL_33:
  v3 = &Ofc::TypeInfoImpl<Dr::DrawingShapeViewElement const *>::c_typeInfo;
  while ( 1 )
  {
    v109 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
    Ofc::TNodeIterator<Art::ViewElement>::DoNext(&v102, &v109, 0);
    Ofc::CProxyPtrImpl::CheckedStrongAssign(&v107, v109);
    v30 = *((_QWORD *)v107 + 2);
    Ofc::CProxyPtrImpl::DtorWeakRelease(&v109);
    if ( !v30 )
      break;
    v31 = (volatile signed __int32 *)*((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v107) + 9);
    if ( *v31 != 0x80000000 )
LABEL_165:
      _InterlockedIncrement(v31);
    v79 = (struct Ofc::CProxyPtrImpl *)v31;
    if ( *((_QWORD *)v31 + 2) )
    {
      v32 = Ofc::CProxyPtrImpl::GetChecked((Ofc::CProxyPtrImpl *)v31);
      if ( !(*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)v32 + 288LL))(v32) )
      {
        v33 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v79 + 2);
        if ( v33 )
        {
          for ( i = (_QWORD *)(**v33)(v33); i; i = (_QWORD *)*i )
          {
            v35 = (const struct Dr::DrawingShapeViewElement ***)i[1];
            if ( v35 == v3
              || v35[1] != (const struct Dr::DrawingShapeViewElement **)v9
              && !(unsigned int)__std_type_info_compare(*v35 + 1, &qword_180E1FA20) )
            {
              v36 = v79;
              goto LABEL_47;
            }
          }
        }
        v36 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_47:
        if ( *(_DWORD *)v36 != 0x80000000 )
          _InterlockedIncrement((volatile signed __int32 *)v36);
        v89 = v36;
        v37 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v79 + 2);
        if ( v37 )
        {
          for ( j = (_QWORD *)(**v37)(v37); j; j = (_QWORD *)*j )
          {
            v39 = j[1];
            if ( (const struct Dr::InkViewElement ***)v39 == &Ofc::TypeInfoImpl<Dr::InkViewElement const *>::c_typeInfo
              || *(struct Dr::DrawingSelectionInfo **)(v39 + 8) != v9
              && !(unsigned int)__std_type_info_compare(*(_QWORD *)v39 + 8LL, &qword_180E201B8) )
            {
              v40 = v79;
              goto LABEL_58;
            }
          }
        }
        v40 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_58:
        if ( *(_DWORD *)v40 != 0x80000000 )
          _InterlockedIncrement((volatile signed __int32 *)v40);
        v96 = v40;
        v41 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v79 + 2);
        if ( v41 )
        {
          for ( k = (_QWORD *)(**v41)(v41); k; k = (_QWORD *)*k )
          {
            v43 = k[1];
            if ( (const struct Dr::InkActionsViewElement ***)v43 == &Ofc::TypeInfoImpl<Dr::InkActionsViewElement const *>::c_typeInfo
              || *(struct Dr::DrawingSelectionInfo **)(v43 + 8) != v9
              && !(unsigned int)__std_type_info_compare(*(_QWORD *)v43 + 8LL, &qword_180E20188) )
            {
              v44 = v79;
              goto LABEL_69;
            }
          }
        }
        v44 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_69:
        if ( *(_DWORD *)v44 != 0x80000000 )
          _InterlockedIncrement((volatile signed __int32 *)v44);
        v95 = v44;
        v45 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v79 + 2);
        if ( v45 )
        {
          for ( m = (_QWORD *)(**v45)(v45); m; m = (_QWORD *)*m )
          {
            v47 = m[1];
            if ( (const struct Dr::DrawingGroupViewElement ***)v47 == &Ofc::TypeInfoImpl<Dr::DrawingGroupViewElement const *>::c_typeInfo
              || *(struct Dr::DrawingSelectionInfo **)(v47 + 8) != v9
              && !(unsigned int)__std_type_info_compare(*(_QWORD *)v47 + 8LL, &qword_180E20250) )
            {
              v48 = v79;
              goto LABEL_80;
            }
          }
        }
        v48 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_80:
        if ( *(_DWORD *)v48 != 0x80000000 )
          _InterlockedIncrement((volatile signed __int32 *)v48);
        v94 = v48;
        v49 = (__int64 (__fastcall ***)(_QWORD))*((_QWORD *)v79 + 2);
        if ( v49 )
        {
          for ( n = (_QWORD *)(**v49)(v49); n; n = (_QWORD *)*n )
          {
            v51 = n[1];
            if ( (const struct Art::ACompatE2oShapeViewElement ***)v51 == &Ofc::TypeInfoImpl<Art::ACompatE2oShapeViewElement const *>::c_typeInfo
              || *(struct Dr::DrawingSelectionInfo **)(v51 + 8) != v9
              && !(unsigned int)__std_type_info_compare(*(_QWORD *)v51 + 8LL, &qword_180E201E8) )
            {
              v52 = v79;
              goto LABEL_91;
            }
          }
        }
        v52 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
LABEL_91:
        if ( *(_DWORD *)v52 != 0x80000000 )
          _InterlockedIncrement((volatile signed __int32 *)v52);
        v90 = v52;
        if ( *((_QWORD *)v89 + 2) )
        {
          v56 = v2;
          v57 = Ofc::CProxyPtrImpl::GetChecked(v89);
          while ( v56 != (struct Ofc::CProxyPtrImpl *)((char *)v2 + 8 * v11) )
          {
            if ( *(_QWORD *)(*(_QWORD *)v56 + 16LL) == *(_QWORD *)(v57[54] + 16LL) )
            {
              if ( v81 >= (v82 & 0x7FFFFFFF) && v80 && v80 <= &v79 && &v79 < &v80[v81] )
              {
                v65 = v79;
                if ( *((_DWORD *)v79 + 1) != 0x80000000 )
                  _InterlockedIncrement((volatile signed __int32 *)v79 + 1);
                v92 = v65;
                v66 = (struct Ofc::CProxyPtrImpl **)Ofc::CArrayImpl::NewTop<Ofc::TWeakPtr<Dr::DrawingElement const>>(&v80);
                Ofc::CProxyPtrImpl::WeakMoveAssign(v66, &v92);
                Ofc::CProxyPtrImpl::DtorWeakRelease(&v92);
              }
              else
              {
                v64 = (struct Ofc::CProxyPtrImpl **)Ofc::CArrayImpl::NewTop<Ofc::TWeakPtr<Dr::DrawingElement const>>(&v80);
                Ofc::CProxyPtrImpl::WeakAssign(v64, v79);
              }
              goto LABEL_110;
            }
            v56 = (struct Ofc::CProxyPtrImpl *)((char *)v56 + 8);
          }
        }
        if ( *((_QWORD *)v94 + 2) )
        {
          v58 = *((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v94) + 53);
          if ( *(_DWORD *)(v58 + 4) != 0x80000000 )
            _InterlockedIncrement((volatile signed __int32 *)(v58 + 4));
          v97 = (struct Ofc::CProxyPtrImpl *)v58;
          v4 |= 1u;
          for ( ii = v2;
                ii != (struct Ofc::CProxyPtrImpl *)((char *)v2 + 8 * v11);
                ii = (struct Ofc::CProxyPtrImpl *)((char *)ii + 8) )
          {
            if ( *(_QWORD *)(*(_QWORD *)ii + 16LL) == *(_QWORD *)(v58 + 16) )
            {
              v53 = 1;
              goto LABEL_96;
            }
          }
        }
        v53 = 0;
LABEL_96:
        if ( (v4 & 1) != 0 )
        {
          v4 &= ~1u;
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v97);
        }
        if ( v53 )
          goto LABEL_138;
        v54 = 0;
        if ( *((_QWORD *)v95 + 2) )
        {
          v77 = Ofc::CProxyPtrImpl::GetChecked(v95);
          InkDrawingElement = Dr::InkActionsViewElement::GetInkDrawingElement(v77, &v98);
          v4 |= 2u;
          if ( (unsigned __int8)Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>>::FContains<Ofc::TWeakPtr<Dr::InkDrawingElement>>(
                                  &Src,
                                  InkDrawingElement) )
            v54 = 1;
        }
        if ( (v4 & 2) != 0 )
        {
          v4 &= ~2u;
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v98);
        }
        if ( v54 )
          goto LABEL_138;
        if ( *((_QWORD *)v96 + 2) )
        {
          v67 = *((_QWORD *)Ofc::CProxyPtrImpl::GetChecked(v96) + 31);
          if ( *(_DWORD *)(v67 + 4) != 0x80000000 )
            _InterlockedIncrement((volatile signed __int32 *)(v67 + 4));
          v99 = (struct Ofc::CProxyPtrImpl *)v67;
          v4 |= 4u;
          for ( jj = v2;
                jj != (struct Ofc::CProxyPtrImpl *)((char *)v2 + 8 * v11);
                jj = (struct Ofc::CProxyPtrImpl *)((char *)jj + 8) )
          {
            if ( *(_QWORD *)(*(_QWORD *)jj + 16LL) == *(_QWORD *)(v67 + 16) )
            {
              v55 = 1;
              goto LABEL_106;
            }
          }
        }
        v55 = 0;
LABEL_106:
        if ( (v4 & 4) != 0 )
        {
          v4 &= ~4u;
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v99);
        }
        if ( v55 )
        {
LABEL_138:
          Ofc::TArray<Ofc::TWeakPtr<Dr::MovieDrawingElement>>::Add<Ofc::TReferringPtr<Dr::MovieDrawingElement>>(
            &v80,
            &v79);
        }
        else if ( *((_QWORD *)v90 + 2) )
        {
          v69 = Ofc::CProxyPtrImpl::GetChecked(v90);
          v70 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(void *, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)v69 + 1240LL))(
                                                v69,
                                                &v100);
          v93 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v70);
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v100);
          if ( *((_QWORD *)v93 + 2) )
          {
            v71 = Ofc::CProxyPtrImpl::GetChecked(v93);
            if ( (*(unsigned __int8 (__fastcall **)(void *))(*(_QWORD *)v71 + 88LL))(v71) )
            {
              v72 = Ofc::CProxyPtrImpl::GetChecked(v90);
              v73 = (*(__int64 (__fastcall **)(void *, struct Ofc::CProxyPtrImpl **))(*(_QWORD *)v72 + 1240LL))(
                      v72,
                      &v101);
              v4 |= 8u;
              v74 = *((_QWORD *)v1 + 2);
              v75 = v74 + 8LL * *((unsigned int *)v1 + 6);
              while ( v74 != v75 )
              {
                if ( *(_QWORD *)(*(_QWORD *)v74 + 16LL) == *(_QWORD *)(*(_QWORD *)v73 + 16LL) )
                {
                  v76 = 1;
                  goto LABEL_154;
                }
                v74 += 8;
              }
            }
          }
          v76 = 0;
LABEL_154:
          if ( (v4 & 8) != 0 )
          {
            v4 &= ~8u;
            Ofc::CProxyPtrImpl::DtorWeakRelease(&v101);
          }
          if ( v76 )
            Ofc::TArray<Ofc::TWeakPtr<Dr::MovieDrawingElement>>::Add<Ofc::TReferringPtr<Dr::MovieDrawingElement>>(
              &v80,
              &v79);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v93);
        }
LABEL_110:
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v90);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v94);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v95);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v96);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v89);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v79);
        goto LABEL_33;
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v79);
    }
    else
    {
      MsoShipAssertTagProc(3737359);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v79);
    }
  }
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v104);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v103);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v107);
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v91);
  v61 = (Mso::Memory *)v86;
  v62 = (struct Ofc::CProxyPtrImpl **)((char *)v86 + 8 * v87);
  if ( v62 > v86 )
  {
    do
      Ofc::CProxyPtrImpl::DtorWeakRelease(--v62);
    while ( v62 > (struct Ofc::CProxyPtrImpl **)v61 );
  }
  if ( v61 )
    Mso::Memory::Free(v61, v60);
  for ( kk = (struct Ofc::CProxyPtrImpl **)((char *)v2 + 8 * v11);
        kk > (struct Ofc::CProxyPtrImpl **)v2;
        Ofc::CProxyPtrImpl::DtorWeakRelease(kk) )
  {
    --kk;
  }
  if ( v2 )
    Mso::Memory::Free(v2, v60);
  v3 = this;
LABEL_14:
  v16 = v3 + 12;
  v17 = (Mso::Memory *)v3[12];
  *v16 = v80;
  v18 = *((unsigned int *)v16 + 2);
  *((_DWORD *)v16 + 2) = v81;
  *((_DWORD *)v16 + 3) = (*((_DWORD *)v16 + 3) & 0x7FFFFFFF | v82 & 0x80000000)
                       ^ ((*((_DWORD *)v16 + 3) & 0x80000000 | v82 & 0x7FFFFFFF)
                        ^ (*((_DWORD *)v16 + 3) & 0x7FFFFFFF | v82 & 0x80000000))
                       & 0x7FFFFFFF;
  Ofc::CProxyPtrImpl::DtorWeakRelease(&v108);
  for ( mm = (struct Ofc::CProxyPtrImpl **)((char *)v17 + 8 * v18);
        mm > (struct Ofc::CProxyPtrImpl **)v17;
        Ofc::CProxyPtrImpl::DtorWeakRelease(mm) )
  {
    --mm;
  }
  if ( v17 )
    Mso::Memory::Free(v17, v19);
  return v16;
}

```

## disassembly

```asm
0x1802209b0  mov     [rsp-8+arg_0], rcx
0x1802209b5  push    rbp
0x1802209b6  push    rbx
0x1802209b7  push    rsi
0x1802209b8  push    rdi
0x1802209b9  push    r12
0x1802209bb  push    r13
0x1802209bd  push    r14
0x1802209bf  push    r15
0x1802209c1  lea     rbp, [rsp-1Fh]
0x1802209c6  sub     rsp, 0E8h
0x1802209cd  mov     rdi, rcx
0x1802209d0  xor     r15d, r15d
0x1802209d3  mov     dword ptr [rbp+57h+arg_8], r15d
0x1802209d7  mov     [rsp+120h+var_F8], r15
0x1802209dc  mov     [rsp+120h+var_F0], r15d
0x1802209e1  mov     [rsp+120h+var_EC], 80000000h
0x1802209e9  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x1802209f0  mov     [rbp+57h+arg_10], rax
0x1802209f4  mov     rcx, [rcx+3A8h]; struct Ofc::CProxyPtrImpl *
0x1802209fb  cmp     [rcx+10h], r15
0x1802209ff  jz      short loc_180220A3F
0x180220a01  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180220a06  mov     [rbp+57h+arg_8], rax
0x180220a0a  mov     rcx, rax; this
0x180220a0d  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180220a12  mov     rdx, rax
0x180220a15  mov     rcx, [rax]
0x180220a18  mov     rax, [rcx+78h]
0x180220a1c  mov     rcx, rdx
0x180220a1f  call    cs:__guard_dispatch_icall_fptr
0x180220a25  mov     rdx, [rax]; struct Ofc::CProxyPtrImpl *
0x180220a28  lea     rcx, [rbp+57h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180220a2c  call    ?WeakAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x180220a31  nop
0x180220a32  lea     rcx, [rbp+57h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180220a36  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180220a3b  mov     rax, [rbp+57h+arg_10]
0x180220a3f  cmp     qword ptr [rax+10h], 0
0x180220a44  jz      loc_180220AFB
0x180220a4a  mov     [rsp+120h+Src], r15
0x180220a4f  mov     [rsp+120h+var_E0], r15d
0x180220a54  mov     [rsp+120h+var_DC], 80000000h
0x180220a5c  mov     [rsp+120h+var_D8], r15
0x180220a61  mov     [rbp+57h+var_D0], r15d
0x180220a65  mov     [rbp+57h+var_CC], 80000000h
0x180220a6c  lea     r14, [rdi+80h]
0x180220a73  lea     rdx, [rsp+120h+Src]
0x180220a78  mov     rcx, r14
0x180220a7b  call    ?GetTopLevelSelectedElements@Dr@@YAXAEAVDrawingSelectionInfo@1@AEAV?$TArray@V?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@@Ofc@@@Z; Dr::GetTopLevelSelectedElements(Dr::DrawingSelectionInfo &,Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>> &)
0x180220a80  lea     rdx, [rsp+120h+var_D8]
0x180220a85  mov     rcx, r14
0x180220a88  call    ?GetDrilldownSelectedElements@Dr@@YAXAEAVDrawingSelectionInfo@1@AEAV?$TArray@V?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@@Ofc@@@Z; Dr::GetDrilldownSelectedElements(Dr::DrawingSelectionInfo &,Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>> &)
0x180220a8d  mov     ebx, [rbp+57h+var_D0]
0x180220a90  test    ebx, ebx
0x180220a92  jz      loc_1802213D9
0x180220a98  mov     edi, [rsp+120h+var_E0]
0x180220a9c  lea     r13d, [rbx+rdi]
0x180220aa0  cmp     r13d, edi
0x180220aa3  jb      loc_1802213EC
0x180220aa9  mov     ebx, [rsp+120h+var_DC]
0x180220aad  mov     eax, ebx
0x180220aaf  btr     eax, 1Fh
0x180220ab3  cmp     eax, r13d
0x180220ab6  jnb     loc_18022126C
0x180220abc  mov     [rbp+57h+arg_18], r15
0x180220ac0  mov     eax, r13d
0x180220ac3  shr     eax, 2
0x180220ac6  mov     edx, 8
0x180220acb  cmp     eax, edx
0x180220acd  cmova   edx, eax; unsigned __int64
0x180220ad0  mov     eax, edx
0x180220ad2  not     eax
0x180220ad4  mov     ecx, 0FFFFFFFFh
0x180220ad9  cmp     r13d, eax
0x180220adc  jbe     loc_180220B91
0x180220ae2  mov     eax, ecx
0x180220ae4  jmp     loc_180220B95
0x180220ae9  test    r12, r12
0x180220aec  jz      short loc_180220AF7
0x180220aee  mov     rcx, r12
0x180220af1  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180220af7  mov     rdi, [rbp+57h+arg_0]
0x180220afb  lea     rsi, [rdi+60h]
0x180220aff  mov     rdi, [rsi]
0x180220b02  mov     rax, [rsp+120h+var_F8]
0x180220b07  mov     [rsi], rax
0x180220b0a  mov     ebx, [rsi+8]
0x180220b0d  mov     eax, [rsp+120h+var_F0]
0x180220b11  mov     [rsi+8], eax
0x180220b14  mov     ecx, [rsi+0Ch]
0x180220b17  mov     r8d, [rsp+120h+var_EC]
0x180220b1c  mov     edx, r8d
0x180220b1f  btr     edx, 1Fh
0x180220b23  mov     eax, ecx
0x180220b25  and     eax, 80000000h
0x180220b2a  or      edx, eax
0x180220b2c  and     r8d, 80000000h
0x180220b33  btr     ecx, 1Fh
0x180220b37  or      r8d, ecx
0x180220b3a  mov     eax, r8d
0x180220b3d  xor     eax, edx
0x180220b3f  btr     eax, 1Fh
0x180220b43  xor     eax, r8d
0x180220b46  mov     [rsi+0Ch], eax
0x180220b49  lea     rcx, [rbp+57h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180220b4d  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180220b52  lea     rbx, [rdi+rbx*8]
0x180220b56  cmp     rbx, rdi
0x180220b59  jbe     short loc_180220B6C
0x180220b5b  sub     rbx, 8
0x180220b5f  mov     rcx, rbx; struct Ofc::CProxyPtrImpl **
0x180220b62  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180220b67  cmp     rbx, rdi
0x180220b6a  ja      short loc_180220B5B
0x180220b6c  test    rdi, rdi
0x180220b6f  jz      short loc_180220B7A
0x180220b71  mov     rcx, rdi
0x180220b74  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180220b7a  mov     rax, rsi
0x180220b7d  add     rsp, 0E8h
0x180220b84  pop     r15
0x180220b86  pop     r14
0x180220b88  pop     r13
0x180220b8a  pop     r12
0x180220b8c  pop     rdi
0x180220b8d  pop     rsi
0x180220b8e  pop     rbx
0x180220b8f  pop     rbp
0x180220b90  retn
0x180220b91  lea     eax, [rdx+r13]
0x180220b95  shl     rax, 3
0x180220b99  cmp     rax, rcx
0x180220b9c  cmovbe  ecx, eax; this
0x180220b9f  mov     esi, ecx
0x180220ba1  shr     esi, 3
0x180220ba4  cmp     esi, r13d
0x180220ba7  jb      loc_1802213CB
0x180220bad  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180220bb2  mov     r12, rax
0x180220bb5  mov     [rbp+57h+arg_18], rax
0x180220bb9  and     ebx, 80000000h
0x180220bbf  or      ebx, esi
0x180220bc1  mov     [rsp+120h+var_DC], ebx
0x180220bc5  mov     r8d, edi
0x180220bc8  mov     rdx, rax; void *
0x180220bcb  mov     rbx, [rsp+120h+Src]
0x180220bd0  mov     rcx, rbx; Src
0x180220bd3  call    ?Do@?$TMoveConstructRange@V?$TReferringPtr@UIInkDrawing@Art@@@Ofc@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do(uchar *,uchar *,ulong)
0x180220bd8  mov     [rsp+120h+Src], r12
0x180220bdd  test    rbx, rbx
0x180220be0  jz      short loc_180220BEB
0x180220be2  mov     rcx, rbx
0x180220be5  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180220beb  lea     edx, ds:0[rdi*8]
0x180220bf2  add     rdx, r12; void *
0x180220bf5  mov     r8d, [rbp+57h+var_D0]
0x180220bf9  mov     rbx, [rsp+120h+var_D8]
0x180220bfe  mov     rcx, rbx; Src
0x180220c01  call    ?Do@?$TMoveConstructRange@V?$TReferringPtr@UIInkDrawing@Art@@@Ofc@@$00@Ofc@@SAXPEAE0K@Z; Ofc::TMoveConstructRange<Ofc::TReferringPtr<Art::IInkDrawing>,1>::Do(uchar *,uchar *,ulong)
0x180220c06  mov     [rsp+120h+var_E0], r13d
0x180220c0b  test    rbx, rbx
0x180220c0e  jz      short loc_180220C19
0x180220c10  mov     rcx, rbx
0x180220c13  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180220c19  mov     [rsp+120h+var_D8], r15
0x180220c1e  and     [rbp+57h+var_CC], 80000000h
0x180220c25  mov     [rbp+57h+var_D0], r15d
0x180220c29  mov     rdi, [rbp+57h+arg_0]
0x180220c2d  lea     rdx, [rdi+108h]; struct Dr::GeneratedE2oSelectionInfo *
0x180220c34  mov     [rbp+57h+var_C8], rdx
0x180220c38  mov     rcx, r14; struct Dr::DrawingSelectionInfo *
0x180220c3b  call    ?GetE2oInfo@DrawingSelection@Dr@@KAXAEAVDrawingSelectionInfo@2@AEAVGeneratedE2oSelectionInfo@2@@Z; Dr::DrawingSelection::GetE2oInfo(Dr::DrawingSelectionInfo &,Dr::GeneratedE2oSelectionInfo &)
0x180220c40  mov     rcx, [rbp+57h+arg_10]; struct Ofc::CProxyPtrImpl *
0x180220c44  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180220c49  mov     [rbp+57h+arg_18], rax
0x180220c4d  mov     rcx, rax; this
0x180220c50  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180220c55  mov     rcx, [rax+0A8h]
0x180220c5c  mov     eax, [rcx+4]
0x180220c5f  cmp     eax, 80000000h
0x180220c64  jz      short loc_180220C6A
0x180220c66  lock inc dword ptr [rcx+4]
0x180220c6a  mov     [rbp+57h+var_B8], rcx
0x180220c6e  lea     rcx, [rbp+57h+arg_18]; struct Ofc::CProxyPtrImpl **
0x180220c72  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180220c77  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180220c7e  mov     [rbp+57h+arg_8], rax
0x180220c82  mov     [rbp+57h+var_60], 1
0x180220c89  mov     rcx, [rbp+57h+var_B8]
0x180220c8d  mov     eax, [rcx+4]
0x180220c90  cmp     eax, 80000000h
0x180220c95  jnz     loc_18022124F
0x180220c9b  mov     [rbp+57h+var_58], rcx
0x180220c9f  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180220ca6  mov     [rbp+57h+var_50], rax
0x180220caa  mov     [rbp+57h+var_48], 1
0x180220cae  mov     rdx, [rbp+57h+var_B8]; struct Ofc::CProxyPtrImpl *
0x180220cb2  lea     rcx, [rbp+57h+var_50]; struct Ofc::CProxyPtrImpl **
0x180220cb6  call    ?WeakAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x180220cbb  lea     r14, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x180220cc2  mov     rsi, [rbp+57h+var_C8]
0x180220cc6  lea     rdi, ?c_typeInfo@?$TypeInfoImpl@PEBVDrawingShapeViewElement@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::DrawingShapeViewElement const *>::c_typeInfo
0x180220ccd  mov     rax, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180220cd4  mov     [rbp+57h+arg_18], rax
0x180220cd8  xor     r8d, r8d
0x180220cdb  lea     rdx, [rbp+57h+arg_18]
0x180220cdf  lea     rcx, [rbp+57h+var_60]
0x180220ce3  call    ?DoNext@?$TNodeIterator@VViewElement@Art@@@Ofc@@AEAA_NAEAV?$TWeakPtr@V?$TTreeNode@VViewElement@Art@@@Ofc@@@2@_N@Z; Ofc::TNodeIterator<Art::ViewElement>::DoNext(Ofc::TWeakPtr<Ofc::TTreeNode<Art::ViewElement>> &,bool)
0x180220ce8  mov     rdx, [rbp+57h+arg_18]; struct Ofc::CProxyPtrImpl *
0x180220cec  lea     rcx, [rbp+57h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180220cf0  call    ?CheckedStrongAssign@CProxyPtrImpl@Ofc@@KAXPEAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAssign(Ofc::CProxyPtrImpl * *,Ofc::CProxyPtrImpl *)
0x180220cf5  mov     rax, [rbp+57h+arg_8]
0x180220cf9  mov     rbx, [rax+10h]
0x180220cfd  lea     rcx, [rbp+57h+arg_18]; struct Ofc::CProxyPtrImpl **
0x180220d01  call    ?DtorWeakRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorWeakRelease(Ofc::CProxyPtrImpl * &)
0x180220d06  test    rbx, rbx
0x180220d09  jz      loc_180221112
0x180220d0f  mov     rcx, [rbp+57h+arg_8]; this
0x180220d13  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180220d18  mov     rcx, [rax+48h]; this
0x180220d1c  mov     eax, [rcx]
0x180220d1e  cmp     eax, 80000000h
0x180220d23  jnz     loc_1802213FA
0x180220d29  mov     [rsp+120h+var_100], rcx
0x180220d2e  cmp     qword ptr [rcx+10h], 0
0x180220d33  jz      loc_1802212C3
0x180220d39  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180220d3e  mov     rdx, rax
0x180220d41  mov     rcx, [rax]
0x180220d44  mov     rax, [rcx+120h]
0x180220d4b  mov     rcx, rdx
0x180220d4e  call    cs:__guard_dispatch_icall_fptr
0x180220d54  test    al, al
0x180220d56  jnz     loc_1802210B6
0x180220d5c  mov     rax, [rsp+120h+var_100]
0x180220d61  mov     rcx, [rax+10h]
0x180220d65  test    rcx, rcx
0x180220d68  jz      short loc_180220DB8
0x180220d6a  mov     rax, [rcx]
0x180220d6d  mov     rax, [rax]
0x180220d70  call    cs:__guard_dispatch_icall_fptr
0x180220d76  mov     rbx, rax
0x180220d79  nop     dword ptr [rax+00000000h]
0x180220d80  test    rbx, rbx
0x180220d83  jz      short loc_180220DB8
0x180220d85  mov     rcx, [rbx+8]
0x180220d89  cmp     rcx, rdi
0x180220d8c  jz      short loc_180220DB1
0x180220d8e  cmp     [rcx+8], r14
0x180220d92  jnz     short loc_180220D99
0x180220d94  mov     rbx, [rbx]
0x180220d97  jmp     short loc_180220D80
0x180220d99  mov     rcx, [rcx]
0x180220d9c  add     rcx, 8
0x180220da0  lea     rdx, qword_180E1FA20
0x180220da7  call    cs:__imp___std_type_info_compare
0x180220dad  test    eax, eax
0x180220daf  jnz     short loc_180220D94
0x180220db1  mov     rcx, [rsp+120h+var_100]
0x180220db6  jmp     short loc_180220DBF
0x180220db8  mov     rcx, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180220dbf  mov     eax, [rcx]
0x180220dc1  cmp     eax, 80000000h
0x180220dc6  jnz     loc_180221402
0x180220dcc  mov     [rbp+57h+var_C8], rcx
0x180220dd0  mov     rax, [rsp+120h+var_100]
0x180220dd5  mov     rcx, [rax+10h]
0x180220dd9  test    rcx, rcx
0x180220ddc  jz      short loc_180220E2F
0x180220dde  mov     rax, [rcx]
0x180220de1  mov     rax, [rax]
0x180220de4  call    cs:__guard_dispatch_icall_fptr
0x180220dea  mov     rbx, rax
0x180220ded  nop     dword ptr [rax]
0x180220df0  test    rbx, rbx
0x180220df3  jz      short loc_180220E2F
0x180220df5  mov     rcx, [rbx+8]
0x180220df9  lea     rax, ?c_typeInfo@?$TypeInfoImpl@PEBVInkViewElement@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::InkViewElement const *>::c_typeInfo
0x180220e00  cmp     rcx, rax
0x180220e03  jz      short loc_180220E28
0x180220e05  cmp     [rcx+8], r14
0x180220e09  jnz     short loc_180220E10
0x180220e0b  mov     rbx, [rbx]
0x180220e0e  jmp     short loc_180220DF0
0x180220e10  mov     rcx, [rcx]
0x180220e13  add     rcx, 8
0x180220e17  lea     rdx, qword_180E201B8
0x180220e1e  call    cs:__imp___std_type_info_compare
0x180220e24  test    eax, eax
0x180220e26  jnz     short loc_180220E0B
0x180220e28  mov     rcx, [rsp+120h+var_100]
0x180220e2d  jmp     short loc_180220E36
0x180220e2f  mov     rcx, cs:?s_pProxyPtrSentinel@?1??GetSentinel@CProxyPtrImpl@Ofc@@KAAEBQEAV23@XZ@4QEAV23@EA; Ofc::CProxyPtrImpl * `Ofc::CProxyPtrImpl::GetSentinel(void)'::`2'::s_pProxyPtrSentinel
0x180220e36  mov     eax, [rcx]
0x180220e38  cmp     eax, 80000000h
0x180220e3d  jnz     loc_18022140A
0x180220e43  mov     [rbp+57h+var_90], rcx
0x180220e47  mov     rax, [rsp+120h+var_100]
0x180220e4c  mov     rcx, [rax+10h]
  ... truncated ...
```
