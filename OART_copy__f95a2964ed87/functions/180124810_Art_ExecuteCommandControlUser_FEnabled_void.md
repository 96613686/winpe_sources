# Art::ExecuteCommandControlUser::FEnabled(void)

- ea: `0x180124810`
- end: `0x180125a08`
- name: `?FEnabled@ExecuteCommandControlUser@Art@@MEAA_NXZ`
- size: `4600`
- prototype: `bool __fastcall(Art::ExecuteCommandControlUser *__hidden this)`
- caller_count: `1`
- callee_count: `37`
- tags: `broker_com_uri`

## callers

- `0x18000b710`

## callees

- `0x18011eb20`
- `0x18011f360`
- `0x180120a60`
- `0x180124600`
- `0x1801247e0`
- `0x180124810`
- `0x180125a10`
- `0x180125bc0`
- `0x1801281f0`
- `0x1801285f0`
- `0x18013dd70`
- `0x18013ddb0`
- `0x18013dfc0`
- `0x18013f070`
- `0x1801e5ef0`
- `0x1802071ec`
- `0x180253f90`
- `0x18025b4f8`
- `0x1802771a0`
- `0x180278e40`
- `0x180279050`
- `0x18035e2d8`
- `0x180376ac0`
- `0x1803a84d4`
- `0x1803a8540`
- `0x180404918`
- `0x1804092e4`
- `0x1805b0ff4`
- `0x18063ed80`
- `0x180644cb8`
- `0x18068fb50`
- `0x1806b65b8`
- `0x1806bc4f0`
- `0x1806bc6a8`
- `0x1806bcadc`
- `0x1806d19bc`
- `0x180711dd0`

## import_xrefs

- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x18012497c`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x180124a16`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x1801251bd`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x18012523c`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x18012497c`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x180124a16`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x1801251bd`
- `MSO!__imp_?FEnableCommand@InsertMedia@@YA_NXZ` at `0x18012523c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180124e6b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180124fbd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180124fe9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801250c1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18012513c`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180124e6b`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180124fbd`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180124fe9`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1801250c1`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18012513c`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180124932`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x180124932`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18012532b`
- `Mso20Win32Client!__imp_?Evaluate@FeatureGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x18012532b`

## pseudocode

```c
char __fastcall Art::ExecuteCommandControlUser::FEnabled(struct Ofc::CProxyPtrImpl **this)
{
  struct Ofc::CProxyPtrImpl **v2; // rsi
  struct Ofc::CProxyPtrImpl *v3; // rax
  void *Checked; // rax
  struct Ofc::CProxyPtrImpl **CurrentView; // rax
  int Tcid; // ebx
  unsigned __int64 v7; // rcx
  int v8; // r9d
  bool v9; // al
  Art::UserInterface *v10; // rax
  struct Art::Selection *CurrentSelection; // rax
  char v12; // di
  void *v13; // rax
  Art *v14; // rcx
  const struct Art::UserInterface *v15; // rdx
  Art::FeatureGates *v16; // rcx
  const struct Art::UserInterface *v17; // rdx
  void *v18; // rax
  char v19; // bl
  Art::View *v21; // rax
  Art *v22; // rax
  const struct Art::Selection *v23; // rdx
  bool valid; // bl
  void *v25; // rax
  char v26; // bl
  char v27; // bl
  void *v28; // rax
  bool v29; // bl
  bool v30; // bl
  struct Art::IAppHost *v31; // rax
  struct Art::IAppHost *v32; // rax
  Art *v33; // rcx
  struct Art::IAppHost *v34; // rax
  struct Art::IAppHost *AppHost; // rax
  char v36; // bl
  struct Art::IAppHost *v37; // rbx
  __int64 (__fastcall *v38)(struct Art::IAppHost *, void *); // rdi
  void *v39; // rax
  Art *v40; // rcx
  struct Art::IAppHost *v41; // rbx
  unsigned __int8 (__fastcall *v42)(struct Art::IAppHost *, void *); // rsi
  void *v43; // rax
  bool v44; // al
  struct Art::IAppHost *v45; // rbx
  unsigned __int8 (__fastcall *v46)(struct Art::IAppHost *, void *); // rsi
  void *v47; // rax
  Art::View *v48; // rax
  Art *v49; // rax
  const struct Art::Selection *v50; // rdx
  bool v51; // r8
  bool v52; // bl
  const struct Art::UserInterface *v53; // rdx
  bool v54; // bl
  const struct Art::UserInterface *v55; // rdx
  bool v56; // bl
  void *v57; // rax
  __int64 v58; // r8
  struct Ofc::CProxyPtrImpl **v59; // rax
  void *v60; // rax
  char v61; // bl
  int v62; // eax
  Art *v63; // rcx
  void *v64; // rax
  __int64 v65; // r8
  struct Ofc::CProxyPtrImpl **v66; // rax
  void *v67; // rax
  Art *v68; // rcx
  void *v69; // rax
  __int64 v70; // r8
  struct Ofc::CProxyPtrImpl **v71; // rax
  void *v72; // rax
  bool v73; // bl
  char v74; // bl
  struct Ofc::CProxyPtrImpl *v75; // [rsp+40h] [rbp-108h] BYREF
  __int64 v76; // [rsp+48h] [rbp-100h]
  __int64 v77; // [rsp+50h] [rbp-F8h] BYREF
  __int64 v78; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v79; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v80; // [rsp+68h] [rbp-E0h]
  __int64 v81; // [rsp+70h] [rbp-D8h] BYREF
  struct Ofc::CProxyPtrImpl *v82; // [rsp+78h] [rbp-D0h] BYREF
  _BYTE v83[184]; // [rsp+90h] [rbp-B8h] BYREF
  struct Ofc::CProxyPtrImpl *v84; // [rsp+150h] [rbp+8h] BYREF
  Ofc::CProxyPtrImpl *v85; // [rsp+158h] [rbp+10h] BYREF
  Ofc::CProxyPtrImpl *v86; // [rsp+160h] [rbp+18h] BYREF
  Art::FeatureGates *v87; // [rsp+168h] [rbp+20h] BYREF

  v2 = this + 4;
  v3 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(this[4]);
  v85 = v3;
  if ( !*((_QWORD *)v3 + 2) )
  {
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
    return 0;
  }
  Checked = Ofc::CProxyPtrImpl::GetChecked(v3);
  CurrentView = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(Checked, &v84, 0);
  v86 = Ofc::CProxyPtrImpl::StrongAddRef(*CurrentView);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
  Tcid = Art::ExecuteCommandControlUser::GetTcid((Art::ExecuteCommandControlUser *)this);
  if ( (unsigned __int8)Art::IsDeferredModel3DE2oSelected(v2)
    && (Tcid == 166 || Tcid == 167 || Tcid == 170 || Tcid == 171 || Tcid == 5736) )
  {
    goto LABEL_116;
  }
  if ( !(unsigned __int8)Art::IsDeferredImageSelected(v2)
    || (unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&byte_180E13D00) )
  {
    goto LABEL_4;
  }
  if ( Tcid > 27398 )
  {
    if ( Tcid != 27530 && Tcid != 27532 )
    {
      v7 = (unsigned int)(Tcid - 33984);
      if ( Tcid != 33984 && Tcid != 34706 )
        goto LABEL_4;
    }
LABEL_116:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
    return 0;
  }
  switch ( Tcid )
  {
    case 27398:
      goto LABEL_116;
    case 1362:
      goto LABEL_116;
    case 1440:
      goto LABEL_116;
    case 14826:
      goto LABEL_116;
  }
  v7 = (unsigned int)(Tcid - 22711);
  if ( Tcid == 22711 || Tcid == 27397 )
    goto LABEL_116;
LABEL_4:
  switch ( Tcid )
  {
    case 27818:
      v27 = Art::FEnabledAdvancedUISwitchForModel3D(v2);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return v27;
    case 931:
    case 2619:
    case 29811:
    case 5811:
    case 27817:
      goto LABEL_182;
    case 34744:
LABEL_122:
      AppHost = Art::GetAppHost((Art *)v7);
      v36 = (*(__int64 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)AppHost + 200LL))(AppHost, 163);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return v36;
    case 33387:
      MsoShipAssertTagProc(36840718);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return 0;
    case 33448:
    case 32730:
      v10 = (Art::UserInterface *)Ofc::CProxyPtrImpl::GetChecked(v85);
      CurrentSelection = Art::UserInterface::GetCurrentSelection(v10);
      if ( CurrentSelection )
      {
        v74 = Art::FDisableInsertInkDrawingCanvas(&v86, CurrentSelection) ^ 1;
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
        return v74;
      }
      goto LABEL_182;
  }
  v9 = byte_180E13A88 < 0
     ? Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180E13A88)
     : byte_180E13A88 != 0;
  if ( !v9 || InsertMedia::FEnableCommand((InsertMedia *)v7) )
  {
    LOBYTE(v7) = 0;
    if ( Tcid == 27088 || Tcid == 33904 )
    {
      v73 = Art::AreSVGExtendedFeaturesEnabled((Art *)v7);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return v73;
    }
    if ( Tcid == 27530 )
    {
      v75 = 0;
      if ( *((_QWORD *)v86 + 2)
        && (*((unsigned __int8 (__fastcall **)(struct Ofc::CProxyPtrImpl **, struct Ofc::CProxyPtrImpl **))*this + 22))(
             this,
             &v75) )
      {
        v29 = 0;
        if ( Art::AreSVGExtendedFeaturesEnabled((Art *)v7) )
        {
          v28 = Ofc::CProxyPtrImpl::GetChecked(v86);
          if ( (*(_BYTE *)Art::View::GetInfoCommandState(v28, &v84, v75) & 1) != 0 )
            v29 = 1;
        }
        if ( v75 )
          (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *, __int64))(*(_QWORD *)v75 + 40LL))(v75, 1);
      }
      else
      {
        v29 = Art::AreSVGExtendedFeaturesEnabled((Art *)v7);
        if ( v75 )
          (*(void (__fastcall **)(struct Ofc::CProxyPtrImpl *, __int64))(*(_QWORD *)v75 + 40LL))(v75, 1);
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return v29;
    }
    v12 = 1;
  }
  else
  {
    v12 = 1;
    LOBYTE(v7) = 1;
  }
  switch ( Tcid )
  {
    case 33273:
      MsoShipAssertTagProc(36226695);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return 0;
    case 27814:
    case 34830:
    case 33308:
      v75 = 0;
      v76 = 0;
      v79 = 0;
      v80 = 0;
      v81 = 0;
      v82 = 0;
      LOBYTE(v8) = 1;
      Art::InsertPictureListInfoCommand::InsertPictureListInfoCommand(
        (unsigned int)v83,
        (unsigned int)&v75,
        (unsigned int)&v79,
        v8,
        0,
        5,
        (__int64)&v85,
        (__int64)&v81);
      if ( !*((_QWORD *)v86 + 2) )
      {
        v69 = Ofc::CProxyPtrImpl::GetChecked(v85);
        LOBYTE(v70) = 1;
        v71 = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(v69, &v84, v70);
        Ofc::CProxyPtrImpl::StrongAssign(&v86, *v71);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
      }
      if ( !Art::FIsModel3DCfEnabled(v68)
        || (unsigned __int8)Art::IsDeferredModel3DE2oSelected(v2)
        || (v72 = Ofc::CProxyPtrImpl::GetChecked(v85),
            (*(_BYTE *)Art::UserInterface::GetInfoCommandState(v72, &v84, v83) & 1) == 0) )
      {
        v12 = 0;
      }
      Art::InsertPictureListInfoCommand::~InsertPictureListInfoCommand((Art::InsertPictureListInfoCommand *)v83);
      Ofc::TObjList<Ofc::TStrMap<Ofc::CVarStr>>::~TObjList<Ofc::TStrMap<Ofc::CVarStr>>((Ofc::CListImpl *)&v81);
      Ofc::TObjList<Ofc::CVarStr>::~TObjList<Ofc::CVarStr>((Ofc::CListImpl *)&v79);
      Ofc::TObjList<Ofc::CVarStr>::~TObjList<Ofc::CVarStr>((Ofc::CListImpl *)&v75);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return v12;
    case 27815:
    case 33309:
    case 34831:
    case 33903:
      v62 = 7;
      if ( (_BYTE)v7 && Tcid == 33309 )
        v62 = 5;
      v81 = 0;
      v82 = 0;
      v79 = 0;
      v80 = 0;
      v75 = 0;
      v76 = 0;
      LOBYTE(v8) = 1;
      Art::InsertPictureListInfoCommand::InsertPictureListInfoCommand(
        (unsigned int)v83,
        (unsigned int)&v81,
        (unsigned int)&v79,
        v8,
        0,
        v62,
        (__int64)&v85,
        (__int64)&v75);
      if ( !*((_QWORD *)v86 + 2) )
      {
        v64 = Ofc::CProxyPtrImpl::GetChecked(v85);
        LOBYTE(v65) = 1;
        v66 = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(v64, &v84, v65);
        Ofc::CProxyPtrImpl::StrongAssign(&v86, *v66);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
      }
      if ( !Art::FIsModel3DOnlineEnabled(v63)
        || (unsigned __int8)Art::IsDeferredModel3DE2oSelected(v2)
        || (v67 = Ofc::CProxyPtrImpl::GetChecked(v85),
            (*(_BYTE *)Art::UserInterface::GetInfoCommandState(v67, &v84, v83) & 1) == 0) )
      {
        v12 = 0;
      }
      Art::InsertPictureListInfoCommand::~InsertPictureListInfoCommand((Art::InsertPictureListInfoCommand *)v83);
      Ofc::TObjList<Ofc::TStrMap<Ofc::CVarStr>>::~TObjList<Ofc::TStrMap<Ofc::CVarStr>>((Ofc::CListImpl *)&v75);
      Ofc::TObjList<Ofc::CVarStr>::~TObjList<Ofc::CVarStr>((Ofc::CListImpl *)&v79);
      Ofc::TObjList<Ofc::CVarStr>::~TObjList<Ofc::CVarStr>((Ofc::CListImpl *)&v81);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return v12;
    case 34116:
      MsoShipAssertTagProc(591152203);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return 0;
    case 27532:
      v30 = Art::FClipboardContainsImage((Art *)v7);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return v30;
  }
  if ( (Tcid == 20868 || Tcid == 33955 || Tcid == 34705) && InsertMedia::FEnableCommand((InsertMedia *)v7) )
  {
LABEL_182:
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
    return 1;
  }
  switch ( Tcid )
  {
    case 34808:
      v31 = Art::GetAppHost((Art *)v7);
      if ( (*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)v31 + 200LL))(v31, 163) )
        MsoShipAssertTagProc(591152203);
      goto LABEL_116;
    case 34809:
      v32 = Art::GetAppHost((Art *)v7);
      if ( (*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)v32 + 200LL))(v32, 163) )
        MsoShipAssertTagProc(36840718);
      goto LABEL_116;
    case 34921:
      if ( !(unsigned __int8)Mso::AB::Optimized::ChangeGate::operator bool(&qword_180E1C2C0)
        || (v34 = Art::GetAppHost(v33),
            !(*(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, __int64))(*(_QWORD *)v34 + 200LL))(v34, 163)) )
      {
        v12 = 0;
      }
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
      Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
      return v12;
  }
  if ( ((unsigned int)(Tcid - 34745) <= 1 || Tcid == 34884) && InsertMedia::FEnableCommand((InsertMedia *)v7) )
    goto LABEL_122;
  if ( Tcid == 1031 )
    goto LABEL_182;
  v84 = Ofc::CProxyPtrImpl::CheckedStrongAddRef(*v2);
  v13 = Ofc::CProxyPtrImpl::GetChecked(v84);
  Art::UserInterface::GetCurrentView(v13, &v87, 0);
  Ofc::CProxyPtrImpl::DtorStrongRelease(&v84);
  v14 = v87;
  if ( !*((_QWORD *)v87 + 2) )
    goto LABEL_159;
  if ( Tcid != 34044 )
  {
    switch ( Tcid )
    {
      case 34218:
        if ( !Dr::FInsertStockVideoEnabled(v87)
          || (v41 = Art::GetAppHost(v40),
              v42 = *(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, void *))(*(_QWORD *)v41 + 744LL),
              v43 = Ofc::CProxyPtrImpl::GetChecked(v87),
              !v42(v41, v43)) )
        {
          v12 = 0;
        }
        break;
      case 34800:
        if ( byte_180E1C330 < 0 )
          v44 = Mso::AB::Optimized::FeatureGate::Evaluate((Mso::AB::Optimized::FeatureGate *)&byte_180E1C330);
        else
          v44 = byte_180E1C330 != 0;
        if ( !v44
          || (v45 = Art::GetAppHost(v14),
              v46 = *(unsigned __int8 (__fastcall **)(struct Art::IAppHost *, void *))(*(_QWORD *)v45 + 760LL),
              v47 = Ofc::CProxyPtrImpl::GetChecked(v87),
              !v46(v45, v47)) )
        {
          v12 = 0;
        }
        break;
      case 33412:
        v21 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v87);
        v22 = Art::View::EnsureAggregateSelection(v21);
        valid = Art::FContainsValidAnimatableModel3DE2os(v22, v23);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
        return valid;
      case 33891:
        v48 = (Art::View *)Ofc::CProxyPtrImpl::GetChecked(v87);
        v49 = Art::View::EnsureAggregateSelection(v48);
        v52 = Art::FAnyPlayableViewElementInSelection(v49, v50, v51);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
        return v52;
      case 34307:
      case 34818:
        if ( Art::FeatureGates::FInsertLiveFeedEnabled(v87) )
        {
          if ( !*((_QWORD *)v86 + 2) )
          {
            v57 = Ofc::CProxyPtrImpl::GetChecked(v85);
            LOBYTE(v58) = 1;
            v59 = (struct Ofc::CProxyPtrImpl **)Art::UserInterface::GetCurrentView(v57, &v75, v58);
            Ofc::CProxyPtrImpl::StrongAssign(&v86, *v59);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v75);
          }
          Art::InsertCameoInfoCommand::InsertCameoInfoCommand((Art::InsertCameoInfoCommand *)&v81);
          v60 = Ofc::CProxyPtrImpl::GetChecked(v85);
          v61 = *(_BYTE *)Art::UserInterface::GetInfoCommandState(v60, &v84, &v81) & 1;
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v82);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
          Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
          return v61;
        }
LABEL_159:
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
        Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
        return 0;
      default:
        if ( (unsigned int)(Tcid - 34488) <= 2 )
        {
          if ( Art::FeatureGates::FInsertLiveFeedEnabled(v87) )
          {
            v56 = Art::FSelectionContainsOnlyLiveFeed(*((Art **)v85 + 2), v55);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
            return v56;
          }
          goto LABEL_159;
        }
        if ( Tcid == 34819 )
        {
          if ( Art::FeatureGates::FInsertLiveFeedEnabled(v87) )
          {
            v54 = Art::FSelectionContainsOnlyOneLiveFeed(*((Art **)v85 + 2), v53);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
            Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
            return v54;
          }
          goto LABEL_159;
        }
        goto LABEL_51;
    }
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
    return v12;
  }
  if ( InsertMedia::FEnableCommand(v87) )
  {
    v37 = Art::GetAppHost(v14);
    v38 = *(__int64 (__fastcall **)(struct Art::IAppHost *, void *))(*(_QWORD *)v37 + 744LL);
    v39 = Ofc::CProxyPtrImpl::GetChecked(v87);
    LOBYTE(v37) = v38(v37, v39);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
    return (char)v37;
  }
LABEL_51:
  if ( Art::FeatureGates::FLiveFeedEnabled(v14) && Art::FSelectionContainsOnlyLiveFeed(*((Art **)v85 + 2), v15) )
  {
    switch ( Tcid )
    {
      case 14826:
        goto LABEL_159;
      case 27175:
        goto LABEL_159;
      case 27397:
        goto LABEL_159;
      case 27398:
        goto LABEL_159;
    }
    v16 = (Art::FeatureGates *)(unsigned int)(Tcid - 33984);
    if ( Tcid == 33984 || Tcid == 34706 )
      goto LABEL_159;
  }
  if ( Art::FeatureGates::FInsertLiveFeedEnabled(v16)
    && Tcid == 164
    && Art::FSelectionContainsAtLeastOneCameo(*((Art **)v85 + 2), v17) )
  {
    goto LABEL_159;
  }
  v78 = 0;
  v77 = 0;
  if ( (*((unsigned __int8 (__fastcall **)(struct Ofc::CProxyPtrImpl **, __int64 *))*this + 22))(this, &v78) )
  {
    v18 = Ofc::CProxyPtrImpl::GetChecked(v87);
    v19 = *(_BYTE *)Art::View::GetInfoCommandState(v18, &v84, v78) & 1;
    if ( v78 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v78 + 40LL))(v78, 1);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
    return v19;
  }
  else if ( (*((unsigned __int8 (__fastcall **)(struct Ofc::CProxyPtrImpl **, __int64 *))*this + 23))(this, &v77) )
  {
    v25 = Ofc::CProxyPtrImpl::GetChecked(v87);
    v26 = *(_BYTE *)Art::View::GetCommandState(v25, &v84, v77) & 1;
    if ( v77 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v77 + 168LL))(v77, 1);
    if ( v78 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v78 + 40LL))(v78, 1);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
    return v26;
  }
  else
  {
    if ( v77 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v77 + 168LL))(v77, 1);
    if ( v78 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v78 + 40LL))(v78, 1);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v87);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v86);
    Ofc::CProxyPtrImpl::DtorStrongRelease(&v85);
    return 0;
  }
}

```

## disassembly

```asm
0x180124810  push    rbx
0x180124812  push    rsi
0x180124813  push    rdi
0x180124814  push    r14
0x180124816  push    r15
0x180124818  sub     rsp, 120h
0x18012481f  mov     r14, rcx
0x180124822  lea     rsi, [rcx+20h]
0x180124826  mov     rcx, [rsi]; struct Ofc::CProxyPtrImpl *
0x180124829  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x18012482e  mov     [rsp+148h+arg_8], rax
0x180124836  xor     r15d, r15d
0x180124839  cmp     [rax+10h], r15
0x18012483d  jz      loc_180124D11
0x180124843  mov     rcx, rax; this
0x180124846  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18012484b  xor     r8d, r8d
0x18012484e  lea     rdx, [rsp+148h+arg_0]
0x180124856  mov     rcx, rax
0x180124859  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x18012485e  mov     rcx, [rax]; struct Ofc::CProxyPtrImpl *
0x180124861  call    ?StrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::StrongAddRef(Ofc::CProxyPtrImpl *)
0x180124866  mov     [rsp+148h+arg_10], rax
0x18012486e  lea     rcx, [rsp+148h+arg_0]; struct Ofc::CProxyPtrImpl **
0x180124876  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x18012487b  mov     rcx, r14; this
0x18012487e  call    ?GetTcid@ExecuteCommandControlUser@Art@@IEAAHXZ; Art::ExecuteCommandControlUser::GetTcid(void)
0x180124883  mov     ebx, eax
0x180124885  mov     rcx, rsi
0x180124888  call    ?IsDeferredModel3DE2oSelected@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::IsDeferredModel3DE2oSelected(Ofc::TWeakPtr<Art::UserInterface> const &)
0x18012488d  test    al, al
0x18012488f  jnz     loc_180124D25
0x180124895  mov     rcx, rsi
0x180124898  call    ?IsDeferredImageSelected@Art@@YA_NAEBV?$TWeakPtr@VUserInterface@Art@@@Ofc@@@Z; Art::IsDeferredImageSelected(Ofc::TWeakPtr<Art::UserInterface> const &)
0x18012489d  test    al, al
0x18012489f  jnz     loc_180124D69
0x1801248a5  cmp     ebx, 6CAAh
0x1801248ab  jz      loc_180124DF8
0x1801248b1  cmp     ebx, 3A3h
0x1801248b7  jz      loc_1801259D7
0x1801248bd  cmp     ebx, 0A3Bh
0x1801248c3  jz      loc_1801259D7
0x1801248c9  cmp     ebx, 7473h
0x1801248cf  jz      loc_1801259D7
0x1801248d5  cmp     ebx, 16B3h
0x1801248db  jz      loc_1801259D7
0x1801248e1  cmp     ebx, 6CA9h
0x1801248e7  jz      loc_1801259D7
0x1801248ed  cmp     ebx, 87B8h
0x1801248f3  jz      loc_180124E23
0x1801248f9  cmp     ebx, 826Bh
0x1801248ff  jz      loc_180124E66
0x180124905  cmp     ebx, 82A8h
0x18012490b  jz      short loc_18012493A
0x18012490d  cmp     ebx, 7FDAh
0x180124913  jz      short loc_18012493A
0x180124915  mov     al, cs:byte_180E13A88
0x18012491b  test    al, al
0x18012491d  js      short loc_18012492B
0x18012491f  setnz   al
0x180124922  test    al, al
0x180124924  jnz     short loc_18012497C
0x180124926  jmp     loc_180124E92
0x18012492b  lea     rcx, byte_180E13A88
0x180124932  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x180124938  jmp     short loc_180124922
0x18012493a  mov     rcx, [rsp+148h+arg_8]; this
0x180124942  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180124947  mov     rcx, rax; this
0x18012494a  call    ?GetCurrentSelection@UserInterface@Art@@QEAAPEAVSelection@2@XZ; Art::UserInterface::GetCurrentSelection(void)
0x18012494f  test    rax, rax
0x180124952  jnz     loc_18012599A
0x180124958  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180124960  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124965  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x18012496d  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124972  mov     eax, 1
0x180124977  jmp     loc_180124A87
0x18012497c  call    cs:__imp_?FEnableCommand@InsertMedia@@YA_NXZ; InsertMedia::FEnableCommand(void)
0x180124982  test    al, al
0x180124984  jnz     loc_180124E92
0x18012498a  mov     edi, 1
0x18012498f  mov     cl, dil; this
0x180124992  cmp     ebx, 81F9h
0x180124998  jz      loc_180124FB8
0x18012499e  cmp     ebx, 6CA6h
0x1801249a4  jz      loc_18012583C
0x1801249aa  cmp     ebx, 880Eh
0x1801249b0  jz      loc_18012583C
0x1801249b6  cmp     ebx, 821Ch
0x1801249bc  jz      loc_18012583C
0x1801249c2  cmp     ebx, 6CA7h
0x1801249c8  jz      loc_1801256F5
0x1801249ce  cmp     ebx, 821Dh
0x1801249d4  jz      loc_1801256F5
0x1801249da  cmp     ebx, 880Fh
0x1801249e0  jz      loc_1801256F5
0x1801249e6  cmp     ebx, 846Fh
0x1801249ec  jz      loc_1801256F5
0x1801249f2  cmp     ebx, 8544h
0x1801249f8  jz      loc_180124FE4
0x1801249fe  cmp     ebx, 6B8Ch
0x180124a04  jz      loc_180125010
0x180124a0a  cmp     ebx, 5184h
0x180124a10  jnz     loc_180125038
0x180124a16  call    cs:__imp_?FEnableCommand@InsertMedia@@YA_NXZ; InsertMedia::FEnableCommand(void)
0x180124a1c  test    al, al
0x180124a1e  jnz     loc_180125055
0x180124a24  cmp     ebx, 87F8h
0x180124a2a  jz      loc_180125077
0x180124a30  cmp     ebx, 87F9h
0x180124a36  jz      loc_1801250E8
0x180124a3c  cmp     ebx, 8869h
0x180124a42  jz      loc_180125164
0x180124a48  lea     eax, [rbx-87B9h]
0x180124a4e  cmp     eax, edi
0x180124a50  jbe     loc_1801251BD
0x180124a56  cmp     ebx, 8844h
0x180124a5c  jz      loc_1801251BD
0x180124a62  cmp     ebx, 407h
0x180124a68  jnz     short loc_180124A96
0x180124a6a  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180124a72  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124a77  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180124a7f  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124a84  mov     al, dil
0x180124a87  add     rsp, 120h
0x180124a8e  pop     r15
0x180124a90  pop     r14
0x180124a92  pop     rdi
0x180124a93  pop     rsi
0x180124a94  pop     rbx
0x180124a95  retn
0x180124a96  mov     rcx, [rsi]; struct Ofc::CProxyPtrImpl *
0x180124a99  call    ?CheckedStrongAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::CheckedStrongAddRef(Ofc::CProxyPtrImpl *)
0x180124a9e  mov     [rsp+148h+arg_0], rax
0x180124aa6  mov     rcx, rax; this
0x180124aa9  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180124aae  xor     r8d, r8d
0x180124ab1  lea     rdx, [rsp+148h+arg_18]
0x180124ab9  mov     rcx, rax
0x180124abc  call    ?GetCurrentView@UserInterface@Art@@QEAA?AV?$TSharedPtr@VView@Art@@@Ofc@@_N@Z; Art::UserInterface::GetCurrentView(bool)
0x180124ac1  nop
0x180124ac2  lea     rcx, [rsp+148h+arg_0]; struct Ofc::CProxyPtrImpl **
0x180124aca  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124acf  mov     rcx, [rsp+148h+arg_18]; this
0x180124ad7  cmp     [rcx+10h], r15
0x180124adb  jz      loc_18012520E
0x180124ae1  cmp     ebx, 84FCh
0x180124ae7  jz      loc_18012523C
0x180124aed  cmp     ebx, 85AAh
0x180124af3  jz      loc_1801252A8
0x180124af9  cmp     ebx, 87F0h
0x180124aff  jz      loc_180125315
0x180124b05  cmp     ebx, 8284h
0x180124b0b  jz      loc_180124C20
0x180124b11  cmp     ebx, 8463h
0x180124b17  jz      loc_180125399
0x180124b1d  cmp     ebx, 8603h
0x180124b23  jz      loc_18012560F
0x180124b29  cmp     ebx, 8802h
0x180124b2f  jz      loc_18012560F
0x180124b35  lea     eax, [rbx-86B8h]
0x180124b3b  cmp     eax, 2
0x180124b3e  jbe     loc_180125597
0x180124b44  cmp     ebx, 8803h
0x180124b4a  jz      loc_1801253DE
0x180124b50  call    ?FLiveFeedEnabled@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FLiveFeedEnabled(void)
0x180124b55  test    al, al
0x180124b57  jnz     loc_180125457
0x180124b5d  call    ?FInsertLiveFeedEnabled@FeatureGates@Art@@YA_NXZ; Art::FeatureGates::FInsertLiveFeedEnabled(void)
0x180124b62  test    al, al
0x180124b64  jnz     loc_1801254D9
0x180124b6a  mov     [rsp+148h+var_F0], r15
0x180124b6f  mov     [rsp+148h+var_F8], r15
0x180124b74  mov     rax, [r14]
0x180124b77  lea     rdx, [rsp+148h+var_F0]
0x180124b7c  mov     rcx, r14
0x180124b7f  mov     rax, [rax+0B0h]
0x180124b86  call    cs:__guard_dispatch_icall_fptr
0x180124b8c  test    al, al
0x180124b8e  jz      loc_180124C65
0x180124b94  mov     rcx, [rsp+148h+arg_18]; this
0x180124b9c  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180124ba1  mov     r8, [rsp+148h+var_F0]
0x180124ba6  lea     rdx, [rsp+148h+arg_0]
0x180124bae  mov     rcx, rax
0x180124bb1  call    ?GetInfoCommandState@View@Art@@QEBA?BVCommandState@2@AEBVInfoCommand@2@@Z; Art::View::GetInfoCommandState(Art::InfoCommand const &)
0x180124bb6  mov     bl, [rax]
0x180124bb8  and     bl, dil
0x180124bbb  mov     rcx, [rsp+148h+var_F8]
0x180124bc0  test    rcx, rcx
0x180124bc3  jz      short loc_180124BD8
0x180124bc5  mov     rax, [rcx]
0x180124bc8  mov     edx, edi
0x180124bca  mov     rax, [rax+0A8h]
0x180124bd1  call    cs:__guard_dispatch_icall_fptr
0x180124bd7  nop
0x180124bd8  mov     rcx, [rsp+148h+var_F0]
0x180124bdd  test    rcx, rcx
0x180124be0  jz      short loc_180124BF2
0x180124be2  mov     rax, [rcx]
0x180124be5  mov     edx, edi
0x180124be7  mov     rax, [rax+28h]
0x180124beb  call    cs:__guard_dispatch_icall_fptr
0x180124bf1  nop
0x180124bf2  lea     rcx, [rsp+148h+arg_18]; struct Ofc::CProxyPtrImpl **
0x180124bfa  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124bff  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180124c07  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124c0c  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180124c14  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124c19  mov     al, bl
0x180124c1b  jmp     loc_180124A87
0x180124c20  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180124c25  mov     rcx, rax; this
0x180124c28  call    ?EnsureAggregateSelection@View@Art@@AEAAAEAVSelection@2@XZ; Art::View::EnsureAggregateSelection(void)
0x180124c2d  mov     rcx, rax; this
0x180124c30  call    ?FContainsValidAnimatableModel3DE2os@Art@@YA_NAEBVSelection@1@@Z; Art::FContainsValidAnimatableModel3DE2os(Art::Selection const &)
0x180124c35  mov     bl, al
0x180124c37  lea     rcx, [rsp+148h+arg_18]; struct Ofc::CProxyPtrImpl **
0x180124c3f  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124c44  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180124c4c  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124c51  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180124c59  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124c5e  mov     al, bl
0x180124c60  jmp     loc_180124A87
0x180124c65  mov     rax, [r14]
0x180124c68  lea     rdx, [rsp+148h+var_F8]
0x180124c6d  mov     rcx, r14
0x180124c70  mov     rax, [rax+0B8h]
0x180124c77  call    cs:__guard_dispatch_icall_fptr
0x180124c7d  test    al, al
0x180124c7f  jz      loc_18012552C
0x180124c85  mov     rcx, [rsp+148h+arg_18]; this
0x180124c8d  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x180124c92  mov     r8, [rsp+148h+var_F8]
0x180124c97  lea     rdx, [rsp+148h+arg_0]
0x180124c9f  mov     rcx, rax
0x180124ca2  call    ?GetCommandState@View@Art@@QEBA?BVCommandState@2@AEBVCommand@2@@Z; Art::View::GetCommandState(Art::Command const &)
0x180124ca7  mov     bl, [rax]
0x180124ca9  and     bl, dil
0x180124cac  mov     rcx, [rsp+148h+var_F8]
0x180124cb1  test    rcx, rcx
0x180124cb4  jz      short loc_180124CC9
0x180124cb6  mov     rax, [rcx]
0x180124cb9  mov     edx, edi
0x180124cbb  mov     rax, [rax+0A8h]
0x180124cc2  call    cs:__guard_dispatch_icall_fptr
0x180124cc8  nop
0x180124cc9  mov     rcx, [rsp+148h+var_F0]
0x180124cce  test    rcx, rcx
0x180124cd1  jz      short loc_180124CE3
0x180124cd3  mov     rax, [rcx]
0x180124cd6  mov     edx, edi
0x180124cd8  mov     rax, [rax+28h]
0x180124cdc  call    cs:__guard_dispatch_icall_fptr
0x180124ce2  nop
0x180124ce3  lea     rcx, [rsp+148h+arg_18]; struct Ofc::CProxyPtrImpl **
0x180124ceb  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124cf0  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180124cf8  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124cfd  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180124d05  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124d0a  mov     al, bl
0x180124d0c  jmp     loc_180124A87
0x180124d11  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180124d19  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124d1e  xor     al, al
0x180124d20  jmp     loc_180124A87
0x180124d25  mov     eax, ebx
0x180124d27  sub     eax, 0A6h
0x180124d2c  jz      short loc_180124D48
0x180124d2e  sub     eax, 1
0x180124d31  jz      short loc_180124D48
0x180124d33  sub     eax, 3
0x180124d36  jz      short loc_180124D48
0x180124d38  sub     eax, 1
0x180124d3b  jz      short loc_180124D48
0x180124d3d  cmp     eax, 15BDh
0x180124d42  jnz     loc_180124895
0x180124d48  lea     rcx, [rsp+148h+arg_10]; struct Ofc::CProxyPtrImpl **
0x180124d50  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124d55  lea     rcx, [rsp+148h+arg_8]; struct Ofc::CProxyPtrImpl **
0x180124d5d  call    ?DtorStrongRelease@CProxyPtrImpl@Ofc@@KAXAEAPEAV12@@Z; Ofc::CProxyPtrImpl::DtorStrongRelease(Ofc::CProxyPtrImpl * &)
0x180124d62  xor     al, al
0x180124d64  jmp     loc_180124A87
0x180124d69  lea     rcx, byte_180E13D00
0x180124d70  call    ??BChangeGate@Optimized@AB@Mso@@QEGBA_NXZ; Mso::AB::Optimized::ChangeGate::operator bool(void)
0x180124d75  test    al, al
0x180124d77  jnz     loc_1801248A5
0x180124d7d  mov     eax, 6B06h
0x180124d82  cmp     ebx, eax
0x180124d84  jg      short loc_180124DB4
0x180124d86  jz      short loc_180124DD7
0x180124d88  mov     ecx, ebx
0x180124d8a  sub     ecx, 552h
0x180124d90  jz      short loc_180124DD7
0x180124d92  sub     ecx, 4Eh ; 'N'
  ... truncated ...
```
