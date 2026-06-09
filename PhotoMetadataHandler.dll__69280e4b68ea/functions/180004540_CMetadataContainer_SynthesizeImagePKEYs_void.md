# CMetadataContainer::_SynthesizeImagePKEYs(void)

- ea: `0x180004540`
- end: `0x180004e0d`
- name: `?_SynthesizeImagePKEYs@CMetadataContainer@@AEAAXXZ`
- size: `2253`
- prototype: `void __fastcall(CMetadataContainer *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180002f30`

## callees

- `0x180004540`
- `0x180004e20`
- `0x1800089f0`
- `0x180008ea0`
- `0x18000e8f0`
- `0x1800132dc`
- `0x180016a40`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800047bc`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004838`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004968`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004a1e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004b0f`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800047bc`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004838`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004968`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004a1e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180004b0f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004607`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004646`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004680`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004760`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004771`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800047dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800047ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000488c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000489d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004905`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004916`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800049c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800049d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a78`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004ac1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004b8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004d91`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004ddc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004607`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004646`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004680`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004760`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004771`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800047dc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800047ed`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000488c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000489d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004905`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004916`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800049c2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800049d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004a78`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004ac1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004b8f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004d91`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180004ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800048ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800048ae`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x180004daa`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x180004daa`

## pseudocode

```c
void __fastcall CMetadataContainer::_SynthesizeImagePKEYs(CMetadataContainer *this)
{
  __int64 v1; // r9
  __int64 v3; // rcx
  const WCHAR *v4; // rsi
  int v5; // eax
  int v6; // edi
  __int64 v7; // rdx
  struct tagPROPVARIANT *v8; // r8
  __int64 v9; // rdx
  _OWORD *v10; // rax
  __int64 v11; // rdx
  double v12; // xmm0_8
  __int64 v13; // rdx
  double v14; // xmm0_8
  const unsigned __int16 *v15; // rdi
  __int64 v16; // rdx
  unsigned int v17; // eax
  const wchar_t *v18; // rax
  bool v19[4]; // [rsp+20h] [rbp-E0h]
  PROPVARIANT pvar; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  PROPVARIANT pvarDest; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v24[8]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v25; // [rsp+80h] [rbp-80h]
  __int128 v26; // [rsp+90h] [rbp-70h]
  __int128 v27; // [rsp+A0h] [rbp-60h]
  __int128 v28; // [rsp+B0h] [rbp-50h]
  __int128 v29; // [rsp+C0h] [rbp-40h]
  __int128 v30; // [rsp+D0h] [rbp-30h]
  __int128 v31; // [rsp+E0h] [rbp-20h]

  v1 = *((unsigned int *)this + 8);
  *(_DWORD *)v19 = *((_DWORD *)this + 9);
  memset(&pvar, 0, sizeof(pvar));
  *(_OWORD *)v24 = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  if ( (int)StringCchPrintfW(v24, 0x40u, &qword_180091AF8, v1, *(_DWORD *)v19) >= 0 )
  {
    pvar.vt = 31;
    if ( (int)PIXStrDup(v24, &pvar.bstrVal) >= 0 )
      CPhotoPropertyItemList::_InternalUpdateOrAddItem(
        (CMetadataContainer *)((char *)this + 96),
        &PKEY_Image_Dimensions,
        &pvar,
        0,
        0);
  }
  PropVariantClear(&pvar);
  pvar.lVal = *((_DWORD *)this + 8);
  pvar.vt = 19;
  CPhotoPropertyItemList::_InternalUpdateOrAddItem(
    (CMetadataContainer *)((char *)this + 96),
    &PKEY_Image_HorizontalSize,
    &pvar,
    0,
    0);
  PropVariantClear(&pvar);
  pvar.lVal = *((_DWORD *)this + 9);
  pvar.vt = 19;
  CPhotoPropertyItemList::_InternalUpdateOrAddItem(
    (CMetadataContainer *)((char *)this + 96),
    &PKEY_Image_VerticalSize,
    &pvar,
    0,
    0);
  PropVariantClear(&pvar);
  v3 = *((_QWORD *)this + 2);
  v4 = 0;
  pvar.vt = 19;
  v22 = 0;
  v21 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, char *, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, (char *)this + 56, &v22);
  v6 = v5;
  if ( v5 < 0
    || (v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v22)(v22, &IID_IWICPixelFormatInfo, &v21),
        v6 = v5,
        v5 < 0)
    || (v5 = (*(__int64 (__fastcall **)(__int64, ULONG *))(*(_QWORD *)v21 + 104LL))(v21, &pvar.ulVal), v6 = v5, v5 < 0) )
  {
    if ( g_doStackCaptures )
      DoStackCapture(v5);
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v6 >= 0 )
    CPhotoPropertyItemList::_InternalUpdateOrAddItem(
      (CMetadataContainer *)((char *)this + 96),
      &PKEY_Image_BitDepth,
      &pvar,
      0,
      0);
  PropVariantClear(&pvar);
  PropVariantClear(&pvar);
  v7 = *((_QWORD *)this + 12);
  if ( v7 )
  {
    do
    {
      if ( *(_DWORD *)(v7 + 16) == 9
        && *(_QWORD *)v7 == *(_QWORD *)&PKEY_Rating.fmtid.Data1
        && *(_QWORD *)(v7 + 8) == *(_QWORD *)PKEY_Rating.fmtid.Data4 )
      {
        break;
      }
      v7 = *(_QWORD *)(v7 + 56);
    }
    while ( v7 );
    if ( v7 && PropVariantCopy(&pvar, (const PROPVARIANT *)(v7 + 24)) < 0 )
      goto LABEL_29;
  }
  if ( !pvar.vt )
  {
LABEL_29:
    PropVariantClear(&pvar);
    PropVariantClear(&pvar);
    v9 = *((_QWORD *)this + 12);
    if ( !v9 )
      goto LABEL_30;
    do
    {
      if ( *(_DWORD *)(v9 + 16) == 100
        && *(_QWORD *)v9 == *(_QWORD *)&PKEY_SimpleRating.fmtid.Data1
        && *(_QWORD *)(v9 + 8) == *(_QWORD *)PKEY_SimpleRating.fmtid.Data4 )
      {
        break;
      }
      v9 = *(_QWORD *)(v9 + 56);
    }
    while ( v9 );
    if ( !v9 || PropVariantCopy(&pvar, (const PROPVARIANT *)(v9 + 24)) >= 0 )
    {
LABEL_30:
      memset(&pvarDest, 0, sizeof(pvarDest));
      if ( (int)CodecUtil::ConvertSimpleRatingToRating((CodecUtil *)&pvar, &pvarDest, v8) >= 0 )
        CPhotoPropertyItemList::_InternalUpdateOrAddItem(
          (CMetadataContainer *)((char *)this + 96),
          &PKEY_Rating,
          &pvarDest,
          0,
          0);
      PropVariantClear(&pvarDest);
    }
  }
  PropVariantClear(&pvar);
  v10 = CoTaskMemAlloc(0x10u);
  pvar.hVal.QuadPart = (LONGLONG)v10;
  if ( v10 )
  {
    *v10 = 0;
    *(GUID *)pvar.hVal.QuadPart = CLSID_MediaTypePhoto;
    pvar.vt = 72;
    CPhotoPropertyItemList::_InternalUpdateOrAddItem(
      (CMetadataContainer *)((char *)this + 96),
      &PKEY_Media_ClassPrimaryID,
      &pvar,
      0,
      0);
  }
  PropVariantClear(&pvar);
  PropVariantClear(&pvar);
  v11 = *((_QWORD *)this + 12);
  if ( v11 )
  {
    do
    {
      if ( *(_DWORD *)(v11 + 16) == 5
        && *(_QWORD *)v11 == *(_QWORD *)&PKEY_Image_HorizontalResolution.fmtid.Data1
        && *(_QWORD *)(v11 + 8) == *(_QWORD *)PKEY_Image_HorizontalResolution.fmtid.Data4 )
      {
        break;
      }
      v11 = *(_QWORD *)(v11 + 56);
    }
    while ( v11 );
    if ( v11 && PropVariantCopy(&pvar, (const PROPVARIANT *)(v11 + 24)) < 0 )
      goto LABEL_119;
  }
  if ( !pvar.vt )
  {
LABEL_119:
    v12 = *((double *)this + 5);
    if ( v12 > 0.0 )
    {
      pvar.vt = 5;
      pvar.dblVal = v12;
      CPhotoPropertyItemList::_InternalUpdateOrAddItem(
        (CMetadataContainer *)((char *)this + 96),
        &PKEY_Image_HorizontalResolution,
        &pvar,
        0,
        0);
    }
  }
  PropVariantClear(&pvar);
  PropVariantClear(&pvar);
  v13 = *((_QWORD *)this + 12);
  if ( v13 )
  {
    do
    {
      if ( *(_DWORD *)(v13 + 16) == 6
        && *(_QWORD *)v13 == *(_QWORD *)&PKEY_Image_VerticalResolution.fmtid.Data1
        && *(_QWORD *)(v13 + 8) == *(_QWORD *)PKEY_Image_VerticalResolution.fmtid.Data4 )
      {
        break;
      }
      v13 = *(_QWORD *)(v13 + 56);
    }
    while ( v13 );
    if ( v13 && PropVariantCopy(&pvar, (const PROPVARIANT *)(v13 + 24)) < 0 )
      goto LABEL_120;
  }
  if ( !pvar.vt )
  {
LABEL_120:
    v14 = *((double *)this + 6);
    if ( v14 > 0.0 )
    {
      pvar.vt = 5;
      pvar.dblVal = v14;
      CPhotoPropertyItemList::_InternalUpdateOrAddItem(
        (CMetadataContainer *)((char *)this + 96),
        &PKEY_Image_VerticalResolution,
        &pvar,
        0,
        0);
    }
  }
  PropVariantClear(&pvar);
  if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatJpeg.Data1
    && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatJpeg.Data4 )
  {
    v15 = L"image/jpeg";
    memset(&pvarDest, 0, sizeof(pvarDest));
    PropVariantClear(&pvarDest);
    v16 = *((_QWORD *)this + 12);
    if ( v16 )
    {
      do
      {
        if ( *(_DWORD *)(v16 + 16) == 40961
          && *(_QWORD *)v16 == *(_QWORD *)&PKEY_Image_ColorSpace.fmtid.Data1
          && *(_QWORD *)(v16 + 8) == *(_QWORD *)PKEY_Image_ColorSpace.fmtid.Data4 )
        {
          break;
        }
        v16 = *(_QWORD *)(v16 + 56);
      }
      while ( v16 );
      if ( v16 && PropVariantCopy(&pvarDest, (const PROPVARIANT *)(v16 + 24)) < 0 )
        goto LABEL_76;
    }
    if ( pvarDest.vt != 18 || ((pvarDest.iVal + 1) & 0xFFFD) != 0 )
      goto LABEL_76;
    v17 = *((_DWORD *)this + 8);
    if ( v17 > 0x280 )
    {
      if ( v17 > 0x400 )
      {
        if ( v17 > 0x1000 )
          goto LABEL_76;
        goto LABEL_73;
      }
    }
    else if ( *((_DWORD *)this + 9) <= 0x1E0u )
    {
      v4 = L"JPEG_SM";
LABEL_76:
      PropVariantClear(&pvarDest);
      goto LABEL_111;
    }
    if ( *((_DWORD *)this + 9) <= 0x300u )
    {
      v4 = L"JPEG_MED";
      goto LABEL_76;
    }
LABEL_73:
    v18 = L"JPEG_LRG";
    if ( *((_DWORD *)this + 9) > 0x1000u )
      v18 = 0;
    v4 = v18;
    goto LABEL_76;
  }
  if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatPng.Data1
    && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatPng.Data4 )
  {
    v15 = L"image/png";
    if ( *((_DWORD *)this + 8) <= 0x1000u && *((_DWORD *)this + 9) <= 0x1000u )
      v4 = L"PNG_LRG";
  }
  else if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatGif.Data1
         && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatGif.Data4 )
  {
    v15 = L"image/gif";
    if ( *((_DWORD *)this + 8) <= 0x640u && *((_DWORD *)this + 9) <= 0x4B0u )
      v4 = L"GIF_LRG";
  }
  else if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatTiff.Data1
         && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatTiff.Data4 )
  {
    v15 = L"image/tiff";
  }
  else if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatAdng.Data1
         && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatAdng.Data4 )
  {
    v15 = L"image/DNG";
  }
  else if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatBmp.Data1
         && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatBmp.Data4 )
  {
    v15 = L"image/bmp";
  }
  else if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatIco.Data1
         && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatIco.Data4 )
  {
    v15 = L"image/x-icon";
  }
  else if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatWmp.Data1
         && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatWmp.Data4 )
  {
    v15 = L"image/vnd.ms-photo";
  }
  else if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatHeif.Data1
         && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatHeif.Data4 )
  {
    v15 = L"image/heic";
  }
  else if ( *((_QWORD *)this + 10) == *(_QWORD *)&GUID_ContainerFormatWebp.Data1
         && *((_QWORD *)this + 11) == *(_QWORD *)GUID_ContainerFormatWebp.Data4 )
  {
    v15 = L"image/webp";
  }
  else
  {
    if ( *((_QWORD *)this + 10) != *(_QWORD *)&GUID_ContainerFormatJpegXL.Data1
      || *((_QWORD *)this + 11) != *(_QWORD *)GUID_ContainerFormatJpegXL.Data4 )
    {
      return;
    }
    v15 = L"image/jxl";
  }
LABEL_111:
  pvar.vt = 31;
  if ( (int)PIXStrDup(v15, &pvar.bstrVal) >= 0 )
    CPhotoPropertyItemList::_InternalUpdateOrAddItem(
      (CMetadataContainer *)((char *)this + 96),
      &PKEY_MIMEType,
      &pvar,
      0,
      0);
  PropVariantClear(&pvar);
  if ( v4 )
  {
    if ( InitPropVariantFromStringAsVector(v4, &pvar) >= 0 )
      CPhotoPropertyItemList::_InternalUpdateOrAddItem(
        (CMetadataContainer *)((char *)this + 96),
        &PKEY_Media_DlnaProfileID,
        &pvar,
        0,
        0);
    PropVariantClear(&pvar);
  }
}

```

## disassembly

```asm
0x180004540  push    rbp
0x180004542  push    rbx
0x180004543  push    rsi
0x180004544  push    rdi
0x180004545  push    r14
0x180004547  push    r15
0x180004549  lea     rbp, [rsp-18h]
0x18000454e  sub     rsp, 118h
0x180004555  movaps  [rsp+140h+var_40], xmm6
0x18000455d  mov     rax, cs:__security_cookie
0x180004564  xor     rax, rsp
0x180004567  mov     [rbp+40h+var_50], rax
0x18000456b  mov     r9d, [rcx+20h]
0x18000456f  lea     r8, qword_180091AF8; unsigned __int16 *
0x180004576  xorps   xmm1, xmm1
0x180004579  xor     eax, eax
0x18000457b  mov     qword ptr [rsp+140h+pvar+10h], rax
0x180004580  mov     rbx, rcx
0x180004583  mov     eax, [rcx+24h]
0x180004586  xorps   xmm0, xmm0
0x180004589  lea     rcx, [rsp+140h+var_D0]; unsigned __int16 *
0x18000458e  mov     dword ptr [rsp+140h+var_120], eax
0x180004592  mov     edx, 40h ; '@'; unsigned __int64
0x180004597  movups  xmmword ptr [rsp+140h+pvar], xmm0
0x18000459c  movups  xmmword ptr [rsp+140h+var_D0], xmm1
0x1800045a1  movups  [rbp+40h+var_C0], xmm1
0x1800045a5  movups  [rbp+40h+var_B0], xmm1
0x1800045a9  movups  [rbp+40h+var_A0], xmm1
0x1800045ad  movups  [rbp+40h+var_90], xmm1
0x1800045b1  movups  [rbp+40h+var_80], xmm1
0x1800045b5  movups  [rbp+40h+var_70], xmm1
0x1800045b9  movups  [rbp+40h+var_60], xmm1
0x1800045bd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800045c2  mov     r15d, 1Fh
0x1800045c8  test    eax, eax
0x1800045ca  js      short loc_180004602
0x1800045cc  lea     rdx, [rsp+140h+pvar+8]; unsigned __int16 **
0x1800045d1  mov     word ptr [rsp+140h+pvar], r15w
0x1800045d7  lea     rcx, [rsp+140h+var_D0]; unsigned __int16 *
0x1800045dc  call    ?PIXStrDup@@YAJPEBGPEAPEAG@Z; PIXStrDup(ushort const *,ushort * *)
0x1800045e1  test    eax, eax
0x1800045e3  js      short loc_180004602
0x1800045e5  lea     rcx, [rbx+60h]; this
0x1800045e9  mov     [rsp+140h+var_120], 0; bool
0x1800045ee  xor     r9d, r9d; bool
0x1800045f1  lea     r8, [rsp+140h+pvar]; struct tagPROPVARIANT *
0x1800045f6  lea     rdx, PKEY_Image_Dimensions; struct _tagpropertykey *
0x1800045fd  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x180004602  lea     rcx, [rsp+140h+pvar]; pvar
0x180004607  call    cs:__imp_PropVariantClear
0x18000460e  nop     dword ptr [rax+rax+00h]
0x180004613  mov     eax, [rbx+20h]
0x180004616  lea     r8, [rsp+140h+pvar]; struct tagPROPVARIANT *
0x18000461b  mov     edi, 13h
0x180004620  mov     dword ptr [rsp+140h+pvar+8], eax
0x180004624  xor     r9d, r9d; bool
0x180004627  mov     word ptr [rsp+140h+pvar], di
0x18000462c  lea     rdx, PKEY_Image_HorizontalSize; struct _tagpropertykey *
0x180004633  mov     [rsp+140h+var_120], 0; bool
0x180004638  lea     rcx, [rbx+60h]; this
0x18000463c  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x180004641  lea     rcx, [rsp+140h+pvar]; pvar
0x180004646  call    cs:__imp_PropVariantClear
0x18000464d  nop     dword ptr [rax+rax+00h]
0x180004652  mov     eax, [rbx+24h]
0x180004655  lea     r8, [rsp+140h+pvar]; struct tagPROPVARIANT *
0x18000465a  xor     r9d, r9d; bool
0x18000465d  mov     dword ptr [rsp+140h+pvar+8], eax
0x180004661  lea     rdx, PKEY_Image_VerticalSize; struct _tagpropertykey *
0x180004668  mov     word ptr [rsp+140h+pvar], di
0x18000466d  lea     rcx, [rbx+60h]; this
0x180004671  mov     [rsp+140h+var_120], 0; bool
0x180004676  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18000467b  lea     rcx, [rsp+140h+pvar]; pvar
0x180004680  call    cs:__imp_PropVariantClear
0x180004687  nop     dword ptr [rax+rax+00h]
0x18000468c  mov     rcx, [rbx+10h]
0x180004690  lea     rdx, [rbx+38h]
0x180004694  xor     esi, esi
0x180004696  mov     word ptr [rsp+140h+pvar], di
0x18000469b  mov     [rsp+140h+var_F0], rsi
0x1800046a0  lea     r8, [rsp+140h+var_F0]
0x1800046a5  mov     [rsp+140h+var_F8], rsi
0x1800046aa  mov     rax, [rcx]
0x1800046ad  mov     rax, [rax+30h]
0x1800046b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b6  mov     edi, eax
0x1800046b8  test    eax, eax
0x1800046ba  js      short loc_1800046FA
0x1800046bc  mov     rcx, [rsp+140h+var_F0]
0x1800046c1  lea     r8, [rsp+140h+var_F8]
0x1800046c6  lea     rdx, IID_IWICPixelFormatInfo
0x1800046cd  mov     rax, [rcx]
0x1800046d0  mov     rax, [rax]
0x1800046d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d8  mov     edi, eax
0x1800046da  test    eax, eax
0x1800046dc  js      short loc_1800046FA
0x1800046de  mov     rcx, [rsp+140h+var_F8]
0x1800046e3  lea     rdx, [rsp+140h+pvar+8]
0x1800046e8  mov     rax, [rcx]
0x1800046eb  mov     rax, [rax+68h]
0x1800046ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046f4  mov     edi, eax
0x1800046f6  test    eax, eax
0x1800046f8  jns     short loc_180004709
0x1800046fa  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180004700  jz      short loc_180004709
0x180004702  mov     ecx, eax; int
0x180004704  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180004709  mov     rcx, [rsp+140h+var_F8]
0x18000470e  test    rcx, rcx
0x180004711  jz      short loc_180004724
0x180004713  mov     rax, [rcx]
0x180004716  mov     rax, [rax+10h]
0x18000471a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000471f  mov     [rsp+140h+var_F8], rsi
0x180004724  mov     rcx, [rsp+140h+var_F0]
0x180004729  test    rcx, rcx
0x18000472c  jz      short loc_18000473A
0x18000472e  mov     rax, [rcx]
0x180004731  mov     rax, [rax+10h]
0x180004735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473a  test    edi, edi
0x18000473c  js      short loc_18000475B
0x18000473e  xor     r9d, r9d; bool
0x180004741  mov     [rsp+140h+var_120], sil; bool
0x180004746  lea     r8, [rsp+140h+pvar]; struct tagPROPVARIANT *
0x18000474b  lea     rdx, PKEY_Image_BitDepth; struct _tagpropertykey *
0x180004752  lea     rcx, [rbx+60h]; this
0x180004756  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x18000475b  lea     rcx, [rsp+140h+pvar]; pvar
0x180004760  call    cs:__imp_PropVariantClear
0x180004767  nop     dword ptr [rax+rax+00h]
0x18000476c  lea     rcx, [rsp+140h+pvar]; pvar
0x180004771  call    cs:__imp_PropVariantClear
0x180004778  nop     dword ptr [rax+rax+00h]
0x18000477d  mov     rdx, [rbx+60h]
0x180004781  test    rdx, rdx
0x180004784  jz      short loc_1800047CC
0x180004786  mov     rax, qword ptr cs:PKEY_Rating.fmtid.Data4
0x18000478d  mov     rcx, qword ptr cs:PKEY_Rating.fmtid.Data1
0x180004794  cmp     dword ptr [rdx+10h], 9
0x180004798  jnz     short loc_1800047A5
0x18000479a  cmp     [rdx], rcx
0x18000479d  jnz     short loc_1800047A5
0x18000479f  cmp     [rdx+8], rax
0x1800047a3  jz      short loc_1800047AE
0x1800047a5  mov     rdx, [rdx+38h]
0x1800047a9  test    rdx, rdx
0x1800047ac  jnz     short loc_180004794
0x1800047ae  test    rdx, rdx
0x1800047b1  jz      short loc_1800047CC
0x1800047b3  add     rdx, 18h; pvarSrc
0x1800047b7  lea     rcx, [rsp+140h+pvar]; pvarDest
0x1800047bc  call    cs:__imp_PropVariantCopy
0x1800047c3  nop     dword ptr [rax+rax+00h]
0x1800047c8  test    eax, eax
0x1800047ca  js      short loc_1800047D7
0x1800047cc  cmp     si, word ptr [rsp+140h+pvar]
0x1800047d1  jnz     loc_180004898
0x1800047d7  lea     rcx, [rsp+140h+pvar]; pvar
0x1800047dc  call    cs:__imp_PropVariantClear
0x1800047e3  nop     dword ptr [rax+rax+00h]
0x1800047e8  lea     rcx, [rsp+140h+pvar]; pvar
0x1800047ed  call    cs:__imp_PropVariantClear
0x1800047f4  nop     dword ptr [rax+rax+00h]
0x1800047f9  mov     rdx, [rbx+60h]
0x1800047fd  test    rdx, rdx
0x180004800  jz      short loc_180004848
0x180004802  mov     rax, qword ptr cs:PKEY_SimpleRating.fmtid.Data4
0x180004809  mov     rcx, qword ptr cs:PKEY_SimpleRating.fmtid.Data1
0x180004810  cmp     dword ptr [rdx+10h], 64h ; 'd'
0x180004814  jnz     short loc_180004821
0x180004816  cmp     [rdx], rcx
0x180004819  jnz     short loc_180004821
0x18000481b  cmp     [rdx+8], rax
0x18000481f  jz      short loc_18000482A
0x180004821  mov     rdx, [rdx+38h]
0x180004825  test    rdx, rdx
0x180004828  jnz     short loc_180004810
0x18000482a  test    rdx, rdx
0x18000482d  jz      short loc_180004848
0x18000482f  add     rdx, 18h; pvarSrc
0x180004833  lea     rcx, [rsp+140h+pvar]; pvarDest
0x180004838  call    cs:__imp_PropVariantCopy
0x18000483f  nop     dword ptr [rax+rax+00h]
0x180004844  test    eax, eax
0x180004846  js      short loc_180004898
0x180004848  xorps   xmm0, xmm0
0x18000484b  lea     rdx, [rsp+140h+pvarDest]; struct tagPROPVARIANT *
0x180004850  xor     eax, eax
0x180004852  lea     rcx, [rsp+140h+pvar]; this
0x180004857  movups  xmmword ptr [rsp+140h+pvarDest], xmm0
0x18000485c  mov     qword ptr [rsp+140h+pvarDest+10h], rax
0x180004861  call    ?ConvertSimpleRatingToRating@CodecUtil@@YAJPEBUtagPROPVARIANT@@PEAU2@@Z; CodecUtil::ConvertSimpleRatingToRating(tagPROPVARIANT const *,tagPROPVARIANT *)
0x180004866  test    eax, eax
0x180004868  js      short loc_180004887
0x18000486a  xor     r9d, r9d; bool
0x18000486d  mov     [rsp+140h+var_120], sil; bool
0x180004872  lea     r8, [rsp+140h+pvarDest]; struct tagPROPVARIANT *
0x180004877  lea     rdx, PKEY_Rating; struct _tagpropertykey *
0x18000487e  lea     rcx, [rbx+60h]; this
0x180004882  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x180004887  lea     rcx, [rsp+140h+pvarDest]; pvar
0x18000488c  call    cs:__imp_PropVariantClear
0x180004893  nop     dword ptr [rax+rax+00h]
0x180004898  lea     rcx, [rsp+140h+pvar]; pvar
0x18000489d  call    cs:__imp_PropVariantClear
0x1800048a4  nop     dword ptr [rax+rax+00h]
0x1800048a9  mov     ecx, 10h; cb
0x1800048ae  call    cs:__imp_CoTaskMemAlloc
0x1800048b5  nop     dword ptr [rax+rax+00h]
0x1800048ba  mov     qword ptr [rsp+140h+pvar+8], rax
0x1800048bf  test    rax, rax
0x1800048c2  jz      short loc_180004900
0x1800048c4  xorps   xmm0, xmm0
0x1800048c7  mov     [rsp+140h+var_120], sil; bool
0x1800048cc  movups  xmmword ptr [rax], xmm0
0x1800048cf  mov     rax, qword ptr [rsp+140h+pvar+8]
0x1800048d4  lea     r8, [rsp+140h+pvar]; struct tagPROPVARIANT *
0x1800048d9  movups  xmm1, xmmword ptr cs:?CLSID_MediaTypePhoto@@3U_GUID@@B.Data1; _GUID const CLSID_MediaTypePhoto ...
0x1800048e0  xor     r9d, r9d; bool
0x1800048e3  lea     rdx, PKEY_Media_ClassPrimaryID; struct _tagpropertykey *
0x1800048ea  lea     rcx, [rbx+60h]; this
0x1800048ee  movups  xmmword ptr [rax], xmm1
0x1800048f1  mov     eax, 48h ; 'H'
0x1800048f6  mov     word ptr [rsp+140h+pvar], ax
0x1800048fb  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x180004900  lea     rcx, [rsp+140h+pvar]; pvar
0x180004905  call    cs:__imp_PropVariantClear
0x18000490c  nop     dword ptr [rax+rax+00h]
0x180004911  lea     rcx, [rsp+140h+pvar]; pvar
0x180004916  call    cs:__imp_PropVariantClear
0x18000491d  nop     dword ptr [rax+rax+00h]
0x180004922  mov     rdx, [rbx+60h]
0x180004926  mov     edi, 5
0x18000492b  xorps   xmm6, xmm6
0x18000492e  test    rdx, rdx
0x180004931  jz      short loc_180004978
0x180004933  mov     rax, qword ptr cs:PKEY_Image_HorizontalResolution.fmtid.Data4
0x18000493a  mov     rcx, qword ptr cs:PKEY_Image_HorizontalResolution.fmtid.Data1
0x180004941  cmp     [rdx+10h], edi
0x180004944  jnz     short loc_180004951
0x180004946  cmp     [rdx], rcx
0x180004949  jnz     short loc_180004951
0x18000494b  cmp     [rdx+8], rax
0x18000494f  jz      short loc_18000495A
0x180004951  mov     rdx, [rdx+38h]
0x180004955  test    rdx, rdx
0x180004958  jnz     short loc_180004941
0x18000495a  test    rdx, rdx
0x18000495d  jz      short loc_180004978
0x18000495f  add     rdx, 18h; pvarSrc
0x180004963  lea     rcx, [rsp+140h+pvar]; pvarDest
0x180004968  call    cs:__imp_PropVariantCopy
0x18000496f  nop     dword ptr [rax+rax+00h]
0x180004974  test    eax, eax
0x180004976  js      short loc_18000497F
0x180004978  cmp     si, word ptr [rsp+140h+pvar]
0x18000497d  jnz     short loc_1800049BD
0x18000497f  movsd   xmm0, qword ptr [rbx+28h]
0x180004984  comisd  xmm0, xmm6
0x180004988  jbe     short loc_1800049BD
0x18000498a  movq    rax, xmm0
0x18000498f  mov     word ptr [rsp+140h+pvar], di
0x180004994  mov     dword ptr [rsp+140h+pvar+8], eax
0x180004998  lea     r8, [rsp+140h+pvar]; struct tagPROPVARIANT *
0x18000499d  shr     rax, 20h
0x1800049a1  lea     rdx, PKEY_Image_HorizontalResolution; struct _tagpropertykey *
0x1800049a8  xor     r9d, r9d; bool
0x1800049ab  mov     dword ptr [rsp+140h+pvar+0Ch], eax
0x1800049af  lea     rcx, [rbx+60h]; this
0x1800049b3  mov     [rsp+140h+var_120], sil; bool
0x1800049b8  call    ?_InternalUpdateOrAddItem@CPhotoPropertyItemList@@AEAAJPEBU_tagpropertykey@@PEBUtagPROPVARIANT@@_N2@Z; CPhotoPropertyItemList::_InternalUpdateOrAddItem(_tagpropertykey const *,tagPROPVARIANT const *,bool,bool)
0x1800049bd  lea     rcx, [rsp+140h+pvar]; pvar
0x1800049c2  call    cs:__imp_PropVariantClear
0x1800049c9  nop     dword ptr [rax+rax+00h]
0x1800049ce  lea     rcx, [rsp+140h+pvar]; pvar
0x1800049d3  call    cs:__imp_PropVariantClear
0x1800049da  nop     dword ptr [rax+rax+00h]
0x1800049df  mov     rdx, [rbx+60h]
0x1800049e3  test    rdx, rdx
0x1800049e6  jz      short loc_180004A2E
0x1800049e8  mov     rax, qword ptr cs:PKEY_Image_VerticalResolution.fmtid.Data4
0x1800049ef  mov     rcx, qword ptr cs:PKEY_Image_VerticalResolution.fmtid.Data1
0x1800049f6  cmp     dword ptr [rdx+10h], 6
0x1800049fa  jnz     short loc_180004A07
0x1800049fc  cmp     [rdx], rcx
0x1800049ff  jnz     short loc_180004A07
0x180004a01  cmp     [rdx+8], rax
0x180004a05  jz      short loc_180004A10
0x180004a07  mov     rdx, [rdx+38h]
0x180004a0b  test    rdx, rdx
0x180004a0e  jnz     short loc_1800049F6
0x180004a10  test    rdx, rdx
0x180004a13  jz      short loc_180004A2E
0x180004a15  add     rdx, 18h; pvarSrc
0x180004a19  lea     rcx, [rsp+140h+pvar]; pvarDest
0x180004a1e  call    cs:__imp_PropVariantCopy
  ... truncated ...
```
