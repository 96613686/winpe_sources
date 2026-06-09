# LookUpTableFlushComplete

- ea: `0x18000c038`
- end: `0x18000c3a8`
- name: `LookUpTableFlushComplete`
- size: `880`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000bdb0`
- `0x18000bfc0`
- `0x18000e7c0`
- `0x180019b74`

## callees

- `0x180001654`
- `0x18000be68`
- `0x18000c038`
- `0x18000c3b0`
- `0x18000ee60`
- `0x180012dd0`

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
      if ( (unsigned int)dword_1800260A0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800260A0, 0x200000000000LL) )
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
          (__int64)&byte_180020DE7,
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
0x18000c038  push    rbp
0x18000c03a  push    rbx
0x18000c03b  push    rsi
0x18000c03c  push    rdi
0x18000c03d  lea     rbp, [rsp-98h]
0x18000c045  sub     rsp, 238h
0x18000c04c  mov     rax, cs:__security_cookie
0x18000c053  xor     rax, rsp
0x18000c056  mov     [rbp+0B0h+var_28], rax
0x18000c05d  mov     edx, [rcx+100h]
0x18000c063  xor     edi, edi
0x18000c065  mov     rbx, rcx
0x18000c068  test    edx, edx
0x18000c06a  jz      loc_18000C38D
0x18000c070  call    UpdateInternalStatsOnFlush
0x18000c075  lea     esi, [rdi+20h]
0x18000c078  cmp     [rcx+110h], rdi
0x18000c07f  jz      loc_18000C37D
0x18000c085  mov     eax, cs:dword_1800260A0
0x18000c08b  cmp     eax, 5
0x18000c08e  jbe     loc_18000C363
0x18000c094  mov     rdx, 200000000000h
0x18000c09e  lea     rcx, dword_1800260A0
0x18000c0a5  call    _tlgKeywordOn
0x18000c0aa  test    al, al
0x18000c0ac  jz      loc_18000C363
0x18000c0b2  lea     ecx, [rdi+2Ah]
0x18000c0b5  mov     [rbp+0B0h+var_130], 4
0x18000c0b9  lea     rax, aSummarycount; "SummaryCount"
0x18000c0c0  mov     [rbp+0B0h+var_B0], cx
0x18000c0c4  mov     [rbp+0B0h+var_C8], rax
0x18000c0c8  lea     eax, [rdi+18h]
0x18000c0cb  mov     [rbp+0B0h+var_C0], ax
0x18000c0cf  mov     eax, [rbx+134h]
0x18000c0d5  mov     [rbp+0B0h+var_118], rax
0x18000c0d9  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x18000c0e0  mov     [rbp+0B0h+var_B8], rax
0x18000c0e4  mov     eax, [rbx+130h]
0x18000c0ea  mov     [rbp+0B0h+var_110], rax
0x18000c0ee  lea     rax, aNumallocationf; "NumAllocationFailures"
0x18000c0f5  mov     [rbp+0B0h+var_A8], rax
0x18000c0f9  mov     eax, [rbx+12Ch]
0x18000c0ff  mov     [rbp+0B0h+var_108], rax
0x18000c103  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x18000c10a  mov     [rbp+0B0h+var_98], rax
0x18000c10e  mov     eax, [rbx+128h]
0x18000c114  mov     [rbp+0B0h+var_100], rax
0x18000c118  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x18000c11f  mov     [rbp+0B0h+var_88], rax
0x18000c123  mov     eax, [rbx+124h]
0x18000c129  mov     [rbp+0B0h+var_F8], rax
0x18000c12d  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18000c134  mov     [rbp+0B0h+var_78], rax
0x18000c138  mov     rax, [rbx+110h]
0x18000c13f  mov     [rbp+0B0h+var_F0], rax
0x18000c143  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x18000c14a  mov     [rbp+0B0h+var_68], rax
0x18000c14e  lea     eax, [rdi+26h]
0x18000c151  mov     [rbp+0B0h+var_60], ax
0x18000c155  mov     eax, [rbx+120h]
0x18000c15b  mov     [rbp+0B0h+var_E8], rax
0x18000c15f  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18000c166  mov     [rbp+0B0h+var_58], rax
0x18000c16a  mov     rax, [rbx+118h]
0x18000c171  mov     [rbp+0B0h+var_E0], rax
0x18000c175  lea     rax, aNumflushes; "NumFlushes"
0x18000c17c  mov     [rbp+0B0h+var_48], rax
0x18000c180  lea     eax, [rdi+14h]
0x18000c183  mov     [rbp+0B0h+var_40], ax
0x18000c187  mov     rax, [rbx+148h]
0x18000c18e  mov     [rbp+0B0h+var_A0], cx
0x18000c192  mov     [rbp+0B0h+var_90], cx
0x18000c196  lea     ecx, [rdi+22h]
0x18000c199  mov     [rbp+0B0h+var_124], 1
0x18000c1a0  mov     [rbp+0B0h+var_12F], 4
0x18000c1a4  mov     [rbp+0B0h+var_12E], 4
0x18000c1a8  mov     [rbp+0B0h+var_12D], 4
0x18000c1ac  mov     [rbp+0B0h+var_12C], 4
0x18000c1b0  mov     [rbp+0B0h+var_80], cx
0x18000c1b4  mov     [rbp+0B0h+var_12B], 4
0x18000c1b8  mov     [rbp+0B0h+var_70], cx
0x18000c1bc  mov     [rbp+0B0h+var_12A], 4
0x18000c1c0  mov     [rbp+0B0h+var_129], 4
0x18000c1c4  mov     [rbp+0B0h+var_50], si
0x18000c1c8  mov     [rbp+0B0h+var_128], 4
0x18000c1cc  mov     rcx, [rax+8]
0x18000c1d0  lea     rax, [rbp+0B0h+var_38]
0x18000c1d4  mov     [rbp+0B0h+var_D8], rax
0x18000c1d8  lea     rax, [rbp+0B0h+var_130]
0x18000c1dc  mov     [rsp+250h+var_138], rax
0x18000c1e4  lea     rax, [rbp+0B0h+var_124]
0x18000c1e8  mov     [rsp+250h+var_140], rax
0x18000c1f0  lea     rax, [rbp+0B0h+var_C8]
0x18000c1f4  movups  xmm0, xmmword ptr [rcx-10h]
0x18000c1f8  mov     [rsp+250h+var_148], rax
0x18000c200  lea     rax, [rbp+0B0h+var_12F]
0x18000c204  mov     [rsp+250h+var_150], rax
0x18000c20c  lea     rax, [rbp+0B0h+var_118]
0x18000c210  mov     [rsp+250h+var_158], rax
0x18000c218  lea     rax, [rbp+0B0h+var_B8]
0x18000c21c  mov     [rsp+250h+var_160], rax
0x18000c224  lea     rax, [rbp+0B0h+var_12E]
0x18000c228  movdqu  [rbp+0B0h+var_38], xmm0
0x18000c22d  mov     [rbp+0B0h+var_127], dil
0x18000c231  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x18000c238  mov     [rbp+0B0h+var_11C], 12Ch
0x18000c23f  mov     [rbp+0B0h+var_D0], 1000000h
0x18000c247  mov     [rsp+250h+var_168], rax
0x18000c24f  lea     rdx, byte_180020DE7
0x18000c256  lea     rax, [rbp+0B0h+var_110]
0x18000c25a  mov     [rsp+250h+var_170], rax
0x18000c262  lea     rax, [rbp+0B0h+var_A8]
0x18000c266  mov     [rsp+250h+var_178], rax
0x18000c26e  lea     rax, [rbp+0B0h+var_12D]
0x18000c272  mov     [rsp+250h+var_180], rax
0x18000c27a  lea     rax, [rbp+0B0h+var_108]
0x18000c27e  mov     [rsp+250h+var_188], rax
0x18000c286  lea     rax, [rbp+0B0h+var_98]
0x18000c28a  mov     [rsp+250h+var_190], rax
0x18000c292  lea     rax, [rbp+0B0h+var_12C]
0x18000c296  mov     [rsp+250h+var_198], rax
0x18000c29e  lea     rax, [rbp+0B0h+var_100]
0x18000c2a2  mov     [rsp+250h+var_1A0], rax
0x18000c2aa  lea     rax, [rbp+0B0h+var_88]
0x18000c2ae  mov     [rsp+250h+var_1A8], rax
0x18000c2b6  lea     rax, [rbp+0B0h+var_12B]
0x18000c2ba  mov     [rsp+250h+var_1B0], rax
0x18000c2c2  lea     rax, [rbp+0B0h+var_F8]
0x18000c2c6  mov     [rsp+250h+var_1B8], rax
0x18000c2ce  lea     rax, [rbp+0B0h+var_78]
0x18000c2d2  mov     [rsp+250h+var_1C0], rax
0x18000c2da  lea     rax, [rbp+0B0h+var_12A]
0x18000c2de  mov     [rsp+250h+var_1C8], rax
0x18000c2e6  lea     rax, [rbp+0B0h+var_F0]
0x18000c2ea  mov     [rsp+250h+var_1D0], rax
0x18000c2f2  lea     rax, [rbp+0B0h+var_68]
0x18000c2f6  mov     [rsp+250h+var_1D8], rax
0x18000c2fb  lea     rax, [rbp+0B0h+var_129]
0x18000c2ff  mov     [rsp+250h+var_1E0], rax
0x18000c304  lea     rax, [rbp+0B0h+var_E8]
0x18000c308  mov     [rsp+250h+var_1E8], rax
0x18000c30d  lea     rax, [rbp+0B0h+var_58]
0x18000c311  mov     [rsp+250h+var_1F0], rax
0x18000c316  lea     rax, [rbp+0B0h+var_128]
0x18000c31a  mov     [rsp+250h+var_1F8], rax
0x18000c31f  lea     rax, [rbp+0B0h+var_E0]
0x18000c323  mov     [rsp+250h+var_200], rax
0x18000c328  lea     rax, [rbp+0B0h+var_48]
0x18000c32c  mov     [rsp+250h+var_208], rax
0x18000c331  lea     rax, [rbp+0B0h+var_D8]
0x18000c335  mov     [rsp+250h+var_210], rax
0x18000c33a  lea     rax, [rbp+0B0h+var_127]
0x18000c33e  mov     [rsp+250h+var_218], rax
0x18000c343  lea     rax, [rbp+0B0h+var_120]
0x18000c347  mov     [rsp+250h+var_220], rax
0x18000c34c  lea     rax, [rbp+0B0h+var_11C]
0x18000c350  mov     [rsp+250h+var_228], rax
0x18000c355  lea     rax, [rbp+0B0h+var_D0]
0x18000c359  mov     [rsp+250h+var_230], rax
0x18000c35e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18000c363  xorps   xmm0, xmm0
0x18000c366  xor     eax, eax
0x18000c368  movups  xmmword ptr [rbx+110h], xmm0
0x18000c36f  movups  xmmword ptr [rbx+120h], xmm0
0x18000c376  mov     [rbx+130h], rax
0x18000c37d  mov     edx, edi
0x18000c37f  mov     rcx, rbx
0x18000c382  call    FlushLookUpTableBucket
0x18000c387  inc     edi
0x18000c389  cmp     edi, esi
0x18000c38b  jb      short loc_18000C37D
0x18000c38d  mov     rcx, [rbp+0B0h+var_28]
0x18000c394  xor     rcx, rsp; StackCookie
0x18000c397  call    __security_check_cookie
0x18000c39c  add     rsp, 238h
0x18000c3a3  pop     rdi
0x18000c3a4  pop     rsi
0x18000c3a5  pop     rbx
0x18000c3a6  pop     rbp
0x18000c3a7  retn
```
