# Art::ThemeVariants::ThemeVariants(Mso::OpenXml::IPackage &,Ofc::TCntPtr<Mso::OpenXml::IPart> &,bool)

- ea: `0x180153100`
- end: `0x1801538b4`
- name: `??0ThemeVariants@Art@@QEAA@AEAUIPackage@OpenXml@Mso@@AEAV?$TCntPtr@UIPart@OpenXml@Mso@@@Ofc@@_N@Z`
- size: `1972`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180261274`

## callees

- `0x18000dbc0`
- `0x18000dc24`
- `0x18000dc60`
- `0x18001e0f0`
- `0x180038180`
- `0x1800381b0`
- `0x180038460`
- `0x1800505f0`
- `0x180059cbc`
- `0x1800659a0`
- `0x180070fe0`
- `0x180071720`
- `0x1800cba88`
- `0x180152ee0`
- `0x180153100`
- `0x1801541a4`
- `0x1801aa600`
- `0x1801b09dc`
- `0x180262310`
- `0x1802c6d30`
- `0x1802dcdc4`
- `0x18057146c`
- `0x180580610`
- `0x1806b2e90`
- `0x1806b2eb8`
- `0x1806b32b4`
- `0x1806b33c8`
- `0x1806bcc08`

## import_xrefs

- `api-ms-win-crt-math-l1-1-0!round` at `0x180153555`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015358c`
- `api-ms-win-crt-math-l1-1-0!round` at `0x180153555`
- `api-ms-win-crt-math-l1-1-0!round` at `0x18015358c`
- `gfx!?GetDesktopVirtualDPI@Gfx@@YAAEBV?$TConvertibleDPI2@M@1@XZ` at `0x180153873`
- `gfx!?GetDesktopVirtualDPI@Gfx@@YAAEBV?$TConvertibleDPI2@M@1@XZ` at `0x180153873`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18015355f`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x180153596`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x18015355f`
- `mso40uiWin32Client!__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z` at `0x180153596`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x180153627`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x180153639`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x180153627`
- `mso40uiWin32Client!__imp_?ScalePixelsForSystemSettings@NetUI@@YAHH_N@Z` at `0x180153639`
- `Mso30Win32Client!__imp_?FSet@MetroRelId@@QEAA_NPEB_WI@Z` at `0x180153391`
- `Mso30Win32Client!__imp_?FSet@MetroRelId@@QEAA_NPEB_WI@Z` at `0x180153391`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@W4MetroContentType@@@Z` at `0x180153362`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@W4MetroContentType@@@Z` at `0x180153362`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x180153198`
- `Mso30Win32Client!__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z` at `0x180153198`
- `Mso30Win32Client!__imp_??0MetroRelId@@QEAA@XZ` at `0x18015336f`
- `Mso30Win32Client!__imp_??0MetroRelId@@QEAA@XZ` at `0x18015336f`
- `Mso30Win32Client!__imp_?CreateInstance@SaxReaderFactory@MetroXml@Mso@@QEBA?AV?$TCntPtr@UIMetroSAXXMLReader@@@3@XZ` at `0x180153230`
- `Mso30Win32Client!__imp_?CreateInstance@SaxReaderFactory@MetroXml@Mso@@QEBA?AV?$TCntPtr@UIMetroSAXXMLReader@@@3@XZ` at `0x180153230`
- `Mso20Win32Client!__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z` at `0x180153203`
- `Mso20Win32Client!__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z` at `0x180153203`

## pseudocode

```c
Ofc::CListImpl *__fastcall Art::ThemeVariants::ThemeVariants(Ofc::CListImpl *a1, __int64 a2, _QWORD *a3, char a4)
{
  struct ISAXXMLReader *v4; // rbx
  struct Ofc::IRefCountElemLoader *v5; // r14
  _QWORD *v6; // r15
  __int64 v7; // rsi
  __int64 v9; // rax
  __int64 v10; // r13
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
  __int64 v21; // rdi
  unsigned int i; // ecx
  char *v23; // rcx
  _OWORD *v24; // rax
  __int64 v25; // rdx
  int *v26; // r9
  unsigned __int64 v27; // rdx
  unsigned int v28; // r8d
  __int64 *v29; // r15
  __int64 v30; // rax
  _QWORD *v31; // r13
  int PowerPointThumbnailFromPackage; // eax
  Art *v33; // rcx
  double v34; // xmm0_8
  int v35; // edx
  bool v36; // r8
  int v37; // edx
  int v38; // eax
  Art *v39; // rcx
  int v40; // esi
  int v41; // edx
  bool v42; // r8
  double v43; // xmm0_8
  int v44; // edx
  int v45; // eax
  int v46; // edi
  __int64 v47; // rdi
  const wchar_t *v48; // rdx
  unsigned int v49; // edx
  _QWORD *v51; // rcx
  float *DesktopVirtualDPI; // rax
  double v53; // xmm1_8
  char v54; // [rsp+30h] [rbp-D0h] BYREF
  char v55; // [rsp+31h] [rbp-CFh]
  struct ISAXXMLReader *v56; // [rsp+38h] [rbp-C8h] BYREF
  int v57; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t v58[4]; // [rsp+48h] [rbp-B8h] BYREF
  int v59; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v60; // [rsp+54h] [rbp-ACh]
  _DWORD v61[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct ISAXXMLReader *v62; // [rsp+60h] [rbp-A0h] BYREF
  struct IByteStream *v63; // [rsp+68h] [rbp-98h] BYREF
  char *v64; // [rsp+70h] [rbp-90h]
  __int64 v65; // [rsp+78h] [rbp-88h]
  __int64 *v66; // [rsp+80h] [rbp-80h] BYREF
  __int16 v67; // [rsp+88h] [rbp-78h]
  _QWORD *v68; // [rsp+90h] [rbp-70h]
  char v69[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v71; // [rsp+A8h] [rbp-58h]
  Art::Extension *v72; // [rsp+B0h] [rbp-50h]
  double v73[2]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v74[3]; // [rsp+C8h] [rbp-38h] BYREF
  int v75; // [rsp+E0h] [rbp-20h]
  int v76; // [rsp+E4h] [rbp-1Ch]
  int v77; // [rsp+E8h] [rbp-18h]
  Ofc::CListImpl *v78; // [rsp+F0h] [rbp-10h]
  struct ISAXXMLReader *v79; // [rsp+F8h] [rbp-8h]
  struct Ofc::IRefCountElemLoader *v80; // [rsp+100h] [rbp+0h]
  __int64 v81; // [rsp+108h] [rbp+8h]
  _QWORD v82[3]; // [rsp+110h] [rbp+10h] BYREF
  char v83[8]; // [rsp+128h] [rbp+28h] BYREF
  char v84[280]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v85[3]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v86[24]; // [rsp+260h] [rbp+160h] BYREF
  char v87; // [rsp+278h] [rbp+178h] BYREF
  char v88[48]; // [rsp+490h] [rbp+390h] BYREF
  _BYTE v89[528]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v90[560]; // [rsp+6D0h] [rbp+5D0h] BYREF
  char v91[48]; // [rsp+900h] [rbp+800h] BYREF
  wchar_t v92[2088]; // [rsp+930h] [rbp+830h] BYREF

  v55 = a4;
  v6 = a3;
  v68 = a3;
  v7 = a2;
  v65 = a2;
  v78 = a1;
  v9 = 2;
  v10 = 0;
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
  Mso::OpenXml::RelatedPartParams::RelatedPartParams(v90, 289, 1, 0);
  if ( (*(int (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD *))(*(_QWORD *)v7 + 96LL))(v7, v90, 0, v6) < 0 )
    goto LABEL_63;
  v63 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IByteStream **))(*(_QWORD *)*v6 + 144LL))(*v6, 0, &v63);
  if ( v12 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v12, 0x1E44D309u);
    goto LABEL_66;
  }
  v62 = 0;
  IStreamFromIBSEx = MsoHrGetIStreamFromIBSEx(v63, 0, 0, (struct IStream **)&v62);
  if ( IStreamFromIBSEx < 0 )
  {
LABEL_66:
    Ofc::CHResultException::ThrowTag(IStreamFromIBSEx, 0x1E44D308u);
    goto LABEL_67;
  }
  Ofc::TVector<Art::ThemeVariant,1,4294967295>::TVector<Art::ThemeVariant,1,4294967295>(v69);
  v72 = 0;
  v66 = 0;
  v67 = 0;
  Mso::MetroXml::SaxReaderFactory::CreateInstance(&v66, &v56);
  v4 = v56;
  v56 = 0;
  v79 = v4;
  v82[0] = &Ofc::CDefReaderParams::`vftable';
  v82[1] = v4;
  v82[2] = v85;
  Ofc::CUriTokenizer::CUriTokenizer((Ofc::CUriTokenizer *)v83, v14);
  v54 = 1;
  Ofc::CDefRecoveryHandler::CDefRecoveryHandler(v85, &v54);
  v17 = (char *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x60, v15, v16);
  v5 = (struct Ofc::IRefCountElemLoader *)v17;
  v64 = v17;
  if ( v17 )
  {
    *((_QWORD *)v17 + 1) = v69;
    *(_QWORD *)v17 = &Ofc::TRefCountedElemLoader<Ofc::TCompElemLoader<Art::OSSOverride,Ofc::TSelfAdapter<Art::OSSOverride>,Ofc::TSelfAdapter<Art::OSSOverride>>,Art::OSSOverride>::`vftable';
    *((_DWORD *)v17 + 4) = 0;
    Ofc::CCompElemLoaderImpl::CCompElemLoaderImpl((Ofc::CCompElemLoaderImpl *)(v17 + 32), 1u, 1u);
    v19 = &Ofc::TCompElemLoader<Art::ThemeVariantManager,Ofc::TSelfAdapter<Art::ThemeVariantManager>,Ofc::TSelfAdapter<Art::ThemeVariantManager>>::`vftable';
    *v51 = &Ofc::TCompElemLoader<Art::ThemeVariantManager,Ofc::TSelfAdapter<Art::ThemeVariantManager>,Ofc::TSelfAdapter<Art::ThemeVariantManager>>::`vftable';
    *((_QWORD *)v5 + 3) = v51;
  }
  else
  {
    v5 = 0;
  }
  v80 = v5;
  if ( v5 )
    (*(void (__fastcall **)(struct Ofc::IRefCountElemLoader *))(*(_QWORD *)v5 + 80LL))(v5);
  v74[0] = &Ofc::CXmlName::`vftable';
  v74[1] = L"themeVariantManager";
  v74[2] = 0;
  v75 = 0;
  v76 = 19;
  v77 = 153;
  v20 = (Ofc::CSAXReader *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0xD0, v18, (unsigned int)v19);
  if ( !v20 )
  {
    v21 = 0;
    goto LABEL_14;
  }
LABEL_67:
  v21 = Ofc::CSAXReader::CSAXReader(v20, (struct Ofc::IReaderParams *)v82, v5, (const struct Ofc::CXmlName *)v74);
LABEL_14:
  v64 = (char *)v21;
  v81 = v21;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
  Ofc::ReadSAXStream(v4, v62, (struct IStream *)v21, (struct ISAXContentHandler *)(v21 + 8), 0);
  for ( i = 0; ; i = v60 )
  {
    if ( i < v71 )
      v10 = v70 + 56LL * i;
    v60 = i + 1;
    if ( !v10 )
      break;
    Mso::OpenXml::RelatedPartParams::RelatedPartParams(v86, 16);
    MetroRelId::MetroRelId((MetroRelId *)v89);
    MetroRelId::FSet((MetroRelId *)v89, *(const wchar_t **)(v10 + 48), *(_DWORD *)(*(_QWORD *)(v10 + 48) - 4LL) / 2);
    v23 = &v87;
    v24 = v89;
    v25 = 4;
    do
    {
      *(_OWORD *)v23 = *v24;
      *((_OWORD *)v23 + 1) = v24[1];
      *((_OWORD *)v23 + 2) = v24[2];
      *((_OWORD *)v23 + 3) = v24[3];
      *((_OWORD *)v23 + 4) = v24[4];
      *((_OWORD *)v23 + 5) = v24[5];
      *((_OWORD *)v23 + 6) = v24[6];
      v23 += 128;
      *((_OWORD *)v23 - 1) = v24[7];
      v24 += 8;
      --v25;
    }
    while ( v25 );
    *(_QWORD *)v23 = *(_QWORD *)v24;
    v56 = 0;
    if ( (*(int (__fastcall **)(_QWORD, _BYTE *, struct ISAXXMLReader **, _QWORD, _QWORD))(*(_QWORD *)*v6 + 96LL))(
           *v6,
           v86,
           &v56,
           0,
           0) >= 0 )
    {
      v59 = 2084;
      if ( ((int (__fastcall *)(struct ISAXXMLReader *, wchar_t *, int *))v56->lpVtbl->getEntityResolver)(
             v56,
             v92,
             &v59) >= 0
        && Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*(_QWORD *)(v10 + 32)) > 0
        && Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*(_QWORD *)(v10 + 40)) > 0 )
      {
        *(_QWORD *)v58 = &word_180A77374;
        if ( !Art::FGetLocalizedThemeName(*(Art **)(v10 + 8), v58, 0, v26) )
          Ofc::CStr::operator=((Ofc::CStr *)v58, *(void **)(v10 + 8));
        v29 = (__int64 *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x50, v27, v28);
        if ( v29 )
        {
          v7 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*(_QWORD *)(v10 + 40));
          v47 = Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(*(_QWORD *)(v10 + 32));
          v48 = *(const wchar_t **)v58;
          *((_DWORD *)v29 + 2) = 0;
          *((_DWORD *)v29 + 2) = 0;
          *v29 = (__int64)&Art::ThemeVariants::Entry::`vftable';
          *((_OWORD *)v29 + 1) = *(_OWORD *)(v10 + 16);
          Ofc::CVarStr::CVarStr((Ofc::CVarStr *)(v29 + 4), v48);
          Ofc::CVarStr::CVarStr((Ofc::CVarStr *)(v29 + 5), v92);
          v29[6] = v47;
          v29[7] = v7;
          v29[8] = 0;
          v29[9] = 0;
          LODWORD(v7) = v65;
        }
        else
        {
          v29 = 0;
        }
        v66 = v29;
        if ( v29 )
        {
          v30 = (__int64)(v29 + 1);
          _InterlockedIncrement((volatile signed __int32 *)v29 + 2);
        }
        else
        {
          v30 = 8;
        }
        if ( v29 )
          _InterlockedIncrement((volatile signed __int32 *)v30);
        *Ofc::CListImpl::NewTail(a1) = v29;
        v57 = 0;
        v31 = v29 + 8;
        PowerPointThumbnailFromPackage = Art::GetPowerPointThumbnailFromPackage(
                                           v7,
                                           20,
                                           (int)v29 + 64,
                                           (unsigned int)&v57,
                                           v29[5]);
        if ( PowerPointThumbnailFromPackage < 0 )
        {
          Ofc::CHResultException::ThrowTag(PowerPointThumbnailFromPackage, 0x1E44D344u);
          break;
        }
        if ( v55 )
          Art::GetPowerPointThumbnailFromPackage(v7, 21, (_DWORD)v29 + 72, (unsigned int)&v57, v29[5]);
        *(float *)&v34 = FLOAT_96_0;
        v61[0] = 1119879168;
        *(float *)&v61[1] = FLOAT_96_0;
        if ( Art::FDynamicDpiEnabled(v33) )
        {
          Art::GetScaleFactor(v61, 0);
          v34 = round((float)(96.0 * 85.0));
          v38 = NetUI::ScaleProportionalToSystemFontPx((NetUI *)(unsigned int)(int)v34, v37);
        }
        else
        {
          LOBYTE(v35) = 1;
          v38 = NetUI::ScalePixelsForSystemSettings((NetUI *)0x55, v35, v36);
        }
        v40 = v38;
        if ( Art::FDynamicDpiEnabled(v39) )
        {
          Art::GetScaleFactor(v61, 0);
          v43 = round((float)(*(float *)&v34 * 48.0));
          v45 = NetUI::ScaleProportionalToSystemFontPx((NetUI *)(unsigned int)(int)v43, v44);
        }
        else
        {
          LOBYTE(v41) = 1;
          v45 = NetUI::ScalePixelsForSystemSettings((NetUI *)0x30, v41, v42);
        }
        v46 = v45;
        if ( (*(int (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 40LL))(*v31) > v40
          || (*(int (__fastcall **)(_QWORD))(*(_QWORD *)*v31 + 48LL))(*v31) > v46 )
        {
          DesktopVirtualDPI = (float *)Gfx::GetDesktopVirtualDPI();
          v53 = DesktopVirtualDPI[1];
          v73[0] = *DesktopVirtualDPI;
          v73[1] = v53;
          Art::ThumbnailHelper::ResizeImage((_DWORD)v29 + 64, v40, v46, 3, (__int64)v73);
        }
        Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(v29 + 1);
        Ofc::XString::Release((Ofc::XString *)(*(_QWORD *)v58 - 12LL));
        LODWORD(v7) = v65;
        v6 = v68;
      }
    }
    v10 = 0;
    if ( v56 )
      ((void (__fastcall *)(struct ISAXXMLReader *))v56->lpVtbl->Release)(v56);
    Mso::TCntPtr<Art::CMetroProgress>::Clear(v88);
  }
  Art::ThemeVariants::InitVariantsList(a1);
  if ( v64 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v64 + 16LL))(v64);
  if ( v5 )
    (*(void (__fastcall **)(struct Ofc::IRefCountElemLoader *))(*(_QWORD *)v5 + 88LL))(v5);
  v82[0] = &Ofc::CDefReaderParams::`vftable';
  v85[0] = &Ofc::CDefRecoveryHandler::`vftable';
  Ofc::TFixedVarArray<Ofc::CUriTokenizer::PointerTokenPair,16>::~TFixedVarArray<Ofc::CUriTokenizer::PointerTokenPair,16>(v84);
  if ( v4 )
    ((void (__fastcall *)(struct ISAXXMLReader *))v4->lpVtbl->Release)(v4);
  if ( v72 )
    Art::Extension::`scalar deleting destructor'(v72, v49);
  Ofc::TArray<Art::ThemeVariant>::~TArray<Art::ThemeVariant>(&v70);
  if ( v62 )
    ((void (__fastcall *)(struct ISAXXMLReader *))v62->lpVtbl->Release)(v62);
  if ( v63 )
    (*(void (__fastcall **)(struct IByteStream *))(*(_QWORD *)v63 + 16LL))(v63);
LABEL_63:
  Mso::TCntPtr<Art::CMetroProgress>::Clear(v91);
  return a1;
}

```

## disassembly

```asm
0x180153100  mov     [rsp-8+arg_18], rbx
0x180153105  push    rbp
0x180153106  push    rsi
0x180153107  push    rdi
0x180153108  push    r12
0x18015310a  push    r13
0x18015310c  push    r14
0x18015310e  push    r15
0x180153110  lea     rbp, [rsp-18A0h]
0x180153118  mov     eax, 19A0h
0x18015311d  call    _alloca_probe
0x180153122  sub     rsp, rax
0x180153125  movaps  [rsp+19D0h+var_40], xmm7
0x18015312d  mov     rax, cs:__security_cookie
0x180153134  xor     rax, rsp
0x180153137  mov     [rbp+18D0h+var_50], rax
0x18015313e  mov     [rsp+19D0h+var_199F], r9b
0x180153143  mov     r15, r8
0x180153146  mov     [rbp+18D0h+var_1940], r8
0x18015314a  mov     rsi, rdx
0x18015314d  mov     [rsp+19D0h+var_1958], rdx
0x180153152  mov     r12, rcx
0x180153155  mov     [rbp+18D0h+var_18E0], rcx
0x180153159  mov     ecx, 2
0x18015315e  mov     eax, ecx
0x180153160  xor     r13d, r13d
0x180153163  lea     edi, [rcx-1]
0x180153166  mov     [r12], r13
0x18015316a  mov     [r12+8], r13
0x18015316f  sub     rax, rdi
0x180153172  jnz     short loc_180153166
0x180153174  mov     rax, rcx
0x180153177  mov     [r12+10h], r13
0x18015317c  mov     [r12+18h], r13
0x180153181  sub     rax, rdi
0x180153184  jnz     short loc_180153177
0x180153186  xor     r9d, r9d
0x180153189  mov     r8, rdi
0x18015318c  mov     edx, 121h
0x180153191  lea     rcx, [rbp+18D0h+var_1300]
0x180153198  call    cs:__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@PEBXW4MetroContentType@@@Z; Mso::OpenXml::RelatedPartParams::RelatedPartParams(MetroPartType,void const *,MetroContentType)
0x18015319e  mov     rax, [rsi]
0x1801531a1  mov     [rsp+19D0h+var_19B0], r13; struct ISAXErrorHandler *
0x1801531a6  mov     r9, r15
0x1801531a9  xor     r8d, r8d
0x1801531ac  lea     rdx, [rbp+18D0h+var_1300]
0x1801531b3  mov     rcx, rsi
0x1801531b6  mov     rax, [rax+60h]
0x1801531ba  call    cs:__guard_dispatch_icall_fptr
0x1801531c0  test    eax, eax
0x1801531c2  js      loc_18015377F
0x1801531c8  mov     [rsp+19D0h+var_1968], r13
0x1801531cd  mov     rcx, [r15]
0x1801531d0  mov     rax, [rcx]
0x1801531d3  lea     r8, [rsp+19D0h+var_1968]
0x1801531d8  xor     edx, edx
0x1801531da  mov     rax, [rax+90h]
0x1801531e1  call    cs:__guard_dispatch_icall_fptr
0x1801531e7  test    eax, eax
0x1801531e9  js      loc_180153818
0x1801531ef  mov     [rsp+19D0h+var_1970], r13
0x1801531f4  lea     r9, [rsp+19D0h+var_1970]
0x1801531f9  xor     r8d, r8d
0x1801531fc  xor     edx, edx
0x1801531fe  mov     rcx, [rsp+19D0h+var_1968]
0x180153203  call    cs:__imp_?MsoHrGetIStreamFromIBSEx@@YAJPEAUIByteStream@@PEB_WPEAUIMetroProgress@@PEAPEAUIStream@@@Z; MsoHrGetIStreamFromIBSEx(IByteStream *,wchar_t const *,IMetroProgress *,IStream * *)
0x180153209  test    eax, eax
0x18015320b  js      loc_180153828
0x180153211  lea     rcx, [rbp+18D0h+var_1938]
0x180153215  call    ??0?$TVector@VThemeVariant@Art@@$00$0PPPPPPPP@@Ofc@@QEAA@XZ; Ofc::TVector<Art::ThemeVariant,1,4294967295>::TVector<Art::ThemeVariant,1,4294967295>(void)
0x18015321a  mov     [rbp+18D0h+var_1920], r13
0x18015321e  mov     [rbp+18D0h+var_1950], r13
0x180153222  mov     [rbp+18D0h+var_1948], r13w
0x180153227  lea     rdx, [rsp+19D0h+var_1998]
0x18015322c  lea     rcx, [rbp+18D0h+var_1950]
0x180153230  call    cs:__imp_?CreateInstance@SaxReaderFactory@MetroXml@Mso@@QEBA?AV?$TCntPtr@UIMetroSAXXMLReader@@@3@XZ; Mso::MetroXml::SaxReaderFactory::CreateInstance(void)
0x180153236  mov     rbx, [rsp+19D0h+var_1998]
0x18015323b  mov     [rsp+19D0h+var_1998], r13
0x180153240  mov     [rbp+18D0h+var_18D8], rbx
0x180153244  lea     rax, ??_7CDefReaderParams@Ofc@@6B@; const Ofc::CDefReaderParams::`vftable'
0x18015324b  mov     [rbp+18D0h+var_18C0], rax
0x18015324f  mov     [rbp+18D0h+var_18B8], rbx
0x180153253  lea     rax, [rbp+18D0h+var_1788]
0x18015325a  mov     [rbp+18D0h+var_18B0], rax
0x18015325e  lea     rcx, [rbp+18D0h+var_18A8]; this
0x180153262  call    ??0CUriTokenizer@Ofc@@QEAA@PEBUCBuiltinNamespaceList@1@@Z; Ofc::CUriTokenizer::CUriTokenizer(Ofc::CBuiltinNamespaceList const *)
0x180153267  mov     [rsp+19D0h+var_19A0], dil
0x18015326c  lea     rdx, [rsp+19D0h+var_19A0]
0x180153271  lea     rcx, [rbp+18D0h+var_1788]
0x180153278  call    ??0CDefRecoveryHandler@Ofc@@QEAA@V?$TBitset@E$00@1@@Z; Ofc::CDefRecoveryHandler::CDefRecoveryHandler(Ofc::TBitset<uchar,1>)
0x18015327d  mov     ecx, 60h ; '`'; this
0x180153282  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180153287  mov     r14, rax
0x18015328a  mov     [rsp+19D0h+var_1960], rax
0x18015328f  test    rax, rax
0x180153292  jnz     loc_1801537E1
0x180153298  mov     r14, r13
0x18015329b  mov     [rbp+18D0h+var_18D0], r14
0x18015329f  test    r14, r14
0x1801532a2  jz      short loc_1801532B5
0x1801532a4  mov     rax, [r14]
0x1801532a7  mov     rcx, r14
0x1801532aa  mov     rax, [rax+50h]
0x1801532ae  call    cs:__guard_dispatch_icall_fptr
0x1801532b4  nop
0x1801532b5  lea     rax, ??_7CXmlName@Ofc@@6B@; const Ofc::CXmlName::`vftable'
0x1801532bc  mov     [rbp+18D0h+var_1908], rax
0x1801532c0  lea     rax, aThemevariantma; "themeVariantManager"
0x1801532c7  mov     [rbp+18D0h+var_1900], rax
0x1801532cb  mov     [rbp+18D0h+var_18F8], r13
0x1801532cf  mov     [rbp+18D0h+var_18F0], r13d
0x1801532d3  mov     [rbp+18D0h+var_18EC], 13h
0x1801532da  mov     [rbp+18D0h+var_18E8], 99h
0x1801532e1  mov     ecx, 0D0h; this
0x1801532e6  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801532eb  test    rax, rax
0x1801532ee  jnz     loc_180153839
0x1801532f4  mov     rdi, r13
0x1801532f7  mov     [rsp+19D0h+var_1960], rdi
0x1801532fc  mov     [rbp+18D0h+var_18C8], rdi
0x180153300  test    rdi, rdi
0x180153303  jz      short loc_180153316
0x180153305  mov     rax, [rdi]
0x180153308  mov     rcx, rdi
0x18015330b  mov     rax, [rax+8]
0x18015330f  call    cs:__guard_dispatch_icall_fptr
0x180153315  nop
0x180153316  lea     r9, [rdi+8]; struct ISAXContentHandler *
0x18015331a  mov     r8, rdi; struct IStream *
0x18015331d  mov     rdx, [rsp+19D0h+var_1970]; struct ISAXXMLReader *
0x180153322  mov     rcx, rbx; this
0x180153325  call    ?ReadSAXStream@Ofc@@YAXAEAUISAXXMLReader@@AEAUIStream@@AEAUISAXContentHandler@@AEAUISAXErrorHandler@@@Z; Ofc::ReadSAXStream(ISAXXMLReader &,IStream &,ISAXContentHandler &,ISAXErrorHandler &)
0x18015332a  mov     ecx, r13d
0x18015332d  movsd   xmm7, cs:__real@c1e0000000000000
0x180153335  cmp     ecx, [rbp+18D0h+var_1928]
0x180153338  jnb     short loc_180153344
0x18015333a  mov     eax, ecx
0x18015333c  imul    r13, rax, 38h ; '8'
0x180153340  add     r13, [rbp+18D0h+var_1930]
0x180153344  inc     ecx
0x180153346  mov     [rsp+19D0h+var_197C], ecx
0x18015334a  xor     edi, edi
0x18015334c  test    r13, r13
0x18015334f  jz      loc_1801536C5
0x180153355  xor     r8d, r8d
0x180153358  lea     edx, [rdi+10h]
0x18015335b  lea     rcx, [rbp+18D0h+var_1770]
0x180153362  call    cs:__imp_??0RelatedPartParams@OpenXml@Mso@@QEAA@W4MetroPartType@@W4MetroContentType@@@Z; Mso::OpenXml::RelatedPartParams::RelatedPartParams(MetroPartType,MetroContentType)
0x180153368  lea     rcx, [rbp+18D0h+var_1510]
0x18015336f  call    cs:__imp_??0MetroRelId@@QEAA@XZ; MetroRelId::MetroRelId(void)
0x180153375  mov     rcx, [r13+30h]
0x180153379  mov     eax, [rcx-4]
0x18015337c  cdq
0x18015337d  lea     r8d, [rdi+2]
0x180153381  idiv    r8d
0x180153384  mov     r8d, eax
0x180153387  mov     rdx, rcx
0x18015338a  lea     rcx, [rbp+18D0h+var_1510]
0x180153391  call    cs:__imp_?FSet@MetroRelId@@QEAA_NPEB_WI@Z; MetroRelId::FSet(wchar_t const *,uint)
0x180153397  lea     rcx, [rbp+18D0h+var_1758]
0x18015339e  lea     rax, [rbp+18D0h+var_1510]
0x1801533a5  lea     edx, [rdi+4]
0x1801533a8  lea     r8d, [rdx+7Ch]
0x1801533ac  movups  xmm0, xmmword ptr [rax]
0x1801533af  movups  xmmword ptr [rcx], xmm0
0x1801533b2  movups  xmm1, xmmword ptr [rax+10h]
0x1801533b6  movups  xmmword ptr [rcx+10h], xmm1
0x1801533ba  movups  xmm0, xmmword ptr [rax+20h]
0x1801533be  movups  xmmword ptr [rcx+20h], xmm0
0x1801533c2  movups  xmm1, xmmword ptr [rax+30h]
0x1801533c6  movups  xmmword ptr [rcx+30h], xmm1
0x1801533ca  movups  xmm0, xmmword ptr [rax+40h]
0x1801533ce  movups  xmmword ptr [rcx+40h], xmm0
0x1801533d2  movups  xmm1, xmmword ptr [rax+50h]
0x1801533d6  movups  xmmword ptr [rcx+50h], xmm1
0x1801533da  movups  xmm0, xmmword ptr [rax+60h]
0x1801533de  movups  xmmword ptr [rcx+60h], xmm0
0x1801533e2  add     rcx, r8
0x1801533e5  movups  xmm1, xmmword ptr [rax+70h]
0x1801533e9  movups  xmmword ptr [rcx-10h], xmm1
0x1801533ed  add     rax, r8
0x1801533f0  sub     rdx, 1
0x1801533f4  jnz     short loc_1801533AC
0x1801533f6  mov     rax, [rax]
0x1801533f9  mov     [rcx], rax
0x1801533fc  mov     [rsp+19D0h+var_1998], rdi
0x180153401  mov     rcx, [r15]
0x180153404  mov     rax, [rcx]
0x180153407  mov     [rsp+19D0h+var_19B0], rdi
0x18015340c  xor     r9d, r9d
0x18015340f  lea     r8, [rsp+19D0h+var_1998]
0x180153414  lea     rdx, [rbp+18D0h+var_1770]
0x18015341b  mov     rax, [rax+60h]
0x18015341f  call    cs:__guard_dispatch_icall_fptr
0x180153425  test    eax, eax
0x180153427  js      loc_1801535F0
0x18015342d  mov     [rsp+19D0h+var_1980], 824h
0x180153435  mov     rcx, [rsp+19D0h+var_1998]
0x18015343a  mov     rax, [rcx]
0x18015343d  lea     r8, [rsp+19D0h+var_1980]
0x180153442  lea     rdx, [rbp+18D0h+var_10A0]
0x180153449  mov     rax, [rax+38h]
0x18015344d  call    cs:__guard_dispatch_icall_fptr
0x180153453  test    eax, eax
0x180153455  js      loc_1801535F0
0x18015345b  mov     rcx, [r13+20h]
0x18015345f  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x180153464  test    rax, rax
0x180153467  jle     loc_1801535F0
0x18015346d  mov     rcx, [r13+28h]
0x180153471  call    ??$PinData@V?$TRangeRestricted@_JUCoordRange@Art@@@Ofc@@@Art@@YA_J_J@Z; Art::PinData<Ofc::TRangeRestricted<__int64,Art::CoordRange>>(__int64)
0x180153476  test    rax, rax
0x180153479  jle     loc_1801535F0
0x18015347f  lea     rax, word_180A77374
0x180153486  mov     qword ptr [rsp+19D0h+var_1988], rax
0x18015348b  xor     r8d, r8d; struct Ofc::CStr *
0x18015348e  lea     rdx, [rsp+19D0h+var_1988]; wchar_t *
0x180153493  mov     rcx, [r13+8]; this
0x180153497  call    ?FGetLocalizedThemeName@Art@@YA_NPEB_WAEAVCStr@Ofc@@PEAH@Z; Art::FGetLocalizedThemeName(wchar_t const *,Ofc::CStr &,int *)
0x18015349c  test    al, al
0x18015349e  jz      loc_180153854
0x1801534a4  mov     ecx, 50h ; 'P'; this
0x1801534a9  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801534ae  mov     r15, rax
0x1801534b1  test    rax, rax
0x1801534b4  jnz     loc_180153644
0x1801534ba  mov     r15, rdi
0x1801534bd  mov     [rbp+18D0h+var_1950], r15
0x1801534c1  test    r15, r15
0x1801534c4  jnz     loc_180153867
0x1801534ca  lea     eax, [r15+8]
0x1801534ce  test    r15, r15
0x1801534d1  jz      short loc_1801534D6
0x1801534d3  lock inc dword ptr [rax]
0x1801534d6  mov     rcx, r12; this
0x1801534d9  call    ?NewTail@CListImpl@Ofc@@IEAAPEAPEAXXZ; Ofc::CListImpl::NewTail(void)
0x1801534de  mov     [rax], r15
0x1801534e1  mov     [rsp+19D0h+var_1990], edi
0x1801534e5  mov     rax, [r15+28h]
0x1801534e9  lea     r13, [r15+40h]
0x1801534ed  mov     [rsp+19D0h+var_19B0], rax
0x1801534f2  lea     r9, [rsp+19D0h+var_1990]
0x1801534f7  mov     r8, r13
0x1801534fa  mov     edx, 14h
0x1801534ff  mov     rcx, rsi
0x180153502  call    ?GetPowerPointThumbnailFromPackage@Art@@YAJAEAUIPackage@OpenXml@Mso@@W4MetroPartType@@AEAV?$TCntPtr@UIImage@GEL@@@Ofc@@PEAKPEB_W@Z; Art::GetPowerPointThumbnailFromPackage(Mso::OpenXml::IPackage &,MetroPartType,Ofc::TCntPtr<GEL::IImage> &,ulong *,wchar_t const *)
0x180153507  test    eax, eax
0x180153509  js      loc_1801536B5
0x18015350f  cmp     [rsp+19D0h+var_199F], dil
0x180153514  jnz     loc_1801537BD
0x18015351a  movss   xmm0, cs:__real@42c00000
0x180153522  mov     [rsp+19D0h+var_1978], 42C00000h
0x18015352a  movss   [rsp+19D0h+var_1974], xmm0
0x180153530  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x180153535  test    al, al
0x180153537  jz      loc_180153620
0x18015353d  xor     edx, edx
0x18015353f  lea     rcx, [rsp+19D0h+var_1978]
0x180153544  call    ?GetScaleFactor@Art@@YAMAEBV?$TConvertibleDPI2@M@Gfx@@_N@Z; Art::GetScaleFactor(Gfx::TConvertibleDPI2<float> const &,bool)
0x180153549  mulss   xmm0, cs:__real@42aa0000
0x180153551  cvtss2sd xmm0, xmm0; X
0x180153555  call    cs:__imp_round
0x18015355b  cvttsd2si ecx, xmm0
0x18015355f  call    cs:__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z; NetUI::ScaleProportionalToSystemFontPx(int)
0x180153565  mov     esi, eax
0x180153567  call    ?FDynamicDpiEnabled@Art@@YA_NXZ; Art::FDynamicDpiEnabled(void)
0x18015356c  test    al, al
0x18015356e  jz      loc_180153632
0x180153574  xor     edx, edx
0x180153576  lea     rcx, [rsp+19D0h+var_1978]
0x18015357b  call    ?GetScaleFactor@Art@@YAMAEBV?$TConvertibleDPI2@M@Gfx@@_N@Z; Art::GetScaleFactor(Gfx::TConvertibleDPI2<float> const &,bool)
0x180153580  mulss   xmm0, cs:__real@42400000
0x180153588  cvtss2sd xmm0, xmm0; X
0x18015358c  call    cs:__imp_round
0x180153592  cvttsd2si ecx, xmm0
0x180153596  call    cs:__imp_?ScaleProportionalToSystemFontPx@NetUI@@YAHH@Z; NetUI::ScaleProportionalToSystemFontPx(int)
0x18015359c  mov     edi, eax
0x18015359e  mov     rcx, [r13+0]
0x1801535a2  mov     rax, [rcx]
0x1801535a5  mov     rax, [rax+28h]
0x1801535a9  call    cs:__guard_dispatch_icall_fptr
0x1801535af  cmp     eax, esi
0x1801535b1  jg      loc_180153873
0x1801535b7  mov     rcx, [r13+0]
0x1801535bb  mov     rax, [rcx]
0x1801535be  mov     rax, [rax+30h]
0x1801535c2  call    cs:__guard_dispatch_icall_fptr
0x1801535c8  cmp     eax, edi
0x1801535ca  jg      loc_180153873
0x1801535d0  lea     rcx, [r15+8]
0x1801535d4  call    ?Release@?$TRefCountNoVirt@V?$TRefCount@VCThreadingPolicyMultiThread@Ofc@@@Ofc@@VCThreadingPolicyMultiThread@2@@Ofc@@QEBAXXZ; Ofc::TRefCountNoVirt<Ofc::TRefCount<Ofc::CThreadingPolicyMultiThread>,Ofc::CThreadingPolicyMultiThread>::Release(void)
0x1801535d9  mov     rcx, qword ptr [rsp+19D0h+var_1988]
0x1801535de  add     rcx, 0FFFFFFFFFFFFFFF4h; this
0x1801535e2  call    ?Release@XString@Ofc@@QEAAXXZ; Ofc::XString::Release(void)
0x1801535e7  mov     rsi, [rsp+19D0h+var_1958]
0x1801535ec  mov     r15, [rbp+18D0h+var_1940]
0x1801535f0  mov     rcx, [rsp+19D0h+var_1998]
0x1801535f5  xor     r13d, r13d
0x1801535f8  test    rcx, rcx
0x1801535fb  jz      short loc_18015360B
  ... truncated ...
```
