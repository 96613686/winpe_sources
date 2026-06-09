# Igx::CElementSelection::OnQuerySelectionInfo(Ofc::TypeInfo const &)

- ea: `0x1800263e0`
- end: `0x1800267ac`
- name: `?OnQuerySelectionInfo@CElementSelection@Igx@@EEAAPEAXAEBVTypeInfo@Ofc@@@Z`
- size: `972`
- prototype: `void *__fastcall(Igx::CElementSelection *__hidden this, const struct Ofc::TypeInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800262f0`

## callees

- `0x1800030c0`
- `0x180013110`
- `0x180024bd0`
- `0x1800263e0`
- `0x1800290f0`
- `0x180029590`
- `0x18015b3f8`
- `0x18015b51c`
- `0x18015b630`

## import_xrefs

- `oart!__imp_??0PictureBgRemovalSelectionInfo@Art@@QEAA@PEAVPictureMaskingSelectionInfo@1@@Z` at `0x180038d76`
- `oart!__imp_??0PictureBgRemovalSelectionInfo@Art@@QEAA@PEAVPictureMaskingSelectionInfo@1@@Z` at `0x180038d76`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026421`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002646b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002649d`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800264cf`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026501`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026533`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026565`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026597`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800265c9`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800265fb`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002662d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002665f`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002668d`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026421`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002646b`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002649d`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800264cf`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026501`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026533`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026565`
- `VCRUNTIME140!__std_type_info_compare` at `0x180026597`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800265c9`
- `VCRUNTIME140!__std_type_info_compare` at `0x1800265fb`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002662d`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002665f`
- `VCRUNTIME140!__std_type_info_compare` at `0x18002668d`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800266ad`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800266e8`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18002670f`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180026739`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180038dc2`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180038ded`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800266ad`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x1800266e8`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x18002670f`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180026739`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180038dc2`
- `mso40uiWin32Client!__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ` at `0x180038ded`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int *__fastcall Igx::CElementSelection::OnQuerySelectionInfo(
        Igx::CElementSelection *this,
        struct Art::BlipFillPropsSelectionInfo **a2,
        unsigned int a3)
{
  int *result; // rax
  Ofc::CProxyPtrImpl *v6; // rcx
  void *v7; // rax
  void *Checked; // rax
  void *v10; // rax
  void *v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  Art::PictureBgRemovalSelectionInfo *v15; // rax
  void *v16; // rax
  void *v17; // rax
  Art::Selection *v18; // rax

  if ( a2 == (struct Art::BlipFillPropsSelectionInfo **)&Ofc::TypeInfoImpl<Art::E2oSelectionInfo>::c_typeInfo
    || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
    && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_180349598) )
  {
    return (int *)*((_QWORD *)this + 72);
  }
  if ( a2 != (struct Art::BlipFillPropsSelectionInfo **)&Ofc::TypeInfoImpl<Igx::AElementSelectionInfo>::c_typeInfo
    && (a2[1] == (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
     || (unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_1803495F8)) )
  {
    if ( a2 == (struct Art::BlipFillPropsSelectionInfo **)&Ofc::TypeInfoImpl<Art::ViewElemSelectionInfo>::c_typeInfo
      || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
      && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_180349378) )
    {
      Igx::CElementSelection::UpdateViewElementInfo(this);
      return (int *)((char *)this + 48);
    }
    if ( a2 != (struct Art::BlipFillPropsSelectionInfo **)&Ofc::TypeInfoImpl<Art::TextSelectionInfo>::c_typeInfo
      && (a2[1] == (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
       || (unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_1803495C8))
      && a2 != &Ofc::TypeInfoImpl<Art::TextPropSelectionInfo>::c_typeInfo
      && (a2[1] == (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
       || (unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_180349628)) )
    {
      if ( a2 == &Ofc::TypeInfoImpl<Art::TextFrameSelectionInfo>::c_typeInfo
        || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
        && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_180349418) )
      {
        Igx::CElementSelection::UpdateGeneratedTextFrameInfo(this);
        return (int *)((char *)this + 64);
      }
      if ( a2 == &Ofc::TypeInfoImpl<Art::ShapePropSelectionInfo>::c_typeInfo
        || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
        && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_1803493E0) )
      {
        return (int *)*((_QWORD *)this + 73);
      }
      if ( a2 == &Ofc::TypeInfoImpl<Art::BlipFillPropsSelectionInfo>::c_typeInfo
        || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
        && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_180349488) )
      {
        Igx::CElementSelection::UpdateBlipFillPropsInfo(this);
        return (int *)((char *)this + 624);
      }
      if ( a2 == &Ofc::TypeInfoImpl<Art::SVGBlipFillPropSelectionInfo>::c_typeInfo
        || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
        && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_1803494F8) )
      {
        return (int *)*((_QWORD *)this + 75);
      }
      if ( a2 == &Ofc::TypeInfoImpl<Art::PictureMaskingSelectionInfo>::c_typeInfo
        || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
        && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_1803494C0) )
      {
        return (int *)((char *)this + 656);
      }
      if ( a2 != (struct Art::BlipFillPropsSelectionInfo **)&Ofc::TypeInfoImpl<Art::PictureBgRemovalSelectionInfo>::c_typeInfo
        && (a2[1] == (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
         || (unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_180349530)) )
      {
        if ( a2 == &Ofc::TypeInfoImpl<Art::E2oFormatSelectionInfo>::c_typeInfo
          || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
          && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_1803493A8) )
        {
          return (int *)*((_QWORD *)this + 74);
        }
        if ( a2 == &Ofc::TypeInfoImpl<Art::E2oDrillDownSelectionInfo>::c_typeInfo
          || a2[1] != (struct Art::BlipFillPropsSelectionInfo *)&Ofc::TypeInfo::s_moduleTag
          && !(unsigned int)__std_type_info_compare((char *)*a2 + 8, &qword_180349450) )
        {
          Checked = Ofc::CProxyPtrImpl::GetChecked(*((Ofc::CProxyPtrImpl **)this + 5));
          if ( *(_QWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)Checked + 64LL))(Checked) + 16LL) )
          {
            v10 = Ofc::CProxyPtrImpl::GetChecked(*((Ofc::CProxyPtrImpl **)this + 5));
            if ( (*(unsigned int (__fastcall **)(void *, _QWORD))(*(_QWORD *)v10 + 192LL))(v10, 0) )
              return (int *)((char *)this + 608);
            v11 = Ofc::CProxyPtrImpl::GetChecked(*((Ofc::CProxyPtrImpl **)this + 5));
            v12 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v11 + 192LL))(v11, 1);
            v13 = 0;
            if ( v12 )
              return (int *)((char *)this + 608);
            return (int *)v13;
          }
        }
        return 0;
      }
      v14 = *((_QWORD *)this + 84);
      if ( !v14 )
      {
        v15 = (Art::PictureBgRemovalSelectionInfo *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x10, 0, a3);
        if ( v15 )
          v14 = Art::PictureBgRemovalSelectionInfo::PictureBgRemovalSelectionInfo(
                  v15,
                  (Igx::CElementSelection *)((char *)this + 656));
        else
          v14 = 0;
        *((_QWORD *)this + 84) = v14;
      }
      return (int *)v14;
    }
    else
    {
      v16 = Ofc::CProxyPtrImpl::GetChecked(*((Ofc::CProxyPtrImpl **)this + 5));
      if ( !*(_QWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v16 + 64LL))(v16) + 16LL) )
        return 0;
      v17 = Ofc::CProxyPtrImpl::GetChecked(*((Ofc::CProxyPtrImpl **)this + 5));
      v18 = (Art::Selection *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v17 + 280LL))(v17);
      result = (int *)Art::Selection::ValidateAndQuerySelection(
                        v18,
                        (const struct Ofc::TypeInfo *)&Ofc::TypeInfoImpl<Art::TextSelectionInfo>::c_typeInfo);
      if ( !result || result[8] <= 0 && !*((_BYTE *)result + 61) )
      {
        Igx::CElementSelection::UpdateGeneratedTextInfo(this);
        return (int *)Igx::CElementSelection::UpdateGeneratedTextInfoForElements(this);
      }
    }
  }
  else
  {
    v6 = (Ofc::CProxyPtrImpl *)*((_QWORD *)this + 5);
    if ( *((_QWORD *)v6 + 2)
      && (v7 = Ofc::CProxyPtrImpl::GetChecked(v6),
          *(_QWORD *)(*(_QWORD *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v7 + 64LL))(v7) + 16LL)) )
    {
      return *(int **)(*((_QWORD *)this + 5) + 16LL);
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800263e0  mov     [rsp+arg_0], rbx
0x1800263e5  mov     [rsp+arg_10], rbp
0x1800263ea  mov     [rsp+arg_18], rsi
0x1800263ef  push    rdi
0x1800263f0  sub     rsp, 20h
0x1800263f4  mov     rbx, rdx
0x1800263f7  mov     rdi, rcx
0x1800263fa  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VE2oSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::E2oSelectionInfo>::c_typeInfo
0x180026401  cmp     rdx, rax
0x180026404  jz      short loc_18002642B
0x180026406  lea     rsi, ?s_moduleTag@TypeInfo@Ofc@@2HB; int const Ofc::TypeInfo::s_moduleTag
0x18002640d  cmp     [rdx+8], rsi
0x180026411  jz      short loc_180026447
0x180026413  mov     rcx, [rdx]
0x180026416  add     rcx, 8
0x18002641a  lea     rdx, qword_180349598
0x180026421  call    cs:__imp___std_type_info_compare
0x180026427  test    eax, eax
0x180026429  jnz     short loc_180026447
0x18002642b  mov     rax, [rdi+240h]
0x180026432  mov     rbx, [rsp+28h+arg_0]
0x180026437  mov     rbp, [rsp+28h+arg_10]
0x18002643c  mov     rsi, [rsp+28h+arg_18]
0x180026441  add     rsp, 20h
0x180026445  pop     rdi
0x180026446  retn
0x180026447  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VAElementSelectionInfo@Igx@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Igx::AElementSelectionInfo>::c_typeInfo
0x18002644e  cmp     rbx, rax
0x180026451  jz      loc_18002669E
0x180026457  cmp     [rbx+8], rsi
0x18002645b  jz      short loc_180026479
0x18002645d  mov     rcx, [rbx]
0x180026460  add     rcx, 8
0x180026464  lea     rdx, qword_1803495F8
0x18002646b  call    cs:__imp___std_type_info_compare
0x180026471  test    eax, eax
0x180026473  jz      loc_18002669E
0x180026479  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VViewElemSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::ViewElemSelectionInfo>::c_typeInfo
0x180026480  cmp     rbx, rax
0x180026483  jz      loc_180026771
0x180026489  cmp     [rbx+8], rsi
0x18002648d  jz      short loc_1800264AB
0x18002648f  mov     rcx, [rbx]
0x180026492  add     rcx, 8
0x180026496  lea     rdx, qword_180349378
0x18002649d  call    cs:__imp___std_type_info_compare
0x1800264a3  test    eax, eax
0x1800264a5  jz      loc_180026771
0x1800264ab  lea     rbp, ?c_typeInfo@?$TypeInfoImpl@VTextSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::TextSelectionInfo>::c_typeInfo
0x1800264b2  cmp     rbx, rbp
0x1800264b5  jz      loc_180038DBE
0x1800264bb  cmp     [rbx+8], rsi
0x1800264bf  jz      short loc_1800264DD
0x1800264c1  mov     rcx, [rbx]
0x1800264c4  add     rcx, 8
0x1800264c8  lea     rdx, qword_1803495C8
0x1800264cf  call    cs:__imp___std_type_info_compare
0x1800264d5  test    eax, eax
0x1800264d7  jz      loc_180038DBE
0x1800264dd  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VTextPropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::TextPropSelectionInfo>::c_typeInfo
0x1800264e4  cmp     rbx, rax
0x1800264e7  jz      loc_180038DBE
0x1800264ed  cmp     [rbx+8], rsi
0x1800264f1  jz      short loc_18002650F
0x1800264f3  mov     rcx, [rbx]
0x1800264f6  add     rcx, 8
0x1800264fa  lea     rdx, qword_180349628
0x180026501  call    cs:__imp___std_type_info_compare
0x180026507  test    eax, eax
0x180026509  jz      loc_180038DBE
0x18002650f  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VTextFrameSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::TextFrameSelectionInfo>::c_typeInfo
0x180026516  cmp     rbx, rax
0x180026519  jz      loc_18002679A
0x18002651f  cmp     [rbx+8], rsi
0x180026523  jz      short loc_180026541
0x180026525  mov     rcx, [rbx]
0x180026528  add     rcx, 8
0x18002652c  lea     rdx, qword_180349418
0x180026533  call    cs:__imp___std_type_info_compare
0x180026539  test    eax, eax
0x18002653b  jz      loc_18002679A
0x180026541  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VShapePropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::ShapePropSelectionInfo>::c_typeInfo
0x180026548  cmp     rbx, rax
0x18002654b  jz      loc_18002678E
0x180026551  cmp     [rbx+8], rsi
0x180026555  jz      short loc_180026573
0x180026557  mov     rcx, [rbx]
0x18002655a  add     rcx, 8
0x18002655e  lea     rdx, qword_1803493E0
0x180026565  call    cs:__imp___std_type_info_compare
0x18002656b  test    eax, eax
0x18002656d  jz      loc_18002678E
0x180026573  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VBlipFillPropsSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::BlipFillPropsSelectionInfo>::c_typeInfo
0x18002657a  cmp     rbx, rax
0x18002657d  jz      loc_180038DAA
0x180026583  cmp     [rbx+8], rsi
0x180026587  jz      short loc_1800265A5
0x180026589  mov     rcx, [rbx]
0x18002658c  add     rcx, 8
0x180026590  lea     rdx, qword_180349488
0x180026597  call    cs:__imp___std_type_info_compare
0x18002659d  test    eax, eax
0x18002659f  jz      loc_180038DAA
0x1800265a5  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VSVGBlipFillPropSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::SVGBlipFillPropSelectionInfo>::c_typeInfo
0x1800265ac  cmp     rbx, rax
0x1800265af  jz      loc_180038D9E
0x1800265b5  cmp     [rbx+8], rsi
0x1800265b9  jz      short loc_1800265D7
0x1800265bb  mov     rcx, [rbx]
0x1800265be  add     rcx, 8
0x1800265c2  lea     rdx, qword_1803494F8
0x1800265c9  call    cs:__imp___std_type_info_compare
0x1800265cf  test    eax, eax
0x1800265d1  jz      loc_180038D9E
0x1800265d7  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VPictureMaskingSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::PictureMaskingSelectionInfo>::c_typeInfo
0x1800265de  cmp     rbx, rax
0x1800265e1  jz      loc_180038D92
0x1800265e7  cmp     [rbx+8], rsi
0x1800265eb  jz      short loc_180026609
0x1800265ed  mov     rcx, [rbx]
0x1800265f0  add     rcx, 8
0x1800265f4  lea     rdx, qword_1803494C0
0x1800265fb  call    cs:__imp___std_type_info_compare
0x180026601  test    eax, eax
0x180026603  jz      loc_180038D92
0x180026609  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VPictureBgRemovalSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::PictureBgRemovalSelectionInfo>::c_typeInfo
0x180026610  cmp     rbx, rax
0x180026613  jz      loc_180038D4C
0x180026619  cmp     [rbx+8], rsi
0x18002661d  jz      short loc_18002663B
0x18002661f  mov     rcx, [rbx]
0x180026622  add     rcx, 8
0x180026626  lea     rdx, qword_180349530
0x18002662d  call    cs:__imp___std_type_info_compare
0x180026633  test    eax, eax
0x180026635  jz      loc_180038D4C
0x18002663b  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VE2oFormatSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::E2oFormatSelectionInfo>::c_typeInfo
0x180026642  cmp     rbx, rax
0x180026645  jz      loc_180026782
0x18002664b  cmp     [rbx+8], rsi
0x18002664f  jz      short loc_18002666D
0x180026651  mov     rcx, [rbx]
0x180026654  add     rcx, 8
0x180026658  lea     rdx, qword_1803493A8
0x18002665f  call    cs:__imp___std_type_info_compare
0x180026665  test    eax, eax
0x180026667  jz      loc_180026782
0x18002666d  lea     rax, ?c_typeInfo@?$TypeInfoImpl@VE2oDrillDownSelectionInfo@Art@@@Ofc@@2VTypeInfo@2@B; Ofc::TypeInfo const Ofc::TypeInfoImpl<Art::E2oDrillDownSelectionInfo>::c_typeInfo
0x180026674  cmp     rbx, rax
0x180026677  jz      short loc_1800266E4
0x180026679  cmp     [rbx+8], rsi
0x18002667d  jz      short loc_180026697
0x18002667f  mov     rcx, [rbx]
0x180026682  add     rcx, 8
0x180026686  lea     rdx, qword_180349450
0x18002668d  call    cs:__imp___std_type_info_compare
0x180026693  test    eax, eax
0x180026695  jz      short loc_1800266E4
0x180026697  xor     eax, eax
0x180026699  jmp     loc_180026432
0x18002669e  mov     rcx, [rdi+28h]
0x1800266a2  cmp     qword ptr [rcx+10h], 0
0x1800266a7  jz      loc_180038E42
0x1800266ad  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800266b3  mov     rdx, rax
0x1800266b6  mov     rcx, [rax]
0x1800266b9  mov     rax, [rcx+40h]
0x1800266bd  mov     rcx, rdx
0x1800266c0  call    cs:__guard_dispatch_icall_fptr
0x1800266c6  mov     rcx, [rax]
0x1800266c9  cmp     qword ptr [rcx+10h], 0
0x1800266ce  jz      loc_180038E42
0x1800266d4  mov     rax, [rdi+28h]
0x1800266d8  mov     rdx, [rax+10h]
0x1800266dc  mov     rax, rdx
0x1800266df  jmp     loc_180026432
0x1800266e4  mov     rcx, [rdi+28h]
0x1800266e8  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800266ee  mov     rdx, rax
0x1800266f1  mov     rcx, [rax]
0x1800266f4  mov     rax, [rcx+40h]
0x1800266f8  mov     rcx, rdx
0x1800266fb  call    cs:__guard_dispatch_icall_fptr
0x180026701  mov     rcx, [rax]
0x180026704  cmp     qword ptr [rcx+10h], 0
0x180026709  jz      short loc_180026697
0x18002670b  mov     rcx, [rdi+28h]
0x18002670f  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180026715  mov     r8, rax
0x180026718  mov     rcx, [rax]
0x18002671b  mov     rax, [rcx+0C0h]
0x180026722  xor     edx, edx
0x180026724  mov     rcx, r8
0x180026727  call    cs:__guard_dispatch_icall_fptr
0x18002672d  test    eax, eax
0x18002672f  jnz     loc_180038D40
0x180026735  mov     rcx, [rdi+28h]
0x180026739  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18002673f  mov     r8, rax
0x180026742  mov     rcx, [rax]
0x180026745  mov     rax, [rcx+0C0h]
0x18002674c  mov     edx, 1
0x180026751  mov     rcx, r8
0x180026754  call    cs:__guard_dispatch_icall_fptr
0x18002675a  lea     rcx, [rdi+260h]
0x180026761  xor     edx, edx
0x180026763  test    eax, eax
0x180026765  cmovnz  rdx, rcx
0x180026769  mov     rax, rdx
0x18002676c  jmp     loc_180026432
0x180026771  mov     rcx, rdi; this
0x180026774  call    ?UpdateViewElementInfo@CElementSelection@Igx@@AEAAXXZ; Igx::CElementSelection::UpdateViewElementInfo(void)
0x180026779  lea     rax, [rdi+30h]
0x18002677d  jmp     loc_180026432
0x180026782  mov     rax, [rdi+250h]
0x180026789  jmp     loc_180026432
0x18002678e  mov     rax, [rdi+248h]
0x180026795  jmp     loc_180026432
0x18002679a  mov     rcx, rdi; this
0x18002679d  call    ?UpdateGeneratedTextFrameInfo@CElementSelection@Igx@@AEAAXXZ; Igx::CElementSelection::UpdateGeneratedTextFrameInfo(void)
0x1800267a2  lea     rax, [rdi+40h]
0x1800267a6  jmp     loc_180026432
0x180038d40  lea     rax, [rdi+260h]
0x180038d47  jmp     loc_180026432
0x180038d4c  mov     rdx, [rdi+2A0h]; unsigned __int64
0x180038d53  test    rdx, rdx
0x180038d56  jnz     short loc_180038D8A
0x180038d58  mov     ecx, 10h; this
0x180038d5d  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180038d62  mov     [rsp+28h+arg_8], rax
0x180038d67  test    rax, rax
0x180038d6a  jz      short loc_180038D81
0x180038d6c  lea     rdx, [rdi+290h]
0x180038d73  mov     rcx, rax
0x180038d76  call    cs:__imp_??0PictureBgRemovalSelectionInfo@Art@@QEAA@PEAVPictureMaskingSelectionInfo@1@@Z; Art::PictureBgRemovalSelectionInfo::PictureBgRemovalSelectionInfo(Art::PictureMaskingSelectionInfo *)
0x180038d7c  mov     rdx, rax
0x180038d7f  jmp     short loc_180038D83
0x180038d81  xor     edx, edx
0x180038d83  mov     [rdi+2A0h], rdx
0x180038d8a  mov     rax, rdx
0x180038d8d  jmp     loc_180026432
0x180038d92  lea     rax, [rdi+290h]
0x180038d99  jmp     loc_180026432
0x180038d9e  mov     rax, [rdi+258h]
0x180038da5  jmp     loc_180026432
0x180038daa  mov     rcx, rdi; this
0x180038dad  call    ?UpdateBlipFillPropsInfo@CElementSelection@Igx@@AEAAXXZ; Igx::CElementSelection::UpdateBlipFillPropsInfo(void)
0x180038db2  lea     rax, [rdi+270h]
0x180038db9  jmp     loc_180026432
0x180038dbe  mov     rcx, [rdi+28h]
0x180038dc2  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180038dc8  mov     rdx, rax
0x180038dcb  mov     rcx, [rax]
0x180038dce  mov     rax, [rcx+40h]
0x180038dd2  mov     rcx, rdx
0x180038dd5  call    cs:__guard_dispatch_icall_fptr
0x180038ddb  mov     rcx, [rax]
0x180038dde  cmp     qword ptr [rcx+10h], 0
0x180038de3  jz      loc_180026697
0x180038de9  mov     rcx, [rdi+28h]
0x180038ded  call    cs:__imp_?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180038df3  mov     r8, rax
0x180038df6  mov     rcx, [rax]
0x180038df9  mov     rax, [rcx+118h]
0x180038e00  mov     rcx, r8
0x180038e03  call    cs:__guard_dispatch_icall_fptr
0x180038e09  mov     rdx, rbp; struct Ofc::TypeInfo *
0x180038e0c  mov     rcx, rax; this
0x180038e0f  call    ?ValidateAndQuerySelection@Selection@Art@@AEAAPEAXAEBVTypeInfo@Ofc@@@Z; Art::Selection::ValidateAndQuerySelection(Ofc::TypeInfo const &)
0x180038e14  test    rax, rax
0x180038e17  jz      short loc_180038E2D
0x180038e19  cmp     dword ptr [rax+20h], 0
0x180038e1d  jg      loc_180026432
0x180038e23  cmp     byte ptr [rax+3Dh], 0
0x180038e27  jnz     loc_180026432
0x180038e2d  mov     rcx, rdi; this
0x180038e30  call    ?UpdateGeneratedTextInfo@CElementSelection@Igx@@AEAAXXZ; Igx::CElementSelection::UpdateGeneratedTextInfo(void)
0x180038e35  mov     rcx, rdi; this
0x180038e38  call    ?UpdateGeneratedTextInfoForElements@CElementSelection@Igx@@AEAAPEAXXZ; Igx::CElementSelection::UpdateGeneratedTextInfoForElements(void)
0x180038e3d  jmp     loc_180026432
0x180038e42  xor     edx, edx
0x180038e44  jmp     loc_1800266DC
```
