# LookUpTableFlushComplete

- ea: `0x180025ff4`
- end: `0x180026364`
- name: `LookUpTableFlushComplete`
- size: `880`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025d00`
- `0x180026500`
- `0x180026560`
- `0x180026720`

## callees

- `0x1800010b0`
- `0x180002ea0`
- `0x1800050f0`
- `0x180025c48`
- `0x180025ff4`
- `0x1800265d8`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // rcx
  char v8; // [rsp+120h] [rbp-80h] BYREF
  char v9; // [rsp+121h] [rbp-7Fh] BYREF
  char v10; // [rsp+122h] [rbp-7Eh] BYREF
  char v11; // [rsp+123h] [rbp-7Dh] BYREF
  char v12; // [rsp+124h] [rbp-7Ch] BYREF
  char v13; // [rsp+125h] [rbp-7Bh] BYREF
  char v14; // [rsp+126h] [rbp-7Ah] BYREF
  char v15; // [rsp+127h] [rbp-79h] BYREF
  char v16; // [rsp+128h] [rbp-78h] BYREF
  _BYTE v17[3]; // [rsp+129h] [rbp-77h] BYREF
  int v18; // [rsp+12Ch] [rbp-74h] BYREF
  int v19; // [rsp+130h] [rbp-70h] BYREF
  int v20; // [rsp+134h] [rbp-6Ch] BYREF
  __int64 v21; // [rsp+138h] [rbp-68h] BYREF
  __int64 v22; // [rsp+140h] [rbp-60h] BYREF
  __int64 v23; // [rsp+148h] [rbp-58h] BYREF
  __int64 v24; // [rsp+150h] [rbp-50h] BYREF
  __int64 v25; // [rsp+158h] [rbp-48h] BYREF
  __int64 v26; // [rsp+160h] [rbp-40h] BYREF
  __int64 v27; // [rsp+168h] [rbp-38h] BYREF
  __int64 v28; // [rsp+170h] [rbp-30h] BYREF
  __int128 *v29; // [rsp+178h] [rbp-28h] BYREF
  __int64 v30; // [rsp+180h] [rbp-20h] BYREF
  const wchar_t *v31; // [rsp+188h] [rbp-18h] BYREF
  __int16 v32; // [rsp+190h] [rbp-10h]
  const wchar_t *v33; // [rsp+198h] [rbp-8h] BYREF
  __int16 v34; // [rsp+1A0h] [rbp+0h]
  const wchar_t *v35; // [rsp+1A8h] [rbp+8h] BYREF
  __int16 v36; // [rsp+1B0h] [rbp+10h]
  const wchar_t *v37; // [rsp+1B8h] [rbp+18h] BYREF
  __int16 v38; // [rsp+1C0h] [rbp+20h]
  const wchar_t *v39; // [rsp+1C8h] [rbp+28h] BYREF
  __int16 v40; // [rsp+1D0h] [rbp+30h]
  const wchar_t *v41; // [rsp+1D8h] [rbp+38h] BYREF
  __int16 v42; // [rsp+1E0h] [rbp+40h]
  const wchar_t *v43; // [rsp+1E8h] [rbp+48h] BYREF
  __int16 v44; // [rsp+1F0h] [rbp+50h]
  const wchar_t *v45; // [rsp+1F8h] [rbp+58h] BYREF
  __int16 v46; // [rsp+200h] [rbp+60h]
  const wchar_t *v47; // [rsp+208h] [rbp+68h] BYREF
  __int16 v48; // [rsp+210h] [rbp+70h]
  __int128 v49; // [rsp+218h] [rbp+78h] BYREF

  v1 = 0;
  if ( *(_DWORD *)(a1 + 256) )
  {
    UpdateInternalStatsOnFlush();
    if ( *(_QWORD *)(v3 + 272) )
    {
      if ( (unsigned int)dword_180040080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040080, 0x200000000000LL) )
      {
        v8 = 4;
        v34 = 42;
        v31 = L"SummaryCount";
        v32 = 24;
        v21 = *(unsigned int *)(a1 + 308);
        v33 = L"NumLargeEventFailures";
        v22 = *(unsigned int *)(a1 + 304);
        v35 = L"NumAllocationFailures";
        v23 = *(unsigned int *)(a1 + 300);
        v37 = L"NumBucketLimitReached";
        v24 = *(unsigned int *)(a1 + 296);
        v39 = L"MinEntriesFlushed";
        v25 = *(unsigned int *)(a1 + 292);
        v41 = L"MaxEntriesFlushed";
        v26 = *(_QWORD *)(a1 + 272);
        v43 = L"TotalEntriesFlushed";
        v44 = 38;
        v27 = *(unsigned int *)(a1 + 288);
        v45 = L"MaxEntriesStored";
        v28 = *(_QWORD *)(a1 + 280);
        v47 = L"NumFlushes";
        v48 = 20;
        v6 = *(_QWORD *)(a1 + 328);
        v36 = 42;
        v38 = 42;
        v18 = 1;
        v9 = 4;
        v10 = 4;
        v11 = 4;
        v12 = 4;
        v40 = 34;
        v13 = 4;
        v42 = 34;
        v14 = 4;
        v15 = 4;
        v46 = 32;
        v16 = 4;
        v7 = *(_QWORD *)(v6 + 8);
        v29 = &v49;
        v49 = *(_OWORD *)(v7 - 16);
        v17[0] = 0;
        v19 = -1;
        v20 = 300;
        v30 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (__int64)byte_180038549,
          v4,
          v5,
          (__int64)&v30,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v17,
          (__int64 *)&v29,
          (__int64 *)&v47,
          (__int64)&v28,
          (__int64)&v16,
          (__int64 *)&v45,
          (__int64)&v27,
          (__int64)&v15,
          (__int64 *)&v43,
          (__int64)&v26,
          (__int64)&v14,
          (__int64 *)&v41,
          (__int64)&v25,
          (__int64)&v13,
          (__int64 *)&v39,
          (__int64)&v24,
          (__int64)&v12,
          (__int64 *)&v37,
          (__int64)&v23,
          (__int64)&v11,
          (__int64 *)&v35,
          (__int64)&v22,
          (__int64)&v10,
          (__int64 *)&v33,
          (__int64)&v21,
          (__int64)&v9,
          (__int64 *)&v31,
          (__int64)&v18,
          (__int64)&v8);
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
0x180025ff4  push    rbp
0x180025ff6  push    rbx
0x180025ff7  push    rsi
0x180025ff8  push    rdi
0x180025ff9  lea     rbp, [rsp-98h]
0x180026001  sub     rsp, 238h
0x180026008  mov     rax, cs:__security_cookie
0x18002600f  xor     rax, rsp
0x180026012  mov     [rbp+0B0h+var_28], rax
0x180026019  mov     edx, [rcx+100h]
0x18002601f  xor     edi, edi
0x180026021  mov     rbx, rcx
0x180026024  test    edx, edx
0x180026026  jz      loc_180026349
0x18002602c  call    UpdateInternalStatsOnFlush
0x180026031  lea     esi, [rdi+20h]
0x180026034  cmp     [rcx+110h], rdi
0x18002603b  jz      loc_180026339
0x180026041  mov     eax, cs:dword_180040080
0x180026047  cmp     eax, 5
0x18002604a  jbe     loc_18002631F
0x180026050  mov     rdx, 200000000000h
0x18002605a  lea     rcx, dword_180040080
0x180026061  call    _tlgKeywordOn
0x180026066  test    al, al
0x180026068  jz      loc_18002631F
0x18002606e  lea     ecx, [rdi+2Ah]
0x180026071  mov     [rbp+0B0h+var_130], 4
0x180026075  lea     rax, aSummarycount; "SummaryCount"
0x18002607c  mov     [rbp+0B0h+var_B0], cx
0x180026080  mov     [rbp+0B0h+var_C8], rax
0x180026084  lea     eax, [rdi+18h]
0x180026087  mov     [rbp+0B0h+var_C0], ax
0x18002608b  mov     eax, [rbx+134h]
0x180026091  mov     [rbp+0B0h+var_118], rax
0x180026095  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18002609c  mov     [rbp+0B0h+var_B8], rax
0x1800260a0  mov     eax, [rbx+130h]
0x1800260a6  mov     [rbp+0B0h+var_110], rax
0x1800260aa  lea     rax, aNumallocationf; "NumAllocationFailures"
0x1800260b1  mov     [rbp+0B0h+var_A8], rax
0x1800260b5  mov     eax, [rbx+12Ch]
0x1800260bb  mov     [rbp+0B0h+var_108], rax
0x1800260bf  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x1800260c6  mov     [rbp+0B0h+var_98], rax
0x1800260ca  mov     eax, [rbx+128h]
0x1800260d0  mov     [rbp+0B0h+var_100], rax
0x1800260d4  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x1800260db  mov     [rbp+0B0h+var_88], rax
0x1800260df  mov     eax, [rbx+124h]
0x1800260e5  mov     [rbp+0B0h+var_F8], rax
0x1800260e9  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x1800260f0  mov     [rbp+0B0h+var_78], rax
0x1800260f4  mov     rax, [rbx+110h]
0x1800260fb  mov     [rbp+0B0h+var_F0], rax
0x1800260ff  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180026106  mov     [rbp+0B0h+var_68], rax
0x18002610a  lea     eax, [rdi+26h]
0x18002610d  mov     [rbp+0B0h+var_60], ax
0x180026111  mov     eax, [rbx+120h]
0x180026117  mov     [rbp+0B0h+var_E8], rax
0x18002611b  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x180026122  mov     [rbp+0B0h+var_58], rax
0x180026126  mov     rax, [rbx+118h]
0x18002612d  mov     [rbp+0B0h+var_E0], rax
0x180026131  lea     rax, aNumflushes; "NumFlushes"
0x180026138  mov     [rbp+0B0h+var_48], rax
0x18002613c  lea     eax, [rdi+14h]
0x18002613f  mov     [rbp+0B0h+var_40], ax
0x180026143  mov     rax, [rbx+148h]
0x18002614a  mov     [rbp+0B0h+var_A0], cx
0x18002614e  mov     [rbp+0B0h+var_90], cx
0x180026152  lea     ecx, [rdi+22h]
0x180026155  mov     [rbp+0B0h+var_124], 1
0x18002615c  mov     [rbp+0B0h+var_12F], 4
0x180026160  mov     [rbp+0B0h+var_12E], 4
0x180026164  mov     [rbp+0B0h+var_12D], 4
0x180026168  mov     [rbp+0B0h+var_12C], 4
0x18002616c  mov     [rbp+0B0h+var_80], cx
0x180026170  mov     [rbp+0B0h+var_12B], 4
0x180026174  mov     [rbp+0B0h+var_70], cx
0x180026178  mov     [rbp+0B0h+var_12A], 4
0x18002617c  mov     [rbp+0B0h+var_129], 4
0x180026180  mov     [rbp+0B0h+var_50], si
0x180026184  mov     [rbp+0B0h+var_128], 4
0x180026188  mov     rcx, [rax+8]
0x18002618c  lea     rax, [rbp+0B0h+var_38]
0x180026190  mov     [rbp+0B0h+var_D8], rax
0x180026194  lea     rax, [rbp+0B0h+var_130]
0x180026198  mov     [rsp+250h+var_138], rax
0x1800261a0  lea     rax, [rbp+0B0h+var_124]
0x1800261a4  mov     [rsp+250h+var_140], rax
0x1800261ac  lea     rax, [rbp+0B0h+var_C8]
0x1800261b0  movups  xmm0, xmmword ptr [rcx-10h]
0x1800261b4  mov     [rsp+250h+var_148], rax
0x1800261bc  lea     rax, [rbp+0B0h+var_12F]
0x1800261c0  mov     [rsp+250h+var_150], rax
0x1800261c8  lea     rax, [rbp+0B0h+var_118]
0x1800261cc  mov     [rsp+250h+var_158], rax
0x1800261d4  lea     rax, [rbp+0B0h+var_B8]
0x1800261d8  mov     [rsp+250h+var_160], rax
0x1800261e0  lea     rax, [rbp+0B0h+var_12E]
0x1800261e4  movdqu  [rbp+0B0h+var_38], xmm0
0x1800261e9  mov     [rbp+0B0h+var_127], dil
0x1800261ed  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x1800261f4  mov     [rbp+0B0h+var_11C], 12Ch
0x1800261fb  mov     [rbp+0B0h+var_D0], 1000000h
0x180026203  mov     [rsp+250h+var_168], rax
0x18002620b  lea     rdx, byte_180038549
0x180026212  lea     rax, [rbp+0B0h+var_110]
0x180026216  mov     [rsp+250h+var_170], rax
0x18002621e  lea     rax, [rbp+0B0h+var_A8]
0x180026222  mov     [rsp+250h+var_178], rax
0x18002622a  lea     rax, [rbp+0B0h+var_12D]
0x18002622e  mov     [rsp+250h+var_180], rax
0x180026236  lea     rax, [rbp+0B0h+var_108]
0x18002623a  mov     [rsp+250h+var_188], rax
0x180026242  lea     rax, [rbp+0B0h+var_98]
0x180026246  mov     [rsp+250h+var_190], rax
0x18002624e  lea     rax, [rbp+0B0h+var_12C]
0x180026252  mov     [rsp+250h+var_198], rax
0x18002625a  lea     rax, [rbp+0B0h+var_100]
0x18002625e  mov     [rsp+250h+var_1A0], rax
0x180026266  lea     rax, [rbp+0B0h+var_88]
0x18002626a  mov     [rsp+250h+var_1A8], rax
0x180026272  lea     rax, [rbp+0B0h+var_12B]
0x180026276  mov     [rsp+250h+var_1B0], rax
0x18002627e  lea     rax, [rbp+0B0h+var_F8]
0x180026282  mov     [rsp+250h+var_1B8], rax
0x18002628a  lea     rax, [rbp+0B0h+var_78]
0x18002628e  mov     [rsp+250h+var_1C0], rax
0x180026296  lea     rax, [rbp+0B0h+var_12A]
0x18002629a  mov     [rsp+250h+var_1C8], rax
0x1800262a2  lea     rax, [rbp+0B0h+var_F0]
0x1800262a6  mov     [rsp+250h+var_1D0], rax
0x1800262ae  lea     rax, [rbp+0B0h+var_68]
0x1800262b2  mov     [rsp+250h+var_1D8], rax
0x1800262b7  lea     rax, [rbp+0B0h+var_129]
0x1800262bb  mov     [rsp+250h+var_1E0], rax
0x1800262c0  lea     rax, [rbp+0B0h+var_E8]
0x1800262c4  mov     [rsp+250h+var_1E8], rax
0x1800262c9  lea     rax, [rbp+0B0h+var_58]
0x1800262cd  mov     [rsp+250h+var_1F0], rax
0x1800262d2  lea     rax, [rbp+0B0h+var_128]
0x1800262d6  mov     [rsp+250h+var_1F8], rax
0x1800262db  lea     rax, [rbp+0B0h+var_E0]
0x1800262df  mov     [rsp+250h+var_200], rax
0x1800262e4  lea     rax, [rbp+0B0h+var_48]
0x1800262e8  mov     [rsp+250h+var_208], rax
0x1800262ed  lea     rax, [rbp+0B0h+var_D8]
0x1800262f1  mov     [rsp+250h+var_210], rax
0x1800262f6  lea     rax, [rbp+0B0h+var_127]
0x1800262fa  mov     [rsp+250h+var_218], rax
0x1800262ff  lea     rax, [rbp+0B0h+var_120]
0x180026303  mov     [rsp+250h+var_220], rax
0x180026308  lea     rax, [rbp+0B0h+var_11C]
0x18002630c  mov     [rsp+250h+var_228], rax
0x180026311  lea     rax, [rbp+0B0h+var_D0]
0x180026315  mov     [rsp+250h+var_230], rax
0x18002631a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18002631f  xorps   xmm0, xmm0
0x180026322  xor     eax, eax
0x180026324  movups  xmmword ptr [rbx+110h], xmm0
0x18002632b  movups  xmmword ptr [rbx+120h], xmm0
0x180026332  mov     [rbx+130h], rax
0x180026339  mov     edx, edi
0x18002633b  mov     rcx, rbx
0x18002633e  call    FlushLookUpTableBucket
0x180026343  inc     edi
0x180026345  cmp     edi, esi
0x180026347  jb      short loc_180026339
0x180026349  mov     rcx, [rbp+0B0h+var_28]
0x180026350  xor     rcx, rsp; StackCookie
0x180026353  call    __security_check_cookie
0x180026358  add     rsp, 238h
0x18002635f  pop     rdi
0x180026360  pop     rsi
0x180026361  pop     rbx
0x180026362  pop     rbp
0x180026363  retn
```
