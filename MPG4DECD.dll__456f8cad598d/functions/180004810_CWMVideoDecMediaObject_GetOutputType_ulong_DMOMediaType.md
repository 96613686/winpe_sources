# CWMVideoDecMediaObject::GetOutputType(ulong,_DMOMediaType *)

- ea: `0x180004810`
- end: `0x180004f1a`
- name: `?GetOutputType@CWMVideoDecMediaObject@@MEAAJKPEAU_DMOMediaType@@@Z`
- size: `1802`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, unsigned int, DMO_MEDIA_TYPE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001450`
- `0x1800018b0`
- `0x180002174`
- `0x180002ce4`
- `0x1800035f4`
- `0x180003934`
- `0x1800039c0`
- `0x180004810`
- `0x18000500c`
- `0x180008154`

## import_xrefs

- `msdmo!MoInitMediaType` at `0x1800049fe`
- `msdmo!MoInitMediaType` at `0x1800049fe`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180004d82`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180004dad`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180004d82`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180004dad`
- `ext-ms-win-gdi-dc-l1-2-0!GetSystemPaletteEntries` at `0x180004da7`
- `ext-ms-win-gdi-dc-l1-2-0!GetSystemPaletteEntries` at `0x180004da7`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180004d8b`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180004d8b`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180004db9`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180004db9`

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
  DWORD v37; // eax
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
  v17 = *(&off_180027030 + (unsigned int)v4);
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
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v41 + 2) = byte_1800245F2[4 * v41];
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v41 + 1) = byte_1800245F1[4 * v41];
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v41) = byte_1800245F0[4 * v41];
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
0x180004810  mov     [rsp+arg_8], rbx
0x180004815  push    rbp
0x180004816  push    rsi
0x180004817  push    rdi
0x180004818  push    r12
0x18000481a  push    r13
0x18000481c  push    r14
0x18000481e  push    r15
0x180004820  sub     rsp, 70h
0x180004824  mov     rax, cs:__security_cookie
0x18000482b  xor     rax, rsp
0x18000482e  mov     [rsp+0A8h+var_40], rax
0x180004833  mov     eax, [rcx+38h]
0x180004836  xor     r11d, r11d
0x180004839  neg     eax
0x18000483b  mov     r9d, edx
0x18000483e  lea     rdx, [rcx+40h]; unsigned __int64
0x180004842  mov     [rsp+0A8h+var_80], r8
0x180004847  sbb     rsi, rsi
0x18000484a  mov     [rsp+0A8h+var_78], r11
0x18000484f  and     rsi, rdx
0x180004852  mov     r13, r8
0x180004855  mov     [rsp+0A8h+var_70], rsi
0x18000485a  mov     r14, rcx
0x18000485d  jz      loc_180004EDC
0x180004863  mov     r10, [rsi+50h]
0x180004867  test    r10, r10
0x18000486a  jz      loc_180004EDC
0x180004870  mov     ecx, [rcx+378h]
0x180004876  lea     ebp, [r11+1]
0x18000487a  test    ecx, ecx
0x18000487c  jz      short loc_18000488A
0x18000487e  mov     eax, r11d
0x180004881  cmp     [r14+380h], r11d
0x180004888  jz      short loc_18000488C
0x18000488a  mov     eax, ebp
0x18000488c  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004893  lea     rdi, [rsi+2Ch]
0x180004897  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000489e  cmp     [rdi], r8
0x1800048a1  jnz     short loc_1800048A9
0x1800048a3  cmp     [rdi+8], rdx
0x1800048a7  jz      short loc_1800048B6
0x1800048a9  test    ecx, ecx
0x1800048ab  jz      short loc_1800048BB
0x1800048ad  cmp     [r14+380h], r11d
0x1800048b4  jnz     short loc_1800048BB
0x1800048b6  mov     r15d, r11d
0x1800048b9  jmp     short loc_1800048BE
0x1800048bb  mov     r15d, ebp
0x1800048be  mov     [rsp+0A8h+var_88], r15d
0x1800048c3  cmp     [rdi], r8
0x1800048c6  jnz     short loc_18000490C
0x1800048c8  cmp     [rdi+8], rdx
0x1800048cc  jnz     short loc_180004901
0x1800048ce  test    ecx, ecx
0x1800048d0  jnz     short loc_1800048E8
0x1800048d2  mov     dword ptr [r10+1Ch], 7
0x1800048da  mov     rdx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x1800048e1  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800048e8  mov     rax, [rsi+50h]
0x1800048ec  cmp     dword ptr [rax+1Ch], 2
0x1800048f0  jz      short loc_1800048FE
0x1800048f2  mov     eax, ebp
0x1800048f4  mov     [rsp+0A8h+var_88], r11d
0x1800048f9  mov     r15d, r11d
0x1800048fc  jmp     short loc_180004901
0x1800048fe  mov     eax, r11d
0x180004901  cmp     [rdi], r8
0x180004904  jnz     short loc_18000490C
0x180004906  cmp     [rdi+8], rdx
0x18000490a  jz      short loc_180004915
0x18000490c  cmp     [r14+380h], r11d
0x180004913  jz      short loc_18000493D
0x180004915  test    eax, eax
0x180004917  jz      short loc_180004945
0x180004919  cmp     r9d, 9
0x18000491d  jb      short loc_180004955
0x18000491f  cmp     r9d, 12h
0x180004923  jnb     short loc_18000494B
0x180004925  mov     rax, 0E38E38E38E38E38Fh
0x18000492f  mul     r9
0x180004932  shr     rdx, 3
0x180004936  lea     rax, [rdx+rdx*8]
0x18000493a  sub     r9, rax
0x18000493d  mov     [rsp+0A8h+var_88], r11d
0x180004942  mov     r15d, r11d
0x180004945  cmp     r9d, 9
0x180004949  jb      short loc_180004955
0x18000494b  mov     ebp, 80040206h
0x180004950  jmp     loc_180004EF3
0x180004955  lfence
0x180004958  test    r13, r13
0x18000495b  jnz     short loc_180004965
0x18000495d  mov     ebp, r11d
0x180004960  jmp     loc_180004EF3
0x180004965  mov     eax, r9d
0x180004968  lea     r12, __ImageBase
0x18000496f  mov     r12, rva off_180027030[r12+rax*8]
0x180004977  mov     rax, [rdi]
0x18000497a  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004981  jnz     short loc_180004997
0x180004983  mov     rax, [rdi+8]
0x180004987  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18000498e  jnz     short loc_180004997
0x180004990  mov     ecx, 0B0h
0x180004995  jmp     short loc_1800049A4
0x180004997  mov     eax, r15d
0x18000499a  neg     eax
0x18000499c  sbb     ecx, ecx
0x18000499e  and     ecx, 18h
0x1800049a1  add     ecx, 58h ; 'X'
0x1800049a4  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x1800049ab  sub     rax, [r12]
0x1800049af  jnz     short loc_1800049BD
0x1800049b1  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x1800049b8  sub     rax, [r12+8]
0x1800049bd  test    rax, rax
0x1800049c0  setz    al
0x1800049c3  neg     al
0x1800049c5  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x1800049cc  sbb     edx, edx
0x1800049ce  and     edx, 0Ch
0x1800049d1  sub     rax, [r12]
0x1800049d5  jnz     short loc_1800049E3
0x1800049d7  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x1800049de  sub     rax, [r12+8]
0x1800049e3  test    rax, rax
0x1800049e6  mov     r8d, 400h
0x1800049ec  cmovz   edx, r8d
0x1800049f0  lea     eax, [rdx+rcx]
0x1800049f3  mov     edx, [rsi+48h]
0x1800049f6  cmp     eax, edx
0x1800049f8  mov     rcx, r13; pmt
0x1800049fb  cmovnb  edx, eax; cbFormat
0x1800049fe  call    cs:__imp_MoInitMediaType
0x180004a04  mov     rbx, [r13+50h]
0x180004a08  xor     r11d, r11d
0x180004a0b  test    rbx, rbx
0x180004a0e  jnz     short loc_180004A1A
0x180004a10  mov     ebp, 80004003h
0x180004a15  jmp     loc_180004EF3
0x180004a1a  mov     rax, [rdi]
0x180004a1d  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004a24  jnz     short loc_180004AA4
0x180004a26  mov     rax, [rdi+8]
0x180004a2a  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180004a31  jnz     short loc_180004AA4
0x180004a33  mov     rax, [rsi+50h]
0x180004a37  movups  xmm0, xmmword ptr [rax]
0x180004a3a  movups  xmmword ptr [rbx], xmm0
0x180004a3d  movups  xmm1, xmmword ptr [rax+10h]
0x180004a41  movups  xmmword ptr [rbx+10h], xmm1
0x180004a45  movups  xmm0, xmmword ptr [rax+20h]
0x180004a49  movups  xmmword ptr [rbx+20h], xmm0
0x180004a4d  movups  xmm1, xmmword ptr [rax+30h]
0x180004a51  movups  xmmword ptr [rbx+30h], xmm1
0x180004a55  movups  xmm0, xmmword ptr [rax+40h]
0x180004a59  movups  xmmword ptr [rbx+40h], xmm0
0x180004a5d  movups  xmm1, xmmword ptr [rax+50h]
0x180004a61  movups  xmmword ptr [rbx+50h], xmm1
0x180004a65  movups  xmm0, xmmword ptr [rax+60h]
0x180004a69  movups  xmmword ptr [rbx+60h], xmm0
0x180004a6d  movups  xmm1, xmmword ptr [rax+70h]
0x180004a71  movups  xmmword ptr [rbx+70h], xmm1
0x180004a75  movups  xmm0, xmmword ptr [rax+80h]
0x180004a7c  movups  xmmword ptr [rbx+80h], xmm0
0x180004a83  movups  xmm1, xmmword ptr [rax+90h]
0x180004a8a  movups  xmmword ptr [rbx+90h], xmm1
0x180004a91  movups  xmm0, xmmword ptr [rax+0A0h]
0x180004a98  movups  xmmword ptr [rbx+0A0h], xmm0
0x180004a9f  jmp     loc_180004BD1
0x180004aa4  mov     rax, [rdi]
0x180004aa7  test    r15d, r15d
0x180004aaa  jz      loc_180004B5D
0x180004ab0  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180004ab7  jnz     short loc_180004B21
0x180004ab9  mov     rax, [rdi+8]
0x180004abd  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180004ac4  jnz     short loc_180004B21
0x180004ac6  mov     rsi, [rsi+50h]
0x180004aca  test    rsi, rsi
0x180004acd  jz      loc_180004BD1
0x180004ad3  xor     edx, edx; Val
0x180004ad5  mov     rcx, rbx; void *
0x180004ad8  lea     r8d, [rdx+70h]; Size
0x180004adc  call    memset_0
0x180004ae1  movups  xmm0, xmmword ptr [rsi]
0x180004ae4  movdqu  xmmword ptr [rbx], xmm0
0x180004ae8  movups  xmm1, xmmword ptr [rsi+10h]
0x180004aec  movdqu  xmmword ptr [rbx+10h], xmm1
0x180004af1  mov     eax, [rsi+20h]
0x180004af4  mov     [rbx+20h], eax
0x180004af7  mov     eax, [rsi+24h]
0x180004afa  mov     [rbx+24h], eax
0x180004afd  mov     rax, [rsi+28h]
0x180004b01  mov     [rbx+28h], rax
0x180004b05  movups  xmm0, xmmword ptr [rsi+30h]
0x180004b09  movups  xmmword ptr [rbx+48h], xmm0
0x180004b0d  movups  xmm1, xmmword ptr [rsi+40h]
0x180004b11  movups  xmmword ptr [rbx+58h], xmm1
0x180004b15  movsd   xmm0, qword ptr [rsi+50h]
0x180004b1a  movsd   qword ptr [rbx+68h], xmm0
0x180004b1f  jmp     short loc_180004B7F
0x180004b21  mov     rax, [rsi+50h]
0x180004b25  movups  xmm0, xmmword ptr [rax]
0x180004b28  movups  xmmword ptr [rbx], xmm0
0x180004b2b  movups  xmm1, xmmword ptr [rax+10h]
0x180004b2f  movups  xmmword ptr [rbx+10h], xmm1
0x180004b33  movups  xmm0, xmmword ptr [rax+20h]
0x180004b37  movups  xmmword ptr [rbx+20h], xmm0
0x180004b3b  movups  xmm1, xmmword ptr [rax+30h]
0x180004b3f  movups  xmmword ptr [rbx+30h], xmm1
0x180004b43  movups  xmm0, xmmword ptr [rax+40h]
0x180004b47  movups  xmmword ptr [rbx+40h], xmm0
0x180004b4b  movups  xmm1, xmmword ptr [rax+50h]
0x180004b4f  movups  xmmword ptr [rbx+50h], xmm1
0x180004b53  movups  xmm0, xmmword ptr [rax+60h]
0x180004b57  movups  xmmword ptr [rbx+60h], xmm0
0x180004b5b  jmp     short loc_180004BD1
0x180004b5d  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180004b64  jnz     short loc_180004B84
0x180004b66  mov     rax, [rdi+8]
0x180004b6a  cmp     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180004b71  jnz     short loc_180004B84
0x180004b73  mov     rcx, [rsi+50h]; struct tagVIDEOINFOHEADER2 *
0x180004b77  mov     rdx, rbx; struct tagVIDEOINFOHEADER *
0x180004b7a  call    ?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)
0x180004b7f  xor     r11d, r11d
0x180004b82  jmp     short loc_180004BD1
0x180004b84  mov     rax, [rdi]
0x180004b87  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180004b8e  jnz     short loc_180004BD1
0x180004b90  mov     rax, [rdi+8]
0x180004b94  cmp     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180004b9b  jnz     short loc_180004BD1
0x180004b9d  mov     rax, [rsi+50h]
0x180004ba1  movups  xmm0, xmmword ptr [rax]
0x180004ba4  movups  xmmword ptr [rbx], xmm0
0x180004ba7  movups  xmm1, xmmword ptr [rax+10h]
0x180004bab  movups  xmmword ptr [rbx+10h], xmm1
0x180004baf  movups  xmm0, xmmword ptr [rax+20h]
0x180004bb3  movups  xmmword ptr [rbx+20h], xmm0
0x180004bb7  movups  xmm1, xmmword ptr [rax+30h]
0x180004bbb  movups  xmmword ptr [rbx+30h], xmm1
0x180004bbf  movups  xmm0, xmmword ptr [rax+40h]
0x180004bc3  movups  xmmword ptr [rbx+40h], xmm0
0x180004bc7  movsd   xmm1, qword ptr [rax+50h]
0x180004bcc  movsd   qword ptr [rbx+50h], xmm1
0x180004bd1  movups  xmm0, xmmword ptr [r12]
0x180004bd6  lea     rbx, [r13+10h]
0x180004bda  movdqu  xmmword ptr [rbx], xmm0
0x180004bde  movups  xmm1, xmmword ptr cs:MEDIATYPE_Video.Data1
0x180004be5  movdqu  xmmword ptr [r13+0], xmm1
0x180004beb  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180004bf2  mov     [r13+20h], rbp
0x180004bf6  mov     [r13+28h], r11d
0x180004bfa  movdqu  xmmword ptr [r13+2Ch], xmm0
0x180004c00  mov     rax, [rdi]
0x180004c03  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004c0a  jnz     short loc_180004C22
0x180004c0c  mov     rax, [rdi+8]
0x180004c10  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180004c17  jnz     short loc_180004C22
0x180004c19  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004c20  jmp     short loc_180004C37
0x180004c22  test    r15d, r15d
0x180004c25  jz      short loc_180004C30
0x180004c27  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x180004c2e  jmp     short loc_180004C37
0x180004c30  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180004c37  movdqu  xmmword ptr [r13+2Ch], xmm0
0x180004c3d  mov     rax, [rdi]
0x180004c40  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180004c47  jnz     short loc_180004C82
0x180004c49  mov     rax, [rdi+8]
0x180004c4d  cmp     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180004c54  jnz     short loc_180004C82
0x180004c56  mov     rdx, [r13+50h]; struct _MFVIDEOFORMAT *
0x180004c5a  lea     rcx, [rsp+0A8h+var_78]; struct tagVIDEOINFOHEADER **
0x180004c5f  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180004c64  xor     r11d, r11d
0x180004c67  mov     ebp, eax
0x180004c69  test    eax, eax
0x180004c6b  js      loc_180004EE1
0x180004c71  mov     r15d, r11d
0x180004c74  mov     r13, [rsp+0A8h+var_78]
0x180004c79  cmp     [rsp+0A8h+var_88], r11d
0x180004c7e  jz      short loc_180004CA7
0x180004c80  jmp     short loc_180004C96
0x180004c82  mov     ebp, r11d
0x180004c85  test    r15d, r15d
0x180004c88  jz      short loc_180004CA0
0x180004c8a  mov     r15, [rsp+0A8h+var_80]
0x180004c8f  mov     r13, r11
0x180004c92  mov     r15, [r15+50h]
0x180004c96  lea     rsi, [r15+48h]
0x180004c9a  mov     [r15+20h], r11d
0x180004c9e  jmp     short loc_180004CAF
0x180004ca0  mov     r13, [r13+50h]
  ... truncated ...
```
