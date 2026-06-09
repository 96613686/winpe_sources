# CaProgressiveCompressor::Init(CacNx::Quality)

- ea: `0x18016c610`
- end: `0x18016cad8`
- name: `?Init@CaProgressiveCompressor@@QEAAJW4Quality@CacNx@@@Z`
- size: `1224`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18016cae0`

## callees

- `0x18000116c`
- `0x180002170`
- `0x18007f42c`
- `0x18007f6b0`
- `0x18016c5c8`
- `0x18016c610`
- `0x18016d00c`
- `0x18016d60c`
- `0x18019c010`

## string_xrefs

- `0x18016c652`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016c707`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016c7bf`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016c848`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016c8dc`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016c92f`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016c9c8`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016ca55`: `onecore\termsrv\cardp\progressivecalista\caprogressivecompressor.cpp`
- `0x18016c662`: `CaProgressiveCompressor::Init has already been initialized`
- `0x18016c712`: `CaProgressiveCompressor::Init failed could not initialize encDescs hr = 0x%08x`
- `0x18016c8e7`: `CaProgressiveCompressor::Init failed could not initialize m_encodingRects hr = 0x%08x`
- `0x18016c93d`: `CaProgressiveCompressor::Init ran out of memory trying to allocate outEncContexts`
- `0x18016c7ca`: `CaProgressiveCompressor::Init failed could not initialize m_descs hr = 0x%08x`
- `0x18016c853`: `CaProgressiveCompressor::Init failed could not initialize m_surfaceRects hr = 0x%08x`
- `0x18016c9d3`: `CaProgressiveCompressor::Init could not get encoder factory hr = 0x%08x`
- `0x18016ca60`: `CaProgressiveCompressor::Init could not get encoder factory hr = 0x%08x`

## pseudocode

```c
__int64 __fastcall CaProgressiveCompressor::Init(__int64 a1, int a2, int a3, int a4)
{
  unsigned int v6; // ebx
  void *v7; // rax
  __int16 *v8; // rdx
  const char **v9; // rax
  void *v10; // rax
  int EncoderFactoryInstance; // esi
  int v12; // r8d
  int v13; // r9d
  int v14; // ecx
  char *v15; // rdx
  const char *v16; // rax
  void *v17; // rax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rcx
  int (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // rcx
  int v23; // eax
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rcx
  const char **v27; // [rsp+30h] [rbp-40h]
  const char **v28; // [rsp+40h] [rbp-30h]
  __int64 v29; // [rsp+50h] [rbp-20h] BYREF
  const char *v30; // [rsp+58h] [rbp-18h] BYREF
  const char *v31; // [rsp+60h] [rbp-10h] BYREF
  const char *v32; // [rsp+68h] [rbp-8h] BYREF
  int v33; // [rsp+90h] [rbp+20h] BYREF
  int v34; // [rsp+A0h] [rbp+30h] BYREF
  const char *v35; // [rsp+A8h] [rbp+38h] BYREF

  if ( *(_QWORD *)(a1 + 200) )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v33 = 215;
      v35 = "Init";
      v30 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
      v31 = "CaProgressiveCompressor::Init has already been initialized";
      v34 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        a1,
        (unsigned int)qword_1802A0F00,
        a3,
        a4,
        (__int64)&v31,
        (__int64)&v34,
        (__int64)&v30,
        (__int64)&v33,
        (__int64)&v35);
    }
    return 2147942487LL;
  }
  *(_DWORD *)(a1 + 264) = a2;
  if ( *(_QWORD *)(a1 + 240) )
  {
    v6 = -2147467259;
LABEL_9:
    if ( (unsigned int)CallbackContext <= 2 )
      return v6;
    v34 = 224;
    v31 = "Init";
    v8 = (__int16 *)byte_1802A10C5;
    v30 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
    v32 = "CaProgressiveCompressor::Init failed could not initialize encDescs hr = 0x%08x";
    v28 = &v31;
    v27 = &v30;
    v9 = &v32;
LABEL_11:
    LODWORD(v35) = -2147467259;
    v33 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      a1,
      (_DWORD)v8,
      a3,
      a4,
      (__int64)v9,
      (__int64)&v35,
      (__int64)v27,
      (__int64)&v34,
      (__int64)v28,
      (__int64)&v33);
    return v6;
  }
  v7 = operator new(0x5DC0u);
  *(_QWORD *)(a1 + 240) = v7;
  if ( !v7 )
  {
    v6 = -2147024882;
    goto LABEL_9;
  }
  *(_DWORD *)(a1 + 252) = 1000;
  if ( *(_QWORD *)(a1 + 144) )
  {
    v6 = -2147467259;
LABEL_16:
    if ( (unsigned int)CallbackContext <= 2 )
      return v6;
    v34 = 232;
    v32 = "Init";
    v8 = word_1802A2592;
    v31 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
    v30 = "CaProgressiveCompressor::Init failed could not initialize m_descs hr = 0x%08x";
    v28 = &v32;
    v27 = &v31;
    v9 = &v30;
    goto LABEL_11;
  }
  v10 = operator new(0x3E80u);
  *(_QWORD *)(a1 + 144) = v10;
  if ( !v10 )
  {
    v6 = -2147024882;
    goto LABEL_16;
  }
  *(_DWORD *)(a1 + 156) = 1000;
  EncoderFactoryInstance = CaSimpleArray<tagRECT>::Init(a1 + 112);
  if ( EncoderFactoryInstance < 0 )
  {
    v14 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v34 = 240;
      v32 = "Init";
      v15 = (char *)word_1802A1E52;
      v31 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
      v16 = "CaProgressiveCompressor::Init failed could not initialize m_surfaceRects hr = 0x%08x";
LABEL_21:
      v30 = v16;
      LODWORD(v35) = -2147467259;
      v33 = EncoderFactoryInstance;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v14,
        (_DWORD)v15,
        v12,
        v13,
        (__int64)&v30,
        (__int64)&v35,
        (__int64)&v31,
        (__int64)&v34,
        (__int64)&v32,
        (__int64)&v33);
      return (unsigned int)EncoderFactoryInstance;
    }
    return (unsigned int)EncoderFactoryInstance;
  }
  EncoderFactoryInstance = CaSimpleArray<tagRECT>::Init(a1 + 208);
  if ( EncoderFactoryInstance < 0 )
  {
    v14 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext <= 2 )
      return (unsigned int)EncoderFactoryInstance;
    v34 = 248;
    v32 = "Init";
    v15 = byte_1802A2549;
    v31 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
    v16 = "CaProgressiveCompressor::Init failed could not initialize m_encodingRects hr = 0x%08x";
    goto LABEL_21;
  }
  v17 = operator new(0x1F40u);
  *(_QWORD *)(a1 + 200) = v17;
  if ( v17 )
  {
    memset_0(v17, 0, 0x1F40u);
    EncoderFactoryInstance = CacNx::CreateEncoderFactoryInstance(v21, a1 + 72);
    if ( EncoderFactoryInstance >= 0 )
    {
      v22 = *(int (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 256);
      v29 = 0;
      if ( (**v22)(v22, &IID_ICaGfxSourceProgressive, &v29) >= 0 && v29 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 24LL))(v29, a1);
      v23 = CaProgressiveCompressor::setupBestEncodingEngine((CaProgressiveCompressor *)a1);
      v6 = v23;
      if ( v23 < 0 && (unsigned int)CallbackContext > 2 )
      {
        v33 = v23;
        v34 = 283;
        v32 = "Init";
        v31 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
        v30 = "CaProgressiveCompressor::Init could not get encoder factory hr = 0x%08x";
        LODWORD(v35) = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (_DWORD)CallbackContext,
          (unsigned int)&dword_1802A2224,
          v24,
          v25,
          (__int64)&v30,
          (__int64)&v35,
          (__int64)&v31,
          (__int64)&v34,
          (__int64)&v32,
          (__int64)&v33);
      }
      v26 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      return v6;
    }
    v14 = (int)CallbackContext;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v34 = 265;
      v32 = "Init";
      v15 = byte_1802A1E9B;
      v31 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
      v16 = "CaProgressiveCompressor::Init could not get encoder factory hr = 0x%08x";
      goto LABEL_21;
    }
    return (unsigned int)EncoderFactoryInstance;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    v33 = 255;
    v35 = "Init";
    v34 = -2147467259;
    v32 = "onecore\\termsrv\\cardp\\progressivecalista\\caprogressivecompressor.cpp";
    v31 = "CaProgressiveCompressor::Init ran out of memory trying to allocate outEncContexts";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v18,
      (unsigned int)byte_1802A226D,
      v19,
      v20,
      (__int64)&v31,
      (__int64)&v34,
      (__int64)&v32,
      (__int64)&v33,
      (__int64)&v35);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18016c610  mov     r11, rsp
0x18016c613  mov     [r11+10h], rbx
0x18016c617  push    rbp
0x18016c618  push    rsi
0x18016c619  push    rdi
0x18016c61a  mov     rbp, rsp
0x18016c61d  sub     rsp, 70h
0x18016c621  cmp     qword ptr [rcx+0C8h], 0
0x18016c629  mov     rbx, rcx
0x18016c62c  jz      short loc_18016C6A7
0x18016c62e  mov     eax, cs:CallbackContext
0x18016c634  cmp     eax, 2
0x18016c637  jbe     short loc_18016C69D
0x18016c639  lea     rax, aInit; "Init"
0x18016c640  mov     [rbp+arg_0], 0D7h
0x18016c647  mov     [rbp+arg_18], rax
0x18016c64b  lea     rdx, qword_1802A0F00
0x18016c652  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016c659  mov     edi, 80004005h
0x18016c65e  mov     [rbp+var_18], rax
0x18016c662  lea     rax, aCaprogressivec_12; "CaProgressiveCompressor::Init has alrea"...
0x18016c669  mov     [rbp+var_10], rax
0x18016c66d  lea     rax, [rbp+arg_18]
0x18016c671  mov     [r11-48h], rax
0x18016c675  lea     rax, [rbp+arg_0]
0x18016c679  mov     [r11-50h], rax
0x18016c67d  lea     rax, [rbp+var_18]
0x18016c681  mov     [r11-58h], rax
0x18016c685  lea     rax, [rbp+arg_10]
0x18016c689  mov     [r11-60h], rax
0x18016c68d  lea     rax, [rbp+var_10]
0x18016c691  mov     [r11-68h], rax
0x18016c695  mov     [rbp+arg_10], edi
0x18016c698  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18016c69d  mov     eax, 80070057h
0x18016c6a2  jmp     loc_18016CAC8
0x18016c6a7  mov     [rcx+108h], edx
0x18016c6ad  mov     edi, 80004005h
0x18016c6b2  cmp     qword ptr [rcx+0F0h], 0
0x18016c6ba  jz      short loc_18016C6C0
0x18016c6bc  mov     ebx, edi
0x18016c6be  jmp     short loc_18016C6DF
0x18016c6c0  mov     ecx, 5DC0h; Size
0x18016c6c5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18016c6ca  mov     [rbx+0F0h], rax
0x18016c6d1  test    rax, rax
0x18016c6d4  jnz     loc_18016C763
0x18016c6da  mov     ebx, 8007000Eh
0x18016c6df  mov     eax, cs:CallbackContext
0x18016c6e5  cmp     eax, 2
0x18016c6e8  jbe     loc_18016CAC6
0x18016c6ee  lea     rax, aInit; "Init"
0x18016c6f5  mov     [rbp+arg_10], 0E0h
0x18016c6fc  mov     [rbp+var_10], rax
0x18016c700  lea     rdx, byte_1802A10C5
0x18016c707  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016c70e  mov     [rbp+var_18], rax
0x18016c712  lea     rax, aCaprogressivec_25; "CaProgressiveCompressor::Init failed co"...
0x18016c719  mov     [rbp+var_8], rax
0x18016c71d  lea     rax, [rbp+arg_0]
0x18016c721  mov     [rsp+70h+var_28], rax
0x18016c726  lea     rax, [rbp+var_10]
0x18016c72a  mov     [rsp+70h+var_30], rax
0x18016c72f  lea     rax, [rbp+arg_10]
0x18016c733  mov     [rsp+70h+var_38], rax
0x18016c738  lea     rax, [rbp+var_18]
0x18016c73c  mov     [rsp+70h+var_40], rax
0x18016c741  lea     rax, [rbp+arg_18]
0x18016c745  mov     [rsp+70h+var_48], rax
0x18016c74a  lea     rax, [rbp+var_8]
0x18016c74e  mov     [rsp+70h+var_50], rax
0x18016c753  mov     dword ptr [rbp+arg_18], edi
0x18016c756  mov     [rbp+arg_0], ebx
0x18016c759  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016c75e  jmp     loc_18016CAC6
0x18016c763  mov     esi, 3E8h
0x18016c768  mov     [rbx+0FCh], esi
0x18016c76e  cmp     qword ptr [rbx+90h], 0
0x18016c776  jz      short loc_18016C77C
0x18016c778  mov     ebx, edi
0x18016c77a  jmp     short loc_18016C797
0x18016c77c  mov     ecx, 3E80h; Size
0x18016c781  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18016c786  mov     [rbx+90h], rax
0x18016c78d  test    rax, rax
0x18016c790  jnz     short loc_18016C80B
0x18016c792  mov     ebx, 8007000Eh
0x18016c797  mov     eax, cs:CallbackContext
0x18016c79d  cmp     eax, 2
0x18016c7a0  jbe     loc_18016CAC6
0x18016c7a6  lea     rax, aInit; "Init"
0x18016c7ad  mov     [rbp+arg_10], 0E8h
0x18016c7b4  mov     [rbp+var_8], rax
0x18016c7b8  lea     rdx, word_1802A2592
0x18016c7bf  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016c7c6  mov     [rbp+var_10], rax
0x18016c7ca  lea     rax, aCaprogressivec_13; "CaProgressiveCompressor::Init failed co"...
0x18016c7d1  mov     [rbp+var_18], rax
0x18016c7d5  lea     rax, [rbp+arg_0]
0x18016c7d9  mov     [rsp+70h+var_28], rax
0x18016c7de  lea     rax, [rbp+var_8]
0x18016c7e2  mov     [rsp+70h+var_30], rax
0x18016c7e7  lea     rax, [rbp+arg_10]
0x18016c7eb  mov     [rsp+70h+var_38], rax
0x18016c7f0  lea     rax, [rbp+var_10]
0x18016c7f4  mov     [rsp+70h+var_40], rax
0x18016c7f9  lea     rax, [rbp+arg_18]
0x18016c7fd  mov     [rsp+70h+var_48], rax
0x18016c802  lea     rax, [rbp+var_18]
0x18016c806  jmp     loc_18016C74E
0x18016c80b  lea     rcx, [rbx+70h]
0x18016c80f  mov     [rbx+9Ch], esi
0x18016c815  call    ?Init@?$CaSimpleArray@UtagRECT@@@@QEAAJI@Z; CaSimpleArray<tagRECT>::Init(uint)
0x18016c81a  mov     esi, eax
0x18016c81c  test    eax, eax
0x18016c81e  jns     loc_18016C8A6
0x18016c824  mov     ecx, cs:CallbackContext
0x18016c82a  cmp     ecx, 2
0x18016c82d  jbe     short loc_18016C89F
0x18016c82f  lea     rax, aInit; "Init"
0x18016c836  mov     [rbp+arg_10], 0F0h
0x18016c83d  mov     [rbp+var_8], rax
0x18016c841  lea     rdx, word_1802A1E52
0x18016c848  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016c84f  mov     [rbp+var_10], rax
0x18016c853  lea     rax, aCaprogressivec_18; "CaProgressiveCompressor::Init failed co"...
0x18016c85a  mov     [rbp+var_18], rax
0x18016c85e  lea     rax, [rbp+arg_0]
0x18016c862  mov     [rsp+70h+var_28], rax
0x18016c867  lea     rax, [rbp+var_8]
0x18016c86b  mov     [rsp+70h+var_30], rax
0x18016c870  lea     rax, [rbp+arg_10]
0x18016c874  mov     [rsp+70h+var_38], rax
0x18016c879  lea     rax, [rbp+var_10]
0x18016c87d  mov     [rsp+70h+var_40], rax
0x18016c882  lea     rax, [rbp+arg_18]
0x18016c886  mov     [rsp+70h+var_48], rax
0x18016c88b  lea     rax, [rbp+var_18]
0x18016c88f  mov     [rsp+70h+var_50], rax
0x18016c894  mov     dword ptr [rbp+arg_18], edi
0x18016c897  mov     [rbp+arg_0], esi
0x18016c89a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016c89f  mov     eax, esi
0x18016c8a1  jmp     loc_18016CAC8
0x18016c8a6  lea     rcx, [rbx+0D0h]
0x18016c8ad  call    ?Init@?$CaSimpleArray@UtagRECT@@@@QEAAJI@Z; CaSimpleArray<tagRECT>::Init(uint)
0x18016c8b2  mov     esi, eax
0x18016c8b4  test    eax, eax
0x18016c8b6  jns     short loc_18016C8F3
0x18016c8b8  mov     ecx, cs:CallbackContext
0x18016c8be  cmp     ecx, 2
0x18016c8c1  jbe     short loc_18016C89F
0x18016c8c3  lea     rax, aInit; "Init"
0x18016c8ca  mov     [rbp+arg_10], 0F8h
0x18016c8d1  mov     [rbp+var_8], rax
0x18016c8d5  lea     rdx, byte_1802A2549
0x18016c8dc  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016c8e3  mov     [rbp+var_10], rax
0x18016c8e7  lea     rax, aCaprogressivec_29; "CaProgressiveCompressor::Init failed co"...
0x18016c8ee  jmp     loc_18016C85A
0x18016c8f3  mov     esi, 1F40h
0x18016c8f8  mov     ecx, esi; Size
0x18016c8fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18016c8ff  mov     [rbx+0C8h], rax
0x18016c906  test    rax, rax
0x18016c909  jnz     short loc_18016C984
0x18016c90b  mov     eax, cs:CallbackContext
0x18016c911  cmp     eax, 2
0x18016c914  jbe     short loc_18016C97A
0x18016c916  lea     rax, aInit; "Init"
0x18016c91d  mov     [rbp+arg_0], 0FFh
0x18016c924  mov     [rbp+arg_18], rax
0x18016c928  lea     rdx, byte_1802A226D
0x18016c92f  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016c936  mov     [rbp+arg_10], edi
0x18016c939  mov     [rbp+var_8], rax
0x18016c93d  lea     rax, aCaprogressivec_4; "CaProgressiveCompressor::Init ran out o"...
0x18016c944  mov     [rbp+var_10], rax
0x18016c948  lea     rax, [rbp+arg_18]
0x18016c94c  mov     [rsp+70h+var_30], rax
0x18016c951  lea     rax, [rbp+arg_0]
0x18016c955  mov     [rsp+70h+var_38], rax
0x18016c95a  lea     rax, [rbp+var_8]
0x18016c95e  mov     [rsp+70h+var_40], rax
0x18016c963  lea     rax, [rbp+arg_10]
0x18016c967  mov     [rsp+70h+var_48], rax
0x18016c96c  lea     rax, [rbp+var_10]
0x18016c970  mov     [rsp+70h+var_50], rax
0x18016c975  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18016c97a  mov     eax, 8007000Eh
0x18016c97f  jmp     loc_18016CAC8
0x18016c984  mov     r8, rsi; Size
0x18016c987  xor     edx, edx; Val
0x18016c989  mov     rcx, rax; void *
0x18016c98c  call    memset_0
0x18016c991  lea     rdx, [rbx+48h]
0x18016c995  call    ?CreateEncoderFactoryInstance@CacNx@@YAJW4EncoderFactoryVersion@1@PEAPEAVIEncoderFactory@1@@Z; CacNx::CreateEncoderFactoryInstance(CacNx::EncoderFactoryVersion,CacNx::IEncoderFactory * *)
0x18016c99a  mov     esi, eax
0x18016c99c  test    eax, eax
0x18016c99e  jns     short loc_18016C9DF
0x18016c9a0  mov     ecx, cs:CallbackContext
0x18016c9a6  cmp     ecx, 2
0x18016c9a9  jbe     loc_18016C89F
0x18016c9af  lea     rax, aInit; "Init"
0x18016c9b6  mov     [rbp+arg_10], 109h
0x18016c9bd  mov     [rbp+var_8], rax
0x18016c9c1  lea     rdx, byte_1802A1E9B
0x18016c9c8  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016c9cf  mov     [rbp+var_10], rax
0x18016c9d3  lea     rax, aCaprogressivec_20; "CaProgressiveCompressor::Init could not"...
0x18016c9da  jmp     loc_18016C85A
0x18016c9df  mov     rcx, [rbx+100h]
0x18016c9e6  lea     r8, [rbp+var_20]
0x18016c9ea  mov     [rbp+var_20], 0
0x18016c9f2  lea     rdx, IID_ICaGfxSourceProgressive
0x18016c9f9  mov     rax, [rcx]
0x18016c9fc  mov     rax, [rax]
0x18016c9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ca04  test    eax, eax
0x18016ca06  js      short loc_18016CA20
0x18016ca08  mov     rcx, [rbp+var_20]
0x18016ca0c  test    rcx, rcx
0x18016ca0f  jz      short loc_18016CA20
0x18016ca11  mov     rax, [rcx]
0x18016ca14  mov     rdx, rbx
0x18016ca17  mov     rax, [rax+18h]
0x18016ca1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016ca20  mov     rcx, rbx; this
0x18016ca23  call    ?setupBestEncodingEngine@CaProgressiveCompressor@@AEAAJXZ; CaProgressiveCompressor::setupBestEncodingEngine(void)
0x18016ca28  mov     ebx, eax
0x18016ca2a  test    eax, eax
0x18016ca2c  jns     short loc_18016CAA9
0x18016ca2e  mov     ecx, cs:CallbackContext
0x18016ca34  cmp     ecx, 2
0x18016ca37  jbe     short loc_18016CAA9
0x18016ca39  mov     [rbp+arg_0], eax
0x18016ca3c  lea     rdx, dword_1802A2224
0x18016ca43  lea     rax, aInit; "Init"
0x18016ca4a  mov     [rbp+arg_10], 11Bh
0x18016ca51  mov     [rbp+var_8], rax
0x18016ca55  lea     rax, aOnecoreTermsrv_33; "onecore\\termsrv\\cardp\\progressivecal"...
0x18016ca5c  mov     [rbp+var_10], rax
0x18016ca60  lea     rax, aCaprogressivec_20; "CaProgressiveCompressor::Init could not"...
0x18016ca67  mov     [rbp+var_18], rax
0x18016ca6b  lea     rax, [rbp+arg_0]
0x18016ca6f  mov     [rsp+70h+var_28], rax
0x18016ca74  lea     rax, [rbp+var_8]
0x18016ca78  mov     [rsp+70h+var_30], rax
0x18016ca7d  lea     rax, [rbp+arg_10]
0x18016ca81  mov     [rsp+70h+var_38], rax
0x18016ca86  lea     rax, [rbp+var_10]
0x18016ca8a  mov     [rsp+70h+var_40], rax
0x18016ca8f  lea     rax, [rbp+arg_18]
0x18016ca93  mov     [rsp+70h+var_48], rax
0x18016ca98  lea     rax, [rbp+var_18]
0x18016ca9c  mov     [rsp+70h+var_50], rax
0x18016caa1  mov     dword ptr [rbp+arg_18], edi
0x18016caa4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18016caa9  mov     rcx, [rbp+var_20]
0x18016caad  test    rcx, rcx
0x18016cab0  jz      short loc_18016CAC6
0x18016cab2  mov     [rbp+var_20], 0
0x18016caba  mov     rax, [rcx]
0x18016cabd  mov     rax, [rax+10h]
0x18016cac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016cac6  mov     eax, ebx
0x18016cac8  mov     rbx, [rsp+70h+arg_8]
0x18016cad0  add     rsp, 70h
0x18016cad4  pop     rdi
0x18016cad5  pop     rsi
0x18016cad6  pop     rbp
0x18016cad7  retn
```
