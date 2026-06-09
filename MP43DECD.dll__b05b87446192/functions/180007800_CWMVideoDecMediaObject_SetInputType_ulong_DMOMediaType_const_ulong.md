# CWMVideoDecMediaObject::SetInputType(ulong,_DMOMediaType const *,ulong)

- ea: `0x180007800`
- end: `0x180007ee7`
- name: `?SetInputType@CWMVideoDecMediaObject@@UEAAJKPEBU_DMOMediaType@@K@Z`
- size: `1767`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *this, int, const struct _DMOMediaType *, char)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops`

## callees

- `0x180001420`
- `0x180001880`
- `0x180002144`
- `0x180003138`
- `0x180003534`
- `0x180003874`
- `0x180003b10`
- `0x180003bb0`
- `0x180006ca8`
- `0x180007800`
- `0x1800087f8`
- `0x18000aa50`
- `0x180020f45`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007eb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007eb8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007849`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007849`
- `msdmo!MoCopyMediaType` at `0x180007e53`
- `msdmo!MoCopyMediaType` at `0x180007e6e`
- `msdmo!MoCopyMediaType` at `0x180007e53`
- `msdmo!MoCopyMediaType` at `0x180007e6e`
- `msdmo!MoFreeMediaType` at `0x1800078c4`
- `msdmo!MoFreeMediaType` at `0x1800078d1`
- `msdmo!MoFreeMediaType` at `0x180007b92`
- `msdmo!MoFreeMediaType` at `0x180007e39`
- `msdmo!MoFreeMediaType` at `0x180007e46`
- `msdmo!MoFreeMediaType` at `0x180007ead`
- `msdmo!MoFreeMediaType` at `0x1800078c4`
- `msdmo!MoFreeMediaType` at `0x1800078d1`
- `msdmo!MoFreeMediaType` at `0x180007b92`
- `msdmo!MoFreeMediaType` at `0x180007e39`
- `msdmo!MoFreeMediaType` at `0x180007e46`
- `msdmo!MoFreeMediaType` at `0x180007ead`
- `msdmo!MoInitMediaType` at `0x180007a2d`
- `msdmo!MoInitMediaType` at `0x180007a2d`

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
  v9 = CheckType(a3, (const struct _GUID *const *)&off_180027010, 2u);
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
0x180007800  mov     [rsp-8+arg_8], rbx
0x180007805  push    rbp
0x180007806  push    rsi
0x180007807  push    rdi
0x180007808  push    r12
0x18000780a  push    r13
0x18000780c  push    r14
0x18000780e  push    r15
0x180007810  lea     rbp, [rsp-50h]
0x180007815  sub     rsp, 150h
0x18000781c  mov     rax, cs:__security_cookie
0x180007823  xor     rax, rsp
0x180007826  mov     [rbp+80h+var_40], rax
0x18000782a  lea     rax, [rcx+0C8h]
0x180007831  mov     [rsp+180h+var_13C], r9d
0x180007836  mov     rsi, rcx
0x180007839  mov     [rsp+180h+lpCriticalSection], rax
0x18000783e  mov     rcx, rax; lpCriticalSection
0x180007841  mov     r14d, r9d
0x180007844  mov     rdi, r8
0x180007847  mov     ebx, edx
0x180007849  call    cs:__imp_EnterCriticalSection
0x18000784f  xor     r12d, r12d
0x180007852  mov     qword ptr [rsi+190h], 0FFFFFFFFFFFFFC18h
0x18000785d  xor     edx, edx; Val
0x18000785f  mov     [rsi+198h], r12
0x180007866  lea     rcx, [rbp+80h+pmt.majortype.Data2]; void *
0x18000786a  mov     [rsp+180h+var_128], r12
0x18000786f  mov     [rbp+80h+pmt.majortype.Data1], r12d
0x180007873  lea     r15d, [r12+54h]
0x180007878  mov     r8d, r15d; Size
0x18000787b  call    memset_0
0x180007880  mov     r8d, r15d; Size
0x180007883  mov     [rbp+80h+pmtSrc.majortype.Data1], r12d
0x180007887  xor     edx, edx; Val
0x180007889  lea     rcx, [rbp+80h+pmtSrc.majortype.Data2]; void *
0x18000788d  call    memset_0
0x180007892  cmp     ebx, 1
0x180007895  jb      short loc_1800078A1
0x180007897  mov     ebx, 80040201h
0x18000789c  jmp     loc_180007EA9
0x1800078a1  xor     r15d, r15d
0x1800078a4  test    rdi, rdi
0x1800078a7  jnz     short loc_1800078F0
0x1800078a9  test    r14b, 2
0x1800078ad  jz      loc_180007A3C
0x1800078b3  mov     ebx, r15d
0x1800078b6  cmp     [rsi+8], r15d
0x1800078ba  jz      short loc_1800078D7
0x1800078bc  lea     rcx, [rsi+10h]; pmt
0x1800078c0  mov     [rsi+8], r15d
0x1800078c4  call    cs:__imp_MoFreeMediaType
0x1800078ca  lea     rcx, [rsi+638h]; pmt
0x1800078d1  call    cs:__imp_MoFreeMediaType
0x1800078d7  lea     rcx, [rsi+690h]; void *
0x1800078de  xor     edx, edx; Val
0x1800078e0  mov     r8d, 0B0h; Size
0x1800078e6  call    memset_0
0x1800078eb  jmp     loc_180007EA9
0x1800078f0  movups  xmm0, xmmword ptr [rdi+2Ch]
0x1800078f4  mov     r13, [rdi+50h]
0x1800078f8  lea     rcx, [rsp+180h+Buf1]; Buf1
0x1800078fd  mov     r14d, [rdi+48h]
0x180007901  mov     rdx, r13
0x180007904  mov     r8d, r14d
0x180007907  movdqu  [rsp+180h+Buf1], xmm0
0x18000790d  call    prvValidateMediaTypeSize
0x180007912  test    eax, eax
0x180007914  js      loc_180007EA4
0x18000791a  mov     r8d, 2; unsigned int
0x180007920  lea     rdx, off_180027010; struct _GUID **
0x180007927  mov     rcx, rdi; struct _DMOMediaType *
0x18000792a  call    ?CheckType@@YAJPEBU_DMOMediaType@@PEBQEBU_GUID@@I@Z; CheckType(_DMOMediaType const *,_GUID const * const *,uint)
0x18000792f  mov     ebx, eax
0x180007931  test    eax, eax
0x180007933  js      loc_180007EA9
0x180007939  mov     r9, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180007940  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180007947  mov     [rsp+180h+var_140], r15d
0x18000794c  mov     [rsp+180h+var_134], r15d
0x180007951  mov     [rsp+180h+var_130], r15d
0x180007956  cmp     [rdi+2Ch], r9
0x18000795a  jnz     short loc_180007987
0x18000795c  cmp     [rdi+34h], r8
0x180007960  jnz     short loc_180007987
0x180007962  mov     rdx, r13; struct _MFVIDEOFORMAT *
0x180007965  lea     rcx, [rsp+180h+var_128]; struct tagVIDEOINFOHEADER **
0x18000796a  call    ?ConvertMFVideoFormatToVIH2@@YAJPEAPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH2(tagVIDEOINFOHEADER * *,_MFVIDEOFORMAT *)
0x18000796f  mov     ebx, eax
0x180007971  test    eax, eax
0x180007973  js      short loc_18000797F
0x180007975  mov     r13, [rsp+180h+var_128]
0x18000797a  jmp     loc_180007A7A
0x18000797f  mov     r14d, r12d
0x180007982  jmp     loc_180007B5A
0x180007987  mov     r11, qword ptr cs:FORMAT_VideoInfo.Data1
0x18000798e  cmp     [rdi+2Ch], r11
0x180007992  jnz     short loc_1800079A5
0x180007994  mov     r10, qword ptr cs:FORMAT_VideoInfo.Data4
0x18000799b  cmp     [rdi+34h], r10
0x18000799f  jz      loc_180007A96
0x1800079a5  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x1800079ac  cmp     [rdi+2Ch], rax
0x1800079b0  jnz     loc_180007EA4
0x1800079b6  mov     rcx, qword ptr cs:FORMAT_VideoInfo2.Data4
0x1800079bd  cmp     [rdi+34h], rcx
0x1800079c1  jnz     loc_180007EA4
0x1800079c7  cmp     [rdi+2Ch], rax
0x1800079cb  jnz     loc_180007E9D
0x1800079d1  cmp     [rdi+34h], rcx
0x1800079d5  jnz     loc_180007E9D
0x1800079db  mov     eax, [r13+38h]
0x1800079df  lea     ebx, [r14-70h]
0x1800079e3  movups  xmm0, xmmword ptr [rdi]
0x1800079e6  mov     [rsp+180h+var_134], eax
0x1800079ea  lea     edx, [rbx+58h]; cbFormat
0x1800079ed  mov     eax, [r13+3Ch]
0x1800079f1  lea     rcx, [rbp+80h+pmt]; pmt
0x1800079f5  movups  xmm1, xmmword ptr [rdi+10h]
0x1800079f9  mov     [rsp+180h+var_130], eax
0x1800079fd  movaps  xmmword ptr [rbp+80h+pmt.majortype.Data1], xmm0
0x180007a01  movups  xmm0, xmmword ptr [rdi+20h]
0x180007a05  mov     [rbp+80h+pmt.pbFormat], r15
0x180007a09  movaps  xmmword ptr [rbp+80h+pmt.subtype.Data1], xmm1
0x180007a0d  movups  xmm1, xmmword ptr [rdi+30h]
0x180007a11  movaps  xmmword ptr [rbp+80h+pmt.bFixedSizeSamples], xmm0
0x180007a15  movups  xmm0, xmmword ptr [rdi+40h]
0x180007a19  movaps  xmmword ptr [rbp+80h+pmt.formattype.Data2], xmm1
0x180007a1d  movaps  xmmword ptr [rbp+80h+pmt.pUnk], xmm0
0x180007a21  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180007a28  movdqu  xmmword ptr [rbp+80h+pmt.formattype.Data1], xmm0
0x180007a2d  call    cs:__imp_MoInitMediaType
0x180007a33  mov     rdx, [rbp+80h+pmt.pbFormat]; struct tagVIDEOINFOHEADER *
0x180007a37  test    rdx, rdx
0x180007a3a  jnz     short loc_180007A46
0x180007a3c  mov     ebx, 80004003h
0x180007a41  jmp     loc_180007EA9
0x180007a46  mov     rcx, [rdi+50h]; struct tagVIDEOINFOHEADER2 *
0x180007a4a  call    ?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)
0x180007a4f  test    ebx, ebx
0x180007a51  jz      short loc_180007A6B
0x180007a53  mov     rdx, [rdi+50h]
0x180007a57  mov     rcx, [rbp+80h+pmt.pbFormat]
0x180007a5b  add     rdx, 70h ; 'p'; Src
0x180007a5f  add     rcx, 58h ; 'X'; void *
0x180007a63  mov     r8d, ebx; Size
0x180007a66  call    memcpy_0
0x180007a6b  mov     r13, [rbp+80h+pmt.pbFormat]
0x180007a6f  mov     ebx, r15d
0x180007a72  mov     [rsp+180h+var_140], 1
0x180007a7a  mov     r11, qword ptr cs:FORMAT_VideoInfo.Data1
0x180007a81  mov     r10, qword ptr cs:FORMAT_VideoInfo.Data4
0x180007a88  mov     r9, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180007a8f  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180007a96  mov     r14d, [r13+34h]
0x180007a9a  test    r14d, r14d
0x180007a9d  jle     loc_180007B50
0x180007aa3  cmp     [r13+38h], r15d
0x180007aa7  jle     loc_180007B50
0x180007aad  mov     eax, 1000h
0x180007ab2  cmp     r14d, eax
0x180007ab5  jg      loc_180007B50
0x180007abb  cmp     [r13+38h], eax
0x180007abf  jg      loc_180007B50
0x180007ac5  cmp     [rsi+0Ch], r15d
0x180007ac9  jz      loc_180007B9D
0x180007acf  cmp     [rsi+94h], r9
0x180007ad6  jnz     short loc_180007AE5
0x180007ad8  cmp     [rsi+9Ch], r8
0x180007adf  jz      loc_180007B9D
0x180007ae5  cmp     [rsi+94h], r11
0x180007aec  jnz     short loc_180007B0F
0x180007aee  cmp     [rsi+9Ch], r10
0x180007af5  jnz     short loc_180007B0F
0x180007af7  mov     rax, [rsi+0B8h]
0x180007afe  mov     r15, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007b05  lea     rcx, [rax+34h]
0x180007b09  lea     rdx, [rax+38h]
0x180007b0d  jmp     short loc_180007B3E
0x180007b0f  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180007b16  cmp     [rsi+94h], rax
0x180007b1d  jnz     short loc_180007B50
0x180007b1f  mov     r15, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007b26  cmp     [rsi+9Ch], r15
0x180007b2d  jnz     short loc_180007B50
0x180007b2f  mov     rax, [rsi+0B8h]
0x180007b36  lea     rcx, [rax+4Ch]
0x180007b3a  lea     rdx, [rax+50h]; unsigned __int64
0x180007b3e  mov     eax, [rdx]
0x180007b40  neg     eax
0x180007b42  cmovs   eax, [rdx]
0x180007b45  cmp     [r13+38h], eax
0x180007b49  jg      short loc_180007B50
0x180007b4b  cmp     r14d, [rcx]
0x180007b4e  jle     short loc_180007BA4
0x180007b50  mov     ebx, 80040205h
0x180007b55  mov     r14d, [rsp+180h+var_140]
0x180007b5a  mov     rax, [rsp+180h+var_128]
0x180007b5f  test    rax, rax
0x180007b62  jz      short loc_180007B6C
0x180007b64  mov     rcx, rax; void *
0x180007b67  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180007b6c  test    r12, r12
0x180007b6f  jz      short loc_180007B85
0x180007b71  mov     rax, [r12]
0x180007b75  mov     edx, 1
0x180007b7a  mov     rcx, r12
0x180007b7d  mov     rax, [rax]
0x180007b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b85  test    r14d, r14d
0x180007b88  jz      loc_180007EA9
0x180007b8e  lea     rcx, [rbp+80h+pmt]; pmt
0x180007b92  call    cs:__imp_MoFreeMediaType
0x180007b98  jmp     loc_180007EA9
0x180007b9d  mov     r15, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007ba4  mov     ecx, [rdi+10h]
0x180007ba7  call    NeedHeader
0x180007bac  mov     edx, eax
0x180007bae  mov     r14d, 0B0h
0x180007bb4  test    eax, eax
0x180007bb6  jz      short loc_180007BFE
0x180007bb8  cmp     [rdi+2Ch], r9
0x180007bbc  jnz     short loc_180007BCA
0x180007bbe  cmp     [rdi+34h], r8
0x180007bc2  jnz     short loc_180007BCA
0x180007bc4  cmp     [rdi+48h], r14d
0x180007bc8  jbe     short loc_180007B50
0x180007bca  cmp     [rdi+2Ch], r11
0x180007bce  jnz     short loc_180007BE0
0x180007bd0  cmp     [rdi+34h], r10
0x180007bd4  jnz     short loc_180007BE0
0x180007bd6  cmp     dword ptr [rdi+48h], 58h ; 'X'
0x180007bda  jbe     loc_180007B50
0x180007be0  mov     rcx, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180007be7  cmp     [rdi+2Ch], rcx
0x180007beb  jnz     short loc_180007C05
0x180007bed  cmp     [rdi+34h], r15
0x180007bf1  jnz     short loc_180007C05
0x180007bf3  cmp     dword ptr [rdi+48h], 70h ; 'p'
0x180007bf7  ja      short loc_180007C05
0x180007bf9  jmp     loc_180007B50
0x180007bfe  mov     rcx, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180007c05  mov     rax, [rdi+10h]
0x180007c09  xor     r15d, r15d
0x180007c0c  cmp     rax, cs:MEDIASUBTYPE_WMV3
0x180007c13  mov     [rsp+180h+var_138], r15d
0x180007c18  jnz     short loc_180007C85
0x180007c1a  mov     rax, [rdi+18h]
0x180007c1e  cmp     rax, cs:qword_1800241C8
0x180007c25  jnz     short loc_180007C85
0x180007c27  cmp     [rdi+2Ch], r9
0x180007c2b  jnz     short loc_180007C38
0x180007c2d  cmp     [rdi+34h], r8
0x180007c31  jnz     short loc_180007C38
0x180007c33  mov     rcx, r14
0x180007c36  jmp     short loc_180007C63
0x180007c38  cmp     [rdi+2Ch], rcx
0x180007c3c  jnz     short loc_180007C52
0x180007c3e  mov     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180007c45  cmp     [rdi+34h], rax
0x180007c49  jnz     short loc_180007C52
0x180007c4b  mov     ecx, 70h ; 'p'
0x180007c50  jmp     short loc_180007C63
0x180007c52  cmp     [rdi+2Ch], r11
0x180007c56  jnz     short loc_180007C7B
0x180007c58  cmp     [rdi+34h], r10
0x180007c5c  jnz     short loc_180007C7B
0x180007c5e  mov     ecx, 58h ; 'X'
0x180007c63  mov     rax, [rdi+50h]
0x180007c67  xor     ebx, ebx
0x180007c69  test    byte ptr [rcx+rax], 20h
0x180007c6d  lea     ecx, [rbx+1]
0x180007c70  cmovnz  r15d, ecx
0x180007c74  mov     [rsp+180h+var_138], r15d
0x180007c79  jmp     short loc_180007C8A
0x180007c7b  mov     ebx, 80004005h
0x180007c80  jmp     loc_180007B55
0x180007c85  mov     ecx, 1
0x180007c8a  mov     r15d, [rdi+48h]
0x180007c8e  cmp     r15d, 400h
0x180007c95  ja      loc_180007B50
0x180007c9b  mov     eax, [rsp+180h+var_13C]
0x180007c9f  and     eax, ecx
0x180007ca1  mov     [rsp+180h+var_13C], eax
0x180007ca5  jz      short loc_180007CB4
0x180007ca7  cmp     [rsi+0Ch], r12d
0x180007cab  jz      short loc_180007CB4
0x180007cad  xor     ebx, ebx
0x180007caf  jmp     loc_180007B55
0x180007cb4  test    edx, edx
0x180007cb6  jz      loc_180007DD0
0x180007cbc  cmp     [rdi+2Ch], r9
0x180007cc0  jnz     short loc_180007CD1
0x180007cc2  cmp     [rdi+34h], r8
0x180007cc6  jnz     short loc_180007CD1
0x180007cc8  cmp     r15d, r14d
0x180007ccb  jbe     loc_180007B50
0x180007cd1  cmp     [rdi+2Ch], r11
0x180007cd5  jnz     short loc_180007CE7
0x180007cd7  cmp     [rdi+34h], r10
  ... truncated ...
```
