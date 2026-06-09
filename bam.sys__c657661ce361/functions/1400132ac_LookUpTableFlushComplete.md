# LookUpTableFlushComplete

- ea: `0x1400132ac`
- end: `0x14001361d`
- name: `LookUpTableFlushComplete`
- size: `881`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000eec0`
- `0x14000f0c0`
- `0x140013230`
- `0x140013670`

## callees

- `0x140001008`
- `0x140001578`
- `0x1400023b4`
- `0x1400026d0`
- `0x14000ef44`
- `0x1400132ac`

## pseudocode

```c
void __fastcall LookUpTableFlushComplete(__int64 a1)
{
  unsigned int v1; // edi
  __int64 v3; // rcx
  int v4; // r8d
  int v5; // r9d
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
    if ( *(_QWORD *)(v3 + 288) )
    {
      if ( (unsigned int)dword_1400071C0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400071C0, 0x200000000000LL) )
      {
        v8 = 4;
        v34 = 42;
        v31 = L"SummaryCount";
        v32 = 24;
        v21 = *(unsigned int *)(a1 + 324);
        v33 = L"NumLargeEventFailures";
        v22 = *(unsigned int *)(a1 + 320);
        v35 = L"NumAllocationFailures";
        v23 = *(unsigned int *)(a1 + 316);
        v37 = L"NumBucketLimitReached";
        v24 = *(unsigned int *)(a1 + 312);
        v39 = L"MinEntriesFlushed";
        v25 = *(unsigned int *)(a1 + 308);
        v41 = L"MaxEntriesFlushed";
        v26 = *(_QWORD *)(a1 + 288);
        v43 = L"TotalEntriesFlushed";
        v44 = 38;
        v27 = *(unsigned int *)(a1 + 304);
        v45 = L"MaxEntriesStored";
        v28 = *(_QWORD *)(a1 + 296);
        v47 = L"NumFlushes";
        v48 = 20;
        v6 = *(_QWORD *)(a1 + 344);
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
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (unsigned int)byte_140005995,
          v4,
          v5,
          (__int64)&v30,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)v17,
          (__int64)&v29,
          (__int64)&v47,
          (__int64)&v28,
          (__int64)&v16,
          (__int64)&v45,
          (__int64)&v27,
          (__int64)&v15,
          (__int64)&v43,
          (__int64)&v26,
          (__int64)&v14,
          (__int64)&v41,
          (__int64)&v25,
          (__int64)&v13,
          (__int64)&v39,
          (__int64)&v24,
          (__int64)&v12,
          (__int64)&v37,
          (__int64)&v23,
          (__int64)&v11,
          (__int64)&v35,
          (__int64)&v22,
          (__int64)&v10,
          (__int64)&v33,
          (__int64)&v21,
          (__int64)&v9,
          (__int64)&v31,
          (__int64)&v18,
          (__int64)&v8);
      }
      *(_OWORD *)(a1 + 288) = 0;
      *(_OWORD *)(a1 + 304) = 0;
      *(_QWORD *)(a1 + 320) = 0;
    }
    do
      FlushLookUpTableBucket(a1, v1++);
    while ( v1 < 0x20 );
  }
}

```

## disassembly

```asm
0x1400132ac  push    rbp
0x1400132ae  push    rbx
0x1400132af  push    rsi
0x1400132b0  push    rdi
0x1400132b1  lea     rbp, [rsp-98h]
0x1400132b9  sub     rsp, 238h
0x1400132c0  mov     rax, cs:__security_cookie
0x1400132c7  xor     rax, rsp
0x1400132ca  mov     [rbp+0B0h+var_28], rax
0x1400132d1  mov     edx, [rcx+100h]
0x1400132d7  xor     edi, edi
0x1400132d9  mov     rbx, rcx
0x1400132dc  test    edx, edx
0x1400132de  jz      loc_140013601
0x1400132e4  call    UpdateInternalStatsOnFlush
0x1400132e9  lea     esi, [rdi+20h]
0x1400132ec  cmp     [rcx+120h], rdi
0x1400132f3  jz      loc_1400135F1
0x1400132f9  mov     eax, cs:dword_1400071C0
0x1400132ff  cmp     eax, 5
0x140013302  jbe     loc_1400135D7
0x140013308  mov     rdx, 200000000000h
0x140013312  lea     rcx, dword_1400071C0
0x140013319  call    _tlgKeywordOn
0x14001331e  test    al, al
0x140013320  jz      loc_1400135D7
0x140013326  lea     ecx, [rdi+2Ah]
0x140013329  mov     [rbp+0B0h+var_130], 4
0x14001332d  lea     rax, aSummarycount; "SummaryCount"
0x140013334  mov     [rbp+0B0h+var_B0], cx
0x140013338  mov     [rbp+0B0h+var_C8], rax
0x14001333c  lea     eax, [rdi+18h]
0x14001333f  mov     [rbp+0B0h+var_C0], ax
0x140013343  mov     eax, [rbx+144h]
0x140013349  mov     [rbp+0B0h+var_118], rax
0x14001334d  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x140013354  mov     [rbp+0B0h+var_B8], rax
0x140013358  mov     eax, [rbx+140h]
0x14001335e  mov     [rbp+0B0h+var_110], rax
0x140013362  lea     rax, aNumallocationf; "NumAllocationFailures"
0x140013369  mov     [rbp+0B0h+var_A8], rax
0x14001336d  mov     eax, [rbx+13Ch]
0x140013373  mov     [rbp+0B0h+var_108], rax
0x140013377  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x14001337e  mov     [rbp+0B0h+var_98], rax
0x140013382  mov     eax, [rbx+138h]
0x140013388  mov     [rbp+0B0h+var_100], rax
0x14001338c  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x140013393  mov     [rbp+0B0h+var_88], rax
0x140013397  mov     eax, [rbx+134h]
0x14001339d  mov     [rbp+0B0h+var_F8], rax
0x1400133a1  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x1400133a8  mov     [rbp+0B0h+var_78], rax
0x1400133ac  mov     rax, [rbx+120h]
0x1400133b3  mov     [rbp+0B0h+var_F0], rax
0x1400133b7  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x1400133be  mov     [rbp+0B0h+var_68], rax
0x1400133c2  lea     eax, [rdi+26h]
0x1400133c5  mov     [rbp+0B0h+var_60], ax
0x1400133c9  mov     eax, [rbx+130h]
0x1400133cf  mov     [rbp+0B0h+var_E8], rax
0x1400133d3  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x1400133da  mov     [rbp+0B0h+var_58], rax
0x1400133de  mov     rax, [rbx+128h]
0x1400133e5  mov     [rbp+0B0h+var_E0], rax
0x1400133e9  lea     rax, aNumflushes; "NumFlushes"
0x1400133f0  mov     [rbp+0B0h+var_48], rax
0x1400133f4  lea     eax, [rdi+14h]
0x1400133f7  mov     [rbp+0B0h+var_40], ax
0x1400133fb  mov     rax, [rbx+158h]
0x140013402  mov     [rbp+0B0h+var_A0], cx
0x140013406  mov     [rbp+0B0h+var_90], cx
0x14001340a  lea     ecx, [rdi+22h]
0x14001340d  mov     [rbp+0B0h+var_124], 1
0x140013414  mov     [rbp+0B0h+var_12F], 4
0x140013418  mov     [rbp+0B0h+var_12E], 4
0x14001341c  mov     [rbp+0B0h+var_12D], 4
0x140013420  mov     [rbp+0B0h+var_12C], 4
0x140013424  mov     [rbp+0B0h+var_80], cx
0x140013428  mov     [rbp+0B0h+var_12B], 4
0x14001342c  mov     [rbp+0B0h+var_70], cx
0x140013430  mov     [rbp+0B0h+var_12A], 4
0x140013434  mov     [rbp+0B0h+var_129], 4
0x140013438  mov     [rbp+0B0h+var_50], si
0x14001343c  mov     [rbp+0B0h+var_128], 4
0x140013440  mov     rcx, [rax+8]
0x140013444  lea     rax, [rbp+0B0h+var_38]
0x140013448  mov     [rbp+0B0h+var_D8], rax
0x14001344c  lea     rax, [rbp+0B0h+var_130]
0x140013450  mov     [rsp+250h+var_138], rax
0x140013458  lea     rax, [rbp+0B0h+var_124]
0x14001345c  mov     [rsp+250h+var_140], rax
0x140013464  lea     rax, [rbp+0B0h+var_C8]
0x140013468  movups  xmm0, xmmword ptr [rcx-10h]
0x14001346c  mov     [rsp+250h+var_148], rax
0x140013474  lea     rax, [rbp+0B0h+var_12F]
0x140013478  mov     [rsp+250h+var_150], rax
0x140013480  lea     rax, [rbp+0B0h+var_118]
0x140013484  mov     [rsp+250h+var_158], rax
0x14001348c  lea     rax, [rbp+0B0h+var_B8]
0x140013490  mov     [rsp+250h+var_160], rax
0x140013498  lea     rax, [rbp+0B0h+var_12E]
0x14001349c  movdqu  [rbp+0B0h+var_38], xmm0
0x1400134a1  mov     [rbp+0B0h+var_127], dil
0x1400134a5  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x1400134ac  mov     [rbp+0B0h+var_11C], 12Ch
0x1400134b3  mov     [rbp+0B0h+var_D0], 1000000h
0x1400134bb  mov     [rsp+250h+var_168], rax
0x1400134c3  lea     rdx, byte_140005995
0x1400134ca  lea     rax, [rbp+0B0h+var_110]
0x1400134ce  mov     [rsp+250h+var_170], rax
0x1400134d6  lea     rax, [rbp+0B0h+var_A8]
0x1400134da  mov     [rsp+250h+var_178], rax
0x1400134e2  lea     rax, [rbp+0B0h+var_12D]
0x1400134e6  mov     [rsp+250h+var_180], rax
0x1400134ee  lea     rax, [rbp+0B0h+var_108]
0x1400134f2  mov     [rsp+250h+var_188], rax
0x1400134fa  lea     rax, [rbp+0B0h+var_98]
0x1400134fe  mov     [rsp+250h+var_190], rax
0x140013506  lea     rax, [rbp+0B0h+var_12C]
0x14001350a  mov     [rsp+250h+var_198], rax
0x140013512  lea     rax, [rbp+0B0h+var_100]
0x140013516  mov     [rsp+250h+var_1A0], rax
0x14001351e  lea     rax, [rbp+0B0h+var_88]
0x140013522  mov     [rsp+250h+var_1A8], rax
0x14001352a  lea     rax, [rbp+0B0h+var_12B]
0x14001352e  mov     [rsp+250h+var_1B0], rax
0x140013536  lea     rax, [rbp+0B0h+var_F8]
0x14001353a  mov     [rsp+250h+var_1B8], rax
0x140013542  lea     rax, [rbp+0B0h+var_78]
0x140013546  mov     [rsp+250h+var_1C0], rax
0x14001354e  lea     rax, [rbp+0B0h+var_12A]
0x140013552  mov     [rsp+250h+var_1C8], rax
0x14001355a  lea     rax, [rbp+0B0h+var_F0]
0x14001355e  mov     [rsp+250h+var_1D0], rax
0x140013566  lea     rax, [rbp+0B0h+var_68]
0x14001356a  mov     [rsp+250h+var_1D8], rax
0x14001356f  lea     rax, [rbp+0B0h+var_129]
0x140013573  mov     [rsp+250h+var_1E0], rax
0x140013578  lea     rax, [rbp+0B0h+var_E8]
0x14001357c  mov     [rsp+250h+var_1E8], rax
0x140013581  lea     rax, [rbp+0B0h+var_58]
0x140013585  mov     [rsp+250h+var_1F0], rax
0x14001358a  lea     rax, [rbp+0B0h+var_128]
0x14001358e  mov     [rsp+250h+var_1F8], rax
0x140013593  lea     rax, [rbp+0B0h+var_E0]
0x140013597  mov     [rsp+250h+var_200], rax
0x14001359c  lea     rax, [rbp+0B0h+var_48]
0x1400135a0  mov     [rsp+250h+var_208], rax
0x1400135a5  lea     rax, [rbp+0B0h+var_D8]
0x1400135a9  mov     [rsp+250h+var_210], rax
0x1400135ae  lea     rax, [rbp+0B0h+var_127]
0x1400135b2  mov     [rsp+250h+var_218], rax
0x1400135b7  lea     rax, [rbp+0B0h+var_120]
0x1400135bb  mov     [rsp+250h+var_220], rax
0x1400135c0  lea     rax, [rbp+0B0h+var_11C]
0x1400135c4  mov     [rsp+250h+var_228], rax
0x1400135c9  lea     rax, [rbp+0B0h+var_D0]
0x1400135cd  mov     [rsp+250h+var_230], rax
0x1400135d2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1400135d7  xorps   xmm0, xmm0
0x1400135da  xor     eax, eax
0x1400135dc  movups  xmmword ptr [rbx+120h], xmm0
0x1400135e3  movups  xmmword ptr [rbx+130h], xmm0
0x1400135ea  mov     [rbx+140h], rax
0x1400135f1  mov     edx, edi
0x1400135f3  mov     rcx, rbx
0x1400135f6  call    FlushLookUpTableBucket
0x1400135fb  inc     edi
0x1400135fd  cmp     edi, esi
0x1400135ff  jb      short loc_1400135F1
0x140013601  mov     rcx, [rbp+0B0h+var_28]
0x140013608  xor     rcx, rsp; StackCookie
0x14001360b  call    __security_check_cookie
0x140013610  add     rsp, 238h
0x140013617  pop     rdi
0x140013618  pop     rsi
0x140013619  pop     rbx
0x14001361a  pop     rbp
0x14001361b  retn
```
