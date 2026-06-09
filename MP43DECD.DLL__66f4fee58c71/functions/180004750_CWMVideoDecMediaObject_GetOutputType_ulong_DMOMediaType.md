# CWMVideoDecMediaObject::GetOutputType(ulong,_DMOMediaType *)

- ea: `0x180004750`
- end: `0x180004e5a`
- name: `?GetOutputType@CWMVideoDecMediaObject@@MEAAJKPEAU_DMOMediaType@@@Z`
- size: `1802`
- prototype: `int(CWMVideoDecMediaObject *__hidden this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001420`
- `0x180001880`
- `0x180002144`
- `0x180002c24`
- `0x180003534`
- `0x180003874`
- `0x180003900`
- `0x180004750`
- `0x180004f4c`
- `0x180008094`

## import_xrefs

- `msdmo!MoInitMediaType` at `0x18000493e`
- `msdmo!MoInitMediaType` at `0x18000493e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180004cc2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180004ced`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180004cc2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180004ced`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180004ccb`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180004ccb`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180004cf9`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180004cf9`
- `ext-ms-win-gdi-dc-l1-2-0!GetSystemPaletteEntries` at `0x180004ce7`
- `ext-ms-win-gdi-dc-l1-2-0!GetSystemPaletteEntries` at `0x180004ce7`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::GetOutputType(
        CWMVideoDecMediaObject *this,
        unsigned int a2,
        DMO_MEDIA_TYPE *a3)
{
  bool v3; // cf
  unsigned __int64 v4; // r9
  char *v5; // rdx
  unsigned __int64 v6; // rsi
  __int64 v9; // r10
  int v10; // ecx
  int v11; // eax
  __int64 v12; // r8
  __int64 *v13; // rdi
  __int64 v14; // rdx
  BOOL v15; // r15d
  int v16; // ebp
  _QWORD *v17; // r12
  int v18; // ecx
  __int64 v19; // rax
  int v20; // edx
  __int64 v21; // rax
  unsigned int v22; // eax
  DWORD v23; // edx
  BYTE *pbFormat; // rbx
  _OWORD *v25; // rax
  __int64 v26; // rax
  __int64 v27; // rsi
  _OWORD *v28; // rax
  __int64 v29; // rax
  GUID *p_subtype; // rbx
  GUID v31; // xmm0
  BYTE *v32; // r15
  struct tagVIDEOINFOHEADER *v33; // r13
  struct tagBITMAPINFOHEADER *p_bmiHeader; // rsi
  LONG v35; // r11d
  int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // r11d
  DMO_MEDIA_TYPE *v39; // rcx
  HWND DesktopWindow; // rax
  __int64 v41; // r12
  HDC DC; // rbx
  HWND v43; // rax
  __int64 i; // rcx
  BYTE *v45; // rbx
  LONG biWidth; // eax
  LONG biHeight; // eax
  int v49; // [rsp+20h] [rbp-88h]
  struct tagVIDEOINFOHEADER *v51; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 v52; // [rsp+38h] [rbp-70h]
  tagPALETTEENTRY pPalEntries[10]; // [rsp+40h] [rbp-68h] BYREF

  v3 = *((_DWORD *)this + 14) != 0;
  v4 = a2;
  v5 = (char *)this + 64;
  v51 = 0;
  v6 = ((unsigned __int64)this + 64) & -(__int64)v3;
  v52 = v6;
  if ( !v6 || (v9 = *(_QWORD *)((((unsigned __int64)this + 64) & -(__int64)v3) + 0x50)) == 0 )
  {
    v16 = -2147220989;
    goto LABEL_103;
  }
  v10 = *((_DWORD *)this + 222);
  if ( !v10 || (v11 = 0, *((_DWORD *)this + 224)) )
    v11 = 1;
  v12 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  v13 = (__int64 *)(v6 + 44);
  v14 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  v15 = (*(_QWORD *)(v6 + 44) != *(_QWORD *)&FORMAT_MFVideoFormat.Data1
      || *(_QWORD *)(v6 + 52) != *(_QWORD *)FORMAT_MFVideoFormat.Data4)
     && (!v10 || *((_DWORD *)this + 224));
  v49 = v15;
  if ( *v13 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 )
  {
    if ( *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
    {
      if ( !v10 )
      {
        *(_DWORD *)(v9 + 28) = 7;
        v14 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
        v12 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v6 + 80) + 28LL) == 2 )
      {
        v11 = 0;
      }
      else
      {
        v11 = 1;
        v49 = 0;
        v15 = 0;
      }
    }
    if ( *v13 == v12 && *(_QWORD *)(v6 + 52) == v14 )
      goto LABEL_22;
  }
  if ( *((_DWORD *)this + 224) )
  {
LABEL_22:
    if ( !v11 )
      goto LABEL_27;
    if ( (unsigned int)v4 < 9 )
      goto LABEL_29;
    if ( (unsigned int)v4 >= 0x12 )
      return (unsigned int)-2147220986;
    v4 %= 9u;
  }
  v49 = 0;
  v15 = 0;
LABEL_27:
  if ( (unsigned int)v4 >= 9 )
    return (unsigned int)-2147220986;
LABEL_29:
  _mm_lfence();
  if ( !a3 )
    return 0;
  v17 = *(&off_180027020 + (unsigned int)v4);
  if ( *v13 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 && *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
    v18 = 176;
  else
    v18 = v15 ? 112 : 88;
  v19 = *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 - *v17;
  if ( *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 == *v17 )
    v19 = *(_QWORD *)MEDIASUBTYPE_RGB565.Data4 - v17[1];
  v20 = v19 == 0 ? 0xC : 0;
  v21 = *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 - *v17;
  if ( *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 == *v17 )
    v21 = *(_QWORD *)MEDIASUBTYPE_RGB8.Data4 - v17[1];
  if ( !v21 )
    v20 = 1024;
  v22 = v20 + v18;
  v23 = *(_DWORD *)(v6 + 72);
  if ( v22 >= v23 )
    v23 = v22;
  MoInitMediaType(a3, v23);
  pbFormat = a3->pbFormat;
  if ( !pbFormat )
    return (unsigned int)-2147467261;
  if ( *v13 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 && *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
  {
    v25 = *(_OWORD **)(v6 + 80);
    *(_OWORD *)pbFormat = *v25;
    *((_OWORD *)pbFormat + 1) = v25[1];
    *((_OWORD *)pbFormat + 2) = v25[2];
    *((_OWORD *)pbFormat + 3) = v25[3];
    *((_OWORD *)pbFormat + 4) = v25[4];
    *((_OWORD *)pbFormat + 5) = v25[5];
    *((_OWORD *)pbFormat + 6) = v25[6];
    *((_OWORD *)pbFormat + 7) = v25[7];
    *((_OWORD *)pbFormat + 8) = v25[8];
    *((_OWORD *)pbFormat + 9) = v25[9];
    *((_OWORD *)pbFormat + 10) = v25[10];
  }
  else
  {
    v26 = *v13;
    if ( v15 )
    {
      if ( v26 == *(_QWORD *)&FORMAT_VideoInfo.Data1 && *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4 )
      {
        v27 = *(_QWORD *)(v6 + 80);
        if ( v27 )
        {
          memset_0(a3->pbFormat, 0, 0x70u);
          *(_OWORD *)pbFormat = *(_OWORD *)v27;
          *((_OWORD *)pbFormat + 1) = *(_OWORD *)(v27 + 16);
          *((_DWORD *)pbFormat + 8) = *(_DWORD *)(v27 + 32);
          *((_DWORD *)pbFormat + 9) = *(_DWORD *)(v27 + 36);
          *((_QWORD *)pbFormat + 5) = *(_QWORD *)(v27 + 40);
          *(_OWORD *)(pbFormat + 72) = *(_OWORD *)(v27 + 48);
          *(_OWORD *)(pbFormat + 88) = *(_OWORD *)(v27 + 64);
          *((_QWORD *)pbFormat + 13) = *(_QWORD *)(v27 + 80);
        }
      }
      else
      {
        v28 = *(_OWORD **)(v6 + 80);
        *(_OWORD *)pbFormat = *v28;
        *((_OWORD *)pbFormat + 1) = v28[1];
        *((_OWORD *)pbFormat + 2) = v28[2];
        *((_OWORD *)pbFormat + 3) = v28[3];
        *((_OWORD *)pbFormat + 4) = v28[4];
        *((_OWORD *)pbFormat + 5) = v28[5];
        *((_OWORD *)pbFormat + 6) = v28[6];
      }
    }
    else if ( v26 == *(_QWORD *)&FORMAT_VideoInfo2.Data1 && *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_VideoInfo2.Data4 )
    {
      ConvertVIH2ToVIH(*(struct tagVIDEOINFOHEADER2 **)(v6 + 80), (struct tagVIDEOINFOHEADER *)a3->pbFormat);
    }
    else if ( *v13 == *(_QWORD *)&FORMAT_VideoInfo.Data1 && *(_QWORD *)(v6 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4 )
    {
      v29 = *(_QWORD *)(v6 + 80);
      *(_OWORD *)pbFormat = *(_OWORD *)v29;
      *((_OWORD *)pbFormat + 1) = *(_OWORD *)(v29 + 16);
      *((_OWORD *)pbFormat + 2) = *(_OWORD *)(v29 + 32);
      *((_OWORD *)pbFormat + 3) = *(_OWORD *)(v29 + 48);
      *((_OWORD *)pbFormat + 4) = *(_OWORD *)(v29 + 64);
      *((_QWORD *)pbFormat + 10) = *(_QWORD *)(v29 + 80);
    }
  }
  p_subtype = &a3->subtype;
  a3->subtype = *(GUID *)v17;
  a3->majortype = MEDIATYPE_Video;
  *(_QWORD *)&a3->bFixedSizeSamples = 1;
  a3->lSampleSize = 0;
  a3->formattype = GUID_00000000_0000_0000_0000_000000000000;
  if ( *v13 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 && v13[1] == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
  {
    v31 = FORMAT_MFVideoFormat;
  }
  else if ( v15 )
  {
    v31 = FORMAT_VideoInfo2;
  }
  else
  {
    v31 = FORMAT_VideoInfo;
  }
  a3->formattype = v31;
  if ( *v13 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 && v13[1] == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
  {
    v16 = ConvertMFVideoFormatToVIH2(&v51, (struct _MFVIDEOFORMAT *)a3->pbFormat);
    if ( v16 < 0 )
      goto LABEL_103;
    v32 = 0;
    v33 = v51;
    if ( v49 )
      goto LABEL_73;
  }
  else
  {
    v16 = 0;
    if ( v15 )
    {
      v33 = 0;
      v32 = a3->pbFormat;
LABEL_73:
      p_bmiHeader = (struct tagBITMAPINFOHEADER *)(v32 + 72);
      *((_DWORD *)v32 + 8) = 0;
      goto LABEL_76;
    }
    v33 = (struct tagVIDEOINFOHEADER *)a3->pbFormat;
    v32 = 0;
  }
  p_bmiHeader = &v33->bmiHeader;
  v33->dwBitRate = 0;
LABEL_76:
  p_bmiHeader->biSize = 40;
  p_bmiHeader->biCompression = biCompressionFromSubtype(p_subtype);
  if ( (*((_BYTE *)this + 1568) & 3) != 0 )
  {
    p_bmiHeader->biWidth = *((_DWORD *)this + 242);
    v36 = -*((_DWORD *)this + 243);
    if ( p_bmiHeader->biHeight >= v35 )
      v36 = *((_DWORD *)this + 243);
    p_bmiHeader->biHeight = v36;
    *((_DWORD *)this + 246) = *((_DWORD *)this + 242);
    *((_DWORD *)this + 247) = *((_DWORD *)this + 243);
  }
  p_bmiHeader->biBitCount = BitCountFromSubtype();
  v37 = ImageSize(p_bmiHeader);
  v39 = a3;
  p_bmiHeader->biSizeImage = v37;
  a3->lSampleSize = v37;
  if ( *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 == *v17 && *(_QWORD *)MEDIASUBTYPE_RGB565.Data4 == v17[1] )
  {
    p_bmiHeader[1].biSize = 63488;
    p_bmiHeader[1].biWidth = 2016;
    p_bmiHeader[1].biHeight = 31;
  }
  if ( *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 == *v17 && *(_QWORD *)MEDIASUBTYPE_RGB8.Data4 == v17[1] )
  {
    p_bmiHeader->biClrUsed = 226;
    p_bmiHeader->biClrImportant = 226;
    DesktopWindow = GetDesktopWindow();
    v41 = 10;
    DC = GetDC(DesktopWindow);
    GetSystemPaletteEntries(DC, 0, 0xAu, pPalEntries);
    v43 = GetDesktopWindow();
    ReleaseDC(v43, DC);
    v38 = 0;
    for ( i = 0; i != 10; ++i )
    {
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * i + 2) = pPalEntries[i].peRed;
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * i + 1) = pPalEntries[i].peGreen;
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * i) = pPalEntries[i].peBlue;
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * i + 3) = 0;
    }
    do
    {
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v41 + 2) = byte_1800245B2[4 * v41];
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v41 + 1) = byte_1800245B1[4 * v41];
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v41) = byte_1800245B0[4 * v41];
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v41++ + 3) = 0;
    }
    while ( v41 != 226 );
    v39 = a3;
  }
  if ( *v13 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 && v13[1] == *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
  {
    v45 = v39->pbFormat;
    ConvertVIHToMFVideoFormat2((struct _MFVIDEOFORMAT *)v45, v33);
    *((_DWORD *)v45 + 7) = *(_DWORD *)(*(_QWORD *)(v52 + 80) + 28LL);
    *((_DWORD *)v45 + 9) = *((_DWORD *)this + 441);
    *((_DWORD *)v45 + 8) = *((_DWORD *)this + 440);
    *((_DWORD *)v45 + 10) = *((_DWORD *)this + 442);
    goto LABEL_103;
  }
  if ( v49 != v38 )
  {
    biWidth = *((_DWORD *)this + 225);
    if ( biWidth )
    {
      if ( *((_DWORD *)this + 226) <= v38 )
      {
LABEL_95:
        v16 = -2147418113;
        goto LABEL_103;
      }
    }
    else
    {
      if ( *((_DWORD *)this + 226) != v38 )
        goto LABEL_95;
      biWidth = p_bmiHeader->biWidth;
    }
    *((_DWORD *)v32 + 14) = biWidth;
    biHeight = *((_DWORD *)this + 226);
    if ( !biHeight )
      biHeight = p_bmiHeader->biHeight;
    *((_DWORD *)v32 + 15) = biHeight;
    if ( *((_DWORD *)this + 222) == v38 )
      *((_DWORD *)v32 + 12) = 165;
  }
LABEL_103:
  if ( v51 )
    operator delete(v51, (unsigned __int64)v5);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x180004750  mov     [rsp+arg_8], rbx
0x180004755  push    rbp
0x180004756  push    rsi
0x180004757  push    rdi
0x180004758  push    r12
0x18000475a  push    r13
0x18000475c  push    r14
0x18000475e  push    r15
0x180004760  sub     rsp, 70h
0x180004764  mov     rax, cs:__security_cookie
0x18000476b  xor     rax, rsp
0x18000476e  mov     [rsp+0A8h+var_40], rax
0x180004773  mov     eax, [rcx+38h]
0x180004776  xor     r11d, r11d
0x180004779  neg     eax
0x18000477b  mov     r9d, edx
0x18000477e  lea     rdx, [rcx+40h]; unsigned __int64
0x180004782  mov     [rsp+0A8h+var_80], r8
0x180004787  sbb     rsi, rsi
0x18000478a  mov     [rsp+0A8h+var_78], r11
0x18000478f  and     rsi, rdx
0x180004792  mov     r13, r8
0x180004795  mov     [rsp+0A8h+var_70], rsi
0x18000479a  mov     r14, rcx
0x18000479d  jz      loc_180004E1C
0x1800047a3  mov     r10, [rsi+50h]
0x1800047a7  test    r10, r10
0x1800047aa  jz      loc_180004E1C
0x1800047b0  mov     ecx, [rcx+378h]
0x1800047b6  lea     ebp, [r11+1]
0x1800047ba  test    ecx, ecx
0x1800047bc  jz      short loc_1800047CA
0x1800047be  mov     eax, r11d
0x1800047c1  cmp     [r14+380h], r11d
0x1800047c8  jz      short loc_1800047CC
0x1800047ca  mov     eax, ebp
0x1800047cc  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800047d3  lea     rdi, [rsi+2Ch]
0x1800047d7  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x1800047de  cmp     [rdi], r8
0x1800047e1  jnz     short loc_1800047E9
0x1800047e3  cmp     [rdi+8], rdx
0x1800047e7  jz      short loc_1800047F6
0x1800047e9  test    ecx, ecx
0x1800047eb  jz      short loc_1800047FB
0x1800047ed  cmp     [r14+380h], r11d
0x1800047f4  jnz     short loc_1800047FB
0x1800047f6  mov     r15d, r11d
0x1800047f9  jmp     short loc_1800047FE
0x1800047fb  mov     r15d, ebp
0x1800047fe  mov     [rsp+0A8h+var_88], r15d
0x180004803  cmp     [rdi], r8
0x180004806  jnz     short loc_18000484C
0x180004808  cmp     [rdi+8], rdx
0x18000480c  jnz     short loc_180004841
0x18000480e  test    ecx, ecx
0x180004810  jnz     short loc_180004828
0x180004812  mov     dword ptr [r10+1Ch], 7
0x18000481a  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180004821  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004828  mov     rax, [rsi+50h]
0x18000482c  cmp     dword ptr [rax+1Ch], 2
0x180004830  jz      short loc_18000483E
0x180004832  mov     eax, ebp
0x180004834  mov     [rsp+0A8h+var_88], r11d
0x180004839  mov     r15d, r11d
0x18000483c  jmp     short loc_180004841
0x18000483e  mov     eax, r11d
0x180004841  cmp     [rdi], r8
0x180004844  jnz     short loc_18000484C
0x180004846  cmp     [rdi+8], rdx
0x18000484a  jz      short loc_180004855
0x18000484c  cmp     [r14+380h], r11d
0x180004853  jz      short loc_18000487D
0x180004855  test    eax, eax
0x180004857  jz      short loc_180004885
0x180004859  cmp     r9d, 9
0x18000485d  jb      short loc_180004895
0x18000485f  cmp     r9d, 12h
0x180004863  jnb     short loc_18000488B
0x180004865  mov     rax, 0E38E38E38E38E38Fh
0x18000486f  mul     r9
0x180004872  shr     rdx, 3
0x180004876  lea     rax, [rdx+rdx*8]
0x18000487a  sub     r9, rax
0x18000487d  mov     [rsp+0A8h+var_88], r11d
0x180004882  mov     r15d, r11d
0x180004885  cmp     r9d, 9
0x180004889  jb      short loc_180004895
0x18000488b  mov     ebp, 80040206h
0x180004890  jmp     loc_180004E33
0x180004895  lfence
0x180004898  test    r13, r13
0x18000489b  jnz     short loc_1800048A5
0x18000489d  mov     ebp, r11d
0x1800048a0  jmp     loc_180004E33
0x1800048a5  mov     eax, r9d
0x1800048a8  lea     r12, __ImageBase
0x1800048af  mov     r12, rva off_180027020[r12+rax*8]
0x1800048b7  mov     rax, [rdi]
0x1800048ba  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800048c1  jnz     short loc_1800048D7
0x1800048c3  mov     rax, [rdi+8]
0x1800048c7  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x1800048ce  jnz     short loc_1800048D7
0x1800048d0  mov     ecx, 0B0h
0x1800048d5  jmp     short loc_1800048E4
0x1800048d7  mov     eax, r15d
0x1800048da  neg     eax
0x1800048dc  sbb     ecx, ecx
0x1800048de  and     ecx, 18h
0x1800048e1  add     ecx, 58h ; 'X'
0x1800048e4  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x1800048eb  sub     rax, [r12]
0x1800048ef  jnz     short loc_1800048FD
0x1800048f1  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x1800048f8  sub     rax, [r12+8]
0x1800048fd  test    rax, rax
0x180004900  setz    al
0x180004903  neg     al
0x180004905  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x18000490c  sbb     edx, edx
0x18000490e  and     edx, 0Ch
0x180004911  sub     rax, [r12]
0x180004915  jnz     short loc_180004923
0x180004917  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x18000491e  sub     rax, [r12+8]
0x180004923  test    rax, rax
0x180004926  mov     r8d, 400h
0x18000492c  cmovz   edx, r8d
0x180004930  lea     eax, [rdx+rcx]
0x180004933  mov     edx, [rsi+48h]
0x180004936  cmp     eax, edx
0x180004938  mov     rcx, r13; pmt
0x18000493b  cmovnb  edx, eax; cbFormat
0x18000493e  call    cs:__imp_MoInitMediaType
0x180004944  mov     rbx, [r13+50h]
0x180004948  xor     r11d, r11d
0x18000494b  test    rbx, rbx
0x18000494e  jnz     short loc_18000495A
0x180004950  mov     ebp, 80004003h
0x180004955  jmp     loc_180004E33
0x18000495a  mov     rax, [rdi]
0x18000495d  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004964  jnz     short loc_1800049E4
0x180004966  mov     rax, [rdi+8]
0x18000496a  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180004971  jnz     short loc_1800049E4
0x180004973  mov     rax, [rsi+50h]
0x180004977  movups  xmm0, xmmword ptr [rax]
0x18000497a  movups  xmmword ptr [rbx], xmm0
0x18000497d  movups  xmm1, xmmword ptr [rax+10h]
0x180004981  movups  xmmword ptr [rbx+10h], xmm1
0x180004985  movups  xmm0, xmmword ptr [rax+20h]
0x180004989  movups  xmmword ptr [rbx+20h], xmm0
0x18000498d  movups  xmm1, xmmword ptr [rax+30h]
0x180004991  movups  xmmword ptr [rbx+30h], xmm1
0x180004995  movups  xmm0, xmmword ptr [rax+40h]
0x180004999  movups  xmmword ptr [rbx+40h], xmm0
0x18000499d  movups  xmm1, xmmword ptr [rax+50h]
0x1800049a1  movups  xmmword ptr [rbx+50h], xmm1
0x1800049a5  movups  xmm0, xmmword ptr [rax+60h]
0x1800049a9  movups  xmmword ptr [rbx+60h], xmm0
0x1800049ad  movups  xmm1, xmmword ptr [rax+70h]
0x1800049b1  movups  xmmword ptr [rbx+70h], xmm1
0x1800049b5  movups  xmm0, xmmword ptr [rax+80h]
0x1800049bc  movups  xmmword ptr [rbx+80h], xmm0
0x1800049c3  movups  xmm1, xmmword ptr [rax+90h]
0x1800049ca  movups  xmmword ptr [rbx+90h], xmm1
0x1800049d1  movups  xmm0, xmmword ptr [rax+0A0h]
0x1800049d8  movups  xmmword ptr [rbx+0A0h], xmm0
0x1800049df  jmp     loc_180004B11
0x1800049e4  mov     rax, [rdi]
0x1800049e7  test    r15d, r15d
0x1800049ea  jz      loc_180004A9D
0x1800049f0  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800049f7  jnz     short loc_180004A61
0x1800049f9  mov     rax, [rdi+8]
0x1800049fd  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180004a04  jnz     short loc_180004A61
0x180004a06  mov     rsi, [rsi+50h]
0x180004a0a  test    rsi, rsi
0x180004a0d  jz      loc_180004B11
0x180004a13  xor     edx, edx; Val
0x180004a15  mov     rcx, rbx; void *
0x180004a18  lea     r8d, [rdx+70h]; Size
0x180004a1c  call    memset_0
0x180004a21  movups  xmm0, xmmword ptr [rsi]
0x180004a24  movdqu  xmmword ptr [rbx], xmm0
0x180004a28  movups  xmm1, xmmword ptr [rsi+10h]
0x180004a2c  movdqu  xmmword ptr [rbx+10h], xmm1
0x180004a31  mov     eax, [rsi+20h]
0x180004a34  mov     [rbx+20h], eax
0x180004a37  mov     eax, [rsi+24h]
0x180004a3a  mov     [rbx+24h], eax
0x180004a3d  mov     rax, [rsi+28h]
0x180004a41  mov     [rbx+28h], rax
0x180004a45  movups  xmm0, xmmword ptr [rsi+30h]
0x180004a49  movups  xmmword ptr [rbx+48h], xmm0
0x180004a4d  movups  xmm1, xmmword ptr [rsi+40h]
0x180004a51  movups  xmmword ptr [rbx+58h], xmm1
0x180004a55  movsd   xmm0, qword ptr [rsi+50h]
0x180004a5a  movsd   qword ptr [rbx+68h], xmm0
0x180004a5f  jmp     short loc_180004ABF
0x180004a61  mov     rax, [rsi+50h]
0x180004a65  movups  xmm0, xmmword ptr [rax]
0x180004a68  movups  xmmword ptr [rbx], xmm0
0x180004a6b  movups  xmm1, xmmword ptr [rax+10h]
0x180004a6f  movups  xmmword ptr [rbx+10h], xmm1
0x180004a73  movups  xmm0, xmmword ptr [rax+20h]
0x180004a77  movups  xmmword ptr [rbx+20h], xmm0
0x180004a7b  movups  xmm1, xmmword ptr [rax+30h]
0x180004a7f  movups  xmmword ptr [rbx+30h], xmm1
0x180004a83  movups  xmm0, xmmword ptr [rax+40h]
0x180004a87  movups  xmmword ptr [rbx+40h], xmm0
0x180004a8b  movups  xmm1, xmmword ptr [rax+50h]
0x180004a8f  movups  xmmword ptr [rbx+50h], xmm1
0x180004a93  movups  xmm0, xmmword ptr [rax+60h]
0x180004a97  movups  xmmword ptr [rbx+60h], xmm0
0x180004a9b  jmp     short loc_180004B11
0x180004a9d  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180004aa4  jnz     short loc_180004AC4
0x180004aa6  mov     rax, [rdi+8]
0x180004aaa  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180004ab1  jnz     short loc_180004AC4
0x180004ab3  mov     rcx, [rsi+50h]; struct tagVIDEOINFOHEADER2 *
0x180004ab7  mov     rdx, rbx; struct tagVIDEOINFOHEADER *
0x180004aba  call    ?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)
0x180004abf  xor     r11d, r11d
0x180004ac2  jmp     short loc_180004B11
0x180004ac4  mov     rax, [rdi]
0x180004ac7  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180004ace  jnz     short loc_180004B11
0x180004ad0  mov     rax, [rdi+8]
0x180004ad4  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180004adb  jnz     short loc_180004B11
0x180004add  mov     rax, [rsi+50h]
0x180004ae1  movups  xmm0, xmmword ptr [rax]
0x180004ae4  movups  xmmword ptr [rbx], xmm0
0x180004ae7  movups  xmm1, xmmword ptr [rax+10h]
0x180004aeb  movups  xmmword ptr [rbx+10h], xmm1
0x180004aef  movups  xmm0, xmmword ptr [rax+20h]
0x180004af3  movups  xmmword ptr [rbx+20h], xmm0
0x180004af7  movups  xmm1, xmmword ptr [rax+30h]
0x180004afb  movups  xmmword ptr [rbx+30h], xmm1
0x180004aff  movups  xmm0, xmmword ptr [rax+40h]
0x180004b03  movups  xmmword ptr [rbx+40h], xmm0
0x180004b07  movsd   xmm1, qword ptr [rax+50h]
0x180004b0c  movsd   qword ptr [rbx+50h], xmm1
0x180004b11  movups  xmm0, xmmword ptr [r12]
0x180004b16  lea     rbx, [r13+10h]
0x180004b1a  movdqu  xmmword ptr [rbx], xmm0
0x180004b1e  movups  xmm1, xmmword ptr cs:MEDIATYPE_Video.Data1
0x180004b25  movdqu  xmmword ptr [r13+0], xmm1
0x180004b2b  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180004b32  mov     [r13+20h], rbp
0x180004b36  mov     [r13+28h], r11d
0x180004b3a  movdqu  xmmword ptr [r13+2Ch], xmm0
0x180004b40  mov     rax, [rdi]
0x180004b43  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004b4a  jnz     short loc_180004B62
0x180004b4c  mov     rax, [rdi+8]
0x180004b50  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180004b57  jnz     short loc_180004B62
0x180004b59  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004b60  jmp     short loc_180004B77
0x180004b62  test    r15d, r15d
0x180004b65  jz      short loc_180004B70
0x180004b67  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x180004b6e  jmp     short loc_180004B77
0x180004b70  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180004b77  movdqu  xmmword ptr [r13+2Ch], xmm0
0x180004b7d  mov     rax, [rdi]
0x180004b80  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004b87  jnz     short loc_180004BC2
0x180004b89  mov     rax, [rdi+8]
0x180004b8d  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180004b94  jnz     short loc_180004BC2
0x180004b96  mov     rdx, [r13+50h]; struct _MFVIDEOFORMAT *
0x180004b9a  lea     rcx, [rsp+0A8h+var_78]; struct tagVIDEOINFOHEADER **
0x180004b9f  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180004ba4  xor     r11d, r11d
0x180004ba7  mov     ebp, eax
0x180004ba9  test    eax, eax
0x180004bab  js      loc_180004E21
0x180004bb1  mov     r15d, r11d
0x180004bb4  mov     r13, [rsp+0A8h+var_78]
0x180004bb9  cmp     [rsp+0A8h+var_88], r11d
0x180004bbe  jz      short loc_180004BE7
0x180004bc0  jmp     short loc_180004BD6
0x180004bc2  mov     ebp, r11d
0x180004bc5  test    r15d, r15d
0x180004bc8  jz      short loc_180004BE0
0x180004bca  mov     r15, [rsp+0A8h+var_80]
0x180004bcf  mov     r13, r11
0x180004bd2  mov     r15, [r15+50h]
0x180004bd6  lea     rsi, [r15+48h]
0x180004bda  mov     [r15+20h], r11d
0x180004bde  jmp     short loc_180004BEF
0x180004be0  mov     r13, [r13+50h]
  ... truncated ...
```
