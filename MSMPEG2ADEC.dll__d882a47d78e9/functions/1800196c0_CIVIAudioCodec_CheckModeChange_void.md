# CIVIAudioCodec::CheckModeChange(void)

- ea: `0x1800196c0`
- end: `0x180019d05`
- name: `?CheckModeChange@CIVIAudioCodec@@IEAAJXZ`
- size: `1605`
- prototype: `__int64 __fastcall(CIVIAudioCodec *__hidden this)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a6b0`
- `0x18001b1d0`
- `0x18001b610`
- `0x18001bb60`

## callees

- `0x180019160`
- `0x1800196c0`
- `0x18001ccb0`
- `0x180029ec8`
- `0x1800886f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019799`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019799`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019814`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019991`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019af8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019cd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019af8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019cd7`

## pseudocode

```c
__int64 __fastcall CIVIAudioCodec::CheckModeChange(CIVIAudioCodec *this)
{
  bool v2; // zf
  __int64 v3; // r12
  __int64 v4; // rbx
  int v5; // ecx
  int v6; // ecx
  ULONG cbFormat; // r13d
  BYTE *v8; // rax
  BYTE *pbFormat; // r14
  __int64 v10; // rcx
  __int64 v11; // r8
  int v12; // eax
  char *v13; // rax
  int v14; // r15d
  __int16 v15; // ax
  __int16 v16; // ax
  int v17; // eax
  BYTE *v18; // rax
  __int64 v19; // rcx
  int v20; // eax
  GUID v21; // xmm0
  unsigned int v22; // eax
  const void *v23; // rcx
  _QWORD *v24; // rbx
  __int64 v25; // rcx
  int v26; // ecx
  int v27; // eax
  __int64 v28; // rax
  int v29; // ecx
  int v30; // ecx
  int v31; // ecx
  int v32; // ecx
  GUID Buf2; // [rsp+48h] [rbp-49h] BYREF
  _AMMediaType v35; // [rsp+58h] [rbp-39h] BYREF

  if ( !*((_DWORD *)this + 2) )
    return 0;
  memset(&v35.formattype + 1, 0, 28);
  v35.lSampleSize = 1;
  v35.bFixedSizeSamples = 1;
  CIVIAudioCodec::CheckAudioMode(this);
  v2 = *((_DWORD *)this + 1480) == 32;
  v35.majortype = MEDIATYPE_Audio;
  if ( v2 )
  {
    v3 = *(_QWORD *)&MEDIASUBTYPE_IEEE_FLOAT.Data1;
    v4 = *(_QWORD *)MEDIASUBTYPE_IEEE_FLOAT.Data4;
  }
  else
  {
    v3 = *(_QWORD *)&MEDIASUBTYPE_PCM.Data1;
    v4 = *(_QWORD *)MEDIASUBTYPE_PCM.Data4;
  }
  v5 = *((_DWORD *)this + 92);
  *(_QWORD *)v35.subtype.Data4 = v4;
  *(_QWORD *)&v35.subtype.Data1 = v3;
  v35.formattype = FORMAT_WaveFormatEx;
  v35.bTemporalCompression = 0;
  v6 = v5 - 5;
  if ( !v6 )
  {
    v18 = (BYTE *)CoTaskMemAlloc(0x28u);
    pbFormat = v18;
    if ( v18 )
    {
      v19 = *((unsigned int *)this + 1480);
      cbFormat = 40;
      v35.pbFormat = v18;
      v20 = *((_DWORD *)this + 1435);
      v35.cbFormat = 40;
      if ( (_DWORD)v19 == 16 )
        v21 = MEDIASUBTYPE_PCM;
      else
        v21 = MEDIASUBTYPE_IEEE_FLOAT;
      Buf2 = v21;
      ((void (__fastcall *)(__int64, BYTE *, __int64, __int64, _WORD, _DWORD, GUID *, int))CIVIAudioCodec::PrepareWfx)(
        v19,
        pbFormat,
        65534,
        6,
        v19,
        *((_DWORD *)this + 1557),
        &Buf2,
        v20);
      v12 = 3 * *((_DWORD *)this + 1476);
LABEL_29:
      v17 = 8 * v12;
      goto LABEL_30;
    }
LABEL_77:
    pbFormat = v35.pbFormat;
    cbFormat = v35.cbFormat;
    goto LABEL_78;
  }
  if ( v6 != 1 )
  {
    cbFormat = 18;
    v8 = (BYTE *)CoTaskMemAlloc(0x12u);
    pbFormat = v8;
    if ( v8 )
    {
      v10 = *((unsigned int *)this + 1480);
      v11 = 1;
      v35.pbFormat = v8;
      if ( (_DWORD)v10 != 16 )
        v11 = 3;
      v35.cbFormat = 18;
      Buf2 = GUID_00000000_0000_0000_0000_000000000000;
      ((void (__fastcall *)(__int64, BYTE *, __int64, __int64, _WORD, _DWORD, GUID *, int))CIVIAudioCodec::PrepareWfx)(
        v10,
        v8,
        v11,
        2,
        v10,
        *((_DWORD *)this + 1557),
        &Buf2,
        2);
      v12 = *((_DWORD *)this + 1476);
      goto LABEL_29;
    }
    goto LABEL_77;
  }
  v13 = (char *)CoTaskMemAlloc(0x34u);
  pbFormat = (BYTE *)v13;
  if ( !v13 )
    goto LABEL_77;
  v2 = *((_DWORD *)this + 1555) == 6;
  v14 = *((_DWORD *)this + 1557);
  cbFormat = 52;
  v35.pbFormat = (BYTE *)v13;
  v35.cbFormat = 52;
  if ( v2 )
  {
    *(_DWORD *)v13 = 196606;
    *((_DWORD *)v13 + 1) = v14;
    *((_WORD *)v13 + 6) = 4;
    Buf2 = GUID_00000008_0000_0010_8000_00aa00389b71;
    *((_DWORD *)v13 + 2) = 4 * v14;
    *(GUID *)(v13 + 24) = GUID_00000008_0000_0010_8000_00aa00389b71;
    *(_DWORD *)(v13 + 14) = 16;
    *((_WORD *)v13 + 9) = 16;
    *((_DWORD *)v13 + 5) = 3;
    if ( !memcmp_0(&GUID_00000008_0000_0010_8000_00aa00389b71, &Buf2, 0x10u)
      || !memcmp_0(&GUID_00000092_0000_0010_8000_00aa00389b71, &Buf2, 0x10u) )
    {
      *((_DWORD *)pbFormat + 10) = v14;
      v15 = 34;
      *(_QWORD *)(pbFormat + 44) = 6;
    }
    else
    {
      v15 = 22;
    }
    *((_WORD *)pbFormat + 8) = v15;
    v3 = *(_QWORD *)&GUID_00000008_0000_0010_8000_00aa00389b71.Data1;
    v4 = *(_QWORD *)GUID_00000008_0000_0010_8000_00aa00389b71.Data4;
  }
  else
  {
    *(_DWORD *)v13 = 196606;
    *((_DWORD *)v13 + 1) = v14;
    *((_WORD *)v13 + 6) = 4;
    Buf2 = GUID_00000092_0000_0010_8000_00aa00389b71;
    *((_DWORD *)v13 + 2) = 4 * v14;
    *(GUID *)(v13 + 24) = GUID_00000092_0000_0010_8000_00aa00389b71;
    *(_DWORD *)(v13 + 14) = 16;
    *((_WORD *)v13 + 9) = 16;
    *((_DWORD *)v13 + 5) = 3;
    if ( !memcmp_0(&GUID_00000008_0000_0010_8000_00aa00389b71, &Buf2, 0x10u)
      || !memcmp_0(&GUID_00000092_0000_0010_8000_00aa00389b71, &Buf2, 0x10u) )
    {
      *((_DWORD *)pbFormat + 10) = v14;
      v16 = 34;
      *(_QWORD *)(pbFormat + 44) = 6;
    }
    else
    {
      v16 = 22;
    }
    *((_WORD *)pbFormat + 8) = v16;
    v3 = *(_QWORD *)&GUID_00000092_0000_0010_8000_00aa00389b71.Data1;
    v4 = *(_QWORD *)GUID_00000092_0000_0010_8000_00aa00389b71.Data4;
  }
  v17 = 4 * *((_DWORD *)this + 1476);
  *(_QWORD *)v35.subtype.Data4 = v4;
  *(_QWORD *)&v35.subtype.Data1 = v3;
LABEL_30:
  *((_DWORD *)this + 1475) = v17;
  if ( *((_QWORD *)this + 26) == *(_QWORD *)&MEDIATYPE_Audio.Data1
    && *((_QWORD *)this + 27) == _mm_srli_si128((__m128i)MEDIATYPE_Audio, 8).m128i_u64[0]
    && *((_QWORD *)this + 28) == v3
    && *((_QWORD *)this + 29) == v4
    && *(_QWORD *)((char *)this + 252) == *(_QWORD *)&FORMAT_WaveFormatEx.Data1
    && *(_QWORD *)((char *)this + 260) == *(_QWORD *)FORMAT_WaveFormatEx.Data4 )
  {
    v22 = *((_DWORD *)this + 70);
    if ( v22 == cbFormat
      && (!v22 || (v23 = (const void *)*((_QWORD *)this + 36)) != 0 && pbFormat && !memcmp_0(v23, pbFormat, v22)) )
    {
LABEL_55:
      if ( *((_DWORD *)this + 3786) )
        *((int *)this + 1475) /= 3;
      v27 = *((_DWORD *)this + 1555);
      if ( v27 == 6 )
      {
        v2 = *((_DWORD *)this + 92) == 6;
        *((_DWORD *)this + 1533) = 2;
        *((_DWORD *)this + 1530) = 0;
        *((_DWORD *)this + 1532) = 1;
        *((_DWORD *)this + 1534) = 3;
        *((_DWORD *)this + 1531) = 4;
        *((_DWORD *)this + 1535) = 5;
        if ( !v2 )
        {
          *((_DWORD *)this + 1528) = 2;
          *((_DWORD *)this + 1536) = *((_DWORD *)this + 1425) != 0 ? 2 : 0;
        }
        *((_DWORD *)this + 1537) = 1;
        *((_DWORD *)this + 2) = 0;
        goto LABEL_78;
      }
      if ( v27 != 4 )
        goto LABEL_76;
      v28 = *((_QWORD *)this + 780);
      if ( !v28 )
        goto LABEL_76;
      *(_DWORD *)(v28 + 135628) = 2;
      v29 = *((_DWORD *)this + 1474);
      if ( v29 )
      {
        *(_DWORD *)(*((_QWORD *)this + 780) + 135616LL) = v29;
        goto LABEL_74;
      }
      if ( *((_DWORD *)this + 1431) == 2 )
      {
        v30 = *((_DWORD *)this + 1569);
        if ( v30 )
        {
          v31 = v30 - 1;
          if ( !v31 )
          {
            *(_DWORD *)(*((_QWORD *)this + 780) + 135616LL) = 6;
            goto LABEL_74;
          }
          v32 = v31 - 1;
          if ( !v32 )
          {
            *(_DWORD *)(*((_QWORD *)this + 780) + 135616LL) = 7;
            goto LABEL_74;
          }
          if ( v32 == 1 )
          {
            *(_DWORD *)(*((_QWORD *)this + 780) + 135616LL) = 5;
            goto LABEL_74;
          }
        }
      }
      *(_DWORD *)(*((_QWORD *)this + 780) + 135616LL) = 3;
LABEL_74:
      if ( *((_DWORD *)this + 1571) )
        *(_DWORD *)(*((_QWORD *)this + 780) + 135336LL) = 1;
LABEL_76:
      *((_DWORD *)this + 2) = 0;
      goto LABEL_78;
    }
  }
  if ( *(_QWORD *)((char *)this + 252) != *(_QWORD *)&FORMAT_WaveFormatEx.Data1
    || *(_QWORD *)((char *)this + 260) != *(_QWORD *)FORMAT_WaveFormatEx.Data4 )
  {
    v24 = (_QWORD *)((char *)this + 288);
LABEL_47:
    v26 = 48000;
    goto LABEL_48;
  }
  v24 = (_QWORD *)((char *)this + 288);
  v25 = *((_QWORD *)this + 36);
  if ( !v25 )
    goto LABEL_47;
  v26 = *(_DWORD *)(v25 + 4);
  if ( !v26 )
    goto LABEL_47;
LABEL_48:
  *((_DWORD *)this + 1436) = v26 != *((_DWORD *)this + 1557);
  if ( &v35 != (_AMMediaType *)((char *)this + 208) )
  {
    if ( *((_DWORD *)this + 70) )
    {
      CoTaskMemFree(*((LPVOID *)this + 36));
      *((_DWORD *)this + 70) = 0;
      *((_QWORD *)this + 36) = 0;
    }
    *((_QWORD *)this + 34) = 0;
    CopyMediaType((struct _AMMediaType *)((char *)this + 208), &v35);
  }
  if ( *v24 )
  {
    *((_DWORD *)this + 3) = 1;
    goto LABEL_55;
  }
  *((_DWORD *)this + 1436) = 0;
LABEL_78:
  if ( cbFormat )
    CoTaskMemFree(pbFormat);
  return 0;
}

```

## disassembly

```asm
0x1800196c0  mov     rax, rsp
0x1800196c3  push    rbp
0x1800196c4  push    rsi
0x1800196c5  lea     rbp, [rax-5Fh]
0x1800196c9  sub     rsp, 0D8h
0x1800196d0  cmp     dword ptr [rcx+8], 0
0x1800196d4  mov     rsi, rcx
0x1800196d7  jz      loc_180019CF8
0x1800196dd  mov     [rax+18h], rdi
0x1800196e1  xorps   xmm0, xmm0
0x1800196e4  mov     [rax-18h], r13
0x1800196e8  mov     [rax-28h], r15
0x1800196ec  movaps  xmmword ptr [rax-38h], xmm6
0x1800196f0  mov     [rax+10h], rbx
0x1800196f4  movups  xmmword ptr [rbp+57h+var_90+3Ch], xmm0
0x1800196f8  mov     [rax+20h], r12
0x1800196fc  movups  xmmword ptr [rbp+57h+var_90.cbFormat], xmm0
0x180019700  mov     [rbp+57h+var_90.lSampleSize], 1
0x180019707  mov     [rbp+57h+var_90.bFixedSizeSamples], 1
0x18001970e  call    ?CheckAudioMode@CIVIAudioCodec@@AEAAXXZ; CIVIAudioCodec::CheckAudioMode(void)
0x180019713  cmp     dword ptr [rsi+1720h], 20h ; ' '
0x18001971a  movups  xmm6, xmmword ptr cs:MEDIATYPE_Audio.Data1
0x180019721  movaps  xmmword ptr [rbp+57h+var_90.majortype.Data1], xmm6
0x180019725  jnz     short loc_180019737
0x180019727  mov     r12, qword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data1
0x18001972e  mov     rbx, qword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data4
0x180019735  jmp     short loc_180019745
0x180019737  mov     r12, qword ptr cs:MEDIASUBTYPE_PCM.Data1
0x18001973e  mov     rbx, qword ptr cs:MEDIASUBTYPE_PCM.Data4
0x180019745  mov     rax, qword ptr cs:FORMAT_WaveFormatEx.Data1
0x18001974c  mov     r15d, 2
0x180019752  mov     ecx, [rsi+170h]
0x180019758  mov     rdi, qword ptr cs:FORMAT_WaveFormatEx.Data4
0x18001975f  mov     qword ptr [rbp+57h+var_90.subtype.Data4], rbx
0x180019763  mov     qword ptr [rbp+57h+var_90.subtype.Data1], r12
0x180019767  mov     [rsp+0E0h+var_18], r14
0x18001976f  mov     [rbp+57h+arg_0], rax
0x180019773  mov     qword ptr [rbp+57h+var_90.formattype.Data1], rax
0x180019777  mov     qword ptr [rbp+57h+var_90.formattype.Data4], rdi
0x18001977b  mov     [rbp+57h+var_90.bTemporalCompression], 0
0x180019782  sub     ecx, 5
0x180019785  jz      loc_18001998C
0x18001978b  cmp     ecx, 1
0x18001978e  jz      short loc_18001980F
0x180019790  mov     r13d, 12h
0x180019796  mov     ecx, r13d; cb
0x180019799  call    cs:__imp_CoTaskMemAlloc
0x1800197a0  nop     dword ptr [rax+rax+00h]
0x1800197a5  mov     r14, rax
0x1800197a8  test    rax, rax
0x1800197ab  jz      loc_180019C97
0x1800197b1  mov     ecx, [rsi+1720h]
0x1800197b7  mov     r8d, 1
0x1800197bd  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800197c4  mov     [rbp+57h+var_90.pbFormat], rax
0x1800197c8  cmp     ecx, 10h
0x1800197cb  mov     [rsp+38h], r15d
0x1800197d0  mov     eax, 3
0x1800197d5  cmovnz  r8d, eax
0x1800197d9  mov     [rbp+57h+var_90.cbFormat], r13d
0x1800197dd  lea     rax, [rbp+57h+Buf2]
0x1800197e1  movaps  [rbp+57h+Buf2], xmm0
0x1800197e5  mov     qword ptr [rsp+0E0h+var_B0], rax
0x1800197ea  mov     r9d, r15d
0x1800197ed  mov     eax, [rsi+1854h]
0x1800197f3  mov     rdx, r14
0x1800197f6  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1800197fa  mov     word ptr [rsp+0E0h+var_C0], cx
0x1800197ff  call    ?PrepareWfx@CIVIAudioCodec@@IEAAXPEAUtWAVEFORMATEX@@IGGJU_GUID@@W4ChMaskType@@@Z; CIVIAudioCodec::PrepareWfx(tWAVEFORMATEX *,uint,ushort,ushort,long,_GUID,ChMaskType)
0x180019804  mov     eax, [rsi+1710h]
0x18001980a  jmp     loc_180019A16
0x18001980f  mov     ecx, 34h ; '4'; cb
0x180019814  call    cs:__imp_CoTaskMemAlloc
0x18001981b  nop     dword ptr [rax+rax+00h]
0x180019820  mov     r14, rax
0x180019823  test    rax, rax
0x180019826  jz      loc_180019C97
0x18001982c  cmp     dword ptr [rsi+184Ch], 6
0x180019833  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180019837  mov     r15d, [rsi+1854h]
0x18001983e  lea     rcx, _GUID_00000008_0000_0010_8000_00aa00389b71; Buf1
0x180019845  mov     r13d, 34h ; '4'
0x18001984b  mov     [rbp+57h+var_90.pbFormat], rax
0x18001984f  mov     ebx, 10h
0x180019854  mov     [rbp+57h+var_90.cbFormat], r13d
0x180019858  mov     r8d, ebx; Size
0x18001985b  jnz     loc_1800198EE
0x180019861  movups  xmm0, xmmword ptr cs:_GUID_00000008_0000_0010_8000_00aa00389b71.Data1
0x180019868  mov     dword ptr [rax], 2FFFEh
0x18001986e  mov     [rax+4], r15d
0x180019872  mov     word ptr [rax+0Ch], 4
0x180019878  lea     eax, ds:0[r15*4]
0x180019880  movaps  [rbp+57h+Buf2], xmm0
0x180019884  mov     [r14+8], eax
0x180019888  movups  xmmword ptr [r14+18h], xmm0
0x18001988d  mov     [r14+0Eh], ebx
0x180019891  mov     [r14+12h], bx
0x180019896  mov     dword ptr [r14+14h], 3
0x18001989e  call    memcmp_0
0x1800198a3  test    eax, eax
0x1800198a5  jz      short loc_1800198C5
0x1800198a7  mov     r8d, ebx; Size
0x1800198aa  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1800198ae  lea     rcx, _GUID_00000092_0000_0010_8000_00aa00389b71; Buf1
0x1800198b5  call    memcmp_0
0x1800198ba  test    eax, eax
0x1800198bc  jz      short loc_1800198C5
0x1800198be  mov     eax, 16h
0x1800198c3  jmp     short loc_1800198D6
0x1800198c5  mov     [r14+28h], r15d
0x1800198c9  mov     eax, 22h ; '"'
0x1800198ce  mov     qword ptr [r14+2Ch], 6
0x1800198d6  mov     [r14+10h], ax
0x1800198db  mov     r12, qword ptr cs:_GUID_00000008_0000_0010_8000_00aa00389b71.Data1
0x1800198e2  mov     rbx, qword ptr cs:_GUID_00000008_0000_0010_8000_00aa00389b71.Data4
0x1800198e9  jmp     loc_180019976
0x1800198ee  movups  xmm0, xmmword ptr cs:_GUID_00000092_0000_0010_8000_00aa00389b71.Data1
0x1800198f5  mov     dword ptr [rax], 2FFFEh
0x1800198fb  mov     [rax+4], r15d
0x1800198ff  mov     word ptr [rax+0Ch], 4
0x180019905  lea     eax, ds:0[r15*4]
0x18001990d  movaps  [rbp+57h+Buf2], xmm0
0x180019911  mov     [r14+8], eax
0x180019915  movups  xmmword ptr [r14+18h], xmm0
0x18001991a  mov     [r14+0Eh], ebx
0x18001991e  mov     [r14+12h], bx
0x180019923  mov     dword ptr [r14+14h], 3
0x18001992b  call    memcmp_0
0x180019930  test    eax, eax
0x180019932  jz      short loc_180019952
0x180019934  mov     r8, rbx; Size
0x180019937  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18001993b  lea     rcx, _GUID_00000092_0000_0010_8000_00aa00389b71; Buf1
0x180019942  call    memcmp_0
0x180019947  test    eax, eax
0x180019949  jz      short loc_180019952
0x18001994b  mov     eax, 16h
0x180019950  jmp     short loc_180019963
0x180019952  mov     [r14+28h], r15d
0x180019956  mov     eax, 22h ; '"'
0x18001995b  mov     qword ptr [r14+2Ch], 6
0x180019963  mov     [r14+10h], ax
0x180019968  mov     r12, qword ptr cs:_GUID_00000092_0000_0010_8000_00aa00389b71.Data1
0x18001996f  mov     rbx, qword ptr cs:_GUID_00000092_0000_0010_8000_00aa00389b71.Data4
0x180019976  mov     eax, [rsi+1710h]
0x18001997c  shl     eax, 2
0x18001997f  mov     qword ptr [rbp+57h+var_90.subtype.Data4], rbx
0x180019983  mov     qword ptr [rbp+57h+var_90.subtype.Data1], r12
0x180019987  jmp     loc_180019A19
0x18001998c  mov     ecx, 28h ; '('; cb
0x180019991  call    cs:__imp_CoTaskMemAlloc
0x180019998  nop     dword ptr [rax+rax+00h]
0x18001999d  mov     r14, rax
0x1800199a0  test    rax, rax
0x1800199a3  jz      loc_180019C97
0x1800199a9  mov     ecx, [rsi+1720h]
0x1800199af  mov     r13d, 28h ; '('
0x1800199b5  mov     [rbp+57h+var_90.pbFormat], rax
0x1800199b9  mov     eax, [rsi+166Ch]
0x1800199bf  mov     [rbp+57h+var_90.cbFormat], r13d
0x1800199c3  cmp     ecx, 10h
0x1800199c6  jnz     short loc_1800199D1
0x1800199c8  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_PCM.Data1
0x1800199cf  jmp     short loc_1800199D8
0x1800199d1  movups  xmm0, xmmword ptr cs:MEDIASUBTYPE_IEEE_FLOAT.Data1
0x1800199d8  mov     [rsp+38h], eax
0x1800199dc  mov     r9d, 6
0x1800199e2  lea     rax, [rbp+57h+Buf2]
0x1800199e6  movdqa  [rbp+57h+Buf2], xmm0
0x1800199eb  mov     qword ptr [rsp+0E0h+var_B0], rax
0x1800199f0  mov     r8d, 0FFFEh
0x1800199f6  mov     eax, [rsi+1854h]
0x1800199fc  mov     rdx, r14
0x1800199ff  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180019a03  mov     word ptr [rsp+0E0h+var_C0], cx
0x180019a08  call    ?PrepareWfx@CIVIAudioCodec@@IEAAXPEAUtWAVEFORMATEX@@IGGJU_GUID@@W4ChMaskType@@@Z; CIVIAudioCodec::PrepareWfx(tWAVEFORMATEX *,uint,ushort,ushort,long,_GUID,ChMaskType)
0x180019a0d  mov     eax, [rsi+1710h]
0x180019a13  lea     eax, [rax+rax*2]
0x180019a16  shl     eax, 3
0x180019a19  mov     [rsi+170Ch], eax
0x180019a1f  lea     r15, [rsi+0D0h]
0x180019a26  movq    rax, xmm6
0x180019a2b  cmp     [r15], rax
0x180019a2e  jnz     short loc_180019A8E
0x180019a30  psrldq  xmm6, 8
0x180019a35  movq    rax, xmm6
0x180019a3a  cmp     [r15+8], rax
0x180019a3e  jnz     short loc_180019A8E
0x180019a40  cmp     [r15+10h], r12
0x180019a44  jnz     short loc_180019A8E
0x180019a46  cmp     [r15+18h], rbx
0x180019a4a  jnz     short loc_180019A8E
0x180019a4c  mov     rax, [rbp+57h+arg_0]
0x180019a50  cmp     [r15+2Ch], rax
0x180019a54  jnz     short loc_180019A8E
0x180019a56  cmp     [r15+34h], rdi
0x180019a5a  jnz     short loc_180019A8E
0x180019a5c  mov     eax, [r15+48h]
0x180019a60  cmp     eax, r13d
0x180019a63  jnz     short loc_180019A8E
0x180019a65  test    eax, eax
0x180019a67  jz      loc_180019B35
0x180019a6d  mov     rcx, [r15+50h]; Buf1
0x180019a71  test    rcx, rcx
0x180019a74  jz      short loc_180019A8E
0x180019a76  test    r14, r14
0x180019a79  jz      short loc_180019A8E
0x180019a7b  mov     r8d, eax; Size
0x180019a7e  mov     rdx, r14; Buf2
0x180019a81  call    memcmp_0
0x180019a86  test    eax, eax
0x180019a88  jz      loc_180019B35
0x180019a8e  mov     rax, [rsi+0FCh]
0x180019a95  cmp     rax, qword ptr cs:FORMAT_WaveFormatEx.Data1
0x180019a9c  jnz     short loc_180019AC6
0x180019a9e  mov     rax, [rsi+104h]
0x180019aa5  cmp     rax, qword ptr cs:FORMAT_WaveFormatEx.Data4
0x180019aac  jnz     short loc_180019AC6
0x180019aae  lea     rbx, [rsi+120h]
0x180019ab5  mov     rcx, [rbx]
0x180019ab8  test    rcx, rcx
0x180019abb  jz      short loc_180019ACD
0x180019abd  mov     ecx, [rcx+4]
0x180019ac0  test    ecx, ecx
0x180019ac2  jz      short loc_180019ACD
0x180019ac4  jmp     short loc_180019AD2
0x180019ac6  lea     rbx, [rsi+120h]
0x180019acd  mov     ecx, 0BB80h
0x180019ad2  xor     edi, edi
0x180019ad4  cmp     ecx, [rsi+1854h]
0x180019ada  mov     eax, edi
0x180019adc  setnz   al
0x180019adf  mov     [rsi+1670h], eax
0x180019ae5  lea     rax, [rbp+57h+var_90]
0x180019ae9  cmp     rax, r15
0x180019aec  jz      short loc_180019B1C
0x180019aee  cmp     [r15+48h], edi
0x180019af2  jz      short loc_180019B0C
0x180019af4  mov     rcx, [r15+50h]; pv
0x180019af8  call    cs:__imp_CoTaskMemFree
0x180019aff  nop     dword ptr [rax+rax+00h]
0x180019b04  mov     [r15+48h], edi
0x180019b08  mov     [r15+50h], rdi
0x180019b0c  lea     rdx, [rbp+57h+var_90]; struct _AMMediaType *
0x180019b10  mov     [r15+40h], rdi
0x180019b14  mov     rcx, r15; struct _AMMediaType *
0x180019b17  call    ?CopyMediaType@@YAJPEAU_AMMediaType@@PEBU1@@Z; CopyMediaType(_AMMediaType *,_AMMediaType const *)
0x180019b1c  cmp     [rbx], rdi
0x180019b1f  jnz     short loc_180019B2C
0x180019b21  mov     [rsi+1670h], edi
0x180019b27  jmp     loc_180019C9F
0x180019b2c  mov     dword ptr [rsi+0Ch], 1
0x180019b33  jmp     short loc_180019B37
0x180019b35  xor     edi, edi
0x180019b37  cmp     dword ptr [rsi+3B28h], 0
0x180019b3e  jz      short loc_180019B58
0x180019b40  mov     eax, 55555556h
0x180019b45  imul    dword ptr [rsi+170Ch]
0x180019b4b  mov     eax, edx
0x180019b4d  shr     eax, 1Fh
0x180019b50  add     edx, eax
0x180019b52  mov     [rsi+170Ch], edx
0x180019b58  mov     eax, [rsi+184Ch]
0x180019b5e  cmp     eax, 6
0x180019b61  jnz     short loc_180019BD0
0x180019b63  cmp     dword ptr [rsi+170h], 6
0x180019b6a  mov     eax, 2
0x180019b6f  mov     [rsi+17F4h], eax
0x180019b75  mov     [rsi+17E8h], edi
0x180019b7b  mov     dword ptr [rsi+17F0h], 1
0x180019b85  mov     dword ptr [rsi+17F8h], 3
0x180019b8f  mov     dword ptr [rsi+17ECh], 4
0x180019b99  mov     dword ptr [rsi+17FCh], 5
0x180019ba3  jz      short loc_180019BBE
0x180019ba5  mov     [rsi+17E0h], eax
0x180019bab  mov     eax, [rsi+1644h]
0x180019bb1  neg     eax
0x180019bb3  sbb     ecx, ecx
0x180019bb5  and     ecx, 2
0x180019bb8  mov     [rsi+1800h], ecx
0x180019bbe  mov     dword ptr [rsi+1804h], 1
0x180019bc8  mov     [rsi+8], edi
0x180019bcb  jmp     loc_180019C9F
0x180019bd0  cmp     eax, 4
0x180019bd3  jnz     loc_180019C92
0x180019bd9  mov     rax, [rsi+1860h]
0x180019be0  test    rax, rax
0x180019be3  jz      loc_180019C92
0x180019be9  mov     dword ptr [rax+211CCh], 2
0x180019bf3  mov     ecx, [rsi+1708h]
0x180019bf9  test    ecx, ecx
0x180019bfb  jz      short loc_180019C0C
0x180019bfd  mov     rax, [rsi+1860h]
0x180019c04  mov     [rax+211C0h], ecx
0x180019c0a  jmp     short loc_180019C78
0x180019c0c  cmp     dword ptr [rsi+165Ch], 2
0x180019c13  jnz     short loc_180019C67
0x180019c15  mov     ecx, [rsi+1884h]
0x180019c1b  test    ecx, ecx
0x180019c1d  jz      short loc_180019C67
  ... truncated ...
```
