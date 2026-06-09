# CWMVideoDecMediaObject::GetOutputType(ulong,_DMOMediaType *)

- ea: `0x180029020`
- end: `0x18002987b`
- name: `?GetOutputType@CWMVideoDecMediaObject@@MEAAJKPEAU_DMOMediaType@@@Z`
- size: `2139`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, unsigned int, struct _DMOMediaType *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180012df8`
- `0x180029020`
- `0x180029884`
- `0x180029ae4`
- `0x180029d58`
- `0x180029ec8`
- `0x180029f78`
- `0x18002a004`
- `0x18002a6b0`
- `0x18002aac0`

## import_xrefs

- `msdmo!MoInitMediaType` at `0x18002930f`
- `msdmo!MoInitMediaType` at `0x18002930f`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180029619`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180029644`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180029619`
- `ext-ms-win-ntuser-window-l1-1-0!GetDesktopWindow` at `0x180029644`
- `ext-ms-win-gdi-dc-l1-2-0!GetSystemPaletteEntries` at `0x18002963e`
- `ext-ms-win-gdi-dc-l1-2-0!GetSystemPaletteEntries` at `0x18002963e`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180029622`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!GetDC` at `0x180029622`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180029650`
- `ext-ms-win-rtcore-ntuser-dc-access-l1-1-0!ReleaseDC` at `0x180029650`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::GetOutputType(
        CWMVideoDecMediaObject *this,
        unsigned int a2,
        struct _DMOMediaType *a3)
{
  int v3; // eax
  unsigned __int64 v7; // r14
  __int64 v8; // r11
  int v9; // r15d
  int v10; // ebp
  int v11; // ebx
  int v12; // edx
  bool v13; // zf
  int v14; // ecx
  __int64 v15; // r9
  __int64 *v16; // rsi
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // edx
  unsigned int v22; // r8d
  unsigned int v23; // eax
  unsigned int v24; // r9d
  unsigned int v25; // r8d
  unsigned int v26; // eax
  bool v27; // cf
  unsigned int v28; // r8d
  int v29; // ebp
  _QWORD *v30; // rbx
  __int64 v31; // rax
  int v32; // edx
  __int64 v33; // rax
  int v34; // ecx
  __int64 v35; // rax
  __int64 v36; // rax
  _OWORD *v37; // rcx
  __int64 v38; // rax
  _OWORD *v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  _OWORD *v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  char *v46; // r12
  __int64 v47; // rax
  GUID v48; // xmm0
  __int64 v49; // rax
  _DWORD *v50; // r15
  struct tagVIDEOINFOHEADER *v51; // r13
  struct tagBITMAPINFOHEADER *p_bmiHeader; // r14
  DWORD v53; // eax
  struct _DMOMediaType *v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rax
  HWND DesktopWindow; // rax
  __int64 v58; // r12
  HDC DC; // rbx
  HWND v60; // rax
  __int64 i; // rcx
  __int64 v62; // rax
  __int64 v63; // rbx
  unsigned __int64 v64; // rdx
  __int64 v65; // rax
  __int128 v66; // xmm0
  LONG biWidth; // eax
  LONG biHeight; // eax
  int v70; // [rsp+20h] [rbp-88h]
  void *Block; // [rsp+30h] [rbp-78h] BYREF
  unsigned __int64 v73; // [rsp+38h] [rbp-70h]
  tagPALETTEENTRY pPalEntries[10]; // [rsp+40h] [rbp-68h] BYREF

  v3 = -*((_DWORD *)this + 14);
  Block = 0;
  v7 = ((unsigned __int64)this + 64) & -(__int64)(v3 != 0);
  v73 = v7;
  if ( !v7 || (v8 = *(_QWORD *)((((unsigned __int64)this + 64) & -(__int64)(v3 != 0)) + 0x50)) == 0 )
  {
    v29 = -2147220989;
    goto LABEL_152;
  }
  v9 = 1;
  if ( *((_DWORD *)this + 131) || *((_DWORD *)this + 132) )
  {
    v11 = 1;
    v10 = 1;
  }
  else
  {
    v10 = 0;
    v11 = 0;
  }
  v12 = *((_DWORD *)this + 130);
  if ( !v12 || (v13 = *((_DWORD *)this + 133) == 0, v14 = 0, !v13) )
    v14 = 1;
  v15 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  v16 = (__int64 *)(v7 + 44);
  v17 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  v18 = *(_QWORD *)(v7 + 44) - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( !v18 )
    v18 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( !v18 || v12 && !*((_DWORD *)this + 133) )
    v9 = 0;
  v70 = v9;
  v19 = *v16 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( !v19 )
    v19 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( !v19 )
  {
    if ( !v12 )
    {
      *(_DWORD *)(v8 + 28) = 7;
      v17 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
      v15 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
    }
    if ( *(_DWORD *)(*(_QWORD *)(v7 + 80) + 28LL) == 2 )
    {
      v14 = 0;
    }
    else
    {
      v14 = 1;
      v70 = 0;
      v9 = 0;
    }
  }
  v20 = *v16 - v15;
  if ( *v16 == v15 )
    v20 = *(_QWORD *)(v7 + 52) - v17;
  if ( v20 && !*((_DWORD *)this + 133) )
  {
    v14 = 0;
    v21 = 0;
LABEL_33:
    v70 = 0;
    v9 = 0;
    goto LABEL_34;
  }
  v21 = 0;
  if ( v14 )
  {
    v22 = *((_DWORD *)this + 328);
    if ( a2 >= v22 && a2 < 2 * v22 )
    {
      a2 %= v22;
      v21 = 1;
      goto LABEL_33;
    }
  }
LABEL_34:
  v23 = *((_DWORD *)this + 129);
  v24 = a2;
  v25 = *((_DWORD *)this + 128);
  if ( v25 >= v23 )
  {
    if ( v10 )
    {
      if ( a2 >= v23 )
      {
        ++a2;
        if ( v14 )
        {
          if ( !v21 && a2 == *((_DWORD *)this + 328) )
            a2 = v24;
        }
      }
    }
    if ( v11 )
    {
      if ( a2 >= v25 )
      {
        v28 = a2++;
        if ( v14 )
        {
          if ( !v21 && a2 == *((_DWORD *)this + 328) )
            a2 = v28;
        }
      }
    }
  }
  else
  {
    if ( v11 )
    {
      if ( a2 >= v25 )
      {
        ++a2;
        if ( v14 )
        {
          if ( !v21 && a2 == *((_DWORD *)this + 328) )
            a2 = v24;
        }
      }
    }
    if ( v10 )
    {
      if ( a2 >= v23 )
      {
        v26 = a2++;
        if ( v14 )
        {
          if ( !v21 )
          {
            v27 = a2 < *((_DWORD *)this + 328);
            if ( a2 != *((_DWORD *)this + 328) )
              goto LABEL_60;
            a2 = v26;
          }
        }
      }
    }
  }
  v27 = a2 < *((_DWORD *)this + 328);
LABEL_60:
  if ( !v27 )
    return (unsigned int)-2147220986;
  _mm_lfence();
  if ( !a3 )
    return 0;
  v30 = *(_QWORD **)(*((_QWORD *)this + 163) + 8LL * a2);
  v31 = *v16 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( *v16 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 )
    v31 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( v31 )
    v32 = v9 != 0 ? 112 : 88;
  else
    v32 = 176;
  v33 = *v16 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( *v16 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 )
    v33 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( v33 )
  {
    v35 = *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 - *v30;
    if ( *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 == *v30 )
      v35 = *(_QWORD *)MEDIASUBTYPE_RGB565.Data4 - v30[1];
    v34 = v35 == 0 ? 0xC : 0;
    v36 = *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 - *v30;
    if ( *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 == *v30 )
      v36 = *(_QWORD *)MEDIASUBTYPE_RGB8.Data4 - v30[1];
    if ( !v36 )
      v34 = 1024;
  }
  else
  {
    v34 = 4 * *(_DWORD *)(*(_QWORD *)(v7 + 80) + 164LL);
  }
  MoInitMediaType((DMO_MEDIA_TYPE *)a3, v34 + v32);
  v37 = (_OWORD *)*((_QWORD *)a3 + 10);
  if ( !v37 )
    return (unsigned int)-2147467261;
  v38 = *v16 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( *v16 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 )
    v38 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( v38 )
  {
    v40 = *v16;
    if ( v9 )
    {
      v41 = v40 - *(_QWORD *)&FORMAT_VideoInfo.Data1;
      if ( !v41 )
        v41 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
      if ( v41 )
      {
        v42 = *(_OWORD **)(v7 + 80);
        *v37 = *v42;
        v37[1] = v42[1];
        v37[2] = v42[2];
        v37[3] = v42[3];
        v37[4] = v42[4];
        v37[5] = v42[5];
        v37[6] = v42[6];
      }
      else
      {
        ConvertVIHToVIH2(*(struct tagVIDEOINFOHEADER **)(v7 + 80), *((struct tagVIDEOINFOHEADER2 **)a3 + 10));
      }
    }
    else
    {
      v43 = v40 - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
      if ( !v43 )
        v43 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
      if ( v43 )
      {
        v44 = *v16 - *(_QWORD *)&FORMAT_VideoInfo.Data1;
        if ( *v16 == *(_QWORD *)&FORMAT_VideoInfo.Data1 )
          v44 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
        if ( !v44 )
        {
          v45 = *(_QWORD *)(v7 + 80);
          *v37 = *(_OWORD *)v45;
          v37[1] = *(_OWORD *)(v45 + 16);
          v37[2] = *(_OWORD *)(v45 + 32);
          v37[3] = *(_OWORD *)(v45 + 48);
          v37[4] = *(_OWORD *)(v45 + 64);
          *((_QWORD *)v37 + 10) = *(_QWORD *)(v45 + 80);
        }
      }
      else
      {
        ConvertVIH2ToVIH(*(struct tagVIDEOINFOHEADER2 **)(v7 + 80), *((struct tagVIDEOINFOHEADER **)a3 + 10));
      }
    }
  }
  else
  {
    v39 = *(_OWORD **)(v7 + 80);
    *v37 = *v39;
    v37[1] = v39[1];
    v37[2] = v39[2];
    v37[3] = v39[3];
    v37[4] = v39[4];
    v37[5] = v39[5];
    v37[6] = v39[6];
    v37[7] = v39[7];
    v37[8] = v39[8];
    v37[9] = v39[9];
    v37[10] = v39[10];
  }
  v46 = (char *)a3 + 16;
  *((_OWORD *)a3 + 1) = *(_OWORD *)v30;
  *(GUID *)a3 = MEDIATYPE_Video;
  *((_QWORD *)a3 + 4) = 1;
  *((_DWORD *)a3 + 10) = 0;
  *(GUID *)((char *)a3 + 44) = GUID_00000000_0000_0000_0000_000000000000;
  v47 = *v16 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( *v16 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 )
    v47 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( v47 )
  {
    if ( v9 )
      v48 = FORMAT_VideoInfo2;
    else
      v48 = FORMAT_VideoInfo;
  }
  else
  {
    v48 = FORMAT_MFVideoFormat;
  }
  *(GUID *)((char *)a3 + 44) = v48;
  v49 = *v16 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( *v16 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 )
    v49 = *(_QWORD *)(v7 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( v49 )
  {
    v29 = 0;
    if ( v9 )
    {
      v51 = 0;
      v50 = (_DWORD *)*((_QWORD *)a3 + 10);
LABEL_114:
      p_bmiHeader = (struct tagBITMAPINFOHEADER *)(v50 + 18);
      v50[8] = 0;
      goto LABEL_117;
    }
    v51 = (struct tagVIDEOINFOHEADER *)*((_QWORD *)a3 + 10);
    v50 = 0;
  }
  else
  {
    v29 = ConvertMFVideoFormatToVIH2((struct tagVIDEOINFOHEADER **)&Block, *((struct _MFVIDEOFORMAT **)a3 + 10));
    if ( v29 < 0 )
      goto LABEL_152;
    v50 = 0;
    v51 = (struct tagVIDEOINFOHEADER *)Block;
    if ( v70 )
      goto LABEL_114;
  }
  p_bmiHeader = &v51->bmiHeader;
  v51->dwBitRate = 0;
LABEL_117:
  p_bmiHeader->biSize = 40;
  p_bmiHeader->biCompression = biCompressionFromSubtype(v46);
  p_bmiHeader->biBitCount = BitCountFromSubtype();
  v53 = ImageSize(p_bmiHeader);
  v54 = a3;
  p_bmiHeader->biSizeImage = v53;
  *((_DWORD *)a3 + 10) = v53;
  v55 = *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 - *v30;
  if ( *(_QWORD *)&MEDIASUBTYPE_RGB565.Data1 == *v30 )
    v55 = *(_QWORD *)MEDIASUBTYPE_RGB565.Data4 - v30[1];
  if ( !v55 )
  {
    p_bmiHeader[1].biSize = 63488;
    p_bmiHeader[1].biWidth = 2016;
    p_bmiHeader[1].biHeight = 31;
  }
  v56 = *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 - *v30;
  if ( *(_QWORD *)&MEDIASUBTYPE_RGB8.Data1 == *v30 )
    v56 = *(_QWORD *)MEDIASUBTYPE_RGB8.Data4 - v30[1];
  if ( !v56 )
  {
    p_bmiHeader->biClrUsed = 226;
    p_bmiHeader->biClrImportant = 226;
    DesktopWindow = GetDesktopWindow();
    v58 = 10;
    DC = GetDC(DesktopWindow);
    GetSystemPaletteEntries(DC, 0, 0xAu, pPalEntries);
    v60 = GetDesktopWindow();
    ReleaseDC(v60, DC);
    for ( i = 0; i != 10; ++i )
    {
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * i + 2) = pPalEntries[i].peRed;
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * i + 1) = pPalEntries[i].peGreen;
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * i) = pPalEntries[i].peBlue;
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * i + 3) = 0;
    }
    do
    {
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v58 + 2) = *((_BYTE *)qword_180055350 + 4 * v58 + 2);
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v58 + 1) = *((_BYTE *)qword_180055350 + 4 * v58 + 1);
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v58) = *((_BYTE *)qword_180055350 + 4 * v58);
      *((_BYTE *)&p_bmiHeader[1].biSize + 4 * v58++ + 3) = 0;
    }
    while ( v58 != 226 );
    v54 = a3;
  }
  v62 = *v16 - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( *v16 == *(_QWORD *)&FORMAT_MFVideoFormat.Data1 )
    v62 = v16[1] - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( !v62 )
  {
    v63 = *((_QWORD *)v54 + 10);
    ConvertVIHToMFVideoFormat2((struct _MFVIDEOFORMAT *)v63, v51);
    v64 = v73;
    *(_DWORD *)(v63 + 28) = *(_DWORD *)(*(_QWORD *)(v73 + 80) + 28LL);
    v65 = MFVideoFormat_H263 - *((_QWORD *)this + 202);
    if ( MFVideoFormat_H263 == *((_QWORD *)this + 202) )
      v65 = 0x719B3800AA000080LL - *((_QWORD *)this + 203);
    if ( !v65 && *((_DWORD *)this + 148) && *((_DWORD *)this + 420) && *((_DWORD *)this + 421) )
    {
      *(_OWORD *)(v63 + 60) = *(_OWORD *)((char *)this + 1732);
      *(_OWORD *)(v63 + 76) = *(_OWORD *)((char *)this + 1748);
      *(_OWORD *)(v63 + 92) = *(_OWORD *)((char *)this + 1764);
      *(_DWORD *)(v63 + 8) = *((_DWORD *)this + 420);
      *(_DWORD *)(v63 + 12) = *((_DWORD *)this + 421);
      *((_DWORD *)this + 148) = 0;
    }
    else
    {
      *(_OWORD *)(v63 + 60) = *(_OWORD *)(*(_QWORD *)(v64 + 80) + 60LL);
      *(_OWORD *)(v63 + 76) = *(_OWORD *)(*(_QWORD *)(v64 + 80) + 76LL);
      v66 = *(_OWORD *)(*(_QWORD *)(v64 + 80) + 92LL);
      *(_DWORD *)(v63 + 8) += *(_DWORD *)(v63 + 8) & 1;
      *(_DWORD *)(v63 + 12) += *(_DWORD *)(v63 + 12) & 1;
      *(_OWORD *)(v63 + 92) = v66;
    }
    *(_DWORD *)(v63 + 36) = *((_DWORD *)this + 339);
    *(_DWORD *)(v63 + 32) = *((_DWORD *)this + 338);
    *(_DWORD *)(v63 + 40) = *((_DWORD *)this + 340);
    goto LABEL_152;
  }
  if ( v70 )
  {
    biWidth = *((_DWORD *)this + 134);
    if ( biWidth )
    {
      if ( !*((_DWORD *)this + 135) )
      {
LABEL_143:
        v29 = -2147418113;
        goto LABEL_152;
      }
    }
    else
    {
      if ( *((_DWORD *)this + 135) )
        goto LABEL_143;
      biWidth = p_bmiHeader->biWidth;
    }
    v50[14] = biWidth;
    biHeight = *((_DWORD *)this + 135);
    if ( !biHeight )
      biHeight = p_bmiHeader->biHeight;
    v50[15] = biHeight;
    if ( !*((_DWORD *)this + 130) )
      v50[12] = 165;
    v50[19] += v50[19] & 1;
    v50[20] += v50[20] & 1;
  }
LABEL_152:
  if ( Block )
    operator delete(Block);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x180029020  mov     [rsp+arg_8], rbx
0x180029025  push    rbp
0x180029026  push    rsi
0x180029027  push    rdi
0x180029028  push    r12
0x18002902a  push    r13
0x18002902c  push    r14
0x18002902e  push    r15
0x180029030  sub     rsp, 70h
0x180029034  mov     rax, cs:__security_cookie
0x18002903b  xor     rax, rsp
0x18002903e  mov     [rsp+0A8h+var_40], rax
0x180029043  mov     eax, [rcx+38h]
0x180029046  lea     r9, [rcx+40h]
0x18002904a  xor     r12d, r12d
0x18002904d  mov     [rsp+0A8h+var_80], r8
0x180029052  neg     eax
0x180029054  mov     [rsp+0A8h+Block], r12
0x180029059  mov     r13, r8
0x18002905c  mov     r10d, edx
0x18002905f  sbb     r14, r14
0x180029062  mov     rdi, rcx
0x180029065  and     r14, r9
0x180029068  mov     [rsp+0A8h+var_70], r14
0x18002906d  jz      loc_18002983D
0x180029073  mov     r11, [r14+50h]
0x180029077  test    r11, r11
0x18002907a  jz      loc_18002983D
0x180029080  lea     r15d, [r12+1]
0x180029085  cmp     [rcx+20Ch], r12d
0x18002908c  jnz     short loc_18002909F
0x18002908e  cmp     [rcx+210h], r12d
0x180029095  jnz     short loc_18002909F
0x180029097  mov     ebp, r12d
0x18002909a  mov     ebx, r12d
0x18002909d  jmp     short loc_1800290A5
0x18002909f  mov     ebx, r15d
0x1800290a2  mov     ebp, r15d
0x1800290a5  mov     edx, [rcx+208h]
0x1800290ab  test    edx, edx
0x1800290ad  jz      short loc_1800290BB
0x1800290af  cmp     [rcx+214h], r12d
0x1800290b6  mov     ecx, r12d
0x1800290b9  jz      short loc_1800290BE
0x1800290bb  mov     ecx, r15d
0x1800290be  mov     r9, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800290c5  lea     rsi, [r14+2Ch]
0x1800290c9  mov     rax, [rsi]
0x1800290cc  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x1800290d3  sub     rax, r9
0x1800290d6  jnz     short loc_1800290DF
0x1800290d8  mov     rax, [rsi+8]
0x1800290dc  sub     rax, r8
0x1800290df  test    rax, rax
0x1800290e2  jz      short loc_1800290F1
0x1800290e4  test    edx, edx
0x1800290e6  jz      short loc_1800290F4
0x1800290e8  cmp     [rdi+214h], r12d
0x1800290ef  jnz     short loc_1800290F4
0x1800290f1  mov     r15d, r12d
0x1800290f4  mov     rax, [rsi]
0x1800290f7  mov     [rsp+0A8h+var_88], r15d
0x1800290fc  sub     rax, r9
0x1800290ff  jnz     short loc_180029108
0x180029101  mov     rax, [rsi+8]
0x180029105  sub     rax, r8
0x180029108  test    rax, rax
0x18002910b  jnz     short loc_180029143
0x18002910d  test    edx, edx
0x18002910f  jnz     short loc_180029127
0x180029111  mov     dword ptr [r11+1Ch], 7
0x180029119  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180029120  mov     r9, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180029127  mov     rax, [r14+50h]
0x18002912b  cmp     dword ptr [rax+1Ch], 2
0x18002912f  jz      short loc_180029140
0x180029131  mov     ecx, 1
0x180029136  mov     [rsp+0A8h+var_88], r12d
0x18002913b  mov     r15d, r12d
0x18002913e  jmp     short loc_180029143
0x180029140  mov     ecx, r12d
0x180029143  mov     rax, [rsi]
0x180029146  sub     rax, r9
0x180029149  jnz     short loc_180029152
0x18002914b  mov     rax, [rsi+8]
0x18002914f  sub     rax, r8
0x180029152  test    rax, rax
0x180029155  jz      short loc_180029168
0x180029157  cmp     [rdi+214h], r12d
0x18002915e  jnz     short loc_180029168
0x180029160  mov     ecx, r12d
0x180029163  mov     edx, r12d
0x180029166  jmp     short loc_180029192
0x180029168  mov     edx, r12d
0x18002916b  test    ecx, ecx
0x18002916d  jz      short loc_18002919A
0x18002916f  mov     r8d, [rdi+520h]
0x180029176  cmp     r10d, r8d
0x180029179  jb      short loc_18002919A
0x18002917b  lea     eax, [r8+r8]
0x18002917f  cmp     r10d, eax
0x180029182  jnb     short loc_18002919A
0x180029184  mov     eax, r10d
0x180029187  div     r8d
0x18002918a  mov     r10d, edx
0x18002918d  mov     edx, 1
0x180029192  mov     [rsp+0A8h+var_88], r12d
0x180029197  mov     r15d, r12d
0x18002919a  mov     eax, [rdi+204h]
0x1800291a0  mov     r9d, r10d
0x1800291a3  mov     r8d, [rdi+200h]
0x1800291aa  cmp     r8d, eax
0x1800291ad  jnb     short loc_1800291F3
0x1800291af  test    ebx, ebx
0x1800291b1  jz      short loc_1800291CE
0x1800291b3  cmp     r10d, r8d
0x1800291b6  jb      short loc_1800291CE
0x1800291b8  inc     r10d
0x1800291bb  test    ecx, ecx
0x1800291bd  jz      short loc_1800291CE
0x1800291bf  test    edx, edx
0x1800291c1  jnz     short loc_1800291CE
0x1800291c3  cmp     r10d, [rdi+520h]
0x1800291ca  cmovz   r10d, r9d
0x1800291ce  test    ebp, ebp
0x1800291d0  jz      short loc_180029238
0x1800291d2  cmp     r10d, eax
0x1800291d5  jb      short loc_180029238
0x1800291d7  mov     eax, r10d
0x1800291da  inc     r10d
0x1800291dd  test    ecx, ecx
0x1800291df  jz      short loc_180029238
0x1800291e1  test    edx, edx
0x1800291e3  jnz     short loc_180029238
0x1800291e5  cmp     r10d, [rdi+520h]
0x1800291ec  jnz     short loc_18002923F
0x1800291ee  mov     r10d, eax
0x1800291f1  jmp     short loc_180029238
0x1800291f3  test    ebp, ebp
0x1800291f5  jz      short loc_180029214
0x1800291f7  cmp     r10d, eax
0x1800291fa  jb      short loc_180029214
0x1800291fc  inc     r10d
0x1800291ff  mov     eax, r10d
0x180029202  test    ecx, ecx
0x180029204  jz      short loc_180029214
0x180029206  test    edx, edx
0x180029208  jnz     short loc_180029214
0x18002920a  cmp     eax, [rdi+520h]
0x180029210  cmovz   r10d, r9d
0x180029214  test    ebx, ebx
0x180029216  jz      short loc_180029238
0x180029218  cmp     r10d, r8d
0x18002921b  jb      short loc_180029238
0x18002921d  mov     r8d, r10d
0x180029220  inc     r10d
0x180029223  mov     eax, r10d
0x180029226  test    ecx, ecx
0x180029228  jz      short loc_180029238
0x18002922a  test    edx, edx
0x18002922c  jnz     short loc_180029238
0x18002922e  cmp     eax, [rdi+520h]
0x180029234  cmovz   r10d, r8d
0x180029238  cmp     r10d, [rdi+520h]
0x18002923f  jb      short loc_18002924B
0x180029241  mov     ebp, 80040206h
0x180029246  jmp     loc_180029854
0x18002924b  lfence
0x18002924e  test    r13, r13
0x180029251  jnz     short loc_18002925B
0x180029253  mov     ebp, r12d
0x180029256  jmp     loc_180029854
0x18002925b  mov     rax, [rdi+518h]
0x180029262  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180029269  mov     ecx, r10d
0x18002926c  mov     rbx, [rax+rcx*8]
0x180029270  mov     rax, [rsi]
0x180029273  mov     rcx, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18002927a  sub     rax, r8
0x18002927d  jnz     short loc_180029286
0x18002927f  mov     rax, [rsi+8]
0x180029283  sub     rax, rcx
0x180029286  test    rax, rax
0x180029289  jnz     short loc_180029292
0x18002928b  mov     edx, 0B0h
0x180029290  jmp     short loc_18002929F
0x180029292  mov     eax, r15d
0x180029295  neg     eax
0x180029297  sbb     edx, edx
0x180029299  and     edx, 18h
0x18002929c  add     edx, 58h ; 'X'
0x18002929f  mov     rax, [rsi]
0x1800292a2  sub     rax, r8
0x1800292a5  jnz     short loc_1800292AE
0x1800292a7  mov     rax, [rsi+8]
0x1800292ab  sub     rax, rcx
0x1800292ae  test    rax, rax
0x1800292b1  jnz     short loc_1800292C2
0x1800292b3  mov     rax, [r14+50h]
0x1800292b7  mov     ecx, [rax+0A4h]
0x1800292bd  shl     ecx, 2
0x1800292c0  jmp     short loc_18002930A
0x1800292c2  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data1
0x1800292c9  sub     rax, [rbx]
0x1800292cc  jnz     short loc_1800292D9
0x1800292ce  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB565.Data4
0x1800292d5  sub     rax, [rbx+8]
0x1800292d9  test    rax, rax
0x1800292dc  setz    al
0x1800292df  neg     al
0x1800292e1  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data1
0x1800292e8  sbb     ecx, ecx
0x1800292ea  and     ecx, 0Ch
0x1800292ed  sub     rax, [rbx]
0x1800292f0  jnz     short loc_1800292FD
0x1800292f2  mov     rax, qword ptr cs:MEDIASUBTYPE_RGB8.Data4
0x1800292f9  sub     rax, [rbx+8]
0x1800292fd  test    rax, rax
0x180029300  mov     r8d, 400h
0x180029306  cmovz   ecx, r8d
0x18002930a  add     edx, ecx; cbFormat
0x18002930c  mov     rcx, r13; pmt
0x18002930f  call    cs:__imp_MoInitMediaType
0x180029315  mov     rcx, [r13+50h]
0x180029319  test    rcx, rcx
0x18002931c  jnz     short loc_180029328
0x18002931e  mov     ebp, 80004003h
0x180029323  jmp     loc_180029854
0x180029328  mov     rax, [rsi]
0x18002932b  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180029332  jnz     short loc_18002933F
0x180029334  mov     rax, [rsi+8]
0x180029338  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18002933f  test    rax, rax
0x180029342  jnz     short loc_1800293B5
0x180029344  mov     rax, [r14+50h]
0x180029348  movups  xmm0, xmmword ptr [rax]
0x18002934b  movups  xmmword ptr [rcx], xmm0
0x18002934e  movups  xmm1, xmmword ptr [rax+10h]
0x180029352  movups  xmmword ptr [rcx+10h], xmm1
0x180029356  movups  xmm0, xmmword ptr [rax+20h]
0x18002935a  movups  xmmword ptr [rcx+20h], xmm0
0x18002935e  movups  xmm1, xmmword ptr [rax+30h]
0x180029362  movups  xmmword ptr [rcx+30h], xmm1
0x180029366  movups  xmm0, xmmword ptr [rax+40h]
0x18002936a  movups  xmmword ptr [rcx+40h], xmm0
0x18002936e  movups  xmm1, xmmword ptr [rax+50h]
0x180029372  movups  xmmword ptr [rcx+50h], xmm1
0x180029376  movups  xmm0, xmmword ptr [rax+60h]
0x18002937a  movups  xmmword ptr [rcx+60h], xmm0
0x18002937e  movups  xmm1, xmmword ptr [rax+70h]
0x180029382  movups  xmmword ptr [rcx+70h], xmm1
0x180029386  movups  xmm0, xmmword ptr [rax+80h]
0x18002938d  movups  xmmword ptr [rcx+80h], xmm0
0x180029394  movups  xmm1, xmmword ptr [rax+90h]
0x18002939b  movups  xmmword ptr [rcx+90h], xmm1
0x1800293a2  movups  xmm0, xmmword ptr [rax+0A0h]
0x1800293a9  movups  xmmword ptr [rcx+0A0h], xmm0
0x1800293b0  jmp     loc_18002949A
0x1800293b5  mov     rax, [rsi]
0x1800293b8  test    r15d, r15d
0x1800293bb  jz      short loc_180029423
0x1800293bd  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x1800293c4  jnz     short loc_1800293D1
0x1800293c6  mov     rax, [rsi+8]
0x1800293ca  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800293d1  test    rax, rax
0x1800293d4  jnz     short loc_1800293E7
0x1800293d6  mov     rdx, rcx; struct tagVIDEOINFOHEADER2 *
0x1800293d9  mov     rcx, [r14+50h]; struct tagVIDEOINFOHEADER *
0x1800293dd  call    ?ConvertVIHToVIH2@@YAJPEAUtagVIDEOINFOHEADER@@PEAUtagVIDEOINFOHEADER2@@@Z; ConvertVIHToVIH2(tagVIDEOINFOHEADER *,tagVIDEOINFOHEADER2 *)
0x1800293e2  jmp     loc_18002949A
0x1800293e7  mov     rax, [r14+50h]
0x1800293eb  movups  xmm0, xmmword ptr [rax]
0x1800293ee  movups  xmmword ptr [rcx], xmm0
0x1800293f1  movups  xmm1, xmmword ptr [rax+10h]
0x1800293f5  movups  xmmword ptr [rcx+10h], xmm1
0x1800293f9  movups  xmm0, xmmword ptr [rax+20h]
0x1800293fd  movups  xmmword ptr [rcx+20h], xmm0
0x180029401  movups  xmm1, xmmword ptr [rax+30h]
0x180029405  movups  xmmword ptr [rcx+30h], xmm1
0x180029409  movups  xmm0, xmmword ptr [rax+40h]
0x18002940d  movups  xmmword ptr [rcx+40h], xmm0
0x180029411  movups  xmm1, xmmword ptr [rax+50h]
0x180029415  movups  xmmword ptr [rcx+50h], xmm1
0x180029419  movups  xmm0, xmmword ptr [rax+60h]
0x18002941d  movups  xmmword ptr [rcx+60h], xmm0
0x180029421  jmp     short loc_18002949A
0x180029423  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18002942a  jnz     short loc_180029437
0x18002942c  mov     rax, [rsi+8]
0x180029430  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180029437  test    rax, rax
0x18002943a  jnz     short loc_18002944A
0x18002943c  mov     rdx, rcx; struct tagVIDEOINFOHEADER *
0x18002943f  mov     rcx, [r14+50h]; struct tagVIDEOINFOHEADER2 *
0x180029443  call    ?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)
0x180029448  jmp     short loc_18002949A
0x18002944a  mov     rax, [rsi]
0x18002944d  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
  ... truncated ...
```
