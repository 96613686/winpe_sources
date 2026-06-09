# LookUpTableFlushComplete

- ea: `0x18001639c`
- end: `0x180016779`
- name: `LookUpTableFlushComplete`
- size: `989`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015774`
- `0x180016020`
- `0x180016810`
- `0x180016870`
- `0x1800169fc`

## callees

- `0x180001a9c`
- `0x1800026f0`
- `0x180015ef8`
- `0x18001639c`

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
      if ( (unsigned int)dword_1800253B8 > 5
        && (qword_1800253C8 & 0x200000000000LL) != 0
        && (qword_1800253D0 & 0x200000000000LL) == qword_1800253D0 )
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
          (__int64)&dword_18001FE34,
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
      result = FlushLookUpTableBucket(a1, v5++);
    while ( v5 < 0x20 );
  }
  return result;
}

```

## disassembly

```asm
0x18001639c  mov     [rsp-8+arg_8], rbx
0x1800163a1  mov     [rsp-8+arg_10], rsi
0x1800163a6  push    rbp
0x1800163a7  push    rdi
0x1800163a8  push    r14
0x1800163aa  lea     rbp, [rsp-90h]
0x1800163b2  sub     rsp, 230h
0x1800163b9  mov     rax, cs:__security_cookie
0x1800163c0  xor     rax, rsp
0x1800163c3  mov     [rbp+0A0h+var_18], rax
0x1800163ca  mov     eax, [rcx+100h]
0x1800163d0  xor     edi, edi
0x1800163d2  mov     rbx, rcx
0x1800163d5  test    eax, eax
0x1800163d7  jz      loc_180016752
0x1800163dd  cmp     [rcx+128h], eax
0x1800163e3  ja      short loc_1800163EE
0x1800163e5  cmp     [rcx+118h], rdi
0x1800163ec  jnz     short loc_1800163F4
0x1800163ee  mov     [rcx+128h], eax
0x1800163f4  cmp     [rcx+124h], eax
0x1800163fa  jnb     short loc_180016402
0x1800163fc  mov     [rcx+124h], eax
0x180016402  mov     esi, 1
0x180016407  movq    xmm1, rax
0x18001640c  movq    xmm0, rsi
0x180016411  lea     r14d, [rsi+1Fh]
0x180016415  punpcklqdq xmm1, xmm0
0x180016419  movdqu  xmm0, xmmword ptr [rcx+110h]
0x180016421  paddq   xmm1, xmm0
0x180016425  movdqu  xmmword ptr [rcx+110h], xmm1
0x18001642d  cmp     [rcx+110h], rdi
0x180016434  jz      loc_180016741
0x18001643a  mov     eax, cs:dword_1800253B8
0x180016440  cmp     eax, 5
0x180016443  jbe     loc_180016727
0x180016449  mov     rcx, cs:qword_1800253D0
0x180016450  mov     rdx, 200000000000h
0x18001645a  mov     rax, cs:qword_1800253C8
0x180016461  test    rdx, rax
0x180016464  jz      loc_180016727
0x18001646a  mov     rax, rcx
0x18001646d  and     rax, rdx
0x180016470  cmp     rax, rcx
0x180016473  jnz     loc_180016727
0x180016479  lea     ecx, [rsi+29h]
0x18001647c  mov     [rbp+0A0h+var_120], 4
0x180016480  lea     rax, aSummarycount; "SummaryCount"
0x180016487  mov     [rbp+0A0h+var_A0], cx
0x18001648b  mov     [rbp+0A0h+var_B8], rax
0x18001648f  lea     eax, [rsi+17h]
0x180016492  mov     [rbp+0A0h+var_B0], ax
0x180016496  mov     eax, [rbx+134h]
0x18001649c  mov     [rbp+0A0h+var_108], rax
0x1800164a0  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x1800164a7  mov     [rbp+0A0h+var_A8], rax
0x1800164ab  mov     eax, [rbx+130h]
0x1800164b1  mov     [rbp+0A0h+var_100], rax
0x1800164b5  lea     rax, aNumallocationf; "NumAllocationFailures"
0x1800164bc  mov     [rbp+0A0h+var_98], rax
0x1800164c0  mov     eax, [rbx+12Ch]
0x1800164c6  mov     [rbp+0A0h+var_F8], rax
0x1800164ca  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x1800164d1  mov     [rbp+0A0h+var_88], rax
0x1800164d5  mov     eax, [rbx+128h]
0x1800164db  mov     [rbp+0A0h+var_F0], rax
0x1800164df  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x1800164e6  mov     [rbp+0A0h+var_78], rax
0x1800164ea  mov     eax, [rbx+124h]
0x1800164f0  mov     [rbp+0A0h+var_E8], rax
0x1800164f4  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x1800164fb  mov     [rbp+0A0h+var_68], rax
0x1800164ff  mov     rax, [rbx+110h]
0x180016506  mov     [rbp+0A0h+var_E0], rax
0x18001650a  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180016511  mov     [rbp+0A0h+var_58], rax
0x180016515  lea     eax, [rsi+25h]
0x180016518  mov     [rbp+0A0h+var_50], ax
0x18001651c  mov     eax, [rbx+120h]
0x180016522  mov     [rbp+0A0h+var_D8], rax
0x180016526  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18001652d  mov     [rbp+0A0h+var_48], rax
0x180016531  mov     rax, [rbx+118h]
0x180016538  mov     [rbp+0A0h+var_D0], rax
0x18001653c  lea     rax, aNumflushes; "NumFlushes"
0x180016543  mov     [rbp+0A0h+var_38], rax
0x180016547  lea     eax, [rsi+13h]
0x18001654a  mov     [rbp+0A0h+var_30], ax
0x18001654e  mov     rax, [rbx+148h]
0x180016555  mov     [rbp+0A0h+var_90], cx
0x180016559  mov     [rbp+0A0h+var_80], cx
0x18001655d  lea     ecx, [rsi+21h]
0x180016560  mov     [rbp+0A0h+var_114], esi
0x180016563  mov     [rbp+0A0h+var_11F], 4
0x180016567  mov     [rbp+0A0h+var_11E], 4
0x18001656b  mov     [rbp+0A0h+var_11D], 4
0x18001656f  mov     [rbp+0A0h+var_11C], 4
0x180016573  mov     [rbp+0A0h+var_70], cx
0x180016577  mov     [rbp+0A0h+var_11B], 4
0x18001657b  mov     [rbp+0A0h+var_60], cx
0x18001657f  mov     [rbp+0A0h+var_11A], 4
0x180016583  mov     [rbp+0A0h+var_119], 4
0x180016587  mov     [rbp+0A0h+var_40], r14w
0x18001658c  mov     [rbp+0A0h+var_118], 4
0x180016590  mov     rcx, [rax+8]
0x180016594  lea     rax, [rbp+0A0h+var_28]
0x180016598  mov     [rbp+0A0h+var_C8], rax
0x18001659c  lea     rax, [rbp+0A0h+var_120]
0x1800165a0  mov     [rsp+240h+var_128], rax
0x1800165a8  lea     rax, [rbp+0A0h+var_114]
0x1800165ac  mov     [rsp+240h+var_130], rax
0x1800165b4  lea     rax, [rbp+0A0h+var_B8]
0x1800165b8  movups  xmm0, xmmword ptr [rcx-10h]
0x1800165bc  mov     [rsp+240h+var_138], rax
0x1800165c4  lea     rax, [rbp+0A0h+var_11F]
0x1800165c8  mov     [rsp+240h+var_140], rax
0x1800165d0  lea     rax, [rbp+0A0h+var_108]
0x1800165d4  mov     [rsp+240h+var_148], rax
0x1800165dc  lea     rax, [rbp+0A0h+var_A8]
0x1800165e0  mov     [rsp+240h+var_150], rax
0x1800165e8  lea     rax, [rbp+0A0h+var_11E]
0x1800165ec  movdqu  [rbp+0A0h+var_28], xmm0
0x1800165f1  mov     [rbp+0A0h+var_117], dil
0x1800165f5  mov     [rbp+0A0h+var_110], 0FFFFFFFFh
0x1800165fc  mov     [rbp+0A0h+var_10C], 12Ch
0x180016603  mov     [rbp+0A0h+var_C0], 1000000h
0x18001660b  mov     [rsp+240h+var_158], rax
0x180016613  lea     rdx, dword_18001FE34
0x18001661a  lea     rax, [rbp+0A0h+var_100]
0x18001661e  mov     [rsp+240h+var_160], rax
0x180016626  lea     rax, [rbp+0A0h+var_98]
0x18001662a  mov     [rsp+240h+var_168], rax
0x180016632  lea     rax, [rbp+0A0h+var_11D]
0x180016636  mov     [rsp+240h+var_170], rax
0x18001663e  lea     rax, [rbp+0A0h+var_F8]
0x180016642  mov     [rsp+240h+var_178], rax
0x18001664a  lea     rax, [rbp+0A0h+var_88]
0x18001664e  mov     [rsp+240h+var_180], rax
0x180016656  lea     rax, [rbp+0A0h+var_11C]
0x18001665a  mov     [rsp+240h+var_188], rax
0x180016662  lea     rax, [rbp+0A0h+var_F0]
0x180016666  mov     [rsp+240h+var_190], rax
0x18001666e  lea     rax, [rbp+0A0h+var_78]
0x180016672  mov     [rsp+240h+var_198], rax
0x18001667a  lea     rax, [rbp+0A0h+var_11B]
0x18001667e  mov     [rsp+240h+var_1A0], rax
0x180016686  lea     rax, [rbp+0A0h+var_E8]
0x18001668a  mov     [rsp+240h+var_1A8], rax
0x180016692  lea     rax, [rbp+0A0h+var_68]
0x180016696  mov     [rsp+240h+var_1B0], rax
0x18001669e  lea     rax, [rbp+0A0h+var_11A]
0x1800166a2  mov     [rsp+240h+var_1B8], rax
0x1800166aa  lea     rax, [rbp+0A0h+var_E0]
0x1800166ae  mov     [rsp+240h+var_1C0], rax
0x1800166b6  lea     rax, [rbp+0A0h+var_58]
0x1800166ba  mov     [rsp+240h+var_1C8], rax
0x1800166bf  lea     rax, [rbp+0A0h+var_119]
0x1800166c3  mov     [rsp+240h+var_1D0], rax
0x1800166c8  lea     rax, [rbp+0A0h+var_D8]
0x1800166cc  mov     [rsp+240h+var_1D8], rax
0x1800166d1  lea     rax, [rbp+0A0h+var_48]
0x1800166d5  mov     [rsp+240h+var_1E0], rax
0x1800166da  lea     rax, [rbp+0A0h+var_118]
0x1800166de  mov     [rsp+240h+var_1E8], rax
0x1800166e3  lea     rax, [rbp+0A0h+var_D0]
0x1800166e7  mov     [rsp+240h+var_1F0], rax
0x1800166ec  lea     rax, [rbp+0A0h+var_38]
0x1800166f0  mov     [rsp+240h+var_1F8], rax
0x1800166f5  lea     rax, [rbp+0A0h+var_C8]
0x1800166f9  mov     [rsp+240h+var_200], rax
0x1800166fe  lea     rax, [rbp+0A0h+var_117]
0x180016702  mov     [rsp+240h+var_208], rax
0x180016707  lea     rax, [rbp+0A0h+var_110]
0x18001670b  mov     [rsp+240h+var_210], rax
0x180016710  lea     rax, [rbp+0A0h+var_10C]
0x180016714  mov     [rsp+240h+var_218], rax
0x180016719  lea     rax, [rbp+0A0h+var_C0]
0x18001671d  mov     [rsp+240h+var_220], rax
0x180016722  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180016727  xorps   xmm0, xmm0
0x18001672a  xor     eax, eax
0x18001672c  movups  xmmword ptr [rbx+110h], xmm0
0x180016733  movups  xmmword ptr [rbx+120h], xmm0
0x18001673a  mov     [rbx+130h], rax
0x180016741  mov     edx, edi
0x180016743  mov     rcx, rbx
0x180016746  call    FlushLookUpTableBucket
0x18001674b  add     edi, esi
0x18001674d  cmp     edi, r14d
0x180016750  jb      short loc_180016741
0x180016752  mov     rcx, [rbp+0A0h+var_18]
0x180016759  xor     rcx, rsp; StackCookie
0x18001675c  call    __security_check_cookie
0x180016761  lea     r11, [rsp+240h+var_10]
0x180016769  mov     rbx, [r11+28h]
0x18001676d  mov     rsi, [r11+30h]
0x180016771  mov     rsp, r11
0x180016774  pop     r14
0x180016776  pop     rdi
0x180016777  pop     rbp
0x180016778  retn
```
