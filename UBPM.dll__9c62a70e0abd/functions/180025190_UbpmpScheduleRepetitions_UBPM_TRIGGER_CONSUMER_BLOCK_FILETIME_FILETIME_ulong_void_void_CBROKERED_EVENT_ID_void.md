# UbpmpScheduleRepetitions(_UBPM_TRIGGER_CONSUMER_BLOCK *,_FILETIME *,_FILETIME *,ulong,void *,void *,_CBROKERED_EVENT_ID *,void * *,void * *,_CBROKERED_EVENT_ID *,void * *)

- ea: `0x180025190`
- end: `0x180025a7d`
- name: `?UbpmpScheduleRepetitions@@YAKPEAU_UBPM_TRIGGER_CONSUMER_BLOCK@@PEAU_FILETIME@@1KPEAX2PEAU_CBROKERED_EVENT_ID@@PEAPEAX434@Z`
- size: `2285`
- prototype: `unsigned int(struct _UBPM_TRIGGER_CONSUMER_BLOCK *, struct _FILETIME *, struct _FILETIME *, unsigned int, void *, void *, struct _CBROKERED_EVENT_ID *, void **, void **, struct _CBROKERED_EVENT_ID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024d08`

## callees

- `0x18001af64`
- `0x180025190`
- `0x18004022e`
- `0x180040260`

## import_xrefs

- `EventAggregation!EaCreateAggregation` at `0x1800255a2`
- `EventAggregation!EaCreateAggregation` at `0x1800255f1`
- `EventAggregation!EaCreateAggregation` at `0x1800258aa`
- `EventAggregation!EaCreateAggregation` at `0x180025973`
- `EventAggregation!EaCreateAggregation` at `0x1800255a2`
- `EventAggregation!EaCreateAggregation` at `0x1800255f1`
- `EventAggregation!EaCreateAggregation` at `0x1800258aa`
- `EventAggregation!EaCreateAggregation` at `0x180025973`
- `EventAggregation!EaDeleteAggregation` at `0x180025a1e`
- `EventAggregation!EaDeleteAggregation` at `0x180025a2f`
- `EventAggregation!EaDeleteAggregation` at `0x180025a51`
- `EventAggregation!EaDeleteAggregation` at `0x180025a1e`
- `EventAggregation!EaDeleteAggregation` at `0x180025a2f`
- `EventAggregation!EaDeleteAggregation` at `0x180025a51`
- `EventAggregation!EaGetAggregation` at `0x180025508`
- `EventAggregation!EaGetAggregation` at `0x18002566b`
- `EventAggregation!EaGetAggregation` at `0x180025508`
- `EventAggregation!EaGetAggregation` at `0x18002566b`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180025349`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180025747`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180025349`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180025747`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180025a40`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180025a62`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180025a40`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180025a62`
- `TimeBrokerClient!TbCreateCEvent` at `0x18002541f`
- `TimeBrokerClient!TbCreateCEvent` at `0x18002581d`
- `TimeBrokerClient!TbCreateCEvent` at `0x18002541f`
- `TimeBrokerClient!TbCreateCEvent` at `0x18002581d`

## pseudocode

```c
__int64 __fastcall UbpmpScheduleRepetitions(
        struct _UBPM_TRIGGER_CONSUMER_BLOCK *a1,
        struct _FILETIME *a2,
        struct _FILETIME *a3,
        unsigned int a4,
        void *a5,
        void *a6,
        struct _CBROKERED_EVENT_ID *a7,
        void **a8,
        void **a9,
        struct _CBROKERED_EVENT_ID *a10,
        void **a11)
{
  __int64 v15; // rdi
  const wchar_t *v16; // rdx
  __int64 v17; // rsi
  _WORD *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r9
  _WORD *v21; // rcx
  __int64 v22; // rax
  _BYTE *v23; // rax
  unsigned int Aggregation; // ebx
  _QWORD *v25; // rcx
  int v27; // edx
  const wchar_t *v28; // rcx
  _WORD *v29; // rdx
  _WORD *v30; // rcx
  __int64 v31; // rax
  _BYTE *v32; // rax
  __int64 v33; // [rsp+50h] [rbp-B8h] BYREF
  void *v34; // [rsp+58h] [rbp-B0h]
  void *v35; // [rsp+60h] [rbp-A8h]
  __int64 v36; // [rsp+68h] [rbp-A0h] BYREF
  void *v37; // [rsp+70h] [rbp-98h]
  void **v38; // [rsp+78h] [rbp-90h]
  struct _CBROKERED_EVENT_ID *v39; // [rsp+80h] [rbp-88h]
  void **v40; // [rsp+88h] [rbp-80h]
  struct _CBROKERED_EVENT_ID *v41; // [rsp+90h] [rbp-78h]
  void **v42; // [rsp+98h] [rbp-70h]
  _OWORD v43[3]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v44; // [rsp+D0h] [rbp-38h]
  struct _SYSTEMTIME v45; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v46; // [rsp+E8h] [rbp-20h]
  __int128 v47; // [rsp+F8h] [rbp-10h]
  __int128 v48; // [rsp+108h] [rbp+0h]
  __int128 v49; // [rsp+118h] [rbp+10h]
  __int128 v50; // [rsp+128h] [rbp+20h]
  __int128 v51; // [rsp+138h] [rbp+30h]
  __int128 v52; // [rsp+148h] [rbp+40h]
  __int128 v53; // [rsp+158h] [rbp+50h]
  __int128 v54; // [rsp+168h] [rbp+60h]
  __int128 v55; // [rsp+178h] [rbp+70h]
  __int128 v56; // [rsp+188h] [rbp+80h]
  __int128 v57; // [rsp+198h] [rbp+90h]
  __int128 v58; // [rsp+1A8h] [rbp+A0h]
  __int128 v59; // [rsp+1B8h] [rbp+B0h]
  __int64 v60; // [rsp+1C8h] [rbp+C0h]
  _OWORD v61[3]; // [rsp+1D8h] [rbp+D0h] BYREF
  __int64 v62; // [rsp+208h] [rbp+100h]
  __int64 v63; // [rsp+210h] [rbp+108h] BYREF
  __int64 v64; // [rsp+218h] [rbp+110h] BYREF
  __int128 v65; // [rsp+220h] [rbp+118h] BYREF
  __int128 v66; // [rsp+230h] [rbp+128h]
  __int64 v67; // [rsp+240h] [rbp+138h]
  struct _SYSTEMTIME SystemTime; // [rsp+248h] [rbp+140h] BYREF
  __int128 v69; // [rsp+258h] [rbp+150h]
  __int128 v70; // [rsp+268h] [rbp+160h]
  __int128 v71; // [rsp+278h] [rbp+170h]
  __int128 v72; // [rsp+288h] [rbp+180h]
  __int128 v73; // [rsp+298h] [rbp+190h]
  __int128 v74; // [rsp+2A8h] [rbp+1A0h]
  __int128 v75; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int128 v76; // [rsp+2C8h] [rbp+1C0h]
  __int128 v77; // [rsp+2D8h] [rbp+1D0h]
  __int128 v78; // [rsp+2E8h] [rbp+1E0h]
  __int128 v79; // [rsp+2F8h] [rbp+1F0h]
  __int128 v80; // [rsp+308h] [rbp+200h]
  __int128 v81; // [rsp+318h] [rbp+210h]
  __int128 v82; // [rsp+328h] [rbp+220h]
  __int64 v83; // [rsp+338h] [rbp+230h]

  v37 = a5;
  v39 = a7;
  v38 = a8;
  v42 = a9;
  v41 = a10;
  v40 = a11;
  v44 = 0;
  v33 = 0;
  v63 = 0;
  v35 = 0;
  v36 = 0;
  v62 = 0;
  v34 = 0;
  v64 = 0;
  v67 = 0;
  memset(v43, 0, sizeof(v43));
  memset(v61, 0, sizeof(v61));
  v65 = 0;
  v66 = 0;
  if ( a2 && a3 )
  {
    memset_0(&SystemTime, 0, 0xF8u);
    v15 = 2147483646;
    v16 = L"TsRepetition";
    v17 = 64;
    v18 = (_WORD *)&v75 + 2;
    v19 = 2147483646;
    v20 = 64;
    do
    {
      if ( !v19 )
        break;
      if ( !*v16 )
        break;
      *v18++ = *v16++;
      --v19;
      --v20;
    }
    while ( v20 );
    v21 = v18 - 1;
    if ( v20 )
      v21 = v18;
    *v21 = 0;
    DWORD2(v73) = 0;
    v22 = *((_QWORD *)a1 + 3);
    *(_DWORD *)&SystemTime.wYear = 4;
    *((_QWORD *)&v69 + 1) = a4 | 0x100000000LL;
    v23 = *(_BYTE **)(*(_QWORD *)(v22 + 40) + 32LL);
    BYTE5(v71) = v23 && (*v23 & 0x10) != 0;
    FileTimeToSystemTime(a2, (LPSYSTEMTIME)&SystemTime.wHour);
    v45 = SystemTime;
    v60 = v83;
    v47 = v70;
    v46 = v69;
    v49 = v72;
    v48 = v71;
    v51 = v74;
    v50 = v73;
    v53 = v76;
    v52 = v75;
    v55 = v78;
    v54 = v77;
    v57 = v80;
    v56 = v79;
    v59 = v82;
    v58 = v81;
    Aggregation = TbCreateCEvent(&v45, &v63);
    if ( Aggregation )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v27 = 40;
    }
    else if ( a6 && (Aggregation = EaGetAggregation(a6, &v36)) != 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v27 = 41;
    }
    else
    {
      Aggregation = EaGetAggregation(v37, &v33);
      if ( !Aggregation )
      {
        *((_QWORD *)&v65 + 1) = v63;
        *(_QWORD *)&v43[0] = &v65;
        *(_QWORD *)&v65 = 0;
        v67 = 0;
        v66 = 0;
        *((_QWORD *)&v43[0] + 1) = *(_QWORD *)(v33 + 8);
        if ( a6 )
        {
          Aggregation = EaCreateAggregation(v43, UbpmpRepetitionArrived, 0);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 43;
            goto LABEL_49;
          }
          *((_QWORD *)&v43[0] + 1) = *(_QWORD *)(v36 + 8);
          Aggregation = EaCreateAggregation(v43, 0, &UbpmpRepetitionsStopped);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 44;
            goto LABEL_49;
          }
        }
        else
        {
          Aggregation = EaCreateAggregation(v43, UbpmpRepetitionArrived, &UbpmpRepetitionsStopped);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 45;
            goto LABEL_49;
          }
        }
        if ( a3->dwLowDateTime || a3->dwHighDateTime )
        {
          memset_0(&SystemTime, 0, 0xF8u);
          v28 = L"TsDuration";
          v29 = (_WORD *)&v75 + 2;
          do
          {
            if ( !v15 )
              break;
            if ( !*v28 )
              break;
            *v29++ = *v28++;
            --v15;
            --v17;
          }
          while ( v17 );
          v30 = v29 - 1;
          if ( v17 )
            v30 = v29;
          *v30 = 0;
          DWORD2(v73) = 0;
          *((_QWORD *)&v69 + 1) = 0x100000000LL;
          v31 = *((_QWORD *)a1 + 3);
          *(_DWORD *)&SystemTime.wYear = 4;
          v32 = *(_BYTE **)(*(_QWORD *)(v31 + 40) + 32LL);
          BYTE5(v71) = v32 && (*v32 & 0x10) != 0;
          FileTimeToSystemTime(a3, (LPSYSTEMTIME)&SystemTime.wHour);
          v45 = SystemTime;
          v60 = v83;
          v47 = v70;
          v46 = v69;
          v49 = v72;
          v48 = v71;
          v51 = v74;
          v50 = v73;
          v53 = v76;
          v52 = v75;
          v55 = v78;
          v54 = v77;
          v57 = v80;
          v56 = v79;
          v59 = v82;
          v58 = v81;
          Aggregation = TbCreateCEvent(&v45, &v64);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 46;
            goto LABEL_49;
          }
          *((_QWORD *)&v65 + 1) = v64;
          *(_QWORD *)&v65 = 0;
          *(_QWORD *)&v61[0] = &v65;
          v67 = 0;
          v66 = 0;
          Aggregation = EaCreateAggregation(v61, UbpmpDurationEndArrived, 0);
          if ( Aggregation )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_13;
            v27 = 47;
            goto LABEL_49;
          }
        }
        *v38 = 0;
        *(_QWORD *)v39 = v63;
        *v40 = v34;
        *(_QWORD *)v41 = v64;
        *v42 = v35;
        return Aggregation;
      }
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_13;
      v27 = 42;
    }
LABEL_49:
    WPP_SF_Sd(
      v25[2],
      v27,
      (unsigned int)WPP_dd0be36be19438d0c9cf63f3ad92ceae_Traceguids,
      *(_QWORD *)(*((_QWORD *)a1 + 3) + 8LL),
      Aggregation);
LABEL_13:
    if ( v35 )
      EaDeleteAggregation();
    if ( v63 != __PAIR64__(v63, 0) )
      TbDeleteCEvent();
    if ( v34 )
      EaDeleteAggregation();
    if ( v64 != __PAIR64__(v64, 0) )
      TbDeleteCEvent();
    return Aggregation;
  }
  return 87;
}

```

## disassembly

```asm
0x180025190  mov     r11, rsp
0x180025193  push    rbp
0x180025194  push    rbx
0x180025195  push    r12
0x180025197  push    r13
0x180025199  push    r14
0x18002519b  push    r15
0x18002519d  lea     rbp, [r11-298h]
0x1800251a4  sub     rsp, 368h
0x1800251ab  mov     rax, cs:__security_cookie
0x1800251b2  xor     rax, rsp
0x1800251b5  mov     [rbp+290h+var_50], rax
0x1800251bc  mov     rax, [rbp+290h+arg_20]
0x1800251c3  xorps   xmm0, xmm0
0x1800251c6  mov     r12, [rbp+290h+arg_28]
0x1800251cd  mov     r13, rcx
0x1800251d0  xor     ecx, ecx
0x1800251d2  mov     [rsp+390h+var_328], rax
0x1800251d7  mov     rax, [rbp+290h+arg_30]
0x1800251de  mov     r15d, r9d
0x1800251e1  mov     [rsp+390h+var_318], rax
0x1800251e6  mov     r14, r8
0x1800251e9  mov     rax, [rbp+290h+arg_38]
0x1800251f0  mov     rbx, rdx
0x1800251f3  mov     [rsp+390h+var_320], rax
0x1800251f8  mov     rax, [rbp+290h+arg_40]
0x1800251ff  mov     [rbp+290h+var_300], rax
0x180025203  mov     rax, [rbp+290h+arg_48]
0x18002520a  mov     [rbp+290h+var_308], rax
0x18002520e  mov     rax, [rbp+290h+arg_50]
0x180025215  mov     [rbp+290h+var_310], rax
0x180025219  xor     eax, eax
0x18002521b  mov     [rbp+290h+var_2C8], rax
0x18002521f  mov     [rsp+390h+var_350], rcx
0x180025224  mov     [rsp+390h+var_348], rcx
0x180025229  mov     [rbp+290h+var_188], rcx
0x180025230  mov     [rsp+390h+var_338], rcx
0x180025235  mov     [rsp+390h+var_330], rcx
0x18002523a  mov     [rbp+290h+var_190], rax
0x180025241  mov     [rsp+390h+var_340], rcx
0x180025246  mov     [rbp+290h+var_180], rcx
0x18002524d  mov     [rbp+290h+var_158], rax
0x180025254  movups  [rbp+290h+var_2F8], xmm0
0x180025258  movups  [rbp+290h+var_2E8], xmm0
0x18002525c  movups  [rbp+290h+var_2D8], xmm0
0x180025260  movups  [rbp+290h+var_1C0], xmm0
0x180025267  movups  [rbp+290h+var_1B0], xmm0
0x18002526e  movups  [rbp+290h+var_1A0], xmm0
0x180025275  movups  [rbp+290h+var_178], xmm0
0x18002527c  movups  [rbp+290h+var_168], xmm0
0x180025283  test    rdx, rdx
0x180025286  jz      loc_180025A73
0x18002528c  test    r8, r8
0x18002528f  jz      loc_180025A73
0x180025295  mov     [r11-38h], rsi
0x180025299  lea     rcx, [rbp+290h+SystemTime]; void *
0x1800252a0  xor     edx, edx; Val
0x1800252a2  mov     [r11-40h], rdi
0x1800252a6  mov     r8d, 0F8h; Size
0x1800252ac  call    memset_0
0x1800252b1  mov     edi, 7FFFFFFEh
0x1800252b6  lea     rdx, aTsrepetition; "TsRepetition"
0x1800252bd  mov     esi, 40h ; '@'
0x1800252c2  lea     r8, [rbp+290h+var_DC]
0x1800252c9  mov     ecx, edi
0x1800252cb  mov     r9d, esi
0x1800252ce  xchg    ax, ax
0x1800252d0  test    rcx, rcx
0x1800252d3  jz      short loc_1800252F2
0x1800252d5  movzx   eax, word ptr [rdx]
0x1800252d8  test    ax, ax
0x1800252db  jz      short loc_1800252F2
0x1800252dd  mov     [r8], ax
0x1800252e1  add     rdx, 2
0x1800252e5  add     r8, 2
0x1800252e9  dec     rcx
0x1800252ec  sub     r9, 1
0x1800252f0  jnz     short loc_1800252D0
0x1800252f2  test    r9, r9
0x1800252f5  lea     rcx, [r8-2]
0x1800252f9  cmovnz  rcx, r8
0x1800252fd  xor     eax, eax
0x1800252ff  mov     [rcx], ax
0x180025302  mov     [rbp+290h+var_F8], eax
0x180025308  mov     rax, [r13+18h]
0x18002530c  mov     dword ptr [rbp+290h+SystemTime.wYear], 4
0x180025316  mov     [rbp+290h+var_138], r15d
0x18002531d  mov     [rbp+290h+var_134], 1
0x180025327  mov     rcx, [rax+28h]
0x18002532b  mov     rax, [rcx+20h]
0x18002532f  test    rax, rax
0x180025332  jnz     loc_1800254E0
0x180025338  mov     [rbp+290h+var_11B], 0
0x18002533f  lea     rdx, [rbp+290h+SystemTime.wHour]; lpSystemTime
0x180025346  mov     rcx, rbx; lpFileTime
0x180025349  call    cs:__imp_FileTimeToSystemTime
0x180025350  nop     dword ptr [rax+rax+00h]
0x180025355  movaps  xmm0, xmmword ptr [rbp+290h+SystemTime.wYear]
0x18002535c  lea     rdx, [rbp+290h+var_188]
0x180025363  movaps  xmm1, xmmword ptr [rbp+150h]
0x18002536a  lea     rcx, [rbp+290h+var_2C0]
0x18002536e  mov     rax, [rbp+290h+var_60]
0x180025375  movups  [rbp+290h+var_2C0], xmm0
0x180025379  mov     [rbp+290h+var_1D0], rax
0x180025380  movaps  xmm0, [rbp+290h+var_130]
0x180025387  movups  [rbp+290h+var_2A0], xmm0
0x18002538b  movaps  xmm0, [rbp+290h+var_110]
0x180025392  movups  [rbp+290h+var_2B0], xmm1
0x180025396  movaps  xmm1, xmmword ptr [rbp+170h]
0x18002539d  movups  [rbp+290h+var_280], xmm0
0x1800253a1  movaps  xmm0, [rbp+290h+var_F0]
0x1800253a8  movups  [rbp+290h+var_290], xmm1
0x1800253ac  movaps  xmm1, xmmword ptr [rbp+190h]
0x1800253b3  movups  [rbp+290h+var_260], xmm0
0x1800253b7  movaps  xmm0, [rbp+290h+var_D0]
0x1800253be  movups  [rbp+290h+var_270], xmm1
0x1800253c2  movaps  xmm1, xmmword ptr [rbp+1B0h]
0x1800253c9  movups  [rbp+290h+var_240], xmm0
0x1800253cd  movaps  xmm0, [rbp+290h+var_B0]
0x1800253d4  movups  [rbp+290h+var_250], xmm1
0x1800253d8  movaps  xmm1, [rbp+290h+var_C0]
0x1800253df  movups  [rbp+290h+var_220], xmm0
0x1800253e3  movaps  xmm0, [rbp+290h+var_90]
0x1800253ea  movups  [rbp+290h+var_230], xmm1
0x1800253ee  movaps  xmm1, [rbp+290h+var_A0]
0x1800253f5  movups  [rbp+290h+var_200], xmm0
0x1800253fc  movaps  xmm0, [rbp+290h+var_70]
0x180025403  movups  [rbp+290h+var_210], xmm1
0x18002540a  movaps  xmm1, [rbp+290h+var_80]
0x180025411  movups  [rbp+290h+var_1E0], xmm0
0x180025418  movups  [rbp+290h+var_1F0], xmm1
0x18002541f  call    cs:__imp_TbCreateCEvent
0x180025426  nop     dword ptr [rax+rax+00h]
0x18002542b  mov     ebx, eax
0x18002542d  test    eax, eax
0x18002542f  jz      loc_1800254F5
0x180025435  mov     rcx, cs:WPP_GLOBAL_Control
0x18002543c  lea     rax, WPP_GLOBAL_Control
0x180025443  cmp     rcx, rax
0x180025446  jnz     loc_1800259B4
0x18002544c  mov     rcx, [rsp+390h+var_350]
0x180025451  test    rcx, rcx
0x180025454  jnz     loc_180025A1E
0x18002545a  mov     rcx, [rsp+390h+var_338]
0x18002545f  test    rcx, rcx
0x180025462  jnz     loc_180025A2F
0x180025468  mov     rcx, [rbp+290h+var_188]
0x18002546f  test    ecx, ecx
0x180025471  jnz     loc_180025A40
0x180025477  cmp     dword ptr [rbp+290h+var_188+4], ecx
0x18002547d  jnz     loc_180025A40
0x180025483  mov     rcx, [rsp+390h+var_340]
0x180025488  test    rcx, rcx
0x18002548b  jnz     loc_180025A51
0x180025491  mov     rcx, [rbp+290h+var_180]
0x180025498  test    ecx, ecx
0x18002549a  jnz     loc_180025A62
0x1800254a0  cmp     dword ptr [rbp+290h+var_180+4], ecx
0x1800254a6  jnz     loc_180025A62
0x1800254ac  mov     rsi, [rsp+360h]
0x1800254b4  mov     eax, ebx
0x1800254b6  mov     rdi, [rsp+390h+var_38]
0x1800254be  mov     rcx, [rbp+290h+var_50]
0x1800254c5  xor     rcx, rsp; StackCookie
0x1800254c8  call    __security_check_cookie
0x1800254cd  add     rsp, 368h
0x1800254d4  pop     r15
0x1800254d6  pop     r14
0x1800254d8  pop     r13
0x1800254da  pop     r12
0x1800254dc  pop     rbx
0x1800254dd  pop     rbp
0x1800254de  retn
0x1800254e0  test    byte ptr [rax], 10h
0x1800254e3  jz      loc_180025338
0x1800254e9  mov     [rbp+290h+var_11B], 1
0x1800254f0  jmp     loc_18002533F
0x1800254f5  test    r12, r12
0x1800254f8  jnz     loc_180025663
0x1800254fe  mov     rcx, [rsp+390h+var_328]
0x180025503  lea     rdx, [rsp+390h+var_348]
0x180025508  call    cs:__imp_EaGetAggregation
0x18002550f  nop     dword ptr [rax+rax+00h]
0x180025514  mov     ebx, eax
0x180025516  test    eax, eax
0x180025518  jnz     loc_1800259C8
0x18002551e  mov     eax, dword ptr [rbp+290h+var_188]
0x180025524  lea     rdx, UbpmpRepetitionArrived
0x18002552b  mov     dword ptr [rbp+290h+var_178+8], eax
0x180025531  xor     r9d, r9d
0x180025534  mov     eax, dword ptr [rbp+290h+var_188+4]
0x18002553a  xorps   xmm0, xmm0
0x18002553d  mov     dword ptr [rbp+290h+var_178+0Ch], eax
0x180025543  lea     rax, [rbp+290h+var_178]
0x18002554a  mov     qword ptr [rbp+290h+var_2F8], rax
0x18002554e  mov     rax, [rsp+390h+var_348]
0x180025553  mov     qword ptr [rbp+290h+var_178], 0
0x18002555e  mov     [rbp+290h+var_158], 0
0x180025569  movdqu  [rbp+290h+var_168], xmm0
0x180025571  mov     rcx, [rax+8]
0x180025575  lea     rax, [rsp+390h+var_350]
0x18002557a  mov     [rsp+390h+var_358], rax
0x18002557f  mov     dword ptr [rsp+390h+var_360], r9d
0x180025584  mov     qword ptr [rsp+390h+var_368], r13
0x180025589  mov     qword ptr [rbp+290h+var_2F8+8], rcx
0x18002558d  lea     rcx, [rbp+290h+var_2F8]
0x180025591  mov     [rsp+390h+var_370], r9
0x180025596  test    r12, r12
0x180025599  jz      loc_18002596C
0x18002559f  xor     r8d, r8d
0x1800255a2  call    cs:__imp_EaCreateAggregation
0x1800255a9  nop     dword ptr [rax+rax+00h]
0x1800255ae  mov     ebx, eax
0x1800255b0  test    eax, eax
0x1800255b2  jnz     loc_180025907
0x1800255b8  mov     rax, [rsp+390h+var_330]
0x1800255bd  lea     r8, UbpmpRepetitionsStopped
0x1800255c4  xor     r9d, r9d
0x1800255c7  xor     edx, edx
0x1800255c9  mov     rcx, [rax+8]
0x1800255cd  lea     rax, [rsp+390h+var_338]
0x1800255d2  mov     [rsp+390h+var_358], rax
0x1800255d7  mov     dword ptr [rsp+390h+var_360], ebx
0x1800255db  mov     qword ptr [rbp+290h+var_2F8+8], rcx
0x1800255df  lea     rcx, [rbp+290h+var_2F8]
0x1800255e3  mov     qword ptr [rsp+390h+var_368], r13
0x1800255e8  mov     [rsp+390h+var_370], 0
0x1800255f1  call    cs:__imp_EaCreateAggregation
0x1800255f8  nop     dword ptr [rax+rax+00h]
0x1800255fd  mov     ebx, eax
0x1800255ff  test    eax, eax
0x180025601  jnz     loc_18002592F
0x180025607  cmp     dword ptr [r14], 0
0x18002560b  jnz     loc_1800256AC
0x180025611  cmp     dword ptr [r14+4], 0
0x180025616  jnz     loc_1800256AC
0x18002561c  mov     rcx, [rsp+390h+var_320]
0x180025621  mov     rax, [rsp+390h+var_350]
0x180025626  mov     [rcx], rax
0x180025629  mov     rcx, [rsp+390h+var_318]
0x18002562e  mov     rax, [rbp+290h+var_188]
0x180025635  mov     [rcx], rax
0x180025638  mov     rcx, [rbp+290h+var_310]
0x18002563c  mov     rax, [rsp+390h+var_340]
0x180025641  mov     [rcx], rax
0x180025644  mov     rcx, [rbp+290h+var_308]
0x180025648  mov     rax, [rbp+290h+var_180]
0x18002564f  mov     [rcx], rax
0x180025652  mov     rcx, [rbp+290h+var_300]
0x180025656  mov     rax, [rsp+390h+var_338]
0x18002565b  mov     [rcx], rax
0x18002565e  jmp     loc_1800254AC
0x180025663  lea     rdx, [rsp+390h+var_330]
0x180025668  mov     rcx, r12
0x18002566b  call    cs:__imp_EaGetAggregation
0x180025672  nop     dword ptr [rax+rax+00h]
0x180025677  mov     ebx, eax
0x180025679  test    eax, eax
0x18002567b  jz      loc_1800254FE
0x180025681  mov     rcx, cs:WPP_GLOBAL_Control
0x180025688  lea     rax, WPP_GLOBAL_Control
0x18002568f  cmp     rcx, rax
0x180025692  jz      loc_18002544C
0x180025698  test    byte ptr [rcx+1Ch], 1
0x18002569c  jz      loc_18002544C
0x1800256a2  mov     edx, 29h ; ')'
0x1800256a7  jmp     loc_1800258E6
0x1800256ac  xor     edx, edx; Val
0x1800256ae  lea     rcx, [rbp+290h+SystemTime]; void *
0x1800256b5  mov     r8d, 0F8h; Size
0x1800256bb  call    memset_0
0x1800256c0  lea     rcx, aTsduration; "TsDuration"
0x1800256c7  lea     rdx, [rbp+290h+var_DC]
0x1800256ce  xchg    ax, ax
0x1800256d0  test    rdi, rdi
0x1800256d3  jz      short loc_1800256F1
0x1800256d5  movzx   eax, word ptr [rcx]
0x1800256d8  test    ax, ax
0x1800256db  jz      short loc_1800256F1
0x1800256dd  mov     [rdx], ax
0x1800256e0  add     rcx, 2
0x1800256e4  add     rdx, 2
0x1800256e8  dec     rdi
0x1800256eb  sub     rsi, 1
0x1800256ef  jnz     short loc_1800256D0
0x1800256f1  test    rsi, rsi
0x1800256f4  lea     rcx, [rdx-2]
0x1800256f8  cmovnz  rcx, rdx
0x1800256fc  xor     eax, eax
0x1800256fe  mov     [rcx], ax
0x180025701  mov     [rbp+290h+var_F8], eax
0x180025707  mov     [rbp+290h+var_138], eax
0x18002570d  mov     rax, [r13+18h]
0x180025711  mov     dword ptr [rbp+290h+SystemTime.wYear], 4
0x18002571b  mov     [rbp+290h+var_134], 1
0x180025725  mov     rcx, [rax+28h]
0x180025729  mov     rax, [rcx+20h]
0x18002572d  test    rax, rax
0x180025730  jnz     loc_180025957
0x180025736  mov     [rbp+290h+var_11B], 0
  ... truncated ...
```
