# ConvertDMOMediaTypeToMFMediaType(_MFVIDEOFORMAT *,_DMOMediaType const *)

- ea: `0x18002c0bc`
- end: `0x18002c2e1`
- name: `?ConvertDMOMediaTypeToMFMediaType@@YAJPEAU_MFVIDEOFORMAT@@PEBU_DMOMediaType@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(struct _MFVIDEOFORMAT *, const struct _DMOMediaType *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013fa0`
- `0x18002dc70`

## callees

- `0x18002c0bc`
- `0x180046010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18002c115`
- `MFPlat!MFCreateMediaType` at `0x18002c164`
- `MFPlat!MFCreateMediaType` at `0x18002c115`
- `MFPlat!MFCreateMediaType` at `0x18002c164`
- `MFPlat!MFCreateMFVideoFormatFromMFMediaType` at `0x18002c19f`
- `MFPlat!MFCreateMFVideoFormatFromMFMediaType` at `0x18002c19f`
- `MFPlat!MFInitMediaTypeFromVideoInfoHeader2` at `0x18002c134`
- `MFPlat!MFInitMediaTypeFromVideoInfoHeader2` at `0x18002c134`
- `MFPlat!MFInitMediaTypeFromVideoInfoHeader` at `0x18002c183`
- `MFPlat!MFInitMediaTypeFromVideoInfoHeader` at `0x18002c183`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c2b0`

## pseudocode

```c
__int64 __fastcall ConvertDMOMediaTypeToMFMediaType(struct _MFVIDEOFORMAT *a1, const struct _DMOMediaType *a2)
{
  MFVIDEOFORMAT *v3; // rcx
  __int64 v5; // rax
  HRESULT v6; // ebx
  HRESULT v7; // eax
  __int64 v8; // rax
  __int128 v9; // xmm0
  __int64 v10; // rax
  _OWORD *v11; // rax
  UINT32 pcbSize; // [rsp+40h] [rbp+20h] BYREF
  IMFMediaType *ppMFType; // [rsp+50h] [rbp+30h] BYREF
  MFVIDEOFORMAT *ppMFVF; // [rsp+58h] [rbp+38h] BYREF

  ppMFType = 0;
  v3 = 0;
  ppMFVF = 0;
  if ( !a1 || !a2 )
    return 2147500035LL;
  v5 = *(_QWORD *)((char *)a2 + 44) - *(_QWORD *)&FORMAT_VideoInfo2.Data1;
  if ( !v5 )
    v5 = *(_QWORD *)((char *)a2 + 52) - *(_QWORD *)FORMAT_VideoInfo2.Data4;
  if ( !v5 )
  {
    pcbSize = 0;
    v6 = MFCreateMediaType(&ppMFType);
    if ( v6 < 0 )
      goto LABEL_16;
    v7 = MFInitMediaTypeFromVideoInfoHeader2(ppMFType, *((const VIDEOINFOHEADER2 **)a2 + 10), *((_DWORD *)a2 + 18), 0);
    goto LABEL_13;
  }
  v8 = *(_QWORD *)((char *)a2 + 44) - *(_QWORD *)&FORMAT_VideoInfo.Data1;
  if ( !v8 )
    v8 = *(_QWORD *)((char *)a2 + 52) - *(_QWORD *)FORMAT_VideoInfo.Data4;
  if ( v8 )
  {
    v10 = *(_QWORD *)((char *)a2 + 44) - *(_QWORD *)&FORMAT_MFVideoFormat.Data1;
    if ( !v10 )
      v10 = *(_QWORD *)((char *)a2 + 52) - *(_QWORD *)FORMAT_MFVideoFormat.Data4;
    if ( v10 )
    {
      v6 = -2147220987;
      goto LABEL_23;
    }
    v11 = (_OWORD *)*((_QWORD *)a2 + 10);
    v6 = 0;
    *(_OWORD *)&a1->dwSize = *v11;
    *(_OWORD *)&a1->videoInfo.PixelAspectRatio.Numerator = v11[1];
    *(_OWORD *)&a1->videoInfo.TransferFunction = v11[2];
    *(_OWORD *)&a1->videoInfo.FramesPerSecond.Numerator = v11[3];
    *(_OWORD *)&a1->videoInfo.GeometricAperture.OffsetY.fract = v11[4];
    *(_OWORD *)&a1->videoInfo.MinimumDisplayAperture.OffsetY.fract = v11[5];
    *(_OWORD *)&a1->videoInfo.PanScanAperture.OffsetY.fract = v11[6];
    *(_OWORD *)&a1->videoInfo.VideoFlags = v11[7];
    *(_OWORD *)a1->guidFormat.Data4 = v11[8];
    *(_OWORD *)&a1->compressedInfo.AvgBitErrorRate = v11[9];
    v9 = v11[10];
    goto LABEL_21;
  }
  pcbSize = 0;
  v6 = MFCreateMediaType(&ppMFType);
  if ( v6 >= 0 )
  {
    v7 = MFInitMediaTypeFromVideoInfoHeader(ppMFType, *((const VIDEOINFOHEADER **)a2 + 10), *((_DWORD *)a2 + 18), 0);
LABEL_13:
    v6 = v7;
    if ( v7 >= 0 )
    {
      v6 = MFCreateMFVideoFormatFromMFMediaType(ppMFType, &ppMFVF, &pcbSize);
      if ( v6 >= 0 )
      {
        v3 = ppMFVF;
        *(_OWORD *)&a1->dwSize = *(_OWORD *)&ppMFVF->dwSize;
        *(_OWORD *)&a1->videoInfo.PixelAspectRatio.Numerator = *(_OWORD *)&v3->videoInfo.PixelAspectRatio.Numerator;
        *(_OWORD *)&a1->videoInfo.TransferFunction = *(_OWORD *)&v3->videoInfo.TransferFunction;
        *(_OWORD *)&a1->videoInfo.FramesPerSecond.Numerator = *(_OWORD *)&v3->videoInfo.FramesPerSecond.Numerator;
        *(_OWORD *)&a1->videoInfo.GeometricAperture.OffsetY.fract = *(_OWORD *)&v3->videoInfo.GeometricAperture.OffsetY.fract;
        *(_OWORD *)&a1->videoInfo.MinimumDisplayAperture.OffsetY.fract = *(_OWORD *)&v3->videoInfo.MinimumDisplayAperture.OffsetY.fract;
        *(_OWORD *)&a1->videoInfo.PanScanAperture.OffsetY.fract = *(_OWORD *)&v3->videoInfo.PanScanAperture.OffsetY.fract;
        *(_OWORD *)&a1->videoInfo.VideoFlags = *(_OWORD *)&v3->videoInfo.VideoFlags;
        *(_OWORD *)a1->guidFormat.Data4 = *(_OWORD *)v3->guidFormat.Data4;
        *(_OWORD *)&a1->compressedInfo.AvgBitErrorRate = *(_OWORD *)&v3->compressedInfo.AvgBitErrorRate;
        v9 = *(_OWORD *)&v3->surfaceInfo.Format;
LABEL_21:
        *(_OWORD *)&a1->surfaceInfo.Format = v9;
        goto LABEL_23;
      }
    }
  }
LABEL_16:
  v3 = ppMFVF;
LABEL_23:
  CoTaskMemFree(v3);
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002c0bc  mov     [rsp-18h+arg_8], rbx
0x18002c0c1  push    rbp
0x18002c0c2  push    rsi
0x18002c0c3  push    rdi
0x18002c0c4  mov     rbp, rsp
0x18002c0c7  sub     rsp, 20h
0x18002c0cb  mov     rdi, rcx
0x18002c0ce  mov     [rbp+ppMFType], 0
0x18002c0d6  xor     ecx, ecx; pv
0x18002c0d8  mov     rsi, rdx
0x18002c0db  mov     [rbp+ppMFVF], rcx
0x18002c0df  test    rdi, rdi
0x18002c0e2  jz      loc_18002C2CF
0x18002c0e8  test    rdx, rdx
0x18002c0eb  jz      loc_18002C2CF
0x18002c0f1  mov     rax, [rdx+2Ch]
0x18002c0f5  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data1
0x18002c0fc  jnz     short loc_18002C109
0x18002c0fe  mov     rax, [rdx+34h]
0x18002c102  sub     rax, qword ptr cs:FORMAT_VideoInfo2.Data4
0x18002c109  test    rax, rax
0x18002c10c  jnz     short loc_18002C13C
0x18002c10e  mov     [rbp+pcbSize], ecx
0x18002c111  lea     rcx, [rbp+ppMFType]; ppMFType
0x18002c115  call    cs:__imp_MFCreateMediaType
0x18002c11b  mov     ebx, eax
0x18002c11d  test    eax, eax
0x18002c11f  js      loc_18002C215
0x18002c125  mov     r8d, [rsi+48h]; cbBufSize
0x18002c129  xor     r9d, r9d; pSubtype
0x18002c12c  mov     rdx, [rsi+50h]; pVIH2
0x18002c130  mov     rcx, [rbp+ppMFType]; pMFType
0x18002c134  call    cs:__imp_MFInitMediaTypeFromVideoInfoHeader2
0x18002c13a  jmp     short loc_18002C189
0x18002c13c  mov     rax, [rdx+2Ch]
0x18002c140  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data1
0x18002c147  jnz     short loc_18002C154
0x18002c149  mov     rax, [rdx+34h]
0x18002c14d  sub     rax, qword ptr cs:FORMAT_VideoInfo.Data4
0x18002c154  test    rax, rax
0x18002c157  jnz     loc_18002C21E
0x18002c15d  mov     [rbp+pcbSize], ecx
0x18002c160  lea     rcx, [rbp+ppMFType]; ppMFType
0x18002c164  call    cs:__imp_MFCreateMediaType
0x18002c16a  mov     ebx, eax
0x18002c16c  test    eax, eax
0x18002c16e  js      loc_18002C215
0x18002c174  mov     r8d, [rsi+48h]; cbBufSize
0x18002c178  xor     r9d, r9d; pSubtype
0x18002c17b  mov     rdx, [rsi+50h]; pVIH
0x18002c17f  mov     rcx, [rbp+ppMFType]; pMFType
0x18002c183  call    cs:__imp_MFInitMediaTypeFromVideoInfoHeader
0x18002c189  mov     ebx, eax
0x18002c18b  test    eax, eax
0x18002c18d  js      loc_18002C215
0x18002c193  mov     rcx, [rbp+ppMFType]; pMFType
0x18002c197  lea     r8, [rbp+pcbSize]; pcbSize
0x18002c19b  lea     rdx, [rbp+ppMFVF]; ppMFVF
0x18002c19f  call    cs:__imp_MFCreateMFVideoFormatFromMFMediaType
0x18002c1a5  mov     ebx, eax
0x18002c1a7  test    eax, eax
0x18002c1a9  js      short loc_18002C215
0x18002c1ab  mov     rcx, [rbp+ppMFVF]
0x18002c1af  movups  xmm0, xmmword ptr [rcx]
0x18002c1b2  movups  xmmword ptr [rdi], xmm0
0x18002c1b5  movups  xmm1, xmmword ptr [rcx+10h]
0x18002c1b9  movups  xmmword ptr [rdi+10h], xmm1
0x18002c1bd  movups  xmm0, xmmword ptr [rcx+20h]
0x18002c1c1  movups  xmmword ptr [rdi+20h], xmm0
0x18002c1c5  movups  xmm1, xmmword ptr [rcx+30h]
0x18002c1c9  movups  xmmword ptr [rdi+30h], xmm1
0x18002c1cd  movups  xmm0, xmmword ptr [rcx+40h]
0x18002c1d1  movups  xmmword ptr [rdi+40h], xmm0
0x18002c1d5  movups  xmm1, xmmword ptr [rcx+50h]
0x18002c1d9  movups  xmmword ptr [rdi+50h], xmm1
0x18002c1dd  movups  xmm0, xmmword ptr [rcx+60h]
0x18002c1e1  movups  xmmword ptr [rdi+60h], xmm0
0x18002c1e5  movups  xmm1, xmmword ptr [rcx+70h]
0x18002c1e9  movups  xmmword ptr [rdi+70h], xmm1
0x18002c1ed  movups  xmm0, xmmword ptr [rcx+80h]
0x18002c1f4  movups  xmmword ptr [rdi+80h], xmm0
0x18002c1fb  movups  xmm1, xmmword ptr [rcx+90h]
0x18002c202  movups  xmmword ptr [rdi+90h], xmm1
0x18002c209  movups  xmm0, xmmword ptr [rcx+0A0h]
0x18002c210  jmp     loc_18002C2A2
0x18002c215  mov     rcx, [rbp+ppMFVF]
0x18002c219  jmp     loc_18002C2B0
0x18002c21e  mov     rax, [rdx+2Ch]
0x18002c222  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data1
0x18002c229  jnz     short loc_18002C236
0x18002c22b  mov     rax, [rdx+34h]
0x18002c22f  sub     rax, qword ptr cs:FORMAT_MFVideoFormat.Data4
0x18002c236  test    rax, rax
0x18002c239  jnz     short loc_18002C2AB
0x18002c23b  mov     rax, [rdx+50h]
0x18002c23f  xor     ebx, ebx
0x18002c241  movups  xmm0, xmmword ptr [rax]
0x18002c244  movups  xmmword ptr [rdi], xmm0
0x18002c247  movups  xmm1, xmmword ptr [rax+10h]
0x18002c24b  movups  xmmword ptr [rdi+10h], xmm1
0x18002c24f  movups  xmm0, xmmword ptr [rax+20h]
0x18002c253  movups  xmmword ptr [rdi+20h], xmm0
0x18002c257  movups  xmm1, xmmword ptr [rax+30h]
0x18002c25b  movups  xmmword ptr [rdi+30h], xmm1
0x18002c25f  movups  xmm0, xmmword ptr [rax+40h]
0x18002c263  movups  xmmword ptr [rdi+40h], xmm0
0x18002c267  movups  xmm1, xmmword ptr [rax+50h]
0x18002c26b  movups  xmmword ptr [rdi+50h], xmm1
0x18002c26f  movups  xmm0, xmmword ptr [rax+60h]
0x18002c273  movups  xmmword ptr [rdi+60h], xmm0
0x18002c277  movups  xmm1, xmmword ptr [rax+70h]
0x18002c27b  movups  xmmword ptr [rdi+70h], xmm1
0x18002c27f  movups  xmm0, xmmword ptr [rax+80h]
0x18002c286  movups  xmmword ptr [rdi+80h], xmm0
0x18002c28d  movups  xmm1, xmmword ptr [rax+90h]
0x18002c294  movups  xmmword ptr [rdi+90h], xmm1
0x18002c29b  movups  xmm0, xmmword ptr [rax+0A0h]
0x18002c2a2  movups  xmmword ptr [rdi+0A0h], xmm0
0x18002c2a9  jmp     short loc_18002C2B0
0x18002c2ab  mov     ebx, 80040205h
0x18002c2b0  call    cs:__imp_CoTaskMemFree
0x18002c2b6  mov     rcx, [rbp+ppMFType]
0x18002c2ba  test    rcx, rcx
0x18002c2bd  jz      short loc_18002C2CB
0x18002c2bf  mov     rax, [rcx]
0x18002c2c2  mov     rax, [rax+10h]
0x18002c2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c2cb  mov     eax, ebx
0x18002c2cd  jmp     short loc_18002C2D4
0x18002c2cf  mov     eax, 80004003h
0x18002c2d4  mov     rbx, [rsp+20h+arg_8]
0x18002c2d9  add     rsp, 20h
0x18002c2dd  pop     rdi
0x18002c2de  pop     rsi
0x18002c2df  pop     rbp
0x18002c2e0  retn
```
