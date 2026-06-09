# Planar::BC_CompressBitmap(uchar *,uchar *,uint,uchar *,uint,uchar *,uint,uchar *,uint,uint *,uint,uint,uint,int,int,int,Planar::_MATCH *,int)

- ea: `0x18003cfc8`
- end: `0x18003d8b0`
- name: `?BC_CompressBitmap@Planar@@YAHPEAE0I0I0I0IPEAIIIIHHHPEAU_MATCH@1@H@Z`
- size: `2280`
- prototype: `int(Planar *__hidden this, unsigned __int8 *, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int *, unsigned int, unsigned int, unsigned int, int, int, int, struct Planar::_MATCH *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18003cbf0`

## callees

- `0x1800018a4`
- `0x180002550`
- `0x180003158`
- `0x180004a94`
- `0x180006830`
- `0x18003cfc8`
- `0x18003d914`
- `0x180052b34`
- `0x1800542e0`
- `0x1800a9278`
- `0x1800ab094`
- `0x1800ac998`

## string_xrefs

- `0x18003d0d7`: `onecore\termsrv\rdpplatform\codecs\planar\planarcompression.cpp`
- `0x18003d153`: `onecore\termsrv\rdpplatform\codecs\planar\planarcompression.cpp`
- `0x18003d0be`: `BC_CompressBitmap`
- `0x18003d13a`: `BC_CompressBitmap`
- `0x18003d1e2`: `Compress 32 bpp Planar`
- `0x18003d545`: `Compress 32 bpp Planar`
- `0x18003d270`: `Compress 32 bpp`
- `0x18003d5de`: `Compress 32 bpp`
- `0x18003d2de`: `Compress 24 bpp`
- `0x18003d650`: `Compress 24 bpp`
- `0x18003d348`: `Compress 16bpp`
- `0x18003d6be`: `Compress 16bpp`
- `0x18003d3b2`: `Compress 15bpp`
- `0x18003d72c`: `Compress 15bpp`
- `0x18003d419`: `Compress 8bpp`
- `0x18003d797`: `Compress 8bpp`
- `0x18003d48b`: `*pcbCompressedData(%u)`
- `0x18003d4cb`: `Failed to compress main body`

## pseudocode

```c
__int64 __fastcall Planar::BC_CompressBitmap(
        Planar *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        void *a4,
        unsigned __int8 *a5,
        const char *a6,
        unsigned __int8 *a7,
        const char *a8,
        unsigned __int8 *a9,
        unsigned int *a10,
        unsigned int *a11,
        unsigned int a12,
        unsigned int a13,
        unsigned int a14,
        int a15,
        int a16,
        __int64 a17,
        struct Planar::_MATCH *a18)
{
  unsigned int v19; // r13d
  unsigned int v21; // edi
  unsigned int v22; // r15d
  __int16 *v23; // rdx
  const char *v24; // rax
  unsigned int v25; // ebx
  unsigned int v26; // esi
  unsigned int v27; // r15d
  unsigned int v28; // eax
  int v29; // r8d
  int v30; // r9d
  unsigned int v31; // ecx
  __int16 *v32; // rdx
  char *v33; // rdx
  unsigned int v34; // eax
  unsigned int v35; // ecx
  __int16 v36; // ax
  unsigned int *v37; // rax
  unsigned __int8 *v39; // [rsp+30h] [rbp-40h]
  unsigned int v40; // [rsp+38h] [rbp-38h]
  unsigned __int8 *v41; // [rsp+40h] [rbp-30h]
  unsigned int v42; // [rsp+48h] [rbp-28h]
  int v43; // [rsp+68h] [rbp-8h]
  const char *v45; // [rsp+C8h] [rbp+58h] BYREF

  v19 = (unsigned int)a3;
  if ( (unsigned int)CallbackContext > 5 )
  {
    v45 = (const char *)a2;
    a8 = "pbSrcBitmap(%p) pbDstBuffer(%p) cbDstBuffer(%#x)";
    LODWORD(a7) = (_DWORD)a3;
    a6 = (const char *)this;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_1801B5D23,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&a8,
      (__int64)&a6,
      (__int64)&v45,
      (__int64)&a7);
  }
  v21 = (unsigned int)a11;
  v22 = a12;
  if ( (unsigned int)CallbackContext > 5 )
  {
    v45 = "width(%u) height(%u)";
    LODWORD(a7) = a12;
    LODWORD(a9) = (_DWORD)a11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&byte_1801B5CE7,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&v45,
      (__int64)&a9,
      (__int64)&a7);
  }
  if ( !a4 )
  {
    if ( a15 )
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return 0;
      LODWORD(a7) = 560;
      v45 = "BC_CompressBitmap";
      v23 = word_1801B5CA2;
      a6 = "onecore\\termsrv\\rdpplatform\\codecs\\planar\\planarcompression.cpp";
      v24 = "pbBmpSplitColorChannels expected to be non-NULL!";
    }
    else
    {
      if ( (unsigned int)CallbackContext <= 2 )
        return 0;
      LODWORD(a7) = 567;
      v45 = "BC_CompressBitmap";
      v23 = (__int16 *)byte_1801B5C5D;
      a6 = "onecore\\termsrv\\rdpplatform\\codecs\\planar\\planarcompression.cpp";
      v24 = "pbXorBuffer expected to be non-NULL!";
    }
    a8 = v24;
    LODWORD(a9) = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (_DWORD)v23,
      (_DWORD)a3,
      (_DWORD)a4,
      (__int64)&a8,
      (__int64)&a9,
      (__int64)&a6,
      (__int64)&a7,
      (__int64)&v45);
    return 0;
  }
  v25 = a13;
  v26 = v22 * v21 * ((a13 + 7) >> 3);
  LODWORD(a7) = a15 != 0 ? a14 : 0;
  if ( a16 )
  {
    v27 = 1;
    switch ( a13 )
    {
      case 8u:
        goto LABEL_34;
      case 0xFu:
        if ( (unsigned int)CallbackContext > 5 )
        {
          v45 = "Compress 15bpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)qword_1801B5BB8,
            0,
            (_DWORD)a4,
            (__int64)&v45);
        }
        v28 = Planar::CompressV2<15,unsigned short,2,65407>(this, v19, a4, (int)a5, a17);
        goto LABEL_37;
      case 0x10u:
        if ( (unsigned int)CallbackContext > 5 )
        {
          v45 = "Compress 16bpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)byte_1801B5BD9,
            0,
            (_DWORD)a4,
            (__int64)&v45);
        }
        v28 = Planar::CompressV2<16,unsigned short,2,65535>(this, v19, a4, (int)a5, a17);
        goto LABEL_37;
      case 0x18u:
        if ( (unsigned int)CallbackContext > 5 )
        {
          v45 = "Compress 24 bpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)word_1801B5BFA,
            0,
            (_DWORD)a4,
            (__int64)&v45);
        }
        v28 = Planar::CompressV2<24,unsigned long,3,16777215>(
                (char *)this,
                (char *)a2,
                v26,
                3 * v21,
                v19,
                (char *)a4,
                (unsigned int)a5,
                a17);
        goto LABEL_37;
    }
    if ( a13 != 32 )
    {
LABEL_34:
      if ( (unsigned int)CallbackContext > 5 )
      {
        v45 = "Compress 8bpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&byte_1801B5B97,
          0,
          (_DWORD)a4,
          (__int64)&v45);
      }
      LODWORD(v39) = (_DWORD)a5;
      v28 = Planar::CompressV2Int(this, a2, (unsigned __int8 *)v26, v21, v19, (unsigned int)a4, v39, v40);
    }
    else if ( a15 )
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v45 = "Compress 32 bpp Planar";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&dword_1801B5C3C,
          0,
          (_DWORD)a4,
          (__int64)&v45);
      }
      LOBYTE(v42) = 3;
      LODWORD(v41) = v26;
      LODWORD(v39) = v19;
      v28 = Planar::BC_CompressPlanar(
              this,
              (unsigned __int8 *)0x20,
              v21,
              a12,
              4 * (v21 & 0x7FFFFFF),
              (int)a2,
              v39,
              (unsigned int)a4,
              v41,
              v42,
              (unsigned __int8)a7,
              1,
              (_DWORD)a18 != 0,
              v43);
    }
    else
    {
      if ( (unsigned int)CallbackContext > 5 )
      {
        v45 = "Compress 32 bpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801B5C1B,
          0,
          (_DWORD)a4,
          (__int64)&v45);
      }
      v28 = Planar::CompressV2<32,unsigned long,4,4294967295>(this, v19, a4, (int)a5, a17);
    }
LABEL_37:
    v31 = v28;
    if ( v28 )
    {
      *a10 = v28;
      if ( (unsigned int)CallbackContext > 5 )
      {
        v32 = word_1801B5B62;
LABEL_40:
        v45 = "*pcbCompressedData(%u)";
        LODWORD(a7) = v31;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v31,
          (_DWORD)v32,
          v29,
          v30,
          (__int64)&v45,
          (__int64)&a7);
        return v27;
      }
      return v27;
    }
    if ( (unsigned int)CallbackContext <= 4 )
      return 0;
    v33 = byte_1801B5B41;
LABEL_43:
    v45 = "Failed to compress main body";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (_DWORD)v33,
      0,
      v30,
      (__int64)&v45);
    return 0;
  }
  if ( v19 <= 8 )
  {
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(a7) = v19;
      v45 = "Not enough buffer space for header: %u";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        a15,
        (unsigned int)&byte_1801B59F7,
        (_DWORD)a3,
        (_DWORD)a4,
        (__int64)&v45,
        (__int64)&a7);
    }
    return 0;
  }
  v27 = 1;
  switch ( a13 )
  {
    case 8u:
LABEL_66:
      if ( (unsigned int)CallbackContext > 5 )
      {
        v45 = "Compress 8bpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801B5A7B,
          0,
          (_DWORD)a4,
          (__int64)&v45);
      }
      LODWORD(v39) = (_DWORD)a5;
      v34 = Planar::CompressV2Int(this, a2 + 8, (unsigned __int8 *)v26, v21, v19 - 8, (unsigned int)a4, v39, v40);
      break;
    case 0xFu:
      if ( (unsigned int)CallbackContext > 5 )
      {
        v45 = "Compress 15bpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&dword_1801B5A9C,
          0,
          (_DWORD)a4,
          (__int64)&v45);
      }
      v34 = Planar::CompressV2<15,unsigned short,2,65407>(this, v19 - 8, a4, (int)a5, a17);
      break;
    case 0x10u:
      if ( (unsigned int)CallbackContext > 5 )
      {
        v45 = "Compress 16bpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801B5ABD,
          0,
          (_DWORD)a4,
          (__int64)&v45);
      }
      v34 = Planar::CompressV2<16,unsigned short,2,65535>(this, v19 - 8, a4, (int)a5, a17);
      break;
    case 0x18u:
      if ( (unsigned int)CallbackContext > 5 )
      {
        v45 = "Compress 24 bpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)&word_1801B5ADE,
          0,
          (_DWORD)a4,
          (__int64)&v45);
      }
      v34 = Planar::CompressV2<24,unsigned long,3,16777215>(
              (char *)this,
              (char *)a2 + 8,
              v26,
              3 * v21,
              v19 - 8,
              (char *)a4,
              (unsigned int)a5,
              a17);
      break;
    case 0x20u:
      if ( a15 )
      {
        if ( (unsigned int)CallbackContext > 5 )
        {
          v45 = "Compress 32 bpp Planar";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)qword_1801B5B20,
            0,
            (_DWORD)a4,
            (__int64)&v45);
        }
        LOBYTE(v42) = 3;
        LODWORD(v41) = v26;
        LODWORD(v39) = v19 - 8;
        v34 = Planar::BC_CompressPlanar(
                this,
                (unsigned __int8 *)0x20,
                v21,
                a12,
                4 * (v21 & 0x7FFFFFF),
                (_DWORD)a2 + 8,
                v39,
                (unsigned int)a4,
                v41,
                v42,
                (unsigned __int8)a7,
                1,
                (_DWORD)a18 != 0,
                v43);
      }
      else
      {
        if ( (unsigned int)CallbackContext > 5 )
        {
          v45 = "Compress 32 bpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            (unsigned int)&CallbackContext,
            (unsigned int)&byte_1801B5AFF,
            0,
            (_DWORD)a4,
            (__int64)&v45);
        }
        v34 = Planar::CompressV2<32,unsigned long,4,4294967295>(this, v19 - 8, a4, (int)a5, a17);
      }
      break;
    default:
      goto LABEL_66;
  }
  v35 = v34;
  if ( !v34 )
  {
    if ( (unsigned int)CallbackContext <= 4 )
      return 0;
    v33 = byte_1801B5A25;
    goto LABEL_43;
  }
  *((_WORD *)a2 + 1) = v34;
  *(_WORD *)a2 = 0;
  if ( v25 <= 8 )
    v36 = v21;
  else
    v36 = 4 * ((v21 * ((v25 + 3) & 0xFFFFFFFC) + 31) >> 5);
  *((_WORD *)a2 + 2) = v36;
  v31 = v35 + 8;
  v37 = a10;
  *((_WORD *)a2 + 3) = v26;
  *v37 = v31;
  if ( (unsigned int)CallbackContext > 5 )
  {
    v32 = &word_1801B5A46;
    goto LABEL_40;
  }
  return v27;
}

```

## disassembly

```asm
0x18003cfc8  mov     r11, rsp
0x18003cfcb  mov     [r11+10h], rbx
0x18003cfcf  mov     [r11+8], rcx
0x18003cfd3  push    rbp
0x18003cfd4  push    rsi
0x18003cfd5  push    rdi
0x18003cfd6  push    r12
0x18003cfd8  push    r13
0x18003cfda  push    r14
0x18003cfdc  push    r15
0x18003cfde  mov     rbp, rsp
0x18003cfe1  sub     rsp, 70h
0x18003cfe5  mov     eax, cs:CallbackContext
0x18003cfeb  mov     r12, r9
0x18003cfee  mov     r13d, r8d
0x18003cff1  mov     r14, rdx
0x18003cff4  cmp     eax, 5
0x18003cff7  jbe     short loc_18003D03D
0x18003cff9  lea     rax, aPbsrcbitmapPPb; "pbSrcBitmap(%p) pbDstBuffer(%p) cbDstBu"...
0x18003d000  mov     [rbp+arg_18], rdx
0x18003d004  mov     [rbp+arg_38], rax
0x18003d008  lea     rdx, byte_1801B5D23
0x18003d00f  lea     rax, [rbp+arg_30]
0x18003d013  mov     dword ptr [rbp+arg_30], r8d
0x18003d017  mov     [r11-70h], rax
0x18003d01b  lea     rax, [rbp+arg_18]
0x18003d01f  mov     [r11-78h], rax
0x18003d023  lea     rax, [rbp+arg_28]
0x18003d027  mov     [r11-80h], rax
0x18003d02b  lea     rax, [rbp+arg_38]
0x18003d02f  mov     qword ptr [rsp+70h+var_50], rax
0x18003d034  mov     [rbp+arg_28], rcx
0x18003d038  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18003d03d  mov     eax, cs:CallbackContext
0x18003d043  mov     edi, dword ptr [rbp+arg_50]
0x18003d049  cmp     eax, 5
0x18003d04c  jbe     short loc_18003D096
0x18003d04e  mov     r15d, [rbp+arg_58]
0x18003d055  lea     rax, aWidthUHeightU; "width(%u) height(%u)"
0x18003d05c  mov     [rbp+arg_18], rax
0x18003d060  lea     rdx, byte_1801B5CE7
0x18003d067  lea     rax, [rbp+arg_30]
0x18003d06b  mov     dword ptr [rbp+arg_30], r15d
0x18003d06f  mov     [rsp+70h+var_40], rax
0x18003d074  lea     rax, [rbp+arg_40]
0x18003d07b  mov     [rsp+70h+var_48], rax
0x18003d080  lea     rax, [rbp+arg_18]
0x18003d084  mov     qword ptr [rsp+70h+var_50], rax
0x18003d089  mov     dword ptr [rbp+arg_40], edi
0x18003d08f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003d094  jmp     short loc_18003D09D
0x18003d096  mov     r15d, [rbp+arg_58]
0x18003d09d  test    r12, r12
0x18003d0a0  jnz     loc_18003D167
0x18003d0a6  mov     eax, cs:CallbackContext
0x18003d0ac  cmp     [rbp+arg_70], r12d
0x18003d0b3  jz      short loc_18003D131
0x18003d0b5  cmp     eax, 2
0x18003d0b8  jbe     loc_18003D892
0x18003d0be  lea     rax, aBcCompressbitm; "BC_CompressBitmap"
0x18003d0c5  mov     dword ptr [rbp+arg_30], 230h
0x18003d0cc  mov     [rbp+arg_18], rax
0x18003d0d0  lea     rdx, word_1801B5CA2
0x18003d0d7  lea     rax, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x18003d0de  mov     [rbp+arg_28], rax
0x18003d0e2  lea     rax, aPbbmpsplitcolo; "pbBmpSplitColorChannels expected to be "...
0x18003d0e9  mov     [rbp+arg_38], rax
0x18003d0ed  lea     rax, [rbp+arg_18]
0x18003d0f1  mov     [rsp+70h+var_30], rax
0x18003d0f6  lea     rax, [rbp+arg_30]
0x18003d0fa  mov     qword ptr [rsp+70h+var_38], rax
0x18003d0ff  lea     rax, [rbp+arg_28]
0x18003d103  mov     [rsp+70h+var_40], rax
0x18003d108  lea     rax, [rbp+arg_40]
0x18003d10f  mov     [rsp+70h+var_48], rax
0x18003d114  lea     rax, [rbp+arg_38]
0x18003d118  mov     qword ptr [rsp+70h+var_50], rax
0x18003d11d  mov     dword ptr [rbp+arg_40], 80004005h
0x18003d127  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003d12c  jmp     loc_18003D892
0x18003d131  cmp     eax, 2
0x18003d134  jbe     loc_18003D892
0x18003d13a  lea     rax, aBcCompressbitm; "BC_CompressBitmap"
0x18003d141  mov     dword ptr [rbp+arg_30], 237h
0x18003d148  mov     [rbp+arg_18], rax
0x18003d14c  lea     rdx, byte_1801B5C5D
0x18003d153  lea     rax, aOnecoreTermsrv_13; "onecore\\termsrv\\rdpplatform\\codecs\\"...
0x18003d15a  mov     [rbp+arg_28], rax
0x18003d15e  lea     rax, aPbxorbufferExp; "pbXorBuffer expected to be non-NULL!"
0x18003d165  jmp     short loc_18003D0E9
0x18003d167  mov     ebx, [rbp+arg_60]
0x18003d16d  mov     ecx, [rbp+arg_70]
0x18003d173  mov     eax, ecx
0x18003d175  lea     esi, [rbx+7]
0x18003d178  shr     esi, 3
0x18003d17b  imul    esi, edi
0x18003d17e  imul    esi, r15d
0x18003d182  neg     eax
0x18003d184  sbb     eax, eax
0x18003d186  and     eax, [rbp+arg_68]
0x18003d18c  cmp     [rbp+arg_78], 0
0x18003d193  mov     dword ptr [rbp+arg_30], eax
0x18003d196  jz      loc_18003D4F3
0x18003d19c  mov     r15d, 1
0x18003d1a2  sub     ebx, 8
0x18003d1a5  jz      loc_18003D40E
0x18003d1ab  sub     ebx, 7
0x18003d1ae  jz      loc_18003D3A7
0x18003d1b4  sub     ebx, r15d
0x18003d1b7  jz      loc_18003D33D
0x18003d1bd  sub     ebx, 8
0x18003d1c0  jz      loc_18003D2D3
0x18003d1c6  cmp     ebx, 8
0x18003d1c9  jnz     loc_18003D40E
0x18003d1cf  mov     eax, cs:CallbackContext
0x18003d1d5  test    ecx, ecx
0x18003d1d7  jz      loc_18003D26B
0x18003d1dd  cmp     eax, 5
0x18003d1e0  jbe     short loc_18003D20C
0x18003d1e2  lea     rax, aCompress32BppP; "Compress 32 bpp Planar"
0x18003d1e9  xor     r8d, r8d
0x18003d1ec  mov     [rbp+arg_18], rax
0x18003d1f0  lea     rdx, dword_1801B5C3C
0x18003d1f7  lea     rax, [rbp+arg_18]
0x18003d1fb  lea     rcx, CallbackContext
0x18003d202  mov     qword ptr [rsp+70h+var_50], rax
0x18003d207  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d20c  mov     r9d, [rbp+arg_58]; unsigned int
0x18003d213  xor     eax, eax
0x18003d215  cmp     dword ptr [rbp+arg_88], eax
0x18003d21b  mov     ecx, edi
0x18003d21d  mov     r8d, edi; unsigned int
0x18003d220  mov     edx, 20h ; ' '; unsigned __int8 *
0x18003d225  setnz   al
0x18003d228  and     ecx, 7FFFFFFh
0x18003d22e  mov     [rsp+70h+var_10], eax; int
0x18003d232  mov     eax, dword ptr [rbp+arg_30]
0x18003d235  mov     [rsp+70h+var_18], r15d; int
0x18003d23a  mov     dword ptr [rsp+70h+var_20], eax; unsigned __int8
0x18003d23e  mov     byte ptr [rsp+70h+var_28], 3; unsigned int
0x18003d243  mov     dword ptr [rsp+70h+var_30], esi; unsigned __int8 *
0x18003d247  mov     qword ptr [rsp+70h+var_38], r12; unsigned int
0x18003d24c  shl     ecx, 2
0x18003d24f  mov     dword ptr [rsp+70h+var_40], r13d; unsigned __int8 *
0x18003d254  mov     [rsp+70h+var_48], r14; int
0x18003d259  mov     [rsp+70h+var_50], ecx; unsigned int
0x18003d25d  mov     rcx, [rbp+Src]; this
0x18003d261  call    ?BC_CompressPlanar@Planar@@YAIPEAEIIIJ0I0IEHHH@Z; Planar::BC_CompressPlanar(uchar *,uint,uint,uint,long,uchar *,uint,uchar *,uint,uchar,int,int,int)
0x18003d266  jmp     loc_18003D466
0x18003d26b  cmp     eax, 5
0x18003d26e  jbe     short loc_18003D29A
0x18003d270  lea     rax, aCompress32Bpp; "Compress 32 bpp"
0x18003d277  xor     r8d, r8d
0x18003d27a  mov     [rbp+arg_18], rax
0x18003d27e  lea     rdx, byte_1801B5C1B
0x18003d285  lea     rax, [rbp+arg_18]
0x18003d289  lea     rcx, CallbackContext
0x18003d290  mov     qword ptr [rsp+70h+var_50], rax
0x18003d295  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d29a  mov     rax, [rbp+arg_80]
0x18003d2a1  lea     r9d, ds:0[rdi*4]
0x18003d2a9  mov     rcx, [rbp+Src]; Src
0x18003d2ad  mov     r8d, esi
0x18003d2b0  mov     qword ptr [rsp+70h+var_38], rax; __int64
0x18003d2b5  mov     rdx, r14
0x18003d2b8  mov     eax, dword ptr [rbp+arg_20]
0x18003d2bb  mov     dword ptr [rsp+70h+var_40], eax; int
0x18003d2bf  mov     [rsp+70h+var_48], r12; void *
0x18003d2c4  mov     [rsp+70h+var_50], r13d; int
0x18003d2c9  call    ??$CompressV2@$0CA@K$03$0PPPPPPPP@@Planar@@YAIPEAE0III0IPEAU_MATCH@0@@Z; Planar::CompressV2<32,ulong,4,4294967295>(uchar *,uchar *,uint,uint,uint,uchar *,uint,Planar::_MATCH *)
0x18003d2ce  jmp     loc_18003D466
0x18003d2d3  mov     eax, cs:CallbackContext
0x18003d2d9  cmp     eax, 5
0x18003d2dc  jbe     short loc_18003D308
0x18003d2de  lea     rax, aCompress24Bpp; "Compress 24 bpp"
0x18003d2e5  xor     r8d, r8d
0x18003d2e8  mov     [rbp+arg_18], rax
0x18003d2ec  lea     rdx, word_1801B5BFA
0x18003d2f3  lea     rax, [rbp+arg_18]
0x18003d2f7  lea     rcx, CallbackContext
0x18003d2fe  mov     qword ptr [rsp+70h+var_50], rax
0x18003d303  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d308  mov     rax, [rbp+arg_80]
0x18003d30f  lea     r9d, [rdi+rdi*2]
0x18003d313  mov     rcx, [rbp+Src]; Src
0x18003d317  mov     r8d, esi
0x18003d31a  mov     qword ptr [rsp+70h+var_38], rax; __int64
0x18003d31f  mov     rdx, r14
0x18003d322  mov     eax, dword ptr [rbp+arg_20]
0x18003d325  mov     dword ptr [rsp+70h+var_40], eax; int
0x18003d329  mov     [rsp+70h+var_48], r12; void *
0x18003d32e  mov     [rsp+70h+var_50], r13d; int
0x18003d333  call    ??$CompressV2@$0BI@K$02$0PPPPPP@@Planar@@YAIPEAE0III0IPEAU_MATCH@0@@Z; Planar::CompressV2<24,ulong,3,16777215>(uchar *,uchar *,uint,uint,uint,uchar *,uint,Planar::_MATCH *)
0x18003d338  jmp     loc_18003D466
0x18003d33d  mov     eax, cs:CallbackContext
0x18003d343  cmp     eax, 5
0x18003d346  jbe     short loc_18003D372
0x18003d348  lea     rax, aCompress16bpp; "Compress 16bpp"
0x18003d34f  xor     r8d, r8d
0x18003d352  mov     [rbp+arg_18], rax
0x18003d356  lea     rdx, byte_1801B5BD9
0x18003d35d  lea     rax, [rbp+arg_18]
0x18003d361  lea     rcx, CallbackContext
0x18003d368  mov     qword ptr [rsp+70h+var_50], rax
0x18003d36d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d372  mov     rax, [rbp+arg_80]
0x18003d379  lea     r9d, [rdi+rdi]
0x18003d37d  mov     rcx, [rbp+Src]; Src
0x18003d381  mov     r8d, esi
0x18003d384  mov     qword ptr [rsp+70h+var_38], rax; __int64
0x18003d389  mov     rdx, r14
0x18003d38c  mov     eax, dword ptr [rbp+arg_20]
0x18003d38f  mov     dword ptr [rsp+70h+var_40], eax; int
0x18003d393  mov     [rsp+70h+var_48], r12; void *
0x18003d398  mov     [rsp+70h+var_50], r13d; int
0x18003d39d  call    ??$CompressV2@$0BA@G$01$0PPPP@@Planar@@YAIPEAE0III0IPEAU_MATCH@0@@Z; Planar::CompressV2<16,ushort,2,65535>(uchar *,uchar *,uint,uint,uint,uchar *,uint,Planar::_MATCH *)
0x18003d3a2  jmp     loc_18003D466
0x18003d3a7  mov     eax, cs:CallbackContext
0x18003d3ad  cmp     eax, 5
0x18003d3b0  jbe     short loc_18003D3DC
0x18003d3b2  lea     rax, aCompress15bpp; "Compress 15bpp"
0x18003d3b9  xor     r8d, r8d
0x18003d3bc  mov     [rbp+arg_18], rax
0x18003d3c0  lea     rdx, qword_1801B5BB8
0x18003d3c7  lea     rax, [rbp+arg_18]
0x18003d3cb  lea     rcx, CallbackContext
0x18003d3d2  mov     qword ptr [rsp+70h+var_50], rax
0x18003d3d7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d3dc  mov     rax, [rbp+arg_80]
0x18003d3e3  lea     r9d, [rdi+rdi]
0x18003d3e7  mov     rcx, [rbp+Src]; Src
0x18003d3eb  mov     r8d, esi
0x18003d3ee  mov     qword ptr [rsp+70h+var_38], rax; __int64
0x18003d3f3  mov     rdx, r14
0x18003d3f6  mov     eax, dword ptr [rbp+arg_20]
0x18003d3f9  mov     dword ptr [rsp+70h+var_40], eax; int
0x18003d3fd  mov     [rsp+70h+var_48], r12; void *
0x18003d402  mov     [rsp+70h+var_50], r13d; int
0x18003d407  call    ??$CompressV2@$0P@G$01$0PPHP@@Planar@@YAIPEAE0III0IPEAU_MATCH@0@@Z; Planar::CompressV2<15,ushort,2,65407>(uchar *,uchar *,uint,uint,uint,uchar *,uint,Planar::_MATCH *)
0x18003d40c  jmp     short loc_18003D466
0x18003d40e  mov     eax, cs:CallbackContext
0x18003d414  cmp     eax, 5
0x18003d417  jbe     short loc_18003D443
0x18003d419  lea     rax, aCompress8bpp; "Compress 8bpp"
0x18003d420  xor     r8d, r8d
0x18003d423  mov     [rbp+arg_18], rax
0x18003d427  lea     rdx, byte_1801B5B97
0x18003d42e  lea     rax, [rbp+arg_18]
0x18003d432  lea     rcx, CallbackContext
0x18003d439  mov     qword ptr [rsp+70h+var_50], rax
0x18003d43e  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d443  mov     eax, dword ptr [rbp+arg_20]
0x18003d446  mov     r9d, edi; unsigned int
0x18003d449  mov     rcx, [rbp+Src]; this
0x18003d44d  mov     r8d, esi; unsigned __int8 *
0x18003d450  mov     dword ptr [rsp+70h+var_40], eax; unsigned __int8 *
0x18003d454  mov     rdx, r14; unsigned __int8 *
0x18003d457  mov     [rsp+70h+var_48], r12; unsigned int
0x18003d45c  mov     [rsp+70h+var_50], r13d; unsigned int
0x18003d461  call    ?CompressV2Int@Planar@@YAIPEAE0III0I@Z; Planar::CompressV2Int(uchar *,uchar *,uint,uint,uint,uchar *,uint)
0x18003d466  mov     ecx, eax
0x18003d468  test    eax, eax
0x18003d46a  jz      short loc_18003D4B5
0x18003d46c  mov     rax, [rbp+arg_48]
0x18003d473  mov     [rax], ecx
0x18003d475  mov     eax, cs:CallbackContext
0x18003d47b  cmp     eax, 5
0x18003d47e  jbe     loc_18003D895
0x18003d484  lea     rdx, word_1801B5B62
0x18003d48b  lea     rax, aPcbcompressedd; "*pcbCompressedData(%u)"
0x18003d492  mov     [rbp+arg_18], rax
0x18003d496  lea     rax, [rbp+arg_30]
0x18003d49a  mov     [rsp+70h+var_48], rax
0x18003d49f  lea     rax, [rbp+arg_18]
0x18003d4a3  mov     qword ptr [rsp+70h+var_50], rax
0x18003d4a8  mov     dword ptr [rbp+arg_30], ecx
0x18003d4ab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003d4b0  jmp     loc_18003D895
0x18003d4b5  mov     eax, cs:CallbackContext
0x18003d4bb  cmp     eax, 4
0x18003d4be  jbe     loc_18003D892
0x18003d4c4  lea     rdx, byte_1801B5B41
0x18003d4cb  lea     rax, aFailedToCompre; "Failed to compress main body"
0x18003d4d2  xor     r8d, r8d
0x18003d4d5  mov     [rbp+arg_18], rax
0x18003d4d9  lea     rcx, CallbackContext
0x18003d4e0  lea     rax, [rbp+arg_18]
0x18003d4e4  mov     qword ptr [rsp+70h+var_50], rax
0x18003d4e9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18003d4ee  jmp     loc_18003D892
0x18003d4f3  cmp     r13d, 8
0x18003d4f7  jbe     loc_18003D85A
0x18003d4fd  mov     eax, ebx
0x18003d4ff  mov     r15d, 1
0x18003d505  sub     eax, 8
0x18003d508  jz      loc_18003D78C
0x18003d50e  sub     eax, 7
0x18003d511  jz      loc_18003D721
0x18003d517  sub     eax, r15d
0x18003d51a  jz      loc_18003D6B3
  ... truncated ...
```
