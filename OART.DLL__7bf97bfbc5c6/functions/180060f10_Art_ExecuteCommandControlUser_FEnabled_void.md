# Art::ExecuteCommandControlUser::FEnabled(void)

- ea: `0x180060f10`
- end: `0x18006203d`
- name: `?FEnabled@ExecuteCommandControlUser@Art@@MEAA_NXZ`
- size: `4397`
- prototype: `bool __fastcall(Art::ExecuteCommandControlUser *__hidden this)`
- caller_count: `1`
- callee_count: `36`
- tags: `broker_com_uri`

## callers

- `0x180055260`

## callees

- `0x180003c40`
- `0x180003c60`
- `0x180003d20`
- `0x180011550`
- `0x180011b20`
- `0x180014d48`
- `0x180015120`
- `0x180015160`
- `0x18005f690`
- `0x180060d60`
- `0x180060e00`
- `0x180060f10`
- `0x180062040`
- `0x18006cbe0`
- `0x18006d0a0`
- `0x180071720`
- `0x180130634`
- `0x1801441e4`
- `0x1801f7680`
- `0x18026c3d0`
- `0x1803075d4`
- `0x180307608`
- `0x1803076a0`
- `0x1803c5020`
- `0x1804e941c`
- `0x1804f63f0`
- `0x18058f198`
- `0x1806216c0`
- `0x180622ff8`
- `0x180674c90`
- `0x180678a64`
- `0x1806a5084`
- `0x1806a51d0`
- `0x1806a57c4`
- `0x1806a5c5c`
- `0x1807003b0`

## import_xrefs

- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x180061191`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x1800613b4`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x18006154a`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x18006163e`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x180061191`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x1800613b4`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x18006154a`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x18006163e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180061142`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800612bd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180061345`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180061432`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800614ab`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180061142`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800612bd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180061345`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180061432`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800614ab`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180061741`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180061741`

## pseudocode

```c
char __fastcall Art::ExecuteCommandControlUser::FEnabled(struct Ofc::CProxyPtrImpl **this)
{
  struct Ofc::CProxyPtrImpl **v2; // rsi
  struct Ofc::CProxyPtrImpl *v3; // rax
  void *Checked; // rax
  volatile signed __int32 **CurrentView; // rax
  volatile signed __int32 *v7; // rcx
  char v8; // di
  int Tcid; // ebx
  unsigned __int64 v10; // rcx
  char v11; // bl
  struct Art::IAppHost *AppHost; // rax
  char v13; // bl
  Art *v14; // rcx
  int v15; // r9d
  void *v16; // rax
  bool v17; // bl
  bool v18; // bl
  struct Art::IAppHost *v19; // rax
  struct Art::IAppHost *v20; // rax
  Art *v21; // rcx
  struct Art::IAppHost *v22; // rax
  void *v23; // rax
  Art *v24; // rcx
  struct Art::IAppHost *v25; // rbx
  __int64 (__fastcall *v26)(struct Art::IAppHost *, void *); // rdi
  void *v27; // rax
  Art *v28; // rcx
  struct Art::IAppHost *v29; // rbx
  unsigned __int8 (__fastcall *v30)(struct Art::IAppHost *, void *); // rsi
  void *v31; // rax
  bool v32; // al
  struct Art::IAppHost *v33; // rbx
  unsigned __int8 (__fastcall *v34)(struct Art::IAppHost *, void *); // rsi
  void *v35; // rax
  Art::View *v36; // rax
  Art *v37; // rax
  const struct Art::Selection *v38; // rdx
  bool valid; // bl
  Art::View *v40; // rax
  Art *v41; // rax
  const struct Art::Selection *v42; // rdx
  bool v43; // r8
  bool v44; // bl
  const struct Art::UserInterface *v45; // rdx
  bool v46; // bl
  const struct Art::UserInterface *v47; // rdx
  Art::FeatureGates *v48; // rcx
  const struct Art::UserInterface *v49; // rdx
  void *v50; // rax
  char v51; // bl
  void *v52; // rax
  char v53; // bl
  const struct Art::UserInterface *v54; // rdx
  bool v55; // bl
  void *v56; // rax
  __int64 v57; // r8
  struct Ofc::CProxyPtrImpl **v58; // rax
  void *v59; // rax
  char v60; // bl
  int v61; // eax
  Art *v62; // rcx
  void *v63; // rax
  __int64 v64; // r8
  struct Ofc::CProxyPtrImpl **v65; // rax
  void *v66; // rax
  Art *v67; // rcx
  void *v68; // rax
  __int64 v69; // r8
  struct Ofc::CProxyPtrImpl **v70; // rax
  void *v71; // rax
  bool v72; // bl
  Art::UserInterface *v73; // rax
  struct Art::Selection *CurrentSelection; // rax
  char v75; // bl
  struct Ofc::CProxyPtrImpl *v76; // [rsp+40h] [rbp-108h] BYREF
  __int64 v77; // [rsp+48h] [rbp-100h]
  __int64 v78; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v79; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v80; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v81; // [rsp+68h] [rbp-E0h]
  __int64 v82; // [rsp+70h] [rbp-D8h] BYREF
  struct Ofc::CProxyPtrImpl *v83; // [rsp+78h] [rbp-D0h] BYREF
  _BYTE v84[184]; // [rsp+90h] [rbp-B8h] BYREF
  struct Ofc::CProxyPtrImpl *v85; // [rsp+150h] [rbp+8h] BYREF
  Ofc::CProxyPtrImpl *v86; // [rsp+158h] [rbp+10h] BYREF
  Ofc::CProxyPtrImpl *v87; // [rsp+160h] [rbp+18h] BYREF
  Dr *v88; // [rsp+168h] [rbp+20h] BYREF

  v2 = this + 4;
  v3 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[4]);
  v86 = v3;
  if ( !*((_QWORD *)v3 + 2) )
  {
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    return 0;
  }
  Checked = Ofc::CProxyPtrImpl::GetChecked(v3);
  CurrentView = (volatile signed __int32 **)Art::UserInterface::GetCurrentView(Checked, &v85, 0);
  v7 = *CurrentView;
  v8 = 1;
  if ( **CurrentView != 0x80000000 )
    _InterlockedAdd(v7, 1u);
  v87 = (Ofc::CProxyPtrImpl *)v7;
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
  Tcid = Art::ExecuteCommandControlUser::GetTcid((Art::ExecuteCommandControlUser *)this);
  if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&byte_180E1A4C8)
    && (unsigned __int8)Art::IsDeferredModel3DE2oSelected(v2)
    && Tcid == 5736 )
  {
    goto LABEL_78;
  }
  if ( (unsigned __int8)Art::IsDeferredImageSelected(v2)
    && !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&byte_180E1A4B8) )
  {
    if ( Tcid > 27398 )
    {
      if ( Tcid == 27530 )
        goto LABEL_78;
      if ( Tcid == 27532 )
        goto LABEL_78;
      v10 = (unsigned int)(Tcid - 33984);
      if ( Tcid == 33984 || Tcid == 34706 )
        goto LABEL_78;
    }
    else
    {
      switch ( Tcid )
      {
        case 27398:
          goto LABEL_78;
        case 1362:
          goto LABEL_78;
        case 1440:
          goto LABEL_78;
        case 14826:
          goto LABEL_78;
      }
      v10 = (unsigned int)(Tcid - 22711);
      if ( Tcid == 22711 || Tcid == 27397 )
        goto LABEL_78;
    }
  }
  switch ( Tcid )
  {
    case 27818:
      v11 = Art::FEnabledAdvancedUISwitchForModel3D(v2);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v11;
    case 931:
    case 2619:
    case 29811:
    case 5811:
    case 27817:
      goto LABEL_169;
    case 34744:
LABEL_31:
      AppHost = Art::GetAppHost((Art *)v10);
      v13 = (*(__int64 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)AppHost + 200LL))(AppHost, 163);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v13;
    case 33387:
      MsoShipAssertTagProc(36840718);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return 0;
    case 33448:
    case 32730:
      v73 = (Art::UserInterface *)Ofc::CProxyPtrImpl::GetChecked(v86);
      CurrentSelection = Art::UserInterface::GetCurrentSelection(v73);
      if ( CurrentSelection )
      {
        v75 = Art::FDisableInsertInkDrawingCanvas(&v87, CurrentSelection) ^ 1;
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        return v75;
      }
      goto LABEL_169;
  }
  if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&byte_180E1A4E8)
    || InsertMedia::FEnableCommand(v14) )
  {
    LOBYTE(v14) = 0;
    if ( Tcid == 27088 || Tcid == 33904 )
    {
      v72 = Art::AreSVGExtendedFeaturesEnabled(v14);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v72;
    }
    if ( Tcid == 27530 )
    {
      v76 = 0;
      if ( *((_QWORD *)v87 + 2)
        && (*((unsigned __int8 (__fastcall **)(struct Ofc::CProxyPtrImpl **, struct Ofc::CProxyPtrImpl **))*this + 22))(
             this,
             &v76) )
      {
        if ( !Art::AreSVGExtendedFeaturesEnabled(v14)
          || (v16 = Ofc::CProxyPtrImpl::GetChecked(v87),
              v17 = 1,
              (*(_BYTE *)Art::View::GetInfoCommandState(v16, &v85, v76) & 1) == 0) )
        {
          v17 = 0;
        }
        if ( v76 )
          (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *, __int64))(*(_QWORD *)v76 + 40LL))(v76, 1);
      }
      else
      {
        v17 = Art::AreSVGExtendedFeaturesEnabled(v14);
        if ( v76 )
          (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *, __int64))(*(_QWORD *)v76 + 40LL))(v76, 1);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v17;
    }
  }
  else
  {
    LOBYTE(v14) = 1;
  }
  switch ( Tcid )
  {
    case 33273:
      MsoShipAssertTagProc(36226695);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return 0;
    case 27814:
    case 34830:
    case 33308:
      v76 = 0;
      v77 = 0;
      v80 = 0;
      v81 = 0;
      v82 = 0;
      v83 = 0;
      LOBYTE(v15) = 1;
      Art::InsertPictureListInfoCommand::InsertPictureListInfoCommand(
        (unsigned int)v84,
        (unsigned int)&v76,
        (unsigned int)&v80,
        v15,
        0,
        5,
        (__int64)&v86,
        (__int64)&v82);
      if ( !*((_QWORD *)v87 + 2) )
      {
        v68 = Ofc::CProxyPtrImpl::GetChecked(v86);
        LOBYTE(v69) = 1;
        v70 = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(v68, &v85, v69);
        Ofc::CProxyPtrImpl::StrongAssign(&v87, *v70);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      }
      if ( !Art::FIsModel3DCfEnabled(v67)
        || (v71 = Ofc::CProxyPtrImpl::GetChecked(v86),
            (*(_BYTE *)Art::UserInterface::GetInfoCommandState(v71, &v85, v84) & 1) == 0) )
      {
        v8 = 0;
      }
      Art::InsertPictureListInfoCommand::~InsertPictureListInfoCommand((Art::InsertPictureListInfoCommand *)v84);
      Ofc::TObjList<Ofc::TStrMap<Ofc::CVarStr>>::~TObjList<Ofc::TStrMap<Ofc::CVarStr>>((Ofc::CListImpl *)&v82);
      Ofc::TObjList<Ofc::CVarStr>::~TObjList<Ofc::CVarStr>((Ofc::CListImpl *)&v80);
      Ofc::TObjList<Ofc::CVarStr>::~TObjList<Ofc::CVarStr>((Ofc::CListImpl *)&v76);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v8;
    case 27815:
    case 33309:
    case 34831:
    case 33903:
      v61 = 7;
      if ( (_BYTE)v14 && Tcid == 33309 )
        v61 = 5;
      v82 = 0;
      v83 = 0;
      v80 = 0;
      v81 = 0;
      v76 = 0;
      v77 = 0;
      LOBYTE(v15) = 1;
      Art::InsertPictureListInfoCommand::InsertPictureListInfoCommand(
        (unsigned int)v84,
        (unsigned int)&v82,
        (unsigned int)&v80,
        v15,
        0,
        v61,
        (__int64)&v86,
        (__int64)&v76);
      if ( !*((_QWORD *)v87 + 2) )
      {
        v63 = Ofc::CProxyPtrImpl::GetChecked(v86);
        LOBYTE(v64) = 1;
        v65 = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(v63, &v85, v64);
        Ofc::CProxyPtrImpl::StrongAssign(&v87, *v65);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      }
      if ( !Art::FIsModel3DOnlineEnabled(v62)
        || (v66 = Ofc::CProxyPtrImpl::GetChecked(v86),
            (*(_BYTE *)Art::UserInterface::GetInfoCommandState(v66, &v85, v84) & 1) == 0) )
      {
        v8 = 0;
      }
      Art::InsertPictureListInfoCommand::~InsertPictureListInfoCommand((Art::InsertPictureListInfoCommand *)v84);
      Ofc::TObjList<Ofc::TStrMap<Ofc::CVarStr>>::~TObjList<Ofc::TStrMap<Ofc::CVarStr>>((Ofc::CListImpl *)&v76);
      Ofc::TObjList<Ofc::CVarStr>::~TObjList<Ofc::CVarStr>((Ofc::CListImpl *)&v80);
      Ofc::TObjList<Ofc::CVarStr>::~TObjList<Ofc::CVarStr>((Ofc::CListImpl *)&v82);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v8;
    case 34116:
      MsoShipAssertTagProc(591152203);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return 0;
    case 27532:
      v18 = Art::FClipboardContainsImage(v14);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v18;
  }
  if ( (Tcid == 20868 || Tcid == 33955 || Tcid == 34705) && InsertMedia::FEnableCommand(v14) )
  {
LABEL_169:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    return 1;
  }
  switch ( Tcid )
  {
    case 34808:
      v19 = Art::GetAppHost(v14);
      if ( (*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)v19 + 200LL))(v19, 163) )
        MsoShipAssertTagProc(591152203);
LABEL_78:
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return 0;
    case 34809:
      v20 = Art::GetAppHost(v14);
      if ( (*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)v20 + 200LL))(v20, 163) )
        MsoShipAssertTagProc(36840718);
      goto LABEL_78;
    case 34921:
      if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&qword_180E1C3E8)
        || (v22 = Art::GetAppHost(v21),
            !(*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)v22 + 200LL))(v22, 163)) )
      {
        v8 = 0;
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v8;
  }
  if ( ((unsigned int)(Tcid - 34745) <= 1 || Tcid == 34884) && InsertMedia::FEnableCommand(v14) )
    goto LABEL_31;
  if ( Tcid == 1031 )
    goto LABEL_169;
  v85 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v2);
  v23 = Ofc::CProxyPtrImpl::GetChecked(v85);
  Art::UserInterface::GetCurrentView(v23, &v88, 0);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
  v24 = v88;
  if ( !*((_QWORD *)v88 + 2) )
  {
LABEL_147:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    return 0;
  }
  switch ( Tcid )
  {
    case 34044:
      if ( InsertMedia::FEnableCommand(v88) )
      {
        v25 = Art::GetAppHost(v24);
        v26 = *(__int64 (__fastcall **)(struct Art::IAppHost *, void *))(*(_QWORD *)v25 + 744LL);
        v27 = Ofc::CProxyPtrImpl::GetChecked(v88);
        LOBYTE(v25) = v26(v25, v27);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        return (char)v25;
      }
LABEL_116:
      if ( Art::FeatureGates::FLiveFeedEnabled(v24) && Art::FSelectionContainsOnlyLiveFeed(*((Art **)v86 + 2), v47) )
      {
        switch ( Tcid )
        {
          case 14826:
            goto LABEL_147;
          case 27175:
            goto LABEL_147;
          case 27397:
            goto LABEL_147;
          case 27398:
            goto LABEL_147;
        }
        v48 = (Art::FeatureGates *)(unsigned int)(Tcid - 33984);
        if ( Tcid == 33984 || Tcid == 34706 )
          goto LABEL_147;
      }
      if ( Art::FeatureGates::FInsertLiveFeedEnabled(v48)
        && Tcid == 164
        && Art::FSelectionContainsAtLeastOneCameo(*((Art **)v86 + 2), v49) )
      {
        goto LABEL_147;
      }
      v79 = 0;
      v78 = 0;
      if ( (*((unsigned __int8 (__fastcall **)(struct Ofc::CProxyPtrImpl **, __int64 *))*this + 22))(this, &v79) )
      {
        v50 = Ofc::CProxyPtrImpl::GetChecked(v88);
        v51 = *(_BYTE *)Art::View::GetInfoCommandState(v50, &v85, v79) & 1;
        if ( v79 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v79 + 40LL))(v79, 1);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        return v51;
      }
      else if ( (*((unsigned __int8 (__fastcall **)(struct Ofc::CProxyPtrImpl **, __int64 *))*this + 23))(this, &v78) )
      {
        v52 = Ofc::CProxyPtrImpl::GetChecked(v88);
        v53 = *(_BYTE *)Art::View::GetCommandState(v52, &v85, v78) & 1;
        if ( v78 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v78 + 168LL))(v78, 1);
        if ( v79 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v79 + 40LL))(v79, 1);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        return v53;
      }
      else
      {
        if ( v78 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v78 + 168LL))(v78, 1);
        if ( v79 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v79 + 40LL))(v79, 1);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        return 0;
      }
    case 34218:
      if ( !Dr::FInsertStockVideoEnabled(v88)
        || (v29 = Art::GetAppHost(v28),
            v30 = *(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, void *))(*(_QWORD *)v29 + 744LL),
            v31 = Ofc::CProxyPtrImpl::GetChecked(v88),
            !v30(v29, v31)) )
      {
        v8 = 0;
      }
LABEL_97:
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v8;
    case 34800:
      if ( byte_180E1C538 < 0 )
        v32 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180E1C538);
      else
        v32 = byte_180E1C538 != 0;
      if ( !v32
        || (v33 = Art::GetAppHost(v24),
            v34 = *(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, void *))(*(_QWORD *)v33 + 760LL),
            v35 = Ofc::CProxyPtrImpl::GetChecked(v88),
            !v34(v33, v35)) )
      {
        v8 = 0;
      }
      goto LABEL_97;
    case 33412:
      v36 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v88);
      v37 = Art::View::EnsureAggregateSelection(v36);
      valid = Art::FContainsValidAnimatableModel3DE2os(v37, v38);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return valid;
    case 33891:
      v40 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v88);
      v41 = Art::View::EnsureAggregateSelection(v40);
      v44 = Art::FAnyPlayableViewElementInSelection(v41, v42, v43);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      return v44;
  }
  if ( Tcid != 34307 && Tcid != 34818 )
  {
    if ( (unsigned int)(Tcid - 34488) <= 2 )
    {
      if ( Art::FeatureGates::FInsertLiveFeedEnabled(v88) )
      {
        v55 = Art::FSelectionContainsOnlyLiveFeed(*((Art **)v86 + 2), v54);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        return v55;
      }
      goto LABEL_147;
    }
    if ( Tcid == 34819 )
    {
      if ( Art::FeatureGates::FInsertLiveFeedEnabled(v88) )
      {
        v46 = Art::FSelectionContainsOnlyOneLiveFeed(*((Art **)v86 + 2), v45);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        return v46;
      }
      goto LABEL_147;
    }
    goto LABEL_116;
  }
  if ( !Art::FeatureGates::FInsertLiveFeedEnabled(v88) )
    goto LABEL_147;
  if ( !*((_QWORD *)v87 + 2) )
  {
    v56 = Ofc::CProxyPtrImpl::GetChecked(v86);
    LOBYTE(v57) = 1;
    v58 = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(v56, &v76, v57);
    Ofc::CProxyPtrImpl::StrongAssign(&v87, *v58);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v76);
  }
  Art::InsertCameoInfoCommand::InsertCameoInfoCommand((Art::InsertCameoInfoCommand *)&v82);
  v59 = Ofc::CProxyPtrImpl::GetChecked(v86);
  v60 = *(_BYTE *)Art::UserInterface::GetInfoCommandState(v59, &v85, &v82) & 1;
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v83);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v88);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
  return v60;
}

```

## disassembly

```asm
0x180060f10  push    rbx
0x180060f12  push    rsi
0x180060f13  push    rdi
0x180060f14  push    r14
0x180060f16  push    r15
0x180060f18  sub     rsp, 120h
0x180060f1f  mov     r14, rcx
0x180060f22  lea     rsi, [rcx+20h]
0x180060f26  mov     rcx, [rsi]; struct Ofc::CProxyPtrImpl *
0x180060f29  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180060f2e  mov     [rsp+148h+arg_8], rax
0x180060f36  xor     r15d, r15d
0x180060f39  cmp     [rax+10h], r15
0x180060f3d  jnz     short loc_180060F53
0x180060f3f  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180060f47  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180060f4c  xor     al, al
0x180060f4e  jmp     loc_18006202E
0x180060f53  mov     rcx, rax; this
0x180060f56  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180060f5b  xor     r8d, r8d
0x180060f5e  lea     rdx, [rsp+148h+arg_0]
0x180060f66  mov     rcx, rax
0x180060f69  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x180060f6e  mov     rcx, [rax]
0x180060f71  mov     eax, [rcx]
0x180060f73  mov     edi, 1
0x180060f78  cmp     eax, 80000000h
0x180060f7d  jz      short loc_180060F83
0x180060f7f  nop
0x180060f80  lock add [rcx], edi
0x180060f83  mov     [rsp+148h+arg_10], rcx
0x180060f8b  lea     rcx, [rsp+148h+arg_0]; struct Ofc::CProxyPtrImpl **
0x180060f93  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180060f98  mov     rcx, r14; this
0x180060f9b  call    ?GetTcid@ExecuteCommandControlUser@Art@@IEAAHXZ; Art::ExecuteCommandControlUser::GetTcid(void)
0x180060fa0  mov     ebx, eax
0x180060fa2  lea     rcx, byte_180E1A4C8
0x180060fa9  call    ??BChangeGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::ChangeGate::operator bool(void)
0x180060fae  test    al, al
0x180060fb0  jnz     short loc_180060FE7
0x180060fb2  mov     rcx, rsi
0x180060fb5  call    ?IsDeferredModel3DE2oSelected@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::IsDeferredModel3DE2oSelected(Ofc::TWeakPtr<Art::UserInterface> const &)
0x180060fba  test    al, al
0x180060fbc  jz      short loc_180060FE7
0x180060fbe  cmp     ebx, 1668h
0x180060fc4  jnz     short loc_180060FE7
0x180060fc6  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180060fce  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180060fd3  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180060fdb  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180060fe0  xor     al, al
0x180060fe2  jmp     loc_18006202E
0x180060fe7  mov     rcx, rsi
0x180060fea  call    ?IsDeferredImageSelected@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::IsDeferredImageSelected(Ofc::TWeakPtr<Art::UserInterface> const &)
0x180060fef  test    al, al
0x180060ff1  jz      loc_18006107B
0x180060ff7  lea     rcx, byte_180E1A4B8
0x180060ffe  call    ??BChangeGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::ChangeGate::operator bool(void)
0x180061003  test    al, al
0x180061005  jnz     short loc_18006107B
0x180061007  mov     eax, 6B06h
0x18006100c  cmp     ebx, eax
0x18006100e  jg      short loc_18006103B
0x180061010  jz      short loc_18006105A
0x180061012  mov     ecx, ebx
0x180061014  sub     ecx, 552h
0x18006101a  jz      short loc_18006105A
0x18006101c  sub     ecx, 4Eh ; 'N'
0x18006101f  jz      short loc_18006105A
0x180061021  sub     ecx, 344Ah
0x180061027  jz      short loc_18006105A
0x180061029  sub     ecx, 1ECDh
0x18006102f  jz      short loc_18006105A
0x180061031  cmp     ecx, 124Eh
0x180061037  jnz     short loc_18006107B
0x180061039  jmp     short loc_18006105A
0x18006103b  mov     ecx, ebx
0x18006103d  sub     ecx, 6B8Ah
0x180061043  jz      short loc_18006105A
0x180061045  sub     ecx, 2
0x180061048  jz      short loc_18006105A
0x18006104a  sub     ecx, 1934h
0x180061050  jz      short loc_18006105A
0x180061052  cmp     ecx, 2D2h
0x180061058  jnz     short loc_18006107B
0x18006105a  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061062  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061067  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x18006106f  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061074  xor     al, al
0x180061076  jmp     loc_18006202E
0x18006107b  cmp     ebx, 6CAAh
0x180061081  jnz     short loc_1800610AE
0x180061083  mov     rcx, rsi
0x180061086  call    ?FEnabledAdvancedUISwitchForModel3D@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::FEnabledAdvancedUISwitchForModel3D(Ofc::TWeakPtr<Art::UserInterface> const &)
0x18006108b  mov     bl, al
0x18006108d  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061095  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18006109a  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x1800610a2  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800610a7  mov     al, bl
0x1800610a9  jmp     loc_18006202E
0x1800610ae  cmp     ebx, 3A3h
0x1800610b4  jz      loc_180062008
0x1800610ba  cmp     ebx, 0A3Bh
0x1800610c0  jz      loc_180062008
0x1800610c6  cmp     ebx, 7473h
0x1800610cc  jz      loc_180062008
0x1800610d2  cmp     ebx, 16B3h
0x1800610d8  jz      loc_180062008
0x1800610de  cmp     ebx, 6CA9h
0x1800610e4  jz      loc_180062008
0x1800610ea  cmp     ebx, 87B8h
0x1800610f0  jnz     short loc_180061135
0x1800610f2  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x1800610f7  mov     r8, rax
0x1800610fa  mov     rcx, [rax]
0x1800610fd  mov     rax, [rcx+0C8h]
0x180061104  mov     edx, 0A3h
0x180061109  mov     rcx, r8
0x18006110c  call    cs:__guard_dispatch_icall_fptr
0x180061112  mov     bl, al
0x180061114  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x18006111c  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061121  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180061129  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18006112e  mov     al, bl
0x180061130  jmp     loc_18006202E
0x180061135  cmp     ebx, 826Bh
0x18006113b  jnz     short loc_180061169
0x18006113d  mov     ecx, 232250Eh
0x180061142  call    cs:__imp_MsoShipAssertTagProc
0x180061148  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061150  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061155  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x18006115d  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061162  xor     al, al
0x180061164  jmp     loc_18006202E
0x180061169  cmp     ebx, 82A8h
0x18006116f  jz      loc_180061F93
0x180061175  cmp     ebx, 7FDAh
0x18006117b  jz      loc_180061F93
0x180061181  lea     rcx, byte_180E1A4E8
0x180061188  call    ??BChangeGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::ChangeGate::operator bool(void)
0x18006118d  test    al, al
0x18006118f  jz      short loc_1800611A3
0x180061191  call    cs:__imp_?FEnableCommand@InsertMedia@@YA_NXZ; InsertMedia::FEnableCommand(void)
0x180061197  test    al, al
0x180061199  jnz     short loc_1800611A3
0x18006119b  mov     cl, dil; this
0x18006119e  jmp     loc_1800612B0
0x1800611a3  mov     cl, r15b; this
0x1800611a6  cmp     ebx, 69D0h
0x1800611ac  jz      loc_180061F6B
0x1800611b2  cmp     ebx, 8470h
0x1800611b8  jz      loc_180061F6B
0x1800611be  cmp     ebx, 6B8Ah
0x1800611c4  jnz     loc_1800612B0
0x1800611ca  mov     [rsp+148h+var_108], r15
0x1800611cf  mov     rax, [rsp+148h+arg_10]
0x1800611d7  cmp     [rax+10h], r15
0x1800611db  jz      loc_18006126E
0x1800611e1  mov     rax, [r14]
0x1800611e4  lea     rdx, [rsp+148h+var_108]
0x1800611e9  mov     rcx, r14
0x1800611ec  mov     rax, [rax+0B0h]
0x1800611f3  call    cs:__guard_dispatch_icall_fptr
0x1800611f9  test    al, al
0x1800611fb  jz      short loc_18006126E
0x1800611fd  call    ?AreSVGExtendedFeaturesEnabled@Art@@YA_NXZ; Art::AreSVGExtendedFeaturesEnabled(void)
0x180061202  test    al, al
0x180061204  jz      short loc_180061230
0x180061206  mov     rcx, [rsp+148h+arg_10]; this
0x18006120e  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180061213  mov     r8, [rsp+148h+var_108]
0x180061218  lea     rdx, [rsp+148h+arg_0]
0x180061220  mov     rcx, rax
0x180061223  call    ?GetInfoCommandState@View@Art@@QEBA?BVCommandState@2@AEBVInfoCommand@2@@Z; Art::View::GetInfoCommandState(Art::InfoCommand const &)
0x180061228  test    [rax], dil
0x18006122b  mov     bl, dil
0x18006122e  jnz     short loc_180061233
0x180061230  mov     bl, r15b
0x180061233  mov     rcx, [rsp+148h+var_108]
0x180061238  test    rcx, rcx
0x18006123b  jz      short loc_18006124D
0x18006123d  mov     rax, [rcx]
0x180061240  mov     edx, edi
0x180061242  mov     rax, [rax+28h]
0x180061246  call    cs:__guard_dispatch_icall_fptr
0x18006124c  nop
0x18006124d  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061255  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18006125a  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180061262  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061267  mov     al, bl
0x180061269  jmp     loc_18006202E
0x18006126e  call    ?AreSVGExtendedFeaturesEnabled@Art@@YA_NXZ; Art::AreSVGExtendedFeaturesEnabled(void)
0x180061273  mov     bl, al
0x180061275  mov     rcx, [rsp+148h+var_108]
0x18006127a  test    rcx, rcx
0x18006127d  jz      short loc_18006128F
0x18006127f  mov     rdx, [rcx]
0x180061282  mov     rax, [rdx+28h]
0x180061286  mov     edx, edi
0x180061288  call    cs:__guard_dispatch_icall_fptr
0x18006128e  nop
0x18006128f  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061297  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18006129c  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x1800612a4  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800612a9  mov     al, bl
0x1800612ab  jmp     loc_18006202E
0x1800612b0  cmp     ebx, 81F9h
0x1800612b6  jnz     short loc_1800612E4
0x1800612b8  mov     ecx, 228C687h
0x1800612bd  call    cs:__imp_MsoShipAssertTagProc
0x1800612c3  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x1800612cb  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800612d0  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x1800612d8  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800612dd  xor     al, al
0x1800612df  jmp     loc_18006202E
0x1800612e4  cmp     ebx, 6CA6h
0x1800612ea  jz      loc_180061E41
0x1800612f0  cmp     ebx, 880Eh
0x1800612f6  jz      loc_180061E41
0x1800612fc  cmp     ebx, 821Ch
0x180061302  jz      loc_180061E41
0x180061308  cmp     ebx, 6CA7h
0x18006130e  jz      loc_180061D06
0x180061314  cmp     ebx, 821Dh
0x18006131a  jz      loc_180061D06
0x180061320  cmp     ebx, 880Fh
0x180061326  jz      loc_180061D06
0x18006132c  cmp     ebx, 846Fh
0x180061332  jz      loc_180061D06
0x180061338  cmp     ebx, 8544h
0x18006133e  jnz     short loc_18006136C
0x180061340  mov     ecx, 233C444Bh
0x180061345  call    cs:__imp_MsoShipAssertTagProc
0x18006134b  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061353  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061358  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180061360  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061365  xor     al, al
0x180061367  jmp     loc_18006202E
0x18006136c  cmp     ebx, 6B8Ch
0x180061372  jnz     short loc_18006139C
0x180061374  call    ?FClipboardContainsImage@Art@@YA_NXZ; Art::FClipboardContainsImage(void)
0x180061379  mov     bl, al
0x18006137b  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061383  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061388  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180061390  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061395  mov     al, bl
0x180061397  jmp     loc_18006202E
0x18006139c  cmp     ebx, 5184h
0x1800613a2  jz      short loc_1800613B4
0x1800613a4  cmp     ebx, 84A3h
0x1800613aa  jz      short loc_1800613B4
0x1800613ac  cmp     ebx, 8791h
0x1800613b2  jnz     short loc_1800613E0
0x1800613b4  call    cs:__imp_?FEnableCommand@InsertMedia@@YA_NXZ; InsertMedia::FEnableCommand(void)
0x1800613ba  test    al, al
0x1800613bc  jz      short loc_1800613E0
0x1800613be  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x1800613c6  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800613cb  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x1800613d3  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x1800613d8  mov     al, dil
0x1800613db  jmp     loc_18006202E
0x1800613e0  cmp     ebx, 87F8h
0x1800613e6  jnz     short loc_180061459
0x1800613e8  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
0x1800613ed  mov     r8, rax
0x1800613f0  mov     rcx, [rax]
0x1800613f3  mov     rax, [rcx+0C8h]
0x1800613fa  mov     edx, 0A3h
0x1800613ff  mov     rcx, r8
0x180061402  call    cs:__guard_dispatch_icall_fptr
0x180061408  test    al, al
0x18006140a  jnz     short loc_18006142D
0x18006140c  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061414  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061419  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180061421  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061426  xor     al, al
0x180061428  jmp     loc_18006202E
0x18006142d  mov     ecx, 233C444Bh
0x180061432  call    cs:__imp_MsoShipAssertTagProc
0x180061438  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180061440  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061445  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x18006144d  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180061452  xor     al, al
0x180061454  jmp     loc_18006202E
0x180061459  cmp     ebx, 87F9h
0x18006145f  jnz     short loc_1800614D2
0x180061461  call    ?GetAppHost@Art@@YAAEAVIAppHost@1@XZ; Art::GetAppHost(void)
  ... truncated ...
```
