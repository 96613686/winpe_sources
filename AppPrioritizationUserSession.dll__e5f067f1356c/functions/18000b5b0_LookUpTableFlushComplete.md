# LookUpTableFlushComplete

- ea: `0x18000b5b0`
- end: `0x18000b98d`
- name: `LookUpTableFlushComplete`
- size: `989`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b560`
- `0x18000ba30`
- `0x18000ba90`
- `0x18000bcc0`

## callees

- `0x1800013c0`
- `0x180002650`
- `0x18000b43c`
- `0x18000b5b0`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(const __m128i *a1, __int64 a2, int a3, int a4)
{
  __int64 result; // rax
  unsigned int v5; // edi
  __int64 v7; // rax
  __int64 v8; // rcx
  char v9; // [rsp+120h] [rbp-80h] BYREF
  char v10; // [rsp+121h] [rbp-7Fh] BYREF
  char v11; // [rsp+122h] [rbp-7Eh] BYREF
  char v12; // [rsp+123h] [rbp-7Dh] BYREF
  char v13; // [rsp+124h] [rbp-7Ch] BYREF
  char v14; // [rsp+125h] [rbp-7Bh] BYREF
  char v15; // [rsp+126h] [rbp-7Ah] BYREF
  char v16; // [rsp+127h] [rbp-79h] BYREF
  char v17; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v18[3]; // [rsp+129h] [rbp-77h] BYREF
  int v19; // [rsp+12Ch] [rbp-74h] BYREF
  int v20; // [rsp+130h] [rbp-70h] BYREF
  int v21; // [rsp+134h] [rbp-6Ch] BYREF
  __int64 v22; // [rsp+138h] [rbp-68h] BYREF
  __int64 v23; // [rsp+140h] [rbp-60h] BYREF
  __int64 v24; // [rsp+148h] [rbp-58h] BYREF
  __int64 v25; // [rsp+150h] [rbp-50h] BYREF
  __int64 v26; // [rsp+158h] [rbp-48h] BYREF
  __int64 v27; // [rsp+160h] [rbp-40h] BYREF
  __int64 v28; // [rsp+168h] [rbp-38h] BYREF
  __int64 v29; // [rsp+170h] [rbp-30h] BYREF
  __int128 *v30; // [rsp+178h] [rbp-28h] BYREF
  __int64 v31; // [rsp+180h] [rbp-20h] BYREF
  const wchar_t *v32; // [rsp+188h] [rbp-18h] BYREF
  __int16 v33; // [rsp+190h] [rbp-10h]
  const wchar_t *v34; // [rsp+198h] [rbp-8h] BYREF
  __int16 v35; // [rsp+1A0h] [rbp+0h]
  const wchar_t *v36; // [rsp+1A8h] [rbp+8h] BYREF
  __int16 v37; // [rsp+1B0h] [rbp+10h]
  const wchar_t *v38; // [rsp+1B8h] [rbp+18h] BYREF
  __int16 v39; // [rsp+1C0h] [rbp+20h]
  const wchar_t *v40; // [rsp+1C8h] [rbp+28h] BYREF
  __int16 v41; // [rsp+1D0h] [rbp+30h]
  const wchar_t *v42; // [rsp+1D8h] [rbp+38h] BYREF
  __int16 v43; // [rsp+1E0h] [rbp+40h]
  const wchar_t *v44; // [rsp+1E8h] [rbp+48h] BYREF
  __int16 v45; // [rsp+1F0h] [rbp+50h]
  const wchar_t *v46; // [rsp+1F8h] [rbp+58h] BYREF
  __int16 v47; // [rsp+200h] [rbp+60h]
  const wchar_t *v48; // [rsp+208h] [rbp+68h] BYREF
  __int16 v49; // [rsp+210h] [rbp+70h]
  __int128 v50; // [rsp+218h] [rbp+78h] BYREF

  result = a1[16].m128i_u32[0];
  v5 = 0;
  if ( (_DWORD)result )
  {
    if ( a1[18].m128i_i32[2] > (unsigned int)result || !a1[17].m128i_i64[1] )
      a1[18].m128i_i32[2] = result;
    if ( a1[18].m128i_i32[1] < (unsigned int)result )
      a1[18].m128i_i32[1] = result;
    a1[17] = _mm_add_epi64(
               _mm_unpacklo_epi64((__m128i)(unsigned __int64)result, (__m128i)1uLL),
               _mm_loadu_si128(a1 + 17));
    if ( a1[17].m128i_i64[0] )
    {
      if ( (unsigned int)dword_180014038 > 5
        && (qword_180014048 & 0x200000000000LL) != 0
        && (qword_180014050 & 0x200000000000LL) == qword_180014050 )
      {
        v9 = 4;
        v35 = 42;
        v32 = L"SummaryCount";
        v33 = 24;
        v22 = a1[19].m128i_u32[1];
        v34 = L"NumLargeEventFailures";
        v23 = a1[19].m128i_u32[0];
        v36 = L"NumAllocationFailures";
        v24 = a1[18].m128i_u32[3];
        v38 = L"NumBucketLimitReached";
        v25 = a1[18].m128i_u32[2];
        v40 = L"MinEntriesFlushed";
        v26 = a1[18].m128i_u32[1];
        v42 = L"MaxEntriesFlushed";
        v27 = a1[17].m128i_i64[0];
        v44 = L"TotalEntriesFlushed";
        v45 = 38;
        v28 = a1[18].m128i_u32[0];
        v46 = L"MaxEntriesStored";
        v29 = a1[17].m128i_i64[1];
        v48 = L"NumFlushes";
        v49 = 20;
        v7 = a1[20].m128i_i64[1];
        v37 = 42;
        v39 = 42;
        v19 = 1;
        v10 = 4;
        v11 = 4;
        v12 = 4;
        v13 = 4;
        v41 = 34;
        v14 = 4;
        v43 = 34;
        v15 = 4;
        v16 = 4;
        v47 = 32;
        v17 = 4;
        v8 = *(_QWORD *)(v7 + 8);
        v30 = &v50;
        v50 = *(_OWORD *)(v8 - 16);
        v18[0] = 0;
        v20 = -1;
        v21 = 300;
        v31 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v8,
          (unsigned int)&unk_1800102B0,
          a3,
          a4,
          (__int64)&v31,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)v18,
          (__int64)&v30,
          (__int64)&v48,
          (__int64)&v29,
          (__int64)&v17,
          (__int64)&v46,
          (__int64)&v28,
          (__int64)&v16,
          (__int64)&v44,
          (__int64)&v27,
          (__int64)&v15,
          (__int64)&v42,
          (__int64)&v26,
          (__int64)&v14,
          (__int64)&v40,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v38,
          (__int64)&v24,
          (__int64)&v12,
          (__int64)&v36,
          (__int64)&v23,
          (__int64)&v11,
          (__int64)&v34,
          (__int64)&v22,
          (__int64)&v10,
          (__int64)&v32,
          (__int64)&v19,
          (__int64)&v9);
      }
      a1[17] = 0;
      a1[18] = 0;
      a1[19].m128i_i64[0] = 0;
    }
    do
      result = FlushLookUpTableBucket(a1, v5++);
    while ( v5 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x18000b5b0  mov     [rsp-8+arg_8], rbx
0x18000b5b5  mov     [rsp-8+arg_10], rsi
0x18000b5ba  push    rbp
0x18000b5bb  push    rdi
0x18000b5bc  push    r14
0x18000b5be  lea     rbp, [rsp-90h]
0x18000b5c6  sub     rsp, 230h
0x18000b5cd  mov     rax, cs:__security_cookie
0x18000b5d4  xor     rax, rsp
0x18000b5d7  mov     [rbp+0A0h+var_18], rax
0x18000b5de  mov     eax, [rcx+100h]
0x18000b5e4  xor     edi, edi
0x18000b5e6  mov     rbx, rcx
0x18000b5e9  test    eax, eax
0x18000b5eb  jz      loc_18000B966
0x18000b5f1  cmp     [rcx+128h], eax
0x18000b5f7  ja      short loc_18000B602
0x18000b5f9  cmp     [rcx+118h], rdi
0x18000b600  jnz     short loc_18000B608
0x18000b602  mov     [rcx+128h], eax
0x18000b608  cmp     [rcx+124h], eax
0x18000b60e  jnb     short loc_18000B616
0x18000b610  mov     [rcx+124h], eax
0x18000b616  mov     esi, 1
0x18000b61b  movq    xmm1, rax
0x18000b620  movq    xmm0, rsi
0x18000b625  lea     r14d, [rsi+1Fh]
0x18000b629  punpcklqdq xmm1, xmm0
0x18000b62d  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18000b635  paddq   xmm1, xmm0
0x18000b639  movdqu  xmmword ptr [rcx+110h], xmm1
0x18000b641  cmp     [rcx+110h], rdi
0x18000b648  jz      loc_18000B955
0x18000b64e  mov     eax, cs:dword_180014038
0x18000b654  cmp     eax, 5
0x18000b657  jbe     loc_18000B93B
0x18000b65d  mov     rcx, cs:qword_180014050
0x18000b664  mov     rdx, 200000000000h
0x18000b66e  mov     rax, cs:qword_180014048
0x18000b675  test    rdx, rax
0x18000b678  jz      loc_18000B93B
0x18000b67e  mov     rax, rcx
0x18000b681  and     rax, rdx
0x18000b684  cmp     rax, rcx
0x18000b687  jnz     loc_18000B93B
0x18000b68d  lea     ecx, [rsi+29h]
0x18000b690  mov     [rbp+0A0h+var_120], 4
0x18000b694  lea     rax, aSummarycount; "SummaryCount"
0x18000b69b  mov     [rbp+0A0h+var_A0], cx
0x18000b69f  mov     [rbp+0A0h+var_B8], rax
0x18000b6a3  lea     eax, [rsi+17h]
0x18000b6a6  mov     [rbp+0A0h+var_B0], ax
0x18000b6aa  mov     eax, [rbx+134h]
0x18000b6b0  mov     [rbp+0A0h+var_108], rax
0x18000b6b4  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18000b6bb  mov     [rbp+0A0h+var_A8], rax
0x18000b6bf  mov     eax, [rbx+130h]
0x18000b6c5  mov     [rbp+0A0h+var_100], rax
0x18000b6c9  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18000b6d0  mov     [rbp+0A0h+var_98], rax
0x18000b6d4  mov     eax, [rbx+12Ch]
0x18000b6da  mov     [rbp+0A0h+var_F8], rax
0x18000b6de  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18000b6e5  mov     [rbp+0A0h+var_88], rax
0x18000b6e9  mov     eax, [rbx+128h]
0x18000b6ef  mov     [rbp+0A0h+var_F0], rax
0x18000b6f3  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18000b6fa  mov     [rbp+0A0h+var_78], rax
0x18000b6fe  mov     eax, [rbx+124h]
0x18000b704  mov     [rbp+0A0h+var_E8], rax
0x18000b708  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18000b70f  mov     [rbp+0A0h+var_68], rax
0x18000b713  mov     rax, [rbx+110h]
0x18000b71a  mov     [rbp+0A0h+var_E0], rax
0x18000b71e  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18000b725  mov     [rbp+0A0h+var_58], rax
0x18000b729  lea     eax, [rsi+25h]
0x18000b72c  mov     [rbp+0A0h+var_50], ax
0x18000b730  mov     eax, [rbx+120h]
0x18000b736  mov     [rbp+0A0h+var_D8], rax
0x18000b73a  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18000b741  mov     [rbp+0A0h+var_48], rax
0x18000b745  mov     rax, [rbx+118h]
0x18000b74c  mov     [rbp+0A0h+var_D0], rax
0x18000b750  lea     rax, aNumflushes; "NumFlushes"
0x18000b757  mov     [rbp+0A0h+var_38], rax
0x18000b75b  lea     eax, [rsi+13h]
0x18000b75e  mov     [rbp+0A0h+var_30], ax
0x18000b762  mov     rax, [rbx+148h]
0x18000b769  mov     [rbp+0A0h+var_90], cx
0x18000b76d  mov     [rbp+0A0h+var_80], cx
0x18000b771  lea     ecx, [rsi+21h]
0x18000b774  mov     [rbp+0A0h+var_114], esi
0x18000b777  mov     [rbp+0A0h+var_11F], 4
0x18000b77b  mov     [rbp+0A0h+var_11E], 4
0x18000b77f  mov     [rbp+0A0h+var_11D], 4
0x18000b783  mov     [rbp+0A0h+var_11C], 4
0x18000b787  mov     [rbp+0A0h+var_70], cx
0x18000b78b  mov     [rbp+0A0h+var_11B], 4
0x18000b78f  mov     [rbp+0A0h+var_60], cx
0x18000b793  mov     [rbp+0A0h+var_11A], 4
0x18000b797  mov     [rbp+0A0h+var_119], 4
0x18000b79b  mov     [rbp+0A0h+var_40], r14w
0x18000b7a0  mov     [rbp+0A0h+var_118], 4
0x18000b7a4  mov     rcx, [rax+8]
0x18000b7a8  lea     rax, [rbp+0A0h+var_28]
0x18000b7ac  mov     [rbp+0A0h+var_C8], rax
0x18000b7b0  lea     rax, [rbp+0A0h+var_120]
0x18000b7b4  mov     [rsp+240h+var_128], rax
0x18000b7bc  lea     rax, [rbp+0A0h+var_114]
0x18000b7c0  mov     [rsp+240h+var_130], rax
0x18000b7c8  lea     rax, [rbp+0A0h+var_B8]
0x18000b7cc  movups  xmm0, xmmword ptr [rcx-10h]
0x18000b7d0  mov     [rsp+240h+var_138], rax
0x18000b7d8  lea     rax, [rbp+0A0h+var_11F]
0x18000b7dc  mov     [rsp+240h+var_140], rax
0x18000b7e4  lea     rax, [rbp+0A0h+var_108]
0x18000b7e8  mov     [rsp+240h+var_148], rax
0x18000b7f0  lea     rax, [rbp+0A0h+var_A8]
0x18000b7f4  mov     [rsp+240h+var_150], rax
0x18000b7fc  lea     rax, [rbp+0A0h+var_11E]
0x18000b800  movdqu  [rbp+0A0h+var_28], xmm0
0x18000b805  mov     [rbp+0A0h+var_117], dil
0x18000b809  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x18000b810  mov     [rbp+0A0h+var_10C], 12Ch
0x18000b817  mov     [rbp+0A0h+var_C0], 1000000h
0x18000b81f  mov     [rsp+240h+var_158], rax
0x18000b827  lea     rdx, unk_1800102B0
0x18000b82e  lea     rax, [rbp+0A0h+var_100]
0x18000b832  mov     [rsp+240h+var_160], rax
0x18000b83a  lea     rax, [rbp+0A0h+var_98]
0x18000b83e  mov     [rsp+240h+var_168], rax
0x18000b846  lea     rax, [rbp+0A0h+var_11D]
0x18000b84a  mov     [rsp+240h+var_170], rax
0x18000b852  lea     rax, [rbp+0A0h+var_F8]
0x18000b856  mov     [rsp+240h+var_178], rax
0x18000b85e  lea     rax, [rbp+0A0h+var_88]
0x18000b862  mov     [rsp+240h+var_180], rax
0x18000b86a  lea     rax, [rbp+0A0h+var_11C]
0x18000b86e  mov     [rsp+240h+var_188], rax
0x18000b876  lea     rax, [rbp+0A0h+var_F0]
0x18000b87a  mov     [rsp+240h+var_190], rax
0x18000b882  lea     rax, [rbp+0A0h+var_78]
0x18000b886  mov     [rsp+240h+var_198], rax
0x18000b88e  lea     rax, [rbp+0A0h+var_11B]
0x18000b892  mov     [rsp+240h+var_1A0], rax
0x18000b89a  lea     rax, [rbp+0A0h+var_E8]
0x18000b89e  mov     [rsp+240h+var_1A8], rax
0x18000b8a6  lea     rax, [rbp+0A0h+var_68]
0x18000b8aa  mov     [rsp+240h+var_1B0], rax
0x18000b8b2  lea     rax, [rbp+0A0h+var_11A]
0x18000b8b6  mov     [rsp+240h+var_1B8], rax
0x18000b8be  lea     rax, [rbp+0A0h+var_E0]
0x18000b8c2  mov     [rsp+240h+var_1C0], rax
0x18000b8ca  lea     rax, [rbp+0A0h+var_58]
0x18000b8ce  mov     [rsp+240h+var_1C8], rax
0x18000b8d3  lea     rax, [rbp+0A0h+var_119]
0x18000b8d7  mov     [rsp+240h+var_1D0], rax
0x18000b8dc  lea     rax, [rbp+0A0h+var_D8]
0x18000b8e0  mov     [rsp+240h+var_1D8], rax
0x18000b8e5  lea     rax, [rbp+0A0h+var_48]
0x18000b8e9  mov     [rsp+240h+var_1E0], rax
0x18000b8ee  lea     rax, [rbp+0A0h+var_118]
0x18000b8f2  mov     [rsp+240h+var_1E8], rax
0x18000b8f7  lea     rax, [rbp+0A0h+var_D0]
0x18000b8fb  mov     [rsp+240h+var_1F0], rax
0x18000b900  lea     rax, [rbp+0A0h+var_38]
0x18000b904  mov     [rsp+240h+var_1F8], rax
0x18000b909  lea     rax, [rbp+0A0h+var_C8]
0x18000b90d  mov     [rsp+240h+var_200], rax
0x18000b912  lea     rax, [rbp+0A0h+var_117]
0x18000b916  mov     [rsp+240h+var_208], rax
0x18000b91b  lea     rax, [rbp+0A0h+var_110]
0x18000b91f  mov     [rsp+240h+var_210], rax
0x18000b924  lea     rax, [rbp+0A0h+var_10C]
0x18000b928  mov     [rsp+240h+var_218], rax
0x18000b92d  lea     rax, [rbp+0A0h+var_C0]
0x18000b931  mov     [rsp+240h+var_220], rax
0x18000b936  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18000b93b  xorps   xmm0, xmm0
0x18000b93e  xor     eax, eax
0x18000b940  movups  xmmword ptr [rbx+110h], xmm0
0x18000b947  movups  xmmword ptr [rbx+120h], xmm0
0x18000b94e  mov     [rbx+130h], rax
0x18000b955  mov     edx, edi
0x18000b957  mov     rcx, rbx
0x18000b95a  call    FlushLookUpTableBucket
0x18000b95f  add     edi, esi
0x18000b961  cmp     edi, r14d
0x18000b964  jb      short loc_18000B955
0x18000b966  mov     rcx, [rbp+0A0h+var_18]
0x18000b96d  xor     rcx, rsp; StackCookie
0x18000b970  call    __security_check_cookie
0x18000b975  lea     r11, [rsp+240h+var_10]
0x18000b97d  mov     rbx, [r11+28h]
0x18000b981  mov     rsi, [r11+30h]
0x18000b985  mov     rsp, r11
0x18000b988  pop     r14
0x18000b98a  pop     rdi
0x18000b98b  pop     rbp
0x18000b98c  retn
```
