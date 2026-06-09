# Art::ThemeVariants::ThemeVariants(Mso::OpenXml::IPackage &,Ofc::TCntPtr<Mso::OpenXml::IPart> &,bool)

- ea: `0x18030e4d4`
- end: `0x18030eca7`
- name: `??0ThemeVariants@Art@@QEAA@AEAUIPackage@OpenXml@Mso@@AEAV?$TCntPtr@UIPart@OpenXml@Mso@@@Ofc@@_N@Z`
- size: `2003`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004071c`

## callees

- `0x18000e1b0`
- `0x18000f870`
- `0x180010220`
- `0x1800143e0`
- `0x180019e80`
- `0x180019f40`
- `0x18002a690`
- `0x1800428ec`
- `0x18007caa0`
- `0x180084c30`
- `0x180128840`
- `0x180139ca0`
- `0x180141230`
- `0x180176424`
- `0x1802769e0`
- `0x180279030`
- `0x180279050`
- `0x1802d56d0`
- `0x18030e4d4`
- `0x18030f43c`
- `0x1803859b4`
- `0x18048adb0`
- `0x180594800`
- `0x18059f97c`
- `0x1806c8720`
- `0x1806c8748`
- `0x1806c8b44`
- `0x1806c8c58`
- `0x1806d17a8`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x18030e930`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18030e968`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18030e930`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18030e968`
- `gfx!?GetDesktopVirtualDPI@Gfx@@YAAEBV?$TConvertibleDPI2@M@1@XZ` at `0x18030ec64`
- `gfx!?GetDesktopVirtualDPI@Gfx@@YAAEBV?$TConvertibleDPI2@M@1@XZ` at `0x18030ec64`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18030e93a`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18030e972`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18030e93a`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18030e972`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18030ea01`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18030ea13`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18030ea01`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x18030ea13`
- `Mso30Win32Client!__imp_?FSet@MetroRelId@@QEAA_NPEB_WI@Z` at `0x18030e765`
- `Mso30Win32Client!__imp_?FSet@MetroRelId@@QEAA_NPEB_WI@Z` at `0x18030e765`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@W4MetroContentType@@@Z` at `0x18030e734`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@W4MetroContentType@@@Z` at `0x18030e734`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x18030e568`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x18030e568`
- `Mso30Win32Client!__imp_??0MetroRelId@@QEAA@XZ` at `0x18030e741`
- `Mso30Win32Client!__imp_??0MetroRelId@@QEAA@XZ` at `0x18030e741`
- `Mso30Win32Client!__imp_?CreateInstance@SaxReaderFactory@MetroXml@Mso@@QEBA?AV?$TCntPtr@UIMetroSAXXMLReader@@@3@XZ` at `0x18030e602`
- `Mso30Win32Client!__imp_?CreateInstance@SaxReaderFactory@MetroXml@Mso@@QEBA?AV?$TCntPtr@UIMetroSAXXMLReader@@@3@XZ` at `0x18030e602`
- `Mso20Win32Client!__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z` at `0x18030e5d3`
- `Mso20Win32Client!__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z` at `0x18030e5d3`

## pseudocode

```c
Ofc::CListImpl *__fastcall Art::ThemeVariants::ThemeVariants(
        Ofc::CListImpl *a1,
        struct ISAXXMLReader *a2,
        _QWORD *a3,
        char a4)
{
  struct Ofc::IRefCountElemLoader *v4; // rdi
  __int64 v5; // r12
  _QWORD *v6; // rsi
  struct ISAXXMLReader *v7; // rbx
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 v11; // rax
  int v12; // eax
  int IStreamFromIBSEx; // eax
  const struct Ofc::CBuiltinNamespaceList *v14; // rdx
  unsigned __int64 v15; // rdx
  unsigned int v16; // r8d
  char *v17; // rax
  unsigned __int64 v18; // rdx
  void **v19; // r8
  Ofc::CSAXReader *v20; // rax
  unsigned int i; // ecx
  char *v22; // rcx
  _OWORD *v23; // rax
  __int64 v24; // rdx
  int *v25; // r9
  unsigned __int64 v26; // rdx
  unsigned int v27; // r8d
  char *v28; // rsi
  __int64 v29; // rax
  int v30; // r15d
  int PowerPointThumbnailFromPackage; // eax
  Art *v32; // rcx
  double v33; // xmm0_8
  int v34; // edx
  bool v35; // r8
  int v36; // edx
  int v37; // eax
  Art *v38; // rcx
  int v39; // r13d
  int v40; // edx
  bool v41; // r8
  double v42; // xmm0_8
  int v43; // edx
  int v44; // eax
  int v45; // r15d
  const wchar_t *v46; // rdx
  unsigned int v47; // edx
  _QWORD *v49; // rcx
  float *DesktopVirtualDPI; // rax
  double v51; // xmm1_8
  char v52; // [rsp+30h] [rbp-D0h] BYREF
  char v53; // [rsp+31h] [rbp-CFh]
  struct ISAXXMLReader *v54; // [rsp+38h] [rbp-C8h] BYREF
  int v55; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v56[4]; // [rsp+48h] [rbp-B8h] BYREF
  int v57; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v58; // [rsp+54h] [rbp-ACh]
  _DWORD v59[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct ISAXXMLReader *v60; // [rsp+60h] [rbp-A0h] BYREF
  struct IByteStream *v61; // [rsp+68h] [rbp-98h] BYREF
  char *v62; // [rsp+70h] [rbp-90h] BYREF
  char *v63; // [rsp+78h] [rbp-88h] BYREF
  __int16 v64; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  struct ISAXXMLReader *v66; // [rsp+90h] [rbp-70h]
  _QWORD *v67; // [rsp+98h] [rbp-68h]
  char v68[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v70; // [rsp+B0h] [rbp-50h]
  Art::Extension *v71; // [rsp+B8h] [rbp-48h]
  double v72[2]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v73[3]; // [rsp+D0h] [rbp-30h] BYREF
  int v74; // [rsp+E8h] [rbp-18h]
  int v75; // [rsp+ECh] [rbp-14h]
  int v76; // [rsp+F0h] [rbp-10h]
  Ofc::CListImpl *v77; // [rsp+F8h] [rbp-8h]
  struct ISAXXMLReader *v78; // [rsp+100h] [rbp+0h]
  struct Ofc::IRefCountElemLoader *v79; // [rsp+108h] [rbp+8h]
  __int64 v80; // [rsp+110h] [rbp+10h]
  _QWORD v81[3]; // [rsp+118h] [rbp+18h] BYREF
  char v82[8]; // [rsp+130h] [rbp+30h] BYREF
  char v83[280]; // [rsp+138h] [rbp+38h] BYREF
  _QWORD v84[2]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v85[24]; // [rsp+260h] [rbp+160h] BYREF
  char v86; // [rsp+278h] [rbp+178h] BYREF
  char v87[48]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v88[528]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v89[560]; // [rsp+6D0h] [rbp+5D0h] BYREF
  char v90[48]; // [rsp+900h] [rbp+800h] BYREF
  wchar_t v91[2088]; // [rsp+930h] [rbp+830h] BYREF

  v53 = a4;
  v6 = a3;
  v67 = a3;
  v7 = a2;
  v66 = a2;
  v77 = a1;
  v9 = 2;
  v10 = 1;
  do
  {
    *(_QWORD *)a1 = 0;
    *((_QWORD *)a1 + 1) = 0;
    --v9;
  }
  while ( v9 );
  v11 = 2;
  do
  {
    *((_QWORD *)a1 + 2) = 0;
    *((_QWORD *)a1 + 3) = 0;
    --v11;
  }
  while ( v11 );
  Mso::OpenXml::RelatedPartParams::RelatedPartParams(v89, 289, 1, 0);
  if ( ((int (__fastcall *)(struct ISAXXMLReader *, _BYTE *, _QWORD, _QWORD *))v7->lpVtbl->putDTDHandler)(
         v7,
         v89,
         0,
         v6) < 0 )
    goto LABEL_62;
  v61 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IByteStream **))(*(_QWORD *)*v6 + 144LL))(*v6, 0, &v61);
  if ( v12 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v12, 0x1E44D309u);
    goto LABEL_67;
  }
  v60 = 0;
  IStreamFromIBSEx = MsoHrGetIStreamFromIBSEx(v61, 0, 0, (struct IStream **)&v60);
  if ( IStreamFromIBSEx < 0 )
  {
LABEL_67:
    Ofc::CHResultException::ThrowTag(IStreamFromIBSEx, 0x1E44D308u);
    goto LABEL_68;
  }
  Ofc::TVector<Art::ThemeVariant,1,4294967295>::TVector<Art::ThemeVariant,1,4294967295>(v68);
  v71 = 0;
  v63 = 0;
  v64 = 0;
  Mso::MetroXml::SaxReaderFactory::CreateInstance(&v63, &v54);
  v7 = v54;
  v54 = 0;
  v78 = v7;
  v81[0] = &Ofc::CDefReaderParams::`vftable';
  v81[1] = v7;
  v81[2] = v84;
  Ofc::CUriTokenizer::CUriTokenizer((Ofc::CUriTokenizer *)v82, v14);
  v52 = 1;
  Ofc::CDefRecoveryHandler::CDefRecoveryHandler(v84, &v52);
  v17 = (char *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v15, v16);
  v4 = (struct Ofc::IRefCountElemLoader *)v17;
  v62 = v17;
  if ( v17 )
  {
    *((_QWORD *)v17 + 1) = v68;
    *(_QWORD *)v17 = &Ofc::TRefCountedElemLoader<Ofc::TCompElemLoader<Art::OSSOverride,Ofc::TSelfAdapter<Art::OSSOverride>,Ofc::TSelfAdapter<Art::OSSOverride>>,Art::OSSOverride>::`vftable';
    *((_DWORD *)v17 + 4) = 0;
    Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl((Ofc::CCompElemLoaderImpl *)(v17 + 32), 1u, 1u);
    v19 = &Ofc::TCompElemLoader<Art::ThemeVariantManager,Ofc::TSelfAdapter<Art::ThemeVariantManager>,Ofc::TSelfAdapter<Art::ThemeVariantManager>>::`vftable';
    *v49 = &Ofc::TCompElemLoader<Art::ThemeVariantManager,Ofc::TSelfAdapter<Art::ThemeVariantManager>,Ofc::TSelfAdapter<Art::ThemeVariantManager>>::`vftable';
    *((_QWORD *)v4 + 3) = v49;
  }
  else
  {
    v4 = 0;
  }
  v79 = v4;
  if ( v4 )
    (*(void (__fastcall **)(struct Ofc::IRefCountElemLoader *))(*(_QWORD *)v4 + 80LL))(v4);
  v73[0] = &Ofc::CXmlName::`vftable';
  v73[1] = L"themeVariantManager";
  v73[2] = 0;
  v74 = 0;
  v75 = 19;
  v76 = 153;
  v20 = (Ofc::CSAXReader *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0xD0, v18, (unsigned int)v19);
  if ( v20 )
    v5 = Ofc::CSAXReader::CSAXReader(v20, (struct Ofc::IReaderParams *)v81, v4, (const struct Ofc::CXmlName *)v73);
  else
    v5 = 0;
  v80 = v5;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  Ofc::ReadSAXStream(v7, v60, (struct IStream *)v5, (struct ISAXContentHandler *)(v5 + 8), 0);
  for ( i = 0; ; i = v58 )
  {
    v10 = i >= v70 ? 0LL : v69 + 56LL * i;
    v58 = i + 1;
    if ( !v10 )
      break;
    Mso::OpenXml::RelatedPartParams::RelatedPartParams(v85, 16);
    MetroRelId::MetroRelId((MetroRelId *)v88);
    MetroRelId::FSet((MetroRelId *)v88, *(const wchar_t **)(v10 + 48), *(_DWORD *)(*(_QWORD *)(v10 + 48) - 4LL) / 2);
    v22 = &v86;
    v23 = v88;
    v24 = 4;
    do
    {
      *(_OWORD *)v22 = *v23;
      *((_OWORD *)v22 + 1) = v23[1];
      *((_OWORD *)v22 + 2) = v23[2];
      *((_OWORD *)v22 + 3) = v23[3];
      *((_OWORD *)v22 + 4) = v23[4];
      *((_OWORD *)v22 + 5) = v23[5];
      *((_OWORD *)v22 + 6) = v23[6];
      v22 += 128;
      *((_OWORD *)v22 - 1) = v23[7];
      v23 += 8;
      --v24;
    }
    while ( v24 );
    *(_QWORD *)v22 = *(_QWORD *)v23;
    v54 = 0;
    if ( (*(int (__fastcall **)(_QWORD, _BYTE *, struct ISAXXMLReader **, _QWORD, _QWORD))(*(_QWORD *)*v6 + 96LL))(
           *v6,
           v85,
           &v54,
           0,
           0) >= 0 )
    {
      v57 = 2084;
      if ( ((int (__fastcall *)(struct ISAXXMLReader *, wchar_t *, int *))v54->lpVtbl->getEntityResolver)(
             v54,
             v91,
             &v57) >= 0
        && Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*(_QWORD *)(v10 + 32)) > 0
        && Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*(_QWORD *)(v10 + 40)) > 0 )
      {
        *(_QWORD *)v56 = &word_180A9C374;
        if ( !Art::FGetLocalizedThemeName(*(Art **)(v10 + 8), v56, 0, v25) )
LABEL_68:
          Ofc::CStr::operator=((Ofc::CStr *)v56, *(void **)(v10 + 8));
        v28 = (char *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x50, v26, v27);
        if ( v28 )
        {
          Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
            &v62,
            v10 + 40);
          Art::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>::CoordMethods<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(
            &v65,
            v10 + 32);
          v46 = *(const wchar_t **)v56;
          *((_DWORD *)v28 + 2) = 0;
          *((_DWORD *)v28 + 2) = 0;
          *(_QWORD *)v28 = &Art::ThemeVariants::Entry::`vftable';
          *((_OWORD *)v28 + 1) = *(_OWORD *)(v10 + 16);
          Ofc::CVarStr::CVarStr((Ofc::CVarStr *)(v28 + 32), v46);
          Ofc::CVarStr::CVarStr((Ofc::CVarStr *)(v28 + 40), v91);
          *((_QWORD *)v28 + 6) = v65;
          *((_QWORD *)v28 + 7) = v62;
          *((_QWORD *)v28 + 8) = 0;
          *((_QWORD *)v28 + 9) = 0;
        }
        else
        {
          v28 = 0;
        }
        v63 = v28;
        if ( v28 )
        {
          v29 = (__int64)(v28 + 8);
          _InterlockedIncrement((volatile signed __int32 *)v28 + 2);
        }
        else
        {
          v29 = 8;
        }
        if ( v28 )
          _InterlockedIncrement((volatile signed __int32 *)v29);
        *Ofc::CListImpl::NewTail(a1) = v28;
        v55 = 0;
        v30 = (int)v66;
        PowerPointThumbnailFromPackage = Art::GetPowerPointThumbnailFromPackage(
                                           (_DWORD)v66,
                                           20,
                                           (int)v28 + 64,
                                           (unsigned int)&v55,
                                           *((_QWORD *)v28 + 5));
        if ( PowerPointThumbnailFromPackage < 0 )
        {
          Ofc::CHResultException::ThrowTag(PowerPointThumbnailFromPackage, 0x1E44D344u);
          __debugbreak();
        }
        if ( v53 )
          Art::GetPowerPointThumbnailFromPackage(v30, 21, (_DWORD)v28 + 72, (unsigned int)&v55, *((_QWORD *)v28 + 5));
        *(float *)&v33 = FLOAT_96_0;
        v59[0] = 1119879168;
        *(float *)&v59[1] = FLOAT_96_0;
        if ( Art::FDynamicDpiEnabled(v32) )
        {
          Art::GetScaleFactor(v59, 0);
          v33 = round((float)(96.0 * 85.0));
          v37 = NetUI::ScaleProportionalToSystemFontPx((NetUI *)(unsigned int)(int)v33, v36);
        }
        else
        {
          LOBYTE(v34) = 1;
          v37 = NetUI::ScalePixelsForSystemSettings((NetUI *)0x55, v34, v35);
        }
        v39 = v37;
        if ( Art::FDynamicDpiEnabled(v38) )
        {
          Art::GetScaleFactor(v59, 0);
          v42 = round((float)(*(float *)&v33 * 48.0));
          v44 = NetUI::ScaleProportionalToSystemFontPx((NetUI *)(unsigned int)(int)v42, v43);
        }
        else
        {
          LOBYTE(v40) = 1;
          v44 = NetUI::ScalePixelsForSystemSettings((NetUI *)0x30, v40, v41);
        }
        v45 = v44;
        if ( (*(int (__fastcall **)(_QWORD))(**((_QWORD **)v28 + 8) + 40LL))(*((_QWORD *)v28 + 8)) > v39
          || (*(int (__fastcall **)(_QWORD))(**((_QWORD **)v28 + 8) + 48LL))(*((_QWORD *)v28 + 8)) > v45 )
        {
          DesktopVirtualDPI = (float *)Gfx::GetDesktopVirtualDPI();
          v51 = DesktopVirtualDPI[1];
          v72[0] = *DesktopVirtualDPI;
          v72[1] = v51;
          Art::ThumbnailHelper::ResizeImage((_DWORD)v28 + 64, v39, v45, 3, (__int64)v72);
        }
        Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v28 + 8);
        Ofc::XString::Release((Ofc::XString *)(*(_QWORD *)v56 - 12LL));
        v6 = v67;
      }
    }
    if ( v54 )
      ((void (__fastcall *)(struct ISAXXMLReader *))v54->lpVtbl->Release)(v54);
    Mso::TCntPtr<Art::CMetroProgress>::Clear(v87);
  }
  Art::ThemeVariants::InitVariantsList(a1);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v4 )
    (*(void (__fastcall **)(struct Ofc::IRefCountElemLoader *))(*(_QWORD *)v4 + 88LL))(v4);
  v81[0] = &Ofc::CDefReaderParams::`vftable';
  v84[0] = &Ofc::CDefRecoveryHandler::`vftable';
  Ofc::TFixedVarArray<Ofc::CUriTokenizer::PointerTokenPair,16>::~TFixedVarArray<Ofc::CUriTokenizer::PointerTokenPair,16>(v83);
  if ( v7 )
    ((void (__fastcall *)(struct ISAXXMLReader *))v7->lpVtbl->Release)(v7);
  if ( v71 )
    Art::Extension::`scalar deleting destructor'(v71, v47);
  Ofc::TArray<Art::ThemeVariant>::~TArray<Art::ThemeVariant>(&v69);
  if ( v60 )
    ((void (__fastcall *)(struct ISAXXMLReader *))v60->lpVtbl->Release)(v60);
  if ( v61 )
    (*(void (__fastcall **)(struct IByteStream *))(*(_QWORD *)v61 + 16LL))(v61);
LABEL_62:
  Mso::TCntPtr<Art::CMetroProgress>::Clear(v90);
  return a1;
}

```

## disassembly

```asm
0x18030e4d4  mov     [rsp-8+arg_18], rbx
0x18030e4d9  push    rbp
0x18030e4da  push    rsi
0x18030e4db  push    rdi
0x18030e4dc  push    r12
0x18030e4de  push    r13
0x18030e4e0  push    r14
0x18030e4e2  push    r15
0x18030e4e4  lea     rbp, [rsp-18A0h]
0x18030e4ec  mov     eax, 19A0h
0x18030e4f1  call    _alloca_probe
0x18030e4f6  sub     rsp, rax
0x18030e4f9  movaps  [rsp+19D0h+var_40], xmm7
0x18030e501  mov     rax, cs:__security_cookie
0x18030e508  xor     rax, rsp
0x18030e50b  mov     [rbp+18D0h+var_50], rax
0x18030e512  mov     [rsp+19D0h+var_199F], r9b
0x18030e517  mov     rsi, r8
0x18030e51a  mov     [rbp+18D0h+var_1938], r8
0x18030e51e  mov     rbx, rdx
0x18030e521  mov     [rbp+18D0h+var_1940], rdx
0x18030e525  mov     r14, rcx
0x18030e528  mov     [rbp+18D0h+var_18D8], rcx
0x18030e52c  mov     ecx, 2
0x18030e531  mov     eax, ecx
0x18030e533  xor     r13d, r13d
0x18030e536  lea     r15d, [rcx-1]
0x18030e53a  mov     [r14], r13
0x18030e53d  mov     [r14+8], r13
0x18030e541  sub     rax, r15
0x18030e544  jnz     short loc_18030E53A
0x18030e546  mov     rax, rcx
0x18030e549  mov     [r14+10h], r13
0x18030e54d  mov     [r14+18h], r13
0x18030e551  sub     rax, r15
0x18030e554  jnz     short loc_18030E549
0x18030e556  xor     r9d, r9d
0x18030e559  mov     r8, r15
0x18030e55c  mov     edx, 121h
0x18030e561  lea     rcx, [rbp+18D0h+var_1300]
0x18030e568  call    cs:__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z; Mso::OpenXml::RelatedPartParams::RelatedPartParams(MetroPartType,void const *,MetroContentType)
0x18030e56e  mov     rax, [rbx]
0x18030e571  mov     [rsp+19D0h+var_19B0], r13; struct ISAXErrorHandler *
0x18030e576  mov     r9, rsi
0x18030e579  xor     r8d, r8d
0x18030e57c  lea     rdx, [rbp+18D0h+var_1300]
0x18030e583  mov     rcx, rbx
0x18030e586  mov     rax, [rax+60h]
0x18030e58a  call    cs:__guard_dispatch_icall_fptr
0x18030e590  test    eax, eax
0x18030e592  js      loc_18030EB60
0x18030e598  mov     [rsp+19D0h+var_1968], r13
0x18030e59d  mov     rcx, [rsi]
0x18030e5a0  mov     rax, [rcx]
0x18030e5a3  lea     r8, [rsp+19D0h+var_1968]
0x18030e5a8  xor     edx, edx
0x18030e5aa  mov     rax, [rax+90h]
0x18030e5b1  call    cs:__guard_dispatch_icall_fptr
0x18030e5b7  test    eax, eax
0x18030e5b9  js      loc_18030EC22
0x18030e5bf  mov     [rsp+19D0h+var_1970], r13
0x18030e5c4  lea     r9, [rsp+19D0h+var_1970]
0x18030e5c9  xor     r8d, r8d
0x18030e5cc  xor     edx, edx
0x18030e5ce  mov     rcx, [rsp+19D0h+var_1968]
0x18030e5d3  call    cs:__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z; MsoHrGetIStreamFromIBSEx(IByteStream *,wchar_t const *,IMetroProgress *,IStream * *)
0x18030e5d9  test    eax, eax
0x18030e5db  js      loc_18030EC32
0x18030e5e1  lea     rcx, [rbp+18D0h+var_1930]
0x18030e5e5  call    ??0?$TVector@VThemeVariant@Art@@$00$0PPPPPPPP@@Ofc@@QEAA@XZ; Ofc::TVector<Art::ThemeVariant,1,4294967295>::TVector<Art::ThemeVariant,1,4294967295>(void)
0x18030e5ea  mov     [rbp+18D0h+var_1918], r13
0x18030e5ee  mov     [rsp+19D0h+var_1958], r13
0x18030e5f3  mov     [rbp+18D0h+var_1950], r13w
0x18030e5f8  lea     rdx, [rsp+19D0h+var_1998]
0x18030e5fd  lea     rcx, [rsp+19D0h+var_1958]
0x18030e602  call    cs:__imp_?CreateInstance@SaxReaderFactory@MetroXml@Mso@@QEBA?AV?$TCntPtr@UIMetroSAXXMLReader@@@3@XZ; Mso::MetroXml::SaxReaderFactory::CreateInstance(void)
0x18030e608  mov     rbx, [rsp+19D0h+var_1998]
0x18030e60d  mov     [rsp+19D0h+var_1998], r13
0x18030e612  mov     [rbp+18D0h+var_18D0], rbx
0x18030e616  lea     rax, ??_7CDefReaderParams@Ofc@@6B@; const Ofc::CDefReaderParams::`vftable'
0x18030e61d  mov     [rbp+18D0h+var_18B8], rax
0x18030e621  mov     [rbp+18D0h+var_18B0], rbx
0x18030e625  lea     rax, [rbp+18D0h+var_1780]
0x18030e62c  mov     [rbp+18D0h+var_18A8], rax
0x18030e630  lea     rcx, [rbp+18D0h+var_18A0]; this
0x18030e634  call    ??0CUriTokenizer@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z; Ofc::CUriTokenizer::CUriTokenizer(Ofc::CBuiltinNamespaceList const *)
0x18030e639  mov     [rsp+19D0h+var_19A0], r15b
0x18030e63e  lea     rdx, [rsp+19D0h+var_19A0]
0x18030e643  lea     rcx, [rbp+18D0h+var_1780]
0x18030e64a  call    ??0CDefRecoveryHandler@Ofc@@QEAA@V?$TBitset@E$00@1@@Z; Ofc::CDefRecoveryHandler::CDefRecoveryHandler(Ofc::TBitset<uchar,1>)
0x18030e64f  mov     ecx, 60h ; '`'; this
0x18030e654  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18030e659  mov     rdi, rax
0x18030e65c  mov     [rsp+19D0h+var_1960], rax
0x18030e661  test    rax, rax
0x18030e664  jnz     loc_18030EBCF
0x18030e66a  mov     rdi, r13
0x18030e66d  mov     [rbp+18D0h+var_18C8], rdi
0x18030e671  test    rdi, rdi
0x18030e674  jz      short loc_18030E687
0x18030e676  mov     rax, [rdi]
0x18030e679  mov     rcx, rdi
0x18030e67c  mov     rax, [rax+50h]
0x18030e680  call    cs:__guard_dispatch_icall_fptr
0x18030e686  nop
0x18030e687  lea     rax, ??_7CXmlName@Ofc@@6B@; const Ofc::CXmlName::`vftable'
0x18030e68e  mov     [rbp+18D0h+var_1900], rax
0x18030e692  lea     rax, aThemevariantma; "themeVariantManager"
0x18030e699  mov     [rbp+18D0h+var_18F8], rax
0x18030e69d  mov     [rbp+18D0h+var_18F0], r13
0x18030e6a1  mov     [rbp+18D0h+var_18E8], r13d
0x18030e6a5  mov     [rbp+18D0h+var_18E4], 13h
0x18030e6ac  mov     [rbp+18D0h+var_18E0], 99h
0x18030e6b3  mov     ecx, 0D0h; this
0x18030e6b8  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18030e6bd  test    rax, rax
0x18030e6c0  jnz     loc_18030EC07
0x18030e6c6  mov     r12, r13
0x18030e6c9  mov     [rbp+18D0h+var_18C0], r12
0x18030e6cd  test    r12, r12
0x18030e6d0  jz      short loc_18030E6E4
0x18030e6d2  mov     rax, [r12]
0x18030e6d6  mov     rcx, r12
0x18030e6d9  mov     rax, [rax+8]
0x18030e6dd  call    cs:__guard_dispatch_icall_fptr
0x18030e6e3  nop
0x18030e6e4  lea     r9, [r12+8]; struct ISAXContentHandler *
0x18030e6e9  mov     r8, r12; struct IStream *
0x18030e6ec  mov     rdx, [rsp+19D0h+var_1970]; struct ISAXXMLReader *
0x18030e6f1  mov     rcx, rbx; this
0x18030e6f4  call    ?ReadSAXStream@Ofc@@YAXAEAUISAXXMLReader@@AEAUIStream@@AEAUISAXContentHandler@@AEAUISAXErrorHandler@@@Z; Ofc::ReadSAXStream(ISAXXMLReader &,IStream &,ISAXContentHandler &,ISAXErrorHandler &)
0x18030e6f9  mov     ecx, r13d
0x18030e6fc  movsd   xmm7, cs:__real@c1e0000000000000
0x18030e704  cmp     ecx, [rbp+18D0h+var_1920]
0x18030e707  jnb     loc_18030EA95
0x18030e70d  mov     eax, ecx
0x18030e70f  imul    r15, rax, 38h ; '8'
0x18030e713  add     r15, [rbp+18D0h+var_1928]
0x18030e717  inc     ecx
0x18030e719  mov     [rsp+19D0h+var_197C], ecx
0x18030e71d  test    r15, r15
0x18030e720  jz      loc_18030EA9D
0x18030e726  xor     r8d, r8d
0x18030e729  lea     edx, [r8+10h]
0x18030e72d  lea     rcx, [rbp+18D0h+var_1770]
0x18030e734  call    cs:__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@W4MetroContentType@@@Z; Mso::OpenXml::RelatedPartParams::RelatedPartParams(MetroPartType,MetroContentType)
0x18030e73a  lea     rcx, [rbp+18D0h+var_1510]
0x18030e741  call    cs:__imp_??0MetroRelId@@QEAA@XZ; MetroRelId::MetroRelId(void)
0x18030e747  mov     rcx, [r15+30h]
0x18030e74b  mov     eax, [rcx-4]
0x18030e74e  cdq
0x18030e74f  mov     r8d, 2
0x18030e755  idiv    r8d
0x18030e758  mov     r8d, eax
0x18030e75b  mov     rdx, rcx
0x18030e75e  lea     rcx, [rbp+18D0h+var_1510]
0x18030e765  call    cs:__imp_?FSet@MetroRelId@@QEAA_NPEB_WI@Z; MetroRelId::FSet(wchar_t const *,uint)
0x18030e76b  lea     rcx, [rbp+18D0h+var_1758]
0x18030e772  lea     rax, [rbp+18D0h+var_1510]
0x18030e779  mov     edx, 4
0x18030e77e  lea     r8d, [rdx+7Ch]
0x18030e782  movups  xmm0, xmmword ptr [rax]
0x18030e785  movups  xmmword ptr [rcx], xmm0
0x18030e788  movups  xmm1, xmmword ptr [rax+10h]
0x18030e78c  movups  xmmword ptr [rcx+10h], xmm1
0x18030e790  movups  xmm0, xmmword ptr [rax+20h]
0x18030e794  movups  xmmword ptr [rcx+20h], xmm0
0x18030e798  movups  xmm1, xmmword ptr [rax+30h]
0x18030e79c  movups  xmmword ptr [rcx+30h], xmm1
0x18030e7a0  movups  xmm0, xmmword ptr [rax+40h]
0x18030e7a4  movups  xmmword ptr [rcx+40h], xmm0
0x18030e7a8  movups  xmm1, xmmword ptr [rax+50h]
0x18030e7ac  movups  xmmword ptr [rcx+50h], xmm1
0x18030e7b0  movups  xmm0, xmmword ptr [rax+60h]
0x18030e7b4  movups  xmmword ptr [rcx+60h], xmm0
0x18030e7b8  add     rcx, r8
0x18030e7bb  movups  xmm1, xmmword ptr [rax+70h]
0x18030e7bf  movups  xmmword ptr [rcx-10h], xmm1
0x18030e7c3  add     rax, r8
0x18030e7c6  sub     rdx, 1
0x18030e7ca  jnz     short loc_18030E782
0x18030e7cc  mov     rax, [rax]
0x18030e7cf  mov     [rcx], rax
0x18030e7d2  mov     [rsp+19D0h+var_1998], r13
0x18030e7d7  mov     rcx, [rsi]
0x18030e7da  mov     rax, [rcx]
0x18030e7dd  mov     [rsp+19D0h+var_19B0], r13
0x18030e7e2  xor     r9d, r9d
0x18030e7e5  lea     r8, [rsp+19D0h+var_1998]
0x18030e7ea  lea     rdx, [rbp+18D0h+var_1770]
0x18030e7f1  mov     rax, [rax+60h]
0x18030e7f5  call    cs:__guard_dispatch_icall_fptr
0x18030e7fb  test    eax, eax
0x18030e7fd  js      loc_18030E9CD
0x18030e803  mov     [rsp+19D0h+var_1980], 824h
0x18030e80b  mov     rcx, [rsp+19D0h+var_1998]
0x18030e810  mov     rax, [rcx]
0x18030e813  lea     r8, [rsp+19D0h+var_1980]
0x18030e818  lea     rdx, [rbp+18D0h+var_10A0]
0x18030e81f  mov     rax, [rax+38h]
0x18030e823  call    cs:__guard_dispatch_icall_fptr
0x18030e829  test    eax, eax
0x18030e82b  js      loc_18030E9CD
0x18030e831  mov     rcx, [r15+20h]
0x18030e835  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x18030e83a  test    rax, rax
0x18030e83d  jle     loc_18030E9CD
0x18030e843  mov     rcx, [r15+28h]
0x18030e847  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x18030e84c  test    rax, rax
0x18030e84f  jle     loc_18030E9CA
0x18030e855  lea     rax, word_180A9C374
0x18030e85c  mov     qword ptr [rsp+19D0h+var_1988], rax
0x18030e861  xor     r8d, r8d; struct Ofc::CStr *
0x18030e864  lea     rdx, [rsp+19D0h+var_1988]; wchar_t *
0x18030e869  mov     rcx, [r15+8]; this
0x18030e86d  call    ?FGetLocalizedThemeName@Art@@YA_NPEB_WAEAVCStr@Ofc@@PEAH@Z; Art::FGetLocalizedThemeName(wchar_t const *,Ofc::CStr &,int *)
0x18030e872  test    al, al
0x18030e874  jz      loc_18030EC45
0x18030e87a  mov     ecx, 50h ; 'P'; this
0x18030e87f  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x18030e884  mov     rsi, rax
0x18030e887  test    rax, rax
0x18030e88a  jnz     loc_18030EA1E
0x18030e890  xor     r13d, r13d
0x18030e893  mov     esi, r13d
0x18030e896  mov     [rsp+19D0h+var_1958], rsi
0x18030e89b  test    rsi, rsi
0x18030e89e  jnz     loc_18030EC58
0x18030e8a4  lea     eax, [rsi+8]
0x18030e8a7  test    rsi, rsi
0x18030e8aa  jz      short loc_18030E8AF
0x18030e8ac  lock inc dword ptr [rax]
0x18030e8af  mov     rcx, r14; this
0x18030e8b2  call    ?NewTail@CListImpl@Ofc@@IEAAPEAPEAXXZ; Ofc::CListImpl::NewTail(void)
0x18030e8b7  mov     [rax], rsi
0x18030e8ba  mov     [rsp+19D0h+var_1990], r13d
0x18030e8bf  mov     rax, [rsi+28h]
0x18030e8c3  lea     r8, [rsi+40h]
0x18030e8c7  mov     [rsp+19D0h+var_19B0], rax
0x18030e8cc  lea     r9, [rsp+19D0h+var_1990]
0x18030e8d1  mov     edx, 14h
0x18030e8d6  mov     r15, [rbp+18D0h+var_1940]
0x18030e8da  mov     rcx, r15
0x18030e8dd  call    ?GetPowerPointThumbnailFromPackage@Art@@YAJAEAUIPackage@OpenXml@Mso@@W4MetroPartType@@AEAV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAKPEB_W@Z; Art::GetPowerPointThumbnailFromPackage(Mso::OpenXml::IPackage &,MetroPartType,Ofc::TCntPtr<GEL::IImage> &,ulong *,wchar_t const *)
0x18030e8e2  test    eax, eax
0x18030e8e4  js      loc_18030EB9E
0x18030e8ea  cmp     [rsp+19D0h+var_199F], r13b
0x18030e8ef  jnz     loc_18030EBAB
0x18030e8f5  movss   xmm0, cs:__real@42c00000
0x18030e8fd  mov     [rsp+19D0h+var_1978], 42C00000h
0x18030e905  movss   [rsp+19D0h+var_1974], xmm0
0x18030e90b  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x18030e910  test    al, al
0x18030e912  jz      loc_18030E9FA
0x18030e918  xor     edx, edx
0x18030e91a  lea     rcx, [rsp+19D0h+var_1978]
0x18030e91f  call    ?GetScaleFactor@Art@@YAMAEBV?$TConvertibleDPI2@M@Gfx@@_N@Z; Art::GetScaleFactor(Gfx::TConvertibleDPI2<float> const &,bool)
0x18030e924  mulss   xmm0, cs:__real@42aa0000
0x18030e92c  cvtss2sd xmm0, xmm0; X
0x18030e930  call    cs:__imp_round
0x18030e936  cvttsd2si ecx, xmm0
0x18030e93a  call    cs:__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z; NetUI::ScaleProportionalToSystemFontPx(int)
0x18030e940  mov     r13d, eax
0x18030e943  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x18030e948  test    al, al
0x18030e94a  jz      loc_18030EA0C
0x18030e950  xor     edx, edx
0x18030e952  lea     rcx, [rsp+19D0h+var_1978]
0x18030e957  call    ?GetScaleFactor@Art@@YAMAEBV?$TConvertibleDPI2@M@Gfx@@_N@Z; Art::GetScaleFactor(Gfx::TConvertibleDPI2<float> const &,bool)
0x18030e95c  mulss   xmm0, cs:__real@42400000
0x18030e964  cvtss2sd xmm0, xmm0; X
0x18030e968  call    cs:__imp_round
0x18030e96e  cvttsd2si ecx, xmm0
0x18030e972  call    cs:__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z; NetUI::ScaleProportionalToSystemFontPx(int)
0x18030e978  mov     r15d, eax
0x18030e97b  mov     rcx, [rsi+40h]
0x18030e97f  mov     rax, [rcx]
0x18030e982  mov     rax, [rax+28h]
0x18030e986  call    cs:__guard_dispatch_icall_fptr
0x18030e98c  cmp     eax, r13d
0x18030e98f  jg      loc_18030EC64
0x18030e995  mov     rcx, [rsi+40h]
0x18030e999  mov     rax, [rcx]
0x18030e99c  mov     rax, [rax+30h]
0x18030e9a0  call    cs:__guard_dispatch_icall_fptr
0x18030e9a6  cmp     eax, r15d
0x18030e9a9  jg      loc_18030EC64
0x18030e9af  lea     rcx, [rsi+8]
0x18030e9b3  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x18030e9b8  mov     rcx, qword ptr [rsp+19D0h+var_1988]
0x18030e9bd  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x18030e9c1  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x18030e9c6  mov     rsi, [rbp+18D0h+var_1938]
0x18030e9ca  xor     r13d, r13d
0x18030e9cd  mov     rcx, [rsp+19D0h+var_1998]
0x18030e9d2  test    rcx, rcx
0x18030e9d5  jz      short loc_18030E9E5
0x18030e9d7  mov     rax, [rcx]
0x18030e9da  mov     rax, [rax+10h]
  ... truncated ...
```
