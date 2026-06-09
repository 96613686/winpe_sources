# CWMVideoDecMediaObject::InitDecoderUsingSetTypes(void)

- ea: `0x1800149ac`
- end: `0x180014e73`
- name: `?InitDecoderUsingSetTypes@CWMVideoDecMediaObject@@AEAAJXZ`
- size: `1223`
- prototype: `__int64 __fastcall(CWMVideoDecMediaObject *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18002ba80`

## callees

- `0x1800129e4`
- `0x1800131e8`
- `0x18001385c`
- `0x180013944`
- `0x180014664`
- `0x1800149ac`
- `0x180014e7c`
- `0x180028c80`
- `0x180028e34`
- `0x180028f90`
- `0x18002a004`
- `0x18002a6b0`
- `0x18002a6bc`
- `0x18002b394`

## import_xrefs

- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180014c40`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180014c40`

## pseudocode

```c
__int64 __fastcall CWMVideoDecMediaObject::InitDecoderUsingSetTypes(CWMVideoDecMediaObject *this)
{
  unsigned __int64 v2; // rsi
  _QWORD *v3; // rbp
  tagVIDEOINFOHEADER *v4; // r15
  struct tagVIDEOINFOHEADER *v5; // r14
  __int64 v6; // rax
  struct _MFVIDEOFORMAT *v7; // rbx
  struct tagVIDEOINFOHEADER *v8; // rax
  int v9; // ebx
  __int64 v10; // r12
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rax
  const RECT *p_rcSource; // r13
  __int64 v16; // r10
  __int64 v17; // r8
  __int64 v18; // rax
  struct _MFVIDEOFORMAT *v19; // rbx
  struct tagVIDEOINFOHEADER *v20; // rax
  __int64 v21; // rdx
  struct tagVIDEOINFOHEADER *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  const RECT *p_biHeight; // rbx
  LONG *p_bottom; // rcx
  LONG biWidth; // edx
  int biHeight; // eax
  int v31; // eax
  int v32; // ecx
  bool v33; // sf
  __int64 v34; // rax
  unsigned int v35; // ebp
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // r12d
  __int64 v39; // r13
  double v40; // xmm0_8
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdx
  unsigned int v45; // [rsp+28h] [rbp-D0h]
  unsigned __int8 *v46; // [rsp+30h] [rbp-C8h]
  unsigned int v47; // [rsp+38h] [rbp-C0h]
  tagVIDEOINFOHEADER *v48; // [rsp+40h] [rbp-B8h]
  tagVIDEOINFOHEADER v49; // [rsp+50h] [rbp-A8h] BYREF

  v2 = ((unsigned __int64)this + 64) & -(__int64)(*((_DWORD *)this + 14) != 0);
  v3 = (_QWORD *)(((unsigned __int64)this + 152) & -(__int64)(*((_DWORD *)this + 15) != 0));
  if ( !v2 || !v3 )
    return (unsigned int)-2147220989;
  v4 = 0;
  v5 = 0;
  v49.rcSource.left = 0;
  memset_0(&v49.rcSource.top, 0, 0x54u);
  v6 = *(_QWORD *)(v2 + 44) - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
  if ( !v6 )
    v6 = *(_QWORD *)(v2 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
  if ( v6 )
  {
    v12 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
    v13 = *(_QWORD *)(v2 + 44) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
    if ( !v13 )
      v13 = *(_QWORD *)(v2 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
    v10 = *(_QWORD *)FORMAT_VideoInfo2.Data4;
    v11 = *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    if ( !v13 )
    {
      v48 = *(tagVIDEOINFOHEADER **)(v2 + 80);
      goto LABEL_23;
    }
    v14 = *(_QWORD *)(v2 + 44) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    if ( !v14 )
      v14 = *(_QWORD *)(v2 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
    if ( v14 )
    {
      v48 = 0;
      goto LABEL_23;
    }
    v9 = ConvertVIH2ToVIH(*(struct tagVIDEOINFOHEADER2 **)(v2 + 80), &v49);
    if ( v9 < 0 )
      return (unsigned int)v9;
    v48 = &v49;
LABEL_11:
    v11 = *(_QWORD *)&FORMAT_VideoInfo2.Data1;
    v12 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
LABEL_23:
    p_rcSource = 0;
    v16 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
    v17 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
    v18 = *(_QWORD *)((char *)v3 + 44) - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
    if ( !v18 )
      v18 = *(_QWORD *)((char *)v3 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
    if ( v18 )
    {
      v21 = *(_QWORD *)FORMAT_VideoInfo.Data4;
      v23 = *(_QWORD *)((char *)v3 + 44) - v12;
      if ( !v23 )
        v23 = *(_QWORD *)((char *)v3 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
      if ( v23 )
      {
        v24 = *(_QWORD *)((char *)v3 + 44) - v11;
        if ( !v24 )
          v24 = *(_QWORD *)((char *)v3 + 52) - v10;
        if ( v24 )
        {
          v9 = -2147220987;
          goto LABEL_82;
        }
        p_rcSource = (const RECT *)v3[10];
        v22 = 0;
      }
      else
      {
        v22 = (struct tagVIDEOINFOHEADER *)v3[10];
      }
      goto LABEL_38;
    }
    v19 = (struct _MFVIDEOFORMAT *)v3[10];
    if ( v19 )
    {
      v20 = (struct tagVIDEOINFOHEADER *)operator new[](0x458u);
      v5 = v20;
      if ( !v20 )
        goto LABEL_8;
      v9 = ConvertMFVideoFormatToVIH3(v20, v19);
      if ( v9 < 0 )
        goto LABEL_82;
      v21 = *(_QWORD *)FORMAT_VideoInfo.Data4;
      v22 = v5;
      v17 = *(_QWORD *)FORMAT_MFVideoFormat.Data4;
      v12 = *(_QWORD *)&FORMAT_VideoInfo.Data1;
      v16 = *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
LABEL_38:
      v25 = *(_QWORD *)((char *)v3 + 44) - v16;
      if ( !v25 )
        v25 = *(_QWORD *)((char *)v3 + 52) - v17;
      if ( !v25 )
        goto LABEL_45;
      v26 = *(_QWORD *)((char *)v3 + 44) - v12;
      if ( !v26 )
        v26 = *(_QWORD *)((char *)v3 + 52) - v21;
      if ( v26 )
      {
        p_biHeight = p_rcSource + 5;
        p_bottom = &p_rcSource[4].bottom;
      }
      else
      {
LABEL_45:
        p_rcSource = &v22->rcSource;
        p_biHeight = (const RECT *)&v22->bmiHeader.biHeight;
        p_bottom = &v22->bmiHeader.biWidth;
      }
      biWidth = v48->bmiHeader.biWidth;
      *((_DWORD *)this + 138) = biWidth;
      biHeight = -v48->bmiHeader.biHeight;
      if ( v48->bmiHeader.biHeight > 0 )
        biHeight = v48->bmiHeader.biHeight;
      *((_DWORD *)this + 139) = biHeight;
      if ( p_biHeight->left >= biHeight && *p_bottom >= biWidth )
      {
        if ( IsRectEmpty(p_rcSource + 1) )
        {
          *((_DWORD *)this + 143) = *((_DWORD *)this + 138);
          *((_DWORD *)this + 144) = *((_DWORD *)this + 139);
          *(_QWORD *)((char *)this + 564) = 0;
        }
        else
        {
          v31 = p_rcSource[1].right - p_rcSource[1].left;
          *((_DWORD *)this + 143) = v31;
          v32 = p_rcSource[1].bottom - p_rcSource[1].top;
          *((_DWORD *)this + 144) = v32;
          if ( v31 < 1 || v31 > *((_DWORD *)this + 138) )
            *((_DWORD *)this + 143) = *((_DWORD *)this + 138);
          if ( v32 < 1 || v32 > *((_DWORD *)this + 139) )
            *((_DWORD *)this + 144) = *((_DWORD *)this + 139);
          *((_DWORD *)this + 141) = p_rcSource[1].left;
          v33 = -(p_biHeight->left + p_rcSource[1].bottom) < 0;
          *((_DWORD *)this + 142) = -(p_biHeight->left + p_rcSource[1].bottom);
          if ( v33 )
            *((_DWORD *)this + 142) = 0;
        }
        v34 = *(_QWORD *)(v2 + 44) - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
        if ( !v34 )
          v34 = *(_QWORD *)(v2 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
        if ( !v34 )
        {
          v35 = 176;
          goto LABEL_73;
        }
        v36 = *(_QWORD *)(v2 + 44) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
        if ( !v36 )
          v36 = *(_QWORD *)(v2 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
        if ( !v36 )
        {
          v35 = 112;
          goto LABEL_73;
        }
        v37 = *(_QWORD *)(v2 + 44) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
        if ( !v37 )
          v37 = *(_QWORD *)(v2 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
        if ( !v37 )
        {
          v35 = 88;
LABEL_73:
          v38 = *(_DWORD *)(v2 + 72);
          v39 = *(_QWORD *)(v2 + 80);
          v40 = FramesPerSecond(v48->AvgTimePerFrame);
          v9 = CWMVideoDecMediaObject::ResetDecoder(
                 this,
                 *(_DWORD *)(v2 + 16),
                 *(_DWORD *)(v41 + 52),
                 *(_DWORD *)(v41 + 56),
                 v40,
                 v45,
                 v46,
                 v47);
          if ( v9 >= 0 )
          {
            if ( !(unsigned int)NeedHeader(*(unsigned int *)(v2 + 16)) && *(_DWORD *)(v2 + 72) == v35
              || (v9 = SessionFrameDecoder::setExtendedFormat(
                         *((SessionFrameDecoder **)this + 68),
                         (unsigned __int8 *)(v39 + v35),
                         v38 - v35),
                  v9 >= 0) )
            {
              v42 = *((_QWORD *)this + 68);
              *((_DWORD *)this + 463) = 0;
              *((_QWORD *)this + 160) = 0;
              *((_QWORD *)this + 161) = 0;
              SessionFrameDecoder::SetQualityMessageState(v42, 0);
              v43 = 3;
              if ( !*((_DWORD *)this + 314) )
                v43 = *((unsigned int *)this + 464);
              SessionFrameDecoder::SetPostProcessingState(*((_QWORD *)this + 68), v43);
              SessionFrameDecoder::SetSWPowerLevel(*((SessionFrameDecoder **)this + 68), *((_DWORD *)this + 324));
              *((_DWORD *)this + 85) = 1;
            }
            else
            {
              DestroyDecoder(*((struct SessionFrameDecoder **)this + 68));
              *((_QWORD *)this + 68) = 0;
            }
          }
          goto LABEL_82;
        }
      }
      v9 = -2147467259;
      goto LABEL_82;
    }
LABEL_12:
    v9 = -2147467261;
    goto LABEL_82;
  }
  v7 = *(struct _MFVIDEOFORMAT **)(v2 + 80);
  if ( !v7 )
    goto LABEL_12;
  v8 = (struct tagVIDEOINFOHEADER *)operator new[](0x458u);
  v4 = v8;
  if ( v8 )
  {
    v9 = ConvertMFVideoFormatToVIH3(v8, v7);
    if ( v9 < 0 )
      goto LABEL_82;
    v10 = *(_QWORD *)FORMAT_VideoInfo2.Data4;
    v48 = v4;
    goto LABEL_11;
  }
LABEL_8:
  v9 = -2147024882;
LABEL_82:
  if ( v4 )
    operator delete(v4);
  if ( v5 )
    operator delete(v5);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800149ac  push    rbx
0x1800149ae  push    rbp
0x1800149af  push    rsi
0x1800149b0  push    rdi
0x1800149b1  push    r12
0x1800149b3  push    r13
0x1800149b5  push    r14
0x1800149b7  push    r15
0x1800149b9  sub     rsp, 0B8h
0x1800149c0  mov     eax, [rcx+38h]
0x1800149c3  lea     rdx, [rcx+40h]
0x1800149c7  neg     eax
0x1800149c9  mov     rdi, rcx
0x1800149cc  mov     eax, [rcx+3Ch]
0x1800149cf  sbb     rsi, rsi
0x1800149d2  and     rsi, rdx
0x1800149d5  lea     rdx, [rcx+98h]
0x1800149dc  neg     eax
0x1800149de  sbb     rbp, rbp
0x1800149e1  and     rbp, rdx
0x1800149e4  test    rsi, rsi
0x1800149e7  jz      loc_180014E58
0x1800149ed  test    rbp, rbp
0x1800149f0  jz      loc_180014E58
0x1800149f6  xor     r15d, r15d
0x1800149f9  lea     rcx, [rsp+0F8h+var_A8.rcSource.top]; void *
0x1800149fe  xor     r14d, r14d
0x180014a01  xor     edx, edx; Val
0x180014a03  mov     [rsp+0F8h+var_A8.rcSource.left], r14d
0x180014a08  lea     r8d, [r15+54h]; Size
0x180014a0c  call    memset_0
0x180014a11  mov     rax, [rsi+2Ch]
0x180014a15  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180014a1c  jnz     short loc_180014A29
0x180014a1e  mov     rax, [rsi+34h]
0x180014a22  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180014a29  test    rax, rax
0x180014a2c  jnz     short loc_180014A91
0x180014a2e  mov     rbx, [rsi+50h]
0x180014a32  test    rbx, rbx
0x180014a35  jz      short loc_180014A87
0x180014a37  mov     ecx, 458h; unsigned __int64
0x180014a3c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014a41  mov     r15, rax
0x180014a44  test    rax, rax
0x180014a47  jnz     short loc_180014A53
0x180014a49  mov     ebx, 8007000Eh
0x180014a4e  jmp     loc_180014E3C
0x180014a53  mov     rdx, rbx; struct _MFVIDEOFORMAT *
0x180014a56  mov     rcx, r15; struct tagVIDEOINFOHEADER *
0x180014a59  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x180014a5e  mov     ebx, eax
0x180014a60  test    eax, eax
0x180014a62  js      loc_180014E3C
0x180014a68  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180014a6f  mov     [rsp+0F8h+var_B8], r15
0x180014a74  mov     rcx, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180014a7b  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180014a82  jmp     loc_180014B0B
0x180014a87  mov     ebx, 80004003h
0x180014a8c  jmp     loc_180014E3C
0x180014a91  mov     rax, [rsi+2Ch]
0x180014a95  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180014a9c  sub     rax, r9
0x180014a9f  jnz     short loc_180014AAC
0x180014aa1  mov     rax, [rsi+34h]
0x180014aa5  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180014aac  mov     r12, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180014ab3  mov     rcx, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180014aba  test    rax, rax
0x180014abd  jnz     short loc_180014ACA
0x180014abf  mov     rdx, [rsi+50h]
0x180014ac3  mov     [rsp+0F8h+var_B8], rdx
0x180014ac8  jmp     short loc_180014B0B
0x180014aca  mov     rax, [rsi+2Ch]
0x180014ace  sub     rax, rcx
0x180014ad1  jnz     short loc_180014ADA
0x180014ad3  mov     rax, [rsi+34h]
0x180014ad7  sub     rax, r12
0x180014ada  test    rax, rax
0x180014add  jnz     short loc_180014B06
0x180014adf  mov     rcx, [rsi+50h]; struct tagVIDEOINFOHEADER2 *
0x180014ae3  lea     rdx, [rsp+0F8h+var_A8]; struct tagVIDEOINFOHEADER *
0x180014ae8  call    ?ConvertVIH2ToVIH@@YAJPEAUtagVIDEOINFOHEADER2@@PEAUtagVIDEOINFOHEADER@@@Z; ConvertVIH2ToVIH(tagVIDEOINFOHEADER2 *,tagVIDEOINFOHEADER *)
0x180014aed  mov     ebx, eax
0x180014aef  test    eax, eax
0x180014af1  js      loc_180014E5D
0x180014af7  lea     rdx, [rsp+0F8h+var_A8]
0x180014afc  mov     [rsp+0F8h+var_B8], rdx
0x180014b01  jmp     loc_180014A74
0x180014b06  mov     [rsp+0F8h+var_B8], r14
0x180014b0b  mov     rax, [rbp+2Ch]
0x180014b0f  xor     r13d, r13d
0x180014b12  mov     r10, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180014b19  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180014b20  sub     rax, r10
0x180014b23  jnz     short loc_180014B2C
0x180014b25  mov     rax, [rbp+34h]
0x180014b29  sub     rax, r8
0x180014b2c  test    rax, rax
0x180014b2f  jnz     short loc_180014B8A
0x180014b31  mov     rbx, [rbp+50h]
0x180014b35  test    rbx, rbx
0x180014b38  jz      loc_180014A87
0x180014b3e  mov     ecx, 458h; unsigned __int64
0x180014b43  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180014b48  mov     r14, rax
0x180014b4b  test    rax, rax
0x180014b4e  jz      loc_180014A49
0x180014b54  mov     rdx, rbx; struct _MFVIDEOFORMAT *
0x180014b57  mov     rcx, rax; struct tagVIDEOINFOHEADER *
0x180014b5a  call    ?ConvertMFVideoFormatToVIH3@@YAJPEAUtagVIDEOINFOHEADER@@PEAU_MFVIDEOFORMAT@@@Z; ConvertMFVideoFormatToVIH3(tagVIDEOINFOHEADER *,_MFVIDEOFORMAT *)
0x180014b5f  mov     ebx, eax
0x180014b61  test    eax, eax
0x180014b63  js      loc_180014E3C
0x180014b69  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data4
0x180014b70  mov     rcx, r14
0x180014b73  mov     r8, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180014b7a  mov     r9, qword ptr cs:FORMAT_VideoInfo.Data1
0x180014b81  mov     r10, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180014b88  jmp     short loc_180014BCB
0x180014b8a  mov     rax, [rbp+2Ch]
0x180014b8e  mov     rdx, qword ptr cs:FORMAT_VideoInfo.Data4
0x180014b95  sub     rax, r9
0x180014b98  jnz     short loc_180014BA1
0x180014b9a  mov     rax, [rbp+34h]
0x180014b9e  sub     rax, rdx
0x180014ba1  test    rax, rax
0x180014ba4  jnz     short loc_180014BAC
0x180014ba6  mov     rcx, [rbp+50h]
0x180014baa  jmp     short loc_180014BCB
0x180014bac  mov     rax, [rbp+2Ch]
0x180014bb0  sub     rax, rcx
0x180014bb3  jnz     short loc_180014BBC
0x180014bb5  mov     rax, [rbp+34h]
0x180014bb9  sub     rax, r12
0x180014bbc  test    rax, rax
0x180014bbf  jnz     loc_180014E37
0x180014bc5  mov     r13, [rbp+50h]
0x180014bc9  xor     ecx, ecx
0x180014bcb  mov     rax, [rbp+2Ch]
0x180014bcf  sub     rax, r10
0x180014bd2  jnz     short loc_180014BDB
0x180014bd4  mov     rax, [rbp+34h]
0x180014bd8  sub     rax, r8
0x180014bdb  test    rax, rax
0x180014bde  jz      short loc_180014BFF
0x180014be0  mov     rax, [rbp+2Ch]
0x180014be4  sub     rax, r9
0x180014be7  jnz     short loc_180014BF0
0x180014be9  mov     rax, [rbp+34h]
0x180014bed  sub     rax, rdx
0x180014bf0  test    rax, rax
0x180014bf3  jz      short loc_180014BFF
0x180014bf5  lea     rbx, [r13+50h]
0x180014bf9  lea     rcx, [r13+4Ch]
0x180014bfd  jmp     short loc_180014C0A
0x180014bff  mov     r13, rcx
0x180014c02  lea     rbx, [rcx+38h]
0x180014c06  add     rcx, 34h ; '4'
0x180014c0a  mov     r8, [rsp+0F8h+var_B8]
0x180014c0f  mov     edx, [r8+34h]
0x180014c13  mov     [rdi+228h], edx
0x180014c19  mov     eax, [r8+38h]
0x180014c1d  neg     eax
0x180014c1f  cmovs   eax, [r8+38h]
0x180014c24  mov     [rdi+22Ch], eax
0x180014c2a  cmp     [rbx], eax
0x180014c2c  jge     short loc_180014C38
0x180014c2e  mov     ebx, 80004005h
0x180014c33  jmp     loc_180014E3C
0x180014c38  cmp     [rcx], edx
0x180014c3a  jl      short loc_180014C2E
0x180014c3c  lea     rcx, [r13+10h]; lprc
0x180014c40  call    cs:__imp_IsRectEmpty
0x180014c46  test    eax, eax
0x180014c48  jz      short loc_180014C6F
0x180014c4a  mov     eax, [rdi+228h]
0x180014c50  mov     [rdi+23Ch], eax
0x180014c56  mov     eax, [rdi+22Ch]
0x180014c5c  mov     [rdi+240h], eax
0x180014c62  mov     qword ptr [rdi+234h], 0
0x180014c6d  jmp     short loc_180014CE1
0x180014c6f  mov     eax, [r13+18h]
0x180014c73  sub     eax, [r13+10h]
0x180014c77  mov     [rdi+23Ch], eax
0x180014c7d  mov     ecx, [r13+1Ch]
0x180014c81  sub     ecx, [r13+14h]
0x180014c85  mov     [rdi+240h], ecx
0x180014c8b  cmp     eax, 1
0x180014c8e  jl      short loc_180014C98
0x180014c90  cmp     eax, [rdi+228h]
0x180014c96  jle     short loc_180014CA4
0x180014c98  mov     eax, [rdi+228h]
0x180014c9e  mov     [rdi+23Ch], eax
0x180014ca4  cmp     ecx, 1
0x180014ca7  jl      short loc_180014CB1
0x180014ca9  cmp     ecx, [rdi+22Ch]
0x180014caf  jle     short loc_180014CBD
0x180014cb1  mov     eax, [rdi+22Ch]
0x180014cb7  mov     [rdi+240h], eax
0x180014cbd  mov     eax, [r13+10h]
0x180014cc1  mov     [rdi+234h], eax
0x180014cc7  mov     eax, [r13+1Ch]
0x180014ccb  add     eax, [rbx]
0x180014ccd  neg     eax
0x180014ccf  mov     [rdi+238h], eax
0x180014cd5  jns     short loc_180014CE1
0x180014cd7  mov     dword ptr [rdi+238h], 0
0x180014ce1  mov     rax, [rsi+2Ch]
0x180014ce5  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x180014cec  jnz     short loc_180014CF9
0x180014cee  mov     rax, [rsi+34h]
0x180014cf2  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x180014cf9  test    rax, rax
0x180014cfc  jnz     short loc_180014D05
0x180014cfe  mov     ebp, 0B0h
0x180014d03  jmp     short loc_180014D4B
0x180014d05  mov     rax, [rsi+2Ch]
0x180014d09  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x180014d10  jnz     short loc_180014D1D
0x180014d12  mov     rax, [rsi+34h]
0x180014d16  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x180014d1d  test    rax, rax
0x180014d20  jnz     short loc_180014D27
0x180014d22  lea     ebp, [rax+70h]
0x180014d25  jmp     short loc_180014D4B
0x180014d27  mov     rax, [rsi+2Ch]
0x180014d2b  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x180014d32  jnz     short loc_180014D3F
0x180014d34  mov     rax, [rsi+34h]
0x180014d38  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x180014d3f  test    rax, rax
0x180014d42  jnz     loc_180014C2E
0x180014d48  lea     ebp, [rax+58h]
0x180014d4b  mov     rax, [rsp+0F8h+var_B8]
0x180014d50  mov     r12d, [rsi+48h]
0x180014d54  mov     r13, [rsi+50h]
0x180014d58  mov     rcx, [rax+28h]
0x180014d5c  call    FramesPerSecond
0x180014d61  mov     r9d, [rax+38h]; int
0x180014d65  mov     rcx, rdi; this
0x180014d68  mov     r8d, [rax+34h]; int
0x180014d6c  mov     edx, [rsi+10h]; unsigned int
0x180014d6f  movsd   [rsp+0F8h+var_D8], xmm0; double
0x180014d75  call    ?ResetDecoder@CWMVideoDecMediaObject@@AEAAJKJJNKPEAEK@Z; CWMVideoDecMediaObject::ResetDecoder(ulong,long,long,double,ulong,uchar *,ulong)
0x180014d7a  mov     ebx, eax
0x180014d7c  test    eax, eax
0x180014d7e  js      loc_180014E3C
0x180014d84  mov     ecx, [rsi+10h]
0x180014d87  call    NeedHeader
0x180014d8c  test    eax, eax
0x180014d8e  jnz     short loc_180014D95
0x180014d90  cmp     [rsi+48h], ebp
0x180014d93  jz      short loc_180014DCB
0x180014d95  mov     rcx, [rdi+220h]; this
0x180014d9c  sub     r12d, ebp
0x180014d9f  mov     edx, ebp
0x180014da1  mov     r8d, r12d; unsigned int
0x180014da4  add     rdx, r13; unsigned __int8 *
0x180014da7  call    ?setExtendedFormat@SessionFrameDecoder@@QEAAJPEAEK@Z; SessionFrameDecoder::setExtendedFormat(uchar *,ulong)
0x180014dac  mov     ebx, eax
0x180014dae  test    eax, eax
0x180014db0  jns     short loc_180014DCB
0x180014db2  mov     rcx, [rdi+220h]; struct SessionFrameDecoder *
0x180014db9  call    ?DestroyDecoder@@YAXPEAVSessionFrameDecoder@@@Z; DestroyDecoder(SessionFrameDecoder *)
0x180014dbe  mov     qword ptr [rdi+220h], 0
0x180014dc9  jmp     short loc_180014E3C
0x180014dcb  mov     rcx, [rdi+220h]
0x180014dd2  xor     edx, edx
0x180014dd4  mov     dword ptr [rdi+73Ch], 0
0x180014dde  mov     qword ptr [rdi+500h], 0
0x180014de9  mov     qword ptr [rdi+508h], 0
0x180014df4  call    ?SetQualityMessageState@SessionFrameDecoder@@QEAAJW4SesDecQualityMessageState@1@@Z; SessionFrameDecoder::SetQualityMessageState(SessionFrameDecoder::SesDecQualityMessageState)
0x180014df9  cmp     dword ptr [rdi+4E8h], 0
0x180014e00  mov     edx, 3
0x180014e05  jnz     short loc_180014E0D
0x180014e07  mov     edx, [rdi+740h]
0x180014e0d  mov     rcx, [rdi+220h]
0x180014e14  call    ?SetPostProcessingState@SessionFrameDecoder@@QEAAJW4SesDecPostProcessingState@1@@Z; SessionFrameDecoder::SetPostProcessingState(SessionFrameDecoder::SesDecPostProcessingState)
0x180014e19  mov     rcx, [rdi+220h]; this
0x180014e20  mov     edx, [rdi+510h]; unsigned int
0x180014e26  call    ?SetSWPowerLevel@SessionFrameDecoder@@QEAAJK@Z; SessionFrameDecoder::SetSWPowerLevel(ulong)
0x180014e2b  mov     dword ptr [rdi+154h], 1
0x180014e35  jmp     short loc_180014E3C
0x180014e37  mov     ebx, 80040205h
0x180014e3c  test    r15, r15
0x180014e3f  jz      short loc_180014E49
0x180014e41  mov     rcx, r15; Block
0x180014e44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014e49  test    r14, r14
0x180014e4c  jz      short loc_180014E5D
0x180014e4e  mov     rcx, r14; Block
0x180014e51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180014e56  jmp     short loc_180014E5D
0x180014e58  mov     ebx, 80040203h
0x180014e5d  mov     eax, ebx
0x180014e5f  add     rsp, 0B8h
0x180014e66  pop     r15
0x180014e68  pop     r14
  ... truncated ...
```
