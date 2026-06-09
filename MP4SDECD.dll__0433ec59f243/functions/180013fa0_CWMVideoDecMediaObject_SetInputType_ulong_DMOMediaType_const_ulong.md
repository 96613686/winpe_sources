# CWMVideoDecMediaObject::SetInputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x180013fa0`
- end: `0x18001465d`
- name: `?SetInputType@CWMVideoDecMediaObject@@UEAAJKPEBU_DMOMediaType@@K@Z`
- size: `1725`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `20`
- tags: `file_ops`

## callees

- `0x180012a08`
- `0x1800131e8`
- `0x180013fa0`
- `0x180014664`
- `0x18001470c`
- `0x180014f1c`
- `0x1800150c8`
- `0x180028c80`
- `0x180028e34`
- `0x18002a670`
- `0x18002a6b0`
- `0x18002a6bc`
- `0x18002aac0`
- `0x18002b394`
- `0x18002b8e0`
- `0x18002bfac`
- `0x18002c0bc`
- `0x18002d62c`
- `0x18002d778`
- `0x1800457f9`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013fef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013fef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001462b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001462b`
- `msdmo!MoCopyMediaType` at `0x1800140d9`
- `msdmo!MoCopyMediaType` at `0x180014589`
- `msdmo!MoCopyMediaType` at `0x1800145b6`
- `msdmo!MoCopyMediaType` at `0x1800140d9`
- `msdmo!MoCopyMediaType` at `0x180014589`
- `msdmo!MoCopyMediaType` at `0x1800145b6`
- `msdmo!MoFreeMediaType` at `0x180014063`
- `msdmo!MoFreeMediaType` at `0x180014070`
- `msdmo!MoFreeMediaType` at `0x18001455d`
- `msdmo!MoFreeMediaType` at `0x18001456a`
- `msdmo!MoFreeMediaType` at `0x180014605`
- `msdmo!MoFreeMediaType` at `0x180014616`
- `msdmo!MoFreeMediaType` at `0x180014620`
- `msdmo!MoFreeMediaType` at `0x180014063`
- `msdmo!MoFreeMediaType` at `0x180014070`
- `msdmo!MoFreeMediaType` at `0x18001455d`
- `msdmo!MoFreeMediaType` at `0x18001456a`
- `msdmo!MoFreeMediaType` at `0x180014605`
- `msdmo!MoFreeMediaType` at `0x180014616`
- `msdmo!MoFreeMediaType` at `0x180014620`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::SetInputType(
        CWMVideoDecMediaObject *this,
        int a2,
        const struct _DMOMediaType *a3,
        char a4)
{
  BYTE *v8; // r12
  HRESULT v9; // ebx
  __int64 v10; // rax
  HRESULT v11; // eax
  BYTE *pbFormat; // r13
  ULONG cbFormat; // r14d
  SessionFrameDecoder *v14; // rsi
  int v15; // ebx
  struct tagVIDEOINFOHEADER *v16; // rax
  BYTE *v17; // rax
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  int *v23; // rcx
  int *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rcx
  unsigned int v29; // ebx
  SessionFrameDecoder *v30; // rax
  double v31; // xmm0_8
  __int64 v32; // r9
  bool v33; // zf
  int v35; // [rsp+28h] [rbp-D8h]
  int v36; // [rsp+40h] [rbp-C0h]
  int v37; // [rsp+40h] [rbp-C0h]
  int v38; // [rsp+44h] [rbp-BCh]
  int v39; // [rsp+48h] [rbp-B8h]
  GUID Buf1; // [rsp+50h] [rbp-B0h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-A0h]
  DMO_MEDIA_TYPE pmt; // [rsp+70h] [rbp-90h] BYREF
  DMO_MEDIA_TYPE pmtDest; // [rsp+D0h] [rbp-30h] BYREF
  DMO_MEDIA_TYPE pmtSrc; // [rsp+130h] [rbp+30h] BYREF

  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 216);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  v8 = 0;
  pmt.majortype.Data1 = 0;
  memset_0(&pmt.majortype.Data2, 0, 0x54u);
  pmtSrc.majortype.Data1 = 0;
  memset_0(&pmtSrc.majortype.Data2, 0, 0x54u);
  pmtDest.majortype.Data1 = 0;
  memset_0(&pmtDest.majortype.Data2, 0, 0x54u);
  if ( a2 )
  {
    v9 = -2147220991;
    goto LABEL_94;
  }
  if ( !a3 )
  {
    if ( (a4 & 2) != 0 )
    {
      v9 = 0;
      if ( *((_DWORD *)this + 2) )
      {
        *((_DWORD *)this + 2) = 0;
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 1112));
        memset_0((char *)this + 1448, 0, 0xB0u);
      }
      memset_0((char *)this + 1272, 0, 0xB0u);
    }
    else
    {
      v9 = -2147467261;
    }
    goto LABEL_94;
  }
  v10 = *(_QWORD *)((char *)a3 + 44) - *(_QWORD *)&FORMAT_MPEG2Video.Data1;
  if ( !v10 )
    v10 = *(_QWORD *)((char *)a3 + 52) - *(_QWORD *)FORMAT_MPEG2Video.Data4;
  if ( v10 )
    v11 = MoCopyMediaType(&pmtDest, (const DMO_MEDIA_TYPE *)a3);
  else
    v11 = MoConvertMPEG2ToVIH2(a3, (struct _DMOMediaType *)&pmtDest);
  v9 = v11;
  if ( v11 >= 0 )
  {
    pbFormat = pmtDest.pbFormat;
    cbFormat = pmtDest.cbFormat;
    Buf1 = pmtDest.formattype;
    if ( (int)prvValidateMediaTypeSize(&Buf1) >= 0 )
    {
      v9 = CheckType((const struct _DMOMediaType *)&pmtDest, (const struct _GUID *const *)&off_180059030, 0xDu);
      if ( v9 < 0 )
        goto LABEL_94;
      v14 = 0;
      v15 = 0;
      v38 = 0;
      v39 = 0;
      if ( !memcmp_0(&pmtDest.formattype, &FORMAT_MFVideoFormat, 0x10u) )
      {
        if ( !pbFormat )
        {
          v9 = -2147467261;
          goto LABEL_87;
        }
        v16 = (struct tagVIDEOINFOHEADER *)operator new[](0x458u);
        v8 = (BYTE *)v16;
        if ( !v16 )
          goto LABEL_20;
        v9 = ConvertMFVideoFormatToVIH3(v16, (struct _MFVIDEOFORMAT *)pbFormat);
        if ( v9 < 0 )
          goto LABEL_87;
        v17 = v8;
        v15 = 0;
        goto LABEL_29;
      }
      if ( !memcmp_0(&pmtDest.formattype, &FORMAT_VideoInfo, 0x10u) )
      {
        v17 = pbFormat;
LABEL_30:
        v18 = *((_DWORD *)v17 + 13);
        *(_QWORD *)&Buf1.Data1 = v17;
        if ( v18 > 0 )
        {
          v19 = *((_DWORD *)v17 + 14);
          if ( v19 > 0 && v18 <= 4096 && v19 <= 4096 )
          {
            if ( !*((_DWORD *)this + 3) )
              goto LABEL_50;
            v20 = *(_QWORD *)((char *)this + 148) - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
            if ( !v20 )
              v20 = *(_QWORD *)((char *)this + 156) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
            if ( !v20 )
              goto LABEL_50;
            v21 = *(_QWORD *)((char *)this + 148) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
            if ( !v21 )
              v21 = *(_QWORD *)((char *)this + 156) - *(_QWORD *)FORMAT_VideoInfo.Data4;
            if ( v21 )
            {
              v25 = *(_QWORD *)((char *)this + 148) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
              if ( !v25 )
                v25 = *(_QWORD *)((char *)this + 156) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
              if ( v25 )
                goto LABEL_86;
              v26 = *((_QWORD *)this + 23);
              v23 = (int *)(v26 + 76);
              v24 = (int *)(v26 + 80);
            }
            else
            {
              v22 = *((_QWORD *)this + 23);
              v23 = (int *)(v22 + 52);
              v24 = (int *)(v22 + 56);
            }
            v27 = -*v24;
            if ( *v24 > 0 )
              v27 = *v24;
            if ( v19 <= v27 && v18 <= *v23 )
            {
LABEL_50:
              v37 = NeedHeader(pmtDest.subtype.Data1);
              if ( (!v37
                 || (memcmp_0(&pmtDest.formattype, &FORMAT_MFVideoFormat, 0x10u) || cbFormat > 0xB0)
                 && (memcmp_0(&pmtDest.formattype, &FORMAT_VideoInfo, 0x10u) || cbFormat > 0x58)
                 && (memcmp_0(&pmtDest.formattype, &FORMAT_VideoInfo2, 0x10u) || cbFormat > 0x70))
                && cbFormat <= 0x2710 )
              {
                if ( (a4 & 1) != 0 )
                {
                  v9 = 0;
                  goto LABEL_87;
                }
                *((_DWORD *)this + 123) = v15;
                *((_DWORD *)this + 122) = v39;
                *((_DWORD *)this + 134) = 0;
                *((_DWORD *)this + 121) = v38;
                *(_QWORD *)((char *)this + 476) = 0;
                if ( !memcmp_0(&pmtDest.formattype, &FORMAT_MFVideoFormat, 0x10u) )
                {
                  v29 = 176;
                }
                else if ( !memcmp_0(&pmtDest.formattype, &FORMAT_VideoInfo2, 0x10u) )
                {
                  v29 = 112;
                }
                else
                {
                  if ( memcmp_0(&pmtDest.formattype, &FORMAT_VideoInfo, 0x10u) )
                    goto LABEL_86;
                  v29 = 88;
                }
                if ( !v37 && cbFormat == v29 )
                  goto LABEL_78;
                if ( (memcmp_0(&pmtDest.formattype, &FORMAT_MFVideoFormat, 0x10u) || cbFormat > 0xB0)
                  && (memcmp_0(&pmtDest.formattype, &FORMAT_VideoInfo, 0x10u) || cbFormat > 0x58)
                  && (memcmp_0(&pmtDest.formattype, &FORMAT_VideoInfo2, 0x10u) || cbFormat > 0x70) )
                {
                  v30 = (SessionFrameDecoder *)operator new(0x28u);
                  if ( !v30 || (v14 = SessionFrameDecoder::SessionFrameDecoder(v30)) == 0 )
                  {
LABEL_20:
                    v9 = -2147024882;
LABEL_87:
                    if ( v8 )
                      operator delete(v8);
                    if ( v14 )
                      SessionFrameDecoder::`vector deleting destructor'(v14, 1u);
                    if ( v38 )
                      MoFreeMediaType(&pmt);
                    goto LABEL_94;
                  }
                  v31 = FramesPerSecond(*(_QWORD *)(*(_QWORD *)&Buf1.Data1 + 40LL));
                  if ( (int)SessionFrameDecoder::Init(
                              v14,
                              pmtDest.subtype.Data1,
                              v31,
                              *(_DWORD *)(v32 + 52),
                              *(_DWORD *)(v32 + 56),
                              v35,
                              0) >= 0
                    && (int)SessionFrameDecoder::setExtendedFormat(v14, &pbFormat[v29], cbFormat - v29) >= 0 )
                  {
LABEL_78:
                    v33 = g_petwPro == 0;
                    *((_DWORD *)this + 135) = 1;
                    if ( !v33 )
                      ETWWrite(v28, MP4SDECD_Discontinuity_Notification_Info, 0, 0);
                    v33 = *((_DWORD *)this + 2) == 0;
                    *((_QWORD *)this + 68) = 1;
                    if ( !v33 )
                    {
                      *((_DWORD *)this + 2) = 0;
                      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
                      MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 1112));
                      memset_0((char *)this + 1448, 0, 0xB0u);
                    }
                    v9 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 16), &pmtDest);
                    if ( v9 >= 0 )
                    {
                      v9 = ConvertDMOMediaTypeToMFMediaType(
                             (struct _MFVIDEOFORMAT *)((char *)this + 1448),
                             (const struct _DMOMediaType *)&pmtDest);
                      if ( v9 >= 0 )
                      {
                        v9 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 1112), &pmtSrc);
                        if ( v9 >= 0 )
                        {
                          *((_DWORD *)this + 73) = 0;
                          *((_DWORD *)this + 2) = 1;
                        }
                      }
                    }
                    goto LABEL_87;
                  }
                }
              }
            }
          }
        }
LABEL_86:
        v9 = -2147220987;
        goto LABEL_87;
      }
      if ( !memcmp_0(&pmtDest.formattype, &FORMAT_VideoInfo2, 0x10u) )
      {
        v39 = *((_DWORD *)pbFormat + 14);
        v36 = *((_DWORD *)pbFormat + 15);
        v9 = MoConvertVIH2ToVIH((const struct _DMOMediaType *)&pmtDest, (struct _DMOMediaType *)&pmt);
        if ( v9 < 0 )
          goto LABEL_94;
        v17 = pmt.pbFormat;
        v15 = v36;
        v38 = 1;
LABEL_29:
        cbFormat = pmtDest.cbFormat;
        pbFormat = pmtDest.pbFormat;
        goto LABEL_30;
      }
    }
    v9 = -2147220987;
  }
LABEL_94:
  MoFreeMediaType(&pmtDest);
  MoFreeMediaType(&pmtSrc);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180013fa0  mov     [rsp-8+arg_8], rbx
0x180013fa5  push    rbp
0x180013fa6  push    rsi
0x180013fa7  push    rdi
0x180013fa8  push    r12
0x180013faa  push    r13
0x180013fac  push    r14
0x180013fae  push    r15
0x180013fb0  lea     rbp, [rsp-0A0h]
0x180013fb8  sub     rsp, 1A0h
0x180013fbf  mov     rax, cs:__security_cookie
0x180013fc6  xor     rax, rsp
0x180013fc9  mov     [rbp+0D0h+var_40], rax
0x180013fd0  lea     rax, [rcx+0D8h]
0x180013fd7  mov     [rsp+1D0h+var_184], r9d
0x180013fdc  mov     rdi, rcx
0x180013fdf  mov     [rsp+1D0h+lpCriticalSection], rax
0x180013fe4  mov     rcx, rax; lpCriticalSection
0x180013fe7  mov     r14d, r9d
0x180013fea  mov     rsi, r8
0x180013fed  mov     ebx, edx
0x180013fef  call    cs:__imp_EnterCriticalSection
0x180013ff5  xor     r12d, r12d
0x180013ff8  lea     rcx, [rsp+1D0h+pmt.majortype.Data2]; void *
0x180013ffd  xor     edx, edx; Val
0x180013fff  mov     [rsp+1D0h+pmt.majortype.Data1], r12d
0x180014004  lea     r15d, [r12+54h]
0x180014009  mov     r8d, r15d; Size
0x18001400c  call    memset_0
0x180014011  mov     r8d, r15d; Size
0x180014014  mov     [rbp+0D0h+pmtSrc.majortype.Data1], r12d
0x180014018  xor     edx, edx; Val
0x18001401a  lea     rcx, [rbp+0D0h+pmtSrc.majortype.Data2]; void *
0x18001401e  call    memset_0
0x180014023  mov     r8d, r15d; Size
0x180014026  mov     [rbp+0D0h+pmtDest.majortype.Data1], r12d
0x18001402a  xor     edx, edx; Val
0x18001402c  lea     rcx, [rbp+0D0h+pmtDest.majortype.Data2]; void *
0x180014030  call    memset_0
0x180014035  cmp     ebx, 1
0x180014038  jb      short loc_180014044
0x18001403a  mov     ebx, 80040201h
0x18001403f  jmp     loc_180014612
0x180014044  test    rsi, rsi
0x180014047  jnz     short loc_1800140A7
0x180014049  test    r14b, 2
0x18001404d  jz      short loc_18001409D
0x18001404f  xor     ebx, ebx
0x180014051  mov     r15d, 0B0h
0x180014057  cmp     [rdi+8], ebx
0x18001405a  jz      short loc_180014087
0x18001405c  lea     rcx, [rdi+10h]; pmt
0x180014060  mov     [rdi+8], ebx
0x180014063  call    cs:__imp_MoFreeMediaType
0x180014069  lea     rcx, [rdi+458h]; pmt
0x180014070  call    cs:__imp_MoFreeMediaType
0x180014076  lea     rcx, [rdi+5A8h]; void *
0x18001407d  mov     r8d, r15d; Size
0x180014080  xor     edx, edx; Val
0x180014082  call    memset_0
0x180014087  lea     rcx, [rdi+4F8h]; void *
0x18001408e  mov     r8, r15; Size
0x180014091  xor     edx, edx; Val
0x180014093  call    memset_0
0x180014098  jmp     loc_180014612
0x18001409d  mov     ebx, 80004003h
0x1800140a2  jmp     loc_180014612
0x1800140a7  mov     rax, [rsi+2Ch]
0x1800140ab  sub     rax, qword ptr cs:FORMAT_MPEG2Video.Data1
0x1800140b2  jnz     short loc_1800140BF
0x1800140b4  mov     rax, [rsi+34h]
0x1800140b8  sub     rax, qword ptr cs:FORMAT_MPEG2Video.Data4
0x1800140bf  test    rax, rax
0x1800140c2  jnz     short loc_1800140D2
0x1800140c4  lea     rdx, [rbp+0D0h+pmtDest]; struct _DMOMediaType *
0x1800140c8  mov     rcx, rsi; struct _DMOMediaType *
0x1800140cb  call    ?MoConvertMPEG2ToVIH2@@YAJPEBU_DMOMediaType@@PEAU1@@Z; MoConvertMPEG2ToVIH2(_DMOMediaType const *,_DMOMediaType *)
0x1800140d0  jmp     short loc_1800140DF
0x1800140d2  mov     rdx, rsi; pmtSrc
0x1800140d5  lea     rcx, [rbp+0D0h+pmtDest]; pmtDest
0x1800140d9  call    cs:__imp_MoCopyMediaType
0x1800140df  mov     ebx, eax
0x1800140e1  test    eax, eax
0x1800140e3  js      loc_180014612
0x1800140e9  mov     rax, qword ptr [rbp+0D0h+pmtDest.formattype.Data1]
0x1800140ed  lea     rcx, [rsp+1D0h+Buf1]; Buf1
0x1800140f2  mov     r13, [rbp+0D0h+pmtDest.pbFormat]
0x1800140f6  mov     r14d, [rbp+0D0h+pmtDest.cbFormat]
0x1800140fa  mov     rdx, r13
0x1800140fd  mov     [rsp+1D0h+Buf1], rax
0x180014102  mov     r8d, r14d
0x180014105  mov     rax, qword ptr [rbp+0D0h+pmtDest.formattype.Data4]
0x180014109  mov     [rsp+1D0h+var_178], rax
0x18001410e  call    prvValidateMediaTypeSize
0x180014113  test    eax, eax
0x180014115  js      loc_18001460D
0x18001411b  mov     r8d, 0Dh; unsigned int
0x180014121  lea     rdx, off_180059030; struct _GUID **
0x180014128  lea     rcx, [rbp+0D0h+pmtDest]; struct _DMOMediaType *
0x18001412c  call    ?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_DMOMediaType const *,_GUID const * const *,uint)
0x180014131  mov     ebx, eax
0x180014133  test    eax, eax
0x180014135  js      loc_180014612
0x18001413b  xor     esi, esi
0x18001413d  lea     rdx, FORMAT_MFVideoFormat; Buf2
0x180014144  xor     ebx, ebx
0x180014146  mov     [rsp+1D0h+var_18C], esi
0x18001414a  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x18001414e  mov     [rsp+1D0h+var_188], ebx
0x180014152  lea     r15d, [rsi+10h]
0x180014156  mov     r8d, r15d; Size
0x180014159  call    memcmp_0
0x18001415e  test    eax, eax
0x180014160  jnz     short loc_1800141A9
0x180014162  test    r13, r13
0x180014165  jz      short loc_18001419F
0x180014167  mov     ecx, 458h; unsigned __int64
0x18001416c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014171  mov     r12, rax
0x180014174  test    rax, rax
0x180014177  jnz     short loc_180014183
0x180014179  mov     ebx, 8007000Eh
0x18001417e  jmp     loc_1800145DA
0x180014183  mov     rdx, r13; struct _MFVIDEOFORMAT *
0x180014186  mov     rcx, r12; struct tagVIDEOINFOHEADER *
0x180014189  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x18001418e  mov     ebx, eax
0x180014190  test    eax, eax
0x180014192  js      loc_1800145DA
0x180014198  mov     rax, r12
0x18001419b  mov     ebx, esi
0x18001419d  jmp     short loc_180014218
0x18001419f  mov     ebx, 80004003h
0x1800141a4  jmp     loc_1800145DA
0x1800141a9  mov     r8, r15; Size
0x1800141ac  lea     rdx, FORMAT_VideoInfo; Buf2
0x1800141b3  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x1800141b7  call    memcmp_0
0x1800141bc  test    eax, eax
0x1800141be  jnz     short loc_1800141C5
0x1800141c0  mov     rax, r13
0x1800141c3  jmp     short loc_180014220
0x1800141c5  mov     r8, r15; Size
0x1800141c8  lea     rdx, FORMAT_VideoInfo2; Buf2
0x1800141cf  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x1800141d3  call    memcmp_0
0x1800141d8  test    eax, eax
0x1800141da  jnz     loc_18001460D
0x1800141e0  mov     eax, [r13+38h]
0x1800141e4  lea     rdx, [rsp+1D0h+pmt]; struct _DMOMediaType *
0x1800141e9  mov     [rsp+1D0h+var_188], eax
0x1800141ed  lea     rcx, [rbp+0D0h+pmtDest]; struct _DMOMediaType *
0x1800141f1  mov     eax, [r13+3Ch]
0x1800141f5  mov     [rsp+1D0h+var_190], eax
0x1800141f9  call    ?MoConvertVIH2ToVIH@@YAJPEBU_DMOMediaType@@PEAU1@@Z; MoConvertVIH2ToVIH(_DMOMediaType const *,_DMOMediaType *)
0x1800141fe  mov     ebx, eax
0x180014200  test    eax, eax
0x180014202  js      loc_180014612
0x180014208  mov     rax, [rbp+0D0h+pmt.pbFormat]
0x18001420c  mov     ebx, [rsp+1D0h+var_190]
0x180014210  mov     [rsp+1D0h+var_18C], 1
0x180014218  mov     r14d, [rbp+0D0h+pmtDest.cbFormat]
0x18001421c  mov     r13, [rbp+0D0h+pmtDest.pbFormat]
0x180014220  mov     r8d, [rax+34h]
0x180014224  mov     [rsp+1D0h+Buf1], rax
0x180014229  test    r8d, r8d
0x18001422c  jle     loc_1800145D5
0x180014232  mov     r9d, [rax+38h]
0x180014236  test    r9d, r9d
0x180014239  jle     loc_1800145D5
0x18001423f  mov     eax, 1000h
0x180014244  cmp     r8d, eax
0x180014247  jg      loc_1800145D5
0x18001424d  cmp     r9d, eax
0x180014250  jg      loc_1800145D5
0x180014256  cmp     [rdi+0Ch], esi
0x180014259  jz      loc_180014309
0x18001425f  mov     rax, [rdi+94h]
0x180014266  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18001426d  jnz     short loc_18001427D
0x18001426f  mov     rax, [rdi+9Ch]
0x180014276  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18001427d  test    rax, rax
0x180014280  jz      loc_180014309
0x180014286  mov     rax, [rdi+94h]
0x18001428d  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180014294  jnz     short loc_1800142A4
0x180014296  mov     rax, [rdi+9Ch]
0x18001429d  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x1800142a4  test    rax, rax
0x1800142a7  jnz     short loc_1800142BA
0x1800142a9  mov     rax, [rdi+0B8h]
0x1800142b0  lea     rcx, [rax+34h]
0x1800142b4  lea     rdx, [rax+38h]
0x1800142b8  jmp     short loc_1800142F0
0x1800142ba  mov     rax, [rdi+94h]
0x1800142c1  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800142c8  jnz     short loc_1800142D8
0x1800142ca  mov     rax, [rdi+9Ch]
0x1800142d1  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800142d8  test    rax, rax
0x1800142db  jnz     loc_1800145D5
0x1800142e1  mov     rax, [rdi+0B8h]
0x1800142e8  lea     rcx, [rax+4Ch]
0x1800142ec  lea     rdx, [rax+50h]
0x1800142f0  mov     eax, [rdx]
0x1800142f2  neg     eax
0x1800142f4  cmovs   eax, [rdx]
0x1800142f7  cmp     r9d, eax
0x1800142fa  jg      loc_1800145D5
0x180014300  cmp     r8d, [rcx]
0x180014303  jg      loc_1800145D5
0x180014309  mov     ecx, [rbp+0D0h+pmtDest.subtype.Data1]
0x18001430c  call    NeedHeader
0x180014311  mov     [rsp+1D0h+var_190], eax
0x180014315  mov     r15d, 0B0h
0x18001431b  test    eax, eax
0x18001431d  jz      short loc_18001438A
0x18001431f  mov     r8d, 10h; Size
0x180014325  lea     rdx, FORMAT_MFVideoFormat; Buf2
0x18001432c  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x180014330  call    memcmp_0
0x180014335  test    eax, eax
0x180014337  jnz     short loc_180014342
0x180014339  cmp     r14d, r15d
0x18001433c  jbe     loc_1800145D5
0x180014342  mov     r8d, 10h; Size
0x180014348  lea     rdx, FORMAT_VideoInfo; Buf2
0x18001434f  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x180014353  call    memcmp_0
0x180014358  test    eax, eax
0x18001435a  jnz     short loc_180014366
0x18001435c  cmp     r14d, 58h ; 'X'
0x180014360  jbe     loc_1800145D5
0x180014366  mov     r8d, 10h; Size
0x18001436c  lea     rdx, FORMAT_VideoInfo2; Buf2
0x180014373  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x180014377  call    memcmp_0
0x18001437c  test    eax, eax
0x18001437e  jnz     short loc_18001438A
0x180014380  cmp     r14d, 70h ; 'p'
0x180014384  jbe     loc_1800145D5
0x18001438a  cmp     r14d, 2710h
0x180014391  ja      loc_1800145D5
0x180014397  test    byte ptr [rsp+1D0h+var_184], 1
0x18001439c  jz      short loc_1800143A5
0x18001439e  xor     ebx, ebx
0x1800143a0  jmp     loc_1800145DA
0x1800143a5  mov     eax, [rsp+1D0h+var_188]
0x1800143a9  lea     rdx, FORMAT_MFVideoFormat; Buf2
0x1800143b0  mov     [rdi+1ECh], ebx
0x1800143b6  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x1800143ba  mov     [rdi+1E8h], eax
0x1800143c0  mov     ebx, 10h
0x1800143c5  mov     eax, [rsp+1D0h+var_18C]
0x1800143c9  mov     r8d, ebx; Size
0x1800143cc  mov     [rdi+218h], esi
0x1800143d2  mov     [rdi+1E4h], eax
0x1800143d8  mov     [rdi+1DCh], rsi
0x1800143df  call    memcmp_0
0x1800143e4  test    eax, eax
0x1800143e6  jnz     short loc_1800143ED
0x1800143e8  mov     ebx, r15d
0x1800143eb  jmp     short loc_180014427
0x1800143ed  mov     r8, rbx; Size
0x1800143f0  lea     rdx, FORMAT_VideoInfo2; Buf2
0x1800143f7  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x1800143fb  call    memcmp_0
0x180014400  test    eax, eax
0x180014402  jnz     short loc_180014409
0x180014404  lea     ebx, [rax+70h]
0x180014407  jmp     short loc_180014427
0x180014409  mov     r8, rbx; Size
0x18001440c  lea     rdx, FORMAT_VideoInfo; Buf2
0x180014413  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x180014417  call    memcmp_0
0x18001441c  test    eax, eax
0x18001441e  jnz     loc_1800145D5
0x180014424  lea     ebx, [rax+58h]
0x180014427  cmp     [rsp+1D0h+var_190], esi
0x18001442b  jnz     short loc_180014436
0x18001442d  cmp     r14d, ebx
0x180014430  jz      loc_18001451B
0x180014436  mov     r8d, 10h; Size
0x18001443c  lea     rdx, FORMAT_MFVideoFormat; Buf2
0x180014443  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x180014447  call    memcmp_0
0x18001444c  test    eax, eax
0x18001444e  jnz     short loc_180014459
0x180014450  cmp     r14d, r15d
0x180014453  jbe     loc_1800145D5
0x180014459  mov     r8d, 10h; Size
0x18001445f  lea     rdx, FORMAT_VideoInfo; Buf2
0x180014466  lea     rcx, [rbp+0D0h+pmtDest.formattype]; Buf1
0x18001446a  call    memcmp_0
0x18001446f  test    eax, eax
0x180014471  jnz     short loc_18001447D
0x180014473  cmp     r14d, 58h ; 'X'
0x180014477  jbe     loc_1800145D5
0x18001447d  mov     r8d, 10h; Size
  ... truncated ...
```
