# LookUpTableFlushComplete

- ea: `0x1800151b0`
- end: `0x1800156ea`
- name: `LookUpTableFlushComplete`
- size: `1338`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800150e0`
- `0x180015130`
- `0x180017ba0`
- `0x180022170`

## callees

- `0x180001008`
- `0x1800151b0`
- `0x18001cf50`
- `0x18001da24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015581`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015581`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800155fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800155fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015683`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015683`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015691`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015691`

## pseudocode

```c
int __fastcall LookUpTableFlushComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  unsigned __int64 v4; // rax
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 i; // r15
  __int64 v9; // rdi
  int v10; // r8d
  __int64 *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 *v15; // rcx
  REGHANDLE j; // r14
  PEVENT_DATA_DESCRIPTOR *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  PEVENT_DATA_DESCRIPTOR v20; // rbx
  HANDLE ProcessHeap; // rax
  char v23; // [rsp+128h] [rbp-80h] BYREF
  char v24; // [rsp+129h] [rbp-7Fh] BYREF
  char v25; // [rsp+12Ah] [rbp-7Eh] BYREF
  char v26; // [rsp+12Bh] [rbp-7Dh] BYREF
  char v27; // [rsp+12Ch] [rbp-7Ch] BYREF
  char v28; // [rsp+12Dh] [rbp-7Bh] BYREF
  char v29; // [rsp+12Eh] [rbp-7Ah] BYREF
  char v30; // [rsp+12Fh] [rbp-79h] BYREF
  char v31; // [rsp+130h] [rbp-78h] BYREF
  char v32[3]; // [rsp+131h] [rbp-77h] BYREF
  int v33; // [rsp+134h] [rbp-74h] BYREF
  int v34; // [rsp+138h] [rbp-70h] BYREF
  int v35; // [rsp+13Ch] [rbp-6Ch] BYREF
  __int64 v36; // [rsp+140h] [rbp-68h] BYREF
  __int64 v37; // [rsp+148h] [rbp-60h] BYREF
  __int64 v38; // [rsp+150h] [rbp-58h] BYREF
  __int64 v39; // [rsp+158h] [rbp-50h] BYREF
  __int64 v40; // [rsp+160h] [rbp-48h] BYREF
  __int64 v41; // [rsp+168h] [rbp-40h] BYREF
  __int64 v42; // [rsp+170h] [rbp-38h] BYREF
  __int64 v43; // [rsp+178h] [rbp-30h] BYREF
  __int128 *v44; // [rsp+180h] [rbp-28h] BYREF
  __int64 v45; // [rsp+188h] [rbp-20h] BYREF
  const wchar_t *v46; // [rsp+190h] [rbp-18h] BYREF
  __int16 v47; // [rsp+198h] [rbp-10h]
  const wchar_t *v48; // [rsp+1A0h] [rbp-8h] BYREF
  __int16 v49; // [rsp+1A8h] [rbp+0h]
  const wchar_t *v50; // [rsp+1B0h] [rbp+8h] BYREF
  __int16 v51; // [rsp+1B8h] [rbp+10h]
  const wchar_t *v52; // [rsp+1C0h] [rbp+18h] BYREF
  __int16 v53; // [rsp+1C8h] [rbp+20h]
  const wchar_t *v54; // [rsp+1D0h] [rbp+28h] BYREF
  __int16 v55; // [rsp+1D8h] [rbp+30h]
  const wchar_t *v56; // [rsp+1E0h] [rbp+38h] BYREF
  __int16 v57; // [rsp+1E8h] [rbp+40h]
  const wchar_t *v58; // [rsp+1F0h] [rbp+48h] BYREF
  __int16 v59; // [rsp+1F8h] [rbp+50h]
  const wchar_t *v60; // [rsp+200h] [rbp+58h] BYREF
  __int16 v61; // [rsp+208h] [rbp+60h]
  const wchar_t *v62; // [rsp+210h] [rbp+68h] BYREF
  __int16 v63; // [rsp+218h] [rbp+70h]
  __int128 v64; // [rsp+220h] [rbp+78h] BYREF

  v4 = *(unsigned int *)(a1 + 256);
  if ( (_DWORD)v4 )
  {
    if ( *(_DWORD *)(a1 + 296) > (unsigned int)v4 || !*(_QWORD *)(a1 + 280) )
      *(_DWORD *)(a1 + 296) = v4;
    if ( *(_DWORD *)(a1 + 292) < (unsigned int)v4 )
      *(_DWORD *)(a1 + 292) = v4;
    *(__m128i *)(a1 + 272) = _mm_add_epi64(
                               _mm_unpacklo_epi64((__m128i)v4, (__m128i)1uLL),
                               _mm_loadu_si128((const __m128i *)(a1 + 272)));
    if ( *(_QWORD *)(a1 + 272) )
    {
      if ( (unsigned int)dword_1800350D0 > 5
        && (qword_1800350E0 & 0x200000000000LL) != 0
        && (qword_1800350E8 & 0x200000000000LL) == qword_1800350E8 )
      {
        v23 = 4;
        v49 = 42;
        v46 = L"SummaryCount";
        v47 = 24;
        v45 = *(unsigned int *)(a1 + 308);
        v48 = L"NumLargeEventFailures";
        v37 = *(unsigned int *)(a1 + 304);
        v50 = L"NumAllocationFailures";
        v38 = *(unsigned int *)(a1 + 300);
        v52 = L"NumBucketLimitReached";
        v39 = *(unsigned int *)(a1 + 296);
        v54 = L"MinEntriesFlushed";
        v40 = *(unsigned int *)(a1 + 292);
        v56 = L"MaxEntriesFlushed";
        v41 = *(_QWORD *)(a1 + 272);
        v58 = L"TotalEntriesFlushed";
        v59 = 38;
        v42 = *(unsigned int *)(a1 + 288);
        v60 = L"MaxEntriesStored";
        v61 = 32;
        v43 = *(_QWORD *)(a1 + 280);
        v62 = L"NumFlushes";
        v63 = 20;
        v6 = *(_QWORD *)(a1 + 328);
        v51 = 42;
        v53 = 42;
        v33 = 1;
        v24 = 4;
        v25 = 4;
        v26 = 4;
        v27 = 4;
        v55 = 34;
        v28 = 4;
        v57 = 34;
        v29 = 4;
        v30 = 4;
        v31 = 4;
        v7 = *(_QWORD *)(v6 + 8);
        v44 = &v64;
        v64 = *(_OWORD *)(v7 - 16);
        v32[0] = 0;
        v34 = -1;
        v35 = 300;
        v36 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
          v7,
          (__int64)byte_18002E0BD,
          1,
          a4,
          (__int64)&v36,
          (__int64)&v35,
          (__int64)&v34,
          (__int64)v32,
          (__int64 *)&v44,
          (__int64 *)&v62,
          (__int64)&v43,
          (__int64)&v31,
          (__int64 *)&v60,
          (__int64)&v42,
          (__int64)&v30,
          (__int64 *)&v58,
          (__int64)&v41,
          (__int64)&v29,
          (__int64 *)&v56,
          (__int64)&v40,
          (__int64)&v28,
          (__int64 *)&v54,
          (__int64)&v39,
          (__int64)&v27,
          (__int64 *)&v52,
          (__int64)&v38,
          (__int64)&v26,
          (__int64 *)&v50,
          (__int64)&v37,
          (__int64)&v25,
          (__int64 *)&v48,
          (__int64)&v45,
          (__int64)&v24,
          (__int64 *)&v46,
          (__int64)&v33,
          (__int64)&v23);
      }
      LODWORD(v4) = 0;
      *(_OWORD *)(a1 + 272) = 0;
      *(_OWORD *)(a1 + 288) = 0;
      *(_QWORD *)(a1 + 304) = 0;
    }
    for ( i = 0; i != 32; ++i )
    {
      if ( *(_QWORD *)(a1 + 8 * i) )
      {
        AcquireSRWLockExclusive((PSRWLOCK)(a1 + 264));
        v9 = *(_QWORD *)(a1 + 8 * i);
        v10 = 0;
        *(_QWORD *)(a1 + 8 * i) = 0;
        v36 = v9;
        if ( v9 )
        {
          v11 = &v36;
          v12 = v9;
          do
          {
            v13 = *(_QWORD *)(v12 + 32);
            *(_QWORD *)(v12 + 32) = 0;
            v11 = (__int64 *)(*v11 + 24);
            v14 = *v11;
            if ( *v11 )
            {
              do
              {
                v15 = (__int64 *)(v14 + 32);
                v14 = *(_QWORD *)(v14 + 32);
              }
              while ( v14 );
            }
            else
            {
              v15 = v11;
            }
            *v15 = v13;
            ++v10;
            v12 = *v11;
          }
          while ( *v11 );
        }
        *(_DWORD *)(a1 + 256) -= v10;
        ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 264));
        v4 = *(_QWORD *)(a1 + 328);
        for ( j = *(_QWORD *)(v4 + 32); v9; LODWORD(v4) = HeapFree(ProcessHeap, 0, v20) )
        {
          v17 = (PEVENT_DATA_DESCRIPTOR *)(v9 + 16);
          v18 = 2;
          if ( (unsigned int)*(unsigned __int8 *)(v9 + 45) + 2 > 2 )
          {
            do
            {
              v19 = v18++;
              (*v17)[v19].Reserved1 = 0;
            }
            while ( v18 < *(unsigned __int8 *)(v9 + 45) + 2 );
          }
          EventWriteTransfer_0(j, (PCEVENT_DESCRIPTOR)v9, 0, 0, *(unsigned __int8 *)(v9 + 44), *v17);
          v9 = *(_QWORD *)(v9 + 24);
          v20 = *v17;
          ProcessHeap = GetProcessHeap();
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800151b0  mov     r11, rsp
0x1800151b3  push    rbp
0x1800151b4  push    rsi
0x1800151b5  lea     rbp, [r11-0B8h]
0x1800151bc  sub     rsp, 248h
0x1800151c3  mov     rax, cs:__security_cookie
0x1800151ca  xor     rax, rsp
0x1800151cd  mov     [rbp+0B0h+var_28], rax
0x1800151d4  mov     eax, [rcx+100h]
0x1800151da  mov     rsi, rcx
0x1800151dd  test    eax, eax
0x1800151df  jz      loc_1800156D1
0x1800151e5  mov     [r11+10h], rbx
0x1800151e9  mov     [r11+18h], rdi
0x1800151ed  mov     [r11-18h], r12
0x1800151f1  mov     [r11-20h], r14
0x1800151f5  mov     [r11-28h], r15
0x1800151f9  cmp     [rcx+128h], eax
0x1800151ff  ja      short loc_18001520B
0x180015201  cmp     qword ptr [rcx+118h], 0
0x180015209  jnz     short loc_180015211
0x18001520b  mov     [rcx+128h], eax
0x180015211  cmp     [rcx+124h], eax
0x180015217  jnb     short loc_18001521F
0x180015219  mov     [rcx+124h], eax
0x18001521f  mov     r8d, 1
0x180015225  movq    xmm1, rax
0x18001522a  movq    xmm0, r8
0x18001522f  punpcklqdq xmm1, xmm0
0x180015233  movdqu  xmm0, xmmword ptr [rcx+110h]
0x18001523b  paddq   xmm1, xmm0
0x18001523f  movdqu  xmmword ptr [rcx+110h], xmm1
0x180015247  cmp     qword ptr [rcx+110h], 0
0x18001524f  jz      loc_18001556A
0x180015255  mov     eax, cs:dword_1800350D0
0x18001525b  cmp     eax, 5
0x18001525e  jbe     loc_180015550
0x180015264  mov     rcx, cs:qword_1800350E8
0x18001526b  mov     rdx, 200000000000h
0x180015275  mov     rax, cs:qword_1800350E0
0x18001527c  test    rdx, rax
0x18001527f  jz      loc_180015550
0x180015285  mov     rax, rcx
0x180015288  and     rax, rdx
0x18001528b  cmp     rax, rcx
0x18001528e  jnz     loc_180015550
0x180015294  mov     ecx, 2Ah ; '*'
0x180015299  mov     [rbp+0B0h+var_130], 4
0x18001529d  lea     rax, aSummarycount; "SummaryCount"
0x1800152a4  mov     [rbp+0B0h+var_B0], cx
0x1800152a8  mov     [rbp+0B0h+var_C8], rax
0x1800152ac  mov     eax, 18h
0x1800152b1  mov     [rbp+0B0h+var_C0], ax
0x1800152b5  mov     eax, [rsi+134h]
0x1800152bb  mov     [rbp+0B0h+var_D0], rax
0x1800152bf  lea     rax, aNumlargeeventf; "NumLargeEventFailures"
0x1800152c6  mov     [rbp+0B0h+var_B8], rax
0x1800152ca  mov     eax, [rsi+130h]
0x1800152d0  mov     [rbp+0B0h+var_110], rax
0x1800152d4  lea     rax, aNumallocationf; "NumAllocationFailures"
0x1800152db  mov     [rbp+0B0h+var_A8], rax
0x1800152df  mov     eax, [rsi+12Ch]
0x1800152e5  mov     [rbp+0B0h+var_108], rax
0x1800152e9  lea     rax, aNumbucketlimit; "NumBucketLimitReached"
0x1800152f0  mov     [rbp+0B0h+var_98], rax
0x1800152f4  mov     eax, [rsi+128h]
0x1800152fa  mov     [rbp+0B0h+var_100], rax
0x1800152fe  lea     rax, aMinentriesflus; "MinEntriesFlushed"
0x180015305  mov     [rbp+0B0h+var_88], rax
0x180015309  mov     eax, [rsi+124h]
0x18001530f  mov     [rbp+0B0h+var_F8], rax
0x180015313  lea     rax, aMaxentriesflus; "MaxEntriesFlushed"
0x18001531a  mov     [rbp+0B0h+var_78], rax
0x18001531e  mov     rax, [rsi+110h]
0x180015325  mov     [rbp+0B0h+var_F0], rax
0x180015329  lea     rax, aTotalentriesfl; "TotalEntriesFlushed"
0x180015330  mov     [rbp+0B0h+var_68], rax
0x180015334  mov     eax, 26h ; '&'
0x180015339  mov     [rbp+0B0h+var_60], ax
0x18001533d  mov     eax, [rsi+120h]
0x180015343  mov     [rbp+0B0h+var_E8], rax
0x180015347  lea     rax, aMaxentriesstor; "MaxEntriesStored"
0x18001534e  mov     [rbp+0B0h+var_58], rax
0x180015352  mov     eax, 20h ; ' '
0x180015357  mov     [rbp+0B0h+var_50], ax
0x18001535b  mov     rax, [rsi+118h]
0x180015362  mov     [rbp+0B0h+var_E0], rax
0x180015366  lea     rax, aNumflushes; "NumFlushes"
0x18001536d  mov     [rbp+0B0h+var_48], rax
0x180015371  mov     eax, 14h
0x180015376  mov     [rbp+0B0h+var_40], ax
0x18001537a  mov     rax, [rsi+148h]
0x180015381  mov     [rbp+0B0h+var_A0], cx
0x180015385  mov     [rbp+0B0h+var_90], cx
0x180015389  mov     ecx, 22h ; '"'
0x18001538e  mov     [rbp+0B0h+var_124], r8d
0x180015392  mov     [rbp+0B0h+var_12F], 4
0x180015396  mov     [rbp+0B0h+var_12E], 4
0x18001539a  mov     [rbp+0B0h+var_12D], 4
0x18001539e  mov     [rbp+0B0h+var_12C], 4
0x1800153a2  mov     [rbp+0B0h+var_80], cx
0x1800153a6  mov     [rbp+0B0h+var_12B], 4
0x1800153aa  mov     [rbp+0B0h+var_70], cx
0x1800153ae  mov     [rbp+0B0h+var_12A], 4
0x1800153b2  mov     [rbp+0B0h+var_129], 4
0x1800153b6  mov     [rbp+0B0h+var_128], 4
0x1800153ba  mov     rcx, [rax+8]
0x1800153be  lea     rax, [rbp+0B0h+var_38]
0x1800153c2  mov     [rbp+0B0h+var_D8], rax
0x1800153c6  lea     rax, [rbp+0B0h+var_130]
0x1800153ca  mov     [rsp+118h], rax
0x1800153d2  lea     rax, [rbp+0B0h+var_124]
0x1800153d6  mov     [rsp+250h+var_140], rax
0x1800153de  lea     rax, [rbp+0B0h+var_C8]
0x1800153e2  movups  xmm0, xmmword ptr [rcx-10h]
0x1800153e6  mov     [rsp+250h+var_148], rax
0x1800153ee  lea     rax, [rbp+0B0h+var_12F]
0x1800153f2  mov     [rsp+250h+var_150], rax
0x1800153fa  lea     rax, [rbp+0B0h+var_D0]
0x1800153fe  mov     [rsp+250h+var_158], rax
0x180015406  lea     rax, [rbp+0B0h+var_B8]
0x18001540a  mov     [rsp+250h+var_160], rax
0x180015412  movups  [rbp+0B0h+var_38], xmm0
0x180015416  mov     [rbp+0B0h+var_127], 0
0x18001541a  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x180015421  mov     [rbp+0B0h+var_11C], 12Ch
0x180015428  mov     [rbp+0B0h+var_118], 1000000h
0x180015430  lea     rax, [rbp+0B0h+var_12E]
0x180015434  mov     [rsp+250h+var_168], rax
0x18001543c  lea     rdx, byte_18002E0BD
0x180015443  lea     rax, [rbp+0B0h+var_110]
0x180015447  mov     [rsp+250h+var_170], rax
0x18001544f  lea     rax, [rbp+0B0h+var_A8]
0x180015453  mov     [rsp+250h+var_178], rax
0x18001545b  lea     rax, [rbp+0B0h+var_12D]
0x18001545f  mov     [rsp+250h+var_180], rax
0x180015467  lea     rax, [rbp+0B0h+var_108]
0x18001546b  mov     [rsp+250h+var_188], rax
0x180015473  lea     rax, [rbp+0B0h+var_98]
0x180015477  mov     [rsp+250h+var_190], rax
0x18001547f  lea     rax, [rbp+0B0h+var_12C]
0x180015483  mov     [rsp+250h+var_198], rax
0x18001548b  lea     rax, [rbp+0B0h+var_100]
0x18001548f  mov     [rsp+250h+var_1A0], rax
0x180015497  lea     rax, [rbp+0B0h+var_88]
0x18001549b  mov     [rsp+250h+var_1A8], rax
0x1800154a3  lea     rax, [rbp+0B0h+var_12B]
0x1800154a7  mov     [rsp+250h+var_1B0], rax
0x1800154af  lea     rax, [rbp+0B0h+var_F8]
0x1800154b3  mov     [rsp+250h+var_1B8], rax
0x1800154bb  lea     rax, [rbp+0B0h+var_78]
0x1800154bf  mov     [rsp+250h+var_1C0], rax
0x1800154c7  lea     rax, [rbp+0B0h+var_12A]
0x1800154cb  mov     [rsp+250h+var_1C8], rax
0x1800154d3  lea     rax, [rbp+0B0h+var_F0]
0x1800154d7  mov     [rsp+250h+var_1D0], rax
0x1800154df  lea     rax, [rbp+0B0h+var_68]
0x1800154e3  mov     [rsp+250h+var_1D8], rax
0x1800154e8  lea     rax, [rbp+0B0h+var_129]
0x1800154ec  mov     [rsp+250h+var_1E0], rax
0x1800154f1  lea     rax, [rbp+0B0h+var_E8]
0x1800154f5  mov     [rsp+250h+var_1E8], rax
0x1800154fa  lea     rax, [rbp+0B0h+var_58]
0x1800154fe  mov     [rsp+250h+var_1F0], rax
0x180015503  lea     rax, [rbp+0B0h+var_128]
0x180015507  mov     [rsp+250h+var_1F8], rax
0x18001550c  lea     rax, [rbp+0B0h+var_E0]
0x180015510  mov     [rsp+250h+var_200], rax
0x180015515  lea     rax, [rbp+0B0h+var_48]
0x180015519  mov     [rsp+250h+var_208], rax
0x18001551e  lea     rax, [rbp+0B0h+var_D8]
0x180015522  mov     [rsp+250h+var_210], rax
0x180015527  lea     rax, [rbp+0B0h+var_127]
0x18001552b  mov     [rsp+250h+var_218], rax
0x180015530  lea     rax, [rbp+0B0h+var_120]
0x180015534  mov     [rsp+250h+var_220], rax
0x180015539  lea     rax, [rbp+0B0h+var_11C]
0x18001553d  mov     [rsp+250h+UserData], rax
0x180015542  lea     rax, [rbp+0B0h+var_118]
0x180015546  mov     qword ptr [rsp+250h+UserDataCount], rax
0x18001554b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U1@U3@U5@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@35735735735735735735735745@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperArray<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperArray<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x180015550  xorps   xmm0, xmm0
0x180015553  xor     eax, eax
0x180015555  movups  xmmword ptr [rsi+110h], xmm0
0x18001555c  movups  xmmword ptr [rsi+120h], xmm0
0x180015563  mov     [rsi+130h], rax
0x18001556a  xor     r12d, r12d
0x18001556d  mov     r15d, r12d
0x180015570  cmp     [rsi+r15*8], r12
0x180015574  jz      loc_18001569C
0x18001557a  lea     rcx, [rsi+108h]; SRWLock
0x180015581  call    cs:__imp_AcquireSRWLockExclusive
0x180015587  mov     rdi, [rsi+r15*8]
0x18001558b  mov     r8d, r12d
0x18001558e  mov     [rsi+r15*8], r12
0x180015592  mov     [rbp+0B0h+var_118], rdi
0x180015596  test    rdi, rdi
0x180015599  jz      short loc_1800155F0
0x18001559b  lea     rdx, [rbp+0B0h+var_118]
0x18001559f  mov     rax, rdi
0x1800155a2  nop     dword ptr [rax+00h]
0x1800155a6  nop     word ptr [rax+rax+00000000h]
0x1800155b0  mov     r9, [rax+20h]
0x1800155b4  mov     [rax+20h], r12
0x1800155b8  mov     rdx, [rdx]
0x1800155bb  add     rdx, 18h
0x1800155bf  mov     rax, [rdx]
0x1800155c2  test    rax, rax
0x1800155c5  jz      short loc_1800155DF
0x1800155c7  nop     word ptr [rax+rax+00000000h]
0x1800155d0  lea     rcx, [rax+20h]
0x1800155d4  mov     rax, [rax+20h]
0x1800155d8  test    rax, rax
0x1800155db  jnz     short loc_1800155D0
0x1800155dd  jmp     short loc_1800155E2
0x1800155df  mov     rcx, rdx
0x1800155e2  mov     [rcx], r9
0x1800155e5  inc     r8d
0x1800155e8  mov     rax, [rdx]
0x1800155eb  test    rax, rax
0x1800155ee  jnz     short loc_1800155B0
0x1800155f0  sub     [rsi+100h], r8d
0x1800155f7  lea     rcx, [rsi+108h]; SRWLock
0x1800155fe  call    cs:__imp_ReleaseSRWLockExclusive
0x180015604  mov     rax, [rsi+148h]
0x18001560b  mov     r14, [rax+20h]
0x18001560f  test    rdi, rdi
0x180015612  jz      loc_18001569C
0x180015618  nop     dword ptr [rax+rax+00000000h]
0x180015620  movzx   ecx, byte ptr [rdi+2Dh]
0x180015624  lea     rbx, [rdi+10h]
0x180015628  mov     eax, 2
0x18001562d  add     ecx, eax
0x18001562f  cmp     ecx, eax
0x180015631  jbe     short loc_18001565B
0x180015633  nop     dword ptr [rax+00h]
0x180015637  nop     word ptr [rax+rax+00000000h]
0x180015640  mov     rcx, [rbx]
0x180015643  movsxd  rdx, eax
0x180015646  inc     eax
0x180015648  add     rdx, rdx
0x18001564b  mov     [rcx+rdx*8+0Dh], r12b
0x180015650  movzx   ecx, byte ptr [rdi+2Dh]
0x180015654  add     ecx, 2
0x180015657  cmp     eax, ecx
0x180015659  jl      short loc_180015640
0x18001565b  movzx   ecx, byte ptr [rdi+2Ch]
0x18001565f  xor     r9d, r9d; RelatedActivityId
0x180015662  mov     rax, [rbx]
0x180015665  xor     r8d, r8d; ActivityId
0x180015668  mov     [rsp+250h+UserData], rax; UserData
0x18001566d  mov     rdx, rdi; EventDescriptor
0x180015670  mov     [rsp+250h+UserDataCount], ecx; UserDataCount
0x180015674  mov     rcx, r14; RegHandle
0x180015677  call    EventWriteTransfer_0
0x18001567c  mov     rdi, [rdi+18h]
0x180015680  mov     rbx, [rbx]
0x180015683  call    cs:__imp_GetProcessHeap
0x180015689  mov     r8, rbx; lpMem
0x18001568c  xor     edx, edx; dwFlags
0x18001568e  mov     rcx, rax; hHeap
0x180015691  call    cs:__imp_HeapFree
0x180015697  test    rdi, rdi
0x18001569a  jnz     short loc_180015620
0x18001569c  inc     r15
0x18001569f  cmp     r15, 20h ; ' '
0x1800156a3  jnz     loc_180015570
0x1800156a9  mov     r15, [rsp+250h+var_20]
0x1800156b1  mov     r14, [rsp+250h+var_18]
0x1800156b9  mov     r12, [rsp+240h]
0x1800156c1  mov     rdi, [rsp+250h+arg_10]
0x1800156c9  mov     rbx, [rsp+250h+arg_8]
0x1800156d1  mov     rcx, [rbp+0B0h+var_28]
0x1800156d8  xor     rcx, rsp; StackCookie
0x1800156db  call    __security_check_cookie
0x1800156e0  add     rsp, 248h
0x1800156e7  pop     rsi
0x1800156e8  pop     rbp
0x1800156e9  retn
```
