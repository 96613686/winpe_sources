# CAACDecTransform::OnOutputTypeChanged(void)

- ea: `0x18003e600`
- end: `0x18003ec70`
- name: `?OnOutputTypeChanged@CAACDecTransform@@MEAAJXZ`
- size: `1648`
- prototype: `__int64 __fastcall(CAACDecTransform *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003af0`
- `0x18003e600`
- `0x18004d320`
- `0x1800558b8`
- `0x180055904`
- `0x18005593c`
- `0x180055a00`
- `0x180096060`
- `0x1800960c0`

## import_xrefs

- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18003e66e`
- `MFPlat!MFCreateWaveFormatExFromMFMediaType` at `0x18003e66e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e812`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003e812`

## pseudocode

```c
__int64 __fastcall CAACDecTransform::OnOutputTypeChanged(CAACDecTransform *this)
{
  CAACDecTransform *v1; // rdi
  unsigned int v2; // edx
  int v3; // r15d
  IMFMediaType *v4; // rcx
  HRESULT v5; // esi
  WAVEFORMATEX *v6; // rdx
  __int64 nChannels; // rbx
  int v8; // r14d
  char v9; // al
  __int16 v10; // ax
  int v11; // eax
  int v13; // r12d
  const void *v14; // r13
  signed __int64 v15; // r13
  __int64 v16; // r14
  __int64 v17; // rcx
  unsigned int v18; // r12d
  unsigned __int64 v19; // r13
  unsigned __int64 v20; // rdi
  unsigned int v21; // ebx
  bool NextReloc; // al
  unsigned int v23; // esi
  char *v24; // r12
  WarbirdRuntime::CPrivateRelocationsTable *v25; // rcx
  unsigned __int64 v26; // rax
  unsigned int v27; // r10d
  unsigned int v28; // ebx
  unsigned __int64 v29; // r14
  __int64 v30; // r8
  __int64 v31; // r8
  __int64 v32; // rcx
  unsigned int v33; // ebx
  char *v34; // rsi
  unsigned int v35; // r12d
  unsigned __int64 v36; // r14
  __int64 v37; // r8
  bool v38; // [rsp+50h] [rbp-69h]
  unsigned int v39; // [rsp+54h] [rbp-65h] BYREF
  __int64 v40; // [rsp+58h] [rbp-61h] BYREF
  void **v41; // [rsp+60h] [rbp-59h] BYREF
  int v42; // [rsp+68h] [rbp-51h]
  WAVEFORMATEX *ppWF; // [rsp+70h] [rbp-49h] BYREF
  char *v44; // [rsp+78h] [rbp-41h]
  __int64 v45; // [rsp+80h] [rbp-39h]
  CAACDecTransform *v46; // [rsp+88h] [rbp-31h]
  signed __int64 v47; // [rsp+90h] [rbp-29h]
  int v48; // [rsp+98h] [rbp-21h] BYREF
  __int64 v49; // [rsp+9Ch] [rbp-1Dh]
  int v50; // [rsp+A4h] [rbp-15h]
  _BYTE v51[16]; // [rsp+B0h] [rbp-9h] BYREF

  v1 = this;
  v46 = this;
  ppWF = 0;
  v2 = WarbirdRuntime::g_VerifiedSegmentData_2;
  v3 = 1;
  if ( (WarbirdRuntime::g_VerifiedSegmentData_2 & 2) != 0 )
  {
    v15 = WarbirdRuntime::g_VerifiedSegmentDataReadWrite_2;
    v47 = WarbirdRuntime::g_VerifiedSegmentDataReadWrite_2;
    v16 = WarbirdRuntime::g_VerifiedSegmentDataReadWrite_2 >> 63;
    v45 = WarbirdRuntime::g_VerifiedSegmentDataReadWrite_2 >> 63;
    v41 = &WarbirdCrypto::CHashFunctionSCP<1,2,3,8984696424074917559>::`vftable';
    v17 = 0;
    v40 = 0;
    v18 = 0;
    v42 = 0;
    if ( (WarbirdRuntime::g_VerifiedSegmentData_2 & 0xFFFFFFFC) != 0 )
    {
      do
      {
        v19 = ((unsigned __int64)qword_1800DC410[v18] >> 5) & 0xFFFFFFF;
        v20 = ((unsigned __int64)qword_1800DC410[v18] >> 33) & 0xFFFFFFF;
        v44 = (char *)&_ImageBase + v20;
        v49 = 0;
        v48 = 0;
        v50 = 0;
        v21 = 0;
        v39 = 0;
        NextReloc = 0;
        v38 = 0;
        if ( (_DWORD)v16 )
        {
          WarbirdRuntime::CPrivateRelocationsTable::Init((WarbirdRuntime::CPrivateRelocationsTable *)&v48, v20, v19);
          NextReloc = WarbirdRuntime::CPrivateRelocationsTable::GetNextReloc(
                        (WarbirdRuntime::CPrivateRelocationsTable *)&v48,
                        (struct WarbirdRuntime::PRIVATE_RELOCATION_ITEM *)&v39);
          v38 = NextReloc;
          v21 = v39;
          v2 = WarbirdRuntime::g_VerifiedSegmentData_2;
        }
        v23 = 0;
        if ( (_DWORD)v19 )
        {
          v24 = v44;
          do
          {
            if ( (_DWORD)v16
              && NextReloc
              && (v25 = (WarbirdRuntime::CPrivateRelocationsTable *)(v23 + (unsigned int)v20),
                  (_DWORD)v25 == (v21 & 0xFFFFFFF)) )
            {
              v26 = WarbirdRuntime::CPrivateRelocationsTable::ApplyRelocation(
                      v25,
                      &v24[v23],
                      v21 >> 28,
                      WarbirdRuntime::g_preferedImageBase - (_QWORD)&_ImageBase,
                      v51);
              v28 = v27;
              if ( v26 )
              {
                v29 = v26;
                do
                {
                  v30 = v28;
                  LOBYTE(v30) = v51[v28];
                  ((void (__fastcall *)(void ***, __int64 *, __int64))v41[1])(&v41, &v40, v30);
                  ++v28;
                }
                while ( v28 < v29 );
                LODWORD(v16) = v45;
              }
              v23 += v28;
              NextReloc = WarbirdRuntime::CPrivateRelocationsTable::GetNextReloc(
                            (WarbirdRuntime::CPrivateRelocationsTable *)&v48,
                            (struct WarbirdRuntime::PRIVATE_RELOCATION_ITEM *)&v39);
              v38 = NextReloc;
              v21 = v39;
            }
            else
            {
              v31 = v23;
              LOBYTE(v31) = v24[v23];
              ((void (__fastcall *)(void ***, __int64 *, __int64))v41[1])(&v41, &v40, v31);
              ++v23;
              NextReloc = v38;
            }
          }
          while ( v23 < (unsigned int)v19 );
          v2 = WarbirdRuntime::g_VerifiedSegmentData_2;
          v18 = v42;
        }
        v42 = ++v18;
      }
      while ( v18 < v2 >> 2 );
      v17 = v40;
      v1 = v46;
      v15 = v47;
    }
    if ( (v17 | 0x8000000000000000uLL) == (v15 | 0x8000000000000000uLL) )
    {
      if ( (_DWORD)v16 )
      {
        v32 = 0;
        v40 = 0;
        v33 = 0;
        if ( (v2 & 0xFFFFFFFC) != 0 )
        {
          do
          {
            v34 = (char *)&_ImageBase + (((unsigned __int64)qword_1800DC410[v33] >> 33) & 0xFFFFFFF);
            v35 = 0;
            v36 = ((unsigned __int64)qword_1800DC410[v33] >> 5) & 0xFFFFFFF;
            if ( (((unsigned __int64)qword_1800DC410[v33] >> 5) & 0xFFFFFFF) != 0 )
            {
              do
              {
                v37 = v35;
                LOBYTE(v37) = v34[v35];
                ((void (__fastcall *)(void ***, __int64 *, __int64))v41[1])(&v41, &v40, v37);
                ++v35;
              }
              while ( v35 < (unsigned int)v36 );
              v2 = WarbirdRuntime::g_VerifiedSegmentData_2;
            }
            ++v33;
          }
          while ( v33 < v2 >> 2 );
          v32 = v40;
        }
        v40 = v32 & 0x7FFFFFFFFFFFFFFFLL;
        _InterlockedCompareExchange64(
          (volatile signed __int64 *)&WarbirdRuntime::g_VerifiedSegmentDataReadWrite_2,
          v32 & 0x7FFFFFFFFFFFFFFFLL,
          v15);
      }
    }
    else
    {
      WarbirdRuntime::CTermination::TrashStack();
    }
  }
  v4 = (IMFMediaType *)*((_QWORD *)v1 + 10);
  if ( !v4 )
  {
    v5 = -1072861856;
    goto LABEL_20;
  }
  v5 = MFCreateWaveFormatExFromMFMediaType(v4, &ppWF, 0, 0);
  if ( v5 < 0 )
    goto LABEL_20;
  v6 = ppWF;
  nChannels = ppWF->nChannels;
  *((_WORD *)v1 + 123030) = nChannels;
  *((_DWORD *)v1 + 61525) = v6->nSamplesPerSec;
  *((_DWORD *)v1 + 61517) = 0;
  *(_QWORD *)((char *)v1 + 276) = 0;
  switch ( v6->wFormatTag )
  {
    case 1u:
      *((_BYTE *)v1 + 256192) = 0;
      *((_DWORD *)v1 + 68) = 16;
      goto LABEL_10;
    case 3u:
      *((_BYTE *)v1 + 256192) = 1;
      *((_DWORD *)v1 + 68) = 32;
LABEL_10:
      if ( (unsigned int)nChannels <= 6 )
        *((_DWORD *)v1 + 61517) = dword_1800B6000[nChannels];
      v10 = nChannels;
      goto LABEL_13;
    case 0x1610u:
      if ( v6[1].wFormatTag )
        *((_DWORD *)v1 + 69) = 1;
      else
        *((_DWORD *)v1 + 70) = 1;
      *((_BYTE *)v1 + 256192) = 0;
      *((_DWORD *)v1 + 68) = 16;
      *((_WORD *)v1 + 123030) = 2;
      *((_DWORD *)v1 + 61517) = 3;
      v10 = 2;
      goto LABEL_13;
  }
  if ( v6->wFormatTag != 65534 || v6->cbSize != 22 )
  {
    v5 = -2147467259;
    goto LABEL_10;
  }
  v13 = *(_DWORD *)&v6[1].nChannels;
  *((_DWORD *)v1 + 61517) = v13;
  v14 = (char *)&v6[1].nSamplesPerSec + 2;
  v8 = 16;
  if ( !memcmp_0((char *)&v6[1].nSamplesPerSec + 2, &GUID_00000003_0000_0010_8000_00aa00389b71, 0x10u) )
  {
    v8 = 32;
    v9 = 1;
LABEL_8:
    *((_BYTE *)v1 + 256192) = v9;
    *((_DWORD *)v1 + 68) = v8;
    goto LABEL_9;
  }
  if ( !memcmp_0(v14, &GUID_00000001_0000_0010_8000_00aa00389b71, 0x10u) )
  {
    v9 = 0;
    goto LABEL_8;
  }
  v5 = -2147467259;
LABEL_9:
  v10 = nChannels;
  if ( !v13 )
    goto LABEL_10;
LABEL_13:
  if ( *((_DWORD *)v1 + 6) <= 2u || v10 != 2 )
    v3 = 0;
  *((_DWORD *)v1 + 61519) = v3;
  v11 = *((_DWORD *)v1 + 69);
  if ( v11 || *((_DWORD *)v1 + 70) )
    *((_DWORD *)v1 + 61522) = 0;
  if ( *((_DWORD *)v1 + 61555) && *((_DWORD *)v1 + 61556) == 42 && *((_DWORD *)v1 + 61524) == 4 && v11 )
  {
    TraceLoggingHelperBase::TraceVA(
      (CAACDecTransform *)((char *)v1 + 246640),
      2u,
      "CAACDecTransform::OnOutputTypeChanged",
      0x5A9u,
      "CAACDecTransform::OnOutputTypeChanged() LOAS to ADTS conversion is not supported for AOT USAC. Reject media type");
    v5 = -1072875852;
  }
  else
  {
    *((_BYTE *)v1 + 246092) = 0;
  }
LABEL_20:
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)v1 + 246640),
    4u,
    "CAACDecTransform::OnOutputTypeChanged",
    0x5B4u,
    "CAACDecTransform::OnOutputTypeChanged() m_fUseIEEEFloatOutput=%d, m_fADTSOutput=%d, m_fAACOutput=%d, m_dwOutSamplesP"
    "erSec=%d, m_wOutputAudioChannelCount=%d",
    *((unsigned __int8 *)v1 + 256192),
    *((_DWORD *)v1 + 69),
    *((_DWORD *)v1 + 70),
    *((_DWORD *)v1 + 61525),
    *((unsigned __int16 *)v1 + 123030));
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)v1 + 246640),
    4u,
    "CAACDecTransform::OnOutputTypeChanged",
    0x5B6u,
    "CAACDecTransform::OnOutputTypeChanged() m_outputBitsPerSample=%d, m_dwOutputChannelMask=0x%X, m_fLimitOutputToStereo=%d",
    *((_DWORD *)v1 + 68),
    *((_DWORD *)v1 + 61517),
    *((_DWORD *)v1 + 61519));
  if ( v5 )
    TraceLoggingHelperBase::TraceVA(
      (CAACDecTransform *)((char *)v1 + 246640),
      2u,
      "CAACDecTransform::OnOutputTypeChanged",
      0x5B7u,
      "Error %08X returned: File: %s, Line: %d",
      v5,
      "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdectransformxheaac.cpp",
      1463);
  CoTaskMemFree(ppWF);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18003e600  push    rbp
0x18003e602  push    rbx
0x18003e603  push    rsi
0x18003e604  push    rdi
0x18003e605  push    r12
0x18003e607  push    r13
0x18003e609  push    r14
0x18003e60b  push    r15
0x18003e60d  lea     rbp, [rsp-1Fh]
0x18003e612  sub     rsp, 0D8h
0x18003e619  mov     rax, cs:__security_cookie
0x18003e620  xor     rax, rsp
0x18003e623  mov     [rbp+57h+var_50], rax
0x18003e627  mov     rdi, rcx
0x18003e62a  mov     [rbp+57h+var_88], rcx
0x18003e62e  xor     r10d, r10d
0x18003e631  mov     [rbp+57h+ppWF], r10
0x18003e635  mov     rdx, cs:?g_VerifiedSegmentData_2@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_CONST_7@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_VerifiedSegmentData_2
0x18003e63c  lea     r11, __ImageBase
0x18003e643  lea     r15d, [r10+1]
0x18003e647  lea     r12d, [r10+2]
0x18003e64b  test    r12b, dl
0x18003e64e  jnz     loc_18003E8BE
0x18003e654  mov     rcx, [rdi+50h]; pMFType
0x18003e658  xor     r13d, r13d
0x18003e65b  test    rcx, rcx
0x18003e65e  jz      loc_18003EB5D
0x18003e664  xor     r9d, r9d; Flags
0x18003e667  xor     r8d, r8d; pcbSize
0x18003e66a  lea     rdx, [rbp+57h+ppWF]; ppWF
0x18003e66e  call    cs:__imp_MFCreateWaveFormatExFromMFMediaType
0x18003e675  nop     dword ptr [rax+rax+00h]
0x18003e67a  mov     esi, eax
0x18003e67c  test    eax, eax
0x18003e67e  js      loc_18003E761
0x18003e684  mov     rdx, [rbp+57h+ppWF]
0x18003e688  movzx   ebx, word ptr [rdx+2]
0x18003e68c  mov     [rdi+3C12Ch], bx
0x18003e693  mov     ecx, [rdx+4]
0x18003e696  mov     [rdi+3C154h], ecx
0x18003e69c  mov     [rdi+3C134h], r13d
0x18003e6a3  mov     [rdi+114h], r13
0x18003e6aa  movzx   ecx, word ptr [rdx]
0x18003e6ad  sub     ecx, r15d
0x18003e6b0  jz      loc_18003EBB9
0x18003e6b6  sub     ecx, r12d
0x18003e6b9  jnz     loc_18003E842
0x18003e6bf  mov     [rdi+3E8C0h], r15b
0x18003e6c6  mov     dword ptr [rdi+110h], 20h ; ' '
0x18003e6d0  jmp     short loc_18003E6F3
0x18003e6d2  mov     r14d, 20h ; ' '
0x18003e6d8  mov     al, r15b
0x18003e6db  xor     r13d, r13d
0x18003e6de  mov     [rdi+3E8C0h], al
0x18003e6e4  mov     [rdi+110h], r14d
0x18003e6eb  movzx   eax, bx
0x18003e6ee  test    r12d, r12d
0x18003e6f1  jnz     short loc_18003E70F
0x18003e6f3  cmp     ebx, 6
0x18003e6f6  ja      short loc_18003E70C
0x18003e6f8  lea     rcx, __ImageBase
0x18003e6ff  mov     eax, ds:rva dword_1800B6000[rcx+rbx*4]
0x18003e706  mov     [rdi+3C134h], eax
0x18003e70c  movzx   eax, bx
0x18003e70f  mov     r12d, 2
0x18003e715  cmp     [rdi+18h], r12d
0x18003e719  ja      loc_18003EBCF
0x18003e71f  mov     r15d, r13d
0x18003e722  mov     [rdi+3C13Ch], r15d
0x18003e729  mov     eax, [rdi+114h]
0x18003e72f  test    eax, eax
0x18003e731  jnz     loc_18003EBDE
0x18003e737  cmp     [rdi+118h], r13d
0x18003e73e  jnz     loc_18003EBDE
0x18003e744  cmp     [rdi+3C1CCh], r13d
0x18003e74b  jz      short loc_18003E75A
0x18003e74d  cmp     dword ptr [rdi+3C1D0h], 2Ah ; '*'
0x18003e754  jz      loc_18003EBEA
0x18003e75a  mov     [rdi+3C14Ch], r13b
0x18003e761  lea     rbx, [rdi+3C370h]
0x18003e768  movzx   eax, word ptr [rdi+3C12Ch]
0x18003e76f  movzx   ecx, byte ptr [rdi+3E8C0h]
0x18003e776  mov     [rsp+110h+var_C8], eax
0x18003e77a  mov     eax, [rdi+3C154h]
0x18003e780  mov     [rsp+110h+var_D0], eax
0x18003e784  mov     eax, [rdi+118h]
0x18003e78a  mov     [rsp+110h+var_D8], eax
0x18003e78e  mov     eax, [rdi+114h]
0x18003e794  mov     dword ptr [rsp+110h+var_E0], eax
0x18003e798  mov     [rsp+110h+var_E8], ecx
0x18003e79c  lea     rax, aCaacdectransfo_20; "CAACDecTransform::OnOutputTypeChanged()"...
0x18003e7a3  mov     [rsp+110h+Format], rax; Format
0x18003e7a8  mov     r9d, 5B4h; unsigned int
0x18003e7ae  lea     r8, aCaacdectransfo_0; "CAACDecTransform::OnOutputTypeChanged"
0x18003e7b5  mov     edx, 4; unsigned __int8
0x18003e7ba  mov     rcx, rbx; this
0x18003e7bd  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003e7c2  mov     eax, [rdi+3C13Ch]
0x18003e7c8  mov     [rsp+110h+var_D8], eax
0x18003e7cc  mov     eax, [rdi+3C134h]
0x18003e7d2  mov     dword ptr [rsp+110h+var_E0], eax
0x18003e7d6  mov     eax, [rdi+110h]
0x18003e7dc  mov     [rsp+110h+var_E8], eax
0x18003e7e0  lea     rax, aCaacdectransfo_21; "CAACDecTransform::OnOutputTypeChanged()"...
0x18003e7e7  mov     [rsp+110h+Format], rax; Format
0x18003e7ec  mov     r9d, 5B6h; unsigned int
0x18003e7f2  lea     r8, aCaacdectransfo_0; "CAACDecTransform::OnOutputTypeChanged"
0x18003e7f9  mov     edx, 4; unsigned __int8
0x18003e7fe  mov     rcx, rbx; this
0x18003e801  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003e806  test    esi, esi
0x18003e808  jnz     loc_18003EC31
0x18003e80e  mov     rcx, [rbp+57h+ppWF]; pv
0x18003e812  call    cs:__imp_CoTaskMemFree
0x18003e819  nop     dword ptr [rax+rax+00h]
0x18003e81e  nop
0x18003e81f  mov     eax, esi
0x18003e821  mov     rcx, [rbp+57h+var_50]
0x18003e825  xor     rcx, rsp; StackCookie
0x18003e828  call    __security_check_cookie
0x18003e82d  add     rsp, 0D8h
0x18003e834  pop     r15
0x18003e836  pop     r14
0x18003e838  pop     r13
0x18003e83a  pop     r12
0x18003e83c  pop     rdi
0x18003e83d  pop     rsi
0x18003e83e  pop     rbx
0x18003e83f  pop     rbp
0x18003e840  retn
0x18003e842  sub     ecx, 160Dh
0x18003e848  jz      loc_18003EB77
0x18003e84e  cmp     ecx, 0E9EEh
0x18003e854  jz      loc_18003EB67
0x18003e85a  mov     esi, 80004005h
0x18003e85f  jmp     loc_18003E6F3
0x18003e864  mov     r12d, [rdx+14h]
0x18003e868  mov     [rdi+3C134h], r12d
0x18003e86f  lea     r13, [rdx+18h]
0x18003e873  mov     r14d, 10h
0x18003e879  mov     r8d, r14d; Size
0x18003e87c  lea     rdx, _GUID_00000003_0000_0010_8000_00aa00389b71; Buf2
0x18003e883  mov     rcx, r13; Buf1
0x18003e886  call    memcmp_0
0x18003e88b  test    eax, eax
0x18003e88d  jz      loc_18003E6D2
0x18003e893  mov     r8d, r14d; Size
0x18003e896  lea     rdx, _GUID_00000001_0000_0010_8000_00aa00389b71; Buf2
0x18003e89d  mov     rcx, r13; Buf1
0x18003e8a0  call    memcmp_0
0x18003e8a5  xor     r13d, r13d
0x18003e8a8  test    eax, eax
0x18003e8aa  jnz     short loc_18003E8B4
0x18003e8ac  mov     al, r13b
0x18003e8af  jmp     loc_18003E6DE
0x18003e8b4  mov     esi, 80004005h
0x18003e8b9  jmp     loc_18003E6EB
0x18003e8be  mov     r13, cs:?g_VerifiedSegmentDataReadWrite_2@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_READ_WRITE_7@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_READ_WRITE_7 WarbirdRuntime::g_VerifiedSegmentDataReadWrite_2
0x18003e8c5  mov     [rbp+57h+var_80], r13
0x18003e8c9  mov     r14, r13
0x18003e8cc  shr     r14, 3Fh
0x18003e8d0  mov     [rbp+57h+var_90], r14
0x18003e8d4  lea     rax, ??_7?$CHashFunctionSCP@$00$01$02$0HMLAANMLHDLFDGLH@@WarbirdCrypto@@6B@; const WarbirdCrypto::CHashFunctionSCP<1,2,3,8984696424074917559>::`vftable'
0x18003e8db  mov     [rbp+57h+var_B0], rax
0x18003e8df  mov     rcx, r10
0x18003e8e2  mov     [rbp+57h+var_B8], rcx
0x18003e8e6  mov     r12d, r10d
0x18003e8e9  mov     [rbp+57h+var_A8], r10d
0x18003e8ed  test    edx, 0FFFFFFFCh
0x18003e8f3  jbe     loc_18003EA88
0x18003e8f9  mov     eax, r12d
0x18003e8fc  mov     rdi, ds:rva qword_1800DC410[r11+rax*8]
0x18003e904  mov     r13, rdi
0x18003e907  shr     r13, 5
0x18003e90b  and     r13d, 0FFFFFFFh
0x18003e912  shr     rdi, 21h
0x18003e916  and     edi, 0FFFFFFFh
0x18003e91c  mov     eax, edi
0x18003e91e  add     rax, r11
0x18003e921  mov     [rbp+57h+var_98], rax
0x18003e925  mov     [rbp+57h+var_74], r10
0x18003e929  mov     [rbp+57h+var_78], r10d
0x18003e92d  mov     [rbp+57h+var_6C], r10d
0x18003e931  mov     ebx, r10d
0x18003e934  mov     [rbp+57h+var_BC], ebx
0x18003e937  mov     al, r10b
0x18003e93a  mov     [rbp+57h+var_C0], al
0x18003e93d  test    r14d, r14d
0x18003e940  jz      short loc_18003E974
0x18003e942  mov     r8d, r13d; unsigned int
0x18003e945  mov     edx, edi; unsigned int
0x18003e947  lea     rcx, [rbp+57h+var_78]; this
0x18003e94b  call    ?Init@CPrivateRelocationsTable@WarbirdRuntime@@QEAAXKK@Z; WarbirdRuntime::CPrivateRelocationsTable::Init(ulong,ulong)
0x18003e950  lea     rdx, [rbp+57h+var_BC]; struct WarbirdRuntime::PRIVATE_RELOCATION_ITEM *
0x18003e954  lea     rcx, [rbp+57h+var_78]; this
0x18003e958  call    ?GetNextReloc@CPrivateRelocationsTable@WarbirdRuntime@@QEAA_NPEAUPRIVATE_RELOCATION_ITEM@2@@Z; WarbirdRuntime::CPrivateRelocationsTable::GetNextReloc(WarbirdRuntime::PRIVATE_RELOCATION_ITEM *)
0x18003e95d  mov     [rbp+57h+var_C0], al
0x18003e960  mov     ebx, [rbp+57h+var_BC]
0x18003e963  mov     rdx, cs:?g_VerifiedSegmentData_2@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_CONST_7@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_VerifiedSegmentData_2
0x18003e96a  xor     r10d, r10d
0x18003e96d  lea     r11, __ImageBase
0x18003e974  mov     esi, r10d
0x18003e977  test    r13d, r13d
0x18003e97a  jz      loc_18003EA59
0x18003e980  mov     r12, [rbp+57h+var_98]
0x18003e984  test    r14d, r14d
0x18003e987  jz      loc_18003EA15
0x18003e98d  test    al, al
0x18003e98f  jz      loc_18003EA15
0x18003e995  lea     ecx, [rsi+rdi]; this
0x18003e998  mov     eax, ebx
0x18003e99a  and     eax, 0FFFFFFFh
0x18003e99f  cmp     ecx, eax
0x18003e9a1  jnz     short loc_18003EA15
0x18003e9a3  mov     r9, cs:?g_preferedImageBase@WarbirdRuntime@@3_KC; unsigned __int64 volatile WarbirdRuntime::g_preferedImageBase
0x18003e9aa  sub     r9, r11; unsigned __int64
0x18003e9ad  shr     ebx, 1Ch
0x18003e9b0  mov     edx, esi
0x18003e9b2  add     rdx, r12; void *
0x18003e9b5  lea     rax, [rbp+57h+var_60]
0x18003e9b9  mov     [rsp+110h+Format], rax; void *
0x18003e9be  movzx   r8d, bx; unsigned __int16
0x18003e9c2  call    ?ApplyRelocation@CPrivateRelocationsTable@WarbirdRuntime@@QEBA_KPEBXG_KPEAX@Z; WarbirdRuntime::CPrivateRelocationsTable::ApplyRelocation(void const *,ushort,unsigned __int64,void *)
0x18003e9c7  mov     ebx, r10d
0x18003e9ca  test    rax, rax
0x18003e9cd  jz      short loc_18003E9FE
0x18003e9cf  mov     r14, rax
0x18003e9d2  mov     r8d, ebx
0x18003e9d5  mov     rax, [rbp+57h+var_B0]
0x18003e9d9  mov     r8b, [rbp+r8+57h+var_60]
0x18003e9de  lea     rdx, [rbp+57h+var_B8]
0x18003e9e2  lea     rcx, [rbp+57h+var_B0]
0x18003e9e6  mov     rax, [rax+8]
0x18003e9ea  call    cs:__guard_dispatch_icall_fptr
0x18003e9f0  add     ebx, r15d
0x18003e9f3  mov     eax, ebx
0x18003e9f5  cmp     rax, r14
0x18003e9f8  jb      short loc_18003E9D2
0x18003e9fa  mov     r14, [rbp+57h+var_90]
0x18003e9fe  add     esi, ebx
0x18003ea00  lea     rdx, [rbp+57h+var_BC]; struct WarbirdRuntime::PRIVATE_RELOCATION_ITEM *
0x18003ea04  lea     rcx, [rbp+57h+var_78]; this
0x18003ea08  call    ?GetNextReloc@CPrivateRelocationsTable@WarbirdRuntime@@QEAA_NPEAUPRIVATE_RELOCATION_ITEM@2@@Z; WarbirdRuntime::CPrivateRelocationsTable::GetNextReloc(WarbirdRuntime::PRIVATE_RELOCATION_ITEM *)
0x18003ea0d  mov     [rbp+57h+var_C0], al
0x18003ea10  mov     ebx, [rbp+57h+var_BC]
0x18003ea13  jmp     short loc_18003EA38
0x18003ea15  mov     r8d, esi
0x18003ea18  mov     rax, [rbp+57h+var_B0]
0x18003ea1c  mov     r8b, [r8+r12]
0x18003ea20  lea     rdx, [rbp+57h+var_B8]
0x18003ea24  lea     rcx, [rbp+57h+var_B0]
0x18003ea28  mov     rax, [rax+8]
0x18003ea2c  call    cs:__guard_dispatch_icall_fptr
0x18003ea32  add     esi, r15d
0x18003ea35  mov     al, [rbp+57h+var_C0]
0x18003ea38  cmp     esi, r13d
0x18003ea3b  mov     r10d, 0
0x18003ea41  lea     r11, __ImageBase
0x18003ea48  jb      loc_18003E984
0x18003ea4e  mov     rdx, cs:?g_VerifiedSegmentData_2@WarbirdRuntime@@3UVERIFIED_SEGMENT_DATA_CONST_7@1@A; WarbirdRuntime::VERIFIED_SEGMENT_DATA_CONST_7 WarbirdRuntime::g_VerifiedSegmentData_2
0x18003ea55  mov     r12d, [rbp+57h+var_A8]
0x18003ea59  add     r12d, r15d
0x18003ea5c  mov     [rbp+57h+var_A8], r12d
0x18003ea60  mov     eax, edx
0x18003ea62  shr     eax, 2
0x18003ea65  cmp     r12d, eax
0x18003ea68  lea     r11, __ImageBase
0x18003ea6f  jb      loc_18003E8F9
0x18003ea75  mov     rcx, [rbp+57h+var_B8]
0x18003ea79  mov     rdi, [rbp+57h+var_88]
0x18003ea7d  mov     r13, [rbp+57h+var_80]
0x18003ea81  lea     r11, __ImageBase
0x18003ea88  mov     r8, 8000000000000000h
0x18003ea92  or      rcx, r8
0x18003ea95  mov     rax, r13
0x18003ea98  or      rax, r8
0x18003ea9b  cmp     rcx, rax
0x18003ea9e  jz      short loc_18003EAAA
0x18003eaa0  call    ?TrashStack@CTermination@WarbirdRuntime@@SAXXZ; WarbirdRuntime::CTermination::TrashStack(void)
0x18003eaa5  jmp     loc_18003EB52
0x18003eaaa  test    r14d, r14d
0x18003eaad  jz      loc_18003EB52
0x18003eab3  mov     rcx, r10
0x18003eab6  mov     [rbp+57h+var_B8], rcx
0x18003eaba  mov     ebx, r10d
0x18003eabd  test    edx, 0FFFFFFFCh
0x18003eac3  jbe     short loc_18003EB35
0x18003eac5  mov     eax, ebx
0x18003eac7  mov     rsi, ds:rva qword_1800DC410[r11+rax*8]
0x18003eacf  mov     r14, rsi
0x18003ead2  shr     r14, 5
0x18003ead6  shr     rsi, 21h
0x18003eada  and     esi, 0FFFFFFFh
0x18003eae0  add     rsi, r11
0x18003eae3  mov     r12d, r10d
0x18003eae6  and     r14d, 0FFFFFFFh
0x18003eaed  jz      short loc_18003EB25
0x18003eaef  mov     r8d, r12d
0x18003eaf2  mov     rax, [rbp+57h+var_B0]
0x18003eaf6  mov     r8b, [r8+rsi]
  ... truncated ...
```
