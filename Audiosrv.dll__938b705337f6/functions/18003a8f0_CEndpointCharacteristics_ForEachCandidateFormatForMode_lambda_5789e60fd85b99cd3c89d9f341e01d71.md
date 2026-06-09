# CEndpointCharacteristics::ForEachCandidateFormatForMode__lambda_5789e60fd85b99cd3c89d9f341e01d71___

- ea: `0x18003a8f0`
- end: `0x18003afcf`
- name: `CEndpointCharacteristics::ForEachCandidateFormatForMode__lambda_5789e60fd85b99cd3c89d9f341e01d71___`
- size: `1759`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180089b6c`

## callees

- `0x1800200e8`
- `0x18002303c`
- `0x180039984`
- `0x18003a8f0`
- `0x18003afe0`
- `0x18003c4c8`
- `0x1800b0be8`
- `0x1800cf8c0`
- `0x1800cfd60`
- `0x1800cfd9c`
- `0x1800d074c`
- `0x1800d0764`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003abbb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003ac50`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003abbb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003ac50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003abc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab18`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ab66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003abc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ac45`

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
  v62 = unk_18016E1D0;
  v63 = unk_18016E1F0;
  v64 = 0;
  v65 = 0;
  v66 = unk_18016E210;
  v67 = 0;
  v68 = 0;
  v69 = unk_18016E1E0;
  v70 = 0;
  v71 = 0;
  v72 = unk_18016E200;
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
0x18003a8f0  push    rbp
0x18003a8f2  push    rbx
0x18003a8f3  push    rsi
0x18003a8f4  push    rdi
0x18003a8f5  push    r12
0x18003a8f7  push    r13
0x18003a8f9  push    r14
0x18003a8fb  push    r15
0x18003a8fd  lea     rbp, [rsp-0F8h]
0x18003a905  sub     rsp, 1F8h
0x18003a90c  mov     rax, cs:__security_cookie
0x18003a913  xor     rax, rsp
0x18003a916  mov     [rbp+130h+var_50], rax
0x18003a91d  mov     [rsp+230h+var_1E0], r9
0x18003a922  mov     r12d, r8d
0x18003a925  mov     r14d, edx
0x18003a928  mov     r13, rcx
0x18003a92b  mov     rsi, [rbp+130h+arg_20]
0x18003a932  mov     rax, [rbp+130h+arg_28]
0x18003a939  mov     [rsp+230h+var_1F8], rax
0x18003a93e  xor     ebx, ebx
0x18003a940  mov     [rbp+130h+var_160], rbx
0x18003a944  mov     [rbp+130h+var_158], rbx
0x18003a948  mov     r15d, ebx
0x18003a94b  xorps   xmm0, xmm0
0x18003a94e  xor     eax, eax
0x18003a950  movups  xmmword ptr [rsp+230h+pvar], xmm0
0x18003a955  mov     [rsp+230h+var_1C8], rax
0x18003a95a  mov     [rbp+130h+var_1B0], 1F40h
0x18003a961  mov     [rbp+130h+var_1AC], 2B11h
0x18003a968  mov     [rbp+130h+var_1A8], 3E80h
0x18003a96f  mov     [rbp+130h+var_1A4], 5622h
0x18003a976  mov     [rbp+130h+var_1A0], 5DC0h
0x18003a97d  mov     [rbp+130h+var_19C], 7D00h
0x18003a984  mov     [rbp+130h+var_198], 0AC44h
0x18003a98b  mov     [rbp+130h+var_194], 0BB80h
0x18003a992  mov     [rbp+130h+var_190], 15888h
0x18003a999  mov     [rbp+130h+var_18C], 17700h
0x18003a9a0  mov     [rbp+130h+var_188], 2B110h
0x18003a9a7  mov     [rbp+130h+var_184], 2EE00h
0x18003a9ae  mov     [rbp+130h+var_180], 56220h
0x18003a9b5  mov     [rbp+130h+var_17C], 5DC00h
0x18003a9bc  movdqa  xmm0, cs:__xmm@00000010000000100000000800000008
0x18003a9c4  movdqu  [rbp+130h+var_150], xmm0
0x18003a9c9  movdqa  xmm1, cs:__xmm@00000020000000180000001800000018
0x18003a9d1  movdqu  [rbp+130h+var_140], xmm1
0x18003a9d6  lea     eax, [rbx+20h]
0x18003a9d9  mov     [rbp+130h+var_130], eax
0x18003a9dc  mov     [rbp+130h+var_12C], eax
0x18003a9df  mov     [rbp+130h+var_120], ebx
0x18003a9e2  mov     [rbp+130h+var_118], rbx
0x18003a9e6  movups  xmm0, xmmword ptr cs:unk_18016E1D0
0x18003a9ed  movdqu  [rbp+130h+var_110], xmm0
0x18003a9f2  movups  xmm1, xmmword ptr cs:unk_18016E1F0
0x18003a9f9  movdqu  [rbp+130h+var_100], xmm1
0x18003a9fe  mov     [rbp+130h+var_F0], ebx
0x18003aa01  mov     [rbp+130h+var_E8], rbx
0x18003aa05  movups  xmm0, xmmword ptr cs:unk_18016E210
0x18003aa0c  movdqu  [rbp+130h+var_E0], xmm0
0x18003aa11  mov     [rbp+130h+var_D0], ebx
0x18003aa14  mov     [rbp+130h+var_C8], rbx
0x18003aa18  movups  xmm0, xmmword ptr cs:unk_18016E1E0
0x18003aa1f  movdqu  [rbp+130h+var_C0], xmm0
0x18003aa24  mov     [rbp+130h+var_B0], ebx
0x18003aa2a  mov     [rbp+130h+var_A8], rbx
0x18003aa31  movups  xmm0, xmmword ptr cs:unk_18016E200
0x18003aa38  movdqu  [rbp+130h+var_A0], xmm0
0x18003aa40  mov     edi, ebx
0x18003aa42  mov     [rbp+130h+var_178], rbx
0x18003aa46  call    ?HasHardwareAudioEngine@CEndpointCharacteristics@@QEAAHXZ; CEndpointCharacteristics::HasHardwareAudioEngine(void)
0x18003aa4b  test    eax, eax
0x18003aa4d  setnz   bl
0x18003aa50  mov     [rsp+230h+pv], rdi
0x18003aa55  mov     rax, [rsp+230h+var_1F8]
0x18003aa5a  movaps  xmm0, xmmword ptr [rax]
0x18003aa5d  movaps  [rbp+130h+var_90], xmm0
0x18003aa64  movaps  xmm1, xmmword ptr [rax+10h]
0x18003aa68  movaps  [rbp+130h+var_80], xmm1
0x18003aa6f  movaps  xmm0, xmmword ptr [rax+20h]
0x18003aa73  movaps  [rbp+130h+var_70], xmm0
0x18003aa7a  movaps  xmm1, xmmword ptr [rax+30h]
0x18003aa7e  movaps  [rbp+130h+var_60], xmm1
0x18003aa85  lea     rax, [rsp+230h+pv]
0x18003aa8a  mov     [rsp+230h+var_208], rax
0x18003aa8f  lea     rax, [rbp+130h+var_90]
0x18003aa96  mov     [rsp+230h+var_210], rax
0x18003aa9b  mov     r9d, r14d
0x18003aa9e  mov     r8b, bl
0x18003aaa1  xor     edx, edx
0x18003aaa3  mov     rcx, r13
0x18003aaa6  call    CEndpointCharacteristics__GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003aaab  nop
0x18003aaac  mov     rcx, [rsp+230h+pv]; pv
0x18003aab1  call    cs:__imp_CoTaskMemFree
0x18003aab7  mov     [rsp+230h+pv], rdi
0x18003aabc  mov     rax, [rsp+230h+var_1F8]
0x18003aac1  movaps  xmm0, xmmword ptr [rax]
0x18003aac4  movaps  [rbp+130h+var_90], xmm0
0x18003aacb  movaps  xmm1, xmmword ptr [rax+10h]
0x18003aacf  movaps  [rbp+130h+var_80], xmm1
0x18003aad6  movaps  xmm0, xmmword ptr [rax+20h]
0x18003aada  movaps  [rbp+130h+var_70], xmm0
0x18003aae1  movaps  xmm1, xmmword ptr [rax+30h]
0x18003aae5  movaps  [rbp+130h+var_60], xmm1
0x18003aaec  lea     rax, [rsp+230h+pv]
0x18003aaf1  mov     [rsp+230h+var_208], rax
0x18003aaf6  lea     rax, [rbp+130h+var_90]
0x18003aafd  mov     [rsp+230h+var_210], rax
0x18003ab02  mov     r9d, r14d
0x18003ab05  mov     r8b, bl
0x18003ab08  mov     dl, 1
0x18003ab0a  mov     rcx, r13
0x18003ab0d  call    CEndpointCharacteristics__GetDeviceFormatInternal__lambda_8e14c3ef8ca8112e9c42aed54b541fda___
0x18003ab12  nop
0x18003ab13  mov     rcx, [rsp+230h+pv]; pv
0x18003ab18  call    cs:__imp_CoTaskMemFree
0x18003ab1e  mov     [rsp+230h+pv], rdi
0x18003ab23  movaps  xmm0, xmmword ptr [rsi]
0x18003ab26  movdqa  xmmword ptr [rsp+230h+var_1C0.Data1], xmm0
0x18003ab2c  lea     rax, [rsp+230h+pv]
0x18003ab31  mov     [rsp+230h+var_210], rax; struct tWAVEFORMATEX **
0x18003ab36  lea     r9, [rsp+230h+var_1C0]; struct _GUID *
0x18003ab3b  mov     r8d, r14d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18003ab3e  mov     rdx, [r13+48h]; struct IPropertyStore *
0x18003ab42  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; struct IMMDeviceEnumerator *
0x18003ab49  call    ?GetProposedConnectorFormatForProcessingMode@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEAPEAUtWAVEFORMATEX@@@Z; GetProposedConnectorFormatForProcessingMode(IMMDeviceEnumerator *,IPropertyStore *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX * *)
0x18003ab4e  mov     rbx, [rsp+230h+pv]
0x18003ab53  xor     r14d, r14d
0x18003ab56  test    eax, eax
0x18003ab58  jns     loc_18003AF42
0x18003ab5e  mov     rsi, [rsp+230h+var_1F8]
0x18003ab63  mov     rcx, rbx; pv
0x18003ab66  call    cs:__imp_CoTaskMemFree
0x18003ab6c  mov     qword ptr [rsp+230h+var_1C0.Data1], r14
0x18003ab71  mov     rcx, [r13+48h]
0x18003ab75  mov     rax, [rcx]
0x18003ab78  lea     r8, [rsp+230h+pvar]
0x18003ab7d  lea     rdx, PKEY_AudioEngine_DeviceFormat
0x18003ab84  mov     rax, [rax+28h]
0x18003ab88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab8d  test    eax, eax
0x18003ab8f  js      short loc_18003ABB6
0x18003ab91  cmp     dword ptr [rsp+230h+pvar+8], 12h
0x18003ab96  jb      short loc_18003ABB6
0x18003ab98  cmp     word ptr [rsp+230h+pvar], 41h ; 'A'
0x18003ab9e  jnz     short loc_18003ABB6
0x18003aba0  mov     rcx, [rsp+230h+var_1C8]; struct tWAVEFORMATEX *
0x18003aba5  movzx   edx, word ptr [rcx+10h]
0x18003aba9  add     rdx, 12h
0x18003abad  mov     eax, dword ptr [rsp+230h+pvar+8]
0x18003abb1  cmp     rax, rdx
0x18003abb4  jz      short loc_18003AC1C
0x18003abb6  lea     rcx, [rsp+230h+pvar]; pvar
0x18003abbb  call    cs:__imp_PropVariantClear
0x18003abc1  nop
0x18003abc2  xor     ecx, ecx; pv
0x18003abc4  call    cs:__imp_CoTaskMemFree
0x18003abca  lea     eax, [r12+r12*2]
0x18003abce  mov     r14d, eax
0x18003abd1  mov     qword ptr [rsp+230h+var_1C0.Data1], r14
0x18003abd6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003abdd  mov     ecx, eax; unsigned __int64
0x18003abdf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18003abe4  mov     rdi, rax
0x18003abe7  mov     [rbp+130h+var_178], rax
0x18003abeb  xor     edx, edx
0x18003abed  test    rax, rax
0x18003abf0  jz      loc_18003AC8B
0x18003abf6  mov     ebx, edx
0x18003abf8  movsxd  rax, ebx
0x18003abfb  shl     rax, 4
0x18003abff  mov     [rbp+130h+var_168], rax
0x18003ac03  mov     esi, [rbp+rax+130h+var_120]
0x18003ac07  mov     dword ptr [rsp+230h+pv], esi
0x18003ac0b  test    esi, esi
0x18003ac0d  jnz     loc_18003AC93
0x18003ac13  inc     ebx
0x18003ac15  cmp     ebx, 9
0x18003ac18  jb      short loc_18003ABF8
0x18003ac1a  jmp     short loc_18003AC4B
0x18003ac1c  call    ?ValidateWaveFormatEx@@YAJPEBUtWAVEFORMATEX@@@Z; ValidateWaveFormatEx(tWAVEFORMATEX const *)
0x18003ac21  mov     r15d, eax
0x18003ac24  test    eax, eax
0x18003ac26  js      short loc_18003ABB6
0x18003ac28  xor     r8d, r8d
0x18003ac2b  mov     rdx, [rsp+230h+var_1C8]
0x18003ac30  mov     rcx, rsi
0x18003ac33  call    _lambda_5789e60fd85b99cd3c89d9f341e01d71___operator__
0x18003ac38  mov     r15d, eax
0x18003ac3b  test    eax, eax
0x18003ac3d  jns     loc_18003ABB6
0x18003ac43  xor     ecx, ecx; pv
0x18003ac45  call    cs:__imp_CoTaskMemFree
0x18003ac4b  lea     rcx, [rsp+230h+pvar]; pvar
0x18003ac50  call    cs:__imp_PropVariantClear
0x18003ac56  nop
0x18003ac57  mov     edx, 1; struct std::nothrow_t *
0x18003ac5c  mov     rcx, rdi; void *
0x18003ac5f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ac64  nop
0x18003ac65  mov     eax, r15d
0x18003ac68  mov     rcx, [rbp+130h+var_50]
0x18003ac6f  xor     rcx, rsp; StackCookie
0x18003ac72  call    __security_check_cookie
0x18003ac77  add     rsp, 1F8h
0x18003ac7e  pop     r15
0x18003ac80  pop     r14
0x18003ac82  pop     r13
0x18003ac84  pop     r12
0x18003ac86  pop     rdi
0x18003ac87  pop     rsi
0x18003ac88  pop     rbx
0x18003ac89  pop     rbp
0x18003ac8a  retn
0x18003ac8b  mov     r15d, 8007000Eh
0x18003ac91  jmp     short loc_18003AC4B
0x18003ac93  mov     r8, r14; Size
0x18003ac96  mov     edx, 1; Val
0x18003ac9b  mov     rcx, rdi; void *
0x18003ac9e  call    memset_0
0x18003aca3  mov     r9d, ebx
0x18003aca6  mov     r8, rdi
0x18003aca9  mov     r13, [rsp+230h+var_1E0]
0x18003acae  mov     rdx, r13
0x18003acb1  mov     ecx, r12d
0x18003acb4  call    ForEachViableDataRange__lambda_4a7d50afe418974c538bbd7e3b182920___; ForEachViableDataRange__lambda_4a7d50afe418974c538bbd7e3b182920_
0x18003acb9  xor     edx, edx
0x18003acbb  test    al, al
0x18003acbd  jz      loc_18003AC13
0x18003acc3  mov     eax, edx
0x18003acc5  mov     [rsp+230h+var_1EC], eax
0x18003acc9  cmp     eax, esi
0x18003accb  jge     loc_18003AFC4
0x18003acd1  mov     esi, edx
0x18003acd3  mov     [rsp+230h+var_1F0], esi
0x18003acd7  cmp     esi, 0Eh
0x18003acda  jnb     loc_18003AFB5
0x18003ace0  lea     r14, [rdi+r12]
0x18003ace4  mov     r8, r12; Size
0x18003ace7  mov     rdx, rdi; Src
0x18003acea  mov     rcx, r14; void *
0x18003aced  call    memcpy_0
0x18003acf2  movsxd  rax, esi
0x18003acf5  mov     r9d, [rbp+rax*4+130h+var_1B0]
0x18003acfa  mov     [rsp+230h+var_1E8], r9d
0x18003acff  xor     edx, edx
0x18003ad01  test    r12d, r12d
0x18003ad04  jnz     loc_18003AEB9
0x18003ad0a  mov     r13d, edx
0x18003ad0d  cmp     r13d, 5
0x18003ad11  jnb     loc_18003AEA9
0x18003ad17  lea     esi, [r12+r12]
0x18003ad1b  add     rsi, rdi
0x18003ad1e  mov     r8, r12; Size
0x18003ad21  mov     rdx, r14; Src
0x18003ad24  mov     rcx, rsi; void *
0x18003ad27  call    memcpy_0
0x18003ad2c  movsxd  r11, r13d
0x18003ad2f  mov     r9d, dword ptr [rbp+r11*8+130h+var_150]
0x18003ad34  xor     edx, edx
0x18003ad36  test    r12d, r12d
0x18003ad39  jz      short loc_18003AD9A
0x18003ad3b  mov     rcx, [rsp+230h+var_1E0]
0x18003ad40  mov     r10b, dl
0x18003ad43  mov     r8d, edx
0x18003ad46  xor     r11d, r11d
0x18003ad49  mov     edx, [rcx]
0x18003ad4b  add     rdx, rcx
0x18003ad4e  mov     [rbp+130h+var_170], rdx
0x18003ad52  mov     edx, r8d
0x18003ad55  cmp     [rdx+rsi], r11b
0x18003ad59  jz      short loc_18003AD80
0x18003ad5b  mov     rax, qword ptr cs:_GUID_73647561_0000_0010_8000_00aa00389b71.Data1
0x18003ad62  sub     rax, [rcx+10h]
0x18003ad66  jnz     short loc_18003AD73
0x18003ad68  mov     rax, qword ptr cs:_GUID_73647561_0000_0010_8000_00aa00389b71.Data4
0x18003ad6f  sub     rax, [rcx+18h]
0x18003ad73  test    rax, rax
0x18003ad76  jz      loc_18003AE68
0x18003ad7c  mov     [rdx+rsi], r11b
0x18003ad80  inc     r8d
0x18003ad83  mov     rcx, [rbp+130h+var_170]
0x18003ad87  cmp     r8d, r12d
0x18003ad8a  jb      short loc_18003AD49
0x18003ad8c  movsxd  r11, r13d
0x18003ad8f  xor     edx, edx
0x18003ad91  test    r10b, r10b
0x18003ad94  jz      loc_18003AE60
0x18003ad9a  xorps   xmm0, xmm0
0x18003ad9d  xor     eax, eax
0x18003ad9f  movups  [rbp+130h+var_90], xmm0
0x18003ada6  movups  [rbp+130h+var_80], xmm0
0x18003adad  mov     qword ptr [rbp+130h+var_70], rax
0x18003adb4  movsxd  rcx, [rsp+230h+var_1EC]
0x18003adb9  mov     rax, [rbp+130h+var_168]
0x18003adbd  mov     rax, [rbp+rax+130h+var_118]
0x18003adc2  mov     edx, [rax+rcx*4]
0x18003adc5  mov     ecx, dword ptr [rbp+r11*8+130h+var_150+4]
0x18003adca  test    edx, edx
0x18003adcc  jz      loc_18003AF9D
  ... truncated ...
```
