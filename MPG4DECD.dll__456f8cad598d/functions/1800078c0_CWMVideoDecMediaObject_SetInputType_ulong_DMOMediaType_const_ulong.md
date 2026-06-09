# CWMVideoDecMediaObject::SetInputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x1800078c0`
- end: `0x180007fa7`
- name: `?SetInputType@CWMVideoDecMediaObject@@UEAAJKPEBU_DMOMediaType@@K@Z`
- size: `1767`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x180001450`
- `0x1800018b0`
- `0x180002174`
- `0x1800031f8`
- `0x1800035f4`
- `0x180003934`
- `0x180003bd0`
- `0x180003c70`
- `0x180006d68`
- `0x1800078c0`
- `0x1800088b8`
- `0x18000ab10`
- `0x180021005`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f78`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007f78`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007909`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007909`
- `msdmo!MoCopyMediaType` at `0x180007f13`
- `msdmo!MoCopyMediaType` at `0x180007f2e`
- `msdmo!MoCopyMediaType` at `0x180007f13`
- `msdmo!MoCopyMediaType` at `0x180007f2e`
- `msdmo!MoFreeMediaType` at `0x180007984`
- `msdmo!MoFreeMediaType` at `0x180007991`
- `msdmo!MoFreeMediaType` at `0x180007c52`
- `msdmo!MoFreeMediaType` at `0x180007ef9`
- `msdmo!MoFreeMediaType` at `0x180007f06`
- `msdmo!MoFreeMediaType` at `0x180007f6d`
- `msdmo!MoFreeMediaType` at `0x180007984`
- `msdmo!MoFreeMediaType` at `0x180007991`
- `msdmo!MoFreeMediaType` at `0x180007c52`
- `msdmo!MoFreeMediaType` at `0x180007ef9`
- `msdmo!MoFreeMediaType` at `0x180007f06`
- `msdmo!MoFreeMediaType` at `0x180007f6d`
- `msdmo!MoInitMediaType` at `0x180007aed`
- `msdmo!MoInitMediaType` at `0x180007aed`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::SetInputType(
        CWMVideoDecMediaObject *this,
        int a2,
        const struct _DMOMediaType *a3,
        char a4)
{
  struct SessionFrameDecoder *v8; // r12
  HRESULT v9; // ebx
  void *pbFormat; // r13
  int v11; // r14d
  unsigned __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // r8
  int v15; // r14d
  __int64 v16; // r11
  __int64 v17; // r10
  GUID v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm0
  int v22; // r14d
  __int64 v23; // rax
  __int64 v24; // r15
  int *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  unsigned int v28; // eax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r10
  __int64 v32; // r11
  unsigned int v33; // r14d
  __int64 v34; // rcx
  int v35; // r15d
  __int64 v36; // rcx
  unsigned int v37; // r15d
  bool v38; // zf
  int v39; // eax
  __int64 v40; // rbx
  double v41; // xmm1_8
  struct SessionFrameDecoder *Decoder; // rax
  __int64 v43; // rcx
  unsigned int v45; // [rsp+28h] [rbp-D8h]
  unsigned __int8 *v46; // [rsp+30h] [rbp-D0h]
  unsigned int v47; // [rsp+38h] [rbp-C8h]
  int v48; // [rsp+40h] [rbp-C0h]
  int v50; // [rsp+44h] [rbp-BCh]
  int v51; // [rsp+48h] [rbp-B8h]
  int v52; // [rsp+4Ch] [rbp-B4h]
  int v53; // [rsp+50h] [rbp-B0h]
  struct tagVIDEOINFOHEADER *v54; // [rsp+58h] [rbp-A8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+60h] [rbp-A0h]
  __int128 Buf1; // [rsp+70h] [rbp-90h] BYREF
  DMO_MEDIA_TYPE pmt; // [rsp+80h] [rbp-80h] BYREF
  DMO_MEDIA_TYPE pmtSrc; // [rsp+E0h] [rbp-20h] BYREF

  lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 200);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 5);
  v8 = 0;
  *((_QWORD *)this + 50) = -1000;
  *((_QWORD *)this + 51) = 0;
  v54 = 0;
  pmt.majortype.Data1 = 0;
  memset_0(&pmt.majortype.Data2, 0, 0x54u);
  pmtSrc.majortype.Data1 = 0;
  memset_0(&pmtSrc.majortype.Data2, 0, 0x54u);
  if ( a2 )
  {
    v9 = -2147220991;
    goto LABEL_117;
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
        MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 1592));
      }
      memset_0((char *)this + 1680, 0, 0xB0u);
      goto LABEL_117;
    }
LABEL_22:
    v9 = -2147467261;
    goto LABEL_117;
  }
  pbFormat = (void *)*((_QWORD *)a3 + 10);
  v11 = *((_DWORD *)a3 + 18);
  Buf1 = *(_OWORD *)((char *)a3 + 44);
  if ( (int)prvValidateMediaTypeSize(&Buf1) < 0 )
    goto LABEL_116;
  v9 = CheckType(a3, (const struct _GUID *const *)&off_180027010, 4u);
  if ( v9 < 0 )
    goto LABEL_117;
  v13 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  v14 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  v48 = 0;
  v52 = 0;
  v53 = 0;
  if ( *(_QWORD *)((char *)a3 + 44) != *(_QWORD *)&FORMAT_MFVideoFormat.Data1
    || *(_QWORD *)((char *)a3 + 52) != *(_QWORD *)FORMAT_MFVideoFormat.Data4 )
  {
    v16 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
    if ( *(_QWORD *)((char *)a3 + 44) == *(_QWORD *)&FORMAT_VideoInfo.Data1 )
    {
      v17 = *(_QWORD *)FORMAT_VideoInfo.Data4;
      if ( *(_QWORD *)((char *)a3 + 52) == *(_QWORD *)FORMAT_VideoInfo.Data4 )
      {
LABEL_27:
        v22 = *((_DWORD *)pbFormat + 13);
        if ( v22 <= 0 || *((int *)pbFormat + 14) <= 0 || v22 > 4096 || *((int *)pbFormat + 14) > 4096 )
          goto LABEL_44;
        if ( !*((_DWORD *)this + 3) || *(_QWORD *)((char *)this + 148) == v13 && *(_QWORD *)((char *)this + 156) == v14 )
        {
          v24 = *(_QWORD *)FORMAT_VideoInfo2.Data4;
        }
        else
        {
          if ( *(_QWORD *)((char *)this + 148) == v16 && *(_QWORD *)((char *)this + 156) == v17 )
          {
            v23 = *((_QWORD *)this + 23);
            v24 = *(_QWORD *)FORMAT_VideoInfo2.Data4;
            v25 = (int *)(v23 + 52);
            v12 = v23 + 56;
          }
          else
          {
            if ( *(_QWORD *)((char *)this + 148) != *(_QWORD *)&FORMAT_VideoInfo2.Data1 )
              goto LABEL_44;
            v24 = *(_QWORD *)FORMAT_VideoInfo2.Data4;
            if ( *(_QWORD *)((char *)this + 156) != *(_QWORD *)FORMAT_VideoInfo2.Data4 )
              goto LABEL_44;
            v26 = *((_QWORD *)this + 23);
            v25 = (int *)(v26 + 76);
            v12 = v26 + 80;
          }
          v27 = -*(_DWORD *)v12;
          if ( *(int *)v12 > 0 )
            v27 = *(_DWORD *)v12;
          if ( *((_DWORD *)pbFormat + 14) > v27 || v22 > *v25 )
            goto LABEL_44;
        }
        v28 = NeedHeader(*((unsigned int *)a3 + 4), v12, v14);
        v12 = v28;
        v33 = 176;
        if ( v28 )
        {
          if ( *(_QWORD *)((char *)a3 + 44) == v30
            && *(_QWORD *)((char *)a3 + 52) == v29
            && *((_DWORD *)a3 + 18) <= 0xB0u )
          {
            goto LABEL_44;
          }
          if ( *(_QWORD *)((char *)a3 + 44) == v32
            && *(_QWORD *)((char *)a3 + 52) == v31
            && *((_DWORD *)a3 + 18) <= 0x58u )
          {
            goto LABEL_44;
          }
          v34 = *(_QWORD *)&FORMAT_VideoInfo2.Data1;
          if ( *(_QWORD *)((char *)a3 + 44) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
            && *(_QWORD *)((char *)a3 + 52) == v24
            && *((_DWORD *)a3 + 18) <= 0x70u )
          {
            goto LABEL_44;
          }
        }
        else
        {
          v34 = *(_QWORD *)&FORMAT_VideoInfo2.Data1;
        }
        v35 = 0;
        v51 = 0;
        if ( *((_QWORD *)a3 + 2) == MEDIASUBTYPE_WMV3 && *((_QWORD *)a3 + 3) == 0x719B3800AA000080LL )
        {
          if ( *(_QWORD *)((char *)a3 + 44) == v30 && *(_QWORD *)((char *)a3 + 52) == v29 )
          {
            v36 = 176;
          }
          else if ( *(_QWORD *)((char *)a3 + 44) == v34
                 && *(_QWORD *)((char *)a3 + 52) == *(_QWORD *)FORMAT_VideoInfo2.Data4 )
          {
            v36 = 112;
          }
          else
          {
            if ( *(_QWORD *)((char *)a3 + 44) != v32 || *(_QWORD *)((char *)a3 + 52) != v31 )
              goto LABEL_79;
            v36 = 88;
          }
          v9 = 0;
          if ( (*(_BYTE *)(v36 + *((_QWORD *)a3 + 10)) & 0x20) != 0 )
            v35 = 1;
          v51 = v35;
        }
        v37 = *((_DWORD *)a3 + 18);
        if ( v37 > 0x400 )
          goto LABEL_44;
        v38 = (a4 & 1) == 0;
        v39 = a4 & 1;
        v50 = v39;
        if ( !v38 && *((_DWORD *)this + 3) )
        {
          v9 = 0;
          goto LABEL_45;
        }
        if ( !(_DWORD)v12 )
        {
LABEL_109:
          if ( !v39 )
          {
            v38 = *((_DWORD *)this + 2) == 0;
            v15 = v48;
            *((_DWORD *)this + 211) = v51;
            *((_DWORD *)this + 213) = v52;
            *((_DWORD *)this + 214) = v53;
            *((_DWORD *)this + 212) = v48;
            *((_DWORD *)this + 237) = 0;
            *((_DWORD *)this + 238) = 1;
            *(_QWORD *)((char *)this + 956) = 1;
            if ( !v38 )
            {
              *((_DWORD *)this + 2) = 0;
              MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 16));
              MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 1592));
            }
            v9 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 16), (const DMO_MEDIA_TYPE *)a3);
            if ( v9 >= 0 )
            {
              v9 = MoCopyMediaType((DMO_MEDIA_TYPE *)((char *)this + 1592), &pmtSrc);
              if ( v9 >= 0 )
              {
                *((_DWORD *)this + 69) = 0;
                CWMVideoDecMediaObject::DeinitDecoder((CWMVideoDecMediaObject *)((char *)this - 48));
                *((_DWORD *)this + 2) = 1;
              }
            }
            goto LABEL_46;
          }
          goto LABEL_45;
        }
        if ( *(_QWORD *)((char *)a3 + 44) == v30 && *(_QWORD *)((char *)a3 + 52) == v29 && v37 <= 0xB0
          || *(_QWORD *)((char *)a3 + 44) == v32 && *(_QWORD *)((char *)a3 + 52) == v31 && v37 <= 0x58
          || *(_QWORD *)((char *)a3 + 44) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
          && *(_QWORD *)((char *)a3 + 52) == *(_QWORD *)FORMAT_VideoInfo2.Data4
          && v37 <= 0x70 )
        {
LABEL_44:
          v9 = -2147220987;
LABEL_45:
          v15 = v48;
          goto LABEL_46;
        }
        if ( *(_QWORD *)((char *)a3 + 44) == v30 && *(_QWORD *)((char *)a3 + 52) == v29 )
        {
LABEL_102:
          v40 = *((_QWORD *)a3 + 10);
          if ( *((_QWORD *)pbFormat + 5) )
            v41 = 10000000.0 / (double)(int)*((_QWORD *)pbFormat + 5);
          else
            v41 = 0.0;
          Decoder = CWMVideoDecMediaObject::CreateDecoder(
                      *(CWMVideoDecMediaObject **)FORMAT_VideoInfo2.Data4,
                      *((_DWORD *)a3 + 4),
                      *((_DWORD *)pbFormat + 13),
                      *((_DWORD *)pbFormat + 14),
                      v41,
                      v45,
                      v46,
                      v47);
          v8 = Decoder;
          if ( Decoder )
          {
            if ( *((_QWORD *)Decoder + 3) )
            {
              v43 = *((_QWORD *)Decoder + 4);
              *(_QWORD *)v43 = v40 + v33;
              *(_QWORD *)(v43 + 12) = 0;
              *(_DWORD *)(v43 + 20) = 0;
              *(_DWORD *)(v43 + 8) = v37 - v33;
              v9 = CVideoObjectDecoder::decodeVOLHead(*((CVideoObjectDecoder **)Decoder + 3));
              if ( v9 >= 0 )
              {
                v39 = v50;
                goto LABEL_109;
              }
            }
          }
          goto LABEL_44;
        }
        if ( *(_QWORD *)((char *)a3 + 44) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
          && *(_QWORD *)((char *)a3 + 52) == *(_QWORD *)FORMAT_VideoInfo2.Data4 )
        {
          v33 = 112;
          goto LABEL_102;
        }
        if ( *(_QWORD *)((char *)a3 + 44) == v32 && *(_QWORD *)((char *)a3 + 52) == v31 )
        {
          v33 = 88;
          goto LABEL_102;
        }
LABEL_79:
        v9 = -2147467259;
        goto LABEL_45;
      }
    }
    if ( *(_QWORD *)((char *)a3 + 44) == *(_QWORD *)&FORMAT_VideoInfo2.Data1
      && *(_QWORD *)((char *)a3 + 52) == *(_QWORD *)FORMAT_VideoInfo2.Data4 )
    {
      if ( *(_QWORD *)((char *)a3 + 44) != *(_QWORD *)&FORMAT_VideoInfo2.Data1
        || *(_QWORD *)((char *)a3 + 52) != *(_QWORD *)FORMAT_VideoInfo2.Data4 )
      {
        v9 = -2147024809;
        goto LABEL_117;
      }
      v52 = *((_DWORD *)pbFormat + 14);
      v18 = (GUID)*((_OWORD *)a3 + 1);
      v53 = *((_DWORD *)pbFormat + 15);
      pmt.majortype = *(GUID *)a3;
      v19 = *((_OWORD *)a3 + 2);
      pmt.pbFormat = 0;
      pmt.subtype = v18;
      v20 = *((_OWORD *)a3 + 3);
      *(_OWORD *)&pmt.bFixedSizeSamples = v19;
      v21 = *((_OWORD *)a3 + 4);
      *((_DWORD *)&pmt.formattype + 4) = HIDWORD(v20);
      *(_OWORD *)&pmt.pUnk = v21;
      pmt.formattype = FORMAT_VideoInfo;
      MoInitMediaType(&pmt, v11 - 112 + 88);
      if ( !pmt.pbFormat )
        goto LABEL_22;
      ConvertVIH2ToVIH(*((struct tagVIDEOINFOHEADER2 **)a3 + 10), (struct tagVIDEOINFOHEADER *)pmt.pbFormat);
      if ( v11 != 112 )
        memcpy_0(pmt.pbFormat + 88, (const void *)(*((_QWORD *)a3 + 10) + 112LL), (unsigned int)(v11 - 112));
      pbFormat = pmt.pbFormat;
      v9 = 0;
      v48 = 1;
      goto LABEL_26;
    }
LABEL_116:
    v9 = -2147220987;
    goto LABEL_117;
  }
  v9 = ConvertMFVideoFormatToVIH2(&v54, (struct _MFVIDEOFORMAT *)pbFormat);
  if ( v9 >= 0 )
  {
    pbFormat = v54;
LABEL_26:
    v16 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
    v17 = *(_QWORD *)FORMAT_VideoInfo.Data4;
    v13 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
    v14 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
    goto LABEL_27;
  }
  v15 = 0;
LABEL_46:
  if ( v54 )
    operator delete(v54, v12);
  if ( v8 )
    (**(void (__fastcall ***)(struct SessionFrameDecoder *, __int64))v8)(v8, 1);
  if ( v15 )
    MoFreeMediaType(&pmt);
LABEL_117:
  MoFreeMediaType(&pmtSrc);
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800078c0  mov     [rsp-8+arg_8], rbx
0x1800078c5  push    rbp
0x1800078c6  push    rsi
0x1800078c7  push    rdi
0x1800078c8  push    r12
0x1800078ca  push    r13
0x1800078cc  push    r14
0x1800078ce  push    r15
0x1800078d0  lea     rbp, [rsp-50h]
0x1800078d5  sub     rsp, 150h
0x1800078dc  mov     rax, cs:__security_cookie
0x1800078e3  xor     rax, rsp
0x1800078e6  mov     [rbp+80h+var_40], rax
0x1800078ea  lea     rax, [rcx+0C8h]
0x1800078f1  mov     [rsp+180h+var_13C], r9d
0x1800078f6  mov     rsi, rcx
0x1800078f9  mov     [rsp+180h+lpCriticalSection], rax
0x1800078fe  mov     rcx, rax; lpCriticalSection
0x180007901  mov     r14d, r9d
0x180007904  mov     rdi, r8
0x180007907  mov     ebx, edx
0x180007909  call    cs:__imp_EnterCriticalSection
0x18000790f  xor     r12d, r12d
0x180007912  mov     qword ptr [rsi+190h], 0FFFFFFFFFFFFFC18h
0x18000791d  xor     edx, edx; Val
0x18000791f  mov     [rsi+198h], r12
0x180007926  lea     rcx, [rbp+80h+pmt.majortype.Data2]; void *
0x18000792a  mov     [rsp+180h+var_128], r12
0x18000792f  mov     [rbp+80h+pmt.majortype.Data1], r12d
0x180007933  lea     r15d, [r12+54h]
0x180007938  mov     r8d, r15d; Size
0x18000793b  call    memset_0
0x180007940  mov     r8d, r15d; Size
0x180007943  mov     [rbp+80h+pmtSrc.majortype.Data1], r12d
0x180007947  xor     edx, edx; Val
0x180007949  lea     rcx, [rbp+80h+pmtSrc.majortype.Data2]; void *
0x18000794d  call    memset_0
0x180007952  cmp     ebx, 1
0x180007955  jb      short loc_180007961
0x180007957  mov     ebx, 80040201h
0x18000795c  jmp     loc_180007F69
0x180007961  xor     r15d, r15d
0x180007964  test    rdi, rdi
0x180007967  jnz     short loc_1800079B0
0x180007969  test    r14b, 2
0x18000796d  jz      loc_180007AFC
0x180007973  mov     ebx, r15d
0x180007976  cmp     [rsi+8], r15d
0x18000797a  jz      short loc_180007997
0x18000797c  lea     rcx, [rsi+10h]; pmt
0x180007980  mov     [rsi+8], r15d
0x180007984  call    cs:__imp_MoFreeMediaType
0x18000798a  lea     rcx, [rsi+638h]; pmt
0x180007991  call    cs:__imp_MoFreeMediaType
0x180007997  lea     rcx, [rsi+690h]; void *
0x18000799e  xor     edx, edx; Val
0x1800079a0  mov     r8d, 0B0h; Size
0x1800079a6  call    memset_0
0x1800079ab  jmp     loc_180007F69
0x1800079b0  movups  xmm0, xmmword ptr [rdi+2Ch]
0x1800079b4  mov     r13, [rdi+50h]
0x1800079b8  lea     rcx, [rsp+180h+Buf1]; Buf1
0x1800079bd  mov     r14d, [rdi+48h]
0x1800079c1  mov     rdx, r13
0x1800079c4  mov     r8d, r14d
0x1800079c7  movdqu  [rsp+180h+Buf1], xmm0
0x1800079cd  call    prvValidateMediaTypeSize
0x1800079d2  test    eax, eax
0x1800079d4  js      loc_180007F64
0x1800079da  mov     r8d, 4; unsigned int
0x1800079e0  lea     rdx, off_180027010; struct _GUID **
0x1800079e7  mov     rcx, rdi; struct _DMOMediaType *
0x1800079ea  call    ?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_DMOMediaType const *,_GUID const * const *,uint)
0x1800079ef  mov     ebx, eax
0x1800079f1  test    eax, eax
0x1800079f3  js      loc_180007F69
0x1800079f9  mov     r9, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180007a00  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180007a07  mov     [rsp+180h+var_140], r15d
0x180007a0c  mov     [rsp+180h+var_134], r15d
0x180007a11  mov     [rsp+180h+var_130], r15d
0x180007a16  cmp     [rdi+2Ch], r9
0x180007a1a  jnz     short loc_180007A47
0x180007a1c  cmp     [rdi+34h], r8
0x180007a20  jnz     short loc_180007A47
0x180007a22  mov     rdx, r13; struct _MFVIDEOFORMAT *
0x180007a25  lea     rcx, [rsp+180h+var_128]; struct tagVIDEOINFOHEADER **
0x180007a2a  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x180007a2f  mov     ebx, eax
0x180007a31  test    eax, eax
0x180007a33  js      short loc_180007A3F
0x180007a35  mov     r13, [rsp+180h+var_128]
0x180007a3a  jmp     loc_180007B3A
0x180007a3f  mov     r14d, r12d
0x180007a42  jmp     loc_180007C1A
0x180007a47  mov     r11, qword ptr cs:FORMAT_VideoInfo.Data1
0x180007a4e  cmp     [rdi+2Ch], r11
0x180007a52  jnz     short loc_180007A65
0x180007a54  mov     r10, qword ptr cs:FORMAT_VideoInfo.Data4
0x180007a5b  cmp     [rdi+34h], r10
0x180007a5f  jz      loc_180007B56
0x180007a65  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180007a6c  cmp     [rdi+2Ch], rax
0x180007a70  jnz     loc_180007F64
0x180007a76  mov     rcx, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007a7d  cmp     [rdi+34h], rcx
0x180007a81  jnz     loc_180007F64
0x180007a87  cmp     [rdi+2Ch], rax
0x180007a8b  jnz     loc_180007F5D
0x180007a91  cmp     [rdi+34h], rcx
0x180007a95  jnz     loc_180007F5D
0x180007a9b  mov     eax, [r13+38h]
0x180007a9f  lea     ebx, [r14-70h]
0x180007aa3  movups  xmm0, xmmword ptr [rdi]
0x180007aa6  mov     [rsp+180h+var_134], eax
0x180007aaa  lea     edx, [rbx+58h]; cbFormat
0x180007aad  mov     eax, [r13+3Ch]
0x180007ab1  lea     rcx, [rbp+80h+pmt]; pmt
0x180007ab5  movups  xmm1, xmmword ptr [rdi+10h]
0x180007ab9  mov     [rsp+180h+var_130], eax
0x180007abd  movaps  xmmword ptr [rbp+80h+pmt.majortype.Data1], xmm0
0x180007ac1  movups  xmm0, xmmword ptr [rdi+20h]
0x180007ac5  mov     [rbp+80h+pmt.pbFormat], r15
0x180007ac9  movaps  xmmword ptr [rbp+80h+pmt.subtype.Data1], xmm1
0x180007acd  movups  xmm1, xmmword ptr [rdi+30h]
0x180007ad1  movaps  xmmword ptr [rbp+80h+pmt.bFixedSizeSamples], xmm0
0x180007ad5  movups  xmm0, xmmword ptr [rdi+40h]
0x180007ad9  movaps  xmmword ptr [rbp+80h+pmt.formattype.Data2], xmm1
0x180007add  movaps  xmmword ptr [rbp+80h+pmt.pUnk], xmm0
0x180007ae1  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180007ae8  movdqu  xmmword ptr [rbp+80h+pmt.formattype.Data1], xmm0
0x180007aed  call    cs:__imp_MoInitMediaType
0x180007af3  mov     rdx, [rbp+80h+pmt.pbFormat]; struct tagVIDEOINFOHEADER *
0x180007af7  test    rdx, rdx
0x180007afa  jnz     short loc_180007B06
0x180007afc  mov     ebx, 80004003h
0x180007b01  jmp     loc_180007F69
0x180007b06  mov     rcx, [rdi+50h]; struct tagVIDEOINFOHEADER2 *
0x180007b0a  call    ?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)
0x180007b0f  test    ebx, ebx
0x180007b11  jz      short loc_180007B2B
0x180007b13  mov     rdx, [rdi+50h]
0x180007b17  mov     rcx, [rbp+80h+pmt.pbFormat]
0x180007b1b  add     rdx, 70h ; 'p'; Src
0x180007b1f  add     rcx, 58h ; 'X'; void *
0x180007b23  mov     r8d, ebx; Size
0x180007b26  call    memcpy_0
0x180007b2b  mov     r13, [rbp+80h+pmt.pbFormat]
0x180007b2f  mov     ebx, r15d
0x180007b32  mov     [rsp+180h+var_140], 1
0x180007b3a  mov     r11, qword ptr cs:FORMAT_VideoInfo.Data1
0x180007b41  mov     r10, qword ptr cs:FORMAT_VideoInfo.Data4
0x180007b48  mov     r9, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180007b4f  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180007b56  mov     r14d, [r13+34h]
0x180007b5a  test    r14d, r14d
0x180007b5d  jle     loc_180007C10
0x180007b63  cmp     [r13+38h], r15d
0x180007b67  jle     loc_180007C10
0x180007b6d  mov     eax, 1000h
0x180007b72  cmp     r14d, eax
0x180007b75  jg      loc_180007C10
0x180007b7b  cmp     [r13+38h], eax
0x180007b7f  jg      loc_180007C10
0x180007b85  cmp     [rsi+0Ch], r15d
0x180007b89  jz      loc_180007C5D
0x180007b8f  cmp     [rsi+94h], r9
0x180007b96  jnz     short loc_180007BA5
0x180007b98  cmp     [rsi+9Ch], r8
0x180007b9f  jz      loc_180007C5D
0x180007ba5  cmp     [rsi+94h], r11
0x180007bac  jnz     short loc_180007BCF
0x180007bae  cmp     [rsi+9Ch], r10
0x180007bb5  jnz     short loc_180007BCF
0x180007bb7  mov     rax, [rsi+0B8h]
0x180007bbe  mov     r15, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007bc5  lea     rcx, [rax+34h]
0x180007bc9  lea     rdx, [rax+38h]
0x180007bcd  jmp     short loc_180007BFE
0x180007bcf  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180007bd6  cmp     [rsi+94h], rax
0x180007bdd  jnz     short loc_180007C10
0x180007bdf  mov     r15, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007be6  cmp     [rsi+9Ch], r15
0x180007bed  jnz     short loc_180007C10
0x180007bef  mov     rax, [rsi+0B8h]
0x180007bf6  lea     rcx, [rax+4Ch]
0x180007bfa  lea     rdx, [rax+50h]; unsigned __int64
0x180007bfe  mov     eax, [rdx]
0x180007c00  neg     eax
0x180007c02  cmovs   eax, [rdx]
0x180007c05  cmp     [r13+38h], eax
0x180007c09  jg      short loc_180007C10
0x180007c0b  cmp     r14d, [rcx]
0x180007c0e  jle     short loc_180007C64
0x180007c10  mov     ebx, 80040205h
0x180007c15  mov     r14d, [rsp+180h+var_140]
0x180007c1a  mov     rax, [rsp+180h+var_128]
0x180007c1f  test    rax, rax
0x180007c22  jz      short loc_180007C2C
0x180007c24  mov     rcx, rax; void *
0x180007c27  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007c2c  test    r12, r12
0x180007c2f  jz      short loc_180007C45
0x180007c31  mov     rax, [r12]
0x180007c35  mov     edx, 1
0x180007c3a  mov     rcx, r12
0x180007c3d  mov     rax, [rax]
0x180007c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c45  test    r14d, r14d
0x180007c48  jz      loc_180007F69
0x180007c4e  lea     rcx, [rbp+80h+pmt]; pmt
0x180007c52  call    cs:__imp_MoFreeMediaType
0x180007c58  jmp     loc_180007F69
0x180007c5d  mov     r15, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007c64  mov     ecx, [rdi+10h]
0x180007c67  call    NeedHeader
0x180007c6c  mov     edx, eax
0x180007c6e  mov     r14d, 0B0h
0x180007c74  test    eax, eax
0x180007c76  jz      short loc_180007CBE
0x180007c78  cmp     [rdi+2Ch], r9
0x180007c7c  jnz     short loc_180007C8A
0x180007c7e  cmp     [rdi+34h], r8
0x180007c82  jnz     short loc_180007C8A
0x180007c84  cmp     [rdi+48h], r14d
0x180007c88  jbe     short loc_180007C10
0x180007c8a  cmp     [rdi+2Ch], r11
0x180007c8e  jnz     short loc_180007CA0
0x180007c90  cmp     [rdi+34h], r10
0x180007c94  jnz     short loc_180007CA0
0x180007c96  cmp     dword ptr [rdi+48h], 58h ; 'X'
0x180007c9a  jbe     loc_180007C10
0x180007ca0  mov     rcx, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180007ca7  cmp     [rdi+2Ch], rcx
0x180007cab  jnz     short loc_180007CC5
0x180007cad  cmp     [rdi+34h], r15
0x180007cb1  jnz     short loc_180007CC5
0x180007cb3  cmp     dword ptr [rdi+48h], 70h ; 'p'
0x180007cb7  ja      short loc_180007CC5
0x180007cb9  jmp     loc_180007C10
0x180007cbe  mov     rcx, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180007cc5  mov     rax, [rdi+10h]
0x180007cc9  xor     r15d, r15d
0x180007ccc  cmp     rax, cs:MEDIASUBTYPE_WMV3
0x180007cd3  mov     [rsp+180h+var_138], r15d
0x180007cd8  jnz     short loc_180007D45
0x180007cda  mov     rax, [rdi+18h]
0x180007cde  cmp     rax, cs:qword_1800241B8
0x180007ce5  jnz     short loc_180007D45
0x180007ce7  cmp     [rdi+2Ch], r9
0x180007ceb  jnz     short loc_180007CF8
0x180007ced  cmp     [rdi+34h], r8
0x180007cf1  jnz     short loc_180007CF8
0x180007cf3  mov     rcx, r14
0x180007cf6  jmp     short loc_180007D23
0x180007cf8  cmp     [rdi+2Ch], rcx
0x180007cfc  jnz     short loc_180007D12
0x180007cfe  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007d05  cmp     [rdi+34h], rax
0x180007d09  jnz     short loc_180007D12
0x180007d0b  mov     ecx, 70h ; 'p'
0x180007d10  jmp     short loc_180007D23
0x180007d12  cmp     [rdi+2Ch], r11
0x180007d16  jnz     short loc_180007D3B
0x180007d18  cmp     [rdi+34h], r10
0x180007d1c  jnz     short loc_180007D3B
0x180007d1e  mov     ecx, 58h ; 'X'
0x180007d23  mov     rax, [rdi+50h]
0x180007d27  xor     ebx, ebx
0x180007d29  test    byte ptr [rcx+rax], 20h
0x180007d2d  lea     ecx, [rbx+1]
0x180007d30  cmovnz  r15d, ecx
0x180007d34  mov     [rsp+180h+var_138], r15d
0x180007d39  jmp     short loc_180007D4A
0x180007d3b  mov     ebx, 80004005h
0x180007d40  jmp     loc_180007C15
0x180007d45  mov     ecx, 1
0x180007d4a  mov     r15d, [rdi+48h]
0x180007d4e  cmp     r15d, 400h
0x180007d55  ja      loc_180007C10
0x180007d5b  mov     eax, [rsp+180h+var_13C]
0x180007d5f  and     eax, ecx
0x180007d61  mov     [rsp+180h+var_13C], eax
0x180007d65  jz      short loc_180007D74
0x180007d67  cmp     [rsi+0Ch], r12d
0x180007d6b  jz      short loc_180007D74
0x180007d6d  xor     ebx, ebx
0x180007d6f  jmp     loc_180007C15
0x180007d74  test    edx, edx
0x180007d76  jz      loc_180007E90
0x180007d7c  cmp     [rdi+2Ch], r9
0x180007d80  jnz     short loc_180007D91
0x180007d82  cmp     [rdi+34h], r8
0x180007d86  jnz     short loc_180007D91
0x180007d88  cmp     r15d, r14d
0x180007d8b  jbe     loc_180007C10
0x180007d91  cmp     [rdi+2Ch], r11
0x180007d95  jnz     short loc_180007DA7
0x180007d97  cmp     [rdi+34h], r10
  ... truncated ...
```
