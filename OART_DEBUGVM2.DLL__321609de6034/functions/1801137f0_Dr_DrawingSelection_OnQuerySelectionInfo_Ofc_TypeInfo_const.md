# Dr::DrawingSelection::OnQuerySelectionInfo(Ofc::TypeInfo const &)

- ea: `0x1801137f0`
- end: `0x1801141a1`
- name: `?OnQuerySelectionInfo@DrawingSelection@Dr@@UEAAPEAXAEBVTypeInfo@Ofc@@@Z`
- size: `2481`
- prototype: `void *__fastcall(Dr::DrawingSelection *__hidden this, const struct Ofc::TypeInfo *)`
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x1806efc40`

## callees

- `0x18000e560`
- `0x18002a690`
- `0x1800726b8`
- `0x1800e8b40`
- `0x1800e8e20`
- `0x1801137f0`
- `0x18011c310`
- `0x18013c620`
- `0x1801d6880`
- `0x1801d77a0`
- `0x180279000`
- `0x180279010`
- `0x180279050`
- `0x18028f27c`
- `0x18028f6a0`
- `0x18029103c`
- `0x1802ecf60`
- `0x1806bc2a8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806bcb10`
- `0x1806d19bc`
- `0x1806d235c`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x180113a45`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113a6d`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113ab0`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113af3`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113b2c`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113b7b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113bab`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113be8`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113c52`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113c8f`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113cd2`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113cff`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113d3b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113d6b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113d9b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113dcb`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113e15`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113e45`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113e81`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113e9f`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113efe`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113f2f`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113f5b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113a45`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113a6d`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113ab0`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113af3`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113b2c`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113b7b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113bab`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113be8`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113c52`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113c8f`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113cd2`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113cff`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113d3b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113d6b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113d9b`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113dcb`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113e15`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113e45`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113e81`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113e9f`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113efe`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113f2f`
- `VCRUNTIME140!__std_type_info_compare` at `0x180113f5b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18011415f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18011415f`

## pseudocode

```c
char *__fastcall Dr::DrawingSelection::OnQuerySelectionInfo(Dr::DrawingSelection *this, void ****a2, unsigned int a3)
{
  int *v5; // rsi
  char *v7; // rsi
  unsigned int i; // ebx
  _DWORD *v9; // rbx
  _DWORD *v10; // rax
  __int64 v11; // rbx
  _DWORD *v12; // rbx
  _DWORD *v13; // rax
  __int64 v14; // rcx
  struct Ofc::CProxyPtrImpl *v15; // rcx
  struct Ofc::CProxyPtrImpl *v16; // rax
  struct Ofc::CProxyPtrImpl *v17; // rcx
  _QWORD *Checked; // rax
  struct Ofc::CProxyPtrImpl **v19; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r9
  struct Ofc::CProxyPtrImpl **v23; // rax
  unsigned int v24; // edx
  unsigned __int64 v25; // r9
  struct Ofc::CProxyPtrImpl **v26; // rax
  struct Ofc::CProxyPtrImpl *v27; // rax
  struct Ofc::CProxyPtrImpl *v28; // [rsp+20h] [rbp-28h] BYREF
  struct Ofc::CProxyPtrImpl *v29; // [rsp+28h] [rbp-20h] BYREF
  struct Ofc::CProxyPtrImpl *v30; // [rsp+58h] [rbp+10h] BYREF
  struct Ofc::CProxyPtrImpl *v31; // [rsp+60h] [rbp+18h] BYREF
  struct Ofc::CProxyPtrImpl *v32; // [rsp+68h] [rbp+20h] BYREF

  if ( a2 == &Ofc::TypeInfoImpl<Dr::DrawingSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14588) )
  {
    return (char *)this + 128;
  }
  if ( a2 == (void ****)&Ofc::TypeInfoImpl<Dr::TopLevelSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14528) )
  {
    Dr::GetTopLevelSelectedElements((char *)this + 128, (char *)this + 576);
    return (char *)this + 568;
  }
  if ( a2 == (void ****)&Ofc::TypeInfoImpl<Dr::DrilldownSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14558) )
  {
    Dr::GetDrilldownSelectedElements((char *)this + 128, (char *)this + 216);
    return (char *)this + 208;
  }
  if ( a2 == (void ****)&Ofc::TypeInfoImpl<Art::ViewElemSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E145F0) )
  {
    return (char *)(*(__int64 (__fastcall **)(Dr::DrawingSelection *))(*(_QWORD *)this + 80LL))(this);
  }
  if ( a2 == &Ofc::TypeInfoImpl<Art::E2oSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14630) )
  {
    v7 = (char *)this + 264;
    if ( *((_DWORD *)this + 72) )
    {
      Art::E2oSelectionInfo::ClearSelectionNoNotify((Dr::DrawingSelection *)((char *)this + 264));
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 264);
    }
    for ( i = 0; ; ++i )
    {
      if ( (signed int)i >= *((_DWORD *)this + 36) )
        return (char *)this + 264;
      if ( i >= *((_DWORD *)this + 36) )
        break;
      v31 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*(struct Ofc::CProxyPtrImpl **)(*((_QWORD *)this + 17) + 8LL * i));
      v14 = *((_QWORD *)v31 + 2);
      if ( v14 && (unsigned __int8)Ofc::CObject::FIsKindOf<Dr::E2oFrameDrawingElement const>(v14 + 8) )
        v15 = v31;
      else
        v15 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
      v16 = Ofc::CProxyPtrImpl::StrongAddRef(v15);
      v29 = v16;
      v17 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
      v28 = `Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
      if ( *((_QWORD *)v16 + 2) )
      {
        Checked = Ofc::CProxyPtrImpl::GetChecked(v16);
        v19 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(_QWORD *, struct Ofc::CProxyPtrImpl **))(Checked[45] + 40LL))(
                                              Checked + 45,
                                              &v32);
        Ofc::CProxyPtrImpl::WeakMoveAssign(&v28, v19);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v32);
        v17 = v28;
      }
      v20 = *((_QWORD *)v17 + 2);
      if ( v20 )
      {
        v21 = *((_QWORD *)this + 35);
        v22 = v21 + 8LL * *((unsigned int *)this + 72);
        while ( v21 != v22 )
        {
          if ( *(_QWORD *)(*(_QWORD *)v21 + 16LL) == v20 )
            goto LABEL_124;
          v21 += 8;
        }
        v24 = *((_DWORD *)this + 72);
        if ( v24 >= (*((_DWORD *)this + 73) & 0x7FFFFFFFu)
          && (v25 = *((_QWORD *)this + 35)) != 0
          && v25 <= (unsigned __int64)&v28
          && (unsigned __int64)&v28 < v25 + 8 * v24 )
        {
          v30 = Ofc::CProxyPtrImpl::WeakAddRef(v17);
          v26 = (struct Ofc::CProxyPtrImpl **)Ofc::CArrayImpl::NewTop<Ofc::TWeakPtr<Dr::DrawingElement const>>((char *)this + 280);
          Ofc::CProxyPtrImpl::WeakMoveAssign(v26, &v30);
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v30);
        }
        else
        {
          v23 = (struct Ofc::CProxyPtrImpl **)Ofc::CArrayImpl::NewTop<Ofc::TWeakPtr<Dr::DrawingElement const>>((char *)this + 280);
          Ofc::CProxyPtrImpl::WeakAssign(v23, v28);
        }
        (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 264);
      }
LABEL_124:
      Ofc::CProxyPtrImpl::DtorWeakRelease(&v28);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v29);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v31);
    }
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_132;
  }
  if ( a2 == (void ****)&Ofc::TypeInfoImpl<Art::EditPointsSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E144F0) )
  {
    return (char *)this + 232;
  }
  if ( a2 == &Ofc::TypeInfoImpl<Art::BlipFillPropsSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E144B8) )
  {
    Dr::DrawingSelection::GetBlipFillPropsInfo(
      (Dr::DrawingSelection *)((char *)this + 128),
      (Dr::DrawingSelection *)((char *)this + 32));
    return (char *)this + 32;
  }
  if ( a2 != &Ofc::TypeInfoImpl<Art::SVGBlipFillPropSelectionInfo>::c_typeInfo
    && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
     || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0B618)) )
  {
    if ( a2 == &Ofc::TypeInfoImpl<Art::PictureShapePropsSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0B5D8) )
    {
      Dr::DrawingSelection::GetPictureShapePropsInfo(
        (Dr::DrawingSelection *)((char *)this + 128),
        (Dr::DrawingSelection *)((char *)this + 64));
      return (char *)this + 64;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Art::SVGSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14480) )
    {
      Dr::DrawingSelection::GetSVGSelectionInfo(
        (Dr::DrawingSelection *)((char *)this + 128),
        (Dr::DrawingSelection *)((char *)this + 200));
      return (char *)this + 200;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Art::PictureMaskingSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0AF08) )
    {
      return (char *)this + 112;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Art::PictureBgRemovalSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0AE98) )
    {
      v11 = *((_QWORD *)this + 115);
      if ( v11 )
        return (char *)v11;
LABEL_132:
      v27 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::Throw::AllocateEx(
                                           (Mso::Memory::Throw *)0x10,
                                           (unsigned __int64)a2,
                                           a3);
      v30 = v27;
      if ( v27 )
        v11 = Art::PictureBgRemovalSelectionInfo::PictureBgRemovalSelectionInfo(
                v27,
                (Dr::DrawingSelection *)((char *)this + 112));
      else
        v11 = 0;
      *((_QWORD *)this + 115) = v11;
      return (char *)v11;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Dr::RemoteSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0AE38) )
    {
      return (char *)this + 592;
    }
    if ( a2 == (void ****)&Ofc::TypeInfoImpl<Dr::RemoteTextSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0AE00) )
    {
      return (char *)this + 656;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Dr::AnchorSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0ADD0) )
    {
      return (char *)this + 880;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Dr::InkStrokesSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0AED0) )
    {
      Dr::DrawingSelection::GetInkStrokesInfo((char *)this + 936, (char *)this + 128, (char *)this + 720);
      return (char *)this + 720;
    }
    if ( a2 == (void ****)&Ofc::TypeInfoImpl<Dr::UnreadChangesInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0AE68) )
    {
      return (char *)this + 808;
    }
    if ( a2 != (void ****)&Ofc::TypeInfoImpl<Art::ShapePropSelectionInfo>::c_typeInfo
      && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
       || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0BB28))
      && a2 != &Ofc::TypeInfoImpl<Dr::DrawingPropSelectionInfo>::c_typeInfo
      && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
       || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0AF78)) )
    {
      if ( a2 != &Ofc::TypeInfoImpl<Art::TextSelectionInfo>::c_typeInfo
        && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0BF50))
        && a2 != (void ****)&Ofc::TypeInfoImpl<Art::TextPropSelectionInfo>::c_typeInfo
        && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0BAF0)) )
      {
        v5 = (int *)((char *)this + 144);
      }
      else
      {
        v5 = (int *)((char *)this + 144);
        if ( *((int *)this + 36) > 0 )
          return (char *)Dr::DrawingSelection::GetTextSelectionInfo(this);
      }
      if ( a2 != &Ofc::TypeInfoImpl<Art::TextFrameSelectionInfo>::c_typeInfo
        && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E145B8))
        || *v5 <= 0 )
      {
        if ( a2 != &Ofc::TypeInfoImpl<Art::AltTextBarFeedbackUIStateInfo>::c_typeInfo
          && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
           || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E0AF40)) )
        {
          return 0;
        }
        else
        {
          return (char *)this + 896;
        }
      }
      else
      {
        return (char *)Dr::DrawingSelection::GetTextFrameSelectionInfo(this);
      }
    }
    else
    {
      v12 = (_DWORD *)*((_QWORD *)this + 114);
      if ( !v12 )
      {
        v13 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x18, (unsigned __int64)a2, a3);
        v12 = v13;
        if ( v13 )
        {
          v13[2] = 0x7FFFF;
          *(_QWORD *)v13 = &Dr::DrawingPropSelectionInfo::`vftable';
          *((_QWORD *)v13 + 2) = this;
        }
        else
        {
          v12 = 0;
        }
        *((_QWORD *)this + 114) = v12;
      }
      return (char *)v12;
    }
  }
  else
  {
    v9 = (_DWORD *)*((_QWORD *)this + 116);
    if ( !v9 )
    {
      v10 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x18, (unsigned __int64)a2, a3);
      v9 = v10;
      if ( v10 )
      {
        v10[2] = 521;
        *(_QWORD *)v10 = &Dr::SVGBlipFillPropSelectionInfo::`vftable';
        *((_QWORD *)v10 + 2) = this;
      }
      else
      {
        v9 = 0;
      }
      *((_QWORD *)this + 116) = v9;
    }
    return (char *)v9;
  }
}

```

## disassembly

```asm
0x1801137f0  mov     [rsp+arg_0], rbx
0x1801137f5  push    rbp
0x1801137f6  push    rsi
0x1801137f7  push    rdi
0x1801137f8  sub     rsp, 30h
0x1801137fc  mov     rbx, rdx
0x1801137ff  mov     rdi, rcx
0x180113802  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VDrawingSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::DrawingSelectionInfo>::c_typeInfo
0x180113809  cmp     rdx, rax
0x18011380c  jz      loc_180113A53
0x180113812  lea     rbp, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x180113819  cmp     [rdx+8], rbp
0x18011381d  jnz     loc_180113A37
0x180113823  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VTopLevelSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::TopLevelSelectionInfo>::c_typeInfo
0x18011382a  cmp     rbx, rax
0x18011382d  jz      loc_180113A7B
0x180113833  cmp     [rbx+8], rbp
0x180113837  jnz     loc_180113A5F
0x18011383d  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VDrilldownSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::DrilldownSelectionInfo>::c_typeInfo
0x180113844  cmp     rbx, rax
0x180113847  jz      loc_180113ABE
0x18011384d  cmp     [rbx+8], rbp
0x180113851  jnz     loc_180113AA2
0x180113857  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VViewElemSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::ViewElemSelectionInfo>::c_typeInfo
0x18011385e  cmp     rbx, rax
0x180113861  jz      loc_180113B01
0x180113867  cmp     [rbx+8], rbp
0x18011386b  jnz     loc_180113AE5
0x180113871  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VE2oSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::E2oSelectionInfo>::c_typeInfo
0x180113878  cmp     rbx, rax
0x18011387b  jz      loc_180113B3A
0x180113881  cmp     [rbx+8], rbp
0x180113885  jnz     loc_180113B1E
0x18011388b  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VEditPointsSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::EditPointsSelectionInfo>::c_typeInfo
0x180113892  cmp     rbx, rax
0x180113895  jz      loc_180113B89
0x18011389b  cmp     [rbx+8], rbp
0x18011389f  jnz     loc_180113B6D
0x1801138a5  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VBlipFillPropsSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::BlipFillPropsSelectionInfo>::c_typeInfo
0x1801138ac  cmp     rbx, rax
0x1801138af  jz      loc_180113BB9
0x1801138b5  cmp     [rbx+8], rbp
0x1801138b9  jnz     loc_180113B9D
0x1801138bf  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VSVGBlipFillPropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::SVGBlipFillPropSelectionInfo>::c_typeInfo
0x1801138c6  cmp     rbx, rax
0x1801138c9  jz      loc_180113BF6
0x1801138cf  cmp     [rbx+8], rbp
0x1801138d3  jnz     loc_180113BDA
0x1801138d9  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VPictureShapePropsSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::PictureShapePropsSelectionInfo>::c_typeInfo
0x1801138e0  cmp     rbx, rax
0x1801138e3  jz      loc_180113C60
0x1801138e9  cmp     [rbx+8], rbp
0x1801138ed  jnz     loc_180113C44
0x1801138f3  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VSVGSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::SVGSelectionInfo>::c_typeInfo
0x1801138fa  cmp     rbx, rax
0x1801138fd  jz      loc_180113C9D
0x180113903  cmp     [rbx+8], rbp
0x180113907  jnz     loc_180113C81
0x18011390d  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VPictureMaskingSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::PictureMaskingSelectionInfo>::c_typeInfo
0x180113914  cmp     rbx, rax
0x180113917  jz      loc_180113CE0
0x18011391d  cmp     [rbx+8], rbp
0x180113921  jnz     loc_180113CC4
0x180113927  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VPictureBgRemovalSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::PictureBgRemovalSelectionInfo>::c_typeInfo
0x18011392e  cmp     rbx, rax
0x180113931  jz      loc_180113D0D
0x180113937  cmp     [rbx+8], rbp
0x18011393b  jnz     loc_180113CF1
0x180113941  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VRemoteSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::RemoteSelectionInfo>::c_typeInfo
0x180113948  cmp     rbx, rax
0x18011394b  jz      loc_180113D49
0x180113951  cmp     [rbx+8], rbp
0x180113955  jnz     loc_180113D2D
0x18011395b  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VRemoteTextSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::RemoteTextSelectionInfo>::c_typeInfo
0x180113962  cmp     rbx, rax
0x180113965  jz      loc_180113D79
0x18011396b  cmp     [rbx+8], rbp
0x18011396f  jnz     loc_180113D5D
0x180113975  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VAnchorSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::AnchorSelectionInfo>::c_typeInfo
0x18011397c  cmp     rbx, rax
0x18011397f  jz      loc_180113DA9
0x180113985  cmp     [rbx+8], rbp
0x180113989  jnz     loc_180113D8D
0x18011398f  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VInkStrokesSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::InkStrokesSelectionInfo>::c_typeInfo
0x180113996  cmp     rbx, rax
0x180113999  jz      loc_180113DD9
0x18011399f  cmp     [rbx+8], rbp
0x1801139a3  jnz     loc_180113DBD
0x1801139a9  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VUnreadChangesInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::UnreadChangesInfo>::c_typeInfo
0x1801139b0  cmp     rbx, rax
0x1801139b3  jz      loc_180113E23
0x1801139b9  cmp     [rbx+8], rbp
0x1801139bd  jnz     loc_180113E07
0x1801139c3  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VShapePropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::ShapePropSelectionInfo>::c_typeInfo
0x1801139ca  cmp     rbx, rax
0x1801139cd  jz      loc_180113E53
0x1801139d3  cmp     [rbx+8], rbp
0x1801139d7  jnz     loc_180113E37
0x1801139dd  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VDrawingPropSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::DrawingPropSelectionInfo>::c_typeInfo
0x1801139e4  cmp     rbx, rax
0x1801139e7  jz      loc_180113E53
0x1801139ed  cmp     [rbx+8], rbp
0x1801139f1  jnz     loc_180113E73
0x1801139f7  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VTextSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::TextSelectionInfo>::c_typeInfo
0x1801139fe  cmp     rbx, rax
0x180113a01  jz      loc_180113EAD
0x180113a07  cmp     [rbx+8], rbp
0x180113a0b  jnz     loc_180113E91
0x180113a11  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VTextPropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::TextPropSelectionInfo>::c_typeInfo
0x180113a18  cmp     rbx, rax
0x180113a1b  jz      loc_180113EAD
0x180113a21  cmp     [rbx+8], rbp
0x180113a25  jnz     loc_180113F4D
0x180113a2b  lea     rsi, [rdi+90h]
0x180113a32  jmp     loc_180113EBD
0x180113a37  mov     rcx, [rdx]
0x180113a3a  add     rcx, 8
0x180113a3e  lea     rdx, qword_180E14588
0x180113a45  call    cs:__imp___std_type_info_compare
0x180113a4b  test    eax, eax
0x180113a4d  jnz     loc_180113823
0x180113a53  lea     rax, [rdi+80h]
0x180113a5a  jmp     loc_180113EE3
0x180113a5f  mov     rcx, [rbx]
0x180113a62  add     rcx, 8
0x180113a66  lea     rdx, qword_180E14528
0x180113a6d  call    cs:__imp___std_type_info_compare
0x180113a73  test    eax, eax
0x180113a75  jnz     loc_18011383D
0x180113a7b  lea     rdx, [rdi+240h]
0x180113a82  lea     rcx, [rdi+80h]
0x180113a89  call    ?GetTopLevelSelectedElements@Dr@@YAXAEAVDrawingSelectionInfo@1@AEAV?$TArray@V?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@@Ofc@@@Z; Dr::GetTopLevelSelectedElements(Dr::DrawingSelectionInfo &,Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>> &)
0x180113a8e  lea     rax, [rdi+238h]
0x180113a95  mov     rbx, [rsp+48h+arg_0]
0x180113a9a  add     rsp, 30h
0x180113a9e  pop     rdi
0x180113a9f  pop     rsi
0x180113aa0  pop     rbp
0x180113aa1  retn
0x180113aa2  mov     rcx, [rbx]
0x180113aa5  add     rcx, 8
0x180113aa9  lea     rdx, qword_180E14558
0x180113ab0  call    cs:__imp___std_type_info_compare
0x180113ab6  test    eax, eax
0x180113ab8  jnz     loc_180113857
0x180113abe  lea     rdx, [rdi+0D8h]
0x180113ac5  lea     rcx, [rdi+80h]
0x180113acc  call    ?GetDrilldownSelectedElements@Dr@@YAXAEAVDrawingSelectionInfo@1@AEAV?$TArray@V?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@@Ofc@@@Z; Dr::GetDrilldownSelectedElements(Dr::DrawingSelectionInfo &,Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>> &)
0x180113ad1  lea     rax, [rdi+0D0h]
0x180113ad8  mov     rbx, [rsp+48h+arg_0]
0x180113add  add     rsp, 30h
0x180113ae1  pop     rdi
0x180113ae2  pop     rsi
0x180113ae3  pop     rbp
0x180113ae4  retn
0x180113ae5  mov     rcx, [rbx]
0x180113ae8  add     rcx, 8
0x180113aec  lea     rdx, qword_180E145F0
0x180113af3  call    cs:__imp___std_type_info_compare
0x180113af9  test    eax, eax
0x180113afb  jnz     loc_180113871
0x180113b01  mov     rax, [rdi]
0x180113b04  mov     rcx, rdi
0x180113b07  mov     rax, [rax+50h]
0x180113b0b  mov     rbx, [rsp+48h+arg_0]
0x180113b10  add     rsp, 30h
0x180113b14  pop     rdi
0x180113b15  pop     rsi
0x180113b16  pop     rbp
0x180113b17  jmp     cs:__guard_dispatch_icall_fptr
0x180113b1e  mov     rcx, [rbx]
0x180113b21  add     rcx, 8
0x180113b25  lea     rdx, qword_180E14630
0x180113b2c  call    cs:__imp___std_type_info_compare
0x180113b32  test    eax, eax
0x180113b34  jnz     loc_18011388B
0x180113b3a  lea     rsi, [rdi+108h]
0x180113b41  cmp     dword ptr [rsi+18h], 0
0x180113b45  jnz     loc_180113FB9
0x180113b4b  xor     ebx, ebx
0x180113b4d  cmp     ebx, [rdi+90h]
0x180113b53  jl      loc_180113FD6
0x180113b59  lea     rax, [rdi+108h]
0x180113b60  mov     rbx, [rsp+48h+arg_0]
0x180113b65  add     rsp, 30h
0x180113b69  pop     rdi
0x180113b6a  pop     rsi
0x180113b6b  pop     rbp
0x180113b6c  retn
0x180113b6d  mov     rcx, [rbx]
0x180113b70  add     rcx, 8
0x180113b74  lea     rdx, qword_180E144F0
0x180113b7b  call    cs:__imp___std_type_info_compare
0x180113b81  test    eax, eax
0x180113b83  jnz     loc_1801138A5
0x180113b89  lea     rax, [rdi+0E8h]
0x180113b90  mov     rbx, [rsp+48h+arg_0]
0x180113b95  add     rsp, 30h
0x180113b99  pop     rdi
0x180113b9a  pop     rsi
0x180113b9b  pop     rbp
0x180113b9c  retn
0x180113b9d  mov     rcx, [rbx]
0x180113ba0  add     rcx, 8
0x180113ba4  lea     rdx, qword_180E144B8
0x180113bab  call    cs:__imp___std_type_info_compare
0x180113bb1  test    eax, eax
0x180113bb3  jnz     loc_1801138BF
0x180113bb9  lea     rcx, [rdi+80h]; struct Dr::DrawingSelectionInfo *
0x180113bc0  lea     rdx, [rdi+20h]; struct Art::BlipFillPropsSelectionInfo *
0x180113bc4  call    ?GetBlipFillPropsInfo@DrawingSelection@Dr@@SAXAEAVDrawingSelectionInfo@2@AEAVBlipFillPropsSelectionInfo@Art@@@Z; Dr::DrawingSelection::GetBlipFillPropsInfo(Dr::DrawingSelectionInfo &,Art::BlipFillPropsSelectionInfo &)
0x180113bc9  lea     rax, [rdi+20h]
0x180113bcd  mov     rbx, [rsp+48h+arg_0]
0x180113bd2  add     rsp, 30h
0x180113bd6  pop     rdi
0x180113bd7  pop     rsi
0x180113bd8  pop     rbp
0x180113bd9  retn
0x180113bda  mov     rcx, [rbx]
0x180113bdd  add     rcx, 8
0x180113be1  lea     rdx, qword_180E0B618
0x180113be8  call    cs:__imp___std_type_info_compare
0x180113bee  test    eax, eax
0x180113bf0  jnz     loc_1801138D9
0x180113bf6  mov     rbx, [rdi+3A0h]
0x180113bfd  test    rbx, rbx
0x180113c00  jnz     short loc_180113C34
0x180113c02  mov     ecx, 18h; this
0x180113c07  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180113c0c  mov     rbx, rax
0x180113c0f  test    rax, rax
0x180113c12  jz      loc_180114199
0x180113c18  mov     dword ptr [rax+8], 209h
0x180113c1f  lea     rax, ??_7SVGBlipFillPropSelectionInfo@Dr@@6B@; const Dr::SVGBlipFillPropSelectionInfo::`vftable'
0x180113c26  mov     [rbx], rax
0x180113c29  mov     [rbx+10h], rdi
0x180113c2d  mov     [rdi+3A0h], rbx
0x180113c34  mov     rax, rbx
0x180113c37  mov     rbx, [rsp+48h+arg_0]
0x180113c3c  add     rsp, 30h
0x180113c40  pop     rdi
0x180113c41  pop     rsi
0x180113c42  pop     rbp
0x180113c43  retn
0x180113c44  mov     rcx, [rbx]
0x180113c47  add     rcx, 8
0x180113c4b  lea     rdx, qword_180E0B5D8
0x180113c52  call    cs:__imp___std_type_info_compare
0x180113c58  test    eax, eax
0x180113c5a  jnz     loc_1801138F3
0x180113c60  lea     rcx, [rdi+80h]; struct Dr::DrawingSelectionInfo *
0x180113c67  lea     rdx, [rdi+40h]; struct Art::PictureShapePropsSelectionInfo *
0x180113c6b  call    ?GetPictureShapePropsInfo@DrawingSelection@Dr@@SAXAEAVDrawingSelectionInfo@2@AEAVPictureShapePropsSelectionInfo@Art@@@Z; Dr::DrawingSelection::GetPictureShapePropsInfo(Dr::DrawingSelectionInfo &,Art::PictureShapePropsSelectionInfo &)
0x180113c70  lea     rax, [rdi+40h]
0x180113c74  mov     rbx, [rsp+48h+arg_0]
0x180113c79  add     rsp, 30h
0x180113c7d  pop     rdi
0x180113c7e  pop     rsi
0x180113c7f  pop     rbp
0x180113c80  retn
0x180113c81  mov     rcx, [rbx]
0x180113c84  add     rcx, 8
0x180113c88  lea     rdx, qword_180E14480
0x180113c8f  call    cs:__imp___std_type_info_compare
0x180113c95  test    eax, eax
0x180113c97  jnz     loc_18011390D
0x180113c9d  lea     rcx, [rdi+80h]; struct Dr::DrawingSelectionInfo *
0x180113ca4  lea     rdx, [rdi+0C8h]; struct Art::SVGSelectionInfo *
0x180113cab  call    ?GetSVGSelectionInfo@DrawingSelection@Dr@@SAXAEAVDrawingSelectionInfo@2@AEAVSVGSelectionInfo@Art@@@Z; Dr::DrawingSelection::GetSVGSelectionInfo(Dr::DrawingSelectionInfo &,Art::SVGSelectionInfo &)
0x180113cb0  lea     rax, [rdi+0C8h]
0x180113cb7  mov     rbx, [rsp+48h+arg_0]
0x180113cbc  add     rsp, 30h
0x180113cc0  pop     rdi
0x180113cc1  pop     rsi
0x180113cc2  pop     rbp
0x180113cc3  retn
0x180113cc4  mov     rcx, [rbx]
0x180113cc7  add     rcx, 8
0x180113ccb  lea     rdx, qword_180E0AF08
0x180113cd2  call    cs:__imp___std_type_info_compare
0x180113cd8  test    eax, eax
0x180113cda  jnz     loc_180113927
0x180113ce0  lea     rax, [rdi+70h]
0x180113ce4  mov     rbx, [rsp+48h+arg_0]
0x180113ce9  add     rsp, 30h
0x180113ced  pop     rdi
0x180113cee  pop     rsi
0x180113cef  pop     rbp
0x180113cf0  retn
0x180113cf1  mov     rcx, [rbx]
0x180113cf4  add     rcx, 8
0x180113cf8  lea     rdx, qword_180E0AE98
0x180113cff  call    cs:__imp___std_type_info_compare
0x180113d05  test    eax, eax
0x180113d07  jnz     loc_180113941
0x180113d0d  mov     rbx, [rdi+398h]
0x180113d14  test    rbx, rbx
0x180113d17  jz      loc_180114166
0x180113d1d  mov     rax, rbx
0x180113d20  mov     rbx, [rsp+48h+arg_0]
  ... truncated ...
```
