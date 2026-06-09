# Dr::DrawingSelection::OnQuerySelectionInfo(Ofc::TypeInfo const &)

- ea: `0x18006b1a0`
- end: `0x18006bb60`
- name: `?OnQuerySelectionInfo@DrawingSelection@Dr@@UEAAPEAXAEBVTypeInfo@Ofc@@@Z`
- size: `2496`
- prototype: `void *__fastcall(Dr::DrawingSelection *__hidden this, const struct Ofc::TypeInfo *)`
- caller_count: `1`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x1806dcdb0`

## callees

- `0x180001504`
- `0x180001810`
- `0x180001c40`
- `0x180011280`
- `0x1800458fc`
- `0x1800659a0`
- `0x18006b1a0`
- `0x18006cf00`
- `0x180071720`
- `0x1800cb158`
- `0x1800cbe10`
- `0x1802258f4`
- `0x1802715dc`
- `0x18032baa8`
- `0x180352cd0`
- `0x18062e440`
- `0x1806a5054`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806a5c90`
- `0x1806bd790`

## import_xrefs

- `VCRUNTIME140!__std_type_info_compare` at `0x18006b3f4`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b41c`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b45d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b49e`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b4d5`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b57b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b5a9`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b5e4`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b64c`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b687`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b6c8`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b6f3`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b72d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b75b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b789`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b7b7`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b7ff`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b82d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b867`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b885`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b8e2`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b911`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b93b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b3f4`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b41c`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b45d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b49e`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b4d5`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b57b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b5a9`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b5e4`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b64c`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b687`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b6c8`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b6f3`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b72d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b75b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b789`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b7b7`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b7ff`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b82d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b867`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b885`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b8e2`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b911`
- `VCRUNTIME140!__std_type_info_compare` at `0x18006b93b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006bb0c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18006bb0c`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b52b`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18006b52b`

## pseudocode

```c
char *__fastcall Dr::DrawingSelection::OnQuerySelectionInfo(Dr::DrawingSelection *this, void ****a2, unsigned int a3)
{
  int *v5; // rsi
  char *v7; // rsi
  __int64 v8; // rax
  unsigned int v9; // ebx
  __int64 v10; // r14
  __int64 i; // rbp
  void *v12; // rdx
  Mso::Memory *v13; // rcx
  _DWORD *v14; // rbx
  _DWORD *v15; // rax
  __int64 v16; // rbx
  _DWORD *v17; // rbx
  _DWORD *v18; // rax
  volatile signed __int32 **v19; // rax
  volatile signed __int32 *v20; // rcx
  struct Ofc::CProxyPtrImpl *v21; // r8
  _QWORD *Checked; // rax
  struct Ofc::CProxyPtrImpl **v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r9
  struct Ofc::CProxyPtrImpl **v27; // rax
  unsigned int v28; // ecx
  unsigned __int64 v29; // r9
  struct Ofc::CProxyPtrImpl **v30; // rax
  struct Ofc::CProxyPtrImpl *v31; // rax
  struct Ofc::CProxyPtrImpl *v32; // [rsp+20h] [rbp-38h] BYREF
  struct Ofc::CProxyPtrImpl *v33; // [rsp+28h] [rbp-30h] BYREF
  struct Ofc::CProxyPtrImpl *v34; // [rsp+68h] [rbp+10h] BYREF
  struct Ofc::CProxyPtrImpl *v35; // [rsp+70h] [rbp+18h] BYREF
  struct Ofc::CProxyPtrImpl *v36; // [rsp+78h] [rbp+20h] BYREF

  if ( a2 == &Ofc::TypeInfoImpl<Dr::DrawingSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E145F8) )
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
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E145C8) )
  {
    Dr::GetDrilldownSelectedElements((char *)this + 128, (char *)this + 216);
    return (char *)this + 208;
  }
  if ( a2 == (void ****)&Ofc::TypeInfoImpl<Art::ViewElemSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14628) )
  {
    return (char *)(*(__int64 (__fastcall **)(Dr::DrawingSelection *))(*(_QWORD *)this + 80LL))(this);
  }
  if ( a2 == &Ofc::TypeInfoImpl<Art::E2oSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E146A0) )
  {
    v7 = (char *)this + 264;
    v8 = *((unsigned int *)this + 72);
    v9 = 0;
    if ( (_DWORD)v8 )
    {
      if ( !*((_BYTE *)this + 296) )
      {
        v10 = *((_QWORD *)this + 35);
        for ( i = v10 + 8 * v8; v10 != i; v10 += 8 )
          sub_1800CBE10(v10);
      }
      Ofc::TDestructRange<Ofc::TWeakPtr<Dr::ConnectorDrawingElement const>,0>::Do(
        *((unsigned __int8 **)this + 35),
        *((_DWORD *)this + 72));
      v13 = (Mso::Memory *)*((_QWORD *)this + 35);
      if ( v13 )
        Mso::Memory::Free(v13, v12);
      *((_QWORD *)this + 35) = 0;
      *((_DWORD *)this + 73) &= 0x80000000;
      *((_DWORD *)this + 72) = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 264);
    }
    while ( 1 )
    {
      if ( (signed int)v9 >= *((_DWORD *)this + 36) )
        return (char *)this + 264;
      if ( v9 >= *((_DWORD *)this + 36) )
        break;
      v35 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*(struct Ofc::CProxyPtrImpl **)(*((_QWORD *)this + 17) + 8LL * v9));
      v19 = (volatile signed __int32 **)Ofc::runtime_cast<Dr::E2oFrameDrawingElement,Dr::DrawingElement>(&v35);
      v20 = *v19;
      if ( **v19 != 0x80000000 )
        _InterlockedIncrement(v20);
      v33 = (struct Ofc::CProxyPtrImpl *)v20;
      v21 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
      v32 = (struct Ofc::CProxyPtrImpl *)`Ofc::CProxyPtrImpl::GetSentinel'::`2'::s_pProxyPtrSentinel;
      if ( *((_QWORD *)v20 + 2) )
      {
        Checked = Ofc::CProxyPtrImpl::GetChecked((Ofc::CProxyPtrImpl *)v20);
        v23 = (struct Ofc::CProxyPtrImpl **)(*(__int64 (__fastcall **)(_QWORD *, struct Ofc::CProxyPtrImpl **))(Checked[45] + 40LL))(
                                              Checked + 45,
                                              &v36);
        Ofc::CProxyPtrImpl::WeakMoveAssign(&v32, v23);
        Ofc::CProxyPtrImpl::DtorWeakRelease(&v36);
        v21 = v32;
      }
      v24 = *((_QWORD *)v21 + 2);
      if ( v24 )
      {
        v25 = *((_QWORD *)this + 35);
        v26 = v25 + 8LL * *((unsigned int *)this + 72);
        while ( v25 != v26 )
        {
          if ( *(_QWORD *)(*(_QWORD *)v25 + 16LL) == v24 )
            goto LABEL_127;
          v25 += 8;
        }
        v28 = *((_DWORD *)this + 72);
        if ( v28 >= (*((_DWORD *)this + 73) & 0x7FFFFFFFu)
          && (v29 = *((_QWORD *)this + 35)) != 0
          && v29 <= (unsigned __int64)&v32
          && (unsigned __int64)&v32 < v29 + 8 * v28 )
        {
          if ( *((_DWORD *)v21 + 1) != 0x80000000 )
            _InterlockedIncrement((volatile signed __int32 *)v21 + 1);
          v34 = v21;
          v30 = (struct Ofc::CProxyPtrImpl **)Ofc::CArrayImpl::NewTop<Ofc::TWeakPtr<Dr::DrawingElement const>>((char *)this + 280);
          Ofc::CProxyPtrImpl::WeakMoveAssign(v30, &v34);
          Ofc::CProxyPtrImpl::DtorWeakRelease(&v34);
        }
        else
        {
          v27 = (struct Ofc::CProxyPtrImpl **)Ofc::CArrayImpl::NewTop<Ofc::TWeakPtr<Dr::DrawingElement const>>((char *)this + 280);
          Ofc::CProxyPtrImpl::WeakAssign(v27, v32);
        }
        (*(void (__fastcall **)(char *))(*(_QWORD *)v7 + 8LL))((char *)this + 264);
      }
LABEL_127:
      Ofc::CProxyPtrImpl::DtorWeakRelease(&v32);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v33);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v35);
      ++v9;
    }
    CrashWithRecovery(0x1E892496u, 0);
    goto LABEL_136;
  }
  if ( a2 == (void ****)&Ofc::TypeInfoImpl<Art::EditPointsSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14558) )
  {
    return (char *)this + 232;
  }
  if ( a2 == &Ofc::TypeInfoImpl<Art::BlipFillPropsSelectionInfo>::c_typeInfo
    || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E144B0) )
  {
    Dr::DrawingSelection::GetBlipFillPropsInfo(
      (Dr::DrawingSelection *)((char *)this + 128),
      (Dr::DrawingSelection *)((char *)this + 32));
    return (char *)this + 32;
  }
  if ( a2 != &Ofc::TypeInfoImpl<Art::SVGBlipFillPropSelectionInfo>::c_typeInfo
    && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
     || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14590)) )
  {
    if ( a2 == &Ofc::TypeInfoImpl<Art::PictureShapePropsSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E144E8) )
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
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14418) )
    {
      return (char *)this + 112;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Art::PictureBgRemovalSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14310) )
    {
      v16 = *((_QWORD *)this + 115);
      if ( v16 )
        return (char *)v16;
LABEL_136:
      v31 = (struct Ofc::CProxyPtrImpl *)Mso::Memory::Throw::AllocateEx(
                                           (Mso::Memory::Throw *)0x10,
                                           (unsigned __int64)a2,
                                           a3);
      v34 = v31;
      if ( v31 )
        v16 = Art::PictureBgRemovalSelectionInfo::PictureBgRemovalSelectionInfo(
                v31,
                (Dr::DrawingSelection *)((char *)this + 112));
      else
        v16 = 0;
      *((_QWORD *)this + 115) = v16;
      return (char *)v16;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Dr::RemoteSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14450) )
    {
      return (char *)this + 592;
    }
    if ( a2 == (void ****)&Ofc::TypeInfoImpl<Dr::RemoteTextSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E143E0) )
    {
      return (char *)this + 656;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Dr::AnchorSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E143B0) )
    {
      return (char *)this + 880;
    }
    if ( a2 == &Ofc::TypeInfoImpl<Dr::InkStrokesSelectionInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14378) )
    {
      Dr::DrawingSelection::GetInkStrokesInfo((char *)this + 936, (char *)this + 128, (char *)this + 720);
      return (char *)this + 720;
    }
    if ( a2 == (void ****)&Ofc::TypeInfoImpl<Dr::UnreadChangesInfo>::c_typeInfo
      || a2[1] != (void ***)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14348) )
    {
      return (char *)this + 808;
    }
    if ( a2 != (void ****)&Ofc::TypeInfoImpl<Art::ShapePropSelectionInfo>::c_typeInfo
      && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
       || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E10280))
      && a2 != &Ofc::TypeInfoImpl<Dr::DrawingPropSelectionInfo>::c_typeInfo
      && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
       || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E102E8)) )
    {
      if ( a2 != &Ofc::TypeInfoImpl<Art::TextSelectionInfo>::c_typeInfo
        && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E102B8))
        && a2 != (void ****)&Ofc::TypeInfoImpl<Art::TextPropSelectionInfo>::c_typeInfo
        && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E10590)) )
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
         || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E14658))
        || *v5 <= 0 )
      {
        if ( a2 != &Ofc::TypeInfoImpl<Art::AltTextBarFeedbackUIStateInfo>::c_typeInfo
          && (a2[1] == (void ***)&Ofc::TypeInfo::s_moduleTag
           || (unsigned int)__std_type_info_compare(*a2 + 1, &qword_180E10320)) )
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
      v17 = (_DWORD *)*((_QWORD *)this + 114);
      if ( !v17 )
      {
        v18 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x18, (unsigned __int64)a2, a3);
        v17 = v18;
        if ( v18 )
        {
          v18[2] = 0x7FFFF;
          *(_QWORD *)v18 = &Dr::DrawingPropSelectionInfo::`vftable';
          *((_QWORD *)v18 + 2) = this;
        }
        else
        {
          v17 = 0;
        }
        *((_QWORD *)this + 114) = v17;
      }
      return (char *)v17;
    }
  }
  else
  {
    v14 = (_DWORD *)*((_QWORD *)this + 116);
    if ( !v14 )
    {
      v15 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x18, (unsigned __int64)a2, a3);
      v14 = v15;
      if ( v15 )
      {
        v15[2] = 521;
        *(_QWORD *)v15 = &Dr::SVGBlipFillPropSelectionInfo::`vftable';
        *((_QWORD *)v15 + 2) = this;
      }
      else
      {
        v14 = 0;
      }
      *((_QWORD *)this + 116) = v14;
    }
    return (char *)v14;
  }
}

```

## disassembly

```asm
0x18006b1a0  push    rbx
0x18006b1a2  push    rbp
0x18006b1a3  push    rsi
0x18006b1a4  push    rdi
0x18006b1a5  push    r14
0x18006b1a7  sub     rsp, 30h
0x18006b1ab  mov     rbx, rdx
0x18006b1ae  mov     rdi, rcx
0x18006b1b1  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VDrawingSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::DrawingSelectionInfo>::c_typeInfo
0x18006b1b8  cmp     rdx, rax
0x18006b1bb  jz      loc_18006B402
0x18006b1c1  lea     rbp, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18006b1c8  cmp     [rdx+8], rbp
0x18006b1cc  jnz     loc_18006B3E6
0x18006b1d2  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VTopLevelSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::TopLevelSelectionInfo>::c_typeInfo
0x18006b1d9  cmp     rbx, rax
0x18006b1dc  jz      loc_18006B42A
0x18006b1e2  cmp     [rbx+8], rbp
0x18006b1e6  jnz     loc_18006B40E
0x18006b1ec  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VDrilldownSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::DrilldownSelectionInfo>::c_typeInfo
0x18006b1f3  cmp     rbx, rax
0x18006b1f6  jz      loc_18006B46B
0x18006b1fc  cmp     [rbx+8], rbp
0x18006b200  jnz     loc_18006B44F
0x18006b206  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VViewElemSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::ViewElemSelectionInfo>::c_typeInfo
0x18006b20d  cmp     rbx, rax
0x18006b210  jz      loc_18006B4AC
0x18006b216  cmp     [rbx+8], rbp
0x18006b21a  jnz     loc_18006B490
0x18006b220  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VE2oSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::E2oSelectionInfo>::c_typeInfo
0x18006b227  cmp     rbx, rax
0x18006b22a  jz      loc_18006B4E3
0x18006b230  cmp     [rbx+8], rbp
0x18006b234  jnz     loc_18006B4C7
0x18006b23a  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VEditPointsSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::EditPointsSelectionInfo>::c_typeInfo
0x18006b241  cmp     rbx, rax
0x18006b244  jz      loc_18006B589
0x18006b24a  cmp     [rbx+8], rbp
0x18006b24e  jnz     loc_18006B56D
0x18006b254  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VBlipFillPropsSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::BlipFillPropsSelectionInfo>::c_typeInfo
0x18006b25b  cmp     rbx, rax
0x18006b25e  jz      loc_18006B5B7
0x18006b264  cmp     [rbx+8], rbp
0x18006b268  jnz     loc_18006B59B
0x18006b26e  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VSVGBlipFillPropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::SVGBlipFillPropSelectionInfo>::c_typeInfo
0x18006b275  cmp     rbx, rax
0x18006b278  jz      loc_18006B5F2
0x18006b27e  cmp     [rbx+8], rbp
0x18006b282  jnz     loc_18006B5D6
0x18006b288  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VPictureShapePropsSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::PictureShapePropsSelectionInfo>::c_typeInfo
0x18006b28f  cmp     rbx, rax
0x18006b292  jz      loc_18006B65A
0x18006b298  cmp     [rbx+8], rbp
0x18006b29c  jnz     loc_18006B63E
0x18006b2a2  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VSVGSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::SVGSelectionInfo>::c_typeInfo
0x18006b2a9  cmp     rbx, rax
0x18006b2ac  jz      loc_18006B695
0x18006b2b2  cmp     [rbx+8], rbp
0x18006b2b6  jnz     loc_18006B679
0x18006b2bc  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VPictureMaskingSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::PictureMaskingSelectionInfo>::c_typeInfo
0x18006b2c3  cmp     rbx, rax
0x18006b2c6  jz      loc_18006B6D6
0x18006b2cc  cmp     [rbx+8], rbp
0x18006b2d0  jnz     loc_18006B6BA
0x18006b2d6  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VPictureBgRemovalSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::PictureBgRemovalSelectionInfo>::c_typeInfo
0x18006b2dd  cmp     rbx, rax
0x18006b2e0  jz      loc_18006B701
0x18006b2e6  cmp     [rbx+8], rbp
0x18006b2ea  jnz     loc_18006B6E5
0x18006b2f0  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VRemoteSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::RemoteSelectionInfo>::c_typeInfo
0x18006b2f7  cmp     rbx, rax
0x18006b2fa  jz      loc_18006B73B
0x18006b300  cmp     [rbx+8], rbp
0x18006b304  jnz     loc_18006B71F
0x18006b30a  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VRemoteTextSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::RemoteTextSelectionInfo>::c_typeInfo
0x18006b311  cmp     rbx, rax
0x18006b314  jz      loc_18006B769
0x18006b31a  cmp     [rbx+8], rbp
0x18006b31e  jnz     loc_18006B74D
0x18006b324  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VAnchorSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::AnchorSelectionInfo>::c_typeInfo
0x18006b32b  cmp     rbx, rax
0x18006b32e  jz      loc_18006B797
0x18006b334  cmp     [rbx+8], rbp
0x18006b338  jnz     loc_18006B77B
0x18006b33e  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VInkStrokesSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::InkStrokesSelectionInfo>::c_typeInfo
0x18006b345  cmp     rbx, rax
0x18006b348  jz      loc_18006B7C5
0x18006b34e  cmp     [rbx+8], rbp
0x18006b352  jnz     loc_18006B7A9
0x18006b358  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VUnreadChangesInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::UnreadChangesInfo>::c_typeInfo
0x18006b35f  cmp     rbx, rax
0x18006b362  jz      loc_18006B80D
0x18006b368  cmp     [rbx+8], rbp
0x18006b36c  jnz     loc_18006B7F1
0x18006b372  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VShapePropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::ShapePropSelectionInfo>::c_typeInfo
0x18006b379  cmp     rbx, rax
0x18006b37c  jz      loc_18006B83B
0x18006b382  cmp     [rbx+8], rbp
0x18006b386  jnz     loc_18006B81F
0x18006b38c  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VDrawingPropSelectionInfo@Dr@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Dr::DrawingPropSelectionInfo>::c_typeInfo
0x18006b393  cmp     rbx, rax
0x18006b396  jz      loc_18006B83B
0x18006b39c  cmp     [rbx+8], rbp
0x18006b3a0  jnz     loc_18006B859
0x18006b3a6  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VTextSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::TextSelectionInfo>::c_typeInfo
0x18006b3ad  cmp     rbx, rax
0x18006b3b0  jz      loc_18006B893
0x18006b3b6  cmp     [rbx+8], rbp
0x18006b3ba  jnz     loc_18006B877
0x18006b3c0  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VTextPropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::TextPropSelectionInfo>::c_typeInfo
0x18006b3c7  cmp     rbx, rax
0x18006b3ca  jz      loc_18006B893
0x18006b3d0  cmp     [rbx+8], rbp
0x18006b3d4  jnz     loc_18006B92D
0x18006b3da  lea     rsi, [rdi+90h]
0x18006b3e1  jmp     loc_18006B8A3
0x18006b3e6  mov     rcx, [rdx]
0x18006b3e9  add     rcx, 8
0x18006b3ed  lea     rdx, qword_180E145F8
0x18006b3f4  call    cs:__imp___std_type_info_compare
0x18006b3fa  test    eax, eax
0x18006b3fc  jnz     loc_18006B1D2
0x18006b402  lea     rax, [rdi+80h]
0x18006b409  jmp     loc_18006B8C9
0x18006b40e  mov     rcx, [rbx]
0x18006b411  add     rcx, 8
0x18006b415  lea     rdx, qword_180E14528
0x18006b41c  call    cs:__imp___std_type_info_compare
0x18006b422  test    eax, eax
0x18006b424  jnz     loc_18006B1EC
0x18006b42a  lea     rdx, [rdi+240h]
0x18006b431  lea     rcx, [rdi+80h]
0x18006b438  call    ?GetTopLevelSelectedElements@Dr@@YAXAEAVDrawingSelectionInfo@1@AEAV?$TArray@V?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@@Ofc@@@Z; Dr::GetTopLevelSelectedElements(Dr::DrawingSelectionInfo &,Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>> &)
0x18006b43d  lea     rax, [rdi+238h]
0x18006b444  add     rsp, 30h
0x18006b448  pop     r14
0x18006b44a  pop     rdi
0x18006b44b  pop     rsi
0x18006b44c  pop     rbp
0x18006b44d  pop     rbx
0x18006b44e  retn
0x18006b44f  mov     rcx, [rbx]
0x18006b452  add     rcx, 8
0x18006b456  lea     rdx, qword_180E145C8
0x18006b45d  call    cs:__imp___std_type_info_compare
0x18006b463  test    eax, eax
0x18006b465  jnz     loc_18006B206
0x18006b46b  lea     rdx, [rdi+0D8h]
0x18006b472  lea     rcx, [rdi+80h]
0x18006b479  call    ?GetDrilldownSelectedElements@Dr@@YAXAEAVDrawingSelectionInfo@1@AEAV?$TArray@V?$TWeakPtr@VDrawingElement@Dr@@@Ofc@@@Ofc@@@Z; Dr::GetDrilldownSelectedElements(Dr::DrawingSelectionInfo &,Ofc::TArray<Ofc::TWeakPtr<Dr::DrawingElement>> &)
0x18006b47e  lea     rax, [rdi+0D0h]
0x18006b485  add     rsp, 30h
0x18006b489  pop     r14
0x18006b48b  pop     rdi
0x18006b48c  pop     rsi
0x18006b48d  pop     rbp
0x18006b48e  pop     rbx
0x18006b48f  retn
0x18006b490  mov     rcx, [rbx]
0x18006b493  add     rcx, 8
0x18006b497  lea     rdx, qword_180E14628
0x18006b49e  call    cs:__imp___std_type_info_compare
0x18006b4a4  test    eax, eax
0x18006b4a6  jnz     loc_18006B220
0x18006b4ac  mov     rax, [rdi]
0x18006b4af  mov     rcx, rdi
0x18006b4b2  mov     rax, [rax+50h]
0x18006b4b6  add     rsp, 30h
0x18006b4ba  pop     r14
0x18006b4bc  pop     rdi
0x18006b4bd  pop     rsi
0x18006b4be  pop     rbp
0x18006b4bf  pop     rbx
0x18006b4c0  jmp     cs:__guard_dispatch_icall_fptr
0x18006b4c7  mov     rcx, [rbx]
0x18006b4ca  add     rcx, 8
0x18006b4ce  lea     rdx, qword_180E146A0
0x18006b4d5  call    cs:__imp___std_type_info_compare
0x18006b4db  test    eax, eax
0x18006b4dd  jnz     loc_18006B23A
0x18006b4e3  lea     rsi, [rdi+108h]
0x18006b4ea  mov     eax, [rsi+18h]
0x18006b4ed  xor     ebx, ebx
0x18006b4ef  test    eax, eax
0x18006b4f1  jz      short loc_18006B54F
0x18006b4f3  cmp     [rsi+20h], bl
0x18006b4f6  jnz     short loc_18006B516
0x18006b4f8  mov     r14, [rsi+10h]
0x18006b4fc  lea     rbp, [r14+rax*8]
0x18006b500  cmp     r14, rbp
0x18006b503  jz      short loc_18006B516
0x18006b505  mov     rcx, r14
0x18006b508  call    sub_1800CBE10
0x18006b50d  add     r14, 8
0x18006b511  cmp     r14, rbp
0x18006b514  jnz     short loc_18006B505
0x18006b516  mov     edx, [rsi+18h]; unsigned int
0x18006b519  mov     rcx, [rsi+10h]; unsigned __int8 *
0x18006b51d  call    ?Do@?$TDestructRange@V?$TWeakPtr@$$CBVConnectorDrawingElement@Dr@@@Ofc@@$0A@@Ofc@@SAXPEAEK@Z; Ofc::TDestructRange<Ofc::TWeakPtr<Dr::ConnectorDrawingElement const>,0>::Do(uchar *,ulong)
0x18006b522  mov     rcx, [rsi+10h]
0x18006b526  test    rcx, rcx
0x18006b529  jz      short loc_18006B531
0x18006b52b  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x18006b531  mov     [rsi+10h], rbx
0x18006b535  and     dword ptr [rsi+1Ch], 80000000h
0x18006b53c  mov     [rsi+18h], ebx
0x18006b53f  mov     rax, [rsi]
0x18006b542  mov     rcx, rsi
0x18006b545  mov     rax, [rax+8]
0x18006b549  call    cs:__guard_dispatch_icall_fptr
0x18006b54f  cmp     ebx, [rdi+90h]
0x18006b555  jl      loc_18006B997
0x18006b55b  lea     rax, [rdi+108h]
0x18006b562  add     rsp, 30h
0x18006b566  pop     r14
0x18006b568  pop     rdi
0x18006b569  pop     rsi
0x18006b56a  pop     rbp
0x18006b56b  pop     rbx
0x18006b56c  retn
0x18006b56d  mov     rcx, [rbx]
0x18006b570  add     rcx, 8
0x18006b574  lea     rdx, qword_180E14558
0x18006b57b  call    cs:__imp___std_type_info_compare
0x18006b581  test    eax, eax
0x18006b583  jnz     loc_18006B254
0x18006b589  lea     rax, [rdi+0E8h]
0x18006b590  add     rsp, 30h
0x18006b594  pop     r14
0x18006b596  pop     rdi
0x18006b597  pop     rsi
0x18006b598  pop     rbp
0x18006b599  pop     rbx
0x18006b59a  retn
0x18006b59b  mov     rcx, [rbx]
0x18006b59e  add     rcx, 8
0x18006b5a2  lea     rdx, qword_180E144B0
0x18006b5a9  call    cs:__imp___std_type_info_compare
0x18006b5af  test    eax, eax
0x18006b5b1  jnz     loc_18006B26E
0x18006b5b7  lea     rcx, [rdi+80h]; struct Dr::DrawingSelectionInfo *
0x18006b5be  lea     rdx, [rdi+20h]; struct Art::BlipFillPropsSelectionInfo *
0x18006b5c2  call    ?GetBlipFillPropsInfo@DrawingSelection@Dr@@SAXAEAVDrawingSelectionInfo@2@AEAVBlipFillPropsSelectionInfo@Art@@@Z; Dr::DrawingSelection::GetBlipFillPropsInfo(Dr::DrawingSelectionInfo &,Art::BlipFillPropsSelectionInfo &)
0x18006b5c7  lea     rax, [rdi+20h]
0x18006b5cb  add     rsp, 30h
0x18006b5cf  pop     r14
0x18006b5d1  pop     rdi
0x18006b5d2  pop     rsi
0x18006b5d3  pop     rbp
0x18006b5d4  pop     rbx
0x18006b5d5  retn
0x18006b5d6  mov     rcx, [rbx]
0x18006b5d9  add     rcx, 8
0x18006b5dd  lea     rdx, qword_180E14590
0x18006b5e4  call    cs:__imp___std_type_info_compare
0x18006b5ea  test    eax, eax
0x18006b5ec  jnz     loc_18006B288
0x18006b5f2  mov     rbx, [rdi+3A0h]
0x18006b5f9  test    rbx, rbx
0x18006b5fc  jnz     short loc_18006B630
0x18006b5fe  mov     ecx, 18h; this
0x18006b603  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18006b608  mov     rbx, rax
0x18006b60b  test    rax, rax
0x18006b60e  jz      loc_18006BB46
0x18006b614  mov     dword ptr [rax+8], 209h
0x18006b61b  lea     rax, ??_7SVGBlipFillPropSelectionInfo@Dr@@6B@; const Dr::SVGBlipFillPropSelectionInfo::`vftable'
0x18006b622  mov     [rbx], rax
0x18006b625  mov     [rbx+10h], rdi
0x18006b629  mov     [rdi+3A0h], rbx
0x18006b630  mov     rax, rbx
0x18006b633  add     rsp, 30h
0x18006b637  pop     r14
0x18006b639  pop     rdi
0x18006b63a  pop     rsi
0x18006b63b  pop     rbp
0x18006b63c  pop     rbx
0x18006b63d  retn
0x18006b63e  mov     rcx, [rbx]
0x18006b641  add     rcx, 8
0x18006b645  lea     rdx, qword_180E144E8
0x18006b64c  call    cs:__imp___std_type_info_compare
0x18006b652  test    eax, eax
0x18006b654  jnz     loc_18006B2A2
0x18006b65a  lea     rcx, [rdi+80h]; struct Dr::DrawingSelectionInfo *
0x18006b661  lea     rdx, [rdi+40h]; struct Art::PictureShapePropsSelectionInfo *
0x18006b665  call    ?GetPictureShapePropsInfo@DrawingSelection@Dr@@SAXAEAVDrawingSelectionInfo@2@AEAVPictureShapePropsSelectionInfo@Art@@@Z; Dr::DrawingSelection::GetPictureShapePropsInfo(Dr::DrawingSelectionInfo &,Art::PictureShapePropsSelectionInfo &)
0x18006b66a  lea     rax, [rdi+40h]
0x18006b66e  add     rsp, 30h
0x18006b672  pop     r14
0x18006b674  pop     rdi
0x18006b675  pop     rsi
0x18006b676  pop     rbp
0x18006b677  pop     rbx
0x18006b678  retn
0x18006b679  mov     rcx, [rbx]
0x18006b67c  add     rcx, 8
0x18006b680  lea     rdx, qword_180E14480
0x18006b687  call    cs:__imp___std_type_info_compare
0x18006b68d  test    eax, eax
  ... truncated ...
```
