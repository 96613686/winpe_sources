# Art::CPropConverterToLegacy::CreateHsp(bool,MSOSP *,MSOSPT,bool,bool,MSOSP *,bool)

- ea: `0x1800cbd20`
- end: `0x1800cca74`
- name: `?CreateHsp@CPropConverterToLegacy@Art@@UEAAPEAUMSOSP@@_NPEAU3@W4MSOSPT@@0010@Z`
- size: `3412`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation`

## callees

- `0x18006aa80`
- `0x18006f9a4`
- `0x1800b69b0`
- `0x1800be4c0`
- `0x1800bebd8`
- `0x1800c0990`
- `0x1800c3b48`
- `0x1800c3bc0`
- `0x1800c3c40`
- `0x1800c3cf4`
- `0x1800c8030`
- `0x1800cbd20`
- `0x1800cca80`
- `0x180107d9c`
- `0x180107e38`
- `0x180276a71`
- `0x180279010`
- `0x180279030`
- `0x180279050`
- `0x1802a23d0`
- `0x180398aa0`
- `0x180683a00`
- `0x1806bc4f0`
- `0x1806dd4b8`

## import_xrefs

- `Mso98Win32Client!__imp_?MsoFIsNinch@@YAHW4MSOPID@@PEBX_K@Z` at `0x1800cc6ac`
- `Mso98Win32Client!__imp_?MsoFIsNinch@@YAHW4MSOPID@@PEBX_K@Z` at `0x1800cc6ac`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x1800cbe7b`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x1800cbe91`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x1800cbe7b`
- `Mso98Win32Client!__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z` at `0x1800cbe91`
- `Mso98Win32Client!__imp_?MsoFreePropSet@@YAXW4MSOPSID@@PEBX@Z` at `0x1800cc43a`
- `Mso98Win32Client!__imp_?MsoFreePropSet@@YAXW4MSOPSID@@PEBX@Z` at `0x1800cca68`
- `Mso98Win32Client!__imp_?MsoFreePropSet@@YAXW4MSOPSID@@PEBX@Z` at `0x1800cc43a`
- `Mso98Win32Client!__imp_?MsoFreePropSet@@YAXW4MSOPSID@@PEBX@Z` at `0x1800cca68`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800cc489`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800cc9c7`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800cca46`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800cc489`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800cc9c7`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1800cca46`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800cc403`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800cc41e`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800cc403`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800cc41e`

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
  struct MSOSP *v8; // rbx
  __int64 v9; // r15
  void *Checked; // rax
  __int64 v13; // r13
  char v14; // r12
  __int64 v15; // rcx
  void (__fastcall *v16)(__int64, _DWORD *, __int64); // rdi
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // rcx
  bool v20; // r8
  int v21; // eax
  int v22; // edi
  _DWORD *v23; // r12
  void *v24; // rax
  int v25; // edi
  void *v26; // rax
  __int64 v27; // r8
  void *v28; // rax
  unsigned __int8 v29; // r15
  void *v30; // rax
  __int64 v31; // rcx
  void *v32; // rax
  bool v33; // di
  char v34; // al
  void *v35; // rax
  void *v36; // rax
  void *v37; // rax
  void *v38; // rax
  void *v39; // rax
  void *v40; // rax
  int v41; // eax
  char v42; // cl
  __int64 v43; // r14
  void *v44; // rax
  void *v45; // rax
  void *v46; // rax
  void *v47; // rdx
  __int64 v48; // rcx
  void *v50; // rax
  void *v51; // rax
  unsigned int (__fastcall *v52)(struct MSOSP *, __int64 *, _QWORD); // rdi
  __int64 v53; // rcx
  __int64 v54; // r8
  bool v55; // r8
  void *v56; // rax
  int v57; // eax
  char v58; // cl
  void *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // rdi
  const struct Art::PresetGeometry2D *v62; // rax
  void *v63; // rax
  void *v64; // rax
  void *v65; // rax
  void *v66; // rax
  void *v67; // rax
  struct MSOSP *v68; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v69; // [rsp+78h] [rbp-88h] BYREF
  __int64 v70; // [rsp+80h] [rbp-80h] BYREF
  int v71; // [rsp+88h] [rbp-78h] BYREF
  struct MSOSP *v72; // [rsp+90h] [rbp-70h]
  __int64 v73; // [rsp+98h] [rbp-68h]
  int v74; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v75; // [rsp+A8h] [rbp-58h]
  int v76; // [rsp+B0h] [rbp-50h]
  unsigned int v77; // [rsp+B4h] [rbp-4Ch]
  int v78; // [rsp+B8h] [rbp-48h]
  __int128 v79; // [rsp+C0h] [rbp-40h]
  __int64 v80; // [rsp+D0h] [rbp-30h]
  _QWORD v81[2]; // [rsp+D8h] [rbp-28h] BYREF
  char v82; // [rsp+E8h] [rbp-18h]
  _DWORD v83[8]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v84[24]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v85[8]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v86[16]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v87[64]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD v88[4]; // [rsp+180h] [rbp+80h] BYREF
  __int64 v89; // [rsp+1A0h] [rbp+A0h]
  _BYTE v90[288]; // [rsp+250h] [rbp+150h] BYREF
  char v91; // [rsp+370h] [rbp+270h]
  _BYTE v92[320]; // [rsp+380h] [rbp+280h] BYREF
  char v93; // [rsp+4C0h] [rbp+3C0h]
  _BYTE v94[176]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v95[192]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v96[368]; // [rsp+640h] [rbp+540h] BYREF
  __int128 v97; // [rsp+7B0h] [rbp+6B0h] BYREF
  _DWORD v98[4]; // [rsp+7C0h] [rbp+6C0h] BYREF
  _BYTE v99[80]; // [rsp+7D0h] [rbp+6D0h] BYREF
  _BYTE v100[112]; // [rsp+820h] [rbp+720h] BYREF

  v9 = a4;
  v73 = a3;
  v72 = a7;
  v81[0] = &Art::SafeUndo::`vftable';
  v81[1] = Ofc::CProxyPtrImpl::WeakAddRef(*(struct Ofc::CProxyPtrImpl **)(a1 + 8));
  v82 = 0;
  Checked = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
  (*(void (__fastcall **)(void *))(*(_QWORD *)Checked + 136LL))(Checked);
  v13 = 1;
  if ( (_DWORD)v9 == 75 || (v14 = 0, (_DWORD)v9 == 201) )
    v14 = 1;
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) )
  {
    MsoShipAssertTagProc(3736918);
    Ofc::CAbortException::ThrowTag(0, 3736919);
LABEL_96:
    Art::CPropConverterToLegacy::TranslateCallout(
      (const struct MSOPSGeometry *)v90,
      (const struct Art::PresetGeometry2D *)&v74,
      (struct MSOPSCallout *)v100);
    goto LABEL_11;
  }
  memset_0(v96, 0, 0x168u);
  memset_0(v90, 0, sizeof(v90));
  v91 = 0;
  memset_0(v83, 0, 0x48u);
  memset_0(v99, 0, sizeof(v99));
  memset_0(v88, 0, 0xC8u);
  memset_0(v94, 0, 0xA8u);
  memset_0(v95, 0, 0xB8u);
  memset_0(v100, 0, 0x68u);
  v68 = 0;
  v93 = 0;
  MsoGetPropSetNinch(4);
  v97 = 0;
  MsoGetPropSetNinch(0);
  if ( *(_BYTE *)(a1 + 304) == 2 )
  {
    v16 = *(void (__fastcall **)(__int64, _DWORD *, __int64))(*(_QWORD *)a1 + 432LL);
    LOBYTE(v15) = *(_BYTE *)(a1 + 304);
    Ofc::ThrowIfInvalidQualifiedValueState(v15);
    v16(a1, v83, a1 + 232);
  }
  Art::CPropConverterToLegacy::TranslateGroupTransform((Art::CPropConverterToLegacy *)a1, (struct Ofc::CRect *)&v97);
  LOBYTE(v17) = 1;
  (*(void (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)a1 + 272LL))(a1, v88, v17);
  if ( v14 )
    v88[0] = v9;
  v71 = v89;
  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)a1 + 368LL))(a1, &v71);
  v89 = v71;
  LOBYTE(v18) = 1;
  (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 264LL))(a1, v99, v18);
  v8 = 0;
  v74 = 0;
  v13 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0x80000000;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  if ( *(_BYTE *)(a1 + 224) == 2 )
  {
    LOBYTE(v19) = *(_BYTE *)(a1 + 224);
    Ofc::ThrowIfInvalidQualifiedValueState(v19);
    if ( (unsigned __int8)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Is<Art::Geom::Preset>(a1 + 208) )
    {
      LOBYTE(v60) = *(_BYTE *)(a1 + 224);
      Ofc::ThrowIfInvalidQualifiedValueState(v60);
      v62 = (const struct Art::PresetGeometry2D *)Ofc::TChoice<Art::Geometry2DDataChoiceIDsImpl>::Get<Art::Geom::Preset>(a1 + 208);
      Art::PresetGeometry2D::PresetGeometry2D((Art::PresetGeometry2D *)v87, v62);
      Art::PresetTextShape::Swap((Art::PresetTextShape *)&v74, (struct Art::PresetTextShape *)v87);
      Art::PresetTextShape::~PresetTextShape((Art::PresetTextShape *)v87);
      v8 = (struct MSOSP *)((unsigned int)(v78 - 104) <= 0xB);
      v13 = v75;
    }
  }
  if ( !a2 )
  {
    Art::CPropConverterToLegacy::TranslateGeoText((Art::CPropConverterToLegacy *)a1, (struct MSOPSGeoText *)v95, v20);
    Art::CPropConverterToLegacy::TranslateFillProps((Art::CPropConverterToLegacy *)a1, (struct MSOPSBlip *)v92, 1);
    if ( *(_BYTE *)(a1 + 144) == 2 )
      (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a1 + 288LL))(a1, v92);
    Art::CPropConverterToLegacy::Translate3D((Art::CPropConverterToLegacy *)a1);
    LOBYTE(v54) = 1;
    (*(void (__fastcall **)(__int64, _BYTE *, __int64))(*(_QWORD *)a1 + 232LL))(a1, v96, v54);
    (*(void (__fastcall **)(__int64, _DWORD *, _BYTE *))(*(_QWORD *)a1 + 248LL))(a1, v83, v90);
    Art::CPropConverterToLegacy::TranslateText((Art::CPropConverterToLegacy *)a1, (struct MSOPSText *)v94, v55);
  }
  if ( (_BYTE)v8 )
    goto LABEL_96;
LABEL_11:
  v98[0] = v83[0];
  v98[1] = v83[2];
  v98[2] = v83[4];
  v98[3] = v83[6];
  v21 = *(_BYTE *)(a1 + 2053) != 0;
  if ( !v88[0] || v88[0] == 20 )
    v21 |= 4u;
  v22 = v21 | 2;
  if ( !a2 )
    v22 = v21;
  v23 = v98;
  if ( *(_QWORD *)(a1 + 1944) )
    v23 = 0;
  v69 = v88[0];
  if ( !a2 && (unsigned int)MsoFIsNinch(768, &v69, 4) )
    v69 = v9;
  if ( *(_BYTE *)(a1 + 2049) && *(_DWORD *)(a1 + 496) == 6 )
  {
    v70 = 0;
    if ( (unsigned __int8)Dr::FIsInkDisp2Ink(a1 + 88) )
    {
      Dr::CopyInkDisp2StrokesToLegacyInkObject(a1 + 88, &v70);
    }
    else
    {
      v61 = *(_QWORD *)(a1 + 88);
      if ( v61 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 8LL))(v61);
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      v70 = v61;
    }
    v59 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    v25 = (*(__int64 (__fastcall **)(void *, struct MSOSP **, _DWORD *, _QWORD, _DWORD, _QWORD, __int64, _QWORD, _QWORD, _QWORD, _DWORD, int))(*(_QWORD *)v59 + 480LL))(
            v59,
            &v68,
            v23,
            *(_QWORD *)(a1 + 1944),
            0,
            0,
            v70,
            0,
            0,
            0,
            *(unsigned __int8 *)(a1 + 2053),
            1);
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
  }
  else
  {
    if ( v72 )
    {
      v25 = 1;
      v68 = v72;
    }
    else
    {
      v24 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      v25 = (*(__int64 (__fastcall **)(void *, struct MSOSP **, _QWORD, _DWORD *, _QWORD, _QWORD, _QWORD, _QWORD, int, int))(*(_QWORD *)v24 + 1352LL))(
              v24,
              &v68,
              v69,
              v23,
              *(_QWORD *)(a1 + 1944),
              0,
              0,
              0,
              v22,
              -1);
    }
    if ( !a2 && !v69 && (*(int *)(*(_QWORD *)(a1 + 504) - 4LL) >= 4 || *(_QWORD *)(a1 + 512)) )
    {
      v69 = 100;
      v51 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, unsigned int *, __int64))(*(_QWORD *)v51 + 624LL))(
        v51,
        v68,
        768,
        &v69,
        4);
    }
    v88[0] = -1;
  }
  if ( !v25 )
  {
    MsoShipAssertTagProc(3736925);
    Ofc::CAbortException::ThrowTag(0, 3736926);
LABEL_53:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    goto LABEL_46;
  }
  if ( (_BYTE)v8 )
  {
    v67 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v67 + 640LL))(v67, v68, 13, v100);
  }
  v26 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
  (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v26 + 640LL))(v26, v68, 1, v99);
  LOBYTE(v27) = a6;
  (*(void (__fastcall **)(__int64, struct MSOSP *, __int64))(*(_QWORD *)a1 + 256LL))(a1, v68, v27);
  (*(void (__fastcall **)(__int64, struct MSOSP *))(*(_QWORD *)a1 + 376LL))(a1, v68);
  if ( a2 )
  {
    v29 = a5;
    if ( !a5 )
    {
      v63 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, __int128 *, __int64))(*(_QWORD *)v63 + 624LL))(
        v63,
        v68,
        905,
        &v97,
        4);
      v64 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, char *, __int64))(*(_QWORD *)v64 + 624LL))(
        v64,
        v68,
        906,
        (char *)&v97 + 4,
        4);
      v65 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, char *, __int64))(*(_QWORD *)v65 + 624LL))(
        v65,
        v68,
        907,
        (char *)&v97 + 8,
        4);
      v66 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, char *, __int64))(*(_QWORD *)v66 + 624LL))(
        v66,
        v68,
        908,
        (char *)&v97 + 12,
        4);
    }
  }
  else
  {
    v28 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v28 + 640LL))(v28, v68, 2, v94);
    v29 = a5;
  }
  if ( !a2 )
  {
    v30 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    if ( (*(unsigned int (__fastcall **)(void *, struct MSOSP *, __int64, __int64))(*(_QWORD *)v30 + 640LL))(
           v30,
           v68,
           6,
           a1 + 1040) )
    {
      v32 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      (*(void (__fastcall **)(void *, struct MSOSP *, __int64, __int64, __int64))(*(_QWORD *)v32 + 624LL))(
        v32,
        v68,
        387,
        a1 + 1064,
        8);
      *(_BYTE *)(a1 + 1416) = 1;
    }
    v33 = 0;
    if ( *(_BYTE *)(a1 + 112) == 2 )
    {
      LOBYTE(v31) = *(_BYTE *)(a1 + 112);
      Ofc::ThrowIfInvalidQualifiedValueState(v31);
      v33 = (unsigned __int8)Ofc::TChoice<Art::FillPropsDataChoiceIDsImpl>::Is<Art::FillPr::BlipFill>(a1 + 96) != 0;
    }
    v34 = v33;
    if ( *(_BYTE *)(a1 + 144) == 2 )
      v34 = 1;
    if ( v34 )
    {
      v56 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
      v57 = (*(__int64 (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v56 + 640LL))(
              v56,
              v68,
              4,
              v92);
      v58 = v93;
      if ( v57 )
        v58 = 1;
      v93 = v58;
    }
    Art::CPropConverterToLegacy::TranslateAndSetShadowStyle((Art::CPropConverterToLegacy *)a1, v68);
    v35 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v35 + 640LL))(v35, v68, 7, v96);
    v36 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _QWORD *))(*(_QWORD *)v36 + 640LL))(v36, v68, 12, v88);
    v37 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v37 + 640LL))(v37, v68, 3, v95);
    v38 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, __int64))(*(_QWORD *)v38 + 640LL))(v38, v68, 11, a1 + 520);
    v39 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, __int64))(*(_QWORD *)v39 + 640LL))(v39, v68, 10, a1 + 788);
    v40 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    v41 = (*(__int64 (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *))(*(_QWORD *)v40 + 640LL))(
            v40,
            v68,
            5,
            v90);
    v42 = v91;
    if ( v41 )
      v42 = 1;
    v91 = v42;
  }
  v43 = v73;
  if ( v73 )
  {
    v70 = 0;
    v8 = (struct MSOSP *)Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    v52 = *(unsigned int (__fastcall **)(struct MSOSP *, __int64 *, _QWORD))(*(_QWORD *)v8 + 776LL);
    if ( v70 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 24LL))(v70);
    v70 = 0;
    if ( !v52(v8, &v70, 0) )
    {
      MsoShipAssertTagProc(3736922);
      Ofc::CAbortException::ThrowTag(0, 3736923);
LABEL_98:
      MsoFreePropSet(5, v90);
      goto LABEL_51;
    }
    v53 = v70;
    if ( v70 )
    {
      (*(void (__fastcall **)(__int64, __int64, struct MSOSP *, _QWORD))(*(_QWORD *)v70 + 168LL))(
        v70,
        v43,
        v68,
        8 * (v29 ^ 1u));
      v53 = v70;
    }
    if ( v53 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 24LL))(v53);
  }
  if ( *(_QWORD *)(a1 + 1944) || v72 && !a8 )
  {
    v44 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *, __int64))(*(_QWORD *)v44 + 624LL))(
      v44,
      v68,
      4,
      v84,
      8);
    v45 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *, __int64))(*(_QWORD *)v45 + 624LL))(
      v45,
      v68,
      62,
      v85,
      8);
    v46 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, __int64, _BYTE *, __int64))(*(_QWORD *)v46 + 624LL))(
      v46,
      v68,
      63,
      v86,
      8);
  }
  else
  {
    v50 = Ofc::CProxyPtrImpl::GetChecked(*(Ofc::CProxyPtrImpl **)(a1 + 8));
    (*(void (__fastcall **)(void *, struct MSOSP *, _QWORD, _DWORD *))(*(_QWORD *)v50 + 640LL))(
      v50,
      v68,
      v29 == 0 ? 0xF : 0,
      v83);
  }
  v82 = 1;
  v8 = v68;
  if ( *((_QWORD *)&v79 + 1) )
    Mso::Memory::Free(*((Mso::Memory **)&v79 + 1), v47);
  v48 = v79;
  if ( (_QWORD)v79 )
    goto LABEL_53;
LABEL_46:
  if ( v13 )
    Mso::Memory::Free((Mso::Memory *)v13, v47);
  if ( !v93 )
    MsoFreePropSet(4, v92);
  if ( !v91 )
    goto LABEL_98;
LABEL_51:
  Art::SafeUndo::~SafeUndo((Art::SafeUndo *)v81);
  return v8;
}

```

## disassembly

```asm
0x1800cbd20  mov     [rsp-8+arg_8], rbx
0x1800cbd25  push    rbp
0x1800cbd26  push    rsi
0x1800cbd27  push    rdi
0x1800cbd28  push    r12
0x1800cbd2a  push    r13
0x1800cbd2c  push    r14
0x1800cbd2e  push    r15
0x1800cbd30  lea     rbp, [rsp-7A0h]
0x1800cbd38  sub     rsp, 8A0h
0x1800cbd3f  mov     rax, cs:__security_cookie
0x1800cbd46  xor     rax, rsp
0x1800cbd49  mov     [rbp+7D0h+var_40], rax
0x1800cbd50  movsxd  r15, r9d
0x1800cbd53  mov     [rbp+7D0h+var_838], r8
0x1800cbd57  mov     r14b, dl
0x1800cbd5a  mov     rsi, rcx
0x1800cbd5d  mov     rax, [rbp+7D0h+arg_30]
0x1800cbd64  mov     [rbp+7D0h+var_840], rax
0x1800cbd68  lea     rax, ??_7SafeUndo@Art@@6B@; const Art::SafeUndo::`vftable'
0x1800cbd6f  mov     [rbp+7D0h+var_7F8], rax
0x1800cbd73  mov     rcx, [rcx+8]; struct Ofc::CProxyPtrImpl *
0x1800cbd77  call    ?WeakAddRef@CProxyPtrImpl@Ofc@@KAPEAV12@PEAV12@@Z; Ofc::CProxyPtrImpl::WeakAddRef(Ofc::CProxyPtrImpl *)
0x1800cbd7c  mov     [rbp+7D0h+var_7F0], rax
0x1800cbd80  xor     edi, edi
0x1800cbd82  mov     [rbp+7D0h+var_7E8], dil
0x1800cbd86  mov     rcx, [rsi+8]; this
0x1800cbd8a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cbd8f  mov     rdx, rax
0x1800cbd92  mov     rcx, [rax]
0x1800cbd95  mov     rax, [rcx+88h]
0x1800cbd9c  mov     rcx, rdx
0x1800cbd9f  call    cs:__guard_dispatch_icall_fptr
0x1800cbda5  nop
0x1800cbda6  lea     r13d, [rdi+1]
0x1800cbdaa  cmp     r15d, 4Bh ; 'K'
0x1800cbdae  jnz     loc_1800CC4B3
0x1800cbdb4  mov     r12b, r13b
0x1800cbdb7  mov     rax, [rsi+8]
0x1800cbdbb  cmp     [rax+10h], rdi
0x1800cbdbf  jz      loc_1800CC9C2
0x1800cbdc5  xor     edx, edx; Val
0x1800cbdc7  mov     r8d, 168h; Size
0x1800cbdcd  lea     rcx, [rbp+7D0h+var_290]; void *
0x1800cbdd4  call    memset_0
0x1800cbdd9  xor     edx, edx; Val
0x1800cbddb  mov     r8d, 120h; Size
0x1800cbde1  lea     rcx, [rbp+7D0h+var_680]; void *
0x1800cbde8  call    memset_0
0x1800cbded  mov     [rbp+7D0h+var_560], dil
0x1800cbdf4  xor     edx, edx; Val
0x1800cbdf6  lea     r8d, [rdx+48h]; Size
0x1800cbdfa  lea     rcx, [rbp+7D0h+var_7E0]; void *
0x1800cbdfe  call    memset_0
0x1800cbe03  xor     edx, edx; Val
0x1800cbe05  lea     r8d, [rdx+50h]; Size
0x1800cbe09  lea     rcx, [rbp+7D0h+var_100]; void *
0x1800cbe10  call    memset_0
0x1800cbe15  xor     edx, edx; Val
0x1800cbe17  mov     r8d, 0C8h; Size
0x1800cbe1d  lea     rcx, [rbp+7D0h+var_750]; void *
0x1800cbe24  call    memset_0
0x1800cbe29  xor     edx, edx; Val
0x1800cbe2b  mov     r8d, 0A8h; Size
0x1800cbe31  lea     rcx, [rbp+7D0h+var_400]; void *
0x1800cbe38  call    memset_0
0x1800cbe3d  xor     edx, edx; Val
0x1800cbe3f  mov     r8d, 0B8h; Size
0x1800cbe45  lea     rcx, [rbp+7D0h+var_350]; void *
0x1800cbe4c  call    memset_0
0x1800cbe51  xor     edx, edx; Val
0x1800cbe53  lea     r8d, [rdx+68h]; Size
0x1800cbe57  lea     rcx, [rbp+7D0h+var_B0]; void *
0x1800cbe5e  call    memset_0
0x1800cbe63  mov     [rsp+8D0h+var_860], rdi
0x1800cbe68  mov     [rbp+7D0h+var_410], dil
0x1800cbe6f  lea     rdx, [rbp+7D0h+var_550]
0x1800cbe76  mov     ecx, 4
0x1800cbe7b  call    cs:__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z; MsoGetPropSetNinch(MSOPSID,void *)
0x1800cbe81  xorps   xmm0, xmm0
0x1800cbe84  movups  [rbp+7D0h+var_120], xmm0
0x1800cbe8b  lea     rdx, [rbp+7D0h+var_7E0]
0x1800cbe8f  xor     ecx, ecx
0x1800cbe91  call    cs:__imp_?MsoGetPropSetNinch@@YAXW4MSOPSID@@PEAX@Z; MsoGetPropSetNinch(MSOPSID,void *)
0x1800cbe97  cmp     byte ptr [rsi+130h], 2
0x1800cbe9e  jnz     short loc_1800CBECE
0x1800cbea0  mov     rax, [rsi]
0x1800cbea3  mov     rdi, [rax+1B0h]
0x1800cbeaa  lea     rbx, [rsi+0E8h]
0x1800cbeb1  mov     cl, [rbx+48h]
0x1800cbeb4  call    ?ThrowIfInvalidQualifiedValueState@Ofc@@YAXW4QualifiedValueState@1@@Z; Ofc::ThrowIfInvalidQualifiedValueState(Ofc::QualifiedValueState)
0x1800cbeb9  mov     r8, rbx
0x1800cbebc  lea     rdx, [rbp+7D0h+var_7E0]
0x1800cbec0  mov     rcx, rsi
0x1800cbec3  mov     rax, rdi
0x1800cbec6  call    cs:__guard_dispatch_icall_fptr
0x1800cbecc  xor     edi, edi
0x1800cbece  lea     rdx, [rbp+7D0h+var_120]; struct Ofc::CRect *
0x1800cbed5  mov     rcx, rsi; this
0x1800cbed8  call    ?TranslateGroupTransform@CPropConverterToLegacy@Art@@QEBAXAEAVCRect@Ofc@@@Z; Art::CPropConverterToLegacy::TranslateGroupTransform(Ofc::CRect &)
0x1800cbedd  mov     rax, [rsi]
0x1800cbee0  mov     r8b, r13b
0x1800cbee3  lea     rdx, [rbp+7D0h+var_750]
0x1800cbeea  mov     rcx, rsi
0x1800cbeed  mov     rax, [rax+110h]
0x1800cbef4  call    cs:__guard_dispatch_icall_fptr
0x1800cbefa  test    r12b, r12b
0x1800cbefd  jnz     loc_1800CC845
0x1800cbf03  mov     eax, dword ptr [rbp+7D0h+var_730]
0x1800cbf09  mov     [rbp+7D0h+var_848], eax
0x1800cbf0c  mov     rax, [rsi]
0x1800cbf0f  lea     rdx, [rbp+7D0h+var_848]
0x1800cbf13  mov     rcx, rsi
0x1800cbf16  mov     rax, [rax+170h]
0x1800cbf1d  call    cs:__guard_dispatch_icall_fptr
0x1800cbf23  movsxd  rax, [rbp+7D0h+var_848]
0x1800cbf27  mov     [rbp+7D0h+var_730], rax
0x1800cbf2e  mov     rax, [rsi]
0x1800cbf31  mov     r8b, r13b
0x1800cbf34  lea     rdx, [rbp+7D0h+var_100]
0x1800cbf3b  mov     rcx, rsi
0x1800cbf3e  mov     rax, [rax+108h]
0x1800cbf45  call    cs:__guard_dispatch_icall_fptr
0x1800cbf4b  movzx   ebx, dil
0x1800cbf4f  mov     [rbp+7D0h+var_830], edi
0x1800cbf52  mov     r13, rdi
0x1800cbf55  mov     [rbp+7D0h+var_828], rdi
0x1800cbf59  mov     [rbp+7D0h+var_820], edi
0x1800cbf5c  mov     [rbp+7D0h+var_81C], 80000000h
0x1800cbf63  mov     [rbp+7D0h+var_818], edi
0x1800cbf66  xorps   xmm0, xmm0
0x1800cbf69  movdqu  [rbp+7D0h+var_810], xmm0
0x1800cbf6e  mov     [rbp+7D0h+var_800], rdi
0x1800cbf72  cmp     byte ptr [rsi+0E0h], 2
0x1800cbf79  jz      loc_1800CC7CC
0x1800cbf7f  mov     r12d, 1
0x1800cbf85  test    r14b, r14b
0x1800cbf88  jz      loc_1800CC617
0x1800cbf8e  test    bl, bl
0x1800cbf90  jnz     loc_1800CC9DD
0x1800cbf96  mov     eax, [rbp+7D0h+var_7E0]
0x1800cbf99  mov     [rbp+7D0h+var_110], eax
0x1800cbf9f  mov     eax, [rbp+7D0h+var_7D8]
0x1800cbfa2  mov     [rbp+7D0h+var_10C], eax
0x1800cbfa8  mov     eax, [rbp+7D0h+var_7D0]
0x1800cbfab  mov     [rbp+7D0h+var_108], eax
0x1800cbfb1  mov     eax, [rbp+7D0h+var_7C8]
0x1800cbfb4  mov     [rbp+7D0h+var_104], eax
0x1800cbfba  mov     eax, edi
0x1800cbfbc  cmp     [rsi+805h], dil
0x1800cbfc3  setnz   al
0x1800cbfc6  mov     rcx, [rbp+7D0h+var_750]
0x1800cbfcd  test    rcx, rcx
0x1800cbfd0  jz      loc_1800CC7C4
0x1800cbfd6  cmp     rcx, 14h
0x1800cbfda  jz      loc_1800CC7C4
0x1800cbfe0  mov     edi, eax
0x1800cbfe2  or      edi, 2
0x1800cbfe5  xor     edx, edx
0x1800cbfe7  test    r14b, r14b
0x1800cbfea  cmovz   edi, eax
0x1800cbfed  lea     r12, [rbp+7D0h+var_110]
0x1800cbff4  cmp     [rsi+798h], rdx
0x1800cbffb  cmovnz  r12, rdx
0x1800cbfff  mov     [rsp+8D0h+var_858], ecx
0x1800cc003  test    r14b, r14b
0x1800cc006  jz      loc_1800CC69C
0x1800cc00c  xor     r15d, r15d
0x1800cc00f  cmp     [rsi+801h], r15b
0x1800cc016  jnz     loc_1800CC70C
0x1800cc01c  mov     rax, [rbp+7D0h+var_840]
0x1800cc020  test    rax, rax
0x1800cc023  jnz     loc_1800CC4C8
0x1800cc029  mov     rcx, [rsi+8]; this
0x1800cc02d  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cc032  mov     r10, rax
0x1800cc035  mov     rcx, [rax]
0x1800cc038  mov     rax, [rcx+548h]
0x1800cc03f  mov     rcx, [rsi+798h]
0x1800cc046  mov     dword ptr [rsp+8D0h+var_888], 0FFFFFFFFh
0x1800cc04e  mov     dword ptr [rsp+8D0h+var_890], edi
0x1800cc052  mov     [rsp+8D0h+var_898], r15
0x1800cc057  mov     [rsp+8D0h+var_8A0], r15
0x1800cc05c  mov     [rsp+8D0h+var_8A8], r15
0x1800cc061  mov     [rsp+8D0h+var_8B0], rcx
0x1800cc066  mov     r9, r12
0x1800cc069  mov     r8d, [rsp+8D0h+var_858]
0x1800cc06e  lea     rdx, [rsp+8D0h+var_860]
0x1800cc073  mov     rcx, r10
0x1800cc076  call    cs:__guard_dispatch_icall_fptr
0x1800cc07c  mov     edi, eax
0x1800cc07e  xor     r12d, r12d
0x1800cc081  test    r14b, r14b
0x1800cc084  jnz     short loc_1800CC091
0x1800cc086  cmp     [rsp+8D0h+var_858], r12d
0x1800cc08b  jz      loc_1800CC524
0x1800cc091  mov     [rbp+7D0h+var_750], 0FFFFFFFFFFFFFFFFh
0x1800cc09c  test    edi, edi
0x1800cc09e  jz      loc_1800CC484
0x1800cc0a4  test    bl, bl
0x1800cc0a6  jnz     loc_1800CC9F9
0x1800cc0ac  mov     rcx, [rsi+8]; this
0x1800cc0b0  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cc0b5  mov     r10, rax
0x1800cc0b8  mov     rcx, [rax]
0x1800cc0bb  mov     rax, [rcx+280h]
0x1800cc0c2  lea     r9, [rbp+7D0h+var_100]
0x1800cc0c9  mov     ebx, 1
0x1800cc0ce  mov     r8d, ebx
0x1800cc0d1  mov     rdx, [rsp+8D0h+var_860]
0x1800cc0d6  mov     rcx, r10
0x1800cc0d9  call    cs:__guard_dispatch_icall_fptr
0x1800cc0df  mov     rax, [rsi]
0x1800cc0e2  mov     r8b, [rbp+7D0h+arg_28]
0x1800cc0e9  mov     rdx, [rsp+8D0h+var_860]
0x1800cc0ee  mov     rcx, rsi
0x1800cc0f1  mov     rax, [rax+100h]
0x1800cc0f8  call    cs:__guard_dispatch_icall_fptr
0x1800cc0fe  mov     rax, [rsi]
0x1800cc101  mov     rdx, [rsp+8D0h+var_860]
0x1800cc106  mov     rcx, rsi
0x1800cc109  mov     rax, [rax+178h]
0x1800cc110  call    cs:__guard_dispatch_icall_fptr
0x1800cc116  test    r14b, r14b
0x1800cc119  jnz     loc_1800CC8A1
0x1800cc11f  mov     rcx, [rsi+8]; this
0x1800cc123  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cc128  mov     r10, rax
0x1800cc12b  mov     rcx, [rax]
0x1800cc12e  mov     rax, [rcx+280h]
0x1800cc135  lea     r9, [rbp+7D0h+var_400]
0x1800cc13c  lea     r8d, [rbx+1]
0x1800cc140  mov     rdx, [rsp+8D0h+var_860]
0x1800cc145  mov     rcx, r10
0x1800cc148  call    cs:__guard_dispatch_icall_fptr
0x1800cc14e  mov     r15b, [rbp+7D0h+arg_20]
0x1800cc155  test    r14b, r14b
0x1800cc158  jnz     loc_1800CC33D
0x1800cc15e  mov     rcx, [rsi+8]; this
0x1800cc162  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cc167  mov     r10, rax
0x1800cc16a  mov     rcx, [rax]
0x1800cc16d  mov     rax, [rcx+280h]
0x1800cc174  lea     r9, [rsi+410h]
0x1800cc17b  mov     r8d, 6
0x1800cc181  mov     rdx, [rsp+8D0h+var_860]
0x1800cc186  mov     rcx, r10
0x1800cc189  call    cs:__guard_dispatch_icall_fptr
0x1800cc18f  test    eax, eax
0x1800cc191  jz      short loc_1800CC1D4
0x1800cc193  mov     rcx, [rsi+8]; this
0x1800cc197  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cc19c  mov     r10, rax
0x1800cc19f  mov     rcx, [rax]
0x1800cc1a2  mov     rax, [rcx+270h]
0x1800cc1a9  lea     r9, [rsi+428h]
0x1800cc1b0  mov     [rsp+8D0h+var_8B0], 8
0x1800cc1b9  mov     r8d, 183h
0x1800cc1bf  mov     rdx, [rsp+8D0h+var_860]
0x1800cc1c4  mov     rcx, r10
0x1800cc1c7  call    cs:__guard_dispatch_icall_fptr
0x1800cc1cd  nop
0x1800cc1ce  mov     [rsi+588h], bl
0x1800cc1d4  movzx   edi, r12b
0x1800cc1d8  cmp     byte ptr [rsi+70h], 2
0x1800cc1dc  jz      loc_1800CC825
0x1800cc1e2  movzx   eax, dil
0x1800cc1e6  cmp     byte ptr [rsi+90h], 2
0x1800cc1ed  cmovz   eax, ebx
0x1800cc1f0  test    al, al
0x1800cc1f2  jnz     loc_1800CC6C4
0x1800cc1f8  mov     rdx, [rsp+8D0h+var_860]; struct MSOSP *
0x1800cc1fd  mov     rcx, rsi; this
0x1800cc200  call    ?TranslateAndSetShadowStyle@CPropConverterToLegacy@Art@@QEBAXPEAUMSOSP@@@Z; Art::CPropConverterToLegacy::TranslateAndSetShadowStyle(MSOSP *)
0x1800cc205  mov     rcx, [rsi+8]; this
0x1800cc209  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cc20e  mov     r10, rax
0x1800cc211  mov     rcx, [rax]
0x1800cc214  mov     rax, [rcx+280h]
0x1800cc21b  lea     r9, [rbp+7D0h+var_290]
0x1800cc222  mov     r8d, 7
0x1800cc228  mov     rdx, [rsp+8D0h+var_860]
0x1800cc22d  mov     rcx, r10
0x1800cc230  call    cs:__guard_dispatch_icall_fptr
0x1800cc236  mov     rcx, [rsi+8]; this
0x1800cc23a  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cc23f  mov     r10, rax
0x1800cc242  mov     rcx, [rax]
0x1800cc245  mov     rax, [rcx+280h]
0x1800cc24c  lea     r9, [rbp+7D0h+var_750]
0x1800cc253  mov     r8d, 0Ch
0x1800cc259  mov     rdx, [rsp+8D0h+var_860]
0x1800cc25e  mov     rcx, r10
0x1800cc261  call    cs:__guard_dispatch_icall_fptr
0x1800cc267  mov     rcx, [rsi+8]; this
0x1800cc26b  call    ?GetChecked@CProxyPtrImpl@Ofc@@IEBAPEAXXZ; Ofc::CProxyPtrImpl::GetChecked(void)
0x1800cc270  mov     r10, rax
0x1800cc273  mov     rcx, [rax]
0x1800cc276  mov     rax, [rcx+280h]
0x1800cc27d  lea     r9, [rbp+7D0h+var_350]
  ... truncated ...
```
