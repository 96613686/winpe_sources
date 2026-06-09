# LookUpTableFlushComplete

- ea: `0x18001181c`
- end: `0x180011b8d`
- name: `LookUpTableFlushComplete`
- size: `881`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800117a0`
- `0x18001b020`
- `0x18001b0e0`
- `0x18001b144`

## callees

- `0x180001168`
- `0x180010ed4`
- `0x18001181c`
- `0x180011e24`
- `0x1800136d4`
- `0x18001b7e0`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // r8
  __int64 v4; // r9
  __int64 v5; // rcx
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rax
  __int64 v9; // rcx
  char v10; // [rsp+120h] [rbp-80h] BYREF
  char v11; // [rsp+121h] [rbp-7Fh] BYREF
  char v12; // [rsp+122h] [rbp-7Eh] BYREF
  char v13; // [rsp+123h] [rbp-7Dh] BYREF
  char v14; // [rsp+124h] [rbp-7Ch] BYREF
  char v15; // [rsp+125h] [rbp-7Bh] BYREF
  char v16; // [rsp+126h] [rbp-7Ah] BYREF
  char v17; // [rsp+127h] [rbp-79h] BYREF
  char v18; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v19[3]; // [rsp+129h] [rbp-77h] BYREF
  int v20; // [rsp+12Ch] [rbp-74h] BYREF
  int v21; // [rsp+130h] [rbp-70h] BYREF
  int v22; // [rsp+134h] [rbp-6Ch] BYREF
  __int64 v23; // [rsp+138h] [rbp-68h] BYREF
  __int64 v24; // [rsp+140h] [rbp-60h] BYREF
  __int64 v25; // [rsp+148h] [rbp-58h] BYREF
  __int64 v26; // [rsp+150h] [rbp-50h] BYREF
  __int64 v27; // [rsp+158h] [rbp-48h] BYREF
  __int64 v28; // [rsp+160h] [rbp-40h] BYREF
  __int64 v29; // [rsp+168h] [rbp-38h] BYREF
  __int64 v30; // [rsp+170h] [rbp-30h] BYREF
  __int128 *v31; // [rsp+178h] [rbp-28h] BYREF
  __int64 v32; // [rsp+180h] [rbp-20h] BYREF
  const wchar_t *v33; // [rsp+188h] [rbp-18h] BYREF
  __int16 v34; // [rsp+190h] [rbp-10h]
  const wchar_t *v35; // [rsp+198h] [rbp-8h] BYREF
  __int16 v36; // [rsp+1A0h] [rbp+0h]
  const wchar_t *v37; // [rsp+1A8h] [rbp+8h] BYREF
  __int16 v38; // [rsp+1B0h] [rbp+10h]
  const wchar_t *v39; // [rsp+1B8h] [rbp+18h] BYREF
  __int16 v40; // [rsp+1C0h] [rbp+20h]
  const wchar_t *v41; // [rsp+1C8h] [rbp+28h] BYREF
  __int16 v42; // [rsp+1D0h] [rbp+30h]
  const wchar_t *v43; // [rsp+1D8h] [rbp+38h] BYREF
  __int16 v44; // [rsp+1E0h] [rbp+40h]
  const wchar_t *v45; // [rsp+1E8h] [rbp+48h] BYREF
  __int16 v46; // [rsp+1F0h] [rbp+50h]
  const wchar_t *v47; // [rsp+1F8h] [rbp+58h] BYREF
  __int16 v48; // [rsp+200h] [rbp+60h]
  const wchar_t *v49; // [rsp+208h] [rbp+68h] BYREF
  __int16 v50; // [rsp+210h] [rbp+70h]
  __int128 v51; // [rsp+218h] [rbp+78h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    UpdateInternalStatsOnFlush();
    if ( *(_QWORD *)(v5 + 272) )
    {
      if ( (unsigned int)dword_180024088 > 5
        && (unsigned __int8)tlgKeywordOn(&dword_180024088, 0x200000000000LL, v3, v4) )
      {
        v10 = 4;
        v36 = 42;
        v33 = L"SummaryCount";
        v34 = 24;
        v23 = *(unsigned int *)(a1 + 308);
        v35 = L"NumLargeEventFailures";
        v24 = *(unsigned int *)(a1 + 304);
        v37 = L"NumAllocationFailures";
        v25 = *(unsigned int *)(a1 + 300);
        v39 = L"NumBucketLimitReached";
        v26 = *(unsigned int *)(a1 + 296);
        v41 = L"MinEntriesFlushed";
        v27 = *(unsigned int *)(a1 + 292);
        v43 = L"MaxEntriesFlushed";
        v28 = *(_QWORD *)(a1 + 272);
        v45 = L"TotalEntriesFlushed";
        v46 = 38;
        v29 = *(unsigned int *)(a1 + 288);
        v47 = L"MaxEntriesStored";
        v30 = *(_QWORD *)(a1 + 280);
        v49 = L"NumFlushes";
        v50 = 20;
        v8 = *(_QWORD *)(a1 + 328);
        v38 = 42;
        v40 = 42;
        v20 = 1;
        v11 = 4;
        v12 = 4;
        v13 = 4;
        v14 = 4;
        v42 = 34;
        v15 = 4;
        v44 = 34;
        v16 = 4;
        v17 = 4;
        v48 = 32;
        v18 = 4;
        v9 = *(_QWORD *)(v8 + 8);
        v31 = &v51;
        v51 = *(_OWORD *)(v9 - 16);
        v19[0] = 0;
        v21 = -1;
        v22 = 300;
        v32 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v9,
          (unsigned int)&word_18001F9C6,
          v6,
          v7,
          (__int64)&v32,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)v19,
          (__int64)&v31,
          (__int64)&v49,
          (__int64)&v30,
          (__int64)&v18,
          (__int64)&v47,
          (__int64)&v29,
          (__int64)&v17,
          (__int64)&v45,
          (__int64)&v28,
          (__int64)&v16,
          (__int64)&v43,
          (__int64)&v27,
          (__int64)&v15,
          (__int64)&v41,
          (__int64)&v26,
          (__int64)&v14,
          (__int64)&v39,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v37,
          (__int64)&v24,
          (__int64)&v12,
          (__int64)&v35,
          (__int64)&v23,
          (__int64)&v11,
          (__int64)&v33,
          (__int64)&v20,
          (__int64)&v10);
      }
      *(_OWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 304) = 0;
    }
    do
      FlushLookUpTableBucket(a1, v1++);
    while ( v1 < 0x20 );
  }
}

```

## disassembly

```asm
0x18001181c  push    rbp
0x18001181e  push    rbx
0x18001181f  push    rsi
0x180011820  push    rdi
0x180011821  lea     rbp, [rsp-98h]
0x180011829  sub     rsp, 238h
0x180011830  mov     rax, cs:__security_cookie
0x180011837  xor     rax, rsp
0x18001183a  mov     [rbp+0B0h+var_28], rax
0x180011841  mov     edx, [rcx+100h]
0x180011847  xor     edi, edi
0x180011849  mov     rbx, rcx
0x18001184c  test    edx, edx
0x18001184e  jz      loc_180011B71
0x180011854  call    UpdateInternalStatsOnFlush
0x180011859  lea     esi, [rdi+20h]
0x18001185c  cmp     [rcx+110h], rdi
0x180011863  jz      loc_180011B61
0x180011869  mov     eax, cs:dword_180024088
0x18001186f  cmp     eax, 5
0x180011872  jbe     loc_180011B47
0x180011878  mov     rdx, 200000000000h
0x180011882  lea     rcx, dword_180024088
0x180011889  call    _tlgKeywordOn
0x18001188e  test    al, al
0x180011890  jz      loc_180011B47
0x180011896  lea     ecx, [rdi+2Ah]
0x180011899  mov     [rbp+0B0h+var_130], 4
0x18001189d  lea     rax, aSummarycount; "SummaryCount"
0x1800118a4  mov     [rbp+0B0h+var_B0], cx
0x1800118a8  mov     [rbp+0B0h+var_C8], rax
0x1800118ac  lea     eax, [rdi+18h]
0x1800118af  mov     [rbp+0B0h+var_C0], ax
0x1800118b3  mov     eax, [rbx+134h]
0x1800118b9  mov     [rbp+0B0h+var_118], rax
0x1800118bd  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x1800118c4  mov     [rbp+0B0h+var_B8], rax
0x1800118c8  mov     eax, [rbx+130h]
0x1800118ce  mov     [rbp+0B0h+var_110], rax
0x1800118d2  lea     rax, aNumallocationf; "NumAllocationFailures"
0x1800118d9  mov     [rbp+0B0h+var_A8], rax
0x1800118dd  mov     eax, [rbx+12Ch]
0x1800118e3  mov     [rbp+0B0h+var_108], rax
0x1800118e7  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x1800118ee  mov     [rbp+0B0h+var_98], rax
0x1800118f2  mov     eax, [rbx+128h]
0x1800118f8  mov     [rbp+0B0h+var_100], rax
0x1800118fc  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180011903  mov     [rbp+0B0h+var_88], rax
0x180011907  mov     eax, [rbx+124h]
0x18001190d  mov     [rbp+0B0h+var_F8], rax
0x180011911  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x180011918  mov     [rbp+0B0h+var_78], rax
0x18001191c  mov     rax, [rbx+110h]
0x180011923  mov     [rbp+0B0h+var_F0], rax
0x180011927  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18001192e  mov     [rbp+0B0h+var_68], rax
0x180011932  lea     eax, [rdi+26h]
0x180011935  mov     [rbp+0B0h+var_60], ax
0x180011939  mov     eax, [rbx+120h]
0x18001193f  mov     [rbp+0B0h+var_E8], rax
0x180011943  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18001194a  mov     [rbp+0B0h+var_58], rax
0x18001194e  mov     rax, [rbx+118h]
0x180011955  mov     [rbp+0B0h+var_E0], rax
0x180011959  lea     rax, aNumflushes; "NumFlushes"
0x180011960  mov     [rbp+0B0h+var_48], rax
0x180011964  lea     eax, [rdi+14h]
0x180011967  mov     [rbp+0B0h+var_40], ax
0x18001196b  mov     rax, [rbx+148h]
0x180011972  mov     [rbp+0B0h+var_A0], cx
0x180011976  mov     [rbp+0B0h+var_90], cx
0x18001197a  lea     ecx, [rdi+22h]
0x18001197d  mov     [rbp+0B0h+var_124], 1
0x180011984  mov     [rbp+0B0h+var_12F], 4
0x180011988  mov     [rbp+0B0h+var_12E], 4
0x18001198c  mov     [rbp+0B0h+var_12D], 4
0x180011990  mov     [rbp+0B0h+var_12C], 4
0x180011994  mov     [rbp+0B0h+var_80], cx
0x180011998  mov     [rbp+0B0h+var_12B], 4
0x18001199c  mov     [rbp+0B0h+var_70], cx
0x1800119a0  mov     [rbp+0B0h+var_12A], 4
0x1800119a4  mov     [rbp+0B0h+var_129], 4
0x1800119a8  mov     [rbp+0B0h+var_50], si
0x1800119ac  mov     [rbp+0B0h+var_128], 4
0x1800119b0  mov     rcx, [rax+8]
0x1800119b4  lea     rax, [rbp+0B0h+var_38]
0x1800119b8  mov     [rbp+0B0h+var_D8], rax
0x1800119bc  lea     rax, [rbp+0B0h+var_130]
0x1800119c0  mov     [rsp+250h+var_138], rax
0x1800119c8  lea     rax, [rbp+0B0h+var_124]
0x1800119cc  mov     [rsp+250h+var_140], rax
0x1800119d4  lea     rax, [rbp+0B0h+var_C8]
0x1800119d8  movups  xmm0, xmmword ptr [rcx-10h]
0x1800119dc  mov     [rsp+250h+var_148], rax
0x1800119e4  lea     rax, [rbp+0B0h+var_12F]
0x1800119e8  mov     [rsp+250h+var_150], rax
0x1800119f0  lea     rax, [rbp+0B0h+var_118]
0x1800119f4  mov     [rsp+250h+var_158], rax
0x1800119fc  lea     rax, [rbp+0B0h+var_B8]
0x180011a00  mov     [rsp+250h+var_160], rax
0x180011a08  lea     rax, [rbp+0B0h+var_12E]
0x180011a0c  movdqu  [rbp+0B0h+var_38], xmm0
0x180011a11  mov     [rbp+0B0h+var_127], dil
0x180011a15  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x180011a1c  mov     [rbp+0B0h+var_11C], 12Ch
0x180011a23  mov     [rbp+0B0h+var_D0], 1000000h
0x180011a2b  mov     [rsp+250h+var_168], rax
0x180011a33  lea     rdx, word_18001F9C6
0x180011a3a  lea     rax, [rbp+0B0h+var_110]
0x180011a3e  mov     [rsp+250h+var_170], rax
0x180011a46  lea     rax, [rbp+0B0h+var_A8]
0x180011a4a  mov     [rsp+250h+var_178], rax
0x180011a52  lea     rax, [rbp+0B0h+var_12D]
0x180011a56  mov     [rsp+250h+var_180], rax
0x180011a5e  lea     rax, [rbp+0B0h+var_108]
0x180011a62  mov     [rsp+250h+var_188], rax
0x180011a6a  lea     rax, [rbp+0B0h+var_98]
0x180011a6e  mov     [rsp+250h+var_190], rax
0x180011a76  lea     rax, [rbp+0B0h+var_12C]
0x180011a7a  mov     [rsp+250h+var_198], rax
0x180011a82  lea     rax, [rbp+0B0h+var_100]
0x180011a86  mov     [rsp+250h+var_1A0], rax
0x180011a8e  lea     rax, [rbp+0B0h+var_88]
0x180011a92  mov     [rsp+250h+var_1A8], rax
0x180011a9a  lea     rax, [rbp+0B0h+var_12B]
0x180011a9e  mov     [rsp+250h+var_1B0], rax
0x180011aa6  lea     rax, [rbp+0B0h+var_F8]
0x180011aaa  mov     [rsp+250h+var_1B8], rax
0x180011ab2  lea     rax, [rbp+0B0h+var_78]
0x180011ab6  mov     [rsp+250h+var_1C0], rax
0x180011abe  lea     rax, [rbp+0B0h+var_12A]
0x180011ac2  mov     [rsp+250h+var_1C8], rax
0x180011aca  lea     rax, [rbp+0B0h+var_F0]
0x180011ace  mov     [rsp+250h+var_1D0], rax
0x180011ad6  lea     rax, [rbp+0B0h+var_68]
0x180011ada  mov     [rsp+250h+var_1D8], rax
0x180011adf  lea     rax, [rbp+0B0h+var_129]
0x180011ae3  mov     [rsp+250h+var_1E0], rax
0x180011ae8  lea     rax, [rbp+0B0h+var_E8]
0x180011aec  mov     [rsp+250h+var_1E8], rax
0x180011af1  lea     rax, [rbp+0B0h+var_58]
0x180011af5  mov     [rsp+250h+var_1F0], rax
0x180011afa  lea     rax, [rbp+0B0h+var_128]
0x180011afe  mov     [rsp+250h+var_1F8], rax
0x180011b03  lea     rax, [rbp+0B0h+var_E0]
0x180011b07  mov     [rsp+250h+var_200], rax
0x180011b0c  lea     rax, [rbp+0B0h+var_48]
0x180011b10  mov     [rsp+250h+var_208], rax
0x180011b15  lea     rax, [rbp+0B0h+var_D8]
0x180011b19  mov     [rsp+250h+var_210], rax
0x180011b1e  lea     rax, [rbp+0B0h+var_127]
0x180011b22  mov     [rsp+250h+var_218], rax
0x180011b27  lea     rax, [rbp+0B0h+var_120]
0x180011b2b  mov     [rsp+250h+var_220], rax
0x180011b30  lea     rax, [rbp+0B0h+var_11C]
0x180011b34  mov     [rsp+250h+var_228], rax
0x180011b39  lea     rax, [rbp+0B0h+var_D0]
0x180011b3d  mov     [rsp+250h+var_230], rax
0x180011b42  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180011b47  xorps   xmm0, xmm0
0x180011b4a  xor     eax, eax
0x180011b4c  movups  xmmword ptr [rbx+110h], xmm0
0x180011b53  movups  xmmword ptr [rbx+120h], xmm0
0x180011b5a  mov     [rbx+130h], rax
0x180011b61  mov     edx, edi
0x180011b63  mov     rcx, rbx
0x180011b66  call    FlushLookUpTableBucket
0x180011b6b  inc     edi
0x180011b6d  cmp     edi, esi
0x180011b6f  jb      short loc_180011B61
0x180011b71  mov     rcx, [rbp+0B0h+var_28]
0x180011b78  xor     rcx, rsp; StackCookie
0x180011b7b  call    __security_check_cookie
0x180011b80  add     rsp, 238h
0x180011b87  pop     rdi
0x180011b88  pop     rsi
0x180011b89  pop     rbx
0x180011b8a  pop     rbp
0x180011b8b  retn
```
