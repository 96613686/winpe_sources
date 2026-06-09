# CEndpointCharacteristics::ForEachCandidateFormatForMode__lambda_5789e60fd85b99cd3c89d9f341e01d71___

- ea: `0x18003aa50`
- end: `0x18003b12f`
- name: `CEndpointCharacteristics::ForEachCandidateFormatForMode__lambda_5789e60fd85b99cd3c89d9f341e01d71___`
- size: `1759`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18008966c`

## callees

- `0x180020238`
- `0x18002318c`
- `0x180039ae4`
- `0x18003aa50`
- `0x18003b140`
- `0x18003c628`
- `0x1800aeee8`
- `0x1800cd8d0`
- `0x1800cdd70`
- `0x1800cddac`
- `0x1800ce75c`
- `0x1800ce774`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003ad1b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003adb0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003ad1b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003adb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ad24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ada5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003acc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ad24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ada5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEndpointCharacteristics::ForEachCandidateFormatForMode__lambda_5789e60fd85b99cd3c89d9f341e01d71___(
        struct IPropertyStore **a1,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a2,
        unsigned int a3,
        unsigned int *a4,
        struct _GUID *a5,
        __int128 *a6)
{
  size_t v6; // r12
  int v9; // r15d
  char *v10; // rdi
  int ProposedConnectorFormatForProcessingMode; // eax
  void *v12; // rbx
  __int128 *v13; // rsi
  unsigned __int64 v14; // r14
  int i; // ebx
  int v16; // esi
  void *v17; // rcx
  unsigned int *v19; // r13
  int v20; // eax
  unsigned int j; // esi
  char *v22; // r14
  unsigned int v23; // r9d
  signed int k; // r13d
  char *v25; // rsi
  __int64 v26; // r11
  unsigned int v27; // r9d
  unsigned int *v28; // rcx
  char v29; // r10
  unsigned int v30; // r8d
  __int64 v31; // rax
  int v32; // edx
  int v33; // ecx
  __int64 v34; // rax
  unsigned int v35; // esi
  unsigned int *v36; // rcx
  char v37; // r10
  unsigned int v38; // r8d
  unsigned int *v39; // r11
  __int64 v40; // rax
  __int64 v41; // rax
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int128 *v43; // [rsp+38h] [rbp-C8h]
  unsigned int v44; // [rsp+40h] [rbp-C0h]
  int v45; // [rsp+44h] [rbp-BCh]
  unsigned int v46; // [rsp+48h] [rbp-B8h]
  unsigned int *v47; // [rsp+50h] [rbp-B0h]
  PROPVARIANT pvar[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct tWAVEFORMATEX *v49; // [rsp+68h] [rbp-98h]
  struct _GUID v50; // [rsp+70h] [rbp-90h] BYREF
  _DWORD v51[14]; // [rsp+80h] [rbp-80h]
  char *v52; // [rsp+B8h] [rbp-48h]
  unsigned int *v53; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v54; // [rsp+C8h] [rbp-38h]
  __int64 v55; // [rsp+D0h] [rbp-30h]
  __int64 v56; // [rsp+D8h] [rbp-28h]
  _OWORD v57[2]; // [rsp+E0h] [rbp-20h]
  int v58; // [rsp+100h] [rbp+0h]
  int v59; // [rsp+104h] [rbp+4h]
  _DWORD v60[2]; // [rsp+110h] [rbp+10h]
  __int64 v61; // [rsp+118h] [rbp+18h]
  __int128 v62; // [rsp+120h] [rbp+20h]
  __int128 v63; // [rsp+130h] [rbp+30h]
  int v64; // [rsp+140h] [rbp+40h]
  __int64 v65; // [rsp+148h] [rbp+48h]
  __int128 v66; // [rsp+150h] [rbp+50h]
  int v67; // [rsp+160h] [rbp+60h]
  __int64 v68; // [rsp+168h] [rbp+68h]
  __int128 v69; // [rsp+170h] [rbp+70h]
  int v70; // [rsp+180h] [rbp+80h]
  __int64 v71; // [rsp+188h] [rbp+88h]
  __int128 v72; // [rsp+190h] [rbp+90h]
  __int128 v73; // [rsp+1A0h] [rbp+A0h] BYREF
  __m256i v74; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v75; // [rsp+1D0h] [rbp+D0h]

  v47 = a4;
  v6 = a3;
  v43 = a6;
  v55 = 0;
  v56 = 0;
  v9 = 0;
  *(_OWORD *)pvar = 0;
  v49 = 0;
  v51[0] = 8000;
  v51[1] = 11025;
  v51[2] = 16000;
  v51[3] = 22050;
  v51[4] = 24000;
  v51[5] = 32000;
  v51[6] = 44100;
  v51[7] = 48000;
  v51[8] = 88200;
  v51[9] = 96000;
  v51[10] = 176400;
  v51[11] = 192000;
  v51[12] = 352800;
  v51[13] = 384000;
  v57[0] = _mm_load_si128((const __m128i *)&_xmm);
  v57[1] = _mm_load_si128((const __m128i *)&_xmm);
  v58 = 32;
  v59 = 32;
  v60[0] = 0;
  v61 = 0;
  v62 = *(_OWORD *)byte_18016F1D0;
  v63 = *(_OWORD *)byte_18016F1F0;
  v64 = 0;
  v65 = 0;
  v66 = *(_OWORD *)byte_18016F210;
  v67 = 0;
  v68 = 0;
  v69 = *(_OWORD *)byte_18016F1E0;
  v70 = 0;
  v71 = 0;
  v72 = *(_OWORD *)byte_18016F200;
  v10 = 0;
  v52 = 0;
  CEndpointCharacteristics::HasHardwareAudioEngine((CEndpointCharacteristics *)a1);
  pv = 0;
  v73 = *a6;
  v74 = *(__m256i *)(a6 + 1);
  v75 = a6[3];
  CEndpointCharacteristics::GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
    (CEndpointCharacteristics *)a1,
    (__int64)&v73,
    (__int64)&pv);
  CoTaskMemFree(pv);
  pv = 0;
  v73 = *v43;
  v74 = *(__m256i *)(v43 + 1);
  v75 = v43[3];
  CEndpointCharacteristics::GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___(
    (CEndpointCharacteristics *)a1,
    (__int64)&v73,
    (__int64)&pv);
  CoTaskMemFree(pv);
  pv = 0;
  v50 = *a5;
  ProposedConnectorFormatForProcessingMode = GetProposedConnectorFormatForProcessingMode(
                                               g_DeviceEnumerator,
                                               a1[9],
                                               a2,
                                               &v50,
                                               (struct tWAVEFORMATEX **)&pv);
  v12 = pv;
  if ( ProposedConnectorFormatForProcessingMode >= 0
    && *((_WORD *)pv + 7)
    && *((_DWORD *)pv + 2)
    && *((_WORD *)pv + 6)
    && *((_WORD *)pv + 1) )
  {
    v13 = v43;
    if ( *((_DWORD *)pv + 1) )
    {
      v9 = lambda_5789e60fd85b99cd3c89d9f341e01d71_::operator()(v43, pv, 0);
      if ( v9 < 0 )
      {
        v17 = v12;
        goto LABEL_15;
      }
    }
  }
  else
  {
    v13 = v43;
  }
  CoTaskMemFree(v12);
  *(_QWORD *)&v50.Data1 = 0;
  if ( ((int (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))a1[9]->lpVtbl->GetValue)(
         a1[9],
         &PKEY_AudioEngine_DeviceFormat,
         pvar) >= 0
    && LODWORD(pvar[1]) >= 0x12
    && LOWORD(pvar[0]) == 65
    && LODWORD(pvar[1]) == v49->cbSize + 18LL )
  {
    v9 = ValidateWaveFormatEx(v49);
    if ( v9 >= 0 )
    {
      v9 = lambda_5789e60fd85b99cd3c89d9f341e01d71_::operator()(v13, v49, 0);
      if ( v9 < 0 )
      {
        v17 = 0;
LABEL_15:
        CoTaskMemFree(v17);
        goto LABEL_16;
      }
    }
  }
  PropVariantClear(pvar);
  CoTaskMemFree(0);
  v14 = (unsigned int)(3 * v6);
  *(_QWORD *)&v50.Data1 = v14;
  v10 = (char *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
  v52 = v10;
  if ( v10 )
  {
    for ( i = 0; (unsigned int)i < 9; ++i )
    {
      v54 = 16LL * i;
      v16 = v60[v54 / 4];
      LODWORD(pv) = v16;
      if ( v16 )
      {
        memset_0(v10, 1, v14);
        v19 = v47;
        if ( (unsigned __int8)ForEachViableDataRange__lambda_4a7d50afe418974c538bbd7e3b182920_(
                                (unsigned int)v6,
                                v47,
                                v10,
                                (unsigned int)i) )
        {
          v20 = 0;
          while ( 1 )
          {
            v45 = v20;
            if ( v20 >= v16 )
              break;
            for ( j = 0; ; j = v35 + 1 )
            {
              v44 = j;
              if ( j >= 0xE )
                break;
              v22 = &v10[v6];
              memcpy_0(&v10[v6], v10, v6);
              v23 = v51[j];
              v46 = v23;
              if ( !(_DWORD)v6 )
                goto LABEL_24;
              v36 = v19;
              v37 = 0;
              v38 = 0;
              do
              {
                v39 = (unsigned int *)((char *)v36 + *v36);
                if ( v22[v38] )
                {
                  v40 = *(_QWORD *)&GUID_73647561_0000_0010_8000_00aa00389b71.Data1 - *((_QWORD *)v36 + 2);
                  if ( *(_QWORD *)&GUID_73647561_0000_0010_8000_00aa00389b71.Data1 == *((_QWORD *)v36 + 2) )
                    v40 = *(_QWORD *)GUID_73647561_0000_0010_8000_00aa00389b71.Data4 - *((_QWORD *)v36 + 3);
                  if ( v40 )
                    goto LABEL_51;
                  v41 = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 - *((_QWORD *)v36 + 4);
                  if ( *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 == *((_QWORD *)v36 + 4) )
                    v41 = *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4 - *((_QWORD *)v36 + 5);
                  if ( v41 || v23 < v36[19] || v23 > v36[20] )
                  {
LABEL_51:
                    v22[v38] = 0;
                  }
                  else
                  {
                    v22[v38] = 1;
                    v37 = 1;
                  }
                }
                ++v38;
                v36 = v39;
              }
              while ( v38 < (unsigned int)v6 );
              v35 = v44;
              if ( v37 )
              {
LABEL_24:
                for ( k = 0; (unsigned int)k < 5; ++k )
                {
                  v25 = &v10[(unsigned int)(2 * v6)];
                  memcpy_0(v25, &v10[v6], v6);
                  v26 = k;
                  v27 = *((_DWORD *)v57 + 2 * k);
                  if ( !(_DWORD)v6 )
                    goto LABEL_74;
                  v28 = v47;
                  v29 = 0;
                  v30 = 0;
                  do
                  {
                    v53 = (unsigned int *)((char *)v28 + *v28);
                    if ( v25[v30] )
                    {
                      v31 = *(_QWORD *)&GUID_73647561_0000_0010_8000_00aa00389b71.Data1 - *((_QWORD *)v28 + 2);
                      if ( *(_QWORD *)&GUID_73647561_0000_0010_8000_00aa00389b71.Data1 == *((_QWORD *)v28 + 2) )
                        v31 = *(_QWORD *)GUID_73647561_0000_0010_8000_00aa00389b71.Data4 - *((_QWORD *)v28 + 3);
                      if ( v31 )
                        goto LABEL_32;
                      v34 = *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 - *((_QWORD *)v28 + 4);
                      if ( *(_QWORD *)&GUID_00000001_0000_0010_8000_00aa00389b71.Data1 == *((_QWORD *)v28 + 4) )
                        v34 = *(_QWORD *)GUID_00000001_0000_0010_8000_00aa00389b71.Data4 - *((_QWORD *)v28 + 5);
                      if ( v34 || v27 < v28[17] || v27 > v28[18] )
                      {
LABEL_32:
                        v25[v30] = 0;
                      }
                      else
                      {
                        v25[v30] = 1;
                        v29 = 1;
                      }
                    }
                    ++v30;
                    v28 = v53;
                  }
                  while ( v30 < (unsigned int)v6 );
                  v26 = k;
                  if ( v29 )
                  {
LABEL_74:
                    v73 = 0;
                    memset(&v74, 0, 24);
                    v32 = *(_DWORD *)(*(__int64 *)((char *)&v61 + v54) + 4LL * v45);
                    v33 = *((_DWORD *)v57 + 2 * v26 + 1);
                    if ( !v32 && i <= 2 )
                      v32 = 4 - (i != 1);
                    v74.m256i_i16[1] = v27;
                    v74.m256i_i32[1] = v32;
                    *(GUID *)&v74.m256i_u64[1] = GUID_00000001_0000_0010_8000_00aa00389b71;
                    LOWORD(v73) = -2;
                    HIWORD(v73) = v33;
                    v74.m256i_i16[0] = 22;
                    WORD1(v73) = i;
                    DWORD1(v73) = v46;
                    WORD6(v73) = i * ((unsigned __int16)v33 >> 3);
                    DWORD2(v73) = v46 * WORD6(v73);
                    v9 = lambda_5789e60fd85b99cd3c89d9f341e01d71_::operator()(v43, &v73, 0);
                    if ( v9 < 0 )
                      goto LABEL_16;
                  }
                }
                v35 = v44;
                v19 = v47;
              }
            }
            v20 = v45 + 1;
            v16 = (int)pv;
          }
          v14 = *(_QWORD *)&v50.Data1;
        }
      }
    }
  }
  else
  {
    v9 = -2147024882;
  }
LABEL_16:
  PropVariantClear(pvar);
  operator delete(v10, (const struct std::nothrow_t *)1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003aa50  push    rbp
0x18003aa52  push    rbx
0x18003aa53  push    rsi
0x18003aa54  push    rdi
0x18003aa55  push    r12
0x18003aa57  push    r13
0x18003aa59  push    r14
0x18003aa5b  push    r15
0x18003aa5d  lea     rbp, [rsp-0F8h]
0x18003aa65  sub     rsp, 1F8h
0x18003aa6c  mov     rax, cs:__security_cookie
0x18003aa73  xor     rax, rsp
0x18003aa76  mov     [rbp+130h+var_50], rax
0x18003aa7d  mov     [rsp+230h+var_1E0], r9
0x18003aa82  mov     r12d, r8d
0x18003aa85  mov     r14d, edx
0x18003aa88  mov     r13, rcx
0x18003aa8b  mov     rsi, [rbp+130h+arg_20]
0x18003aa92  mov     rax, [rbp+130h+arg_28]
0x18003aa99  mov     [rsp+230h+var_1F8], rax
0x18003aa9e  xor     ebx, ebx
0x18003aaa0  mov     [rbp+130h+var_160], rbx
0x18003aaa4  mov     [rbp+130h+var_158], rbx
0x18003aaa8  mov     r15d, ebx
0x18003aaab  xorps   xmm0, xmm0
0x18003aaae  xor     eax, eax
0x18003aab0  movups  xmmword ptr [rsp+230h+pvar], xmm0
0x18003aab5  mov     [rsp+230h+var_1C8], rax
0x18003aaba  mov     [rbp+130h+var_1B0], 1F40h
0x18003aac1  mov     [rbp+130h+var_1AC], 2B11h
0x18003aac8  mov     [rbp+130h+var_1A8], 3E80h
0x18003aacf  mov     [rbp+130h+var_1A4], 5622h
0x18003aad6  mov     [rbp+130h+var_1A0], 5DC0h
0x18003aadd  mov     [rbp+130h+var_19C], 7D00h
0x18003aae4  mov     [rbp+130h+var_198], 0AC44h
0x18003aaeb  mov     [rbp+130h+var_194], 0BB80h
0x18003aaf2  mov     [rbp+130h+var_190], 15888h
0x18003aaf9  mov     [rbp+130h+var_18C], 17700h
0x18003ab00  mov     [rbp+130h+var_188], 2B110h
0x18003ab07  mov     [rbp+130h+var_184], 2EE00h
0x18003ab0e  mov     [rbp+130h+var_180], 56220h
0x18003ab15  mov     [rbp+130h+var_17C], 5DC00h
0x18003ab1c  movdqa  xmm0, cs:__xmm@00000010000000100000000800000008
0x18003ab24  movdqu  [rbp+130h+var_150], xmm0
0x18003ab29  movdqa  xmm1, cs:__xmm@00000020000000180000001800000018
0x18003ab31  movdqu  [rbp+130h+var_140], xmm1
0x18003ab36  lea     eax, [rbx+20h]
0x18003ab39  mov     [rbp+130h+var_130], eax
0x18003ab3c  mov     [rbp+130h+var_12C], eax
0x18003ab3f  mov     [rbp+130h+var_120], ebx
0x18003ab42  mov     [rbp+130h+var_118], rbx
0x18003ab46  movups  xmm0, xmmword ptr cs:byte_18016F1D0
0x18003ab4d  movdqu  [rbp+130h+var_110], xmm0
0x18003ab52  movups  xmm1, xmmword ptr cs:byte_18016F1F0
0x18003ab59  movdqu  [rbp+130h+var_100], xmm1
0x18003ab5e  mov     [rbp+130h+var_F0], ebx
0x18003ab61  mov     [rbp+130h+var_E8], rbx
0x18003ab65  movups  xmm0, xmmword ptr cs:byte_18016F210
0x18003ab6c  movdqu  [rbp+130h+var_E0], xmm0
0x18003ab71  mov     [rbp+130h+var_D0], ebx
0x18003ab74  mov     [rbp+130h+var_C8], rbx
0x18003ab78  movups  xmm0, xmmword ptr cs:byte_18016F1E0
0x18003ab7f  movdqu  [rbp+130h+var_C0], xmm0
0x18003ab84  mov     [rbp+130h+var_B0], ebx
0x18003ab8a  mov     [rbp+130h+var_A8], rbx
0x18003ab91  movups  xmm0, xmmword ptr cs:byte_18016F200
0x18003ab98  movdqu  [rbp+130h+var_A0], xmm0
0x18003aba0  mov     edi, ebx
0x18003aba2  mov     [rbp+130h+var_178], rbx
0x18003aba6  call    ?HasHardwareAudioEngine@CEndpointCharacteristics@@QEAAHXZ; CEndpointCharacteristics::HasHardwareAudioEngine(void)
0x18003abab  test    eax, eax
0x18003abad  setnz   bl
0x18003abb0  mov     [rsp+230h+pv], rdi
0x18003abb5  mov     rax, [rsp+230h+var_1F8]
0x18003abba  movaps  xmm0, xmmword ptr [rax]
0x18003abbd  movaps  [rbp+130h+var_90], xmm0
0x18003abc4  movaps  xmm1, xmmword ptr [rax+10h]
0x18003abc8  movaps  [rbp+130h+var_80], xmm1
0x18003abcf  movaps  xmm0, xmmword ptr [rax+20h]
0x18003abd3  movaps  [rbp+130h+var_70], xmm0
0x18003abda  movaps  xmm1, xmmword ptr [rax+30h]
0x18003abde  movaps  [rbp+130h+var_60], xmm1
0x18003abe5  lea     rax, [rsp+230h+pv]
0x18003abea  mov     [rsp+230h+var_208], rax
0x18003abef  lea     rax, [rbp+130h+var_90]
0x18003abf6  mov     [rsp+230h+var_210], rax
0x18003abfb  mov     r9d, r14d
0x18003abfe  mov     r8b, bl
0x18003ac01  xor     edx, edx
0x18003ac03  mov     rcx, r13
0x18003ac06  call    CEndpointCharacteristics__GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003ac0b  nop
0x18003ac0c  mov     rcx, [rsp+230h+pv]; pv
0x18003ac11  call    cs:__imp_CoTaskMemFree
0x18003ac17  mov     [rsp+230h+pv], rdi
0x18003ac1c  mov     rax, [rsp+230h+var_1F8]
0x18003ac21  movaps  xmm0, xmmword ptr [rax]
0x18003ac24  movaps  [rbp+130h+var_90], xmm0
0x18003ac2b  movaps  xmm1, xmmword ptr [rax+10h]
0x18003ac2f  movaps  [rbp+130h+var_80], xmm1
0x18003ac36  movaps  xmm0, xmmword ptr [rax+20h]
0x18003ac3a  movaps  [rbp+130h+var_70], xmm0
0x18003ac41  movaps  xmm1, xmmword ptr [rax+30h]
0x18003ac45  movaps  [rbp+130h+var_60], xmm1
0x18003ac4c  lea     rax, [rsp+230h+pv]
0x18003ac51  mov     [rsp+230h+var_208], rax
0x18003ac56  lea     rax, [rbp+130h+var_90]
0x18003ac5d  mov     [rsp+230h+var_210], rax
0x18003ac62  mov     r9d, r14d
0x18003ac65  mov     r8b, bl
0x18003ac68  mov     dl, 1
0x18003ac6a  mov     rcx, r13
0x18003ac6d  call    CEndpointCharacteristics__GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003ac72  nop
0x18003ac73  mov     rcx, [rsp+230h+pv]; pv
0x18003ac78  call    cs:__imp_CoTaskMemFree
0x18003ac7e  mov     [rsp+230h+pv], rdi
0x18003ac83  movaps  xmm0, xmmword ptr [rsi]
0x18003ac86  movdqa  xmmword ptr [rsp+230h+var_1C0.Data1], xmm0
0x18003ac8c  lea     rax, [rsp+230h+pv]
0x18003ac91  mov     [rsp+230h+var_210], rax; struct tWAVEFORMATEX **
0x18003ac96  lea     r9, [rsp+230h+var_1C0]; struct _GUID *
0x18003ac9b  mov     r8d, r14d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003ac9e  mov     rdx, [r13+48h]; struct IPropertyStore *
0x18003aca2  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; struct IMMDeviceEnumerator *
0x18003aca9  call    ?GetProposedConnectorFormatForProcessingMode@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; GetProposedConnectorFormatForProcessingMode(IMMDeviceEnumerator *,IPropertyStore *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18003acae  mov     rbx, [rsp+230h+pv]
0x18003acb3  xor     r14d, r14d
0x18003acb6  test    eax, eax
0x18003acb8  jns     loc_18003B0A2
0x18003acbe  mov     rsi, [rsp+230h+var_1F8]
0x18003acc3  mov     rcx, rbx; pv
0x18003acc6  call    cs:__imp_CoTaskMemFree
0x18003accc  mov     qword ptr [rsp+230h+var_1C0.Data1], r14
0x18003acd1  mov     rcx, [r13+48h]
0x18003acd5  mov     rax, [rcx]
0x18003acd8  lea     r8, [rsp+230h+pvar]
0x18003acdd  lea     rdx, PKEY_AudioEngine_DeviceFormat
0x18003ace4  mov     rax, [rax+28h]
0x18003ace8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aced  test    eax, eax
0x18003acef  js      short loc_18003AD16
0x18003acf1  cmp     dword ptr [rsp+230h+pvar+8], 12h
0x18003acf6  jb      short loc_18003AD16
0x18003acf8  cmp     word ptr [rsp+230h+pvar], 41h ; 'A'
0x18003acfe  jnz     short loc_18003AD16
0x18003ad00  mov     rcx, [rsp+230h+var_1C8]; struct tWAVEFORMATEX *
0x18003ad05  movzx   edx, word ptr [rcx+10h]
0x18003ad09  add     rdx, 12h
0x18003ad0d  mov     eax, dword ptr [rsp+230h+pvar+8]
0x18003ad11  cmp     rax, rdx
0x18003ad14  jz      short loc_18003AD7C
0x18003ad16  lea     rcx, [rsp+230h+pvar]; pvar
0x18003ad1b  call    cs:__imp_PropVariantClear
0x18003ad21  nop
0x18003ad22  xor     ecx, ecx; pv
0x18003ad24  call    cs:__imp_CoTaskMemFree
0x18003ad2a  lea     eax, [r12+r12*2]
0x18003ad2e  mov     r14d, eax
0x18003ad31  mov     qword ptr [rsp+230h+var_1C0.Data1], r14
0x18003ad36  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003ad3d  mov     ecx, eax; unsigned __int64
0x18003ad3f  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003ad44  mov     rdi, rax
0x18003ad47  mov     [rbp+130h+var_178], rax
0x18003ad4b  xor     edx, edx
0x18003ad4d  test    rax, rax
0x18003ad50  jz      loc_18003ADEB
0x18003ad56  mov     ebx, edx
0x18003ad58  movsxd  rax, ebx
0x18003ad5b  shl     rax, 4
0x18003ad5f  mov     [rbp+130h+var_168], rax
0x18003ad63  mov     esi, [rbp+rax+130h+var_120]
0x18003ad67  mov     dword ptr [rsp+230h+pv], esi
0x18003ad6b  test    esi, esi
0x18003ad6d  jnz     loc_18003ADF3
0x18003ad73  inc     ebx
0x18003ad75  cmp     ebx, 9
0x18003ad78  jb      short loc_18003AD58
0x18003ad7a  jmp     short loc_18003ADAB
0x18003ad7c  call    ?ValidateWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateWaveFormatEx(tWAVEFORMATEX const *)
0x18003ad81  mov     r15d, eax
0x18003ad84  test    eax, eax
0x18003ad86  js      short loc_18003AD16
0x18003ad88  xor     r8d, r8d
0x18003ad8b  mov     rdx, [rsp+230h+var_1C8]
0x18003ad90  mov     rcx, rsi
0x18003ad93  call    _lambda_5789e60fd85b99cd3c89d9f341e01d71___operator__
0x18003ad98  mov     r15d, eax
0x18003ad9b  test    eax, eax
0x18003ad9d  jns     loc_18003AD16
0x18003ada3  xor     ecx, ecx; pv
0x18003ada5  call    cs:__imp_CoTaskMemFree
0x18003adab  lea     rcx, [rsp+230h+pvar]; pvar
0x18003adb0  call    cs:__imp_PropVariantClear
0x18003adb6  nop
0x18003adb7  mov     edx, 1; struct std::nothrow_t *
0x18003adbc  mov     rcx, rdi; void *
0x18003adbf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003adc4  nop
0x18003adc5  mov     eax, r15d
0x18003adc8  mov     rcx, [rbp+130h+var_50]
0x18003adcf  xor     rcx, rsp; StackCookie
0x18003add2  call    __security_check_cookie
0x18003add7  add     rsp, 1F8h
0x18003adde  pop     r15
0x18003ade0  pop     r14
0x18003ade2  pop     r13
0x18003ade4  pop     r12
0x18003ade6  pop     rdi
0x18003ade7  pop     rsi
0x18003ade8  pop     rbx
0x18003ade9  pop     rbp
0x18003adea  retn
0x18003adeb  mov     r15d, 8007000Eh
0x18003adf1  jmp     short loc_18003ADAB
0x18003adf3  mov     r8, r14; Size
0x18003adf6  mov     edx, 1; Val
0x18003adfb  mov     rcx, rdi; void *
0x18003adfe  call    memset_0
0x18003ae03  mov     r9d, ebx
0x18003ae06  mov     r8, rdi
0x18003ae09  mov     r13, [rsp+230h+var_1E0]
0x18003ae0e  mov     rdx, r13
0x18003ae11  mov     ecx, r12d
0x18003ae14  call    ForEachViableDataRange__lambda_4a7d50afe418974c538bbd7e3b182920___; ForEachViableDataRange__lambda_4a7d50afe418974c538bbd7e3b182920_
0x18003ae19  xor     edx, edx
0x18003ae1b  test    al, al
0x18003ae1d  jz      loc_18003AD73
0x18003ae23  mov     eax, edx
0x18003ae25  mov     [rsp+230h+var_1EC], eax
0x18003ae29  cmp     eax, esi
0x18003ae2b  jge     loc_18003B124
0x18003ae31  mov     esi, edx
0x18003ae33  mov     [rsp+230h+var_1F0], esi
0x18003ae37  cmp     esi, 0Eh
0x18003ae3a  jnb     loc_18003B115
0x18003ae40  lea     r14, [rdi+r12]
0x18003ae44  mov     r8, r12; Size
0x18003ae47  mov     rdx, rdi; Src
0x18003ae4a  mov     rcx, r14; void *
0x18003ae4d  call    memcpy_0
0x18003ae52  movsxd  rax, esi
0x18003ae55  mov     r9d, [rbp+rax*4+130h+var_1B0]
0x18003ae5a  mov     [rsp+230h+var_1E8], r9d
0x18003ae5f  xor     edx, edx
0x18003ae61  test    r12d, r12d
0x18003ae64  jnz     loc_18003B019
0x18003ae6a  mov     r13d, edx
0x18003ae6d  cmp     r13d, 5
0x18003ae71  jnb     loc_18003B009
0x18003ae77  lea     esi, [r12+r12]
0x18003ae7b  add     rsi, rdi
0x18003ae7e  mov     r8, r12; Size
0x18003ae81  mov     rdx, r14; Src
0x18003ae84  mov     rcx, rsi; void *
0x18003ae87  call    memcpy_0
0x18003ae8c  movsxd  r11, r13d
0x18003ae8f  mov     r9d, dword ptr [rbp+r11*8+130h+var_150]
0x18003ae94  xor     edx, edx
0x18003ae96  test    r12d, r12d
0x18003ae99  jz      short loc_18003AEFA
0x18003ae9b  mov     rcx, [rsp+230h+var_1E0]
0x18003aea0  mov     r10b, dl
0x18003aea3  mov     r8d, edx
0x18003aea6  xor     r11d, r11d
0x18003aea9  mov     edx, [rcx]
0x18003aeab  add     rdx, rcx
0x18003aeae  mov     [rbp+130h+var_170], rdx
0x18003aeb2  mov     edx, r8d
0x18003aeb5  cmp     [rdx+rsi], r11b
0x18003aeb9  jz      short loc_18003AEE0
0x18003aebb  mov     rax, qword ptr cs:_GUID_73647561_0000_0010_8000_00aa00389b71.Data1
0x18003aec2  sub     rax, [rcx+10h]
0x18003aec6  jnz     short loc_18003AED3
0x18003aec8  mov     rax, qword ptr cs:_GUID_73647561_0000_0010_8000_00aa00389b71.Data4
0x18003aecf  sub     rax, [rcx+18h]
0x18003aed3  test    rax, rax
0x18003aed6  jz      loc_18003AFC8
0x18003aedc  mov     [rdx+rsi], r11b
0x18003aee0  inc     r8d
0x18003aee3  mov     rcx, [rbp+130h+var_170]
0x18003aee7  cmp     r8d, r12d
0x18003aeea  jb      short loc_18003AEA9
0x18003aeec  movsxd  r11, r13d
0x18003aeef  xor     edx, edx
0x18003aef1  test    r10b, r10b
0x18003aef4  jz      loc_18003AFC0
0x18003aefa  xorps   xmm0, xmm0
0x18003aefd  xor     eax, eax
0x18003aeff  movups  [rbp+130h+var_90], xmm0
0x18003af06  movups  [rbp+130h+var_80], xmm0
0x18003af0d  mov     qword ptr [rbp+130h+var_70], rax
0x18003af14  movsxd  rcx, [rsp+230h+var_1EC]
0x18003af19  mov     rax, [rbp+130h+var_168]
0x18003af1d  mov     rax, [rbp+rax+130h+var_118]
0x18003af22  mov     edx, [rax+rcx*4]
0x18003af25  mov     ecx, dword ptr [rbp+r11*8+130h+var_150+4]
0x18003af2a  test    edx, edx
0x18003af2c  jz      loc_18003B0FD
  ... truncated ...
```
