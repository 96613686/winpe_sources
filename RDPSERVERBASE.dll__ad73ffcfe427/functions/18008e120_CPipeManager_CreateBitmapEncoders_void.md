# CPipeManager::CreateBitmapEncoders(void)

- ea: `0x18008e120`
- end: `0x18008ea3d`
- name: `?CreateBitmapEncoders@CPipeManager@@IEAAJXZ`
- size: `2333`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18009d364`

## callees

- `0x18000202c`
- `0x18000ce04`
- `0x180010d14`
- `0x180076090`
- `0x180079770`
- `0x18008b9e8`
- `0x18008e120`
- `0x180158180`
- `0x1801756e8`
- `0x18019c010`

## import_xrefs

- `RDPBASE!?AlphaCompressor__CreateInstance@@YAJPEAPEAUIRdpImageCompressor@@@Z` at `0x18008e87f`
- `RDPBASE!?AlphaCompressor__CreateInstance@@YAJPEAPEAUIRdpImageCompressor@@@Z` at `0x18008e87f`
- `RDPBASE!?CreateInstance@PlanarCompressor@@SAJGGEHHHPEAPEAUIRdpImageCompressor@@@Z` at `0x18008e5d0`
- `RDPBASE!?CreateInstance@PlanarCompressor@@SAJGGEHHHPEAPEAUIRdpImageCompressor@@@Z` at `0x18008e5d0`
- `RDPBASE!CRDPCacCodecEncoder_CreateInstance` at `0x18008e36c`
- `RDPBASE!CRDPCacCodecEncoder_CreateInstance` at `0x18008e36c`
- `RDPBASE!CRDPNsCodec_CreateInstance` at `0x18008e1b8`
- `RDPBASE!CRDPNsCodec_CreateInstance` at `0x18008e1b8`

## string_xrefs

- `0x18008e278`: `AddCompressorInstance failed`
- `0x18008e43c`: `AddCompressorInstance failed`
- `0x18008e6d6`: `AddCompressorInstance failed`
- `0x18008e7c4`: `AddCompressorInstance failed`
- `0x18008e194`: `RDPCodecCache::NSCodec`
- `0x18008e1e1`: `CRDPNsCodec_CreateInstance failed!`
- `0x18008e250`: `PipeManagerError_CreateBmpEncAddNSCodecInstanceFail`
- `0x18008e291`: `CreateBitmapEncoders`
- `0x18008e455`: `CreateBitmapEncoders`
- `0x18008e624`: `CreateBitmapEncoders`
- `0x18008e6ef`: `CreateBitmapEncoders`
- `0x18008e7dd`: `CreateBitmapEncoders`
- `0x18008e8d3`: `CreateBitmapEncoders`
- `0x18008e9ab`: `CreateBitmapEncoders`
- `0x18008e348`: `RDPCodecCache::ImgCaCodec`
- `0x18008e39c`: `CRDPCacCodecEncoder_CreateInstance failed!`
- `0x18008e414`: `PipeManagerError_CreateBmpEncAddImgCaCodecInstanceFail`
- `0x18008e6b2`: `PipeManagerError_CreateBmpEncAddImgCaCodecInstanceFail`
- `0x18008e539`: `ClearCompressor::CreateInstance failed!`
- `0x18008e5e3`: `PipeManagerError_CreateBmpEncCreatePlanarInstanceFail`
- `0x18008e60b`: `PlanarCompressor::CreateInstance failed`
- `0x18008e79c`: `PipeManagerError_CreateBmpEncAddPlanarInstanceFail`
- `0x18008e892`: `PipeManagerError_CreateBmpEncCreateAlphaInstanceFail`
- `0x18008e8ba`: `Failed to create the alpha compressor`
- `0x18008e96a`: `PipeManagerError_CreateBmpEncAddAlphaInstanceFail`
- `0x18008e992`: `AddCompressorInstance failed for the alpha compressor`

## pseudocode

```c
__int64 __fastcall CPipeManager::CreateBitmapEncoders(CPipeManager *this)
{
  _QWORD *v1; // r14
  __int64 v3; // rcx
  unsigned int v4; // ebx
  _QWORD *v5; // r15
  __int64 v6; // r8
  int v7; // eax
  char v8; // bl
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  signed int v12; // eax
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  __int16 *v16; // rdx
  const char **v17; // rax
  _QWORD *v18; // rsi
  __int64 v19; // r8
  int v20; // eax
  char v21; // bl
  unsigned int v22; // eax
  __int64 *v23; // rcx
  __int64 v24; // rax
  signed int v25; // eax
  int v26; // eax
  __int64 v27; // r8
  char v28; // bl
  unsigned int v29; // eax
  signed int v30; // eax
  __int64 v31; // r8
  __int64 *v32; // rcx
  __int64 v33; // rax
  signed int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  __int64 *v38; // rcx
  __int64 v39; // rax
  signed int v40; // eax
  _QWORD *v41; // r14
  signed int v42; // eax
  __int64 v43; // r8
  __int64 *v44; // rcx
  __int64 v45; // rax
  signed int v46; // eax
  int v48; // [rsp+20h] [rbp-60h]
  const char **v49; // [rsp+30h] [rbp-50h]
  const char **v50; // [rsp+40h] [rbp-40h]
  const char *v51; // [rsp+50h] [rbp-30h] BYREF
  const char *v52; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v53[2]; // [rsp+60h] [rbp-20h] BYREF
  __int128 v54; // [rsp+70h] [rbp-10h] BYREF
  int v55; // [rsp+C0h] [rbp+40h] BYREF
  unsigned int v56; // [rsp+C8h] [rbp+48h] BYREF
  struct IRdpImageCompressor *v57; // [rsp+D0h] [rbp+50h] BYREF
  struct ClearCompressor *v58; // [rsp+D8h] [rbp+58h] BYREF

  v1 = (_QWORD *)((char *)this + 13048);
  v57 = 0;
  v3 = *((_QWORD *)this + 1631);
  if ( !v3 )
  {
    v4 = -2147024809;
    goto LABEL_65;
  }
  v5 = (_QWORD *)((char *)this + 13016);
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 80LL))(v3, 1) )
  {
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, GUID *, struct IRdpImageCompressor **))(*(_QWORD *)*v5 + 48LL))(
           *v5,
           L"RDPCodecCache::NSCodec",
           &IID_IRdpImageCompressor,
           &v57) < 0 )
    {
      v7 = CRDPNsCodec_CreateInstance(0, &IID_IRdpImageCompressor, &v57);
      v8 = v7;
      if ( v7 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          207,
          (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)"CRDPNsCodec_CreateInstance failed!",
          v8);
      }
    }
    if ( v57 )
    {
      v10 = (__int64 *)*((_QWORD *)this + 6127);
      LOBYTE(v6) = 1;
      v11 = *v10;
      v54 = (__int128)CODEC_GUID_NSCODEC;
      v12 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64))(v11 + 24))(v10, &v54, v6);
      v4 = v12;
      if ( v12 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_CreateBmpEncAddNSCodecInstanceFail",
          (char *)0x1FC6,
          v12,
          v48);
        v15 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_65;
        v55 = 8135;
        v58 = (struct ClearCompressor *)"AddCompressorInstance failed";
        v16 = (__int16 *)qword_1802767F0;
        v51 = "CreateBitmapEncoders";
        v52 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v53[0] = "Error HResult failed";
        v50 = &v51;
        v49 = &v52;
        v17 = (const char **)v53;
LABEL_14:
        v56 = v4;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v15,
          (_DWORD)v16,
          v13,
          v14,
          (__int64)v17,
          (__int64)&v56,
          (__int64)v49,
          (__int64)&v55,
          (__int64)v50,
          (__int64)&v58);
        goto LABEL_65;
      }
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v1 + 88LL))(*v1, 1);
    }
    TCntPtr<IRdpImageCompressor>::operator=(&v57, 0);
    v18 = (_QWORD *)((char *)this + 13048);
  }
  else
  {
    v18 = v1;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v1 + 80LL))(*v1, 2) )
  {
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, GUID *, struct IRdpImageCompressor **))(*(_QWORD *)*v5 + 48LL))(
           *v5,
           L"RDPCodecCache::ImgCaCodec",
           &IID_IRdpImageCompressor,
           &v57) < 0 )
    {
      v20 = CRDPCacCodecEncoder_CreateInstance(0, &IID_IRdpImageCompressor, &v57);
      v21 = v20;
      if ( v20 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          209,
          (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
          v22,
          (__int64)"CRDPCacCodecEncoder_CreateInstance failed!",
          v21);
      }
    }
    if ( v57 )
    {
      v23 = (__int64 *)*((_QWORD *)this + 6127);
      LOBYTE(v19) = 5;
      v24 = *v23;
      v54 = (__int128)CODEC_GUID_IMGCACODEC;
      v25 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64))(v24 + 24))(v23, &v54, v19);
      v4 = v25;
      if ( v25 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_CreateBmpEncAddImgCaCodecInstanceFail",
          (char *)0x1FE9,
          v25,
          v48);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_65;
        v55 = 8170;
        v58 = (struct ClearCompressor *)"AddCompressorInstance failed";
        v16 = word_1802767A2;
        v53[0] = "CreateBitmapEncoders";
        v52 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v51 = "Error HResult failed";
        v50 = (const char **)v53;
        v49 = &v52;
        v17 = &v51;
        goto LABEL_14;
      }
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1631) + 88LL))(*((_QWORD *)this + 1631), 2);
    }
    TCntPtr<IRdpImageCompressor>::operator=(&v57, 0);
    v18 = (_QWORD *)((char *)this + 13048);
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1631) + 80LL))(
          *((_QWORD *)this + 1631),
          4) )
  {
LABEL_39:
    if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1631) + 80LL))(
           *((_QWORD *)this + 1631),
           6) )
    {
      v30 = PlanarCompressor::CreateInstance(0, 0, 0, 0, 1, 1, &v57);
      v4 = v30;
      if ( v30 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_CreateBmpEncCreatePlanarInstanceFail",
          (char *)0x2016,
          v30,
          v48);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_65;
        v55 = 8215;
        v58 = (struct ClearCompressor *)"PlanarCompressor::CreateInstance failed";
        v16 = &word_180276706;
        *(_QWORD *)&v54 = "CreateBitmapEncoders";
        v53[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v52 = "Error HResult failed";
        v50 = (const char **)&v54;
        v49 = (const char **)v53;
        v17 = &v52;
        goto LABEL_14;
      }
      if ( v57 )
      {
        v38 = (__int64 *)*((_QWORD *)this + 6127);
        LOBYTE(v31) = 10;
        v39 = *v38;
        v54 = (__int128)CODEC_GUID_PLANAR;
        v40 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64))(v39 + 24))(v38, &v54, v31);
        v4 = v40;
        if ( v40 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
            "PipeManagerError_CreateBmpEncAddPlanarInstanceFail",
            (char *)0x2020,
            v40,
            v48);
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_65;
          v55 = 8225;
          v58 = (struct ClearCompressor *)"AddCompressorInstance failed";
          v16 = (__int16 *)qword_1802766B8;
          *(_QWORD *)&v54 = "CreateBitmapEncoders";
          v53[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
          v52 = "Error HResult failed";
          v50 = (const char **)&v54;
          v49 = (const char **)v53;
          v17 = &v52;
          goto LABEL_14;
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v18 + 88LL))(*v18, 6);
      }
      TCntPtr<IRdpImageCompressor>::operator=(&v57, 0);
      v41 = (_QWORD *)((char *)this + 13048);
    }
    else
    {
      v41 = v18;
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v18 + 80LL))(*v18, 11) )
    {
      v42 = AlphaCompressor__CreateInstance(&v57);
      v4 = v42;
      if ( v42 < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
          "PipeManagerError_CreateBmpEncCreateAlphaInstanceFail",
          (char *)0x202E,
          v42,
          v48);
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_65;
        v55 = 8239;
        v58 = (struct ClearCompressor *)"Failed to create the alpha compressor";
        v16 = word_18027666A;
        *(_QWORD *)&v54 = "CreateBitmapEncoders";
        v53[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
        v52 = "Error HResult failed";
        v50 = (const char **)&v54;
        v49 = (const char **)v53;
        v17 = &v52;
        goto LABEL_14;
      }
      if ( v57 )
      {
        v44 = (__int64 *)*((_QWORD *)this + 6127);
        LOBYTE(v43) = 12;
        v45 = *v44;
        v54 = CODEC_GUID_ALPHACODEC;
        v46 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64))(v45 + 24))(v44, &v54, v43);
        v4 = v46;
        if ( v46 < 0 )
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
            "PipeManagerError_CreateBmpEncAddAlphaInstanceFail",
            (char *)0x2038,
            v46,
            v48);
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_65;
          v55 = 8249;
          v58 = (struct ClearCompressor *)"AddCompressorInstance failed for the alpha compressor";
          v16 = (__int16 *)&dword_18027661C;
          *(_QWORD *)&v54 = "CreateBitmapEncoders";
          v53[0] = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
          v52 = "Error HResult failed";
          v50 = (const char **)&v54;
          v49 = (const char **)v53;
          v17 = &v52;
          goto LABEL_14;
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v41 + 88LL))(*v41, 11);
      }
      TCntPtr<IRdpImageCompressor>::operator=(&v57, 0);
    }
    v4 = 0;
    goto LABEL_65;
  }
  v58 = 0;
  v26 = ClearCompressor::CreateInstance(&v58);
  v28 = v26;
  if ( v26 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v29 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        211,
        (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
        v29,
        (__int64)"ClearCompressor::CreateInstance failed!",
        v28);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 1631) + 88LL))(*((_QWORD *)this + 1631), 4);
    goto LABEL_38;
  }
  v32 = (__int64 *)*((_QWORD *)this + 6127);
  LOBYTE(v27) = 8;
  v33 = *v32;
  v54 = (__int128)CODEC_GUID_CLEARCODEC;
  v34 = (*(__int64 (__fastcall **)(__int64 *, __int128 *, __int64, struct ClearCompressor *))(v33 + 24))(
          v32,
          &v54,
          v27,
          v58);
  v4 = v34;
  if ( v34 >= 0 )
  {
LABEL_38:
    TCntPtr<ClearCompressor>::SafeRelease(&v58);
    v18 = (_QWORD *)((char *)this + 13048);
    goto LABEL_39;
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
    (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
    "PipeManagerError_CreateBmpEncAddImgCaCodecInstanceFail",
    (char *)0x2001,
    v34,
    v48);
  if ( (unsigned int)CallbackContext > 2 )
  {
    v55 = 8194;
    v53[0] = "AddCompressorInstance failed";
    v56 = v4;
    v52 = "CreateBitmapEncoders";
    v51 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
    *(_QWORD *)&v54 = "Error HResult failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v35,
      (unsigned int)&dword_180276754,
      v36,
      v37,
      (__int64)&v54,
      (__int64)&v56,
      (__int64)&v51,
      (__int64)&v55,
      (__int64)&v52,
      (__int64)v53);
  }
  TCntPtr<ClearCompressor>::SafeRelease(&v58);
LABEL_65:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v57);
  return v4;
}

```

## disassembly

```asm
0x18008e120  push    rbp
0x18008e122  push    rbx
0x18008e123  push    rsi
0x18008e124  push    rdi
0x18008e125  push    r12
0x18008e127  push    r14
0x18008e129  push    r15
0x18008e12b  mov     rbp, rsp
0x18008e12e  sub     rsp, 80h
0x18008e135  lea     r14, [rcx+32F8h]
0x18008e13c  mov     [rbp+arg_10], 0
0x18008e144  mov     rdi, rcx
0x18008e147  mov     rcx, [r14]
0x18008e14a  test    rcx, rcx
0x18008e14d  jnz     short loc_18008E159
0x18008e14f  mov     ebx, 80070057h
0x18008e154  jmp     loc_18008EA20
0x18008e159  mov     rax, [rcx]
0x18008e15c  lea     r15, [rdi+32D8h]
0x18008e163  mov     edx, 1
0x18008e168  mov     rax, [rax+50h]
0x18008e16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e171  lea     rsi, WPP_GLOBAL_Control
0x18008e178  mov     r12d, 2
0x18008e17e  test    eax, eax
0x18008e180  jz      loc_18008E31D
0x18008e186  mov     rcx, [r15]
0x18008e189  lea     r9, [rbp+arg_10]
0x18008e18d  lea     r8, IID_IRdpImageCompressor
0x18008e194  lea     rdx, aRdpcodeccacheN; "RDPCodecCache::NSCodec"
0x18008e19b  mov     rax, [rcx]
0x18008e19e  mov     rax, [rax+30h]
0x18008e1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e1a7  test    eax, eax
0x18008e1a9  jns     short loc_18008E210
0x18008e1ab  lea     r8, [rbp+arg_10]
0x18008e1af  xor     ecx, ecx
0x18008e1b1  lea     rdx, IID_IRdpImageCompressor
0x18008e1b8  call    cs:__imp_CRDPNsCodec_CreateInstance
0x18008e1be  mov     ebx, eax
0x18008e1c0  test    eax, eax
0x18008e1c2  jns     short loc_18008E210
0x18008e1c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e1cb  cmp     rcx, rsi
0x18008e1ce  jz      short loc_18008E210
0x18008e1d0  test    byte ptr [rcx+1Ch], 8
0x18008e1d4  jz      short loc_18008E210
0x18008e1d6  cmp     [rcx+19h], r12b
0x18008e1da  jb      short loc_18008E210
0x18008e1dc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008e1e1  lea     rcx, aCrdpnscodecCre; "CRDPNsCodec_CreateInstance failed!"
0x18008e1e8  mov     dword ptr [rsp+80h+var_58], ebx
0x18008e1ec  mov     qword ptr [rsp+80h+var_60], rcx; int
0x18008e1f1  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x18008e1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e1ff  mov     edx, 0CFh
0x18008e204  mov     r9d, eax
0x18008e207  mov     rcx, [rcx+10h]
0x18008e20b  call    WPP_SF_DsD
0x18008e210  mov     r9, [rbp+arg_10]
0x18008e214  test    r9, r9
0x18008e217  jz      loc_18008E2F5
0x18008e21d  mov     rcx, [rdi+0BF78h]
0x18008e224  lea     rdx, [rbp+var_10]
0x18008e228  movups  xmm0, xmmword ptr cs:CODEC_GUID_NSCODEC.Data1
0x18008e22f  mov     r8b, 1
0x18008e232  mov     rax, [rcx]
0x18008e235  movdqu  [rbp+var_10], xmm0
0x18008e23a  mov     rax, [rax+18h]
0x18008e23e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e243  mov     ebx, eax
0x18008e245  test    eax, eax
0x18008e247  jns     loc_18008E309
0x18008e24d  mov     r9d, eax; unsigned int
0x18008e250  lea     rdx, aPipemanagererr_77; "PipeManagerError_CreateBmpEncAddNSCodec"...
0x18008e257  mov     r8d, 1FC6h; char *
0x18008e25d  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008e264  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008e269  mov     ecx, cs:CallbackContext
0x18008e26f  cmp     ecx, r12d
0x18008e272  jbe     loc_18008EA20
0x18008e278  lea     rax, aAddcompressori_0; "AddCompressorInstance failed"
0x18008e27f  mov     [rbp+arg_0], 1FC7h
0x18008e286  mov     [rbp+arg_18], rax
0x18008e28a  lea     rdx, qword_1802767F0
0x18008e291  lea     rax, aCreatebitmapen; "CreateBitmapEncoders"
0x18008e298  mov     [rbp+var_30], rax
0x18008e29c  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008e2a3  mov     [rbp+var_28], rax
0x18008e2a7  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008e2ae  mov     [rbp+var_20], rax
0x18008e2b2  lea     rax, [rbp+arg_18]
0x18008e2b6  mov     [rsp+80h+var_38], rax
0x18008e2bb  lea     rax, [rbp+var_30]
0x18008e2bf  mov     [rsp+80h+var_40], rax
0x18008e2c4  lea     rax, [rbp+arg_0]
0x18008e2c8  mov     [rsp+80h+var_48], rax
0x18008e2cd  lea     rax, [rbp+var_28]
0x18008e2d1  mov     [rsp+80h+var_50], rax
0x18008e2d6  lea     rax, [rbp+arg_8]
0x18008e2da  mov     [rsp+80h+var_58], rax
0x18008e2df  lea     rax, [rbp+var_20]
0x18008e2e3  mov     qword ptr [rsp+80h+var_60], rax
0x18008e2e8  mov     [rbp+arg_8], ebx
0x18008e2eb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008e2f0  jmp     loc_18008EA20
0x18008e2f5  mov     rcx, [r14]
0x18008e2f8  mov     edx, 1
0x18008e2fd  mov     rax, [rcx]
0x18008e300  mov     rax, [rax+58h]
0x18008e304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e309  xor     edx, edx
0x18008e30b  lea     rcx, [rbp+arg_10]
0x18008e30f  call    ??4?$TCntPtr@UIRdpImageCompressor@@@@QEAAPEAUIRdpImageCompressor@@PEAU1@@Z; TCntPtr<IRdpImageCompressor>::operator=(IRdpImageCompressor *)
0x18008e314  lea     rsi, [rdi+32F8h]
0x18008e31b  jmp     short loc_18008E320
0x18008e31d  mov     rsi, r14
0x18008e320  mov     rcx, [r14]
0x18008e323  mov     edx, r12d
0x18008e326  mov     rax, [rcx]
0x18008e329  mov     rax, [rax+50h]
0x18008e32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e332  test    eax, eax
0x18008e334  jz      loc_18008E4D6
0x18008e33a  mov     rcx, [r15]
0x18008e33d  lea     r9, [rbp+arg_10]
0x18008e341  lea     r8, IID_IRdpImageCompressor
0x18008e348  lea     rdx, aRdpcodeccacheI; "RDPCodecCache::ImgCaCodec"
0x18008e34f  mov     rax, [rcx]
0x18008e352  mov     rax, [rax+30h]
0x18008e356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e35b  test    eax, eax
0x18008e35d  jns     short loc_18008E3CD
0x18008e35f  lea     r8, [rbp+arg_10]
0x18008e363  xor     ecx, ecx
0x18008e365  lea     rdx, IID_IRdpImageCompressor
0x18008e36c  call    cs:__imp_CRDPCacCodecEncoder_CreateInstance
0x18008e372  mov     ebx, eax
0x18008e374  test    eax, eax
0x18008e376  jns     short loc_18008E3CD
0x18008e378  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e37f  lea     r15, WPP_GLOBAL_Control
0x18008e386  cmp     rcx, r15
0x18008e389  jz      short loc_18008E3D4
0x18008e38b  test    byte ptr [rcx+1Ch], 8
0x18008e38f  jz      short loc_18008E3D4
0x18008e391  cmp     [rcx+19h], r12b
0x18008e395  jb      short loc_18008E3D4
0x18008e397  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008e39c  lea     rcx, aCrdpcaccodecen; "CRDPCacCodecEncoder_CreateInstance fail"...
0x18008e3a3  mov     dword ptr [rsp+80h+var_58], ebx
0x18008e3a7  mov     qword ptr [rsp+80h+var_60], rcx
0x18008e3ac  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x18008e3b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e3ba  mov     edx, 0D1h
0x18008e3bf  mov     r9d, eax
0x18008e3c2  mov     rcx, [rcx+10h]
0x18008e3c6  call    WPP_SF_DsD
0x18008e3cb  jmp     short loc_18008E3D4
0x18008e3cd  lea     r15, WPP_GLOBAL_Control
0x18008e3d4  mov     r9, [rbp+arg_10]
0x18008e3d8  test    r9, r9
0x18008e3db  jz      loc_18008E4AC
0x18008e3e1  mov     rcx, [rdi+0BF78h]
0x18008e3e8  lea     rdx, [rbp+var_10]
0x18008e3ec  movups  xmm0, xmmword ptr cs:CODEC_GUID_IMGCACODEC.Data1
0x18008e3f3  mov     r8b, 5
0x18008e3f6  mov     rax, [rcx]
0x18008e3f9  movdqu  [rbp+var_10], xmm0
0x18008e3fe  mov     rax, [rax+18h]
0x18008e402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e407  mov     ebx, eax
0x18008e409  test    eax, eax
0x18008e40b  jns     loc_18008E4C2
0x18008e411  mov     r9d, eax; unsigned int
0x18008e414  lea     rdx, aPipemanagererr_56; "PipeManagerError_CreateBmpEncAddImgCaCo"...
0x18008e41b  mov     r8d, 1FE9h; char *
0x18008e421  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008e428  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008e42d  mov     eax, cs:CallbackContext
0x18008e433  cmp     eax, r12d
0x18008e436  jbe     loc_18008EA20
0x18008e43c  lea     rax, aAddcompressori_0; "AddCompressorInstance failed"
0x18008e443  mov     [rbp+arg_0], 1FEAh
0x18008e44a  mov     [rbp+arg_18], rax
0x18008e44e  lea     rdx, word_1802767A2
0x18008e455  lea     rax, aCreatebitmapen; "CreateBitmapEncoders"
0x18008e45c  mov     [rbp+var_20], rax
0x18008e460  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008e467  mov     [rbp+var_28], rax
0x18008e46b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008e472  mov     [rbp+var_30], rax
0x18008e476  lea     rax, [rbp+arg_18]
0x18008e47a  mov     [rsp+80h+var_38], rax
0x18008e47f  lea     rax, [rbp+var_20]
0x18008e483  mov     [rsp+80h+var_40], rax
0x18008e488  lea     rax, [rbp+arg_0]
0x18008e48c  mov     [rsp+80h+var_48], rax
0x18008e491  lea     rax, [rbp+var_28]
0x18008e495  mov     [rsp+80h+var_50], rax
0x18008e49a  lea     rax, [rbp+arg_8]
0x18008e49e  mov     [rsp+80h+var_58], rax
0x18008e4a3  lea     rax, [rbp+var_30]
0x18008e4a7  jmp     loc_18008E2E3
0x18008e4ac  mov     rcx, [rdi+32F8h]
0x18008e4b3  mov     edx, r12d
0x18008e4b6  mov     rax, [rcx]
0x18008e4b9  mov     rax, [rax+58h]
0x18008e4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e4c2  xor     edx, edx
0x18008e4c4  lea     rcx, [rbp+arg_10]
0x18008e4c8  call    ??4?$TCntPtr@UIRdpImageCompressor@@@@QEAAPEAUIRdpImageCompressor@@PEAU1@@Z; TCntPtr<IRdpImageCompressor>::operator=(IRdpImageCompressor *)
0x18008e4cd  lea     rsi, [rdi+32F8h]
0x18008e4d4  jmp     short loc_18008E4DD
0x18008e4d6  lea     r15, WPP_GLOBAL_Control
0x18008e4dd  mov     rcx, [rdi+32F8h]
0x18008e4e4  mov     r14d, 4
0x18008e4ea  mov     edx, r14d
0x18008e4ed  mov     rax, [rcx]
0x18008e4f0  mov     rax, [rax+50h]
0x18008e4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e4f9  test    eax, eax
0x18008e4fb  jz      loc_18008E58E
0x18008e501  lea     rcx, [rbp+arg_18]; struct ClearCompressor **
0x18008e505  mov     [rbp+arg_18], 0
0x18008e50d  call    ?CreateInstance@ClearCompressor@@SAJPEAPEAV1@@Z; ClearCompressor::CreateInstance(ClearCompressor * *)
0x18008e512  mov     ebx, eax
0x18008e514  test    eax, eax
0x18008e516  jns     loc_18008E67B
0x18008e51c  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e523  cmp     rcx, r15
0x18008e526  jz      short loc_18008E568
0x18008e528  test    byte ptr [rcx+1Ch], 8
0x18008e52c  jz      short loc_18008E568
0x18008e52e  cmp     [rcx+19h], r12b
0x18008e532  jb      short loc_18008E568
0x18008e534  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008e539  lea     rcx, aClearcompresso_0; "ClearCompressor::CreateInstance failed!"
0x18008e540  mov     dword ptr [rsp+80h+var_58], ebx
0x18008e544  mov     qword ptr [rsp+80h+var_60], rcx; int
0x18008e549  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x18008e550  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e557  mov     edx, 0D3h
0x18008e55c  mov     r9d, eax
0x18008e55f  mov     rcx, [rcx+10h]
0x18008e563  call    WPP_SF_DsD
0x18008e568  mov     rcx, [rdi+32F8h]
0x18008e56f  mov     edx, r14d
0x18008e572  mov     rax, [rcx]
0x18008e575  mov     rax, [rax+58h]
0x18008e579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e57e  lea     rcx, [rbp+arg_18]
0x18008e582  call    ?SafeRelease@?$TCntPtr@VClearCompressor@@@@AEAAXXZ; TCntPtr<ClearCompressor>::SafeRelease(void)
0x18008e587  lea     rsi, [rdi+32F8h]
0x18008e58e  mov     rcx, [rdi+32F8h]
0x18008e595  mov     r14d, 6
0x18008e59b  mov     edx, r14d
0x18008e59e  mov     rax, [rcx]
0x18008e5a1  mov     rax, [rax+50h]
0x18008e5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e5aa  test    eax, eax
0x18008e5ac  jz      loc_18008E85A
0x18008e5b2  lea     rax, [rbp+arg_10]
0x18008e5b6  xor     edx, edx
0x18008e5b8  mov     [rsp+80h+var_50], rax
0x18008e5bd  xor     ecx, ecx
0x18008e5bf  xor     r9d, r9d
0x18008e5c2  xor     r8d, r8d
0x18008e5c5  lea     eax, [rdx+1]
0x18008e5c8  mov     dword ptr [rsp+80h+var_58], eax
0x18008e5cc  mov     [rsp+80h+var_60], eax; int
0x18008e5d0  call    cs:__imp_?CreateInstance@PlanarCompressor@@SAJGGEHHHPEAPEAUIRdpImageCompressor@@@Z; PlanarCompressor::CreateInstance(ushort,ushort,uchar,int,int,int,IRdpImageCompressor * *)
0x18008e5d6  mov     ebx, eax
0x18008e5d8  test    eax, eax
0x18008e5da  jns     loc_18008E75C
0x18008e5e0  mov     r9d, eax; unsigned int
0x18008e5e3  lea     rdx, aPipemanagererr_103; "PipeManagerError_CreateBmpEncCreatePlan"...
0x18008e5ea  mov     r8d, 2016h; char *
0x18008e5f0  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x18008e5f7  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x18008e5fc  mov     eax, cs:CallbackContext
0x18008e602  cmp     eax, r12d
0x18008e605  jbe     loc_18008EA20
0x18008e60b  lea     rax, aPlanarcompress; "PlanarCompressor::CreateInstance failed"
0x18008e612  mov     [rbp+arg_0], 2017h
0x18008e619  mov     [rbp+arg_18], rax
0x18008e61d  lea     rdx, word_180276706
0x18008e624  lea     rax, aCreatebitmapen; "CreateBitmapEncoders"
0x18008e62b  mov     qword ptr [rbp+var_10], rax
0x18008e62f  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x18008e636  mov     [rbp+var_20], rax
0x18008e63a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008e641  mov     [rbp+var_28], rax
0x18008e645  lea     rax, [rbp+arg_18]
0x18008e649  mov     [rsp+80h+var_38], rax
0x18008e64e  lea     rax, [rbp+var_10]
0x18008e652  mov     [rsp+80h+var_40], rax
0x18008e657  lea     rax, [rbp+arg_0]
0x18008e65b  mov     [rsp+80h+var_48], rax
0x18008e660  lea     rax, [rbp+var_20]
  ... truncated ...
```
