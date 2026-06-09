# CRDPWireEncoder::Reset(IRDPCaps *,ulong,int,uint,ulong,ulong,ulong)

- ea: `0x18005bbe0`
- end: `0x18005c7b3`
- name: `?Reset@CRDPWireEncoder@@UEAAJPEAUIRDPCaps@@KHIKKK@Z`
- size: `3027`
- prototype: `__int64 __fastcall(CRDPWireEncoder *this, struct IRDPCaps *, int, int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180004a94`
- `0x180006210`
- `0x180019a80`
- `0x180019ab0`
- `0x180046a84`
- `0x18005bbe0`
- `0x1800711c8`
- `0x18007125c`
- `0x180072198`
- `0x1800721d4`
- `0x1800723e8`
- `0x18007969c`
- `0x1800d2634`
- `0x1800d2980`
- `0x1800d2b3c`
- `0x180162010`

## string_xrefs

- `0x18005bea7`: `GetCapSet(TS_CAPSETTYPE_SURFACE_COMMANDS) failed!`
- `0x18005bef7`: `Surface commands supported`
- `0x18005bf0c`: `Surface commands are NOT supported, disabling negotiated codecs`
- `0x18005c13c`: `NSCodec compressor negotiated`
- `0x18005c19c`: `Video CAC compressor negotiated on`
- `0x18005c206`: `Image CAC compressor negotiated on`
- `0x18005c266`: `onecore\termsrv\rdpplatform\protocol\crdporderencoder.cpp`
- `0x18005c731`: `onecore\termsrv\rdpplatform\protocol\crdporderencoder.cpp`
- `0x18005c3d7`: `Failed to create the CA image compressor`
- `0x18005c4d9`: `Failed to create the CA video compressor`
- `0x18005c5b4`: `Failed to create the NSCodec compressor`
- `0x18005c62d`: `Default codec is Win6 Planar; disabling rev3 cache and SetSurfaceBits(ex) updates.`
- `0x18005c6e2`: `CreatePlanarCodec failed`
- `0x18005c747`: `No compressors available!`

## pseudocode

```c
__int64 __fastcall CRDPWireEncoder::Reset(
        CRDPWireEncoder *this,
        struct IRDPCaps *a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8)
{
  _QWORD *v8; // r13
  int v12; // esi
  __int64 v13; // rcx
  int Cacodec; // ebx
  int v15; // r9d
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v17; // edx
  const char *v18; // rcx
  int v19; // r9d
  __int64 v20; // rcx
  int v21; // eax
  const char *v22; // rax
  __int16 *v23; // rdx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rax
  __int64 v28; // rcx
  int v29; // ecx
  int v30; // r13d
  const struct tagTS_BITMAP_CODEC_PROPERTY *NextCodec; // rbx
  int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  char v38; // dl
  int v39; // r13d
  int v40; // ebx
  int v41; // edx
  int v43; // [rsp+20h] [rbp-91h]
  const char *v44; // [rsp+50h] [rbp-61h] BYREF
  __int64 v45; // [rsp+58h] [rbp-59h] BYREF
  struct tagTS_BITMAP_CODEC_CAPABILITYSET *v46; // [rsp+60h] [rbp-51h] BYREF
  __int64 v47; // [rsp+68h] [rbp-49h] BYREF
  const char *v48; // [rsp+70h] [rbp-41h] BYREF
  const char *v49; // [rsp+78h] [rbp-39h] BYREF
  __int64 v50; // [rsp+80h] [rbp-31h] BYREF
  __int64 v51; // [rsp+88h] [rbp-29h] BYREF
  const char *v52; // [rsp+90h] [rbp-21h] BYREF
  _BYTE v53[88]; // [rsp+98h] [rbp-19h] BYREF
  const char *v54; // [rsp+100h] [rbp+4Fh] BYREF
  const char *v55; // [rsp+108h] [rbp+57h] BYREF
  int v56; // [rsp+110h] [rbp+5Fh]
  int v57; // [rsp+118h] [rbp+67h]

  v57 = a4;
  v56 = a3;
  *((_DWORD *)this + 39) = -1;
  v8 = (_QWORD *)((char *)this + 232);
  *((_DWORD *)this + 2) = 0;
  v47 = 0;
  v51 = 0;
  v45 = 0;
  v50 = 0;
  if ( a2 != *((struct IRDPCaps **)this + 29) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 232);
    *v8 = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct IRDPCaps *))(*(_QWORD *)a2 + 8LL))(a2);
  }
  v12 = 1;
  *((_DWORD *)this + 64) = 0;
  *((_DWORD *)this + 65) = 1;
  *((_QWORD *)this + 34) = 0;
  *(_QWORD *)((char *)this + 284) = 0;
  *((_DWORD *)this + 53) = 0;
  TCntPtr<IRdpImageDecompressor>::operator=((char *)this + 200, 0);
  *((_DWORD *)this + 73) = a8;
  *((_DWORD *)this + 74) = 0;
  memset_0((char *)this + 48, 0, 0x60u);
  *((_DWORD *)this + 17) = 1;
  *((_DWORD *)this + 19) = 1;
  *((_DWORD *)this + 18) = 1;
  v13 = *v8;
  *((_DWORD *)this + 70) = a3;
  (*(void (__fastcall **)(__int64, __int64 *, __int64))(*(_QWORD *)v13 + 40LL))(v13, &v50, 1);
  if ( v50 && (*(_WORD *)(v50 + 14) & 0x400) != 0 )
    *((_DWORD *)this + 65) = 0;
  Cacodec = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v8 + 40LL))(*v8, &v47, 3);
  if ( Cacodec < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 15;
      v18 = "FAILED GetCapSet";
LABEL_12:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        (unsigned int)WPP_7ae0677e0b44333e1aeaa360d0eb75a2_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v18,
        Cacodec);
      return (unsigned int)Cacodec;
    }
    return (unsigned int)Cacodec;
  }
  if ( v47 )
  {
    if ( (*(_BYTE *)(v47 + 70) & 2) != 0 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v54 = "Client supports REV3 caching";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801BA47D,
          0,
          v15,
          (__int64)&v54);
      }
      *((_DWORD *)this + 64) = 1;
    }
    else if ( (unsigned int)CallbackContext > 4 )
    {
      v54 = "Client does NOT support REV3 caching, disabling negotiated codecs";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&CallbackContext,
        (unsigned int)&dword_1801BA45C,
        0,
        v15,
        (__int64)&v54);
    }
    if ( (*(_BYTE *)(v47 + 70) & 4) != 0 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v54 = "Client supports altsec frame markers";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801BA43B,
          0,
          v15,
          (__int64)&v54);
      }
      *((_DWORD *)this + 67) = 1;
    }
  }
  Cacodec = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v8 + 40LL))(*v8, &v51, 28);
  if ( Cacodec >= 0 )
  {
    v20 = v51;
    if ( v51 )
    {
      *((_DWORD *)this + 68) = (*(_DWORD *)(v51 + 4) >> 1) & 1;
      v21 = (*(_DWORD *)(v20 + 4) >> 4) & 1;
    }
    else
    {
      *((_DWORD *)this + 68) = 0;
      v21 = 0;
    }
    *((_DWORD *)this + 66) = v21;
    if ( *((_DWORD *)this + 68) )
    {
      if ( (unsigned int)CallbackContext <= 4 )
        goto LABEL_38;
      v22 = "Surface commands supported";
      v23 = word_1801BA41A;
    }
    else
    {
      if ( (unsigned int)CallbackContext <= 4 )
        goto LABEL_38;
      v22 = "Surface commands are NOT supported, disabling negotiated codecs";
      v23 = (__int16 *)byte_1801BA3F9;
    }
    v54 = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (_DWORD)v23,
      0,
      v19,
      (__int64)&v54);
LABEL_38:
    Cacodec = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v8 + 40LL))(*v8, &v45, 2);
    if ( Cacodec < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 17;
        v18 = "FAILED to get Bitmap GetCapSet";
        goto LABEL_12;
      }
      return (unsigned int)Cacodec;
    }
    v27 = v45;
    if ( v45 && (*(_BYTE *)(v45 + 23) & 0x10) != 0 )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v54 = " Client supports Extended Bitmap Header";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)qword_1801BA3D8,
          0,
          v26,
          (__int64)&v54);
      }
      v27 = v45;
      *((_DWORD *)this + 69) = 1;
    }
    if ( *((_DWORD *)this + 64) || *((_DWORD *)this + 68) )
    {
      v28 = *v8;
      v46 = 0;
      if ( (*(int (__fastcall **)(__int64, struct tagTS_BITMAP_CODEC_CAPABILITYSET **, __int64))(*(_QWORD *)v28 + 40LL))(
             v28,
             &v46,
             29) >= 0
        && v46 )
      {
        if ( !a5 )
          goto LABEL_136;
        v29 = 0;
        LODWORD(v54) = 0;
        v30 = 0;
        LODWORD(v55) = 0;
        if ( (unsigned int)CallbackContext > 4 )
        {
          LOBYTE(v29) = *((_BYTE *)v46 + 4);
          v44 = "Client has bitmap codec support, %d codecs";
          LOBYTE(a8) = v29;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(
            v29,
            (unsigned int)&byte_1801BA397,
            v25,
            v26,
            (__int64)&v44,
            (__int64)&a8);
        }
        CodecCapsIterator::CodecCapsIterator((CodecCapsIterator *)v53, v46);
        NextCodec = CodecCapsIterator::GetNextCodec((CodecCapsIterator *)v53);
        if ( NextCodec )
        {
          do
          {
            v32 = (int)CallbackContext;
            if ( (unsigned int)CallbackContext > 4 )
            {
              v33 = *((unsigned __int8 *)NextCodec + 16);
              v44 = "Codec %d";
              a8 = v33;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                v33,
                (unsigned int)byte_1801BA361,
                v25,
                v26,
                (__int64)&v44,
                (__int64)&a8);
            }
            if ( *(_QWORD *)NextCodec == *(_QWORD *)&CODEC_GUID_NSCODEC.Data1
              && *((_QWORD *)NextCodec + 1) == *(_QWORD *)CODEC_GUID_NSCODEC.Data4 )
            {
              if ( (a5 & 2) != 0 )
              {
                if ( *(_WORD *)((char *)NextCodec + 17) != 3 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v34 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      18,
                      WPP_7ae0677e0b44333e1aeaa360d0eb75a2_Traceguids,
                      v34,
                      -2147024846);
                  }
                  return (unsigned int)-2147024846;
                }
                if ( (unsigned int)CallbackContext > 4 )
                {
                  v54 = "NSCodec compressor negotiated";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                    (unsigned int)&CallbackContext,
                    (unsigned int)qword_1801BA340,
                    0,
                    v26,
                    (__int64)&v54);
                }
                LODWORD(v54) = 1;
              }
            }
            else if ( *(_QWORD *)NextCodec == *(_QWORD *)&CODEC_GUID_CACODEC.Data1
                   && *((_QWORD *)NextCodec + 1) == *(_QWORD *)CODEC_GUID_CACODEC.Data4 )
            {
              if ( (a5 & 4) != 0 )
              {
                if ( (unsigned int)CallbackContext > 4 )
                {
                  v44 = "Video CAC compressor negotiated on";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                    (unsigned int)&CallbackContext,
                    (unsigned int)&byte_1801BA31F,
                    0,
                    v26,
                    (__int64)&v44);
                }
                v30 = 1;
                *((_DWORD *)this + 75) = *((unsigned __int8 *)NextCodec + 16);
              }
            }
            else if ( *(_QWORD *)NextCodec == *(_QWORD *)&CODEC_GUID_IMGCACODEC.Data1
                   && *((_QWORD *)NextCodec + 1) == *(_QWORD *)CODEC_GUID_IMGCACODEC.Data4 )
            {
              if ( (a5 & 8) != 0 )
              {
                if ( (unsigned int)CallbackContext > 4 )
                {
                  v55 = "Image CAC compressor negotiated on";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                    (unsigned int)&CallbackContext,
                    (unsigned int)&word_1801BA2FE,
                    0,
                    v26,
                    (__int64)&v55);
                }
                *((_DWORD *)this + 76) = *((unsigned __int8 *)NextCodec + 16);
                LODWORD(v55) = 1;
              }
            }
            else if ( (unsigned int)CallbackContext > 2 )
            {
              a8 = 362;
              v52 = "Reset";
              LODWORD(v44) = -2147467259;
              v48 = "onecore\\termsrv\\rdpplatform\\protocol\\crdporderencoder.cpp";
              v49 = "Unknown codec in the merged caps, ignoring";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v32,
                (unsigned int)byte_1801BA2B9,
                v25,
                v26,
                (__int64)&v49,
                (__int64)&v44,
                (__int64)&v48,
                (__int64)&a8,
                (__int64)&v52);
            }
            NextCodec = CodecCapsIterator::GetNextCodec((CodecCapsIterator *)v53);
          }
          while ( NextCodec );
          if ( (_DWORD)v55 )
          {
            Cacodec = CRDPWireEncoder::CreateCacodec((CRDPWireEncoder *)((char *)this - 48), 0, a6, a7);
            if ( Cacodec >= 0 )
            {
              if ( (unsigned int)CallbackContext > 4 )
              {
                v54 = "Default Codec is CAC image";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&CallbackContext,
                  (unsigned int)qword_1801BA298,
                  0,
                  v26,
                  (__int64)&v54);
              }
              if ( *((_QWORD *)this + 24) != *((_QWORD *)this + 25) )
              {
                TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 200);
                *((_QWORD *)this + 25) = *((_QWORD *)this + 24);
                TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 200);
              }
              *((_DWORD *)this + 52) = *((_DWORD *)this + 76);
              *((_DWORD *)this + 71) = 1;
              return (unsigned int)Cacodec;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v35 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                19,
                (unsigned int)WPP_7ae0677e0b44333e1aeaa360d0eb75a2_Traceguids,
                v35,
                (__int64)"Failed to create the CA image compressor",
                Cacodec);
            }
          }
          if ( v30 )
          {
            Cacodec = CRDPWireEncoder::CreateCacodec((CRDPWireEncoder *)((char *)this - 48), 1, a6, a7);
            if ( Cacodec >= 0 )
            {
              if ( (unsigned int)CallbackContext > 4 )
              {
                v54 = "Default Codec is CAC video";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                  (unsigned int)&CallbackContext,
                  (unsigned int)&byte_1801BA277,
                  0,
                  v26,
                  (__int64)&v54);
              }
              if ( *((_QWORD *)this + 24) != *((_QWORD *)this + 25) )
              {
                TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 200);
                *((_QWORD *)this + 25) = *((_QWORD *)this + 24);
                TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 200);
              }
              *((_DWORD *)this + 52) = *((_DWORD *)this + 75);
              *((_DWORD *)this + 71) = 1;
              *((_DWORD *)this + 53) = 1;
              *((_DWORD *)this + 74) = 1;
              return (unsigned int)Cacodec;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v36 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                (unsigned int)WPP_7ae0677e0b44333e1aeaa360d0eb75a2_Traceguids,
                v36,
                (__int64)"Failed to create the CA video compressor",
                Cacodec);
            }
          }
          if ( !(_DWORD)v54 )
            goto LABEL_118;
          Cacodec = CRDPWireEncoder::CreateNscodec((CRDPWireEncoder *)((char *)this - 48));
          if ( Cacodec >= 0 )
          {
            if ( (unsigned int)CallbackContext > 4 )
            {
              v54 = "Default Codec is NSCodec";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                (unsigned int)&CallbackContext,
                (unsigned int)&word_1801BA256,
                0,
                v26,
                (__int64)&v54);
            }
            if ( *((_QWORD *)this + 23) != *((_QWORD *)this + 25) )
            {
              TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 200);
              *((_QWORD *)this + 25) = *((_QWORD *)this + 23);
              TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 200);
            }
            *((_DWORD *)this + 52) = 1;
            *((_DWORD *)this + 71) = 0;
            return (unsigned int)Cacodec;
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v37 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              (unsigned int)WPP_7ae0677e0b44333e1aeaa360d0eb75a2_Traceguids,
              v37,
              (__int64)"Failed to create the NSCodec compressor",
              Cacodec);
          }
        }
      }
LABEL_118:
      v27 = v45;
    }
    if ( (a5 & 1) != 0 )
    {
      if ( v27 )
      {
        v38 = *(_BYTE *)(v27 + 23);
        v39 = v38 & 2;
        v40 = v39 != 0 ? v38 & 4 : 0;
        if ( (v38 & 8) == 0 && v56 == 32 )
        {
LABEL_126:
          if ( (unsigned int)CallbackContext > 4 )
          {
            v54 = "Default codec is Win6 Planar; disabling rev3 cache and SetSurfaceBits(ex) updates.";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              (unsigned int)&CallbackContext,
              (unsigned int)byte_1801BA235,
              0,
              v26,
              (__int64)&v54);
          }
          v41 = v57;
          *((_DWORD *)this + 52) = *((_DWORD *)this + 77);
          v43 = *((_DWORD *)this + 65);
          *((_DWORD *)this + 64) = 0;
          *((_QWORD *)this + 34) = 0;
          *((_DWORD *)this + 66) = 0;
          *((_DWORD *)this + 71) = 0;
          *((_DWORD *)this + 72) = v12;
          Cacodec = CRDPWireEncoder::CreatePlanarCodec((CRDPWireEncoder *)((char *)this - 48), v41, v40, v39, v43);
          if ( Cacodec >= 0 )
          {
            if ( *((_QWORD *)this + 22) != *((_QWORD *)this + 25) )
            {
              TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 200);
              *((_QWORD *)this + 25) = *((_QWORD *)this + 22);
              TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 200);
            }
            return 0;
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v17 = 22;
            v18 = "CreatePlanarCodec failed";
            goto LABEL_12;
          }
          return (unsigned int)Cacodec;
        }
      }
      else
      {
        v40 = 0;
        v39 = 0;
      }
      v12 = 0;
      goto LABEL_126;
    }
LABEL_136:
    if ( (unsigned int)CallbackContext > 2 )
    {
      v55 = "Reset";
      v49 = "onecore\\termsrv\\rdpplatform\\protocol\\crdporderencoder.cpp";
      a8 = 477;
      v48 = "No compressors available!";
      LODWORD(v54) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v24,
        (unsigned int)qword_1801BA1F0,
        v25,
        v26,
        (__int64)&v48,
        (__int64)&v54,
        (__int64)&v49,
        (__int64)&a8,
        (__int64)&v55);
    }
    return (unsigned int)-2147467259;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 16;
    v18 = "GetCapSet(TS_CAPSETTYPE_SURFACE_COMMANDS) failed!";
    goto LABEL_12;
  }
  return (unsigned int)Cacodec;
}

```

## disassembly

```asm
0x18005bbe0  mov     [rsp-8+arg_18], r9d
0x18005bbe5  mov     [rsp-8+arg_10], r8d
0x18005bbea  push    rbp
0x18005bbeb  push    rbx
0x18005bbec  push    rsi
0x18005bbed  push    rdi
0x18005bbee  push    r12
0x18005bbf0  push    r13
0x18005bbf2  push    r14
0x18005bbf4  push    r15
0x18005bbf6  lea     rbp, [rsp-7]
0x18005bbfb  sub     rsp, 0B8h
0x18005bc02  xor     r12d, r12d
0x18005bc05  mov     dword ptr [rcx+9Ch], 0FFFFFFFFh
0x18005bc0f  lea     r13, [rcx+0E8h]
0x18005bc16  mov     [rcx+8], r12d
0x18005bc1a  mov     r15d, r8d
0x18005bc1d  mov     rbx, rdx
0x18005bc20  mov     rdi, rcx
0x18005bc23  mov     [rbp+3Fh+var_88], r12
0x18005bc27  mov     [rbp+3Fh+var_68], r12
0x18005bc2b  mov     [rbp+3Fh+var_98], r12
0x18005bc2f  mov     [rbp+3Fh+var_70], r12
0x18005bc33  cmp     rdx, [r13+0]
0x18005bc37  jz      short loc_18005BC59
0x18005bc39  mov     rcx, r13; void *
0x18005bc3c  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18005bc41  mov     [r13+0], rbx
0x18005bc45  test    rbx, rbx
0x18005bc48  jz      short loc_18005BC59
0x18005bc4a  mov     rax, [rbx]
0x18005bc4d  mov     rcx, rbx
0x18005bc50  mov     rax, [rax+8]
0x18005bc54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc59  mov     esi, 1
0x18005bc5e  mov     [rdi+100h], r12d
0x18005bc65  lea     rcx, [rdi+0C8h]
0x18005bc6c  mov     [rdi+104h], esi
0x18005bc72  xor     edx, edx
0x18005bc74  mov     [rdi+110h], r12
0x18005bc7b  mov     [rdi+11Ch], r12
0x18005bc82  mov     [rdi+0D4h], r12d
0x18005bc89  call    ??4?$TCntPtr@UIRdpImageDecompressor@@@@QEAAPEAUIRdpImageDecompressor@@PEAU1@@Z; TCntPtr<IRdpImageDecompressor>::operator=(IRdpImageDecompressor *)
0x18005bc8e  mov     eax, [rbp+3Fh+arg_38]
0x18005bc94  lea     r8d, [rsi+5Fh]; Size
0x18005bc98  xor     edx, edx; Val
0x18005bc9a  mov     [rdi+124h], eax
0x18005bca0  lea     rcx, [rdi+30h]; void *
0x18005bca4  mov     [rdi+128h], r12d
0x18005bcab  call    memset_0
0x18005bcb0  mov     [rdi+44h], esi
0x18005bcb3  lea     rdx, [rbp+3Fh+var_70]
0x18005bcb7  mov     [rdi+4Ch], esi
0x18005bcba  mov     r8d, esi
0x18005bcbd  mov     [rdi+48h], esi
0x18005bcc0  mov     rcx, [r13+0]
0x18005bcc4  mov     [rdi+118h], r15d
0x18005bccb  mov     rax, [rcx]
0x18005bcce  mov     rax, [rax+28h]
0x18005bcd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcd7  mov     rcx, [rbp+3Fh+var_70]
0x18005bcdb  test    rcx, rcx
0x18005bcde  jz      short loc_18005BCF9
0x18005bce0  movzx   ecx, word ptr [rcx+0Eh]
0x18005bce4  mov     eax, 400h
0x18005bce9  and     cx, ax
0x18005bcec  cmp     r12w, cx
0x18005bcf0  jz      short loc_18005BCF9
0x18005bcf2  mov     [rdi+104h], r12d
0x18005bcf9  mov     rcx, [r13+0]
0x18005bcfd  lea     rdx, [rbp+3Fh+var_88]
0x18005bd01  mov     r8d, 3
0x18005bd07  mov     rax, [rcx]
0x18005bd0a  mov     rax, [rax+28h]
0x18005bd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd13  mov     ebx, eax
0x18005bd15  test    eax, eax
0x18005bd17  jns     short loc_18005BD85
0x18005bd19  mov     rax, cs:WPP_GLOBAL_Control
0x18005bd20  lea     r12, WPP_GLOBAL_Control
0x18005bd27  cmp     rax, r12
0x18005bd2a  jz      loc_18005C79D
0x18005bd30  mov     r14b, 8
0x18005bd33  test    [rax+1Ch], r14b
0x18005bd37  jz      loc_18005C79D
0x18005bd3d  mov     r15d, 2
0x18005bd43  cmp     [rax+19h], r15b
0x18005bd47  jb      loc_18005C79D
0x18005bd4d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005bd52  lea     edx, [r15+0Dh]
0x18005bd56  lea     rcx, aFailedGetcapse; "FAILED GetCapSet"
0x18005bd5d  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x18005bd61  lea     r8, WPP_7ae0677e0b44333e1aeaa360d0eb75a2_Traceguids
0x18005bd68  mov     qword ptr [rsp+0F0h+var_D0], rcx
0x18005bd6d  mov     r9d, eax
0x18005bd70  mov     rcx, cs:WPP_GLOBAL_Control
0x18005bd77  mov     rcx, [rcx+10h]
0x18005bd7b  call    WPP_SF_DsD
0x18005bd80  jmp     loc_18005C79D
0x18005bd85  mov     rax, [rbp+3Fh+var_88]
0x18005bd89  mov     r15d, 2
0x18005bd8f  test    rax, rax
0x18005bd92  jz      loc_18005BE4F
0x18005bd98  test    [rax+46h], r15b
0x18005bd9c  mov     eax, cs:CallbackContext
0x18005bda2  jz      short loc_18005BDDB
0x18005bda4  cmp     eax, 4
0x18005bda7  jbe     short loc_18005BDD3
0x18005bda9  lea     rax, aClientSupports_0; "Client supports REV3 caching"
0x18005bdb0  xor     r8d, r8d
0x18005bdb3  mov     [rbp+3Fh+arg_0], rax
0x18005bdb7  lea     rdx, byte_1801BA47D
0x18005bdbe  lea     rax, [rbp+3Fh+arg_0]
0x18005bdc2  lea     rcx, CallbackContext
0x18005bdc9  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18005bdce  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005bdd3  mov     [rdi+100h], esi
0x18005bdd9  jmp     short loc_18005BE0A
0x18005bddb  cmp     eax, 4
0x18005bdde  jbe     short loc_18005BE0A
0x18005bde0  lea     rax, aClientDoesNotS; "Client does NOT support REV3 caching, d"...
0x18005bde7  xor     r8d, r8d
0x18005bdea  mov     [rbp+3Fh+arg_0], rax
0x18005bdee  lea     rdx, dword_1801BA45C
0x18005bdf5  lea     rax, [rbp+3Fh+arg_0]
0x18005bdf9  lea     rcx, CallbackContext
0x18005be00  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18005be05  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005be0a  mov     rax, [rbp+3Fh+var_88]
0x18005be0e  test    byte ptr [rax+46h], 4
0x18005be12  jz      short loc_18005BE4F
0x18005be14  mov     eax, cs:CallbackContext
0x18005be1a  cmp     eax, 4
0x18005be1d  jbe     short loc_18005BE49
0x18005be1f  lea     rax, aClientSupports_1; "Client supports altsec frame markers"
0x18005be26  xor     r8d, r8d
0x18005be29  mov     [rbp+3Fh+arg_0], rax
0x18005be2d  lea     rdx, byte_1801BA43B
0x18005be34  lea     rax, [rbp+3Fh+arg_0]
0x18005be38  lea     rcx, CallbackContext
0x18005be3f  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18005be44  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005be49  mov     [rdi+10Ch], esi
0x18005be4f  mov     rcx, [r13+0]
0x18005be53  lea     rdx, [rbp+3Fh+var_68]
0x18005be57  mov     r8d, 1Ch
0x18005be5d  mov     rax, [rcx]
0x18005be60  mov     rax, [rax+28h]
0x18005be64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be69  mov     ebx, eax
0x18005be6b  test    eax, eax
0x18005be6d  jns     short loc_18005BEB3
0x18005be6f  mov     rax, cs:WPP_GLOBAL_Control
0x18005be76  lea     r12, WPP_GLOBAL_Control
0x18005be7d  cmp     rax, r12
0x18005be80  jz      loc_18005C79D
0x18005be86  mov     r14b, 8
0x18005be89  test    [rax+1Ch], r14b
0x18005be8d  jz      loc_18005C79D
0x18005be93  cmp     [rax+19h], r15b
0x18005be97  jb      loc_18005C79D
0x18005be9d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005bea2  mov     edx, 10h
0x18005bea7  lea     rcx, aGetcapsetTsCap; "GetCapSet(TS_CAPSETTYPE_SURFACE_COMMAND"...
0x18005beae  jmp     loc_18005BD5D
0x18005beb3  mov     rcx, [rbp+3Fh+var_68]
0x18005beb7  test    rcx, rcx
0x18005beba  jz      short loc_18005BED3
0x18005bebc  mov     eax, [rcx+4]
0x18005bebf  shr     eax, 1
0x18005bec1  and     eax, esi
0x18005bec3  mov     [rdi+110h], eax
0x18005bec9  mov     eax, [rcx+4]
0x18005becc  shr     eax, 4
0x18005becf  and     eax, esi
0x18005bed1  jmp     short loc_18005BEDD
0x18005bed3  mov     [rdi+110h], r12d
0x18005beda  mov     eax, r12d
0x18005bedd  mov     [rdi+108h], eax
0x18005bee3  mov     eax, cs:CallbackContext
0x18005bee9  cmp     [rdi+110h], r12d
0x18005bef0  jz      short loc_18005BF07
0x18005bef2  cmp     eax, 4
0x18005bef5  jbe     short loc_18005BF36
0x18005bef7  lea     rax, aSurfaceCommand_1; "Surface commands supported"
0x18005befe  lea     rdx, word_1801BA41A
0x18005bf05  jmp     short loc_18005BF1A
0x18005bf07  cmp     eax, 4
0x18005bf0a  jbe     short loc_18005BF36
0x18005bf0c  lea     rax, aSurfaceCommand; "Surface commands are NOT supported, dis"...
0x18005bf13  lea     rdx, byte_1801BA3F9
0x18005bf1a  mov     [rbp+3Fh+arg_0], rax
0x18005bf1e  lea     rcx, CallbackContext
0x18005bf25  lea     rax, [rbp+3Fh+arg_0]
0x18005bf29  xor     r8d, r8d
0x18005bf2c  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18005bf31  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005bf36  mov     rcx, [r13+0]
0x18005bf3a  lea     rdx, [rbp+3Fh+var_98]
0x18005bf3e  mov     r8d, r15d
0x18005bf41  mov     rax, [rcx]
0x18005bf44  mov     rax, [rax+28h]
0x18005bf48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bf4d  mov     ebx, eax
0x18005bf4f  test    eax, eax
0x18005bf51  jns     short loc_18005BF97
0x18005bf53  mov     rax, cs:WPP_GLOBAL_Control
0x18005bf5a  lea     r12, WPP_GLOBAL_Control
0x18005bf61  cmp     rax, r12
0x18005bf64  jz      loc_18005C79D
0x18005bf6a  mov     r14b, 8
0x18005bf6d  test    [rax+1Ch], r14b
0x18005bf71  jz      loc_18005C79D
0x18005bf77  cmp     [rax+19h], r15b
0x18005bf7b  jb      loc_18005C79D
0x18005bf81  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005bf86  mov     edx, 11h
0x18005bf8b  lea     rcx, aFailedToGetBit_1; "FAILED to get Bitmap GetCapSet"
0x18005bf92  jmp     loc_18005BD5D
0x18005bf97  mov     rax, [rbp+3Fh+var_98]
0x18005bf9b  test    rax, rax
0x18005bf9e  jz      short loc_18005BFE5
0x18005bfa0  test    byte ptr [rax+17h], 10h
0x18005bfa4  jz      short loc_18005BFE5
0x18005bfa6  mov     eax, cs:CallbackContext
0x18005bfac  cmp     eax, 4
0x18005bfaf  jbe     short loc_18005BFDB
0x18005bfb1  lea     rax, aClientSupports; " Client supports Extended Bitmap Header"
0x18005bfb8  xor     r8d, r8d
0x18005bfbb  mov     [rbp+3Fh+arg_0], rax
0x18005bfbf  lea     rdx, qword_1801BA3D8
0x18005bfc6  lea     rax, [rbp+3Fh+arg_0]
0x18005bfca  lea     rcx, CallbackContext
0x18005bfd1  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18005bfd6  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005bfdb  mov     rax, [rbp+3Fh+var_98]
0x18005bfdf  mov     [rdi+114h], esi
0x18005bfe5  cmp     dword ptr [rdi+100h], 0
0x18005bfec  lea     rbx, aReset; "Reset"
0x18005bff3  lea     r12, WPP_GLOBAL_Control
0x18005bffa  mov     r14b, 8
0x18005bffd  jnz     short loc_18005C00C
0x18005bfff  cmp     dword ptr [rdi+110h], 0
0x18005c006  jz      loc_18005C5E7
0x18005c00c  mov     rcx, [r13+0]
0x18005c010  lea     rdx, [rbp+3Fh+var_90]
0x18005c014  mov     [rbp+3Fh+var_90], 0
0x18005c01c  mov     r8d, 1Dh
0x18005c022  mov     rax, [rcx]
0x18005c025  mov     rax, [rax+28h]
0x18005c029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c02e  test    eax, eax
0x18005c030  js      loc_18005C5E3
0x18005c036  cmp     [rbp+3Fh+var_90], 0
0x18005c03b  jz      loc_18005C5E3
0x18005c041  cmp     [rbp+3Fh+arg_20], 0
0x18005c045  jz      loc_18005C726
0x18005c04b  xor     eax, eax
0x18005c04d  xor     ecx, ecx
0x18005c04f  mov     dword ptr [rbp+3Fh+arg_0], eax
0x18005c052  xor     r13d, r13d
0x18005c055  mov     eax, cs:CallbackContext
0x18005c05b  mov     dword ptr [rbp+3Fh+arg_8], ecx
0x18005c05e  cmp     eax, 4
0x18005c061  jbe     short loc_18005C09C
0x18005c063  mov     rax, [rbp+3Fh+var_90]
0x18005c067  lea     rdx, byte_1801BA397
0x18005c06e  mov     cl, [rax+4]
0x18005c071  lea     rax, aClientHasBitma; "Client has bitmap codec support, %d cod"...
0x18005c078  mov     [rbp+3Fh+var_A0], rax
0x18005c07c  lea     rax, [rbp+3Fh+arg_38]
0x18005c083  mov     [rsp+0F0h+var_C8], rax
0x18005c088  lea     rax, [rbp+3Fh+var_A0]
0x18005c08c  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18005c091  mov     byte ptr [rbp+3Fh+arg_38], cl
0x18005c097  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<1> const &)
0x18005c09c  mov     rdx, [rbp+3Fh+var_90]; struct tagTS_BITMAP_CODEC_CAPABILITYSET *
0x18005c0a0  lea     rcx, [rbp+3Fh+var_58]; this
0x18005c0a4  call    ??0CodecCapsIterator@@QEAA@PEBUtagTS_BITMAP_CODEC_CAPABILITYSET@@@Z; CodecCapsIterator::CodecCapsIterator(tagTS_BITMAP_CODEC_CAPABILITYSET const *)
0x18005c0a9  lea     rcx, [rbp+3Fh+var_58]; this
0x18005c0ad  call    ?GetNextCodec@CodecCapsIterator@@QEAAPEFBUtagTS_BITMAP_CODEC_PROPERTY@@XZ; CodecCapsIterator::GetNextCodec(void)
0x18005c0b2  mov     rbx, rax
0x18005c0b5  test    rax, rax
0x18005c0b8  jz      loc_18005C5E3
0x18005c0be  mov     ecx, cs:CallbackContext
0x18005c0c4  cmp     ecx, 4
0x18005c0c7  jbe     short loc_18005C0FF
0x18005c0c9  movzx   ecx, byte ptr [rbx+10h]
0x18005c0cd  lea     rax, aCodecD; "Codec %d"
0x18005c0d4  mov     [rbp+3Fh+var_A0], rax
0x18005c0d8  lea     rdx, byte_1801BA361
0x18005c0df  lea     rax, [rbp+3Fh+arg_38]
0x18005c0e6  mov     [rbp+3Fh+arg_38], ecx
0x18005c0ec  mov     [rsp+0F0h+var_C8], rax
0x18005c0f1  lea     rax, [rbp+3Fh+var_A0]
0x18005c0f5  mov     qword ptr [rsp+0F0h+var_D0], rax
0x18005c0fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005c0ff  mov     rax, [rbx]
0x18005c102  cmp     rax, qword ptr cs:CODEC_GUID_NSCODEC.Data1
0x18005c109  jnz     short loc_18005C16E
  ... truncated ...
```
