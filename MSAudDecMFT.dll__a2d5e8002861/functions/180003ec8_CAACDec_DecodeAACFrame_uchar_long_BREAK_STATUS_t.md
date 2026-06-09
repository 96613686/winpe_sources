# CAACDec::DecodeAACFrame(uchar *,long,BREAK_STATUS_t *)

- ea: `0x180003ec8`
- end: `0x180004675`
- name: `?DecodeAACFrame@CAACDec@@IEAAJPEAEJPEAW4BREAK_STATUS_t@@@Z`
- size: `1965`
- prototype: `__int64 __fastcall(CAACDec *__hidden this, unsigned __int8 *, int, enum BREAK_STATUS_t *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180002550`
- `0x180004e54`

## callees

- `0x18000205c`
- `0x180003af0`
- `0x180003ec8`
- `0x180004fe0`
- `0x1800100ac`
- `0x1800305b0`
- `0x18003d268`
- `0x180041ad8`
- `0x180048570`
- `0x180048894`
- `0x180048aec`
- `0x18004dd14`
- `0x18005cbbc`
- `0x1800960c0`

## string_xrefs

- `0x1800043a9`: `CAACDec::DecodeAACFrame() channelConfig=%d, m_fIsSBR=%d, m_SamplesPerFrame=%d`
- `0x180004217`: `CAACDec::DecodeAACFrame apply delay compensation: dropSamples=%d, m_delaySamples=%d, offset=%d`
- `0x18000430f`: `CAACDec::DecodeAACFrame() After SBR+PS we should get stereo (actual numChannels: %d, actual channelConfig: %d)`

## pseudocode

```c
__int64 __fastcall CAACDec::DecodeAACFrame(CAACDec *this, unsigned __int8 *a2, int a3, enum BREAK_STATUS_t *a4)
{
  TraceLoggingHelperBase *v4; // rsi
  int v5; // ebp
  int v8; // r15d
  int v9; // edi
  __int64 result; // rax
  __int64 v11; // rcx
  bool v12; // zf
  int v13; // eax
  int v14; // r14d
  int *v15; // r12
  __int64 v16; // rcx
  int v17; // eax
  _BYTE *v18; // r14
  _DWORD *v19; // rcx
  int v20; // ebp
  int v21; // ecx
  int v22; // eax
  int v23; // edi
  int v24; // ecx
  __int64 v25; // rax
  int v26; // ecx
  __int64 v27; // rax
  int v28; // ebp
  int v29; // ecx
  int v30; // edi
  const char *Format; // rax
  int v32; // ecx
  __int64 v33; // rax
  int v34; // ecx
  unsigned int v35; // ebp
  unsigned __int8 *v36; // rdx
  __int64 v37; // rax
  unsigned int v38; // eax
  int v39; // [rsp+28h] [rbp-70h]
  int v40; // [rsp+30h] [rbp-68h]
  int v41; // [rsp+40h] [rbp-58h]
  int v42; // [rsp+44h] [rbp-54h]
  unsigned __int8 *v43; // [rsp+48h] [rbp-50h] BYREF
  int v44; // [rsp+A0h] [rbp+8h] BYREF
  bool v45; // [rsp+A8h] [rbp+10h] BYREF
  int v46; // [rsp+B0h] [rbp+18h]
  enum BREAK_STATUS_t *v47; // [rsp+B8h] [rbp+20h]

  v47 = a4;
  v46 = a3;
  v4 = (CAACDec *)((char *)this + 246488);
  v5 = a3;
  TraceLoggingHelperBase::TraceVA(
    (CAACDec *)((char *)this + 246488),
    5u,
    "CAACDec::DecodeAACFrame",
    0x3BFu,
    "CAACDec::DecodeAACFrame(len=%ld, pkt=0x%p)",
    a3,
    a2);
  v8 = 0;
  v9 = 0;
  v45 = a2 == 0;
  if ( !*((_QWORD *)this + 30745) )
  {
    result = CAACDec::OpenAACDec(this);
    v9 = result;
    if ( (int)result < 0 )
      return result;
    v11 = *((_QWORD *)this + 30753);
    if ( v11 )
    {
      v12 = (unsigned int)MFGetAttributeUINT32(v11, MF_LOW_LATENCY, 0) == 0;
      v13 = 0;
      if ( v12 )
        v13 = *((_DWORD *)this + 61484);
      *((_DWORD *)this + 61484) = v13;
    }
  }
  v14 = 0;
  v41 = 0;
  v42 = 0;
  while ( 1 )
  {
    *((_DWORD *)this + 61488) = *((_DWORD *)this + 61487);
    *((_WORD *)this + 122953) = *((_WORD *)this + 122954);
    *((_DWORD *)this + 61478) = *((_DWORD *)this + 61479);
    *(_QWORD *)((char *)this + 108) = *((unsigned int *)this + 28);
    *((_BYTE *)this + 96) = 0;
    if ( *((_BYTE *)this + 246948) && *((int *)this + 61736) <= 0 )
    {
      *((_BYTE *)this + 246948) = 0;
      TraceLoggingHelperBase::TraceVA(
        v4,
        5u,
        "CAACDec::DecodeAACFrame",
        0x3F0u,
        "CAACDec::DecodeAACFrame stop flushing");
      return (unsigned int)v9;
    }
    if ( (*(unsigned int (__fastcall **)(CAACDec *))(*(_QWORD *)this + 32LL))(this) == 1 )
    {
      *(_DWORD *)v47 = 2;
      return (unsigned int)v9;
    }
    v15 = (int *)((char *)this + 245892);
    if ( *((_DWORD *)this + 61473) )
      break;
    if ( !a2 )
      break;
    if ( !*((_BYTE *)this + 95) )
      break;
    *v15 = v5;
    v16 = *((_QWORD *)this + 30745);
    v43 = a2;
    v44 = v5;
    v17 = aacDecoder_Fill(v16, (__int64)&v43, (__int64)&v44, (__int64)this + 245892);
    if ( !v17 )
      break;
    TraceLoggingHelperBase::TraceVA(
      v4,
      2u,
      "CAACDec::DecodeAACFrame",
      0x414u,
      "CAACDec::DecodeAACFrame() Failed aacDecoder_Fill() with error 0x%x",
      v17);
    v9 = 0;
    *((_BYTE *)this + 95) = 1;
LABEL_55:
    if ( *((int *)this + 28) > 0 )
      v9 = CAACDec::WriteFrame(this);
    TraceLoggingHelperBase::TraceVA(
      v4,
      5u,
      "CAACDec::DecodeAACFrame",
      0x4F9u,
      "CAACDec::DecodeAACFrame() loop (m_ulOutputFrameCnt=%d, m_ulBadFrameCnt=%d)",
      *((_DWORD *)this + 61504),
      *((_DWORD *)this + 61505));
    if ( v9 )
      TraceLoggingHelperBase::TraceVA(
        v4,
        2u,
        "CAACDec::DecodeAACFrame",
        0x4FAu,
        "Error %08X returned: File: %s, Line: %d",
        v9,
        "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdecxheaac.cpp",
        1274);
    if ( *v15 == v5 )
    {
      v41 = v14 + 1;
      if ( (unsigned int)(v14 + 1) > 0x14 )
      {
        TraceLoggingHelperBase::TraceVA(
          v4,
          2u,
          "CAACDec::DecodeAACFrame",
          0x4FFu,
          "CAACDec::DecodeAACFrame() too many DecodeInternalBuffer() calls without progress");
        return (unsigned int)-1072875829;
      }
    }
    if ( v9 < 0 )
      return (unsigned int)v9;
    v42 = *v15;
LABEL_63:
    v5 = v46;
    v14 = v41;
    if ( !*v15 && !v45 && !*((_BYTE *)this + 246948) && !*((_BYTE *)this + 96) )
      return (unsigned int)v9;
  }
  v18 = (char *)this + 95;
  if ( *((_BYTE *)this + 95) )
  {
    LOBYTE(v44) = 1;
    v9 = CAACDec::DecodeInternalBuffer(this, &v45, (bool *)&v44);
    if ( v9 < 0 || !(_BYTE)v44 )
    {
LABEL_52:
      *v18 = 1;
      if ( v9 >= 0 )
      {
LABEL_54:
        v14 = v41;
        v5 = v42;
        goto LABEL_55;
      }
LABEL_53:
      TraceLoggingHelperBase::TraceVA(
        v4,
        2u,
        "CAACDec::DecodeAACFrame",
        0x4EFu,
        "CAACDec::DecodeAACFrame() Error concealment: Zero out buffer");
      memset_0((char *)this + 132, 0, 0xC000u);
      *((_DWORD *)this + 28) = *((_DWORD *)this + 27);
      goto LABEL_54;
    }
  }
  v19 = (_DWORD *)*((_QWORD *)this + 30746);
  v20 = v19[1];
  *((_DWORD *)this + 61636) = (v19[22] >> 15) & 1;
  if ( *((_BYTE *)this + 93) )
  {
    v39 = v19[21];
    *((_DWORD *)this + 61736) = v39;
    *((_DWORD *)this + 61735) = v39;
    *((_BYTE *)this + 93) = 0;
    TraceLoggingHelperBase::TraceVA(
      v4,
      5u,
      "CAACDec::DecodeAACFrame",
      0x433u,
      "CAACDec::DecodeAACFrame set up delayed samples, m_flushSamples=%d, m_delaySamples=%d",
      v39,
      v39);
    v12 = *((_DWORD *)this + 61518) == 42;
    *((_BYTE *)this + 80) = *((_DWORD *)this + 61518) != 42;
    TraceLoggingHelperBase::TraceVA(
      v4,
      5u,
      "CAACDec::DecodeAACFrame",
      0x440u,
      "CAACDec::DecodeAACFrame frameSize=%d, m_fIsSBR=%d, isUSAC=%d",
      v20,
      *((_DWORD *)this + 61636),
      v12);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay>::GetImpl'::`2'::impl)
      || *((_BYTE *)this + 80) )
    {
      if ( *((_DWORD *)this + 61636) )
      {
        v21 = *(_DWORD *)(*((_QWORD *)this + 30746) + 4LL);
        *((_DWORD *)this + 61735) = v21;
        *((_DWORD *)this + 61736) = v21;
      }
    }
  }
  if ( *((_BYTE *)this + 246948) )
  {
    v22 = *((_DWORD *)this + 61736);
    if ( v22 >= v20 )
      v23 = 0;
    else
      v23 = v20 - v22;
    v40 = v23 + v22 - v20;
    *((_DWORD *)this + 61736) = v40;
    TraceLoggingHelperBase::TraceVA(
      v4,
      5u,
      "CAACDec::DecodeAACFrame",
      0x464u,
      "CAACDec::DecodeAACFrame adjust flush samples: dropSamples=%d, m_flushSamples=%d",
      v23,
      v40);
  }
  else
  {
    v24 = *((_DWORD *)this + 61735);
    v25 = *((_QWORD *)this + 30746);
    v23 = v20;
    if ( v24 < v20 )
      v23 = *((_DWORD *)this + 61735);
    v26 = v24 - v23;
    *((_DWORD *)this + 61735) = v26;
    v8 = *(_DWORD *)(v25 + 12) * v23;
    TraceLoggingHelperBase::TraceVA(
      v4,
      5u,
      "CAACDec::DecodeAACFrame",
      0x46Eu,
      "CAACDec::DecodeAACFrame apply delay compensation: dropSamples=%d, m_delaySamples=%d, offset=%d",
      v23,
      v26,
      v8);
  }
  v27 = *((_QWORD *)this + 30746);
  v28 = v20 - v23;
  v29 = *(_DWORD *)(v27 + 88);
  v30 = *(_DWORD *)(v27 + 12);
  Format = "CAACDec::DecodeAACFrame() PS Content detected";
  *((_DWORD *)this + 61637) = (v29 & 0x20000) != 0;
  if ( (v29 & 0x20000) == 0 )
    Format = "CAACDec::DecodeAACFrame() Content is not PS";
  TraceLoggingHelperBase::TraceVA(v4, 5u, "CAACDec::DecodeAACFrame", 4 * ((v29 & 0x20000) == 0) + 1148, Format);
  *((_DWORD *)this + 61487) = **((_DWORD **)this + 30746);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::GetImpl'::`2'::impl)
    && *((_DWORD *)this + 61518) == 42 )
  {
    v32 = v28;
  }
  else
  {
    v32 = *(_DWORD *)(*((_QWORD *)this + 30746) + 68LL) * ((*((_DWORD *)this + 61636) != 0) + 1);
  }
  *((_DWORD *)this + 29) = v32;
  if ( *((_DWORD *)this + 61637) )
  {
    v33 = *((_QWORD *)this + 30746);
    v34 = *(_DWORD *)(v33 + 12);
    if ( v34 != 2 )
    {
      TraceLoggingHelperBase::TraceVA(
        v4,
        2u,
        "CAACDec::DecodeAACFrame",
        0x49Bu,
        "CAACDec::DecodeAACFrame() After SBR+PS we should get stereo (actual numChannels: %d, actual channelConfig: %d)",
        v34,
        *(_DWORD *)(v33 + 60));
      v8 = 0;
      *v18 = 1;
      v9 = -2147467259;
      goto LABEL_53;
    }
  }
  v35 = v30 * v28;
  TraceLoggingHelperBase::TraceVA(
    v4,
    5u,
    "CAACDec::DecodeAACFrame",
    0x4A3u,
    "CAACDec::DecodeAACFrame() m_dwPrevOutSamplesPerSec=%d, m_dwOutSamplesPerSec=%d",
    *((_DWORD *)this + 61488),
    *((_DWORD *)this + 61487));
  TraceLoggingHelperBase::TraceVA(
    v4,
    5u,
    "CAACDec::DecodeAACFrame",
    0x4A5u,
    "CAACDec::DecodeAACFrame() channelConfig=%d, m_fIsSBR=%d, m_SamplesPerFrame=%d",
    *(_DWORD *)(*((_QWORD *)this + 30746) + 60LL),
    *((_DWORD *)this + 61636),
    *((_DWORD *)this + 29));
  TraceLoggingHelperBase::TraceVA(
    v4,
    5u,
    "CAACDec::DecodeAACFrame",
    0x4A7u,
    "CAACDec::DecodeAACFrame() nPCMSamplesDecoded=%d, nChannels=%d",
    v35,
    *(_DWORD *)(*((_QWORD *)this + 30746) + 12LL));
  v9 = (*(__int64 (__fastcall **)(CAACDec *))(*(_QWORD *)this + 8LL))(this);
  if ( v9 < 0 )
  {
LABEL_51:
    v8 = 0;
    goto LABEL_52;
  }
  if ( *((_BYTE *)this + 96) )
  {
    TraceLoggingHelperBase::TraceVA(
      v4,
      5u,
      "CAACDec::DecodeAACFrame",
      0x4B5u,
      "CAACDec::DecodeAACFrame() reprocessing current pkt");
    CAACDec::ResetAACDec(this);
    v8 = 0;
    goto LABEL_63;
  }
  if ( !*((_BYTE *)this + 245940) )
  {
    if ( *((_BYTE *)this + 92) )
    {
      if ( *((_DWORD *)this + 61484) )
      {
        *((_BYTE *)this + 92) = 0;
        if ( *((_DWORD *)this + 12) )
        {
          v37 = *((_QWORD *)this + 5);
          *((_QWORD *)this + 7) = v37;
          *((_QWORD *)this + 9) = v37;
          *((_DWORD *)this + 12) = 0;
        }
      }
    }
    v38 = (*((_DWORD *)this + 30) * v35) >> 3;
    *((_DWORD *)this + 28) = v38;
    if ( v38 )
      v9 = CAACDec::FillOutputBuffer(this, v36, v35, v8);
    goto LABEL_51;
  }
  *((_BYTE *)this + 93) = 1;
  if ( *((_BYTE *)this + 99) )
  {
    CAACDec::CloseUpAACDec(this);
    *((_BYTE *)this + 99) = 0;
  }
  else
  {
    *v18 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180003ec8  mov     r11, rsp
0x180003ecb  mov     [r11+20h], r9
0x180003ecf  mov     [r11+18h], r8d
0x180003ed3  push    rbx
0x180003ed4  push    rbp
0x180003ed5  push    rsi
0x180003ed6  push    rdi
0x180003ed7  push    r12
0x180003ed9  push    r13
0x180003edb  push    r14
0x180003edd  push    r15
0x180003edf  sub     rsp, 58h
0x180003ee3  mov     [r11-68h], rdx
0x180003ee7  lea     rsi, [rcx+3C2D8h]
0x180003eee  mov     [r11-70h], r8d
0x180003ef2  lea     rax, aCaacdecDecodea_38; "CAACDec::DecodeAACFrame(len=%ld, pkt=0x"...
0x180003ef9  mov     ebp, r8d
0x180003efc  mov     [r11-78h], rax
0x180003f00  mov     r13, rdx
0x180003f03  lea     r8, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x180003f0a  mov     rbx, rcx
0x180003f0d  mov     r9d, 3BFh; unsigned int
0x180003f13  mov     rcx, rsi; this
0x180003f16  mov     edx, 5; unsigned __int8
0x180003f1b  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180003f20  xor     r15d, r15d
0x180003f23  test    r13, r13
0x180003f26  mov     edi, r15d
0x180003f29  setz    [rsp+98h+arg_8]
0x180003f31  cmp     [rbx+3C0C8h], r15
0x180003f38  jnz     short loc_180003F7A
0x180003f3a  mov     rcx, rbx; this
0x180003f3d  call    ?OpenAACDec@CAACDec@@IEAAJXZ; CAACDec::OpenAACDec(void)
0x180003f42  mov     edi, eax
0x180003f44  test    eax, eax
0x180003f46  js      loc_180004663
0x180003f4c  mov     rcx, [rbx+3C108h]
0x180003f53  test    rcx, rcx
0x180003f56  jz      short loc_180003F7A
0x180003f58  xor     r8d, r8d
0x180003f5b  lea     rdx, MF_LOW_LATENCY
0x180003f62  call    MFGetAttributeUINT32
0x180003f67  test    eax, eax
0x180003f69  mov     eax, r15d
0x180003f6c  jnz     short loc_180003F74
0x180003f6e  mov     eax, [rbx+3C0B0h]
0x180003f74  mov     [rbx+3C0B0h], eax
0x180003f7a  mov     r14d, r15d
0x180003f7d  mov     [rsp+98h+var_58], r15d
0x180003f82  mov     [rsp+98h+var_54], r15d
0x180003f87  mov     eax, [rbx+3C0BCh]
0x180003f8d  mov     [rbx+3C0C0h], eax
0x180003f93  movzx   eax, word ptr [rbx+3C094h]
0x180003f9a  mov     [rbx+3C092h], ax
0x180003fa1  mov     eax, [rbx+3C09Ch]
0x180003fa7  mov     [rbx+3C098h], eax
0x180003fad  mov     eax, [rbx+70h]
0x180003fb0  mov     [rbx+6Ch], eax
0x180003fb3  mov     [rbx+70h], r15d
0x180003fb7  mov     [rbx+60h], r15b
0x180003fbb  cmp     [rbx+3C4A4h], r15b
0x180003fc2  jz      short loc_180003FD1
0x180003fc4  cmp     [rbx+3C4A0h], r15d
0x180003fcb  jle     loc_1800045D9
0x180003fd1  mov     rax, [rbx]
0x180003fd4  mov     rcx, rbx
0x180003fd7  mov     rax, [rax+20h]
0x180003fdb  call    cs:__guard_dispatch_icall_fptr
0x180003fe1  cmp     eax, 1
0x180003fe4  jz      loc_180004653
0x180003fea  lea     r12, [rbx+3C084h]
0x180003ff1  cmp     [r12], r15d
0x180003ff5  jnz     short loc_180004068
0x180003ff7  test    r13, r13
0x180003ffa  jz      short loc_180004068
0x180003ffc  cmp     [rbx+5Fh], r15b
0x180004000  jz      short loc_180004068
0x180004002  mov     [r12], ebp
0x180004006  lea     r8, [rsp+98h+arg_0]
0x18000400e  mov     rcx, [rbx+3C0C8h]
0x180004015  lea     rdx, [rsp+98h+var_50]
0x18000401a  mov     r9, r12
0x18000401d  mov     [rsp+98h+var_50], r13
0x180004022  mov     [rsp+98h+arg_0], ebp
0x180004029  call    aacDecoder_Fill
0x18000402e  test    eax, eax
0x180004030  jz      short loc_180004068
0x180004032  mov     [rsp+98h+var_70], eax
0x180004036  lea     r8, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x18000403d  lea     rax, aCaacdecDecodea_44; "CAACDec::DecodeAACFrame() Failed aacDec"...
0x180004044  mov     r9d, 414h; unsigned int
0x18000404a  mov     edx, 2; unsigned __int8
0x18000404f  mov     [rsp+98h+Format], rax; Format
0x180004054  mov     rcx, rsi; this
0x180004057  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18000405c  mov     edi, r15d
0x18000405f  mov     byte ptr [rbx+5Fh], 1
0x180004063  jmp     loc_1800044E7
0x180004068  lea     r14, [rbx+5Fh]
0x18000406c  cmp     [r14], r15b
0x18000406f  jz      short loc_1800040A9
0x180004071  lea     r8, [rsp+98h+arg_0]; bool *
0x180004079  mov     byte ptr [rsp+98h+arg_0], 1
0x180004081  lea     rdx, [rsp+98h+arg_8]; bool *
0x180004089  mov     rcx, rbx; this
0x18000408c  call    ?DecodeInternalBuffer@CAACDec@@AEAAJAEA_N0@Z; CAACDec::DecodeInternalBuffer(bool &,bool &)
0x180004091  mov     edi, eax
0x180004093  test    eax, eax
0x180004095  js      loc_180004496
0x18000409b  cmp     byte ptr [rsp+98h+arg_0], r15b
0x1800040a3  jz      loc_180004496
0x1800040a9  mov     rcx, [rbx+3C0D0h]
0x1800040b0  mov     eax, [rcx+58h]
0x1800040b3  mov     ebp, [rcx+4]
0x1800040b6  shr     eax, 0Fh
0x1800040b9  and     eax, 1
0x1800040bc  mov     [rbx+3C310h], eax
0x1800040c2  cmp     [rbx+5Dh], r15b
0x1800040c6  jz      loc_18000418C
0x1800040cc  mov     eax, [rcx+54h]
0x1800040cf  lea     r8, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x1800040d6  mov     dword ptr [rsp+98h+var_68], eax
0x1800040da  mov     edi, 5
0x1800040df  mov     [rsp+98h+var_70], eax
0x1800040e3  mov     r9d, 433h; unsigned int
0x1800040e9  mov     [rbx+3C4A0h], eax
0x1800040ef  mov     edx, edi; unsigned __int8
0x1800040f1  mov     [rbx+3C49Ch], eax
0x1800040f7  mov     rcx, rsi; this
0x1800040fa  lea     rax, aCaacdecDecodea_8; "CAACDec::DecodeAACFrame set up delayed "...
0x180004101  mov     [rbx+5Dh], r15b
0x180004105  mov     [rsp+98h+Format], rax; Format
0x18000410a  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18000410f  cmp     dword ptr [rbx+3C138h], 2Ah ; '*'
0x180004116  lea     r8, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x18000411d  mov     r9d, 440h; unsigned int
0x180004123  mov     edx, edi; unsigned __int8
0x180004125  setnz   al
0x180004128  mov     rcx, rsi; this
0x18000412b  mov     [rbx+50h], al
0x18000412e  mov     eax, r15d
0x180004131  setz    al
0x180004134  mov     [rsp+98h+var_60], eax
0x180004138  mov     eax, [rbx+3C310h]
0x18000413e  mov     dword ptr [rsp+98h+var_68], eax
0x180004142  lea     rax, aCaacdecDecodea_37; "CAACDec::DecodeAACFrame frameSize=%d, m"...
0x180004149  mov     [rsp+98h+var_70], ebp
0x18000414d  mov     [rsp+98h+Format], rax; Format
0x180004152  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180004157  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay> `wil::Feature<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay>::GetImpl(void)'::`2'::impl
0x18000415e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACSbrDelay>::__private_IsEnabled(void)
0x180004163  test    al, al
0x180004165  jz      short loc_18000416D
0x180004167  cmp     [rbx+50h], r15b
0x18000416b  jz      short loc_18000418C
0x18000416d  cmp     [rbx+3C310h], r15d
0x180004174  jz      short loc_18000418C
0x180004176  mov     rax, [rbx+3C0D0h]
0x18000417d  mov     ecx, [rax+4]
0x180004180  mov     [rbx+3C49Ch], ecx
0x180004186  mov     [rbx+3C4A0h], ecx
0x18000418c  cmp     [rbx+3C4A4h], r15b
0x180004193  jz      short loc_1800041E1
0x180004195  mov     eax, [rbx+3C4A0h]
0x18000419b  cmp     eax, ebp
0x18000419d  jge     short loc_1800041A5
0x18000419f  mov     edi, ebp
0x1800041a1  sub     edi, eax
0x1800041a3  jmp     short loc_1800041A7
0x1800041a5  xor     edi, edi
0x1800041a7  sub     eax, ebp
0x1800041a9  lea     r8, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x1800041b0  add     eax, edi
0x1800041b2  mov     r9d, 464h; unsigned int
0x1800041b8  mov     dword ptr [rsp+98h+var_68], eax
0x1800041bc  mov     edx, 5; unsigned __int8
0x1800041c1  mov     [rbx+3C4A0h], eax
0x1800041c7  mov     rcx, rsi; this
0x1800041ca  lea     rax, aCaacdecDecodea_42; "CAACDec::DecodeAACFrame adjust flush sa"...
0x1800041d1  mov     [rsp+98h+var_70], edi
0x1800041d5  mov     [rsp+98h+Format], rax; Format
0x1800041da  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800041df  jmp     short loc_180004238
0x1800041e1  mov     ecx, [rbx+3C49Ch]
0x1800041e7  lea     r8, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x1800041ee  mov     rax, [rbx+3C0D0h]
0x1800041f5  cmp     ecx, ebp
0x1800041f7  mov     edi, ebp
0x1800041f9  mov     r9d, 46Eh; unsigned int
0x1800041ff  cmovl   edi, ecx
0x180004202  mov     edx, 5; unsigned __int8
0x180004207  sub     ecx, edi
0x180004209  mov     r15d, edi
0x18000420c  mov     [rbx+3C49Ch], ecx
0x180004212  imul    r15d, [rax+0Ch]
0x180004217  lea     rax, aCaacdecDecodea_22; "CAACDec::DecodeAACFrame apply delay com"...
0x18000421e  mov     [rsp+98h+var_60], r15d
0x180004223  mov     dword ptr [rsp+98h+var_68], ecx
0x180004227  mov     rcx, rsi; this
0x18000422a  mov     [rsp+98h+var_70], edi
0x18000422e  mov     [rsp+98h+Format], rax; Format
0x180004233  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180004238  mov     rax, [rbx+3C0D0h]
0x18000423f  lea     rdx, aCaacdecDecodea_11; "CAACDec::DecodeAACFrame() Content is no"...
0x180004246  sub     ebp, edi
0x180004248  lea     r8, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x18000424f  mov     r9d, 0
0x180004255  mov     ecx, [rax+58h]
0x180004258  bt      ecx, 11h
0x18000425c  mov     edi, [rax+0Ch]
0x18000425f  lea     rax, aCaacdecDecodea_6; "CAACDec::DecodeAACFrame() PS Content de"...
0x180004266  setb    r9b
0x18000426a  bt      ecx, 11h
0x18000426e  mov     [rbx+3C314h], r9d
0x180004275  mov     rcx, rsi; this
0x180004278  cmovnb  rax, rdx
0x18000427c  xor     r9d, 1
0x180004280  mov     edx, 5; unsigned __int8
0x180004285  mov     [rsp+98h+Format], rax; Format
0x18000428a  lea     r9d, ds:47Ch[r9*4]; unsigned int
0x180004292  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180004297  mov     rax, [rbx+3C0D0h]
0x18000429e  mov     ecx, [rax]
0x1800042a0  mov     [rbx+3C0BCh], ecx
0x1800042a6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter> `wil::Feature<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::GetImpl(void)'::`2'::impl
0x1800042ad  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_XHEAACPeakLimiter>::__private_IsEnabled(void)
0x1800042b2  test    al, al
0x1800042b4  jz      short loc_1800042C3
0x1800042b6  cmp     dword ptr [rbx+3C138h], 2Ah ; '*'
0x1800042bd  jnz     short loc_1800042C3
0x1800042bf  mov     ecx, ebp
0x1800042c1  jmp     short loc_1800042DC
0x1800042c3  mov     eax, [rbx+3C310h]
0x1800042c9  neg     eax
0x1800042cb  mov     rax, [rbx+3C0D0h]
0x1800042d2  sbb     ecx, ecx
0x1800042d4  neg     ecx
0x1800042d6  inc     ecx
0x1800042d8  imul    ecx, [rax+44h]
0x1800042dc  mov     [rbx+74h], ecx
0x1800042df  cmp     dword ptr [rbx+3C314h], 0
0x1800042e6  jz      short loc_180004339
0x1800042e8  mov     rax, [rbx+3C0D0h]
0x1800042ef  mov     ecx, [rax+0Ch]
0x1800042f2  cmp     ecx, 2
0x1800042f5  jz      short loc_180004339
0x1800042f7  mov     eax, [rax+3Ch]
0x1800042fa  lea     r8, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x180004301  mov     dword ptr [rsp+98h+var_68], eax
0x180004305  mov     r9d, 49Bh; unsigned int
0x18000430b  mov     [rsp+98h+var_70], ecx
0x18000430f  lea     rax, aCaacdecDecodea_20; "CAACDec::DecodeAACFrame() After SBR+PS "...
0x180004316  mov     rcx, rsi; this
0x180004319  mov     [rsp+98h+Format], rax; Format
0x18000431e  mov     edx, 2; unsigned __int8
0x180004323  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180004328  xor     r15d, r15d
0x18000432b  mov     byte ptr [r14], 1
0x18000432f  mov     edi, 80004005h
0x180004334  jmp     loc_18000449E
0x180004339  mov     eax, [rbx+3C0BCh]
0x18000433f  mov     r9d, 4A3h; unsigned int
0x180004345  mov     dword ptr [rsp+98h+var_68], eax
0x180004349  mov     edx, 5; unsigned __int8
0x18000434e  mov     eax, [rbx+3C0C0h]
0x180004354  mov     rcx, rsi; this
0x180004357  mov     [rsp+98h+var_70], eax
0x18000435b  lea     rax, aCaacdecDecodea_36; "CAACDec::DecodeAACFrame() m_dwPrevOutSa"...
0x180004362  imul    ebp, edi
0x180004365  lea     rdi, aCaacdecDecodea_31; "CAACDec::DecodeAACFrame"
0x18000436c  mov     r8, rdi; char *
0x18000436f  mov     [rsp+98h+Format], rax; Format
0x180004374  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180004379  mov     eax, [rbx+74h]
0x18000437c  mov     r9d, 4A5h; unsigned int
0x180004382  mov     rcx, [rbx+3C0D0h]
0x180004389  mov     r8, rdi; char *
0x18000438c  mov     [rsp+98h+var_60], eax
0x180004390  mov     edx, 5; unsigned __int8
0x180004395  mov     eax, [rbx+3C310h]
0x18000439b  mov     dword ptr [rsp+98h+var_68], eax
0x18000439f  mov     eax, [rcx+3Ch]
0x1800043a2  mov     rcx, rsi; this
0x1800043a5  mov     [rsp+98h+var_70], eax
0x1800043a9  lea     rax, aCaacdecDecodea_26; "CAACDec::DecodeAACFrame() channelConfig"...
0x1800043b0  mov     [rsp+98h+Format], rax; Format
0x1800043b5  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800043ba  mov     rax, [rbx+3C0D0h]
0x1800043c1  mov     r9d, 4A7h; unsigned int
0x1800043c7  mov     r8, rdi; char *
0x1800043ca  mov     edx, 5; unsigned __int8
0x1800043cf  mov     ecx, [rax+0Ch]
0x1800043d2  lea     rax, aCaacdecDecodea_10; "CAACDec::DecodeAACFrame() nPCMSamplesDe"...
0x1800043d9  mov     dword ptr [rsp+98h+var_68], ecx
0x1800043dd  mov     rcx, rsi; this
0x1800043e0  mov     [rsp+98h+var_70], ebp
0x1800043e4  mov     [rsp+98h+Format], rax; Format
0x1800043e9  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800043ee  mov     rax, [rbx]
0x1800043f1  mov     rcx, rbx
  ... truncated ...
```
