# LookUpTableFlushComplete

- ea: `0x18001b010`
- end: `0x18001b3ed`
- name: `LookUpTableFlushComplete`
- size: `989`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001ac90`
- `0x18001b490`
- `0x18001b4f0`
- `0x18001b720`

## callees

- `0x180001138`
- `0x180001a80`
- `0x18001ab60`
- `0x18001b010`

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
      if ( (unsigned int)dword_180028730 > 5
        && (qword_180028740 & 0x200000000000LL) != 0
        && (qword_180028748 & 0x200000000000LL) == qword_180028748 )
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
          (unsigned int)&word_180024C2E,
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
0x18001b010  mov     [rsp-8+arg_8], rbx
0x18001b015  mov     [rsp-8+arg_10], rsi
0x18001b01a  push    rbp
0x18001b01b  push    rdi
0x18001b01c  push    r14
0x18001b01e  lea     rbp, [rsp-90h]
0x18001b026  sub     rsp, 230h
0x18001b02d  mov     rax, cs:__security_cookie
0x18001b034  xor     rax, rsp
0x18001b037  mov     [rbp+0A0h+var_18], rax
0x18001b03e  mov     eax, [rcx+100h]
0x18001b044  xor     edi, edi
0x18001b046  mov     rbx, rcx
0x18001b049  test    eax, eax
0x18001b04b  jz      loc_18001B3C6
0x18001b051  cmp     [rcx+128h], eax
0x18001b057  ja      short loc_18001B062
0x18001b059  cmp     [rcx+118h], rdi
0x18001b060  jnz     short loc_18001B068
0x18001b062  mov     [rcx+128h], eax
0x18001b068  cmp     [rcx+124h], eax
0x18001b06e  jnb     short loc_18001B076
0x18001b070  mov     [rcx+124h], eax
0x18001b076  mov     esi, 1
0x18001b07b  movq    xmm1, rax
0x18001b080  movq    xmm0, rsi
0x18001b085  lea     r14d, [rsi+1Fh]
0x18001b089  punpcklqdq xmm1, xmm0
0x18001b08d  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18001b095  paddq   xmm1, xmm0
0x18001b099  movdqu  xmmword ptr [rcx+110h], xmm1
0x18001b0a1  cmp     [rcx+110h], rdi
0x18001b0a8  jz      loc_18001B3B5
0x18001b0ae  mov     eax, cs:dword_180028730
0x18001b0b4  cmp     eax, 5
0x18001b0b7  jbe     loc_18001B39B
0x18001b0bd  mov     rcx, cs:qword_180028748
0x18001b0c4  mov     rdx, 200000000000h
0x18001b0ce  mov     rax, cs:qword_180028740
0x18001b0d5  test    rdx, rax
0x18001b0d8  jz      loc_18001B39B
0x18001b0de  mov     rax, rcx
0x18001b0e1  and     rax, rdx
0x18001b0e4  cmp     rax, rcx
0x18001b0e7  jnz     loc_18001B39B
0x18001b0ed  lea     ecx, [rsi+29h]
0x18001b0f0  mov     [rbp+0A0h+var_120], 4
0x18001b0f4  lea     rax, aSummarycount; "SummaryCount"
0x18001b0fb  mov     [rbp+0A0h+var_A0], cx
0x18001b0ff  mov     [rbp+0A0h+var_B8], rax
0x18001b103  lea     eax, [rsi+17h]
0x18001b106  mov     [rbp+0A0h+var_B0], ax
0x18001b10a  mov     eax, [rbx+134h]
0x18001b110  mov     [rbp+0A0h+var_108], rax
0x18001b114  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18001b11b  mov     [rbp+0A0h+var_A8], rax
0x18001b11f  mov     eax, [rbx+130h]
0x18001b125  mov     [rbp+0A0h+var_100], rax
0x18001b129  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18001b130  mov     [rbp+0A0h+var_98], rax
0x18001b134  mov     eax, [rbx+12Ch]
0x18001b13a  mov     [rbp+0A0h+var_F8], rax
0x18001b13e  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18001b145  mov     [rbp+0A0h+var_88], rax
0x18001b149  mov     eax, [rbx+128h]
0x18001b14f  mov     [rbp+0A0h+var_F0], rax
0x18001b153  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18001b15a  mov     [rbp+0A0h+var_78], rax
0x18001b15e  mov     eax, [rbx+124h]
0x18001b164  mov     [rbp+0A0h+var_E8], rax
0x18001b168  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18001b16f  mov     [rbp+0A0h+var_68], rax
0x18001b173  mov     rax, [rbx+110h]
0x18001b17a  mov     [rbp+0A0h+var_E0], rax
0x18001b17e  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18001b185  mov     [rbp+0A0h+var_58], rax
0x18001b189  lea     eax, [rsi+25h]
0x18001b18c  mov     [rbp+0A0h+var_50], ax
0x18001b190  mov     eax, [rbx+120h]
0x18001b196  mov     [rbp+0A0h+var_D8], rax
0x18001b19a  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18001b1a1  mov     [rbp+0A0h+var_48], rax
0x18001b1a5  mov     rax, [rbx+118h]
0x18001b1ac  mov     [rbp+0A0h+var_D0], rax
0x18001b1b0  lea     rax, aNumflushes; "NumFlushes"
0x18001b1b7  mov     [rbp+0A0h+var_38], rax
0x18001b1bb  lea     eax, [rsi+13h]
0x18001b1be  mov     [rbp+0A0h+var_30], ax
0x18001b1c2  mov     rax, [rbx+148h]
0x18001b1c9  mov     [rbp+0A0h+var_90], cx
0x18001b1cd  mov     [rbp+0A0h+var_80], cx
0x18001b1d1  lea     ecx, [rsi+21h]
0x18001b1d4  mov     [rbp+0A0h+var_114], esi
0x18001b1d7  mov     [rbp+0A0h+var_11F], 4
0x18001b1db  mov     [rbp+0A0h+var_11E], 4
0x18001b1df  mov     [rbp+0A0h+var_11D], 4
0x18001b1e3  mov     [rbp+0A0h+var_11C], 4
0x18001b1e7  mov     [rbp+0A0h+var_70], cx
0x18001b1eb  mov     [rbp+0A0h+var_11B], 4
0x18001b1ef  mov     [rbp+0A0h+var_60], cx
0x18001b1f3  mov     [rbp+0A0h+var_11A], 4
0x18001b1f7  mov     [rbp+0A0h+var_119], 4
0x18001b1fb  mov     [rbp+0A0h+var_40], r14w
0x18001b200  mov     [rbp+0A0h+var_118], 4
0x18001b204  mov     rcx, [rax+8]
0x18001b208  lea     rax, [rbp+0A0h+var_28]
0x18001b20c  mov     [rbp+0A0h+var_C8], rax
0x18001b210  lea     rax, [rbp+0A0h+var_120]
0x18001b214  mov     [rsp+240h+var_128], rax
0x18001b21c  lea     rax, [rbp+0A0h+var_114]
0x18001b220  mov     [rsp+240h+var_130], rax
0x18001b228  lea     rax, [rbp+0A0h+var_B8]
0x18001b22c  movups  xmm0, xmmword ptr [rcx-10h]
0x18001b230  mov     [rsp+240h+var_138], rax
0x18001b238  lea     rax, [rbp+0A0h+var_11F]
0x18001b23c  mov     [rsp+240h+var_140], rax
0x18001b244  lea     rax, [rbp+0A0h+var_108]
0x18001b248  mov     [rsp+240h+var_148], rax
0x18001b250  lea     rax, [rbp+0A0h+var_A8]
0x18001b254  mov     [rsp+240h+var_150], rax
0x18001b25c  lea     rax, [rbp+0A0h+var_11E]
0x18001b260  movdqu  [rbp+0A0h+var_28], xmm0
0x18001b265  mov     [rbp+0A0h+var_117], dil
0x18001b269  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x18001b270  mov     [rbp+0A0h+var_10C], 12Ch
0x18001b277  mov     [rbp+0A0h+var_C0], 1000000h
0x18001b27f  mov     [rsp+240h+var_158], rax
0x18001b287  lea     rdx, word_180024C2E
0x18001b28e  lea     rax, [rbp+0A0h+var_100]
0x18001b292  mov     [rsp+240h+var_160], rax
0x18001b29a  lea     rax, [rbp+0A0h+var_98]
0x18001b29e  mov     [rsp+240h+var_168], rax
0x18001b2a6  lea     rax, [rbp+0A0h+var_11D]
0x18001b2aa  mov     [rsp+240h+var_170], rax
0x18001b2b2  lea     rax, [rbp+0A0h+var_F8]
0x18001b2b6  mov     [rsp+240h+var_178], rax
0x18001b2be  lea     rax, [rbp+0A0h+var_88]
0x18001b2c2  mov     [rsp+240h+var_180], rax
0x18001b2ca  lea     rax, [rbp+0A0h+var_11C]
0x18001b2ce  mov     [rsp+240h+var_188], rax
0x18001b2d6  lea     rax, [rbp+0A0h+var_F0]
0x18001b2da  mov     [rsp+240h+var_190], rax
0x18001b2e2  lea     rax, [rbp+0A0h+var_78]
0x18001b2e6  mov     [rsp+240h+var_198], rax
0x18001b2ee  lea     rax, [rbp+0A0h+var_11B]
0x18001b2f2  mov     [rsp+240h+var_1A0], rax
0x18001b2fa  lea     rax, [rbp+0A0h+var_E8]
0x18001b2fe  mov     [rsp+240h+var_1A8], rax
0x18001b306  lea     rax, [rbp+0A0h+var_68]
0x18001b30a  mov     [rsp+240h+var_1B0], rax
0x18001b312  lea     rax, [rbp+0A0h+var_11A]
0x18001b316  mov     [rsp+240h+var_1B8], rax
0x18001b31e  lea     rax, [rbp+0A0h+var_E0]
0x18001b322  mov     [rsp+240h+var_1C0], rax
0x18001b32a  lea     rax, [rbp+0A0h+var_58]
0x18001b32e  mov     [rsp+240h+var_1C8], rax
0x18001b333  lea     rax, [rbp+0A0h+var_119]
0x18001b337  mov     [rsp+240h+var_1D0], rax
0x18001b33c  lea     rax, [rbp+0A0h+var_D8]
0x18001b340  mov     [rsp+240h+var_1D8], rax
0x18001b345  lea     rax, [rbp+0A0h+var_48]
0x18001b349  mov     [rsp+240h+var_1E0], rax
0x18001b34e  lea     rax, [rbp+0A0h+var_118]
0x18001b352  mov     [rsp+240h+var_1E8], rax
0x18001b357  lea     rax, [rbp+0A0h+var_D0]
0x18001b35b  mov     [rsp+240h+var_1F0], rax
0x18001b360  lea     rax, [rbp+0A0h+var_38]
0x18001b364  mov     [rsp+240h+var_1F8], rax
0x18001b369  lea     rax, [rbp+0A0h+var_C8]
0x18001b36d  mov     [rsp+240h+var_200], rax
0x18001b372  lea     rax, [rbp+0A0h+var_117]
0x18001b376  mov     [rsp+240h+var_208], rax
0x18001b37b  lea     rax, [rbp+0A0h+var_110]
0x18001b37f  mov     [rsp+240h+var_210], rax
0x18001b384  lea     rax, [rbp+0A0h+var_10C]
0x18001b388  mov     [rsp+240h+var_218], rax
0x18001b38d  lea     rax, [rbp+0A0h+var_C0]
0x18001b391  mov     [rsp+240h+var_220], rax
0x18001b396  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18001b39b  xorps   xmm0, xmm0
0x18001b39e  xor     eax, eax
0x18001b3a0  movups  xmmword ptr [rbx+110h], xmm0
0x18001b3a7  movups  xmmword ptr [rbx+120h], xmm0
0x18001b3ae  mov     [rbx+130h], rax
0x18001b3b5  mov     edx, edi
0x18001b3b7  mov     rcx, rbx
0x18001b3ba  call    FlushLookUpTableBucket
0x18001b3bf  add     edi, esi
0x18001b3c1  cmp     edi, r14d
0x18001b3c4  jb      short loc_18001B3B5
0x18001b3c6  mov     rcx, [rbp+0A0h+var_18]
0x18001b3cd  xor     rcx, rsp; StackCookie
0x18001b3d0  call    __security_check_cookie
0x18001b3d5  lea     r11, [rsp+240h+var_10]
0x18001b3dd  mov     rbx, [r11+28h]
0x18001b3e1  mov     rsi, [r11+30h]
0x18001b3e5  mov     rsp, r11
0x18001b3e8  pop     r14
0x18001b3ea  pop     rdi
0x18001b3eb  pop     rbp
0x18001b3ec  retn
```
