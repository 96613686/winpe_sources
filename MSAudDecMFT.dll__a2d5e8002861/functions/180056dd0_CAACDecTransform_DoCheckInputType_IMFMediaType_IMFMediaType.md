# CAACDecTransform::DoCheckInputType(IMFMediaType *,IMFMediaType *)

- ea: `0x180056dd0`
- end: `0x1800573f6`
- name: `?DoCheckInputType@CAACDecTransform@@MEAAJPEAUIMFMediaType@@0@Z`
- size: `1574`
- prototype: `__int64 __fastcall(CAACDecTransform *this, struct IMFMediaType *, struct IMFMediaType *)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001100`
- `0x180001250`
- `0x180003af0`
- `0x180004778`
- `0x18003dc40`
- `0x18003fbe0`
- `0x18004152c`
- `0x180041cac`
- `0x18004d320`
- `0x18004dd14`
- `0x180056dd0`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180056f55`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180056f55`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056f8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180057012`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180056f8f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180057012`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x180056e5d`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x180056e5d`

## string_xrefs

- `0x180057099`: `CAACDecTransform::DoCheckInputType() AOT: %d, extension AOT: %d`
- `0x180057108`: `CAACDecTransform::DoCheckInputType() Warning! MP4 extension sample rate is greater than 48kHz. Will only decode core AAC.`

## pseudocode

```c
__int64 __fastcall CAACDecTransform::DoCheckInputType(
        CAACDecTransform *this,
        struct IMFMediaType *a2,
        struct IMFMediaType *a3)
{
  TraceLoggingHelperBase *v5; // r14
  HRESULT v6; // ebx
  WAVEFORMATEX *v7; // rdi
  DWORD nSamplesPerSec; // edx
  unsigned int v9; // r9d
  const char *Format; // rax
  unsigned int v11; // r15d
  WAVEFORMATEX *v12; // rax
  _DWORD *v13; // r12
  int v14; // eax
  const char *v15; // rax
  unsigned int v16; // r9d
  __int16 v17; // ax
  WAVEFORMATEX *v18; // rax
  int v19; // edx
  DWORD v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // r8d
  int v24; // r9d
  __int16 v25; // cx
  DWORD nChannels; // [rsp+28h] [rbp-A1h]
  WAVEFORMATEX *ppWF; // [rsp+90h] [rbp-39h] BYREF
  __int16 v29; // [rsp+98h] [rbp-31h] BYREF
  WORD wBitsPerSample; // [rsp+9Ah] [rbp-2Fh] BYREF
  int v31; // [rsp+9Ch] [rbp-2Dh] BYREF
  int v32; // [rsp+A0h] [rbp-29h] BYREF
  int v33; // [rsp+A4h] [rbp-25h] BYREF
  int v34; // [rsp+A8h] [rbp-21h] BYREF
  int v35; // [rsp+ACh] [rbp-1Dh] BYREF
  int v36; // [rsp+B0h] [rbp-19h] BYREF
  int v37; // [rsp+B4h] [rbp-15h] BYREF
  DWORD v38; // [rsp+B8h] [rbp-11h] BYREF
  int v39; // [rsp+BCh] [rbp-Dh] BYREF
  __int64 v40; // [rsp+C0h] [rbp-9h] BYREF
  _QWORD v41[2]; // [rsp+C8h] [rbp-1h] BYREF
  GUID v42; // [rsp+D8h] [rbp+Fh] BYREF

  v5 = (CAACDecTransform *)((char *)this + 246640);
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)this + 246640),
    4u,
    "CAACDecTransform::DoCheckInputType",
    0x200u,
    "CAACDecTransform::DoCheckInputType()");
  ppWF = 0;
  memset_0((char *)this + 246184, 0, 0x1C4u);
  v6 = MFCreateWaveFormatExFromMFMediaType(a2, &ppWF, 0, 0);
  if ( v6 >= 0 )
  {
    CAACDecTransform::LogMediaTypeAttributes((CAACDecTransform *)((char *)this - 24), a2);
    v7 = ppWF;
    if ( ppWF->nChannels > 6u )
    {
      nChannels = ppWF->nChannels;
      Format = "CAACDecTransform::DoCheckInputType() nChannels =%d\n";
      v9 = 543;
      goto LABEL_7;
    }
    nSamplesPerSec = ppWF->nSamplesPerSec;
    if ( nSamplesPerSec
      && !(unsigned int)CAACDecTransform::IsSupportedSampleRate((CAACDecTransform *)((char *)this - 24), nSamplesPerSec) )
    {
      v9 = 550;
LABEL_6:
      nChannels = nSamplesPerSec;
      Format = "CAACDecTransform::DoCheckInputType() nSamplesPerSec =%d\n";
LABEL_7:
      v6 = -1072875852;
      TraceLoggingHelperBase::TraceVA(v5, 4u, "CAACDecTransform::DoCheckInputType", v9, Format, nChannels);
LABEL_59:
      TraceLoggingHelperBase::TraceVA(
        v5,
        2u,
        "CAACDecTransform::DoCheckInputType",
        0x329u,
        "Error %08X returned: File: %s, Line: %d",
        v6,
        "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdectransformxheaac.cpp",
        809);
      goto LABEL_60;
    }
    if ( nSamplesPerSec > 0xBB80 && nSamplesPerSec != 64000 && nSamplesPerSec != 88200 && nSamplesPerSec != 96000 )
    {
      v9 = 568;
      goto LABEL_6;
    }
    if ( v7->wFormatTag != 255 )
    {
      if ( v7->wFormatTag == 5632 )
        goto LABEL_58;
      if ( v7->wFormatTag != 5648 )
      {
LABEL_16:
        v6 = -1072875852;
        goto LABEL_59;
      }
    }
    if ( v7->wFormatTag == 5648 )
    {
      v11 = v7->cbSize + 18;
    }
    else
    {
      if ( v7->cbSize < 2u )
        goto LABEL_16;
      v11 = v7->cbSize + 30;
      v12 = (WAVEFORMATEX *)calloc(1u, v11);
      v7 = v12;
      if ( !v12 )
      {
        v6 = -2147024882;
        goto LABEL_59;
      }
      if ( memcpy_s(v12, v11, ppWF, 0x12u) || memcpy_s(&v7[1].nBlockAlign, ppWF->cbSize, &ppWF[1], ppWF->cbSize) )
      {
        free(v7);
        v6 = -2147467259;
        goto LABEL_59;
      }
      *(_QWORD *)&v7[1].wFormatTag = 16646144;
    }
    v13 = (_DWORD *)((char *)this + 246224);
    v14 = HEAACFormatBlockParser(
            (_DWORD)v7,
            v11,
            (int)this + 246188,
            (int)this + 246220,
            (__int64)this + 246224,
            (__int64)this + 246500);
    v31 = v14;
    if ( ppWF->wFormatTag == 255 )
    {
      free(v7);
      v14 = v31;
    }
    if ( v14 )
    {
      v15 = "CAACDecTransform::DoCheckInputType() call to HEAACFormatBlockParser() failed. Reject input media type.";
      v16 = 694;
LABEL_30:
      TraceLoggingHelperBase::TraceVA(v5, 4u, "CAACDecTransform::DoCheckInputType", v16, v15);
      goto LABEL_16;
    }
    *((_DWORD *)this + 61546) = 1;
    v17 = *((_WORD *)this + 123103);
    if ( (v17 & 0xFFFC) != 0 || v17 == 2 )
    {
      v15 = "CAACDecTransform::DoCheckInputType() Payload type must be 0, 1 or 3. Reject input media type";
      v16 = 705;
      goto LABEL_30;
    }
    if ( *((_DWORD *)this + 61555) )
    {
      TraceLoggingHelperBase::TraceVA(
        v5,
        4u,
        "CAACDecTransform::DoCheckInputType",
        0x2D3u,
        "CAACDecTransform::DoCheckInputType() AOT: %d, extension AOT: %d",
        *v13,
        *((_DWORD *)this + 61559));
      v18 = ppWF;
      if ( *((_DWORD *)this + 61558) > 0xBB80u
        && ppWF->nSamplesPerSec != 64000
        && ppWF->nSamplesPerSec != 88200
        && ppWF->nSamplesPerSec != 96000 )
      {
        TraceLoggingHelperBase::TraceVA(
          v5,
          4u,
          "CAACDecTransform::DoCheckInputType",
          0x2E6u,
          "CAACDecTransform::DoCheckInputType() MP4 sample rate must be 48kHz or lower. Reject media type");
        goto LABEL_16;
      }
      if ( *((_DWORD *)this + 61561) > 0xBB80u )
      {
        TraceLoggingHelperBase::TraceVA(
          v5,
          4u,
          "CAACDecTransform::DoCheckInputType",
          0x2EEu,
          "CAACDecTransform::DoCheckInputType() Warning! MP4 extension sample rate is greater than 48kHz. Will only decode core AAC.");
        v18 = ppWF;
      }
      v19 = *((_DWORD *)this + 61558);
      v20 = v18->nSamplesPerSec;
      if ( v20 != v19 && v20 != 2 * v19 )
      {
        TraceLoggingHelperBase::TraceVA(
          v5,
          4u,
          "CAACDecTransform::DoCheckInputType",
          0x2F4u,
          "CAACDecTransform::DoCheckInputType() Sample rates do not match (%d != %d). The sample rate from the ASC will take precedence.",
          v20,
          v19);
        *((_BYTE *)this + 255357) = 1;
        v42 = GUID_00000000_0000_0000_0000_000000000000;
        v21 = *((_QWORD *)this + 30836);
        if ( v21 )
        {
          v42 = *(GUID *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v21 + 280LL))(v21, v41);
          v22 = (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 30836) + 296LL))(*((_QWORD *)this + 30836));
        }
        else
        {
          v22 = 0;
        }
        if ( (unsigned int)dword_1800E40B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800E40B0, 0x200000000000LL, v22) )
        {
          v40 = 0x2000000;
          v29 = *((_WORD *)this + 123103);
          v32 = *((_DWORD *)this + 61563);
          v33 = *((_DWORD *)this + 61562);
          v34 = *((_DWORD *)this + 61561);
          v35 = *v13;
          wBitsPerSample = ppWF->wBitsPerSample;
          v36 = *((_DWORD *)this + 61564);
          LOWORD(v31) = ppWF->nChannels;
          v37 = *((_DWORD *)this + 61558);
          v38 = ppWF->nSamplesPerSec;
          v39 = v23;
          v41[0] = &v42;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(
            v38,
            (unsigned int)&dword_1800DC46C,
            v23,
            v24,
            (__int64)v41,
            (__int64)&v39,
            (__int64)&v38,
            (__int64)&v37,
            (__int64)&v31,
            (__int64)&v36,
            (__int64)&wBitsPerSample,
            (__int64)&v35,
            (__int64)&v34,
            (__int64)&v33,
            (__int64)&v32,
            (__int64)&v29,
            (__int64)&v40);
        }
        v18 = ppWF;
      }
      if ( v18->wFormatTag == 5648 )
      {
        v25 = *((_WORD *)this + 123103);
        if ( (v25 == 3 || !v25) && v11 > 0x1E && (unsigned __int64)v11 - 30 < 0x80 )
        {
          *((_DWORD *)this + 61658) = v11 - 30;
          if ( memcpy_s((char *)this + 246504, 0x80u, &v7[1].nBlockAlign, v11 - 30) )
            *((_DWORD *)this + 61658) = 0;
        }
      }
    }
  }
LABEL_58:
  if ( v6 )
    goto LABEL_59;
LABEL_60:
  ATL::CHeapPtr<tWAVEFORMATEX,ATL::CComAllocator>::~CHeapPtr<tWAVEFORMATEX,ATL::CComAllocator>(&ppWF);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180056dd0  mov     [rsp-8+arg_10], rbx
0x180056dd5  push    rbp
0x180056dd6  push    rsi
0x180056dd7  push    rdi
0x180056dd8  push    r12
0x180056dda  push    r13
0x180056ddc  push    r14
0x180056dde  push    r15
0x180056de0  lea     rbp, [rsp-27h]
0x180056de5  sub     rsp, 0F0h
0x180056dec  mov     rax, cs:__security_cookie
0x180056df3  xor     rax, rsp
0x180056df6  mov     [rbp+57h+var_38], rax
0x180056dfa  mov     rdi, rdx
0x180056dfd  mov     rsi, rcx
0x180056e00  lea     r14, [rcx+3C370h]
0x180056e07  lea     rax, aCaacdectransfo_31; "CAACDecTransform::DoCheckInputType()"
0x180056e0e  mov     [rsp+120h+Format], rax; Format
0x180056e13  mov     r9d, 200h; unsigned int
0x180056e19  lea     r13, aCaacdectransfo_29; "CAACDecTransform::DoCheckInputType"
0x180056e20  mov     r8, r13; char *
0x180056e23  mov     r12d, 4
0x180056e29  mov     edx, r12d; unsigned __int8
0x180056e2c  mov     rcx, r14; this
0x180056e2f  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180056e34  mov     [rbp+57h+ppWF], 0
0x180056e3c  lea     rcx, [rsi+3C1A8h]; void *
0x180056e43  xor     edx, edx; Val
0x180056e45  mov     r8d, 1C4h; Size
0x180056e4b  call    memset_0
0x180056e50  xor     r9d, r9d; Flags
0x180056e53  xor     r8d, r8d; pcbSize
0x180056e56  lea     rdx, [rbp+57h+ppWF]; ppWF
0x180056e5a  mov     rcx, rdi; pMFType
0x180056e5d  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x180056e64  nop     dword ptr [rax+rax+00h]
0x180056e69  mov     ebx, eax
0x180056e6b  test    eax, eax
0x180056e6d  js      loc_180057356
0x180056e73  mov     rdx, rdi; struct IMFMediaType *
0x180056e76  lea     rcx, [rsi-18h]; this
0x180056e7a  call    ?LogMediaTypeAttributes@CAACDecTransform@@AEAAXPEAUIMFMediaType@@@Z; CAACDecTransform::LogMediaTypeAttributes(IMFMediaType *)
0x180056e7f  mov     rdi, [rbp+57h+ppWF]
0x180056e83  cmp     word ptr [rdi+2], 6
0x180056e88  ja      loc_1800573DB
0x180056e8e  mov     edx, [rdi+4]; unsigned int
0x180056e91  test    edx, edx
0x180056e93  jz      short loc_180056ED0
0x180056e95  lea     rcx, [rsi-18h]; this
0x180056e99  call    ?IsSupportedSampleRate@CAACDecTransform@@AEAAHK@Z; CAACDecTransform::IsSupportedSampleRate(ulong)
0x180056e9e  test    eax, eax
0x180056ea0  jnz     short loc_180056ED0
0x180056ea2  mov     r9d, 226h; unsigned int
0x180056ea8  mov     dword ptr [rsp+120h+var_F8], edx
0x180056eac  lea     rax, aCaacdectransfo_22; "CAACDecTransform::DoCheckInputType() nS"...
0x180056eb3  mov     ebx, 0C00D36B4h
0x180056eb8  mov     [rsp+120h+Format], rax; Format
0x180056ebd  mov     r8, r13; char *
0x180056ec0  mov     edx, r12d; unsigned __int8
0x180056ec3  mov     rcx, r14; this
0x180056ec6  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180056ecb  jmp     loc_18005735A
0x180056ed0  cmp     edx, 0BB80h
0x180056ed6  jbe     short loc_180056EF8
0x180056ed8  cmp     edx, 0FA00h
0x180056ede  jz      short loc_180056EF8
0x180056ee0  cmp     edx, 15888h
0x180056ee6  jz      short loc_180056EF8
0x180056ee8  cmp     edx, 17700h
0x180056eee  jz      short loc_180056EF8
0x180056ef0  mov     r9d, 238h
0x180056ef6  jmp     short loc_180056EA8
0x180056ef8  movzx   edx, word ptr [rdi]
0x180056efb  mov     ecx, edx
0x180056efd  sub     ecx, 0FFh
0x180056f03  jz      short loc_180056F20
0x180056f05  sub     ecx, 1501h
0x180056f0b  jz      loc_180057356
0x180056f11  cmp     ecx, 10h
0x180056f14  jz      short loc_180056F20
0x180056f16  mov     ebx, 0C00D36B4h
0x180056f1b  jmp     loc_18005735A
0x180056f20  mov     eax, 1610h
0x180056f25  cmp     ax, dx
0x180056f28  jnz     short loc_180056F38
0x180056f2a  movzx   r15d, word ptr [rdi+10h]
0x180056f2f  add     r15d, 12h
0x180056f33  jmp     loc_180056FCA
0x180056f38  mov     eax, 2
0x180056f3d  cmp     [rdi+10h], ax
0x180056f41  jb      short loc_180056F16
0x180056f43  movzx   r15d, word ptr [rdi+10h]
0x180056f48  add     r15d, 1Eh
0x180056f4c  mov     r12d, r15d
0x180056f4f  mov     edx, r15d; Size
0x180056f52  lea     ecx, [rax-1]; Count
0x180056f55  call    cs:__imp_calloc
0x180056f5c  nop     dword ptr [rax+rax+00h]
0x180056f61  mov     rdi, rax
0x180056f64  test    rax, rax
0x180056f67  jnz     short loc_180056F73
0x180056f69  mov     ebx, 8007000Eh
0x180056f6e  jmp     loc_18005735A
0x180056f73  mov     r9d, 12h; SourceSize
0x180056f79  mov     r8, [rbp+57h+ppWF]; Source
0x180056f7d  mov     rdx, r12; DestinationSize
0x180056f80  mov     rcx, rdi; Destination
0x180056f83  call    memcpy_s
0x180056f88  test    eax, eax
0x180056f8a  jz      short loc_180056FA5
0x180056f8c  mov     rcx, rdi; Block
0x180056f8f  call    cs:__imp_free
0x180056f96  nop     dword ptr [rax+rax+00h]
0x180056f9b  mov     ebx, 80004005h
0x180056fa0  jmp     loc_18005735A
0x180056fa5  mov     r8, [rbp+57h+ppWF]
0x180056fa9  movzx   edx, word ptr [r8+10h]; DestinationSize
0x180056fae  add     r8, 12h; Source
0x180056fb2  lea     rcx, [rdi+1Eh]; Destination
0x180056fb6  mov     r9d, edx; SourceSize
0x180056fb9  call    memcpy_s
0x180056fbe  test    eax, eax
0x180056fc0  jnz     short loc_180056F8C
0x180056fc2  mov     qword ptr [rdi+12h], 0FE0000h
0x180056fca  lea     r12, [rsi+3C1D0h]
0x180056fd1  lea     r13, [rsi+3C1CCh]
0x180056fd8  lea     rax, [rsi+3C2E4h]
0x180056fdf  lea     r8, [rsi+3C1ACh]
0x180056fe6  mov     [rsp+120h+var_F8], rax
0x180056feb  mov     [rsp+120h+Format], r12
0x180056ff0  mov     r9, r13
0x180056ff3  mov     edx, r15d
0x180056ff6  mov     rcx, rdi
0x180056ff9  call    HEAACFormatBlockParser
0x180056ffe  mov     [rbp+57h+var_84], eax
0x180057001  mov     rcx, [rbp+57h+ppWF]
0x180057005  mov     edx, 0FFh
0x18005700a  cmp     dx, [rcx]
0x18005700d  jnz     short loc_180057021
0x18005700f  mov     rcx, rdi; Block
0x180057012  call    cs:__imp_free
0x180057019  nop     dword ptr [rax+rax+00h]
0x18005701e  mov     eax, [rbp+57h+var_84]
0x180057021  test    eax, eax
0x180057023  jz      short loc_180057050
0x180057025  lea     rax, aCaacdectransfo_54; "CAACDecTransform::DoCheckInputType() ca"...
0x18005702c  mov     r9d, 2B6h; unsigned int
0x180057032  mov     edx, 4; unsigned __int8
0x180057037  mov     [rsp+120h+Format], rax; Format
0x18005703c  lea     r8, aCaacdectransfo_29; "CAACDecTransform::DoCheckInputType"
0x180057043  mov     rcx, r14; this
0x180057046  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18005704b  jmp     loc_180056F16
0x180057050  mov     dword ptr [rsi+3C1A8h], 1
0x18005705a  movzx   eax, word ptr [rsi+3C1BEh]
0x180057061  mov     ecx, 0FFFCh
0x180057066  test    cx, ax
0x180057069  jnz     loc_1800573C9
0x18005706f  mov     ecx, 2
0x180057074  cmp     ax, cx
0x180057077  jz      loc_1800573C9
0x18005707d  cmp     dword ptr [r13+0], 0
0x180057082  jz      loc_180057356
0x180057088  mov     eax, [r12+0Ch]
0x18005708d  mov     dword ptr [rsp+120h+var_F0], eax
0x180057091  mov     eax, [r12]
0x180057095  mov     dword ptr [rsp+120h+var_F8], eax
0x180057099  lea     rax, aCaacdectransfo_51; "CAACDecTransform::DoCheckInputType() AO"...
0x1800570a0  mov     [rsp+120h+Format], rax; Format
0x1800570a5  mov     r9d, 2D3h; unsigned int
0x1800570ab  lea     r8, aCaacdectransfo_29; "CAACDecTransform::DoCheckInputType"
0x1800570b2  lea     r13d, [rcx+2]
0x1800570b6  mov     edx, r13d; unsigned __int8
0x1800570b9  mov     rcx, r14; this
0x1800570bc  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800570c1  mov     rax, [rbp+57h+ppWF]
0x1800570c5  mov     ecx, 0BB80h
0x1800570ca  cmp     [r12+8], ecx
0x1800570cf  jbe     short loc_180057101
0x1800570d1  cmp     dword ptr [rax+4], 0FA00h
0x1800570d8  jz      short loc_180057101
0x1800570da  cmp     dword ptr [rax+4], 15888h
0x1800570e1  jz      short loc_180057101
0x1800570e3  cmp     dword ptr [rax+4], 17700h
0x1800570ea  jz      short loc_180057101
0x1800570ec  lea     rax, aCaacdectransfo_38; "CAACDecTransform::DoCheckInputType() MP"...
0x1800570f3  mov     r9d, 2E6h
0x1800570f9  mov     edx, r13d
0x1800570fc  jmp     loc_180057037
0x180057101  cmp     [r12+14h], ecx
0x180057106  jbe     short loc_180057130
0x180057108  lea     rax, aCaacdectransfo_35; "CAACDecTransform::DoCheckInputType() Wa"...
0x18005710f  mov     [rsp+120h+Format], rax; Format
0x180057114  mov     r9d, 2EEh; unsigned int
0x18005711a  lea     r8, aCaacdectransfo_29; "CAACDecTransform::DoCheckInputType"
0x180057121  mov     edx, r13d; unsigned __int8
0x180057124  mov     rcx, r14; this
0x180057127  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18005712c  mov     rax, [rbp+57h+ppWF]
0x180057130  mov     edx, [r12+8]
0x180057135  mov     r8d, [rax+4]
0x180057139  cmp     r8d, edx
0x18005713c  jz      loc_1800572F2
0x180057142  lea     ecx, [rdx+rdx]
0x180057145  cmp     r8d, ecx
0x180057148  jz      loc_1800572F2
0x18005714e  mov     dword ptr [rsp+120h+var_F0], edx
0x180057152  mov     dword ptr [rsp+120h+var_F8], r8d
0x180057157  lea     rax, aCaacdectransfo_66; "CAACDecTransform::DoCheckInputType() Sa"...
0x18005715e  mov     [rsp+120h+Format], rax; Format
0x180057163  mov     r9d, 2F4h; unsigned int
0x180057169  lea     r8, aCaacdectransfo_29; "CAACDecTransform::DoCheckInputType"
0x180057170  mov     edx, r13d; unsigned __int8
0x180057173  mov     rcx, r14; this
0x180057176  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18005717b  mov     byte ptr [rsi+3E57Dh], 1
0x180057182  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180057189  movdqu  [rbp+57h+var_48], xmm0
0x18005718e  mov     rcx, [rsi+3C3A0h]
0x180057195  test    rcx, rcx
0x180057198  jnz     short loc_18005719F
0x18005719a  xor     r8d, r8d
0x18005719d  jmp     short loc_1800571D5
0x18005719f  mov     rax, [rcx]
0x1800571a2  lea     rdx, [rbp+57h+var_58]
0x1800571a6  mov     rax, [rax+118h]
0x1800571ad  call    cs:__guard_dispatch_icall_fptr
0x1800571b3  movups  xmm0, xmmword ptr [rax]
0x1800571b6  movdqu  [rbp+57h+var_48], xmm0
0x1800571bb  mov     rcx, [rsi+3C3A0h]
0x1800571c2  mov     rax, [rcx]
0x1800571c5  mov     rax, [rax+128h]
0x1800571cc  call    cs:__guard_dispatch_icall_fptr
0x1800571d2  mov     r8d, eax
0x1800571d5  mov     ecx, cs:dword_1800E40B0
0x1800571db  cmp     ecx, r13d
0x1800571de  jbe     loc_1800572EE
0x1800571e4  mov     rdx, 200000000000h
0x1800571ee  lea     rcx, dword_1800E40B0
0x1800571f5  call    _tlgKeywordOn
0x1800571fa  test    al, al
0x1800571fc  jz      loc_1800572EE
0x180057202  mov     [rbp+57h+var_60], 2000000h
0x18005720a  movzx   eax, word ptr [rsi+3C1BEh]
0x180057211  mov     [rbp+57h+var_88], ax
0x180057215  mov     eax, [r12+1Ch]
0x18005721a  mov     [rbp+57h+var_80], eax
0x18005721d  mov     eax, [r12+18h]
0x180057222  mov     [rbp+57h+var_7C], eax
0x180057225  mov     eax, [r12+14h]
0x18005722a  mov     [rbp+57h+var_78], eax
0x18005722d  mov     eax, [r12]
0x180057231  mov     [rbp+57h+var_74], eax
0x180057234  mov     rax, [rbp+57h+ppWF]
0x180057238  movzx   ecx, word ptr [rax+0Eh]
0x18005723c  mov     [rbp+57h+var_86], cx
0x180057240  mov     ecx, [r12+20h]
0x180057245  mov     [rbp+57h+var_70], ecx
0x180057248  movzx   ecx, word ptr [rax+2]
0x18005724c  mov     word ptr [rbp+57h+var_84], cx
0x180057250  mov     ecx, [r12+8]
0x180057255  mov     [rbp+57h+var_6C], ecx
0x180057258  mov     ecx, [rax+4]
0x18005725b  mov     [rbp+57h+var_68], ecx
0x18005725e  mov     [rbp+57h+var_64], r8d
0x180057262  lea     rax, [rbp+57h+var_48]
0x180057266  mov     [rbp+57h+var_58], rax
0x18005726a  lea     rax, [rbp+57h+var_60]
0x18005726e  mov     [rsp+120h+var_A0], rax
0x180057276  lea     rax, [rbp+57h+var_88]
0x18005727a  mov     [rsp+120h+var_A8], rax
0x18005727f  lea     rax, [rbp+57h+var_80]
0x180057283  mov     [rsp+120h+var_B0], rax
0x180057288  lea     rax, [rbp+57h+var_7C]
0x18005728c  mov     [rsp+120h+var_B8], rax
0x180057291  lea     rax, [rbp+57h+var_78]
0x180057295  mov     [rsp+120h+var_C0], rax
0x18005729a  lea     rax, [rbp+57h+var_74]
0x18005729e  mov     [rsp+120h+var_C8], rax
0x1800572a3  lea     rax, [rbp+57h+var_86]
0x1800572a7  mov     [rsp+120h+var_D0], rax
0x1800572ac  lea     rax, [rbp+57h+var_70]
0x1800572b0  mov     [rsp+120h+var_D8], rax
0x1800572b5  lea     rax, [rbp+57h+var_84]
0x1800572b9  mov     [rsp+120h+var_E0], rax
0x1800572be  lea     rax, [rbp+57h+var_6C]
0x1800572c2  mov     [rsp+120h+var_E8], rax
0x1800572c7  lea     rax, [rbp+57h+var_68]
0x1800572cb  mov     [rsp+120h+var_F0], rax
0x1800572d0  lea     rax, [rbp+57h+var_64]
0x1800572d4  mov     [rsp+120h+var_F8], rax
0x1800572d9  lea     rax, [rbp+57h+var_58]
0x1800572dd  mov     [rsp+120h+Format], rax
0x1800572e2  lea     rdx, dword_1800DC46C
0x1800572e9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByVal@$01@@U2@U3@U2@U2@U2@U2@U3@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByVal@$01@@4544445AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<2>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<2> const &,_tlgWrapperByVal<8> const &)
0x1800572ee  mov     rax, [rbp+57h+ppWF]
0x1800572f2  mov     ecx, 1610h
0x1800572f7  cmp     cx, [rax]
0x1800572fa  jnz     short loc_180057356
0x1800572fc  movzx   ecx, word ptr [rsi+3C1BEh]
  ... truncated ...
```
