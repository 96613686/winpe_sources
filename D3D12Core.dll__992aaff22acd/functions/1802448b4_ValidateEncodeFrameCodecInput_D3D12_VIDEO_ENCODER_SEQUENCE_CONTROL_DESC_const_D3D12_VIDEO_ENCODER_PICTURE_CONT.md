# ValidateEncodeFrameCodecInput(D3D12_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC const &,D3D12_VIDEO_ENCODER_PICTURE_CONTROL_DESC1 const &,D3D12_VIDEO_ENCODER_CODEC const &,TDebugOutputFunctor &)

- ea: `0x1802448b4`
- end: `0x180244ae4`
- name: `?ValidateEncodeFrameCodecInput@@YAJAEBUD3D12_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC@@AEBUD3D12_VIDEO_ENCODER_PICTURE_CONTROL_DESC1@@AEBW4D3D12_VIDEO_ENCODER_CODEC@@AEAUTDebugOutputFunctor@@@Z`
- size: `560`
- prototype: `__int64 __fastcall(const struct D3D12_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC *, const struct D3D12_VIDEO_ENCODER_PICTURE_CONTROL_DESC1 *, const enum D3D12_VIDEO_ENCODER_CODEC *, struct TDebugOutputFunctor *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802404b4`

## callees

- `0x18002ef50`
- `0x1802448b4`

## string_xrefs

- `0x180244a39`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - ...PictureControlCodecData.pH264PicData cannot be null.`
- `0x1802448e8`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE`
- `0x180244920`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - ...PictureControlCodecData.pAV1PicData cannot be null.`
- `0x18024496e`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - If SelectedLayoutMode is not D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_FULL_FRAME or D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_AUTO.then FrameSubregionsLayoutData.pTilesPartition_AV1 must be set with the associated configuration`
- `0x1802449b1`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - ...PictureControlCodecData.pHEVCPicData cannot be null.`
- `0x1802449ff`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - If SelectedLayoutMode is not D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_FULL_FRAME or D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_AUTO.then FrameSubregionsLayoutData.pSlicesPartition_<codec> must be set with the associated configuration`
- `0x180244a87`: `ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - If SelectedLayoutMode is not D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_FULL_FRAME or D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_AUTO.then FrameSubregionsLayoutData.pSlicesPartition_<codec> must be set with the associated configuration`

## pseudocode

```c
__int64 __fastcall ValidateEncodeFrameCodecInput(
        const struct D3D12_VIDEO_ENCODER_SEQUENCE_CONTROL_DESC *a1,
        const struct D3D12_VIDEO_ENCODER_PICTURE_CONTROL_DESC1 *a2,
        const enum D3D12_VIDEO_ENCODER_CODEC *a3,
        struct TDebugOutputFunctor *a4)
{
  bool v8; // di
  const char *v9; // r8

  if ( *((int *)a1 + 14) >= 8 )
  {
    v8 = 0;
    TDebugOutputFunctor::operator()(
      a4,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - Invalid D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE");
  }
  else
  {
    v8 = *(_DWORD *)a3 < 3;
  }
  if ( !*(_DWORD *)a3 )
  {
    if ( !*((_QWORD *)a2 + 2) )
    {
      TDebugOutputFunctor::operator()(
        a4,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - ...PictureControlCodecData.pH264PicData cannot be null.");
      v8 = 0;
    }
    if ( *((_DWORD *)a2 + 2) != 136 )
    {
      TDebugOutputFunctor::operator()(
        a4,
        1305,
        "The data size of the structure passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA.pH264PicData. does not m"
        "atch the expected size of D3D12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_H264 Expected size: %d Received size: %d",
        136,
        *((_DWORD *)a2 + 2));
      v8 = 0;
    }
    if ( *((_DWORD *)a1 + 14) && *((_DWORD *)a1 + 14) != 7 )
    {
      if ( *((_QWORD *)a1 + 9) )
      {
LABEL_38:
        if ( *((_DWORD *)a1 + 16) != 4 )
        {
          v9 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA.pSlic"
               "esPartition_H264. does not match the expected size of D3D12_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYO"
               "UT_DATA_SLICES Expected size: %d Received size: %d";
          goto LABEL_40;
        }
        return !v8 ? 0x80070057 : 0;
      }
      TDebugOutputFunctor::operator()(
        a4,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - If SelectedLayoutMode is not D3D12_VIDEO_E"
        "NCODER_FRAME_SUBREGION_LAYOUT_MODE_FULL_FRAME or D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_AUTO.then Frame"
        "SubregionsLayoutData.pSlicesPartition_<codec> must be set with the associated configuration");
      v8 = 0;
    }
    if ( !*((_QWORD *)a1 + 9) )
      return !v8 ? 0x80070057 : 0;
    goto LABEL_38;
  }
  if ( *(_DWORD *)a3 != 1 )
  {
    if ( *(_DWORD *)a3 != 2 )
      return !v8 ? 0x80070057 : 0;
    if ( !*((_QWORD *)a2 + 2) )
    {
      TDebugOutputFunctor::operator()(
        a4,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - ...PictureControlCodecData.pAV1PicData cannot be null.");
      v8 = 0;
    }
    if ( *((_DWORD *)a2 + 2) != 1792 )
    {
      TDebugOutputFunctor::operator()(
        a4,
        1305,
        "The data size of the structure passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA.pAV1PicData. does not ma"
        "tch the expected size of D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_CODEC_DATA Expected size: %d Received size: %d",
        1792,
        *((_DWORD *)a2 + 2));
      v8 = 0;
    }
    if ( *((_DWORD *)a1 + 14) && *((_DWORD *)a1 + 14) != 7 )
    {
      if ( *((_QWORD *)a1 + 9) )
      {
LABEL_16:
        if ( *((_DWORD *)a1 + 16) != 1048 )
        {
          v9 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA.pTile"
               "sPartition_AV1. does not match the expected size of D3D12_VIDEO_ENCODER_AV1_PICTURE_CONTROL_SUBREGIONS_LA"
               "YOUT_DATA_TILES Expected size: %d Received size: %d";
LABEL_40:
          TDebugOutputFunctor::operator()(a4, 1305, v9);
          v8 = 0;
          return !v8 ? 0x80070057 : 0;
        }
        return !v8 ? 0x80070057 : 0;
      }
      TDebugOutputFunctor::operator()(
        a4,
        1305,
        "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - If SelectedLayoutMode is not D3D12_VIDEO_E"
        "NCODER_FRAME_SUBREGION_LAYOUT_MODE_FULL_FRAME or D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_AUTO.then Frame"
        "SubregionsLayoutData.pTilesPartition_AV1 must be set with the associated configuration");
      v8 = 0;
    }
    if ( !*((_QWORD *)a1 + 9) )
      return !v8 ? 0x80070057 : 0;
    goto LABEL_16;
  }
  if ( !*((_QWORD *)a2 + 2) )
  {
    TDebugOutputFunctor::operator()(
      a4,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - ...PictureControlCodecData.pHEVCPicData cannot be null.");
    v8 = 0;
  }
  if ( *((_DWORD *)a2 + 2) != 144 )
  {
    TDebugOutputFunctor::operator()(
      a4,
      1305,
      "The data size of the structure passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA.pHEVCPicData. does not mat"
      "ch the expected size of D3D12_VIDEO_ENCODER_PICTURE_CONTROL_CODEC_DATA_HEVC2 Expected size: %d Received size: %d",
      144,
      *((_DWORD *)a2 + 2));
    v8 = 0;
  }
  if ( !*((_DWORD *)a1 + 14) || *((_DWORD *)a1 + 14) == 7 )
    goto LABEL_26;
  if ( !*((_QWORD *)a1 + 9) )
  {
    TDebugOutputFunctor::operator()(
      a4,
      1305,
      "ID3D12VideoEncodeCommandList::EncodeFrame arguments are not correct - If SelectedLayoutMode is not D3D12_VIDEO_ENC"
      "ODER_FRAME_SUBREGION_LAYOUT_MODE_FULL_FRAME or D3D12_VIDEO_ENCODER_FRAME_SUBREGION_LAYOUT_MODE_AUTO.then FrameSubr"
      "egionsLayoutData.pSlicesPartition_<codec> must be set with the associated configuration");
    v8 = 0;
LABEL_26:
    if ( !*((_QWORD *)a1 + 9) )
      return !v8 ? 0x80070057 : 0;
  }
  if ( *((_DWORD *)a1 + 16) != 4 )
  {
    v9 = "The data size of the structure passed in D3D12_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA.pSlicesPart"
         "ition_HEVC. does not match the expected size of D3D12_VIDEO_ENCODER_PICTURE_CONTROL_SUBREGIONS_LAYOUT_DATA_SLIC"
         "ES Expected size: %d Received size: %d";
    goto LABEL_40;
  }
  return !v8 ? 0x80070057 : 0;
}

```

## disassembly

```asm
0x1802448b4  push    rbx
0x1802448b6  push    rbp
0x1802448b7  push    rsi
0x1802448b8  push    rdi
0x1802448b9  push    r12
0x1802448bb  push    r14
0x1802448bd  push    r15
0x1802448bf  sub     rsp, 30h
0x1802448c3  xor     r15d, r15d
0x1802448c6  mov     rsi, r9
0x1802448c9  cmp     dword ptr [rcx+38h], 8
0x1802448cd  mov     r14, r8
0x1802448d0  mov     rbp, rdx
0x1802448d3  mov     rbx, rcx
0x1802448d6  mov     r12d, 519h
0x1802448dc  jge     short loc_1802448E8
0x1802448de  cmp     dword ptr [r8], 3
0x1802448e2  setl    dil
0x1802448e6  jmp     short loc_1802448FD
0x1802448e8  lea     r8, aId3d12videoenc_4; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x1802448ef  mov     edx, r12d
0x1802448f2  mov     rcx, rsi
0x1802448f5  mov     dil, r15b
0x1802448f8  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802448fd  mov     ecx, [r14]
0x180244900  test    ecx, ecx
0x180244902  jz      loc_180244A33
0x180244908  sub     ecx, 1
0x18024490b  jz      loc_1802449AB
0x180244911  cmp     ecx, 1
0x180244914  jnz     loc_180244AC9
0x18024491a  cmp     [rbp+10h], r15
0x18024491e  jnz     short loc_180244935
0x180244920  lea     r8, aId3d12videoenc_11; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180244927  mov     edx, r12d
0x18024492a  mov     rcx, rsi
0x18024492d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180244932  mov     dil, r15b
0x180244935  mov     eax, [rbp+8]
0x180244938  mov     r9d, 700h
0x18024493e  cmp     eax, r9d
0x180244941  jz      short loc_18024495C
0x180244943  lea     r8, aTheDataSizeOfT_8; "The data size of the structure passed i"...
0x18024494a  mov     [rsp+68h+var_48], eax
0x18024494e  mov     edx, r12d
0x180244951  mov     rcx, rsi
0x180244954  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180244959  mov     dil, r15b
0x18024495c  cmp     [rbx+38h], r15d
0x180244960  jz      short loc_180244983
0x180244962  cmp     dword ptr [rbx+38h], 7
0x180244966  jz      short loc_180244983
0x180244968  cmp     [rbx+48h], r15
0x18024496c  jnz     short loc_18024498D
0x18024496e  lea     r8, aId3d12videoenc_49; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180244975  mov     edx, r12d
0x180244978  mov     rcx, rsi
0x18024497b  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180244980  mov     dil, r15b
0x180244983  cmp     [rbx+48h], r15
0x180244987  jz      loc_180244AC9
0x18024498d  mov     eax, [rbx+40h]
0x180244990  mov     r9d, 418h
0x180244996  cmp     eax, r9d
0x180244999  jz      loc_180244AC9
0x18024499f  lea     r8, aTheDataSizeOfT_15; "The data size of the structure passed i"...
0x1802449a6  jmp     loc_180244AB7
0x1802449ab  cmp     [rbp+10h], r15
0x1802449af  jnz     short loc_1802449C6
0x1802449b1  lea     r8, aId3d12videoenc_110; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x1802449b8  mov     edx, r12d
0x1802449bb  mov     rcx, rsi
0x1802449be  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802449c3  mov     dil, r15b
0x1802449c6  mov     eax, [rbp+8]
0x1802449c9  mov     r9d, 90h
0x1802449cf  cmp     eax, r9d
0x1802449d2  jz      short loc_1802449ED
0x1802449d4  lea     r8, aTheDataSizeOfT_0; "The data size of the structure passed i"...
0x1802449db  mov     [rsp+68h+var_48], eax
0x1802449df  mov     edx, r12d
0x1802449e2  mov     rcx, rsi
0x1802449e5  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x1802449ea  mov     dil, r15b
0x1802449ed  cmp     [rbx+38h], r15d
0x1802449f1  jz      short loc_180244A14
0x1802449f3  cmp     dword ptr [rbx+38h], 7
0x1802449f7  jz      short loc_180244A14
0x1802449f9  cmp     [rbx+48h], r15
0x1802449fd  jnz     short loc_180244A1E
0x1802449ff  lea     r8, aId3d12videoenc_144; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180244a06  mov     edx, r12d
0x180244a09  mov     rcx, rsi
0x180244a0c  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180244a11  mov     dil, r15b
0x180244a14  cmp     [rbx+48h], r15
0x180244a18  jz      loc_180244AC9
0x180244a1e  mov     eax, [rbx+40h]
0x180244a21  cmp     eax, 4
0x180244a24  jz      loc_180244AC9
0x180244a2a  lea     r8, aTheDataSizeOfT_9; "The data size of the structure passed i"...
0x180244a31  jmp     short loc_180244AB1
0x180244a33  cmp     [rbp+10h], r15
0x180244a37  jnz     short loc_180244A4E
0x180244a39  lea     r8, aId3d12videoenc_65; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180244a40  mov     edx, r12d
0x180244a43  mov     rcx, rsi
0x180244a46  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180244a4b  mov     dil, r15b
0x180244a4e  mov     eax, [rbp+8]
0x180244a51  mov     r9d, 88h
0x180244a57  cmp     eax, r9d
0x180244a5a  jz      short loc_180244A75
0x180244a5c  lea     r8, aTheDataSizeOfT_14; "The data size of the structure passed i"...
0x180244a63  mov     [rsp+68h+var_48], eax
0x180244a67  mov     edx, r12d
0x180244a6a  mov     rcx, rsi
0x180244a6d  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180244a72  mov     dil, r15b
0x180244a75  cmp     [rbx+38h], r15d
0x180244a79  jz      short loc_180244A9C
0x180244a7b  cmp     dword ptr [rbx+38h], 7
0x180244a7f  jz      short loc_180244A9C
0x180244a81  cmp     [rbx+48h], r15
0x180244a85  jnz     short loc_180244AA2
0x180244a87  lea     r8, aId3d12videoenc_144; "ID3D12VideoEncodeCommandList::EncodeFra"...
0x180244a8e  mov     edx, r12d
0x180244a91  mov     rcx, rsi
0x180244a94  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180244a99  mov     dil, r15b
0x180244a9c  cmp     [rbx+48h], r15
0x180244aa0  jz      short loc_180244AC9
0x180244aa2  mov     eax, [rbx+40h]
0x180244aa5  cmp     eax, 4
0x180244aa8  jz      short loc_180244AC9
0x180244aaa  lea     r8, aTheDataSizeOfT_12; "The data size of the structure passed i"...
0x180244ab1  mov     r9d, 4
0x180244ab7  mov     edx, r12d
0x180244aba  mov     [rsp+68h+var_48], eax
0x180244abe  mov     rcx, rsi
0x180244ac1  call    ??RTDebugOutputFunctor@@QEAAXW4D3D12_MESSAGE_ID@@PEBDZZ; TDebugOutputFunctor::operator()(D3D12_MESSAGE_ID,char const *,...)
0x180244ac6  mov     dil, r15b
0x180244ac9  neg     dil
0x180244acc  sbb     eax, eax
0x180244ace  not     eax
0x180244ad0  and     eax, 80070057h
0x180244ad5  add     rsp, 30h
0x180244ad9  pop     r15
0x180244adb  pop     r14
0x180244add  pop     r12
0x180244adf  pop     rdi
0x180244ae0  pop     rsi
0x180244ae1  pop     rbp
0x180244ae2  pop     rbx
0x180244ae3  retn
```
