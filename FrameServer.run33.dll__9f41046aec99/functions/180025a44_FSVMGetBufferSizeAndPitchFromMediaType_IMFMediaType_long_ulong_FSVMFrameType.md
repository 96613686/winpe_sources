# FSVMGetBufferSizeAndPitchFromMediaType(IMFMediaType *,long *,ulong *,FSVMFrameType *)

- ea: `0x180025a44`
- end: `0x180025fcd`
- name: `?FSVMGetBufferSizeAndPitchFromMediaType@@YAJPEAUIMFMediaType@@PEAJPEAKPEAW4FSVMFrameType@@@Z`
- size: `1417`
- prototype: `__int64 __fastcall(struct IMFMediaType *, int *, unsigned int *, enum FSVMFrameType *)`
- caller_count: `3`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d6d30`
- `0x1800d98b0`
- `0x1800dc150`

## callees

- `0x180003e20`
- `0x180009608`
- `0x180009b5c`
- `0x180009d00`
- `0x18000a648`
- `0x180017ab8`
- `0x180024200`
- `0x180025a44`
- `0x1800268a8`
- `0x1800269b0`
- `0x180026a2c`
- `0x180026af4`
- `0x18004d714`
- `0x18004d748`
- `0x18004da70`
- `0x18004db3c`
- `0x18004db80`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateMFVideoFormatFromMFMediaType` at `0x180025c8d`
- `MFPlat!MFCreateMFVideoFormatFromMFMediaType` at `0x180025c8d`
- `MFPlat!MFGetUncompressedVideoFormat` at `0x180025c9f`
- `MFPlat!MFGetUncompressedVideoFormat` at `0x180025c9f`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x180025cb2`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x180025cb2`
- `MFPlat!MFCalculateImageSize` at `0x180025d40`
- `MFPlat!MFCalculateImageSize` at `0x180025d40`

## pseudocode

```c
__int64 __fastcall FSVMGetBufferSizeAndPitchFromMediaType(
        struct IMFMediaType *a1,
        int *a2,
        unsigned int *a3,
        enum FSVMFrameType *a4)
{
  char v8; // r14
  UINT32 v9; // edi
  UINT32 v10; // ebx
  MediaTypeTracer *v11; // rax
  const char *String; // rax
  int v13; // esi
  __int64 v14; // rdx
  __int64 v15; // rdx
  char v16; // r12
  HRESULT v17; // eax
  __int64 v18; // rdx
  DWORD v19; // eax
  DWORD v20; // ebx
  __int64 v21; // rdx
  int v22; // eax
  unsigned int i; // ecx
  int v24; // ecx
  int v25; // ebx
  unsigned int *v26; // rcx
  MediaTypeTracer *v27; // rax
  const char *v28; // rax
  bool v29; // zf
  GuidTrace *v30; // rax
  const char *v31; // rax
  unsigned __int64 v32; // rcx
  char v33; // bl
  char v34; // di
  MediaTypeTracer *v35; // rax
  const char *v36; // rax
  int v37; // edx
  int v38; // r8d
  UINT32 pcbImageSize; // [rsp+40h] [rbp-79h] BYREF
  LONG pStride; // [rsp+44h] [rbp-75h] BYREF
  UINT32 unHeight; // [rsp+48h] [rbp-71h] BYREF
  DWORD dwWidth; // [rsp+4Ch] [rbp-6Dh] BYREF
  MFVIDEOFORMAT *ppMFVF; // [rsp+50h] [rbp-69h] BYREF
  enum FSVMFrameType *v45; // [rsp+58h] [rbp-61h]
  unsigned int *v46; // [rsp+60h] [rbp-59h]
  _BYTE v47[56]; // [rsp+68h] [rbp-51h] BYREF
  GUID guidSubtype; // [rsp+A0h] [rbp-19h] BYREF
  GUID Buf1; // [rsp+B0h] [rbp-9h] BYREF

  v45 = a4;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  v46 = a3;
  guidSubtype = GUID_00000000_0000_0000_0000_000000000000;
  pStride = 0;
  v8 = 0;
  pcbImageSize = 0;
  ppMFVF = 0;
  v9 = 0;
  dwWidth = 0;
  v10 = 0;
  unHeight = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v11 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v47, a1);
    String = FSString::GetString((MediaTypeTracer *)((char *)v11 + 8));
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 59, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, String);
    v8 = 1;
  }
  if ( (v8 & 1) != 0 )
  {
    v8 &= ~1u;
    MediaTypeTracer::~MediaTypeTracer((MediaTypeTracer *)v47);
  }
  if ( !a1 )
  {
    v13 = -2147024809;
    if ( g_wppLevels )
    {
      v14 = 60;
LABEL_8:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v13);
      goto LABEL_52;
    }
    goto LABEL_52;
  }
  if ( !a2 )
  {
    v13 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_52;
    v15 = 61;
LABEL_13:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids,
      0,
      -2147467261);
    goto LABEL_52;
  }
  *a2 = 0;
  if ( !a3 )
  {
    v13 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_52;
    v15 = 62;
    goto LABEL_13;
  }
  *a3 = 0;
  if ( !a4 )
  {
    v13 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_52;
    v15 = 63;
    goto LABEL_13;
  }
  v16 = 0;
  *(_BYTE *)v45 = 0;
  v17 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a1->lpVtbl->GetGUID)(
          a1,
          &MF_MT_MAJOR_TYPE,
          &Buf1);
  v13 = v17;
  if ( v17 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v18 = 64;
LABEL_23:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, v17);
    goto LABEL_51;
  }
  v17 = ((__int64 (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *))a1->lpVtbl->GetGUID)(
          a1,
          &MF_MT_SUBTYPE,
          &guidSubtype);
  v13 = v17;
  if ( v17 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_51;
    v18 = 65;
    goto LABEL_23;
  }
  if ( !(unsigned int)MFGetAttributeUINT32(a1, &MF_MT_COMPRESSED, 0) )
  {
    if ( (int)MFGetAttribute2UINT32asUINT64(a1, &MF_MT_FRAME_SIZE, &dwWidth, &unHeight) < 0
      || (wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
            &ppMFVF,
            0),
          MFCreateMFVideoFormatFromMFMediaType(a1, &ppMFVF, 0) < 0) )
    {
      v9 = dwWidth;
    }
    else
    {
      v19 = MFGetUncompressedVideoFormat(ppMFVF);
      v9 = dwWidth;
      v20 = v19;
      if ( MFGetStrideForBitmapInfoHeader(v19, dwWidth, &pStride) >= 0 )
      {
        v22 = 64;
        for ( i = 0; i < 4; ++i )
        {
          v21 = (int)i;
          if ( v20 == *(_DWORD *)&aNv12_0[8 * i] )
          {
            v22 = *(_DWORD *)&aNv12_0[8 * i + 4];
            if ( !v22 )
              goto LABEL_56;
            break;
          }
        }
        v24 = v22 - 1;
        v25 = -pStride;
        if ( pStride > 0 )
          v25 = pStride;
        if ( (v24 & v25) != 0 )
          v9 = ~v24 & (v22 + v25 - 1);
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
          WPP_SF_dddD(*((_QWORD *)WPP_GLOBAL_Control + 27), v21, aNv12_0);
        v17 = MFCalculateImageSize(&guidSubtype, v9, unHeight, &pcbImageSize);
        v13 = v17;
        if ( v17 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_51;
          v18 = 71;
          goto LABEL_23;
        }
        if ( !memcmp_0(&Buf1, &MFMediaType_Video, 0x10u) && !memcmp_0(&guidSubtype, &MFVideoFormat_L8, 0x10u) )
          pStride = v25;
        v16 = 2;
LABEL_50:
        v26 = v46;
        *a2 = pStride;
        *v26 = pcbImageSize;
        *(_BYTE *)v45 = v16;
        goto LABEL_51;
      }
    }
LABEL_56:
    v10 = unHeight;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v8 |= 2u;
    v30 = GuidTrace::GuidTrace((GuidTrace *)v47, &Buf1);
    v31 = GuidTrace::GetString(v30);
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 66, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, v31);
  }
  if ( (v8 & 2) != 0 )
  {
    v8 &= ~2u;
    FSString::~FSString((FSString *)v47);
  }
  pStride = 0;
  v16 = 1;
  pcbImageSize = 0;
  if ( !v9 || !v10 )
  {
    pcbImageSize = MFGetAttributeUINT32(a1, &MF_MT_SAMPLE_SIZE, 0);
    if ( pcbImageSize && !(unsigned int)MFGetAttributeUINT32(a1, &MF_MT_FIXED_SIZE_SAMPLES, 0) )
    {
      v13 = -1072875852;
      if ( g_wppLevels )
      {
        v14 = 69;
        goto LABEL_8;
      }
      goto LABEL_52;
    }
    goto LABEL_50;
  }
  v32 = v9 * (unsigned __int64)v10;
  if ( v32 > 0xFFFFFFFF )
  {
    pcbImageSize = -1;
    v13 = -2147024362;
    if ( g_wppLevels )
    {
      v14 = 67;
      goto LABEL_8;
    }
LABEL_52:
    if ( byte_18010EC4D )
    {
      v8 |= 4u;
      v27 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v47, a1);
      v28 = FSString::GetString((MediaTypeTracer *)((char *)v27 + 8));
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        72,
        (unsigned int)&WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids,
        v13,
        (__int64)v28);
    }
    v29 = (v8 & 4) == 0;
    goto LABEL_77;
  }
  if ( 4 * (unsigned __int64)(unsigned int)v32 <= 0xFFFFFFFF )
  {
    pcbImageSize = 4 * v32;
    v13 = 0;
    goto LABEL_50;
  }
  pcbImageSize = -1;
  v13 = -2147024362;
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids, 0, -2147024362);
LABEL_51:
  if ( v13 < 0 )
    goto LABEL_52;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v33 = pcbImageSize;
    v34 = pStride;
    v8 |= 8u;
    v35 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v47, a1);
    v36 = FSString::GetString((MediaTypeTracer *)((char *)v35 + 8));
    WPP_SF_DsdDd(*((_QWORD *)WPP_GLOBAL_Control + 27), v37, v38, v13, (__int64)v36, v34, v33, v16);
  }
  v29 = (v8 & 8) == 0;
LABEL_77:
  if ( !v29 )
    MediaTypeTracer::~MediaTypeTracer((MediaTypeTracer *)v47);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppMFVF);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180025a44  push    rbp
0x180025a46  push    rbx
0x180025a47  push    rsi
0x180025a48  push    rdi
0x180025a49  push    r12
0x180025a4b  push    r13
0x180025a4d  push    r14
0x180025a4f  push    r15
0x180025a51  lea     rbp, [rsp-1Fh]
0x180025a56  sub     rsp, 0D8h
0x180025a5d  mov     rax, cs:__security_cookie
0x180025a64  xor     rax, rsp
0x180025a67  mov     [rbp+57h+var_50], rax
0x180025a6b  xor     eax, eax
0x180025a6d  mov     [rbp+57h+var_B8], r9
0x180025a71  mov     [rbp+57h+dwWidth], eax
0x180025a74  mov     r12, r9
0x180025a77  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180025a7e  mov     rsi, r8
0x180025a81  movdqu  [rbp+57h+Buf1], xmm0
0x180025a86  mov     [rbp+57h+var_B0], r8
0x180025a8a  mov     r13, rdx
0x180025a8d  movdqu  xmmword ptr [rbp+57h+guidSubtype.Data1], xmm0
0x180025a92  mov     r15, rcx
0x180025a95  mov     [rbp+57h+pStride], eax
0x180025a98  mov     r14d, eax
0x180025a9b  mov     [rbp+57h+pcbImageSize], eax
0x180025a9e  mov     [rbp+57h+ppMFVF], rax
0x180025aa2  mov     edi, eax
0x180025aa4  mov     [rbp+57h+dwWidth], eax
0x180025aa7  mov     ebx, eax
0x180025aa9  mov     [rbp+57h+unHeight], eax
0x180025aac  cmp     cs:byte_18010EC4D, 8
0x180025ab3  jb      short loc_180025AF2
0x180025ab5  mov     rdx, rcx; struct IMFMediaType *
0x180025ab8  lea     rcx, [rbp+57h+var_A8]; this
0x180025abc  call    ??0MediaTypeTracer@@QEAA@PEAUIMFMediaType@@@Z; MediaTypeTracer::MediaTypeTracer(IMFMediaType *)
0x180025ac1  lea     rcx, [rax+8]; this
0x180025ac5  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180025aca  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ad1  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025ad8  mov     edx, 3Bh ; ';'
0x180025add  mov     r9, rax
0x180025ae0  mov     rcx, [rcx+0D8h]
0x180025ae7  call    WPP_SF_s
0x180025aec  mov     r14d, 1
0x180025af2  test    r14b, 1
0x180025af6  jz      short loc_180025B05
0x180025af8  and     r14d, 0FFFFFFFEh
0x180025afc  lea     rcx, [rbp+57h+var_A8]; this
0x180025b00  call    ??1MediaTypeTracer@@UEAA@XZ; MediaTypeTracer::~MediaTypeTracer(void)
0x180025b05  xor     ecx, ecx
0x180025b07  test    r15, r15
0x180025b0a  jnz     short loc_180025B44
0x180025b0c  mov     esi, 80070057h
0x180025b11  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025b18  jb      loc_180025DBA
0x180025b1e  lea     edx, [rcx+3Ch]
0x180025b21  mov     dword ptr [rsp+110h+var_F0], esi
0x180025b25  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b2c  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025b33  xor     r9d, r9d
0x180025b36  mov     rcx, [rcx+10h]
0x180025b3a  call    WPP_SF_qD
0x180025b3f  jmp     loc_180025DBA
0x180025b44  test    r13, r13
0x180025b47  jnz     short loc_180025B67
0x180025b49  mov     eax, 80004003h
0x180025b4e  mov     esi, eax
0x180025b50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025b57  jb      loc_180025DBA
0x180025b5d  lea     edx, [r13+3Dh]
0x180025b61  mov     dword ptr [rsp+110h+var_F0], eax
0x180025b65  jmp     short loc_180025B25
0x180025b67  mov     [r13+0], ecx
0x180025b6b  test    rsi, rsi
0x180025b6e  jnz     short loc_180025B8B
0x180025b70  mov     eax, 80004003h
0x180025b75  mov     esi, eax
0x180025b77  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025b7e  jb      loc_180025DBA
0x180025b84  mov     edx, 3Eh ; '>'
0x180025b89  jmp     short loc_180025B61
0x180025b8b  mov     [rsi], ecx
0x180025b8d  test    r12, r12
0x180025b90  jnz     short loc_180025BAD
0x180025b92  mov     eax, 80004003h
0x180025b97  mov     esi, eax
0x180025b99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025ba0  jb      loc_180025DBA
0x180025ba6  lea     edx, [r12+3Fh]
0x180025bab  jmp     short loc_180025B61
0x180025bad  mov     rax, [rbp+57h+var_B8]
0x180025bb1  lea     r8, [rbp+57h+Buf1]
0x180025bb5  mov     r12b, cl
0x180025bb8  lea     rdx, MF_MT_MAJOR_TYPE
0x180025bbf  mov     [rax], cl
0x180025bc1  mov     rcx, r15
0x180025bc4  mov     rax, [r15]
0x180025bc7  mov     rax, [rax+50h]
0x180025bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bd0  mov     esi, eax
0x180025bd2  test    eax, eax
0x180025bd4  jns     short loc_180025C0B
0x180025bd6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025bdd  jb      loc_180025DB2
0x180025be3  mov     edx, 40h ; '@'
0x180025be8  mov     dword ptr [rsp+110h+var_F0], eax
0x180025bec  mov     rcx, cs:WPP_GLOBAL_Control
0x180025bf3  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025bfa  xor     r9d, r9d
0x180025bfd  mov     rcx, [rcx+10h]
0x180025c01  call    WPP_SF_qD
0x180025c06  jmp     loc_180025DB2
0x180025c0b  mov     rax, [r15]
0x180025c0e  lea     r8, [rbp+57h+guidSubtype]
0x180025c12  lea     rdx, MF_MT_SUBTYPE
0x180025c19  mov     rcx, r15
0x180025c1c  mov     rax, [rax+50h]
0x180025c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c25  mov     esi, eax
0x180025c27  test    eax, eax
0x180025c29  jns     short loc_180025C3F
0x180025c2b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025c32  jb      loc_180025DB2
0x180025c38  mov     edx, 41h ; 'A'
0x180025c3d  jmp     short loc_180025BE8
0x180025c3f  xor     r8d, r8d
0x180025c42  lea     rdx, MF_MT_COMPRESSED
0x180025c49  mov     rcx, r15
0x180025c4c  call    MFGetAttributeUINT32
0x180025c51  test    eax, eax
0x180025c53  jnz     loc_180025E12
0x180025c59  lea     r9, [rbp+57h+unHeight]
0x180025c5d  mov     rcx, r15
0x180025c60  lea     r8, [rbp+57h+dwWidth]
0x180025c64  lea     rdx, MF_MT_FRAME_SIZE
0x180025c6b  call    MFGetAttribute2UINT32asUINT64
0x180025c70  test    eax, eax
0x180025c72  js      loc_180025E0C
0x180025c78  xor     edx, edx
0x180025c7a  lea     rcx, [rbp+57h+ppMFVF]
0x180025c7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180025c83  xor     r8d, r8d; pcbSize
0x180025c86  lea     rdx, [rbp+57h+ppMFVF]; ppMFVF
0x180025c8a  mov     rcx, r15; pMFType
0x180025c8d  call    cs:__imp_MFCreateMFVideoFormatFromMFMediaType
0x180025c93  test    eax, eax
0x180025c95  js      loc_180025E0C
0x180025c9b  mov     rcx, [rbp+57h+ppMFVF]; pVideoFormat
0x180025c9f  call    cs:__imp_MFGetUncompressedVideoFormat
0x180025ca5  mov     edi, [rbp+57h+dwWidth]
0x180025ca8  lea     r8, [rbp+57h+pStride]; pStride
0x180025cac  mov     ecx, eax; format
0x180025cae  mov     edx, edi; dwWidth
0x180025cb0  mov     ebx, eax
0x180025cb2  call    cs:__imp_MFGetStrideForBitmapInfoHeader
0x180025cb8  test    eax, eax
0x180025cba  js      loc_180025E0F
0x180025cc0  mov     eax, 40h ; '@'
0x180025cc5  lea     r8, aNv12_0; "NV12@"
0x180025ccc  xor     ecx, ecx
0x180025cce  cmp     ecx, 4
0x180025cd1  jnb     short loc_180025CED
0x180025cd3  movsxd  rdx, ecx
0x180025cd6  cmp     ebx, [r8+rdx*8]
0x180025cda  jz      short loc_180025CE0
0x180025cdc  inc     ecx
0x180025cde  jmp     short loc_180025CCE
0x180025ce0  mov     eax, [r8+rdx*8+4]
0x180025ce5  test    eax, eax
0x180025ce7  jz      loc_180025E0F
0x180025ced  mov     r9d, [rbp+57h+pStride]
0x180025cf1  lea     ecx, [rax-1]
0x180025cf4  mov     ebx, r9d
0x180025cf7  neg     ebx
0x180025cf9  cmovs   ebx, r9d
0x180025cfd  test    ebx, ecx
0x180025cff  jz      short loc_180025D0A
0x180025d01  lea     edi, [rbx-1]
0x180025d04  not     ecx
0x180025d06  add     edi, eax
0x180025d08  and     edi, ecx
0x180025d0a  cmp     cs:byte_18010EC4D, 8
0x180025d11  jb      short loc_180025D32
0x180025d13  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d1a  mov     [rsp+110h+var_E0], edi
0x180025d1e  mov     [rsp+110h+var_E8], eax
0x180025d22  mov     dword ptr [rsp+110h+var_F0], ebx
0x180025d26  mov     rcx, [rcx+0D8h]
0x180025d2d  call    WPP_SF_dddD
0x180025d32  mov     r8d, [rbp+57h+unHeight]; unHeight
0x180025d36  lea     r9, [rbp+57h+pcbImageSize]; pcbImageSize
0x180025d3a  mov     edx, edi; unWidth
0x180025d3c  lea     rcx, [rbp+57h+guidSubtype]; guidSubtype
0x180025d40  call    cs:__imp_MFCalculateImageSize
0x180025d46  mov     esi, eax
0x180025d48  test    eax, eax
0x180025d4a  jns     short loc_180025D5F
0x180025d4c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025d53  jb      short loc_180025DB2
0x180025d55  mov     edx, 47h ; 'G'
0x180025d5a  jmp     loc_180025BE8
0x180025d5f  mov     edi, 10h
0x180025d64  lea     rdx, MFMediaType_Video; Buf2
0x180025d6b  mov     r8d, edi; Size
0x180025d6e  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180025d72  call    memcmp_0
0x180025d77  test    eax, eax
0x180025d79  jnz     short loc_180025D95
0x180025d7b  mov     r8d, edi; Size
0x180025d7e  lea     rdx, MFVideoFormat_L8; Buf2
0x180025d85  lea     rcx, [rbp+57h+guidSubtype]; Buf1
0x180025d89  call    memcmp_0
0x180025d8e  test    eax, eax
0x180025d90  jnz     short loc_180025D95
0x180025d92  mov     [rbp+57h+pStride], ebx
0x180025d95  mov     r12d, 2
0x180025d9b  mov     eax, [rbp+57h+pStride]
0x180025d9e  mov     rcx, [rbp+57h+var_B0]
0x180025da2  mov     [r13+0], eax
0x180025da6  mov     eax, [rbp+57h+pcbImageSize]
0x180025da9  mov     [rcx], eax
0x180025dab  mov     rax, [rbp+57h+var_B8]
0x180025daf  mov     [rax], r12b
0x180025db2  test    esi, esi
0x180025db4  jns     loc_180025F40
0x180025dba  cmp     cs:byte_18010EC4D, 1
0x180025dc1  jb      short loc_180025E03
0x180025dc3  mov     rdx, r15; struct IMFMediaType *
0x180025dc6  lea     rcx, [rbp+57h+var_A8]; this
0x180025dca  or      r14d, 4
0x180025dce  call    ??0MediaTypeTracer@@QEAA@PEAUIMFMediaType@@@Z; MediaTypeTracer::MediaTypeTracer(IMFMediaType *)
0x180025dd3  lea     rcx, [rax+8]; this
0x180025dd7  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180025ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025de3  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025dea  mov     edx, 48h ; 'H'
0x180025def  mov     [rsp+110h+var_F0], rax
0x180025df4  mov     r9d, esi
0x180025df7  mov     rcx, [rcx+0D8h]
0x180025dfe  call    WPP_SF_Ds
0x180025e03  test    r14b, 4
0x180025e07  jmp     loc_180025F97
0x180025e0c  mov     edi, [rbp+57h+dwWidth]
0x180025e0f  mov     ebx, [rbp+57h+unHeight]
0x180025e12  cmp     cs:byte_18010EC4D, 8
0x180025e19  mov     r12d, 2
0x180025e1f  jb      short loc_180025E5B
0x180025e21  lea     rdx, [rbp+57h+Buf1]; struct _GUID *
0x180025e25  or      r14d, r12d
0x180025e28  lea     rcx, [rbp+57h+var_A8]; this
0x180025e2c  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180025e31  mov     rcx, rax; this
0x180025e34  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180025e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e40  lea     edx, [r12+40h]
0x180025e45  mov     r9, rax
0x180025e48  lea     r8, WPP_a631a4618ec233985c5c4a2e9723096c_Traceguids
0x180025e4f  mov     rcx, [rcx+0D8h]
0x180025e56  call    WPP_SF_s
0x180025e5b  test    r12b, r14b
0x180025e5e  jz      short loc_180025E6D
0x180025e60  and     r14d, 0FFFFFFFDh
0x180025e64  lea     rcx, [rbp+57h+var_A8]; this
0x180025e68  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180025e6d  mov     [rbp+57h+pStride], 0
0x180025e74  mov     r12b, 1
0x180025e77  mov     [rbp+57h+pcbImageSize], 0
0x180025e7e  test    edi, edi
0x180025e80  jz      short loc_180025EEF
0x180025e82  test    ebx, ebx
0x180025e84  jz      short loc_180025EEF
0x180025e86  mov     ecx, ebx
0x180025e88  mov     edx, 0FFFFFFFFh
0x180025e8d  mov     eax, edi
0x180025e8f  imul    rcx, rax
0x180025e93  cmp     rcx, rdx
0x180025e96  ja      short loc_180025ED0
0x180025e98  mov     eax, ecx
0x180025e9a  shl     rax, 2
0x180025e9e  cmp     rax, rdx
0x180025ea1  ja      short loc_180025EAD
0x180025ea3  mov     [rbp+57h+pcbImageSize], eax
0x180025ea6  xor     esi, esi
0x180025ea8  jmp     loc_180025D9B
0x180025ead  mov     [rbp+57h+pcbImageSize], edx
0x180025eb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180025eb7  mov     esi, 80070216h
0x180025ebc  jb      loc_180025DB2
0x180025ec2  mov     edx, 44h ; 'D'
0x180025ec7  mov     dword ptr [rsp+110h+var_F0], esi
0x180025ecb  jmp     loc_180025BEC
0x180025ed0  mov     [rbp+57h+pcbImageSize], edx
0x180025ed3  mov     esi, 80070216h
0x180025ed8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r12b; MFWppLevels g_wppLevels
0x180025edf  jb      loc_180025DBA
0x180025ee5  mov     edx, 43h ; 'C'
0x180025eea  jmp     loc_180025B21
0x180025eef  xor     r8d, r8d
  ... truncated ...
```
