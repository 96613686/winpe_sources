# Art::CPropConverterToLegacy::CreateHsp(bool,MSOSP *,MSOSPT,bool,bool,MSOSP *,bool)

- ea: `0x18036ac00`
- end: `0x18036b94c`
- name: `?CreateHsp@CPropConverterToLegacy@Art@@UEAAPEAUMSOSP@@_NPEAU3@W4MSOSPT@@0010@Z`
- size: `3404`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation`

## callees

- `0x180040fb0`
- `0x180064914`
- `0x180070fe0`
- `0x180071720`
- `0x1801c75d0`
- `0x1801ca10c`
- `0x1801cb114`
- `0x1801d59e8`
- `0x18020b040`
- `0x18020b1c4`
- `0x18020b8dc`
- `0x18020df88`
- `0x180266440`
- `0x18036ac00`
- `0x18036b94c`
- `0x18036b9cc`
- `0x18036ba6c`
- `0x18036bab0`
- `0x1804881b0`
- `0x18054fff8`
- `0x18064f688`
- `0x1806a5084`
- `0x1806c9318`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoFIsNinch@@YAHW4MSOPID@@PEBX_K@Z` at `0x18036b642`
- `Mso98Win32Client!__imp_?MsoFIsNinch@@YAHW4MSOPID@@PEBX_K@Z` at `0x18036b642`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x18036ad63`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x18036ad79`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x18036ad63`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x18036ad79`
- `Mso98Win32Client!__imp_?MsoFreePropSet@@YAXW4MSOPSID@@PEBX@Z` at `0x18036b32b`
- `Mso98Win32Client!__imp_?MsoFreePropSet@@YAXW4MSOPSID@@PEBX@Z` at `0x18036b940`
- `Mso98Win32Client!__imp_?MsoFreePropSet@@YAXW4MSOPSID@@PEBX@Z` at `0x18036b32b`
- `Mso98Win32Client!__imp_?MsoFreePropSet@@YAXW4MSOPSID@@PEBX@Z` at `0x18036b940`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18036b37a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18036b89f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18036b91e`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18036b37a`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18036b89f`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x18036b91e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18036b2eb`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18036b30f`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18036b2eb`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x18036b30f`

## pseudocode

```c
struct MSOSP *__fastcall Art::CPropConverterToLegacy::CreateHsp(
        __int64 a1,
        char a2,
        __int64 a3,
        int a4,
        unsigned __int8 a5,
        char a6,
        struct MSOSP *a7,
        char a8)
{
  char v8; // bl
  __int64 v9; // r15
  __int64 v12; // rcx
  __int64 v13; // r13
  __int64 v14; // rdi
  void *Checked; // rax
  char v16; // r12
  __int64 v17; // rcx
  void (__fastcall *v18)(__int64, _DWORD *, __int64); // rdi
  __int64 v19; // r8
  __int64 v20; // r8
  __int64 v21; // rcx
  bool v22; // r8
  int v23; // eax
  int v24; // edi
  _DWORD *v25; // r12
  void *v26; // rax
  void *v27; // rax
  __int64 v28; // r8
  void *v29; // rax
  unsigned __int8 v30; // r15
  void *v31; // rax
  __int64 v32; // rcx
  void *v33; // rax
  bool v34; // di
  char v35; // al
  void *v36; // rax
  void *v37; // rax
  void *v38; // rax
  void *v39; // rax
  void *v40; // rax
  void *v41; // rax
  int v42; // eax
  char v43; // cl
  __int64 v44; // r14
  void *v45; // rax
  void *v46; // rax
  void *v47; // rax
  void *v48; // rdx
  struct MSOSP *v49; // rbx
  void *v51; // rax
  unsigned int (__fastcall *v52)(struct MSOSP *, __int64 *, _QWORD); // rdi
  __int64 v53; // rcx
  void *v54; // rax
  __int64 v55; // r8
  bool v56; // r8
  void *v57; // rax
  void *v58; // rax
  int v59; // eax
  char v60; // cl
  __int64 v61; // rdi
  __int64 v62; // rcx
  const struct Art::PresetGeometry2D *v63; // rax
  void *v64; // rax
  void *v65; // rax
  void *v66; // rax
  void *v67; // rax
  void *v68; // rax
  __int64 v69; // [rsp+20h] [rbp-E0h]
  struct MSOSP *v70; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v71; // [rsp+78h] [rbp-88h] BYREF
  __int64 v72; // [rsp+80h] [rbp-80h] BYREF
  int v73; // [rsp+88h] [rbp-78h] BYREF
  struct MSOSP *v74; // [rsp+90h] [rbp-70h]
  __int64 v75; // [rsp+98h] [rbp-68h]
  int v76; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-58h]
  int v78; // [rsp+B0h] [rbp-50h]
  unsigned int v79; // [rsp+B4h] [rbp-4Ch]
  int v80; // [rsp+B8h] [rbp-48h]
  __int128 v81; // [rsp+C0h] [rbp-40h]
  __int64 v82; // [rsp+D0h] [rbp-30h]
  _QWORD v83[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v84; // [rsp+E8h] [rbp-18h]
  _DWORD v85[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v86[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v87[8]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v88[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v89[64]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v90[4]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v91; // [rsp+1A0h] [rbp+A0h]
  _BYTE v92[288]; // [rsp+250h] [rbp+150h] BYREF
  char v93; // [rsp+370h] [rbp+270h]
  _BYTE v94[320]; // [rsp+380h] [rbp+280h] BYREF
  char v95; // [rsp+4C0h] [rbp+3C0h]
  _BYTE v96[176]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v97[192]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v98[368]; // [rsp+640h] [rbp+540h] BYREF
  __int128 v99; // [rsp+7B0h] [rbp+6B0h] BYREF
  _DWORD v100[4]; // [rsp+7C0h] [rbp+6C0h] BYREF
  _BYTE v101[80]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _BYTE v102[112]; // [rsp+820h] [rbp+720h] BYREF

  v9 = a4;
  v75 = a3;
  v74 = a7;
  v83[0] = &Art::SafeUndo::`vftable';
  v12 = *(_QWORD *)(a1 + 8);
  v13 = 1;
  if ( *(_DWORD *)(v12 + 4) != 0x80000000 )
    _InterlockedAdd((volatile signed __int32 *)(v12 + 4), 1u);
  v83[1] = v12;
  v14 = 0;
  v84 = 0;
  Checked = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
  (*(void (__fastcall **)(void *))(*(_QWORD *)Checked + 120LL))(Checked);
  if ( (_DWORD)v9 != 75 )
    goto LABEL_56;
LABEL_4:
  v16 = v13;
  while ( 1 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) == v14 )
    {
      MsoShipAssertTagProc(3736918);
      Ofc::CAbortException::ThrowTag(0, 3736919);
LABEL_100:
      Art::CPropConverterToLegacy::TranslateCallout(
        (const struct MSOPSGeometry *)v92,
        (const struct Art::PresetGeometry2D *)&v76,
        (struct MSOPSCallout *)v102);
      goto LABEL_13;
    }
    memset_0(v98, 0, 0x168u);
    memset_0(v92, 0, sizeof(v92));
    v93 = v14;
    memset_0(v85, 0, 0x48u);
    memset_0(v101, 0, sizeof(v101));
    memset_0(v90, 0, 0xC8u);
    memset_0(v96, 0, 0xA8u);
    memset_0(v97, 0, 0xB8u);
    memset_0(v102, 0, 0x68u);
    v70 = (struct MSOSP *)v14;
    v95 = v14;
    MsoGetPropSetNinch(4);
    v99 = 0;
    MsoGetPropSetNinch(0);
    if ( *(_BYTE *)(a1 + 304) == 2 )
    {
      v18 = *(void (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)a1 + 432LL);
      LOBYTE(v17) = *(_BYTE *)(a1 + 304);
      Ofc::ThrowIfInvalidQualifiedValueState(v17);
      v18(a1, v85, a1 + 232);
      v14 = 0;
    }
    Art::CPropConverterToLegacy::TranslateGroupTransform((Art::CPropConverterToLegacy *)a1, (struct Ofc::CRect *)&v99);
    LOBYTE(v19) = v13;
    (*(void (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 272LL))(a1, v90, v19);
    if ( v16 )
      v90[0] = v9;
    v73 = v91;
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 368LL))(a1, &v73);
    v91 = v73;
    LOBYTE(v20) = v13;
    (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 264LL))(a1, v101, v20);
    v8 = v14;
    v76 = v14;
    v13 = v14;
    v77 = v14;
    v78 = v14;
    v79 = 0x80000000;
    v80 = v14;
    v81 = 0;
    v82 = v14;
    if ( *(_BYTE *)(a1 + 224) == 2 )
    {
      LOBYTE(v21) = *(_BYTE *)(a1 + 224);
      Ofc::ThrowIfInvalidQualifiedValueState(v21);
      if ( (unsigned __int8)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(a1 + 208) )
      {
        LOBYTE(v62) = *(_BYTE *)(a1 + 224);
        Ofc::ThrowIfInvalidQualifiedValueState(v62);
        v63 = (const struct Art::PresetGeometry2D *)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Get<Art::Geom::Preset>(a1 + 208);
        Art::PresetGeometry2D::PresetGeometry2D((Art::PresetGeometry2D *)v89, v63);
        Art::PresetTextShape::Swap((Art::PresetTextShape *)&v76, (struct Art::PresetTextShape *)v89);
        Art::PresetTextShape::~PresetTextShape((Art::PresetTextShape *)v89);
        if ( (unsigned int)(v80 - 104) <= 0xB )
          v8 = 1;
        v13 = v77;
        LODWORD(v14) = 0;
      }
      else
      {
        LODWORD(v14) = 0;
      }
    }
    if ( !a2 )
    {
      Art::CPropConverterToLegacy::TranslateGeoText((Art::CPropConverterToLegacy *)a1, (struct MSOPSGeoText *)v97, v22);
      Art::CPropConverterToLegacy::TranslateFillProps((Art::CPropConverterToLegacy *)a1, (struct MSOPSBlip *)v94, 1);
      if ( *(_BYTE *)(a1 + 144) == 2 )
        (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 288LL))(a1, v94);
      Art::CPropConverterToLegacy::Translate3D((Art::CPropConverterToLegacy *)a1);
      LOBYTE(v55) = 1;
      (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 232LL))(a1, v98, v55);
      (*(void (__fastcall **)(__int64, _DWORD *, _BYTE *))(*(_QWORD *)a1 + 248LL))(a1, v85, v92);
      Art::CPropConverterToLegacy::TranslateText((Art::CPropConverterToLegacy *)a1, (struct MSOPSText *)v96, v56);
    }
    if ( v8 )
      goto LABEL_100;
LABEL_13:
    v100[0] = v85[0];
    v100[1] = v85[2];
    v100[2] = v85[4];
    v100[3] = v85[6];
    v23 = v14;
    LOBYTE(v23) = *(_BYTE *)(a1 + 2053) != (unsigned __int8)v14;
    if ( !v90[0] || v90[0] == 20 )
      v23 |= 4u;
    v24 = v23 | 2;
    if ( !a2 )
      v24 = v23;
    v25 = v100;
    if ( *(_QWORD *)(a1 + 1944) )
      v25 = 0;
    v71 = v90[0];
    if ( !a2 && (unsigned int)MsoFIsNinch(768, &v71, 4) )
      v71 = v9;
    v9 = 0;
    if ( *(_BYTE *)(a1 + 2049) && *(_DWORD *)(a1 + 496) == 6 )
    {
      v72 = 0;
      if ( (unsigned __int8)Dr::FIsInkDisp2Ink(a1 + 88) )
      {
        Dr::CopyInkDisp2StrokesToLegacyInkObject(a1 + 88, &v72);
      }
      else
      {
        v61 = *(_QWORD *)(a1 + 88);
        if ( v61 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 8LL))(v61);
        if ( v72 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
        v72 = v61;
      }
      v57 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      LODWORD(v69) = 0;
      v14 = (*(unsigned int (__fastcall **)(void *, struct MSOSP **, _DWORD *, _QWORD, __int64, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _DWORD, int))(*(_QWORD *)v57 + 464LL))(
              v57,
              &v70,
              v25,
              *(_QWORD *)(a1 + 1944),
              v69,
              0,
              v72,
              0,
              0,
              0,
              *(unsigned __int8 *)(a1 + 2053),
              1);
      if ( v72 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
    }
    else
    {
      if ( v74 )
      {
        v14 = 1;
        v70 = v74;
      }
      else
      {
        v26 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
        v14 = (*(unsigned int (__fastcall **)(void *, struct MSOSP **, _QWORD, _DWORD *, _QWORD, _QWORD, _QWORD, _QWORD, int, int))(*(_QWORD *)v26 + 1336LL))(
                v26,
                &v70,
                v71,
                v25,
                *(_QWORD *)(a1 + 1944),
                0,
                0,
                0,
                v24,
                -1);
      }
      if ( !a2 && !v71 && (*(int *)(*(_QWORD *)(a1 + 504) - 4LL) >= 4 || *(_QWORD *)(a1 + 512)) )
      {
        v71 = 100;
        v54 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
        (*(void (__fastcall **)(void *, struct MSOSP *, __int64, unsigned int *, __int64))(*(_QWORD *)v54 + 608LL))(
          v54,
          v70,
          768,
          &v71,
          4);
      }
      v90[0] = -1;
    }
    if ( (_DWORD)v14 )
      break;
    MsoShipAssertTagProc(3736925);
    Ofc::CAbortException::ThrowTag(0, 3736926);
LABEL_56:
    v16 = v14;
    if ( (_DWORD)v9 == 201 )
      goto LABEL_4;
  }
  if ( v8 )
  {
    v68 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v68 + 624LL))(v68, v70, 13, v102);
  }
  v27 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
  (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v27 + 624LL))(v27, v70, 1, v101);
  LOBYTE(v28) = a6;
  (*(void (__fastcall **)(__int64, struct MSOSP *, __int64))(*(_QWORD *)a1 + 256LL))(a1, v70, v28);
  (*(void (__fastcall **)(__int64, struct MSOSP *))(*(_QWORD *)a1 + 376LL))(a1, v70);
  if ( a2 )
  {
    v30 = a5;
    if ( !a5 )
    {
      v64 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, __int128 *, __int64))(*(_QWORD *)v64 + 608LL))(
        v64,
        v70,
        905,
        &v99,
        4);
      v65 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, char *, __int64))(*(_QWORD *)v65 + 608LL))(
        v65,
        v70,
        906,
        (char *)&v99 + 4,
        4);
      v66 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, char *, __int64))(*(_QWORD *)v66 + 608LL))(
        v66,
        v70,
        907,
        (char *)&v99 + 8,
        4);
      v67 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, char *, __int64))(*(_QWORD *)v67 + 608LL))(
        v67,
        v70,
        908,
        (char *)&v99 + 12,
        4);
    }
  }
  else
  {
    v29 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v29 + 624LL))(v29, v70, 2, v96);
    v30 = a5;
  }
  if ( !a2 )
  {
    v31 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    if ( (*(unsigned int (__fastcall **)(void *, struct MSOSP *, __int64, __int64))(*(_QWORD *)v31 + 624LL))(
           v31,
           v70,
           6,
           a1 + 1040) )
    {
      v33 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, __int64, __int64))(*(_QWORD *)v33 + 608LL))(
        v33,
        v70,
        387,
        a1 + 1064,
        8);
      *(_BYTE *)(a1 + 1416) = 1;
    }
    v34 = 0;
    if ( *(_BYTE *)(a1 + 112) == 2 )
    {
      LOBYTE(v32) = *(_BYTE *)(a1 + 112);
      Ofc::ThrowIfInvalidQualifiedValueState(v32);
      v34 = (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::BlipFill>(a1 + 96) != 0;
    }
    v35 = v34;
    if ( *(_BYTE *)(a1 + 144) == 2 )
      v35 = 1;
    if ( v35 )
    {
      v58 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      v59 = (*(__int64 (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v58 + 624LL))(
              v58,
              v70,
              4,
              v94);
      v60 = v95;
      if ( v59 )
        v60 = 1;
      v95 = v60;
    }
    Art::CPropConverterToLegacy::TranslateAndSetShadowStyle((Art::CPropConverterToLegacy *)a1, v70);
    v36 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v36 + 624LL))(v36, v70, 7, v98);
    v37 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _QWORD *))(*(_QWORD *)v37 + 624LL))(v37, v70, 12, v90);
    v38 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v38 + 624LL))(v38, v70, 3, v97);
    v39 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, __int64))(*(_QWORD *)v39 + 624LL))(v39, v70, 11, a1 + 520);
    v40 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, __int64))(*(_QWORD *)v40 + 624LL))(v40, v70, 10, a1 + 788);
    v41 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    v42 = (*(__int64 (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v41 + 624LL))(
            v41,
            v70,
            5,
            v92);
    v43 = v93;
    if ( v42 )
      v43 = 1;
    v93 = v43;
  }
  v44 = v75;
  if ( v75 )
  {
    v72 = 0;
    v49 = (struct MSOSP *)Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    v52 = *(unsigned int (__fastcall **)(struct MSOSP *, __int64 *, _QWORD))(*(_QWORD *)v49 + 760LL);
    if ( v72 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 24LL))(v72);
    v72 = 0;
    if ( v52(v49, &v72, 0) )
    {
      v53 = v72;
      if ( v72 )
      {
        (*(void (__fastcall **)(__int64, __int64, struct MSOSP *, _QWORD))(*(_QWORD *)v72 + 168LL))(
          v72,
          v44,
          v70,
          8 * (v30 ^ 1u));
        v53 = v72;
      }
      if ( v53 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 24LL))(v53);
      goto LABEL_43;
    }
    MsoShipAssertTagProc(3736922);
    Ofc::CAbortException::ThrowTag(0, 3736923);
    goto LABEL_102;
  }
LABEL_43:
  if ( *(_QWORD *)(a1 + 1944) || v74 && !a8 )
  {
    v45 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *, __int64))(*(_QWORD *)v45 + 608LL))(
      v45,
      v70,
      4,
      v86,
      8);
    v46 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *, __int64))(*(_QWORD *)v46 + 608LL))(
      v46,
      v70,
      62,
      v87,
      8);
    v47 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *, __int64))(*(_QWORD *)v47 + 608LL))(
      v47,
      v70,
      63,
      v88,
      8);
  }
  else
  {
    v51 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, _QWORD, _DWORD *))(*(_QWORD *)v51 + 624LL))(
      v51,
      v70,
      v30 == 0 ? 0xF : 0,
      v85);
  }
  v84 = 1;
  v49 = v70;
  if ( *((_QWORD *)&v81 + 1) )
    Mso::Memory::Free(*((Mso::Memory **)&v81 + 1), v48);
  if ( (_QWORD)v81 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v81 + 16LL))(v81);
  if ( v13 )
    Mso::Memory::Free((Mso::Memory *)v13, v48);
  if ( !v95 )
    MsoFreePropSet(4, v94);
  if ( !v93 )
LABEL_102:
    MsoFreePropSet(5, v92);
  Art::SafeUndo::~SafeUndo((Art::SafeUndo *)v83);
  return v49;
}

```

## disassembly

```asm
0x18036ac00  mov     [rsp-8+arg_8], rbx
0x18036ac05  push    rbp
0x18036ac06  push    rsi
0x18036ac07  push    rdi
0x18036ac08  push    r12
0x18036ac0a  push    r13
0x18036ac0c  push    r14
0x18036ac0e  push    r15
0x18036ac10  lea     rbp, [rsp-7A0h]
0x18036ac18  sub     rsp, 8A0h
0x18036ac1f  mov     rax, cs:__security_cookie
0x18036ac26  xor     rax, rsp
0x18036ac29  mov     [rbp+7D0h+var_40], rax
0x18036ac30  movsxd  r15, r9d
0x18036ac33  mov     [rbp+7D0h+var_838], r8
0x18036ac37  mov     r14b, dl
0x18036ac3a  mov     rsi, rcx
0x18036ac3d  mov     rax, [rbp+7D0h+arg_30]
0x18036ac44  mov     [rbp+7D0h+var_840], rax
0x18036ac48  lea     rax, ??_7SafeUndo@Art@@6B@; const Art::SafeUndo::`vftable'
0x18036ac4f  mov     [rbp+7D0h+var_7F8], rax
0x18036ac53  mov     rcx, [rcx+8]
0x18036ac57  mov     eax, [rcx+4]
0x18036ac5a  mov     r13d, 1
0x18036ac60  cmp     eax, 80000000h
0x18036ac65  jnz     loc_18036B890
0x18036ac6b  mov     [rbp+7D0h+var_7F0], rcx
0x18036ac6f  xor     edi, edi
0x18036ac71  mov     [rbp+7D0h+var_7E8], dil
0x18036ac75  mov     rcx, [rsi+8]; this
0x18036ac79  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036ac7e  mov     rdx, rax
0x18036ac81  mov     rcx, [rax]
0x18036ac84  mov     rax, [rcx+78h]
0x18036ac88  mov     rcx, rdx
0x18036ac8b  call    cs:__guard_dispatch_icall_fptr
0x18036ac91  nop
0x18036ac92  cmp     r15d, 4Bh ; 'K'
0x18036ac96  jnz     loc_18036B391
0x18036ac9c  mov     r12b, r13b
0x18036ac9f  mov     rax, [rsi+8]
0x18036aca3  cmp     [rax+10h], rdi
0x18036aca7  jz      loc_18036B89A
0x18036acad  xor     edx, edx; Val
0x18036acaf  mov     r8d, 168h; Size
0x18036acb5  lea     rcx, [rbp+7D0h+var_290]; void *
0x18036acbc  call    memset_0
0x18036acc1  xor     edx, edx; Val
0x18036acc3  mov     r8d, 120h; Size
0x18036acc9  lea     rcx, [rbp+7D0h+var_680]; void *
0x18036acd0  call    memset_0
0x18036acd5  mov     [rbp+7D0h+var_560], dil
0x18036acdc  xor     edx, edx; Val
0x18036acde  lea     r8d, [rdx+48h]; Size
0x18036ace2  lea     rcx, [rbp+7D0h+var_7E0]; void *
0x18036ace6  call    memset_0
0x18036aceb  xor     edx, edx; Val
0x18036aced  lea     r8d, [rdx+50h]; Size
0x18036acf1  lea     rcx, [rbp+7D0h+var_100]; void *
0x18036acf8  call    memset_0
0x18036acfd  xor     edx, edx; Val
0x18036acff  mov     r8d, 0C8h; Size
0x18036ad05  lea     rcx, [rbp+7D0h+var_750]; void *
0x18036ad0c  call    memset_0
0x18036ad11  xor     edx, edx; Val
0x18036ad13  mov     r8d, 0A8h; Size
0x18036ad19  lea     rcx, [rbp+7D0h+var_400]; void *
0x18036ad20  call    memset_0
0x18036ad25  xor     edx, edx; Val
0x18036ad27  mov     r8d, 0B8h; Size
0x18036ad2d  lea     rcx, [rbp+7D0h+var_350]; void *
0x18036ad34  call    memset_0
0x18036ad39  xor     edx, edx; Val
0x18036ad3b  lea     r8d, [rdx+68h]; Size
0x18036ad3f  lea     rcx, [rbp+7D0h+var_B0]; void *
0x18036ad46  call    memset_0
0x18036ad4b  mov     [rsp+8D0h+var_860], rdi
0x18036ad50  mov     [rbp+7D0h+var_410], dil
0x18036ad57  lea     rdx, [rbp+7D0h+var_550]
0x18036ad5e  mov     ecx, 4
0x18036ad63  call    cs:__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z; MsoGetPropSetNinch(MSOPSID,void *)
0x18036ad69  xorps   xmm0, xmm0
0x18036ad6c  movups  [rbp+7D0h+var_120], xmm0
0x18036ad73  lea     rdx, [rbp+7D0h+var_7E0]
0x18036ad77  xor     ecx, ecx
0x18036ad79  call    cs:__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z; MsoGetPropSetNinch(MSOPSID,void *)
0x18036ad7f  cmp     byte ptr [rsi+130h], 2
0x18036ad86  jnz     short loc_18036ADB6
0x18036ad88  mov     rax, [rsi]
0x18036ad8b  mov     rdi, [rax+1B0h]
0x18036ad92  lea     rbx, [rsi+0E8h]
0x18036ad99  mov     cl, [rbx+48h]
0x18036ad9c  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x18036ada1  mov     r8, rbx
0x18036ada4  lea     rdx, [rbp+7D0h+var_7E0]
0x18036ada8  mov     rcx, rsi
0x18036adab  mov     rax, rdi
0x18036adae  call    cs:__guard_dispatch_icall_fptr
0x18036adb4  xor     edi, edi
0x18036adb6  lea     rdx, [rbp+7D0h+var_120]; struct Ofc::CRect *
0x18036adbd  mov     rcx, rsi; this
0x18036adc0  call    ?TranslateGroupTransform@CPropConverterToLegacy@Art@@QEBAXAEAVCRect@Ofc@@@Z; Art::CPropConverterToLegacy::TranslateGroupTransform(Ofc::CRect &)
0x18036adc5  mov     rax, [rsi]
0x18036adc8  mov     r8b, r13b
0x18036adcb  lea     rdx, [rbp+7D0h+var_750]
0x18036add2  mov     rcx, rsi
0x18036add5  mov     rax, [rax+110h]
0x18036addc  call    cs:__guard_dispatch_icall_fptr
0x18036ade2  test    r12b, r12b
0x18036ade5  jnz     loc_18036B773
0x18036adeb  mov     eax, dword ptr [rbp+7D0h+var_730]
0x18036adf1  mov     [rbp+7D0h+var_848], eax
0x18036adf4  mov     rax, [rsi]
0x18036adf7  lea     rdx, [rbp+7D0h+var_848]
0x18036adfb  mov     rcx, rsi
0x18036adfe  mov     rax, [rax+170h]
0x18036ae05  call    cs:__guard_dispatch_icall_fptr
0x18036ae0b  movsxd  rax, [rbp+7D0h+var_848]
0x18036ae0f  mov     [rbp+7D0h+var_730], rax
0x18036ae16  mov     rax, [rsi]
0x18036ae19  mov     r8b, r13b
0x18036ae1c  lea     rdx, [rbp+7D0h+var_100]
0x18036ae23  mov     rcx, rsi
0x18036ae26  mov     rax, [rax+108h]
0x18036ae2d  call    cs:__guard_dispatch_icall_fptr
0x18036ae33  movzx   ebx, dil
0x18036ae37  mov     [rbp+7D0h+var_830], edi
0x18036ae3a  mov     r13, rdi
0x18036ae3d  mov     [rbp+7D0h+var_828], rdi
0x18036ae41  mov     [rbp+7D0h+var_820], edi
0x18036ae44  mov     [rbp+7D0h+var_81C], 80000000h
0x18036ae4b  mov     [rbp+7D0h+var_818], edi
0x18036ae4e  xorps   xmm0, xmm0
0x18036ae51  movdqu  [rbp+7D0h+var_810], xmm0
0x18036ae56  mov     [rbp+7D0h+var_800], rdi
0x18036ae5a  cmp     byte ptr [rsi+0E0h], 2
0x18036ae61  jz      loc_18036B6E1
0x18036ae67  mov     r12d, 1
0x18036ae6d  test    r14b, r14b
0x18036ae70  jz      loc_18036B4F5
0x18036ae76  test    bl, bl
0x18036ae78  jnz     loc_18036B8B5
0x18036ae7e  mov     eax, [rbp+7D0h+var_7E0]
0x18036ae81  mov     [rbp+7D0h+var_110], eax
0x18036ae87  mov     eax, [rbp+7D0h+var_7D8]
0x18036ae8a  mov     [rbp+7D0h+var_10C], eax
0x18036ae90  mov     eax, [rbp+7D0h+var_7D0]
0x18036ae93  mov     [rbp+7D0h+var_108], eax
0x18036ae99  mov     eax, [rbp+7D0h+var_7C8]
0x18036ae9c  mov     [rbp+7D0h+var_104], eax
0x18036aea2  mov     eax, edi
0x18036aea4  cmp     [rsi+805h], dil
0x18036aeab  setnz   al
0x18036aeae  mov     rcx, [rbp+7D0h+var_750]
0x18036aeb5  test    rcx, rcx
0x18036aeb8  jz      loc_18036B6A2
0x18036aebe  cmp     rcx, 14h
0x18036aec2  jz      loc_18036B6A2
0x18036aec8  mov     edi, eax
0x18036aeca  or      edi, 2
0x18036aecd  xor     edx, edx
0x18036aecf  test    r14b, r14b
0x18036aed2  cmovz   edi, eax
0x18036aed5  lea     r12, [rbp+7D0h+var_110]
0x18036aedc  cmp     [rsi+798h], rdx
0x18036aee3  cmovnz  r12, rdx
0x18036aee7  mov     [rsp+8D0h+var_858], ecx
0x18036aeeb  test    r14b, r14b
0x18036aeee  jz      loc_18036B632
0x18036aef4  xor     r15d, r15d
0x18036aef7  cmp     [rsi+801h], r15b
0x18036aefe  jnz     loc_18036B57A
0x18036af04  mov     rax, [rbp+7D0h+var_840]
0x18036af08  test    rax, rax
0x18036af0b  jnz     loc_18036B3A6
0x18036af11  mov     rcx, [rsi+8]; this
0x18036af15  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036af1a  mov     r10, rax
0x18036af1d  mov     rcx, [rax]
0x18036af20  mov     rax, [rcx+538h]
0x18036af27  mov     rcx, [rsi+798h]
0x18036af2e  mov     dword ptr [rsp+8D0h+var_888], 0FFFFFFFFh
0x18036af36  mov     dword ptr [rsp+8D0h+var_890], edi
0x18036af3a  mov     [rsp+8D0h+var_898], r15
0x18036af3f  mov     [rsp+8D0h+var_8A0], r15
0x18036af44  mov     [rsp+8D0h+var_8A8], r15
0x18036af49  mov     [rsp+8D0h+var_8B0], rcx
0x18036af4e  mov     r9, r12
0x18036af51  mov     r8d, [rsp+8D0h+var_858]
0x18036af56  lea     rdx, [rsp+8D0h+var_860]
0x18036af5b  mov     rcx, r10
0x18036af5e  call    cs:__guard_dispatch_icall_fptr
0x18036af64  mov     edi, eax
0x18036af66  xor     r12d, r12d
0x18036af69  test    r14b, r14b
0x18036af6c  jnz     short loc_18036AF79
0x18036af6e  cmp     [rsp+8D0h+var_858], r12d
0x18036af73  jz      loc_18036B495
0x18036af79  mov     [rbp+7D0h+var_750], 0FFFFFFFFFFFFFFFFh
0x18036af84  test    edi, edi
0x18036af86  jz      loc_18036B375
0x18036af8c  test    bl, bl
0x18036af8e  jnz     loc_18036B8D1
0x18036af94  mov     rcx, [rsi+8]; this
0x18036af98  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036af9d  mov     r10, rax
0x18036afa0  mov     rcx, [rax]
0x18036afa3  mov     rax, [rcx+270h]
0x18036afaa  lea     r9, [rbp+7D0h+var_100]
0x18036afb1  mov     ebx, 1
0x18036afb6  mov     r8d, ebx
0x18036afb9  mov     rdx, [rsp+8D0h+var_860]
0x18036afbe  mov     rcx, r10
0x18036afc1  call    cs:__guard_dispatch_icall_fptr
0x18036afc7  mov     rax, [rsi]
0x18036afca  mov     r8b, [rbp+7D0h+arg_28]
0x18036afd1  mov     rdx, [rsp+8D0h+var_860]
0x18036afd6  mov     rcx, rsi
0x18036afd9  mov     rax, [rax+100h]
0x18036afe0  call    cs:__guard_dispatch_icall_fptr
0x18036afe6  mov     rax, [rsi]
0x18036afe9  mov     rdx, [rsp+8D0h+var_860]
0x18036afee  mov     rcx, rsi
0x18036aff1  mov     rax, [rax+178h]
0x18036aff8  call    cs:__guard_dispatch_icall_fptr
0x18036affe  test    r14b, r14b
0x18036b001  jnz     loc_18036B77F
0x18036b007  mov     rcx, [rsi+8]; this
0x18036b00b  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036b010  mov     r10, rax
0x18036b013  mov     rcx, [rax]
0x18036b016  mov     rax, [rcx+270h]
0x18036b01d  lea     r9, [rbp+7D0h+var_400]
0x18036b024  lea     r8d, [rbx+1]
0x18036b028  mov     rdx, [rsp+8D0h+var_860]
0x18036b02d  mov     rcx, r10
0x18036b030  call    cs:__guard_dispatch_icall_fptr
0x18036b036  mov     r15b, [rbp+7D0h+arg_20]
0x18036b03d  test    r14b, r14b
0x18036b040  jnz     loc_18036B225
0x18036b046  mov     rcx, [rsi+8]; this
0x18036b04a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036b04f  mov     r10, rax
0x18036b052  mov     rcx, [rax]
0x18036b055  mov     rax, [rcx+270h]
0x18036b05c  lea     r9, [rsi+410h]
0x18036b063  mov     r8d, 6
0x18036b069  mov     rdx, [rsp+8D0h+var_860]
0x18036b06e  mov     rcx, r10
0x18036b071  call    cs:__guard_dispatch_icall_fptr
0x18036b077  test    eax, eax
0x18036b079  jz      short loc_18036B0BC
0x18036b07b  mov     rcx, [rsi+8]; this
0x18036b07f  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036b084  mov     r10, rax
0x18036b087  mov     rcx, [rax]
0x18036b08a  mov     rax, [rcx+260h]
0x18036b091  lea     r9, [rsi+428h]
0x18036b098  mov     [rsp+8D0h+var_8B0], 8
0x18036b0a1  mov     r8d, 183h
0x18036b0a7  mov     rdx, [rsp+8D0h+var_860]
0x18036b0ac  mov     rcx, r10
0x18036b0af  call    cs:__guard_dispatch_icall_fptr
0x18036b0b5  nop
0x18036b0b6  mov     [rsi+588h], bl
0x18036b0bc  movzx   edi, r12b
0x18036b0c0  cmp     byte ptr [rsi+70h], 2
0x18036b0c4  jz      loc_18036B703
0x18036b0ca  movzx   eax, dil
0x18036b0ce  cmp     byte ptr [rsi+90h], 2
0x18036b0d5  cmovz   eax, ebx
0x18036b0d8  test    al, al
0x18036b0da  jnz     loc_18036B65A
0x18036b0e0  mov     rdx, [rsp+8D0h+var_860]; struct MSOSP *
0x18036b0e5  mov     rcx, rsi; this
0x18036b0e8  call    ?TranslateAndSetShadowStyle@CPropConverterToLegacy@Art@@QEBAXPEAUMSOSP@@@Z; Art::CPropConverterToLegacy::TranslateAndSetShadowStyle(MSOSP *)
0x18036b0ed  mov     rcx, [rsi+8]; this
0x18036b0f1  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036b0f6  mov     r10, rax
0x18036b0f9  mov     rcx, [rax]
0x18036b0fc  mov     rax, [rcx+270h]
0x18036b103  lea     r9, [rbp+7D0h+var_290]
0x18036b10a  mov     r8d, 7
0x18036b110  mov     rdx, [rsp+8D0h+var_860]
0x18036b115  mov     rcx, r10
0x18036b118  call    cs:__guard_dispatch_icall_fptr
0x18036b11e  mov     rcx, [rsi+8]; this
0x18036b122  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036b127  mov     r10, rax
0x18036b12a  mov     rcx, [rax]
0x18036b12d  mov     rax, [rcx+270h]
0x18036b134  lea     r9, [rbp+7D0h+var_750]
0x18036b13b  mov     r8d, 0Ch
0x18036b141  mov     rdx, [rsp+8D0h+var_860]
0x18036b146  mov     rcx, r10
0x18036b149  call    cs:__guard_dispatch_icall_fptr
0x18036b14f  mov     rcx, [rsi+8]; this
0x18036b153  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x18036b158  mov     r10, rax
0x18036b15b  mov     rcx, [rax]
  ... truncated ...
```
