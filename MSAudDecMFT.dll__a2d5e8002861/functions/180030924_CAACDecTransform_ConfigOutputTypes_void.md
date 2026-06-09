# CAACDecTransform::_ConfigOutputTypes(void)

- ea: `0x180030924`
- end: `0x180030f10`
- name: `?_ConfigOutputTypes@CAACDecTransform@@AEAAJXZ`
- size: `1516`
- prototype: `__int64 __fastcall(CAACDecTransform *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800019d0`
- `0x180042270`

## callees

- `0x180003af0`
- `0x180004778`
- `0x180030924`
- `0x180030f18`
- `0x1800310a0`
- `0x180041ad8`
- `0x18004d320`
- `0x18004dd14`

## string_xrefs

- `0x18003095c`: `CAACDecTransform::_ConfigOutputTypes`
- `0x180030b07`: `CAACDecTransform::_ConfigOutputTypes`
- `0x180030b85`: `CAACDecTransform::_ConfigOutputTypes`
- `0x180030984`: `CAACDecTransform::_ConfigOutputTypes() m_wOutputAudioChannelCount=%d, m_dwOutputChannelMask=0x%X, m_dwOutSamplesPerSec=%d`
- `0x180030b78`: `CAACDecTransform::_ConfigOutputTypes() Do not offer ADTS output for LOAS input with AOT USAC.`

## pseudocode

```c
__int64 __fastcall CAACDecTransform::_ConfigOutputTypes(CAACDecTransform *this)
{
  TraceLoggingHelperBase *v2; // r13
  int v3; // r15d
  int v4; // eax
  int v5; // r14d
  BOOL v6; // esi
  int v7; // eax
  unsigned int v8; // edx
  int inited; // edi
  int v10; // eax
  WORD v11; // cx
  DWORD v12; // r8d
  struct tWAVEFORMATEX *v13; // rdx
  WORD v14; // cx
  DWORD v15; // r8d
  struct tWAVEFORMATEX *v16; // rdx
  int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // r8d
  __int16 v21; // ax
  unsigned int v22; // eax
  WORD v23; // ax
  DWORD v24; // r9d
  int v25; // ecx
  WORD v26; // ax
  __int64 v27; // rcx
  struct tWAVEFORMATEX v28; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v29; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v30; // [rsp+5Ah] [rbp-A6h]
  _BYTE v31[22]; // [rsp+6Ah] [rbp-96h] BYREF
  struct tWAVEFORMATEX v32; // [rsp+80h] [rbp-80h] BYREF
  __int16 v33; // [rsp+92h] [rbp-6Eh]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int16 v35; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+9Ah] [rbp-66h]
  _BYTE Destination[130]; // [rsp+9Eh] [rbp-62h] BYREF

  v2 = (CAACDecTransform *)((char *)this + 246664);
  TraceLoggingHelperBase::TraceVA(
    (CAACDecTransform *)((char *)this + 246664),
    5u,
    "CAACDecTransform::_ConfigOutputTypes",
    0x7D9u,
    "CAACDecTransform::_ConfigOutputTypes() m_wOutputAudioChannelCount=%d, m_dwOutputChannelMask=0x%X, m_dwOutSamplesPerSec=%d",
    *((unsigned __int16 *)this + 123042),
    *((_DWORD *)this + 61523),
    *((_DWORD *)this + 61531));
  v3 = 4;
  memset(v31, 0, sizeof(v31));
  v29 = 0;
  v4 = *((_DWORD *)this + 61530);
  memset(&v28, 0, sizeof(v28));
  v30 = 0;
  if ( v4 != 4 || *((_DWORD *)this + 64056) )
  {
    v5 = 0;
    v6 = v4 == 3;
  }
  else if ( *((_DWORD *)this + 61561) && *((_DWORD *)this + 61562) == 42 )
  {
    v5 = 0;
    TraceLoggingHelperBase::TraceVA(
      v2,
      5u,
      "CAACDecTransform::_ConfigOutputTypes",
      0x7F0u,
      "CAACDecTransform::_ConfigOutputTypes() Do not offer ADTS output for LOAS input with AOT USAC.");
    v6 = 0;
  }
  else
  {
    v5 = 1;
    v6 = 0;
  }
  v7 = *((_DWORD *)this + 64038);
  if ( v7 )
  {
    v8 = 0;
    if ( v7 == 1 )
      v8 = v6;
  }
  else
  {
    if ( *((_WORD *)this + 123042) <= 2u )
      v18 = 2;
    else
      v18 = *((_DWORD *)this + 64056) != 0 ? 2 : 4;
    v8 = v18 + 1;
    if ( !v5 )
      v8 = v18;
  }
  inited = CMFTSimpleBase::_InitAvailableOutputTypeArray((CAACDecTransform *)((char *)this + 24), v8);
  if ( inited < 0 )
    goto LABEL_15;
  v10 = *((_DWORD *)this + 64038);
  if ( v10 )
  {
    if ( v10 == 1 && v6 )
    {
      v32.wFormatTag = 0;
      memset_0(&v32.nChannels, 0, 0x9Cu);
      v22 = *((_DWORD *)this + 61664);
      if ( v22 && memcpy_s(Destination, 0x80u, (char *)this + 246528, v22) )
        goto LABEL_39;
      v23 = MFGetAttributeUINT32(*((_QWORD *)this + 8), &MF_MT_AUDIO_BITS_PER_SAMPLE, 16);
      v24 = *((_DWORD *)this + 61531);
      v32.nChannels = *((_WORD *)this + 123042);
      v32.wFormatTag = 5648;
      v32.wBitsPerSample = v23;
      v32.nSamplesPerSec = v24;
      v25 = v32.nChannels * v23 / 8;
      v32.nBlockAlign = v25;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v26 = *((_WORD *)this + 123328) + 12;
      v32.nAvgBytesPerSec = v24 * v25;
      v27 = *((_QWORD *)this + 8);
      v32.cbSize = v26;
      v33 = 0;
      v32.nAvgBytesPerSec = MFGetAttributeUINT32(v27, &MF_MT_AUDIO_AVG_BYTES_PER_SECOND, 0);
      v20 = 0;
      goto LABEL_46;
    }
    goto LABEL_15;
  }
  v11 = *((_WORD *)this + 123042);
  v12 = *((_DWORD *)this + 61531);
  if ( v11 > 2u )
  {
    WORD5(v30) = 4 * *((_WORD *)this + 123042);
    *(_DWORD *)&v31[2] = *((_DWORD *)this + 61523);
    LOWORD(v30) = v11;
    *(_WORD *)&v31[6] = 3;
    *(_DWORD *)((char *)&v30 + 6) = v12 * 4 * v11;
    v13 = (struct tWAVEFORMATEX *)&v29;
    *(_WORD *)&v31[20] = *(_WORD *)&GUID_00000003_0000_0010_8000_00aa00389b71.Data4[6];
    v29 = -2;
    *(_DWORD *)((char *)&v30 + 2) = v12;
    HIDWORD(v30) = 1441824;
    strcpy(v31, " ");
    *(_DWORD *)&v31[8] = *(unsigned int *)((char *)&GUID_00000003_0000_0010_8000_00aa00389b71.Data1 + 2);
    *(_QWORD *)&v31[12] = *(_QWORD *)&GUID_00000003_0000_0010_8000_00aa00389b71.Data3;
  }
  else
  {
    v28.nAvgBytesPerSec = v12 * 4 * *((unsigned __int16 *)this + 123042);
    v28.wFormatTag = 3;
    v13 = &v28;
    v28.nChannels = v11;
    v28.nSamplesPerSec = v12;
    v28.nBlockAlign = 4 * v11;
    *(_DWORD *)&v28.wBitsPerSample = 32;
  }
  inited = CAACDecTransform::_AddTypes(this, v13, 0, 0);
  if ( inited < 0 )
    goto LABEL_14;
  v14 = *((_WORD *)this + 123042);
  v15 = *((_DWORD *)this + 61531);
  if ( v14 > 2u )
  {
    WORD5(v30) = 2 * *((_WORD *)this + 123042);
    *(_DWORD *)&v31[2] = *((_DWORD *)this + 61523);
    v29 = -2;
    LOWORD(v30) = v14;
    *(_DWORD *)((char *)&v30 + 6) = v15 * 2 * v14;
    v16 = (struct tWAVEFORMATEX *)&v29;
    *(_WORD *)&v31[20] = *(_WORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data4[6];
    *(_DWORD *)((char *)&v30 + 2) = v15;
    HIDWORD(v30) = 1441808;
    *(_WORD *)v31 = 16;
    *(_WORD *)&v31[6] = 1;
    *(_DWORD *)&v31[8] = *(unsigned int *)((char *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 + 2);
    *(_QWORD *)&v31[12] = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data3;
  }
  else
  {
    v28.nAvgBytesPerSec = v15 * 2 * *((unsigned __int16 *)this + 123042);
    v16 = &v28;
    v28.wFormatTag = 1;
    v28.nChannels = v14;
    v28.nSamplesPerSec = v15;
    v28.nBlockAlign = 2 * v14;
    *(_DWORD *)&v28.wBitsPerSample = 16;
  }
  inited = CAACDecTransform::_AddTypes(this, v16, 1u, 0);
  if ( inited < 0 )
    goto LABEL_14;
  if ( *((_WORD *)this + 123042) <= 2u || *((_DWORD *)this + 64056) )
  {
    v3 = 2;
    goto LABEL_36;
  }
  v28.nSamplesPerSec = *((_DWORD *)this + 61531);
  v28.nAvgBytesPerSec = 8 * v28.nSamplesPerSec;
  *(_DWORD *)&v28.wFormatTag = 131075;
  v28.cbSize = 0;
  *(_DWORD *)&v28.nBlockAlign = 2097160;
  inited = CAACDecTransform::_AddTypes(this, &v28, 2u, 0);
  if ( inited < 0
    || (v28.nSamplesPerSec = *((_DWORD *)this + 61531),
        v28.nAvgBytesPerSec = 4 * v28.nSamplesPerSec,
        *(_DWORD *)&v28.wFormatTag = 131073,
        *(_DWORD *)&v28.nBlockAlign = 1048580,
        v28.cbSize = 0,
        inited = CAACDecTransform::_AddTypes(this, &v28, 3u, 0),
        inited < 0) )
  {
LABEL_15:
    if ( !inited )
      return (unsigned int)inited;
    goto LABEL_14;
  }
LABEL_36:
  if ( !v5 )
    goto LABEL_15;
  v32.wFormatTag = 0;
  memset_0(&v32.nChannels, 0, 0x9Cu);
  v19 = *((_DWORD *)this + 61664);
  if ( !v19 || !memcpy_s(Destination, 0x80u, (char *)this + 246528, v19) )
  {
    v32.nChannels = *((_WORD *)this + 123042);
    v20 = v3;
    v32.nSamplesPerSec = *((_DWORD *)this + 61531);
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v21 = *((_WORD *)this + 123328);
    v32.wFormatTag = 5648;
    v32.cbSize = v21 + 12;
    v33 = 1;
    *(_QWORD *)&v32.nAvgBytesPerSec = 0;
LABEL_46:
    inited = CAACDecTransform::_AddTypes(this, &v32, v20, 0);
    goto LABEL_15;
  }
LABEL_39:
  inited = -2147467259;
LABEL_14:
  TraceLoggingHelperBase::TraceVA(
    v2,
    2u,
    "CAACDecTransform::_ConfigOutputTypes",
    0x8C8u,
    "Error %08X returned: File: %s, Line: %d",
    inited,
    "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdectransformxheaac.cpp",
    2248);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180030924  push    rbp
0x180030926  push    rbx
0x180030927  push    rsi
0x180030928  push    rdi
0x180030929  push    r12
0x18003092b  push    r13
0x18003092d  push    r14
0x18003092f  push    r15
0x180030931  lea     rbp, [rsp-38h]
0x180030936  sub     rsp, 138h
0x18003093d  mov     rax, cs:__security_cookie
0x180030944  xor     rax, rsp
0x180030947  mov     [rbp+70h+var_50], rax
0x18003094b  mov     rbx, rcx
0x18003094e  lea     r13, [rcx+3C388h]
0x180030955  movzx   ecx, word ptr [rcx+3C144h]
0x18003095c  lea     r8, aCaacdectransfo_17; "CAACDecTransform::_ConfigOutputTypes"
0x180030963  mov     edi, 5
0x180030968  mov     r9d, 7D9h; unsigned int
0x18003096e  mov     edx, edi; unsigned __int8
0x180030970  mov     eax, [rbx+3C16Ch]
0x180030976  mov     [rsp+170h+var_138], eax
0x18003097a  mov     eax, [rbx+3C14Ch]
0x180030980  mov     dword ptr [rsp+170h+var_140], eax
0x180030984  lea     rax, aCaacdectransfo_12; "CAACDecTransform::_ConfigOutputTypes() "...
0x18003098b  mov     [rsp+170h+var_148], ecx
0x18003098f  mov     rcx, r13; this
0x180030992  mov     [rsp+170h+Format], rax; Format
0x180030997  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x18003099c  xor     eax, eax
0x18003099e  lea     r15d, [rdi-1]
0x1800309a2  xorps   xmm0, xmm0
0x1800309a5  mov     [rsp+170h+var_130.cbSize], ax
0x1800309aa  movups  [rsp+170h+var_106], xmm0
0x1800309af  mov     qword ptr [rsp+170h+var_106+0Eh], rax
0x1800309b4  lea     ecx, [rdi-4]
0x1800309b7  mov     [rsp+170h+var_118], ax
0x1800309bc  mov     eax, [rbx+3C168h]
0x1800309c2  movups  xmmword ptr [rsp+170h+var_130.wFormatTag], xmm0
0x1800309c7  movups  [rsp+170h+var_116], xmm0
0x1800309cc  cmp     eax, r15d
0x1800309cf  jz      loc_180030B59
0x1800309d5  xor     esi, esi
0x1800309d7  xor     r14d, r14d
0x1800309da  cmp     eax, 3
0x1800309dd  setz    sil
0x1800309e1  mov     eax, [rbx+3E898h]
0x1800309e7  mov     r12d, 2
0x1800309ed  test    eax, eax
0x1800309ef  jz      loc_180030BB2
0x1800309f5  xor     edx, edx; unsigned int
0x1800309f7  cmp     eax, ecx
0x1800309f9  jz      loc_180030BDF
0x1800309ff  lea     rcx, [rbx+18h]; this
0x180030a03  call    ?_InitAvailableOutputTypeArray@CMFTSimpleBase@@IEAAJK@Z; CMFTSimpleBase::_InitAvailableOutputTypeArray(ulong)
0x180030a08  mov     edi, eax
0x180030a0a  test    eax, eax
0x180030a0c  js      loc_180030B32
0x180030a12  mov     eax, [rbx+3E898h]
0x180030a18  test    eax, eax
0x180030a1a  jnz     loc_180030E0F
0x180030a20  movzx   ecx, word ptr [rbx+3C144h]
0x180030a27  mov     esi, 0FFFEh
0x180030a2c  mov     r8d, [rbx+3C16Ch]
0x180030a33  mov     eax, ecx
0x180030a35  shl     eax, 2
0x180030a38  mov     edx, eax
0x180030a3a  imul    edx, r8d
0x180030a3e  cmp     cx, r12w
0x180030a42  ja      loc_180030BE9
0x180030a48  mov     r9d, 3
0x180030a4e  mov     [rsp+170h+var_130.nAvgBytesPerSec], edx
0x180030a52  mov     [rsp+170h+var_130.wFormatTag], r9w
0x180030a58  lea     rdx, [rsp+170h+var_130]; struct tWAVEFORMATEX *
0x180030a5d  mov     [rsp+170h+var_130.nChannels], cx
0x180030a62  mov     [rsp+170h+var_130.nSamplesPerSec], r8d
0x180030a67  mov     [rsp+170h+var_130.nBlockAlign], ax
0x180030a6c  mov     dword ptr [rsp+170h+var_130.wBitsPerSample], 20h ; ' '
0x180030a74  xor     r9d, r9d; int
0x180030a77  xor     r8d, r8d; unsigned int
0x180030a7a  mov     rcx, rbx; this
0x180030a7d  call    ?_AddTypes@CAACDecTransform@@AEAAJPEAUtWAVEFORMATEX@@KH@Z; CAACDecTransform::_AddTypes(tWAVEFORMATEX *,ulong,int)
0x180030a82  mov     edi, eax
0x180030a84  test    eax, eax
0x180030a86  js      short loc_180030AF5
0x180030a88  movzx   ecx, word ptr [rbx+3C144h]
0x180030a8f  mov     r9d, 2
0x180030a95  mov     r8d, [rbx+3C16Ch]
0x180030a9c  mov     eax, ecx
0x180030a9e  add     eax, eax
0x180030aa0  mov     edx, eax
0x180030aa2  imul    edx, r8d
0x180030aa6  cmp     cx, r9w
0x180030aaa  mov     r9d, 1
0x180030ab0  ja      loc_180030C57
0x180030ab6  mov     [rsp+170h+var_130.nAvgBytesPerSec], edx
0x180030aba  lea     rdx, [rsp+170h+var_130]; struct tWAVEFORMATEX *
0x180030abf  mov     [rsp+170h+var_130.wFormatTag], r9w
0x180030ac5  mov     [rsp+170h+var_130.nChannels], cx
0x180030aca  mov     [rsp+170h+var_130.nSamplesPerSec], r8d
0x180030acf  mov     [rsp+170h+var_130.nBlockAlign], ax
0x180030ad4  mov     dword ptr [rsp+170h+var_130.wBitsPerSample], 10h
0x180030adc  xor     r9d, r9d; int
0x180030adf  mov     rcx, rbx; this
0x180030ae2  lea     r8d, [r9+1]; unsigned int
0x180030ae6  call    ?_AddTypes@CAACDecTransform@@AEAAJPEAUtWAVEFORMATEX@@KH@Z; CAACDecTransform::_AddTypes(tWAVEFORMATEX *,ulong,int)
0x180030aeb  mov     edi, eax
0x180030aed  test    eax, eax
0x180030aef  jns     loc_180030CBF
0x180030af5  mov     r9d, 8C8h; unsigned int
0x180030afb  lea     rax, aAvcoreCodecdsp_0; "avcore\\codecdsp\\audio\\aacdec\\curren"...
0x180030b02  mov     [rsp+170h+var_138], r9d
0x180030b07  lea     r8, aCaacdectransfo_17; "CAACDecTransform::_ConfigOutputTypes"
0x180030b0e  mov     [rsp+170h+var_140], rax
0x180030b13  mov     edx, 2; unsigned __int8
0x180030b18  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x180030b1f  mov     [rsp+170h+var_148], edi
0x180030b23  mov     rcx, r13; this
0x180030b26  mov     [rsp+170h+Format], rax; Format
0x180030b2b  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180030b30  jmp     short loc_180030B36
0x180030b32  test    edi, edi
0x180030b34  jnz     short loc_180030AF5
0x180030b36  mov     eax, edi
0x180030b38  mov     rcx, [rbp+70h+var_50]
0x180030b3c  xor     rcx, rsp; StackCookie
0x180030b3f  call    __security_check_cookie
0x180030b44  add     rsp, 138h
0x180030b4b  pop     r15
0x180030b4d  pop     r14
0x180030b4f  pop     r13
0x180030b51  pop     r12
0x180030b53  pop     rdi
0x180030b54  pop     rsi
0x180030b55  pop     rbx
0x180030b56  pop     rbp
0x180030b57  retn
0x180030b59  cmp     dword ptr [rbx+3E8E0h], 0
0x180030b60  jnz     loc_1800309D5
0x180030b66  cmp     dword ptr [rbx+3C1E4h], 0
0x180030b6d  jz      short loc_180030BA8
0x180030b6f  cmp     dword ptr [rbx+3C1E8h], 2Ah ; '*'
0x180030b76  jnz     short loc_180030BA8
0x180030b78  lea     rax, aCaacdectransfo_28; "CAACDecTransform::_ConfigOutputTypes() "...
0x180030b7f  mov     r9d, 7F0h; unsigned int
0x180030b85  lea     r8, aCaacdectransfo_17; "CAACDecTransform::_ConfigOutputTypes"
0x180030b8c  mov     [rsp+170h+Format], rax; Format
0x180030b91  mov     edx, edi; unsigned __int8
0x180030b93  mov     rcx, r13; this
0x180030b96  xor     r14d, r14d
0x180030b99  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180030b9e  xor     esi, esi
0x180030ba0  lea     ecx, [rsi+1]
0x180030ba3  jmp     loc_1800309E1
0x180030ba8  mov     r14d, ecx
0x180030bab  xor     esi, esi
0x180030bad  jmp     loc_1800309E1
0x180030bb2  cmp     [rbx+3C144h], r12w
0x180030bba  jbe     short loc_180030BCE
0x180030bbc  mov     eax, [rbx+3E8E0h]
0x180030bc2  neg     eax
0x180030bc4  sbb     ecx, ecx
0x180030bc6  and     ecx, 0FFFFFFFEh
0x180030bc9  add     ecx, r15d
0x180030bcc  jmp     short loc_180030BD1
0x180030bce  mov     ecx, r12d
0x180030bd1  test    r14d, r14d
0x180030bd4  lea     edx, [rcx+1]
0x180030bd7  cmovz   edx, ecx
0x180030bda  jmp     loc_1800309FF
0x180030bdf  test    esi, esi
0x180030be1  cmovnz  edx, ecx
0x180030be4  jmp     loc_1800309FF
0x180030be9  movsd   xmm0, qword ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data3
0x180030bf1  mov     r12d, 20h ; ' '
0x180030bf7  mov     word ptr [rsp+170h+var_116+0Ah], ax
0x180030bfc  mov     eax, [rbx+3C14Ch]
0x180030c02  mov     dword ptr [rsp+170h+var_106+2], eax
0x180030c06  lea     eax, [r12-1Dh]
0x180030c0b  mov     word ptr [rsp+170h+var_116], cx
0x180030c10  mov     ecx, cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data1+2
0x180030c16  mov     word ptr [rsp+170h+var_106+6], ax
0x180030c1b  movzx   eax, word ptr cs:_GUID_00000003_0000_0010_8000_00aa00389b71.Data4+6
0x180030c22  mov     dword ptr [rsp+170h+var_116+6], edx
0x180030c26  lea     rdx, [rsp+170h+var_118]
0x180030c2b  mov     [rsp+170h+var_F2], ax
0x180030c30  mov     [rsp+170h+var_118], si
0x180030c35  mov     dword ptr [rsp+170h+var_116+2], r8d
0x180030c3a  mov     dword ptr [rsp+170h+var_116+0Ch], 160020h
0x180030c42  mov     word ptr [rsp+170h+var_106], r12w
0x180030c48  mov     dword ptr [rsp+170h+var_106+8], ecx
0x180030c4c  movsd   qword ptr [rsp+170h+var_106+0Ch], xmm0
0x180030c52  jmp     loc_180030A74
0x180030c57  movsd   xmm0, qword ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data3
0x180030c5f  mov     word ptr [rsp+170h+var_116+0Ah], ax
0x180030c64  mov     eax, [rbx+3C14Ch]
0x180030c6a  mov     dword ptr [rsp+170h+var_106+2], eax
0x180030c6e  movzx   eax, word ptr cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data4+6
0x180030c75  mov     [rsp+170h+var_118], si
0x180030c7a  mov     esi, 10h
0x180030c7f  mov     word ptr [rsp+170h+var_116], cx
0x180030c84  mov     ecx, cs:_GUID_00000001_0000_0010_8000_00aa00389b71.Data1+2
0x180030c8a  mov     dword ptr [rsp+170h+var_116+6], edx
0x180030c8e  lea     rdx, [rsp+170h+var_118]
0x180030c93  mov     [rsp+170h+var_F2], ax
0x180030c98  mov     dword ptr [rsp+170h+var_116+2], r8d
0x180030c9d  mov     dword ptr [rsp+170h+var_116+0Ch], 160010h
0x180030ca5  mov     word ptr [rsp+170h+var_106], si
0x180030caa  mov     word ptr [rsp+170h+var_106+6], r9w
0x180030cb0  mov     dword ptr [rsp+170h+var_106+8], ecx
0x180030cb4  movsd   qword ptr [rsp+170h+var_106+0Ch], xmm0
0x180030cba  jmp     loc_180030ADC
0x180030cbf  mov     ecx, 2
0x180030cc4  cmp     [rbx+3C144h], cx
0x180030ccb  jbe     loc_180030D6B
0x180030cd1  cmp     dword ptr [rbx+3E8E0h], 0
0x180030cd8  jnz     loc_180030D6B
0x180030cde  mov     eax, [rbx+3C16Ch]
0x180030ce4  lea     rdx, [rsp+170h+var_130]; struct tWAVEFORMATEX *
0x180030ce9  mov     [rsp+170h+var_130.nSamplesPerSec], eax
0x180030ced  mov     r8d, ecx; unsigned int
0x180030cf0  shl     eax, 3
0x180030cf3  xor     r9d, r9d; int
0x180030cf6  mov     [rsp+170h+var_130.nAvgBytesPerSec], eax
0x180030cfa  mov     rcx, rbx; this
0x180030cfd  xor     eax, eax
0x180030cff  mov     dword ptr [rsp+170h+var_130.wFormatTag], 20003h
0x180030d07  mov     [rsp+170h+var_130.cbSize], ax
0x180030d0c  mov     dword ptr [rsp+170h+var_130.nBlockAlign], 200008h
0x180030d14  call    ?_AddTypes@CAACDecTransform@@AEAAJPEAUtWAVEFORMATEX@@KH@Z; CAACDecTransform::_AddTypes(tWAVEFORMATEX *,ulong,int)
0x180030d19  mov     edi, eax
0x180030d1b  test    eax, eax
0x180030d1d  js      loc_180030B32
0x180030d23  mov     eax, [rbx+3C16Ch]
0x180030d29  lea     rdx, [rsp+170h+var_130]; struct tWAVEFORMATEX *
0x180030d2e  mov     [rsp+170h+var_130.nSamplesPerSec], eax
0x180030d32  xor     r9d, r9d; int
0x180030d35  shl     eax, 2
0x180030d38  mov     rcx, rbx; this
0x180030d3b  mov     [rsp+170h+var_130.nAvgBytesPerSec], eax
0x180030d3f  xor     eax, eax
0x180030d41  mov     dword ptr [rsp+170h+var_130.wFormatTag], 20001h
0x180030d49  mov     dword ptr [rsp+170h+var_130.nBlockAlign], 100004h
0x180030d51  mov     [rsp+170h+var_130.cbSize], ax
0x180030d56  lea     r8d, [rax+3]; unsigned int
0x180030d5a  call    ?_AddTypes@CAACDecTransform@@AEAAJPEAUtWAVEFORMATEX@@KH@Z; CAACDecTransform::_AddTypes(tWAVEFORMATEX *,ulong,int)
0x180030d5f  mov     edi, eax
0x180030d61  test    eax, eax
0x180030d63  js      loc_180030B32
0x180030d69  jmp     short loc_180030D6E
0x180030d6b  mov     r15d, ecx
0x180030d6e  test    r14d, r14d
0x180030d71  jz      loc_180030B32
0x180030d77  xor     eax, eax
0x180030d79  lea     rcx, [rbp+70h+var_F0.nChannels]; void *
0x180030d7d  xor     edx, edx; Val
0x180030d7f  mov     [rbp+70h+var_F0.wFormatTag], ax
0x180030d83  mov     r8d, 9Ch; Size
0x180030d89  call    memset_0
0x180030d8e  mov     eax, [rbx+3C380h]
0x180030d94  test    eax, eax
0x180030d96  jz      short loc_180030DBE
0x180030d98  mov     r9d, eax; SourceSize
0x180030d9b  lea     r8, [rbx+3C300h]; Source
0x180030da2  mov     edx, 80h; DestinationSize
0x180030da7  lea     rcx, [rbp+70h+Destination]; Destination
0x180030dab  call    memcpy_s
0x180030db0  test    eax, eax
0x180030db2  jz      short loc_180030DBE
0x180030db4  mov     edi, 80004005h
0x180030db9  jmp     loc_180030AF5
0x180030dbe  movzx   eax, word ptr [rbx+3C144h]
0x180030dc5  mov     edx, 1610h
0x180030dca  mov     [rbp+70h+var_F0.nChannels], ax
0x180030dce  mov     r8d, r15d
0x180030dd1  mov     eax, [rbx+3C16Ch]
0x180030dd7  mov     [rbp+70h+var_F0.nSamplesPerSec], eax
0x180030dda  xor     eax, eax
0x180030ddc  mov     [rbp+70h+var_DC], eax
0x180030ddf  mov     [rbp+70h+var_D8], ax
0x180030de3  mov     [rbp+70h+var_D6], eax
0x180030de6  movzx   eax, word ptr [rbx+3C380h]
0x180030ded  add     ax, 0Ch
0x180030df1  mov     [rbp+70h+var_F0.wFormatTag], dx
0x180030df5  mov     [rbp+70h+var_F0.cbSize], ax
0x180030df9  mov     eax, 1
0x180030dfe  mov     [rbp+70h+var_DE], ax
0x180030e02  mov     qword ptr [rbp+70h+var_F0.nAvgBytesPerSec], 0
0x180030e0a  jmp     loc_180030EFA
0x180030e0f  mov     r9d, 1
0x180030e15  cmp     eax, r9d
0x180030e18  jnz     loc_180030B32
0x180030e1e  test    esi, esi
0x180030e20  jz      loc_180030B32
0x180030e26  xor     eax, eax
0x180030e28  lea     rcx, [rbp+70h+var_F0.nChannels]; void *
0x180030e2c  xor     edx, edx; Val
0x180030e2e  mov     [rbp+70h+var_F0.wFormatTag], ax
0x180030e32  mov     r8d, 9Ch; Size
0x180030e38  call    memset_0
  ... truncated ...
```
