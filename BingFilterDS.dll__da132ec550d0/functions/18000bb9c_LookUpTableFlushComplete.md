# LookUpTableFlushComplete

- ea: `0x18000bb9c`
- end: `0x18000bf79`
- name: `LookUpTableFlushComplete`
- size: `989`
- prototype: `__int64 __fastcall(const __m128i *, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b1d0`
- `0x18000b820`
- `0x18000c010`
- `0x18000c070`

## callees

- `0x18000178c`
- `0x18000b6f0`
- `0x18000bb9c`
- `0x18000c530`

## pseudocode

```c
__int64 __fastcall LookUpTableFlushComplete(const __m128i *a1, __int64 a2, __int64 a3, __int64 a4)
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
      if ( (unsigned int)dword_180015070 > 5
        && (qword_180015080 & 0x200000000000LL) != 0
        && (qword_180015088 & 0x200000000000LL) == qword_180015088 )
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
          (__int64)&unk_180011DE8,
          a3,
          a4,
          (__int64)&v31,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)v18,
          (__int64 *)&v30,
          (__int64 *)&v48,
          (__int64)&v29,
          (__int64)&v17,
          (__int64 *)&v46,
          (__int64)&v28,
          (__int64)&v16,
          (__int64 *)&v44,
          (__int64)&v27,
          (__int64)&v15,
          (__int64 *)&v42,
          (__int64)&v26,
          (__int64)&v14,
          (__int64 *)&v40,
          (__int64)&v25,
          (__int64)&v13,
          (__int64 *)&v38,
          (__int64)&v24,
          (__int64)&v12,
          (__int64 *)&v36,
          (__int64)&v23,
          (__int64)&v11,
          (__int64 *)&v34,
          (__int64)&v22,
          (__int64)&v10,
          (__int64 *)&v32,
          (__int64)&v19,
          (__int64)&v9);
      }
      a1[17] = 0;
      a1[18] = 0;
      a1[19].m128i_i64[0] = 0;
    }
    do
      result = FlushLookUpTableBucket((__int64)a1, v5++);
    while ( v5 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x18000bb9c  mov     [rsp-8+arg_8], rbx
0x18000bba1  mov     [rsp-8+arg_10], rsi
0x18000bba6  push    rbp
0x18000bba7  push    rdi
0x18000bba8  push    r14
0x18000bbaa  lea     rbp, [rsp-90h]
0x18000bbb2  sub     rsp, 230h
0x18000bbb9  mov     rax, cs:__security_cookie
0x18000bbc0  xor     rax, rsp
0x18000bbc3  mov     [rbp+0A0h+var_18], rax
0x18000bbca  mov     eax, [rcx+100h]
0x18000bbd0  xor     edi, edi
0x18000bbd2  mov     rbx, rcx
0x18000bbd5  test    eax, eax
0x18000bbd7  jz      loc_18000BF52
0x18000bbdd  cmp     [rcx+128h], eax
0x18000bbe3  ja      short loc_18000BBEE
0x18000bbe5  cmp     [rcx+118h], rdi
0x18000bbec  jnz     short loc_18000BBF4
0x18000bbee  mov     [rcx+128h], eax
0x18000bbf4  cmp     [rcx+124h], eax
0x18000bbfa  jnb     short loc_18000BC02
0x18000bbfc  mov     [rcx+124h], eax
0x18000bc02  mov     esi, 1
0x18000bc07  movq    xmm1, rax
0x18000bc0c  movq    xmm0, rsi
0x18000bc11  lea     r14d, [rsi+1Fh]
0x18000bc15  punpcklqdq xmm1, xmm0
0x18000bc19  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18000bc21  paddq   xmm1, xmm0
0x18000bc25  movdqu  xmmword ptr [rcx+110h], xmm1
0x18000bc2d  cmp     [rcx+110h], rdi
0x18000bc34  jz      loc_18000BF41
0x18000bc3a  mov     eax, cs:dword_180015070
0x18000bc40  cmp     eax, 5
0x18000bc43  jbe     loc_18000BF27
0x18000bc49  mov     rcx, cs:qword_180015088
0x18000bc50  mov     rdx, 200000000000h
0x18000bc5a  mov     rax, cs:qword_180015080
0x18000bc61  test    rdx, rax
0x18000bc64  jz      loc_18000BF27
0x18000bc6a  mov     rax, rcx
0x18000bc6d  and     rax, rdx
0x18000bc70  cmp     rax, rcx
0x18000bc73  jnz     loc_18000BF27
0x18000bc79  lea     ecx, [rsi+29h]
0x18000bc7c  mov     [rbp+0A0h+var_120], 4
0x18000bc80  lea     rax, aSummarycount; "SummaryCount"
0x18000bc87  mov     [rbp+0A0h+var_A0], cx
0x18000bc8b  mov     [rbp+0A0h+var_B8], rax
0x18000bc8f  lea     eax, [rsi+17h]
0x18000bc92  mov     [rbp+0A0h+var_B0], ax
0x18000bc96  mov     eax, [rbx+134h]
0x18000bc9c  mov     [rbp+0A0h+var_108], rax
0x18000bca0  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18000bca7  mov     [rbp+0A0h+var_A8], rax
0x18000bcab  mov     eax, [rbx+130h]
0x18000bcb1  mov     [rbp+0A0h+var_100], rax
0x18000bcb5  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18000bcbc  mov     [rbp+0A0h+var_98], rax
0x18000bcc0  mov     eax, [rbx+12Ch]
0x18000bcc6  mov     [rbp+0A0h+var_F8], rax
0x18000bcca  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18000bcd1  mov     [rbp+0A0h+var_88], rax
0x18000bcd5  mov     eax, [rbx+128h]
0x18000bcdb  mov     [rbp+0A0h+var_F0], rax
0x18000bcdf  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18000bce6  mov     [rbp+0A0h+var_78], rax
0x18000bcea  mov     eax, [rbx+124h]
0x18000bcf0  mov     [rbp+0A0h+var_E8], rax
0x18000bcf4  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18000bcfb  mov     [rbp+0A0h+var_68], rax
0x18000bcff  mov     rax, [rbx+110h]
0x18000bd06  mov     [rbp+0A0h+var_E0], rax
0x18000bd0a  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18000bd11  mov     [rbp+0A0h+var_58], rax
0x18000bd15  lea     eax, [rsi+25h]
0x18000bd18  mov     [rbp+0A0h+var_50], ax
0x18000bd1c  mov     eax, [rbx+120h]
0x18000bd22  mov     [rbp+0A0h+var_D8], rax
0x18000bd26  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18000bd2d  mov     [rbp+0A0h+var_48], rax
0x18000bd31  mov     rax, [rbx+118h]
0x18000bd38  mov     [rbp+0A0h+var_D0], rax
0x18000bd3c  lea     rax, aNumflushes; "NumFlushes"
0x18000bd43  mov     [rbp+0A0h+var_38], rax
0x18000bd47  lea     eax, [rsi+13h]
0x18000bd4a  mov     [rbp+0A0h+var_30], ax
0x18000bd4e  mov     rax, [rbx+148h]
0x18000bd55  mov     [rbp+0A0h+var_90], cx
0x18000bd59  mov     [rbp+0A0h+var_80], cx
0x18000bd5d  lea     ecx, [rsi+21h]
0x18000bd60  mov     [rbp+0A0h+var_114], esi
0x18000bd63  mov     [rbp+0A0h+var_11F], 4
0x18000bd67  mov     [rbp+0A0h+var_11E], 4
0x18000bd6b  mov     [rbp+0A0h+var_11D], 4
0x18000bd6f  mov     [rbp+0A0h+var_11C], 4
0x18000bd73  mov     [rbp+0A0h+var_70], cx
0x18000bd77  mov     [rbp+0A0h+var_11B], 4
0x18000bd7b  mov     [rbp+0A0h+var_60], cx
0x18000bd7f  mov     [rbp+0A0h+var_11A], 4
0x18000bd83  mov     [rbp+0A0h+var_119], 4
0x18000bd87  mov     [rbp+0A0h+var_40], r14w
0x18000bd8c  mov     [rbp+0A0h+var_118], 4
0x18000bd90  mov     rcx, [rax+8]
0x18000bd94  lea     rax, [rbp+0A0h+var_28]
0x18000bd98  mov     [rbp+0A0h+var_C8], rax
0x18000bd9c  lea     rax, [rbp+0A0h+var_120]
0x18000bda0  mov     [rsp+240h+var_128], rax
0x18000bda8  lea     rax, [rbp+0A0h+var_114]
0x18000bdac  mov     [rsp+240h+var_130], rax
0x18000bdb4  lea     rax, [rbp+0A0h+var_B8]
0x18000bdb8  movups  xmm0, xmmword ptr [rcx-10h]
0x18000bdbc  mov     [rsp+240h+var_138], rax
0x18000bdc4  lea     rax, [rbp+0A0h+var_11F]
0x18000bdc8  mov     [rsp+240h+var_140], rax
0x18000bdd0  lea     rax, [rbp+0A0h+var_108]
0x18000bdd4  mov     [rsp+240h+var_148], rax
0x18000bddc  lea     rax, [rbp+0A0h+var_A8]
0x18000bde0  mov     [rsp+240h+var_150], rax
0x18000bde8  lea     rax, [rbp+0A0h+var_11E]
0x18000bdec  movdqu  [rbp+0A0h+var_28], xmm0
0x18000bdf1  mov     [rbp+0A0h+var_117], dil
0x18000bdf5  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x18000bdfc  mov     [rbp+0A0h+var_10C], 12Ch
0x18000be03  mov     [rbp+0A0h+var_C0], 1000000h
0x18000be0b  mov     [rsp+240h+var_158], rax
0x18000be13  lea     rdx, unk_180011DE8
0x18000be1a  lea     rax, [rbp+0A0h+var_100]
0x18000be1e  mov     [rsp+240h+var_160], rax
0x18000be26  lea     rax, [rbp+0A0h+var_98]
0x18000be2a  mov     [rsp+240h+var_168], rax
0x18000be32  lea     rax, [rbp+0A0h+var_11D]
0x18000be36  mov     [rsp+240h+var_170], rax
0x18000be3e  lea     rax, [rbp+0A0h+var_F8]
0x18000be42  mov     [rsp+240h+var_178], rax
0x18000be4a  lea     rax, [rbp+0A0h+var_88]
0x18000be4e  mov     [rsp+240h+var_180], rax
0x18000be56  lea     rax, [rbp+0A0h+var_11C]
0x18000be5a  mov     [rsp+240h+var_188], rax
0x18000be62  lea     rax, [rbp+0A0h+var_F0]
0x18000be66  mov     [rsp+240h+var_190], rax
0x18000be6e  lea     rax, [rbp+0A0h+var_78]
0x18000be72  mov     [rsp+240h+var_198], rax
0x18000be7a  lea     rax, [rbp+0A0h+var_11B]
0x18000be7e  mov     [rsp+240h+var_1A0], rax
0x18000be86  lea     rax, [rbp+0A0h+var_E8]
0x18000be8a  mov     [rsp+240h+var_1A8], rax
0x18000be92  lea     rax, [rbp+0A0h+var_68]
0x18000be96  mov     [rsp+240h+var_1B0], rax
0x18000be9e  lea     rax, [rbp+0A0h+var_11A]
0x18000bea2  mov     [rsp+240h+var_1B8], rax
0x18000beaa  lea     rax, [rbp+0A0h+var_E0]
0x18000beae  mov     [rsp+240h+var_1C0], rax
0x18000beb6  lea     rax, [rbp+0A0h+var_58]
0x18000beba  mov     [rsp+240h+var_1C8], rax
0x18000bebf  lea     rax, [rbp+0A0h+var_119]
0x18000bec3  mov     [rsp+240h+var_1D0], rax
0x18000bec8  lea     rax, [rbp+0A0h+var_D8]
0x18000becc  mov     [rsp+240h+var_1D8], rax
0x18000bed1  lea     rax, [rbp+0A0h+var_48]
0x18000bed5  mov     [rsp+240h+var_1E0], rax
0x18000beda  lea     rax, [rbp+0A0h+var_118]
0x18000bede  mov     [rsp+240h+var_1E8], rax
0x18000bee3  lea     rax, [rbp+0A0h+var_D0]
0x18000bee7  mov     [rsp+240h+var_1F0], rax
0x18000beec  lea     rax, [rbp+0A0h+var_38]
0x18000bef0  mov     [rsp+240h+var_1F8], rax
0x18000bef5  lea     rax, [rbp+0A0h+var_C8]
0x18000bef9  mov     [rsp+240h+var_200], rax
0x18000befe  lea     rax, [rbp+0A0h+var_117]
0x18000bf02  mov     [rsp+240h+var_208], rax
0x18000bf07  lea     rax, [rbp+0A0h+var_110]
0x18000bf0b  mov     [rsp+240h+var_210], rax
0x18000bf10  lea     rax, [rbp+0A0h+var_10C]
0x18000bf14  mov     [rsp+240h+var_218], rax
0x18000bf19  lea     rax, [rbp+0A0h+var_C0]
0x18000bf1d  mov     [rsp+240h+var_220], rax
0x18000bf22  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18000bf27  xorps   xmm0, xmm0
0x18000bf2a  xor     eax, eax
0x18000bf2c  movups  xmmword ptr [rbx+110h], xmm0
0x18000bf33  movups  xmmword ptr [rbx+120h], xmm0
0x18000bf3a  mov     [rbx+130h], rax
0x18000bf41  mov     edx, edi
0x18000bf43  mov     rcx, rbx
0x18000bf46  call    FlushLookUpTableBucket
0x18000bf4b  add     edi, esi
0x18000bf4d  cmp     edi, r14d
0x18000bf50  jb      short loc_18000BF41
0x18000bf52  mov     rcx, [rbp+0A0h+var_18]
0x18000bf59  xor     rcx, rsp; StackCookie
0x18000bf5c  call    __security_check_cookie
0x18000bf61  lea     r11, [rsp+240h+var_10]
0x18000bf69  mov     rbx, [r11+28h]
0x18000bf6d  mov     rsi, [r11+30h]
0x18000bf71  mov     rsp, r11
0x18000bf74  pop     r14
0x18000bf76  pop     rdi
0x18000bf77  pop     rbp
0x18000bf78  retn
```
