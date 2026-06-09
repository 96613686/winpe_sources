# CmsBPlusTable::AbortUndoRecords(CmsTransactionContext *,SmsUndoRecord *)

- ea: `0x1400d7830`
- end: `0x1400d96e5`
- name: `?AbortUndoRecords@CmsBPlusTable@@SAJPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@@Z`
- size: `7861`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *, struct SmsUndoRecord *)`
- caller_count: `2`
- callee_count: `67`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14007e738`
- `0x14008c930`

## callees

- `0x140004870`
- `0x140004be0`
- `0x1400057e0`
- `0x140082fe4`
- `0x140083074`
- `0x1400834f0`
- `0x14008356c`
- `0x14008c8a0`
- `0x140090d88`
- `0x140096f1c`
- `0x14009aabc`
- `0x1400a2a8c`
- `0x1400a9780`
- `0x1400ac4fc`
- `0x1400afa88`
- `0x1400b059c`
- `0x1400b0ddc`
- `0x1400b2758`
- `0x1400b5240`
- `0x1400b55b0`
- `0x1400b5a1c`
- `0x1400b6b8c`
- `0x1400b6bbc`
- `0x1400b6efc`
- `0x1400b7390`
- `0x1400b769c`
- `0x1400b7990`
- `0x1400b7a34`
- `0x1400b7b3c`
- `0x1400b81a8`
- `0x1400b82ac`
- `0x1400b82d8`
- `0x1400b9b0c`
- `0x1400bc790`
- `0x1400c1e1c`
- `0x1400c4728`
- `0x1400c47c8`
- `0x1400c7354`
- `0x1400c8b24`
- `0x1400cb954`
- `0x1400cd048`
- `0x1400cd160`
- `0x1400cf2bc`
- `0x1400d365c`
- `0x1400d38f0`
- `0x1400d7830`
- `0x1400da014`
- `0x1400da4cc`
- `0x1400da534`
- `0x1400da764`

## import_xrefs

- `ntdll!RtlCopyBitMap` at `0x1400d93ca`
- `ntdll!RtlCopyBitMap` at `0x1400d94d2`
- `ntdll!RtlCopyBitMap` at `0x1400d93ca`
- `ntdll!RtlCopyBitMap` at `0x1400d94d2`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400d7e4d`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1400d7e4d`
- `ntdll!RtlInitializeBitMap` at `0x1400d93af`
- `ntdll!RtlInitializeBitMap` at `0x1400d94ba`
- `ntdll!RtlInitializeBitMap` at `0x1400d93af`
- `ntdll!RtlInitializeBitMap` at `0x1400d94ba`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400d7e6d`
- `ntdll!RtlReleaseSRWLockShared` at `0x1400d7e6d`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400d7e7b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1400d7e7b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CmsBPlusTable::AbortUndoRecords(
        SmsUndoRecord **a1,
        struct SmsUndoRecord *a2,
        __int64 a3,
        __int64 a4)
{
  struct SmsUndoRecord *v4; // r13
  struct CmsTransactionContext *v5; // r14
  SmsUndoRecord *v6; // rcx
  int v7; // r15d
  SmsUndoRecord *v8; // rsi
  int valid; // r12d
  __int64 v10; // rax
  __int64 v11; // r13
  struct CmsTransactionContext *v12; // rdx
  unsigned int *v13; // rdi
  unsigned int v14; // eax
  int v15; // ecx
  __int64 v16; // r15
  struct _SmsIndexEntry *UndoIndexEntry; // rax
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rax
  struct SmsPage *v21; // r8
  CmsVolume *v22; // r13
  __int64 v23; // r12
  unsigned int v24; // ebx
  int *v25; // rcx
  int v26; // r8d
  int *v27; // rdx
  int v28; // eax
  unsigned int v29; // ecx
  int v30; // eax
  __int64 v31; // rbx
  CmsTableSetBase *v32; // rcx
  CmsVolume *v33; // rcx
  int v34; // ecx
  int v35; // ecx
  unsigned __int64 v36; // rcx
  int v37; // ecx
  __int64 v38; // r8
  unsigned int *v39; // rcx
  struct SmsContainer *v40; // r11
  struct SmsPage **v41; // r15
  unsigned int v42; // ecx
  struct SmsPage *v43; // rdx
  int v44; // r8d
  struct _SmsIndexHeader **v45; // r8
  unsigned int *v46; // rcx
  __int64 v47; // rcx
  struct _SmsIndexEntry *v48; // rax
  __m128i *v49; // rax
  unsigned int v50; // r11d
  int v51; // r11d
  struct _SmsIndexHeader *v52; // r10
  struct _SmsIndexEntry *v53; // rax
  CmsBPlusTable *v54; // rcx
  struct _SmsIndexEntry *v55; // r9
  struct _SmsIndexEntry *v56; // rax
  unsigned int *v57; // r10
  unsigned __int8 v58; // r9
  struct _SmsIndexEntry *v59; // rax
  __int16 v60; // r9
  __int64 v61; // r8
  int v62; // ecx
  int v63; // ecx
  int v64; // ecx
  int v65; // ecx
  size_t v66; // r8
  char *v67; // rcx
  const void *v68; // rdx
  unsigned __int64 v69; // rbx
  __int64 v70; // r13
  __int64 *v71; // r15
  __int64 v72; // rcx
  unsigned int v73; // r15d
  unsigned __int64 v74; // rax
  _BYTE *v75; // r12
  struct CmsTransactionContext *v76; // rax
  struct _RTL_BITMAP v77; // xmm1
  unsigned __int64 v78; // r8
  CmsVolumeContainer *v79; // rcx
  struct SmsPage **v80; // r12
  struct _SmsIndexHeader *v81; // rdi
  unsigned __int16 v82; // r9
  struct _SmsIndexHeader *v83; // rbx
  struct CmsTransactionContext *v84; // rdx
  CmsBPlusTable *v85; // rcx
  struct CmsTransactionContext *v86; // rdx
  CmsBPlusTable *v87; // rcx
  struct CmsTransactionContext *v88; // rdx
  CmsVolume *v89; // rcx
  struct CmsBPlusTable *v90; // r8
  struct SmsPage *v91; // rcx
  int v92; // r12d
  int v93; // edx
  struct SmsContainer *v94; // r10
  int v95; // r15d
  CmsVolume *v96; // r13
  __int64 v97; // r8
  __int64 v98; // rdi
  unsigned int v99; // ebx
  int v100; // eax
  bool v101; // zf
  __int64 v102; // rbx
  struct _SmsIndexHeader *IndexHeaderInPage; // rdi
  unsigned int v104; // r11d
  unsigned int k; // r10d
  int v106; // r10d
  struct CmsTransactionContext *v107; // rdx
  __int64 v108; // rcx
  struct CmsBPlusTable *v109; // r8
  unsigned int v110; // r13d
  unsigned int v111; // r10d
  unsigned int v112; // r12d
  unsigned int j; // r11d
  int v114; // r11d
  __int64 v115; // rax
  char *v116; // rcx
  __int64 v117; // rax
  struct CmsTransactionContext *v118; // rdx
  CmsBPlusTable *v119; // rcx
  struct _SmsIndexEntry *v120; // rax
  __m128i *v121; // rax
  struct CmsTransactionContext *v122; // rdx
  CmsBPlusTable *v123; // rcx
  __int64 v124; // r11
  __m128i v125; // xmm1
  char v126; // r10
  struct _SmsIndexEntry *v127; // rax
  SmsUndoRecord *v128; // rcx
  unsigned int v129; // edi
  struct _SmsIndexEntry *v130; // rax
  __int64 v131; // r11
  __int16 v132; // dx
  unsigned __int64 v133; // xmm1_8
  __int64 v134; // rcx
  __int64 v135; // r15
  struct _SmsIndexEntry *v136; // rax
  __int128 *v137; // rdx
  __int64 v138; // r11
  __int16 v139; // r10
  __int64 v140; // rcx
  struct CmsTransactionContext *v141; // rdx
  CmsBPlusTable *v142; // rcx
  __int64 v143; // rcx
  __int64 v144; // rbx
  CmsVolume *v145; // r13
  unsigned int v146; // r9d
  __int64 v147; // r15
  unsigned int v148; // r12d
  int v149; // eax
  unsigned int v150; // eax
  int v151; // ecx
  int v152; // ecx
  int v153; // ecx
  int v154; // ecx
  int v155; // ecx
  __int64 v156; // rax
  __int64 i; // rax
  __int64 v158; // rax
  __int64 v159; // rax
  __int64 v160; // rax
  __int64 v161; // rdx
  char v162; // r8
  int v163; // ecx
  int v164; // ecx
  int v165; // ecx
  unsigned int *v166; // rdx
  size_t v167; // r8
  char *v168; // rdi
  unsigned int v169; // ebx
  int v170; // edx
  struct _SmsIndexEntry *v171; // rax
  unsigned int v172; // edx
  __int64 v173; // r9
  __int64 v174; // rbx
  __int64 v175; // rdx
  signed __int64 v176; // rax
  __int64 v177; // rtt
  CmsStream *v178; // rbx
  CmsReferenced *v179; // rcx
  CmsReferenced **v180; // rbx
  int v181; // ecx
  int v182; // ecx
  int v183; // ecx
  int v184; // ecx
  int v185; // ecx
  struct SmsTrashCleanerEntry **v186; // rbx
  CmsTrashTable *v187; // rcx
  struct _SmsIndexEntry *v188; // rax
  __int64 v189; // rcx
  __int16 v190; // di
  struct CmsTransactionContext *v191; // rdx
  __int64 v192; // r8
  unsigned __int64 v193; // rbx
  CmsBPlusTable *v194; // rcx
  int v195; // ecx
  char *v196; // rax
  struct _SmsIndexEntry *v197; // rax
  __m128i *v198; // rax
  __int64 v199; // rcx
  struct _SmsIndexEntry *v200; // rcx
  unsigned int v201; // r8d
  _SmsIndexHeader *v202; // r9
  __int64 v203; // rcx
  __int64 v204; // rdx
  struct _SmsIndexEntry *v205; // rax
  __m128i *v206; // rax
  __int64 v207; // rbx
  __int64 v208; // rcx
  __int64 v209; // rdx
  unsigned int v210; // eax
  __int64 v211; // rdi
  unsigned __int64 v212; // rax
  unsigned __int64 v213; // rcx
  unsigned int v214; // eax
  __int64 v215; // rdx
  CmsReferenced **v216; // rbx
  __int64 v217; // r9
  int v218; // ecx
  int v219; // ecx
  int v220; // ecx
  int v221; // ecx
  __int64 v222; // rcx
  int v223; // ecx
  int v224; // ecx
  int v225; // ecx
  int v226; // ecx
  int v227; // ecx
  struct SmsTableSetEntry *Entry; // rax
  char v229; // r10
  __int64 v230; // rdx
  __int64 v231; // rcx
  __int64 v232; // r9
  int v233; // eax
  __int64 v234; // rcx
  __int64 v235; // rdx
  unsigned __int64 v236; // rax
  __int64 v237; // r11
  int updated; // eax
  int v239; // ecx
  int v240; // ecx
  int v241; // ecx
  int v242; // ecx
  CmsBlockRefcount *v243; // rcx
  __int64 v244; // r8
  char v245; // al
  __int64 v246; // rdx
  unsigned int *v247; // r15
  struct SmsPage *v248; // r8
  CmsVolume *v249; // r12
  struct SmsPage *v250; // rdi
  unsigned int v251; // ebx
  int v252; // eax
  ULONG *v253; // rdx
  __int64 v254; // rbx
  SmsPage *v255; // rcx
  SmsPage *v256; // rcx
  CmsVolume *v257; // r15
  unsigned int v258; // r9d
  __int64 v259; // r8
  __int64 v260; // rsi
  unsigned int v261; // ebx
  int v262; // eax
  __int64 v263; // rdi
  struct SmsPage **v265; // [rsp+20h] [rbp-E0h]
  bool v266; // [rsp+20h] [rbp-E0h]
  struct CmsBPlusTable *v267; // [rsp+30h] [rbp-D0h]
  SmsUndoRecord *v269; // [rsp+58h] [rbp-A8h]
  struct SmsContainer *v270; // [rsp+60h] [rbp-A0h] BYREF
  int FirstIndexEntry; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v272; // [rsp+6Ch] [rbp-94h] BYREF
  struct CmsTransactionContext *v273; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v274[8]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v275; // [rsp+80h] [rbp-80h] BYREF
  __int64 v276; // [rsp+90h] [rbp-70h] BYREF
  __int64 v277; // [rsp+98h] [rbp-68h]
  struct _RTL_BITMAP v278; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v279; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v280; // [rsp+C0h] [rbp-40h]
  __int128 *v281; // [rsp+C8h] [rbp-38h]
  __int64 v282; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v283; // [rsp+D8h] [rbp-28h] BYREF
  __m128i v284; // [rsp+E8h] [rbp-18h]
  struct _RTL_BITMAP v285; // [rsp+100h] [rbp+0h] BYREF
  int v286; // [rsp+110h] [rbp+10h]
  __int64 v287; // [rsp+118h] [rbp+18h]
  CmsBPlusTable *v288; // [rsp+120h] [rbp+20h] BYREF
  char *v289; // [rsp+128h] [rbp+28h]
  __int64 v290; // [rsp+130h] [rbp+30h] BYREF
  __int64 v291; // [rsp+138h] [rbp+38h]
  __int128 v292; // [rsp+140h] [rbp+40h] BYREF
  __int64 v293; // [rsp+150h] [rbp+50h] BYREF
  __int64 v294; // [rsp+158h] [rbp+58h]
  struct CmsTransactionContext *v295; // [rsp+160h] [rbp+60h]
  __int64 v296; // [rsp+168h] [rbp+68h]
  int v297; // [rsp+170h] [rbp+70h] BYREF
  __int16 v298; // [rsp+174h] [rbp+74h]
  __int128 *v299; // [rsp+178h] [rbp+78h]
  struct SmsPage *v300[2]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v301; // [rsp+190h] [rbp+90h]
  __int64 v302; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 v303; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v304; // [rsp+1B0h] [rbp+B0h]
  __int64 v305; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v306; // [rsp+1C0h] [rbp+C0h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v308; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v309; // [rsp+1E8h] [rbp+E8h]
  __int64 v310; // [rsp+1F8h] [rbp+F8h]
  char v311[16]; // [rsp+200h] [rbp+100h] BYREF
  __int128 v312; // [rsp+210h] [rbp+110h] BYREF

  v4 = a2;
  v5 = (struct CmsTransactionContext *)a1;
  v295 = (struct CmsTransactionContext *)a1;
  v6 = a1[18];
  v269 = v6;
  v7 = 0;
  v8 = 0;
  valid = 0;
  v10 = *(_QWORD *)v5;
  v296 = *(_QWORD *)v5 & 0x40LL;
  *(_QWORD *)v5 = v10 & 0xFFFFFFFFFFFFFFBFuLL;
  while ( 1 )
  {
    v8 = v8 ? *(SmsUndoRecord **)v8 : v6;
    if ( v8 == v4 )
      break;
    v11 = *((_QWORD *)v8 + 5);
    *(_QWORD *)&v278.SizeOfBitMap = v11;
    v12 = 0;
    v273 = 0;
    v282 = 0;
    v272 = 0;
    v270 = 0;
    v13 = (unsigned int *)((char *)v8 + 16);
    if ( (*((_BYTE *)v8 + 20) & 1) == 0
      || ((v14 = *v13, *v13 > 0x1F) || (v15 = -1073741676, !_bittest(&v15, v14))) && v14 != 32 )
    {
      valid = 0;
      FirstIndexEntry = 0;
      v21 = (struct SmsPage *)*((_QWORD *)v8 + 6);
      if ( v21 )
      {
        *((_QWORD *)v8 + 7) = CmsCompositeBase::FindIndexHeaderInPage(*(CmsCompositeBase **)(v11 + 112), v5, v21, a4);
        *((_QWORD *)v8 + 8) = 0;
        goto LABEL_42;
      }
      v29 = *v13;
      if ( *v13 - 5 <= 1 )
      {
        v31 = *((_QWORD *)v8 + 3);
        *(_QWORD *)v31 = CmsCompositeBase::FindIndexHeaderInPage(
                           *(CmsCompositeBase **)(v11 + 112),
                           v5,
                           *(struct SmsPage **)(v31 + 8),
                           a4);
        goto LABEL_41;
      }
      if ( v29 == 20 )
      {
        LOBYTE(v265) = 4;
        v30 = CmsCompositeBase::PinRoot(*(_QWORD *)(v11 + 112), v5, v11, &v282);
      }
      else
      {
        if ( v29 != 12 )
          goto LABEL_43;
        v265 = (struct SmsPage **)&FirstIndexEntry;
        v30 = CmsBPlusTable::PinDataWithRoot(v11, v5, 4, &v273);
      }
      valid = v30;
      FirstIndexEntry = v30;
      ++*(_DWORD *)(*((_QWORD *)v8 + 6) + 388LL);
      goto LABEL_41;
    }
    v16 = *((_QWORD *)v8 + 6);
    *((_OWORD *)v8 + 3) = 0;
    *((_OWORD *)v8 + 4) = 0;
    *((_QWORD *)v8 + 10) = 0;
    UndoIndexEntry = SmsUndoRecord::MmsGetUndoIndexEntry(v8);
    v20 = _SmsIndexEntry::ToKey(UndoIndexEntry, v311, v18, v19);
    v267 = (struct CmsBPlusTable *)&v272;
    LOBYTE(v265) = 1;
    FirstIndexEntry = CmsBPlusTable::FindFirstIndexEntry(v11, v5, v20, (char *)v8 + 48);
    ++*(_DWORD *)(*((_QWORD *)v8 + 6) + 388LL);
    if ( !v16 )
      goto LABEL_31;
    v22 = (CmsVolume *)*((_QWORD *)v5 + 1);
    LODWORD(a4) = 7;
    do
    {
      v23 = 0;
      v24 = a4;
      if ( !*(_QWORD *)(v16 + 304) )
        goto LABEL_29;
      v25 = (int *)(v16 + 312);
      if ( (a4 & 1) != 0 && (v26 = *v25, *(_DWORD *)(v16 + 384) == *v25) )
      {
        v23 = *(_QWORD *)(v16 + 304);
        v27 = (int *)(v16 + 316);
        if ( (a4 & 4) == 0 )
          goto LABEL_27;
        v28 = *v27;
        if ( *(_DWORD *)(v16 + 388) != *v27 )
        {
          v24 = a4 & 0xFFFFFFFB;
          goto LABEL_27;
        }
      }
      else
      {
        if ( (a4 & 4) == 0 )
          goto LABEL_29;
        v27 = (int *)(v16 + 316);
        v28 = *(_DWORD *)(v16 + 316);
        if ( *(_DWORD *)(v16 + 388) != v28 )
          goto LABEL_29;
        v26 = *v25;
        v23 = *(_QWORD *)(v16 + 304);
      }
      *v27 = v28 - 1;
LABEL_27:
      *v25 = v26 - 1;
      if ( v26 == 1 )
        *(_QWORD *)(v16 + 304) = 0;
LABEL_29:
      CmsVolume::UnpinInternal(v22, v5, (struct SmsPage *)v16, a4);
      v16 = v23;
      a4 = v24;
    }
    while ( v23 );
    v11 = *(_QWORD *)&v278.SizeOfBitMap;
LABEL_31:
    valid = FirstIndexEntry;
    v7 = 0;
LABEL_41:
    if ( valid < 0 )
      goto LABEL_56;
LABEL_42:
    v12 = v273;
LABEL_43:
    v283 = 0;
    v284.m128i_i32[0] = 0;
    v284.m128i_i64[1] = 0;
    v32 = (CmsTableSetBase *)*v13;
    if ( (int)v32 > 27 )
    {
      if ( (int)v32 > 40 )
      {
        if ( (int)v32 > 47 )
        {
          v239 = (_DWORD)v32 - 48;
          if ( v239 )
          {
            v240 = v239 - 1;
            if ( v240 )
            {
              v241 = v240 - 1;
              if ( !v241 )
              {
                CmsVolumeContainer::CleanupCompactionContext(
                  *(CmsVolumeContainer **)(*((_QWORD *)v5 + 1) + 3176LL),
                  v5,
                  *((struct SmsCompactionContext **)v8 + 3));
                goto LABEL_76;
              }
              v242 = v241 - 1;
              if ( v242 )
              {
                if ( v242 == 1 )
                {
                  CmsEmbeddedComposite::SetRootSizeBytes(
                    *(CmsEmbeddedComposite **)(*((_QWORD *)v8 + 5) + 112LL),
                    v5,
                    *((struct CmsBPlusTable **)v8 + 5),
                    **((_DWORD **)v8 + 3));
                  goto LABEL_76;
                }
                goto LABEL_56;
              }
              goto LABEL_329;
            }
            updated = CmsVolumeContainer::AdjustCompressedContainerCounts(
                        *(CmsVolumeContainer **)(*((_QWORD *)v5 + 1) + 3176LL),
                        v5,
                        -**((_DWORD **)v8 + 3),
                        -*(_DWORD *)(*((_QWORD *)v8 + 3) + 4LL),
                        -*(_DWORD *)(*((_QWORD *)v8 + 3) + 8LL),
                        -*(_DWORD *)(*((_QWORD *)v8 + 3) + 12LL));
LABEL_322:
            valid = updated;
            goto LABEL_76;
          }
          v246 = *(_QWORD *)(*((_QWORD *)v5 + 1) + 3176LL);
          v247 = (unsigned int *)*((_QWORD *)v8 + 3);
          BitMapHeader = 0;
          v312 = 0;
          *(_OWORD *)v300 = 0;
          v301 = 0;
          v302 = 0;
          *(_QWORD *)&v312 = *(_QWORD *)(*(_QWORD *)v247 + 592LL);
          *((_QWORD *)&v312 + 1) = 0x300000000LL;
          v297 = 16;
          v298 = 0;
          v299 = &v312;
          v265 = v300;
          valid = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, int *, __int64))(**(_QWORD **)(v246 + 64) + 80LL))(
                    *(_QWORD *)(v246 + 64),
                    v5,
                    &v297,
                    1);
          FirstIndexEntry = valid;
          RtlInitializeBitMap(
            &BitMapHeader,
            (PULONG)(v301
                   + *(unsigned __int16 *)(v301 + 10)
                   + *(unsigned __int8 *)(v301 + *(unsigned __int16 *)(v301 + 10) + 40)),
            *(_DWORD *)(*((_QWORD *)v5 + 1) + 84LL));
          RtlCopyBitMap(v247 + 6, &BitMapHeader, v247[2]);
          v248 = v300[0];
          v40 = 0;
          if ( !v300[0] )
            goto LABEL_352;
          v249 = (CmsVolume *)*((_QWORD *)v5 + 1);
          LODWORD(a4) = 3;
          do
          {
            v250 = 0;
            v251 = a4;
            if ( !*((_QWORD *)v248 + 38) )
              goto LABEL_350;
            if ( (a4 & 1) != 0 && *((_DWORD *)v248 + 96) == *((_DWORD *)v248 + 78) )
            {
              v250 = (struct SmsPage *)*((_QWORD *)v248 + 38);
              if ( (a4 & 4) == 0 )
                goto LABEL_348;
            }
            else
            {
              if ( (a4 & 4) == 0 || *((_DWORD *)v248 + 97) != *((_DWORD *)v248 + 79) )
                goto LABEL_350;
              v250 = (struct SmsPage *)*((_QWORD *)v248 + 38);
            }
            v252 = *((_DWORD *)v248 + 79);
            if ( *((_DWORD *)v248 + 97) == v252 )
              *((_DWORD *)v248 + 79) = v252 - 1;
            else
              v251 = a4 & 0xFFFFFFFB;
LABEL_348:
            v101 = (*((_DWORD *)v248 + 78))-- == 1;
            if ( v101 )
              *((_QWORD *)v248 + 38) = 0;
LABEL_350:
            CmsVolume::UnpinInternal(v249, v5, v248, a4);
            v248 = v250;
            a4 = v251;
            v40 = 0;
          }
          while ( v250 );
          v300[0] = 0;
          valid = FirstIndexEntry;
LABEL_352:
          v253 = *(ULONG **)(*(_QWORD *)v247 + 168LL);
          if ( v253 )
          {
            v278 = 0;
            RtlInitializeBitMap(&v278, v253, *(_DWORD *)(*((_QWORD *)v5 + 1) + 84LL));
            RtlCopyBitMap(v247 + 6, &v278, v247[2]);
            goto LABEL_114;
          }
LABEL_57:
          v41 = (struct SmsPage **)v270;
LABEL_58:
          v42 = 1;
          v4 = a2;
          if ( v41 )
          {
            while ( v42 != -1 )
            {
              v43 = v41[v42];
              if ( v43 )
              {
                v44 = *((_DWORD *)v41 + v42 + 4);
                if ( v44 == 1 )
                {
                  *((_QWORD *)v43 + 42) = v40;
                  *((_QWORD *)v41[v42] + 31) = v40;
                }
                else if ( v44 == 2 )
                {
                  *((_QWORD *)v43 + 43) = v40;
                }
              }
              --v42;
            }
            v5 = v295;
            goto LABEL_115;
          }
          v6 = v269;
LABEL_6:
          v7 = 0;
        }
        else
        {
          if ( (_DWORD)v32 == 47 )
          {
            updated = CmsVolumeContainer::UpdateContainerRanges(
                        *(CmsVolumeContainer **)(*((_QWORD *)v5 + 1) + 3176LL),
                        v5,
                        **((struct SmsContainer ***)v8 + 3),
                        (struct _RANGE *)(*((_QWORD *)v8 + 3) + 8LL),
                        *(_DWORD *)(*((_QWORD *)v8 + 3) + 72LL));
            goto LABEL_322;
          }
          v223 = (_DWORD)v32 - 41;
          if ( v223 )
          {
            v224 = v223 - 1;
            if ( !v224 )
            {
              v237 = *((_QWORD *)v8 + 3);
              v178 = *(CmsStream **)(v237 + 8);
              v267 = (struct CmsBPlusTable *)((v237 + 40) & -(__int64)((*(_BYTE *)v237 & 2) != 0));
              LOBYTE(v265) = 0;
              v233 = CmsStream::UpdateStreamSummary(v178, v5, -*(_QWORD *)(v237 + 16), -*(_QWORD *)(v237 + 24));
              goto LABEL_314;
            }
            v225 = v224 - 1;
            if ( v225 )
            {
              v226 = v225 - 1;
              if ( !v226 )
              {
                v232 = *((_QWORD *)v8 + 3);
                v178 = *(CmsStream **)v232;
                v233 = CmsStream::UpdateStreamUserPayload(
                         *(CmsStream **)v232,
                         v5,
                         (void *)(v232 + 12),
                         *(_DWORD *)(v232 + 8));
LABEL_314:
                valid = v233;
                goto LABEL_240;
              }
              v227 = v226 - 1;
              if ( !v227 )
              {
                v230 = *((_QWORD *)v8 + 3);
                v231 = *(_QWORD *)(v11 + 88);
                *(_OWORD *)(v231 + 8) = *(_OWORD *)(v230 + 8);
                *(_OWORD *)(v231 + 24) = *(_OWORD *)(v230 + 24);
                *(_OWORD *)(v231 + 40) = *(_OWORD *)(v230 + 40);
                *(_QWORD *)(v231 + 56) = *(_QWORD *)(v230 + 56);
                v66 = *(unsigned int *)(v231 + 64);
                v68 = (const void *)(v230 + 68);
                v67 = (char *)(v231 + 68);
                goto LABEL_85;
              }
              if ( v227 != 1 )
                goto LABEL_56;
              v4 = a2;
              v6 = v269;
              if ( (*(_BYTE *)v5 & 2) != 0 )
              {
                Entry = CmsTableSetBase::GetEntry(
                          **((CmsTableSetBase ***)v8 + 3),
                          *(_QWORD *)(*((_QWORD *)v8 + 3) + 8LL),
                          (bool)v21);
                *((_BYTE *)Entry + 53) = v229;
                goto LABEL_77;
              }
            }
            else
            {
              v234 = *((_QWORD *)v8 + 3);
              v235 = *(_QWORD *)(v11 + 88);
              _InterlockedAdd64((volatile signed __int64 *)(v235 + 40), -*(_QWORD *)(v234 + 16));
              v236 = *(_QWORD *)(v234 + 24);
              v4 = a2;
              v6 = v269;
              if ( v236 && (*(_BYTE *)(v235 + 8) & 8) != 0 )
                _InterlockedAdd64((volatile signed __int64 *)(v235 + 56), v236);
            }
          }
          else
          {
            v4 = a2;
            v6 = v269;
            if ( (*(_BYTE *)v5 & 2) != 0 )
            {
              *(_BYTE *)(*(_QWORD *)(*((_QWORD *)v8 + 3) + 8LL) + 48LL) &= ~0x10u;
              goto LABEL_220;
            }
          }
        }
      }
      else
      {
        if ( (_DWORD)v32 == 40 )
        {
          CmsTableSetBase::ProcessUndoAttachNew(v32, v5, *((struct SmsUndoTableSetAttachNew **)v8 + 3));
          goto LABEL_76;
        }
        if ( (int)v32 > 34 )
        {
          v218 = (_DWORD)v32 - 35;
          v4 = a2;
          if ( !v218 )
            goto LABEL_220;
          v219 = v218 - 1;
          if ( !v219 )
          {
            v41 = (struct SmsPage **)*((_QWORD *)v8 + 3);
            v40 = 0;
            goto LABEL_58;
          }
          v220 = v219 - 1;
          if ( v220 )
          {
            v221 = v220 - 1;
            if ( v221 )
            {
              if ( v221 == 1 )
              {
                (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *))(***((_QWORD ***)v8 + 3) + 32LL))(
                  **((_QWORD **)v8 + 3),
                  v5);
                goto LABEL_77;
              }
              goto LABEL_56;
            }
            v6 = v269;
            if ( (*(_BYTE *)v5 & 2) != 0 )
            {
              *(_BYTE *)(**((_QWORD **)v8 + 3) + 336LL) &= ~0x10u;
              goto LABEL_220;
            }
          }
          else
          {
            v6 = v269;
            if ( (*(_BYTE *)v5 & 2) != 0 )
            {
              v222 = *((_QWORD *)v8 + 3);
              LODWORD(v265) = *(_DWORD *)(v222 + 20);
              CmsTableSetBase::UpdateSetSummary(
                *(_QWORD *)v222,
                v5,
                (unsigned int)-*(_DWORD *)(v222 + 8),
                (unsigned int)-*(_DWORD *)(v222 + 12));
              goto LABEL_77;
            }
          }
        }
        else
        {
          if ( (_DWORD)v32 == 34 )
          {
            v217 = *((_QWORD *)v8 + 3);
            v285 = *(struct _RTL_BITMAP *)v217;
            v267 = (struct CmsBPlusTable *)((v217 + 24) & -(__int64)(*(_DWORD *)(v217 + 20) != 0));
            LOWORD(v265) = *(_WORD *)(v217 + 18);
            LOBYTE(v217) = *(_BYTE *)(v217 + 16);
            CmsVolumeContainer::SetContainerRangeValid(*(_QWORD *)(*((_QWORD *)v5 + 1) + 3176LL), v5, &v285, v217);
            goto LABEL_76;
          }
          v181 = (_DWORD)v32 - 28;
          if ( v181 )
          {
            v182 = v181 - 1;
            if ( !v182 )
            {
              v216 = (CmsReferenced **)*((_QWORD *)v8 + 3);
              v270 = (struct SmsContainer *)(v216 + 4);
              v285 = *(struct _RTL_BITMAP *)(v216 + 1);
              LOBYTE(v267) = *((_BYTE *)v216 + 25);
              LOBYTE(v265) = *((_BYTE *)v216 + 24) != 0;
              valid = CmsStream::SetRangeValidState(*v216, v5, v21, &v285);
              CmsReferenced::Release(*v216);
              goto LABEL_56;
            }
            v183 = v182 - 1;
            if ( !v183 )
            {
              v205 = SmsUndoRecord::MmsGetUndoIndexEntry(v8);
              v206 = (__m128i *)_SmsIndexEntry::ToRow(v205, v300);
              v283 = *v206;
              v284 = v206[1];
              v207 = *((_QWORD *)v8 + 3);
              _SmsIndexEntry::GetRangeKey(v207, &v276);
              v208 = v277;
              v209 = v276;
              if ( (unsigned __int64)(v277 + v276 - 1) <= *((_QWORD *)v8 + 10) )
              {
                CmsBPlusTable::InsertSimple(
                  (CmsBPlusTable *)v11,
                  v5,
                  (const struct _CmsRow *)&v283,
                  (SmsUndoRecord *)((char *)v8 + 48),
                  0,
                  0);
                _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)v8 + 5) + 48LL));
                goto LABEL_114;
              }
              if ( (*(_BYTE *)(v207 + 8) & 0x40) != 0 )
                v210 = (*(unsigned __int16 *)(v207 + 10) + 7) & 0xFFFFFFF8;
              else
                v210 = *(_DWORD *)v207;
              v211 = v207 + v210;
              v279 = 0;
              LODWORD(v280) = 0;
              v281 = 0;
              while ( 1 )
              {
                v293 = v209;
                v212 = v209 + v208 - 1;
                v213 = *((_QWORD *)v8 + 10);
                if ( v213 >= v212 )
                  v213 = v212;
                v294 = v213 - v209 + 1;
                v214 = (*(_BYTE *)(v207 + 8) & 0x40) != 0
                     ? (*(unsigned __int16 *)(v207 + 10) + 7) & 0xFFFFFFF8
                     : *(_DWORD *)v207;
                LODWORD(v265) = *((_DWORD *)v8 + 3) - v214;
                (*(void (__fastcall **)(struct CmsTransactionContext *, __m128i *, __int64 *, __int64, struct SmsPage **, __int128 *))(*(_QWORD *)(v11 + 24) + 80LL))(
                  v5,
                  &v283,
                  &v293,
                  v211,
                  v265,
                  &v279);
                CmsBPlusTable::InsertSimple(
                  (CmsBPlusTable *)v11,
                  v5,
                  (const struct _CmsRow *)&v279,
                  (SmsUndoRecord *)((char *)v8 + 48),
                  0,
                  0);
                _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)v8 + 5) + 48LL));
                a4 = v294;
                if ( v294 + v293 > (unsigned __int64)(v277 + v276) )
                {
                  v276 += v277;
                  a4 = 0;
                  v215 = 0;
                }
                else
                {
                  v276 += v294;
                  v215 = v277 - v294;
                }
                v277 = v215;
                v6 = v269;
                if ( !v215 )
                  break;
                valid = CmsBPlusTable::FindNextRangeIndexEntryForUndo(
                          (CmsBPlusTable *)v11,
                          v5,
                          (const struct _RANGE *)&v276,
                          (SmsUndoRecord *)((char *)v8 + 48),
                          &v272);
                v208 = v277;
                v209 = v276;
              }
              goto LABEL_3;
            }
            v184 = v183 - 1;
            if ( v184 )
            {
              v185 = v184 - 1;
              if ( v185 )
              {
                if ( v185 == 1 )
                {
                  v186 = (struct SmsTrashCleanerEntry **)*((_QWORD *)v8 + 3);
                  CmsTrashTable::ReleaseTrashCleanerEntry(*(CmsTrashTable **)(*((_QWORD *)v5 + 1) + 3288LL), v12);
                  CmsTrashTable::TeardownEntry(v187, v5, *v186, 0, 0);
                  goto LABEL_76;
                }
                goto LABEL_56;
              }
              v188 = SmsUndoRecord::MmsGetUndoIndexEntry(v8);
              _SmsIndexEntry::GetRangeKey(v188, &v288);
              v190 = *(_WORD *)(v189 + 8) & 0x40;
              while ( 1 )
              {
                _SmsIndexEntry::GetRangeKey(*((_QWORD *)v8 + 8), &v303);
                v193 = v303;
                v194 = v288;
                if ( v303 < (unsigned __int64)v288 )
                {
                  if ( !v190 )
                    goto LABEL_260;
                  v195 = (_DWORD)v288 - v303;
                  *(_QWORD *)(v192 + 12) = v303;
                  *(_DWORD *)(v192 + 20) = v195;
                }
                else
                {
                  CmsBPlusTable::DeleteSimpleForUndo(
                    v288,
                    v191,
                    v8,
                    *((struct _SmsIndexHeader **)v8 + 7),
                    *((_DWORD *)v8 + 18),
                    v274);
                }
                v194 = v288;
LABEL_260:
                v196 = &v289[-v193 - v304];
                v101 = (CmsBPlusTable *)((char *)v194 + (_QWORD)v196) == 0;
                v288 = (CmsBPlusTable *)(v193 + v304);
                v289 = (char *)v194 + (_QWORD)v196;
                v4 = a2;
                v6 = v269;
                if ( !v101 )
                {
                  valid = CmsBPlusTable::FindNextRangeIndexEntryForUndo(
                            *((CmsBPlusTable **)v8 + 5),
                            v5,
                            (const struct _RANGE *)&v288,
                            (SmsUndoRecord *)((char *)v8 + 48),
                            &v272);
                  v6 = v269;
                  if ( valid >= 0 )
                  {
                    if ( v272 )
                      continue;
                  }
                }
                goto LABEL_6;
              }
            }
            v197 = SmsUndoRecord::MmsGetUndoIndexEntry(v8);
            v198 = (__m128i *)_SmsIndexEntry::ToRow(v197, v300);
            v283 = *v198;
            v284 = v198[1];
            _SmsIndexEntry::GetRangeKey(v199, &v290);
            while ( 1 )
            {
              _SmsIndexEntry::GetRangeKey(
                *((_QWORD *)v8 + 7)
              + *(unsigned __int16 *)(*((_QWORD *)v8 + 7)
                                    + *(unsigned int *)(*((_QWORD *)v8 + 7) + 16LL)
                                    + 4LL * *((unsigned int *)v8 + 18)),
                &v305);
              _SmsIndexHeader::MarkIndexEntryDeleted(v202, v200, v201);
              v203 = *((_QWORD *)v8 + 5);
              if ( _InterlockedDecrement64((volatile signed __int64 *)(v203 + 48)) < 0 )
                _InterlockedIncrement64((volatile signed __int64 *)(v203 + 48));
              a4 = v306;
              if ( v306 + v305 > (unsigned __int64)(v291 + v290) )
              {
                v290 += v291;
                v204 = 0;
              }
              else
              {
                v290 += v306;
                v204 = v291 - v306;
              }
              v291 = v204;
              v6 = v269;
              if ( !v204 )
                break;
              valid = CmsBPlusTable::FindNextRangeIndexEntryForUndo(
                        (CmsBPlusTable *)v11,
                        v5,
                        (const struct _RANGE *)&v290,
                        (SmsUndoRecord *)((char *)v8 + 48),
                        &v272);
            }
            v4 = a2;
          }
          else
          {
LABEL_329:
            v243 = *(CmsBlockRefcount **)(*((_QWORD *)v5 + 1) + 3208LL);
            v244 = *((_QWORD *)v8 + 3);
            v245 = *(_BYTE *)(v244 + 16);
            if ( v245 == 2 )
            {
              CmsBlockRefcount::AdjustRefcount(v243, v5, (const struct _RANGE *)v244, 0, 1, 0, v267);
              goto LABEL_76;
            }
            v4 = a2;
            if ( v245 == 4 )
            {
              CmsBlockRefcount::AdjustRefcount(v243, v5, (const struct _RANGE *)v244, 0, 0, 0, v267);
              goto LABEL_77;
            }
LABEL_220:
            v6 = v269;
          }
        }
      }
    }
    else
    {
      if ( (_DWORD)v32 == 27 )
      {
        v180 = (CmsReferenced **)*((_QWORD *)v8 + 3);
        v285 = *(struct _RTL_BITMAP *)(v180 + 1);
        CmsStream::InvalidateChecksums(*v180, v5, &v285, a4);
        v179 = *v180;
        goto LABEL_241;
      }
      if ( (int)v32 > 13 )
      {
        if ( (int)v32 <= 20 )
        {
          if ( (_DWORD)v32 != 20 )
          {
            v151 = (_DWORD)v32 - 14;
            if ( !v151 )
            {
              v270 = (struct SmsContainer *)*((_QWORD *)v8 + 3);
              _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)v8 + 5) + 56LL));
              goto LABEL_189;
            }
            v152 = v151 - 1;
            if ( !v152 )
            {
              CmsBPlusTable::ProcessUndoDeleteQueue(*((CmsBPlusTable **)v8 + 5), v5, *((void **)v8 + 3), 0);
              goto LABEL_76;
            }
            v153 = v152 - 1;
            if ( !v153 )
            {
              CmsBPlusTable::ProcessUndoProcessedDeleteQueue(*((CmsBPlusTable **)v8 + 5), v12, *((void **)v8 + 3), 0);
              goto LABEL_76;
            }
            v154 = v153 - 1;
            if ( !v154 )
            {
              CmsEmbeddedComposite::AbortReparent(*(CmsEmbeddedComposite **)(*((_QWORD *)v8 + 3) + 8LL), v5, v8);
              goto LABEL_76;
            }
            v155 = v154 - 1;
            if ( !v155 )
            {
              CmsBPlusTable::AcquireDeleteLock(*((CmsBPlusTable **)v8 + 5), v12, 1);
              *(_BYTE *)(*((_QWORD *)v8 + 5) + 12LL) |= 0x80u;
              *(_BYTE *)(*((_QWORD *)v8 + 5) + 15LL) |= 8u;
              v159 = *((_QWORD *)v8 + 5);
              if ( *(_DWORD *)(v159 + 124) )
              {
                if ( *(_DWORD *)(v159 + 120) && (*(_BYTE *)(v159 + 13) & 0x10) == 0 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v159 + 24) + 72LL) + 3300LL));
                  *(_BYTE *)(*((_QWORD *)v8 + 5) + 13LL) |= 0x10u;
                }
                v160 = *((_QWORD *)v8 + 5);
                if ( (*(_BYTE *)(v160 + 13) & 0x40) == 0 )
                {
                  _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v160 + 24) + 72LL) + 3304LL));
                  *(_BYTE *)(*((_QWORD *)v8 + 5) + 13LL) |= 0x40u;
                }
              }
              CmsBPlusTable::ReleaseDeleteLock(*((CmsBPlusTable **)v8 + 5), v5);
              CmsReferenced::Release(*((CmsReferenced **)v8 + 5));
              *((_QWORD *)v8 + 5) = 0;
              goto LABEL_76;
            }
            if ( v155 == 1 )
            {
              *(_BYTE *)(*((_QWORD *)v8 + 5) + 12LL) &= ~0x80u;
              v156 = *((_QWORD *)v8 + 5);
              if ( (*(_BYTE *)(v156 + 188) & 0x40) != 0 )
              {
                _InterlockedAdd(
                  (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v156 + 24) + 72LL) + 3008LL),
                  0xFFFFF000);
                for ( i = *((_QWORD *)v8 + 5); *(_QWORD *)(i + 64) != i; i = *(_QWORD *)(i + 64) )
                  ;
                _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(i + 72) + 584LL), 0xFFFFF000);
                _InterlockedAnd((volatile signed __int32 *)(*((_QWORD *)v8 + 5) + 188LL), 0xFFFFFFBF);
              }
              v158 = *((_QWORD *)v8 + 5);
              if ( (*(_BYTE *)(v158 + 13) & 0x10) != 0 )
              {
                _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v158 + 24) + 72LL) + 3300LL));
                *(_BYTE *)(*((_QWORD *)v8 + 5) + 13LL) &= ~0x10u;
              }
              CmsBPlusTable::ReleaseDeleteLock((CmsBPlusTable *)v11, v5);
              goto LABEL_75;
            }
LABEL_56:
            v40 = 0;
            goto LABEL_57;
          }
          v161 = *((_QWORD *)v8 + 3);
          *(_WORD *)(v282 + 22) = *(_WORD *)v161;
          *(_WORD *)(v11 + 210) = *(_WORD *)v161;
          v162 = *(_BYTE *)(v161 + 2);
          *(_BYTE *)(v11 + 15) &= ~4u;
          *(_BYTE *)(v11 + 15) |= v162 != 0 ? 4 : 0;
          if ( v162 )
            *(_WORD *)(v282 + 8) |= 2u;
          else
            *(_WORD *)(v282 + 8) &= ~2u;
          goto LABEL_219;
        }
        v163 = (_DWORD)v32 - 21;
        if ( !v163 )
        {
          v178 = (CmsStream *)**((_QWORD **)v8 + 3);
          CmsStream::TeardownLookupCache(v178);
LABEL_240:
          v179 = v178;
LABEL_241:
          CmsReferenced::Release(v179);
          goto LABEL_76;
        }
        v164 = v163 - 1;
        if ( !v164 )
        {
          CmsStream::HandlePreloadedLookupCacheUndo(
            **((CmsStream ***)v8 + 3),
            v5,
            *((struct SmsPreloadedLookupCacheUndoRecord **)v8 + 3));
          goto LABEL_76;
        }
        v165 = v164 - 2;
        if ( !v165 )
        {
          v174 = *((_QWORD *)v8 + 3);
          v175 = *(_QWORD *)(*((_QWORD *)v8 + 5) + 72LL);
          if ( *(_QWORD *)(v175 + 408) )
          {
            v176 = *(_QWORD *)(v174 + 16);
            if ( v176 )
            {
              v177 = *(_QWORD *)(v174 + 16);
              if ( v177 == _InterlockedCompareExchange64((volatile signed __int64 *)(v175 + 408), 0, v176) )
                operator delete(*(void **)(v174 + 16), (const struct std::nothrow_t *)0x10);
            }
          }
          *(_BYTE *)(*((_QWORD *)v8 + 5) + 13LL) ^= (*(_BYTE *)(*((_QWORD *)v8 + 5) + 13LL)
                                                   ^ (4 * *(_BYTE *)(v174 + 24)))
                                                  & 4;
          *(_OWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 72LL) + 392LL) = *(_OWORD *)v174;
LABEL_219:
          v4 = a2;
          goto LABEL_220;
        }
        v36 = (unsigned int)(v165 - 1);
        if ( !(_DWORD)v36 )
          goto LABEL_229;
        if ( (_DWORD)v36 != 1 )
          goto LABEL_56;
        v166 = (unsigned int *)*((_QWORD *)v8 + 3);
        a4 = *v166;
        v167 = v166[1];
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 72LL) + 696LL) = v167;
        v4 = a2;
        v6 = v269;
        if ( (_DWORD)v167 )
        {
          v168 = (char *)v166 + a4;
          v169 = v167;
          memcpy_0(*(void **)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 72LL) + 704LL), (char *)v166 + a4, v167);
          memcpy_0(*(void **)(*(_QWORD *)(*((_QWORD *)v8 + 5) + 72LL) + 936LL), v168, v169);
          goto LABEL_77;
        }
      }
      else
      {
        if ( (_DWORD)v32 == 13 )
        {
          v270 = (struct SmsContainer *)*((_QWORD *)v8 + 3);
          CmsVolume::AbandonNewlyAllocatedPage(v32, v5, *(struct SmsPage **)v270);
LABEL_189:
          CmsBPlusTable::ReleaseCachedPinList((CmsBPlusTable *)v11, v5, 0);
          goto LABEL_56;
        }
        if ( (int)v32 > 7 )
        {
          v62 = (_DWORD)v32 - 8;
          if ( v62 )
          {
            v63 = v62 - 1;
            if ( !v63 )
            {
              v102 = *((_QWORD *)v8 + 3);
              v270 = (struct SmsContainer *)(v102 + 104);
              IndexHeaderInPage = CmsCompositeBase::FindIndexHeaderInPage(
                                    *(CmsCompositeBase **)(*((_QWORD *)v8 + 5) + 112LL),
                                    v5,
                                    *(struct SmsPage **)(v102 + 104),
                                    a4);
              *((_BYTE *)IndexHeaderInPage + 13) &= ~8u;
              *((_QWORD *)IndexHeaderInPage + 3) = 0;
              if ( *(_DWORD *)(v102 + 16) )
              {
                v110 = *(_DWORD *)(v102 + 4);
                v111 = *(_DWORD *)v102;
                v112 = *(_DWORD *)v102 + v110;
                for ( j = *(_DWORD *)v102; j < v112; j = v114 + 1 )
                  v7 += _SmsIndexHeader::MarkOneIndexEntryDeleted(
                          IndexHeaderInPage,
                          (struct _SmsIndexHeader *)((char *)IndexHeaderInPage
                                                   + *(unsigned __int16 *)((char *)IndexHeaderInPage
                                                                         + 4 * j
                                                                         + *((unsigned int *)IndexHeaderInPage + 4))));
                *((_DWORD *)IndexHeaderInPage + 2) += v7;
                _SmsIndexHeader::RemoveOffsetEntries(IndexHeaderInPage, v111, v110);
                valid = FirstIndexEntry;
                if ( *(_BYTE *)(v102 + 20) )
                {
                  v115 = (unsigned int)(*((_DWORD *)IndexHeaderInPage + 5) - 1);
                  v116 = (char *)IndexHeaderInPage + *((unsigned int *)IndexHeaderInPage + 4);
                  *(_WORD *)&v116[4 * v115 + 2] = -1;
                  v117 = *(unsigned __int16 *)&v116[4 * v115];
                  v108 = 2;
                  *(_WORD *)((char *)IndexHeaderInPage + v117 + 8) |= 2u;
                }
              }
              else
              {
                v104 = *(_DWORD *)v102;
                for ( k = 0; k < v104; k = v106 + 1 )
                  v7 += _SmsIndexHeader::MarkOneIndexEntryDeleted(
                          IndexHeaderInPage,
                          (struct _SmsIndexHeader *)((char *)IndexHeaderInPage
                                                   + *(unsigned __int16 *)((char *)IndexHeaderInPage
                                                                         + 4 * k
                                                                         + *((unsigned int *)IndexHeaderInPage + 4))));
                *((_DWORD *)IndexHeaderInPage + 2) += v7;
                _SmsIndexHeader::RemoveOffsetEntries(IndexHeaderInPage, 0, v104);
              }
              if ( *((_DWORD *)IndexHeaderInPage + 5) == 1 && (*((_BYTE *)IndexHeaderInPage + 13) & 1) != 0 )
              {
                v308 = 0;
                v309 = 0;
                v310 = 0;
                v41 = (struct SmsPage **)v270;
                *(_QWORD *)&v308 = *(_QWORD *)v270;
                *((_QWORD *)&v308 + 1) = IndexHeaderInPage;
                DWORD2(v309) = 0;
                CmsBPlusTable::InsertSimple(
                  *((CmsBPlusTable **)v8 + 5),
                  v5,
                  (const struct _CmsRow *)(v102 + 24),
                  (struct SmsLookupStack *)&v308,
                  0,
                  0);
                CmsBPlusTable::DeleteSimpleForUndo(v119, v118, v8, IndexHeaderInPage, 0, v274);
                CmsRowWithBuffer::Reset((CmsRowWithBuffer *)(v102 + 24));
              }
              else
              {
                v41 = (struct SmsPage **)v270;
              }
              CmsVolume::MarkPageChange((CmsVolume *)v108, v107, v109, *v41, 0, 8);
              _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)v8 + 5) + 56LL));
              goto LABEL_58;
            }
            v64 = v63 - 1;
            if ( v64 )
            {
              v65 = v64 - 1;
              if ( v65 )
              {
                if ( v65 != 1 )
                  goto LABEL_56;
                v66 = *((unsigned int *)v8 + 2);
                v67 = (char *)v12 + *((int *)v8 + 8);
                v68 = (const void *)*((_QWORD *)v8 + 3);
LABEL_85:
                memcpy_0(v67, v68, v66);
                goto LABEL_76;
              }
              v69 = *((_QWORD *)v8 + 3);
              v273 = *(struct CmsTransactionContext **)(v69 + 80);
              v70 = *((_QWORD *)v5 + 1);
              v71 = (__int64 *)(v69 + 88);
              if ( (*(_DWORD *)(v69 + 96) & 0x100) != 0 )
                CmsStream::IncrementStreamReserveClusters(*(CmsStream **)(v69 + 72), v5, *v71);
              if ( (*(_DWORD *)(v69 + 96) & 0x200) != 0 )
                CmsStream::DecrementStreamReserveClusters(*(CmsStream **)(v69 + 72), v5, *v71);
              RtlAcquireSRWLockExclusive(v70 + 3736);
              CmsVolume::ProcessReservationUndo((CmsVolume *)v70, (struct SmsReservationUndoRecord *)(v69 + 88));
              v72 = v70 + 3736;
              if ( *(_QWORD *)(v70 + 3736) < 0x10u )
                RtlReleaseSRWLockExclusive(v72);
              else
                RtlReleaseSRWLockShared(v72);
              v40 = 0;
              if ( *(_BYTE *)(v69 + 67) )
                goto LABEL_57;
              v73 = 0;
              v74 = v69;
              v75 = (_BYTE *)(v69 + 64);
              if ( v69 < v69 + 64 )
              {
                do
                {
                  if ( !*(_QWORD *)(v74 + 8) )
                    break;
                  ++v73;
                  v74 += 16LL;
                }
                while ( v74 < (unsigned __int64)v75 );
              }
              v6 = v269;
              if ( v73 )
              {
                v76 = v273;
                do
                {
                  v77 = *(struct _RTL_BITMAP *)(v69 + 16LL * --v73);
                  v278 = v77;
                  v279 = 0;
                  v280 = 0;
                  *(_QWORD *)v274 = v40;
                  v270 = v40;
                  if ( *((_BYTE *)v76 + 484) == 3 )
                  {
                    if ( *v75 == (_BYTE)v40 )
                    {
                      v78 = *(_QWORD *)(v69 + 16LL * v73) >> (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v70 + 3176) + 8LL)
                                                                       + 80LL)
                                                            + 1);
                    }
                    else
                    {
                      v285 = v77;
                      CmsVolumeContainer::GetContainerIdFromRealRange(*(_QWORD *)(v70 + 3176), v5, &v285, v274);
                      v78 = *(_QWORD *)v274;
                      LOBYTE(v40) = 0;
                    }
                    FirstIndexEntry = CmsVolumeContainer::GetContainerReference(
                                        *(CmsVolumeContainer **)(v70 + 3176),
                                        v5,
                                        v78,
                                        &v270,
                                        1,
                                        (unsigned __int8)v40);
                    v77 = v278;
                    v40 = 0;
                  }
                  if ( *v75 == (_BYTE)v40 )
                  {
                    v285 = v77;
                    v267 = v40;
                    FirstIndexEntry = CmsVolumeContainer::PinContainerRange(
                                        *(_QWORD *)(v70 + 3176),
                                        v5,
                                        &v285,
                                        0,
                                        &v278,
                                        &v279);
                    LOBYTE(v40) = 0;
                  }
                  CmsAllocator::AbortAllocatedLcns(
                    v273,
                    v5,
                    (const struct _RANGE *)&v278,
                    *(_BYTE *)(v69 + 65) != (unsigned __int8)v40,
                    *(_BYTE *)(v69 + 66) != (unsigned __int8)v40,
                    v270);
                  v40 = 0;
                  if ( !*v75 )
                  {
                    v285 = *(struct _RTL_BITMAP *)(v69 + 16LL * v73);
                    CmsVolumeContainer::UnpinContainerRange(*(_QWORD *)(v70 + 3176), v5, &v285, &v279);
                    v40 = 0;
                  }
                  v76 = v273;
                  if ( *((_BYTE *)v273 + 484) == 3 )
                  {
                    if ( !*v75 )
                      _InterlockedDecrement((volatile signed __int32 *)v270 + 26);
                    CmsVolumeContainer::ReleaseContainerReference(v79, v5, v270);
                  }
                }
                while ( v73 );
                valid = FirstIndexEntry;
LABEL_114:
                v4 = a2;
LABEL_115:
                v7 = 0;
                goto LABEL_77;
              }
              valid = FirstIndexEntry;
LABEL_3:
              v4 = a2;
              goto LABEL_6;
            }
            v80 = (struct SmsPage **)(*((_QWORD *)v8 + 3) + 24LL);
            v270 = (struct SmsContainer *)v80;
            v81 = CmsCompositeBase::FindIndexHeaderInPage(
                    *(CmsCompositeBase **)(*((_QWORD *)v8 + 5) + 112LL),
                    v5,
                    *v80,
                    a4);
            v83 = CmsCompositeBase::FindIndexHeaderInPage(
                    *(CmsCompositeBase **)(*((_QWORD *)v8 + 5) + 112LL),
                    v5,
                    v80[1],
                    v82);
            CmsBPlusTable::CompressIndexBucket(v85, v84, *v80, v81, (bool)v265);
            CmsBPlusTable::CompressIndexBucket(v87, v86, v80[1], v83, v266);
            *((_BYTE *)v81 + 13) &= ~8u;
            *((_QWORD *)v81 + 3) = 0;
            *((_BYTE *)v83 + 13) &= ~8u;
            *((_QWORD *)v83 + 3) = 0;
            CmsBPlusTable::MmsMoveIndexEntriesCollateHigh(
              v83,
              *(_QWORD *)(*((_QWORD *)v8 + 5) + 24LL),
              *((_DWORD *)v83 + 5),
              v81,
              *(const struct _SmsPropertyDef **)(*((_QWORD *)v8 + 5) + 24LL));
            CmsVolume::MarkPageChange(v89, v88, v90, *v80, 0, 8);
            _InterlockedDecrement64((volatile signed __int64 *)(*((_QWORD *)v8 + 5) + 56LL));
            v91 = *v80;
            v92 = *((_DWORD *)*v80 + 78);
            v93 = *((_DWORD *)v91 + 79);
            v94 = v270;
            *((_OWORD *)v91 + 19) = *(_OWORD *)(*((_QWORD *)v270 + 1) + 304LL);
            *(_OWORD *)(*((_QWORD *)v94 + 1) + 304LL) = 0;
            v40 = 0;
            if ( v92 <= 0 )
            {
              v41 = (struct SmsPage **)v94;
              valid = FirstIndexEntry;
              goto LABEL_58;
            }
            while ( 1 )
            {
              v95 = v93;
              if ( v93 )
                v95 = v93 - 1;
              v96 = (CmsVolume *)*((_QWORD *)v5 + 1);
              a4 = v93 != 0 ? 7 : 3;
              v97 = *((_QWORD *)v94 + 1);
              if ( v97 )
                break;
LABEL_135:
              --v92;
              v93 = v95;
              if ( v92 <= 0 )
              {
                valid = FirstIndexEntry;
                goto LABEL_57;
              }
            }
            while ( 1 )
            {
              v98 = 0;
              v99 = a4;
              if ( *(_QWORD *)(v97 + 304) )
              {
                if ( (a4 & 1) != 0 && *(_DWORD *)(v97 + 384) == *(_DWORD *)(v97 + 312) )
                {
                  v98 = *(_QWORD *)(v97 + 304);
                  if ( (a4 & 4) != 0 )
                    goto LABEL_128;
                  goto LABEL_131;
                }
                if ( (a4 & 4) != 0 && *(_DWORD *)(v97 + 388) == *(_DWORD *)(v97 + 316) )
                {
                  v98 = *(_QWORD *)(v97 + 304);
LABEL_128:
                  v100 = *(_DWORD *)(v97 + 316);
                  if ( *(_DWORD *)(v97 + 388) == v100 )
                    *(_DWORD *)(v97 + 316) = v100 - 1;
                  else
                    v99 = a4 & 0xFFFFFFFB;
LABEL_131:
                  v101 = (*(_DWORD *)(v97 + 312))-- == 1;
                  if ( v101 )
                    *(_QWORD *)(v97 + 304) = 0;
                }
              }
              CmsVolume::UnpinInternal(v96, v5, (struct SmsPage *)v97, a4);
              v97 = v98;
              a4 = v99;
              v40 = 0;
              if ( !v98 )
              {
                v94 = v270;
                goto LABEL_135;
              }
            }
          }
LABEL_150:
          v120 = SmsUndoRecord::MmsGetUndoIndexEntry(v8);
          v121 = (__m128i *)_SmsIndexEntry::ToRow(v120, &v279);
          v125 = *v121;
          v283 = *v121;
          v284 = v121[1];
          if ( (v126 & 2) == 0 || (*((_BYTE *)v8 + 20) & 1) == 0 )
          {
            if ( *(_BYTE *)(v124 + 16) )
              v150 = *(_DWORD *)v124;
            else
              v150 = 0;
            CmsBPlusTable::UpdateSimple(
              v123,
              v122,
              (const struct _CmsRow *)&v283,
              (SmsUndoRecord *)((char *)v8 + 48),
              (unsigned __int8)v265,
              v150);
            goto LABEL_75;
          }
          v285 = 0;
          v286 = 0;
          v287 = 0;
          v279 = 0;
          LODWORD(v280) = 0;
          v281 = 0;
          v127 = SmsUndoRecord::MmsGetUndoIndexEntry(v8);
          if ( (*((_BYTE *)v127 + 8) & 0x40) != 0 )
            v129 = (*((unsigned __int16 *)v127 + 5) + 7) & 0xFFFFFFF8;
          else
            v129 = *(_DWORD *)v127;
          v130 = SmsUndoRecord::MmsGetUndoIndexEntry(v128);
          *(_WORD *)v274 = v132 & *((_WORD *)v130 + 4);
          v292 = 0u;
          v275 = 0u;
          v133 = _mm_srli_si128(v125, 8).m128i_u64[0];
          if ( *(_WORD *)v274 )
          {
            v134 = *(unsigned int *)(v133 + 8);
            *(_QWORD *)&v275 = *(_QWORD *)v133;
            *((_QWORD *)&v275 + 1) = v134;
          }
          else
          {
            v275 = *(_OWORD *)v133;
          }
          LODWORD(v279) = 16;
          WORD2(v279) = 0;
          WORD3(v279) = v283.m128i_i16[3];
          *((_QWORD *)&v279 + 1) = &v275;
          LODWORD(v280) = 16;
          HIDWORD(v280) = v284.m128i_i32[1];
          v281 = &v275;
          v135 = (__int64)v8 + 48;
          v270 = (struct SmsContainer *)(v129 + v131 + 20);
          while ( 1 )
          {
            v136 = CmsBPlusTable::MmsIndexEntryByOffset(*((struct _SmsIndexHeader **)v8 + 7), *(_DWORD *)(v135 + 24));
            v137 = *(__int128 **)(_SmsIndexEntry::ToRow(v136, v300) + 8);
            if ( v139 )
            {
              v140 = *((unsigned int *)v137 + 2);
              *(_QWORD *)&v292 = *(_QWORD *)v137;
              *((_QWORD *)&v292 + 1) = v140;
            }
            else
            {
              v292 = *v137;
            }
            (*(void (__fastcall **)(struct CmsTransactionContext *, __m128i *, __int128 *, __int64))(*(_QWORD *)(v11 + 24) + 80LL))(
              v5,
              &v283,
              &v292,
              v138);
            CmsBPlusTable::UpdateSimple(
              v142,
              v141,
              (const struct _CmsRow *)&v285,
              (struct SmsLookupStack *)v135,
              v129,
              0);
            *(_QWORD *)&v275 = *((_QWORD *)&v292 + 1) + v275;
            v143 = *((_QWORD *)&v275 + 1) - *((_QWORD *)&v292 + 1);
            *((_QWORD *)&v275 + 1) -= *((_QWORD *)&v292 + 1);
            if ( *((_QWORD *)&v275 + 1) )
            {
              v144 = *((_QWORD *)v8 + 6);
              *(_OWORD *)v135 = 0;
              *(_OWORD *)(v135 + 16) = 0;
              *(_QWORD *)(v135 + 32) = 0;
              v267 = (struct CmsBPlusTable *)&v272;
              LOBYTE(v265) = 1;
              valid = CmsBPlusTable::FindFirstIndexEntry(v11, v5, &v279, v135);
              FirstIndexEntry = valid;
              ++*(_DWORD *)(*((_QWORD *)v8 + 6) + 388LL);
              if ( v144 )
              {
                v145 = (CmsVolume *)*((_QWORD *)v5 + 1);
                v146 = 7;
                while ( 1 )
                {
                  v147 = 0;
                  v148 = v146;
                  if ( *(_QWORD *)(v144 + 304) )
                  {
                    if ( (v146 & 1) != 0 && *(_DWORD *)(v144 + 384) == *(_DWORD *)(v144 + 312) )
                    {
                      v147 = *(_QWORD *)(v144 + 304);
                      if ( (v146 & 4) != 0 )
                        goto LABEL_173;
                      goto LABEL_176;
                    }
                    if ( (v146 & 4) != 0 && *(_DWORD *)(v144 + 388) == *(_DWORD *)(v144 + 316) )
                    {
                      v147 = *(_QWORD *)(v144 + 304);
LABEL_173:
                      v149 = *(_DWORD *)(v144 + 316);
                      if ( *(_DWORD *)(v144 + 388) == v149 )
                        *(_DWORD *)(v144 + 316) = v149 - 1;
                      else
                        v148 = v146 & 0xFFFFFFFB;
LABEL_176:
                      v101 = (*(_DWORD *)(v144 + 312))-- == 1;
                      if ( v101 )
                        *(_QWORD *)(v144 + 304) = 0;
                    }
                  }
                  CmsVolume::UnpinInternal(v145, v5, (struct SmsPage *)v144, v146);
                  v144 = v147;
                  v146 = v148;
                  if ( !v147 )
                  {
                    v143 = *((_QWORD *)&v275 + 1);
                    v11 = *(_QWORD *)&v278.SizeOfBitMap;
                    v135 = (__int64)v8 + 48;
                    goto LABEL_180;
                  }
                }
              }
              v143 = *((_QWORD *)&v275 + 1);
            }
            else
            {
LABEL_180:
              valid = FirstIndexEntry;
            }
            if ( !v143 )
            {
              v7 = 0;
              goto LABEL_75;
            }
          }
        }
        if ( (_DWORD)v32 == 7 )
          goto LABEL_150;
        v33 = (CmsVolume *)(unsigned int)((_DWORD)v32 - 1);
        if ( !(_DWORD)v33 )
        {
          v270 = (struct SmsContainer *)*((_QWORD *)v8 + 3);
          CmsVolume::MarkPageChange(
            v33,
            v12,
            *((struct CmsBPlusTable **)v270 + 1),
            *(struct SmsPage **)(*((_QWORD *)v270 + 1) + 256LL),
            *((struct SmsPage **)v270 + 1),
            12);
          _InterlockedAnd((volatile signed __int32 *)(v61 + 560), 0xFFFFFDFF);
          goto LABEL_56;
        }
        v34 = (_DWORD)v33 - 1;
        if ( v34 && (v35 = v34 - 1) != 0 )
        {
          v36 = (unsigned int)(v35 - 1);
          if ( (_DWORD)v36 )
          {
            v37 = v36 - 1;
            if ( v37 )
            {
              if ( v37 == 1 )
              {
                v38 = *((_QWORD *)v8 + 3);
                v270 = (struct SmsContainer *)(v38 + 8);
                v39 = (unsigned int *)(*(_QWORD *)(*(_QWORD *)(v38 + 16) + 104LL) + 80LL);
                CmsBPlusTable::PopIndexRoot(
                  *((CmsBPlusTable **)v8 + 5),
                  v12,
                  *(struct _SmsIndexHeader **)v38,
                  (struct _SmsIndexHeader *)((char *)v39 + *v39));
                _InterlockedDecrement64((volatile signed __int64 *)(*((_QWORD *)v8 + 5) + 56LL));
              }
            }
            else
            {
              v45 = (struct _SmsIndexHeader **)*((_QWORD *)v8 + 3);
              v270 = (struct SmsContainer *)(v45 + 1);
              v46 = (unsigned int *)(*((_QWORD *)v45[2] + 13) + 80LL);
              valid = CmsBPlusTable::PushIndexRoot(
                        *((CmsBPlusTable **)v8 + 5),
                        v5,
                        *v45,
                        0,
                        (struct _SmsIndexHeader *)((char *)v46 + *v46),
                        v45[2]);
              _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)v8 + 5) + 56LL));
            }
            goto LABEL_56;
          }
LABEL_229:
          v274[0] = 0;
          CmsBPlusTable::DeleteSimpleForUndo(
            (CmsBPlusTable *)v36,
            v12,
            v8,
            *((struct _SmsIndexHeader **)v8 + 7),
            *((_DWORD *)v8 + 18),
            v274);
          if ( *((_DWORD *)v8 + 4) == 25 )
          {
            if ( v274[0] )
            {
              v170 = *(_DWORD *)(*((_QWORD *)v8 + 7) + 20LL);
              if ( v170 )
              {
                v171 = CmsBPlusTable::MmsIndexEntryByOffset(*((struct _SmsIndexHeader **)v8 + 7), v170 - 1);
                *(_WORD *)(v173 + *(unsigned int *)(v173 + 16) + 4LL * v172 + 2) = -1;
                *((_WORD *)v171 + 4) |= 2u;
              }
            }
          }
        }
        else
        {
          if ( (*((_BYTE *)v8 + 20) & 2) != 0 )
          {
            v47 = *((_QWORD *)v8 + 7);
            if ( !*(_DWORD *)(v47 + 20) )
            {
              if ( *((_BYTE *)v8 + 21) )
              {
                _SmsIndexHeader::InitializeIndexHeader(
                  v47,
                  *(_QWORD *)(*((_QWORD *)v8 + 5) + 24LL),
                  *(unsigned int *)(v47 + 32));
                *(_BYTE *)(*((_QWORD *)v8 + 5) + 212LL) = *((_BYTE *)v8 + 21);
              }
            }
          }
          v48 = SmsUndoRecord::MmsGetUndoIndexEntry(v8);
          v49 = (__m128i *)_SmsIndexEntry::ToRow(v48, &v279);
          v283 = *v49;
          v284 = v49[1];
          CmsBPlusTable::InsertSimple(
            *((CmsBPlusTable **)v8 + 5),
            v5,
            (const struct _CmsRow *)&v283,
            (SmsUndoRecord *)((char *)v8 + 48),
            0,
            0);
          if ( !*(_BYTE *)(*((_QWORD *)v8 + 7) + 12LL) )
            _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)v8 + 5) + 48LL));
          if ( (*((_BYTE *)v8 + 20) & 2) != 0 )
          {
            v50 = *(_DWORD *)(*((_QWORD *)v8 + 7) + 20LL);
            if ( v50 <= 1 )
            {
              v56 = SmsUndoRecord::MmsGetUndoIndexEntry(v8);
              if ( (v58 & *((_BYTE *)v56 + 8)) != 0 )
              {
                *(_WORD *)((char *)v57 + v57[4] + 2) = -1;
                v59 = CmsBPlusTable::MmsIndexEntryByOffset((struct _SmsIndexHeader *)v57, 0);
                *((_WORD *)v59 + 4) |= v60;
              }
            }
            else
            {
              CmsBPlusTable::MmsIndexEntryByOffset(*((struct _SmsIndexHeader **)v8 + 7), v50 - 1);
              v53 = CmsBPlusTable::MmsIndexEntryByOffset(v52, v51 - 2);
              CmsBPlusTable::SwapDirectorData(v54, v53, v55);
            }
          }
        }
LABEL_75:
        CmsBPlusTable::ReleaseCachedPinList((CmsBPlusTable *)v11, v5, 0);
LABEL_76:
        v4 = a2;
LABEL_77:
        v6 = v269;
      }
    }
  }
  while ( 2 )
  {
    v263 = *((_QWORD *)v5 + 18);
    if ( (struct SmsUndoRecord *)v263 != v4 )
    {
      v254 = 0;
      if ( *(_DWORD *)(v263 + 16) != 1 )
      {
        switch ( *(_DWORD *)(v263 + 16) )
        {
          case 5:
          case 6:
            v254 = *(_QWORD *)(v263 + 24) + 8LL;
            goto LABEL_369;
          case 9:
            v254 = *(_QWORD *)(v263 + 24) + 104LL;
            goto LABEL_369;
          case 0xA:
            v254 = *(_QWORD *)(v263 + 24) + 24LL;
            goto LABEL_369;
        }
        if ( *(_DWORD *)(v263 + 16) != 13 && *(_DWORD *)(v263 + 16) != 14 )
        {
          if ( *(_DWORD *)(v263 + 16) != 29 )
          {
            if ( *(_DWORD *)(v263 + 16) != 36 )
              goto LABEL_369;
            goto LABEL_368;
          }
          v254 = *(_QWORD *)(v263 + 24) + 32LL;
LABEL_369:
          *((_QWORD *)v5 + 18) = *(_QWORD *)v263;
          if ( v254 )
          {
            if ( *(_QWORD *)v254 )
              SmsPage::InvalidateAllPersistentQIs(*(SmsPage **)v254, v5, 0);
            v255 = *(SmsPage **)(v254 + 8);
            if ( v255 )
              SmsPage::InvalidateAllPersistentQIs(v255, v5, 0);
            SmsMultiPageUndoRecord::UnpinPages((SmsMultiPageUndoRecord *)v254, v5);
          }
          v256 = *(SmsPage **)(v263 + 48);
          if ( v256 )
            SmsPage::InvalidateAllPersistentQIs(v256, v5, 0);
          v257 = (CmsVolume *)*((_QWORD *)v5 + 1);
          v258 = 7;
          v259 = *(_QWORD *)(v263 + 48);
          if ( !v259 )
          {
LABEL_396:
            *(_QWORD *)(v263 + 48) = 0;
            CmsBPlusTable::FreeUndoRecord((struct SmsUndoRecord *)v263, 0, v259);
            continue;
          }
          while ( 1 )
          {
            v260 = 0;
            v261 = v258;
            if ( *(_QWORD *)(v259 + 304) )
            {
              if ( (v258 & 1) != 0 && *(_DWORD *)(v259 + 384) == *(_DWORD *)(v259 + 312) )
              {
                v260 = *(_QWORD *)(v259 + 304);
                if ( (v258 & 4) != 0 )
                  goto LABEL_390;
                goto LABEL_393;
              }
              if ( (v258 & 4) != 0 && *(_DWORD *)(v259 + 388) == *(_DWORD *)(v259 + 316) )
              {
                v260 = *(_QWORD *)(v259 + 304);
LABEL_390:
                v262 = *(_DWORD *)(v259 + 316);
                if ( *(_DWORD *)(v259 + 388) == v262 )
                  *(_DWORD *)(v259 + 316) = v262 - 1;
                else
                  v261 = v258 & 0xFFFFFFFB;
LABEL_393:
                v101 = (*(_DWORD *)(v259 + 312))-- == 1;
                if ( v101 )
                  *(_QWORD *)(v259 + 304) = 0;
              }
            }
            CmsVolume::UnpinInternal(v257, v5, (struct SmsPage *)v259, v258);
            v259 = v260;
            v258 = v261;
            if ( !v260 )
              goto LABEL_396;
          }
        }
      }
LABEL_368:
      v254 = *(_QWORD *)(v263 + 24);
      goto LABEL_369;
    }
    break;
  }
  if ( v296 )
    *(_QWORD *)v5 |= 0x40uLL;
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x1400d7830  push    rbp
0x1400d7832  push    rbx
0x1400d7833  push    rsi
0x1400d7834  push    rdi
0x1400d7835  push    r12
0x1400d7837  push    r13
0x1400d7839  push    r14
0x1400d783b  push    r15
0x1400d783d  lea     rbp, [rsp-138h]
0x1400d7845  sub     rsp, 238h
0x1400d784c  mov     rax, cs:__security_cookie
0x1400d7853  xor     rax, rsp
0x1400d7856  mov     [rbp+170h+var_50], rax
0x1400d785d  mov     r13, rdx
0x1400d7860  mov     [rsp+270h+var_220], rdx
0x1400d7865  mov     r14, rcx
0x1400d7868  mov     [rbp+170h+var_110], rcx
0x1400d786c  mov     rcx, [rcx+90h]
0x1400d7873  mov     [rsp+270h+var_218], rcx
0x1400d7878  xor     r15d, r15d
0x1400d787b  mov     esi, r15d
0x1400d787e  mov     r12d, r15d
0x1400d7881  mov     rax, [r14]
0x1400d7884  mov     rdx, rax
0x1400d7887  and     rdx, 40h
0x1400d788b  mov     [rbp+170h+var_108], rdx
0x1400d788f  and     rax, 0FFFFFFFFFFFFFFBFh
0x1400d7893  mov     [r14], rax
0x1400d7896  jmp     loc_1400D7D78
0x1400d789b  mov     r12d, [rsp+270h+var_208]
0x1400d78a0  mov     r13, [rsp+270h+var_220]
0x1400d78a5  jmp     short loc_1400D78B9
0x1400d78a7  mov     r13, [rsp+270h+var_220]
0x1400d78ac  jmp     short loc_1400D78BC
0x1400d78ae  mov     rcx, [rsp+270h+var_218]
0x1400d78b3  mov     r10d, 2
0x1400d78b9  xor     r15d, r15d
0x1400d78bc  test    rsi, rsi
0x1400d78bf  jnz     short loc_1400D78C6
0x1400d78c1  mov     rsi, rcx
0x1400d78c4  jmp     short loc_1400D78C9
0x1400d78c6  mov     rsi, [rsi]
0x1400d78c9  cmp     rsi, r13
0x1400d78cc  jz      loc_1400D96A4
0x1400d78d2  mov     r13, [rsi+28h]
0x1400d78d6  mov     qword ptr [rbp+170h+var_1D0.SizeOfBitMap], r13
0x1400d78da  mov     rdx, r15
0x1400d78dd  mov     [rsp+270h+var_200], rdx
0x1400d78e2  mov     [rbp+170h+var_1A0], r15
0x1400d78e6  mov     [rsp+270h+var_204], r15d
0x1400d78eb  mov     [rsp+270h+var_210], r15
0x1400d78f0  lea     rdi, [rsi+10h]
0x1400d78f4  test    byte ptr [rsi+14h], 1
0x1400d78f8  jz      loc_1400D7A46
0x1400d78fe  mov     eax, [rdi]
0x1400d7900  cmp     eax, 1Fh
0x1400d7903  ja      short loc_1400D790F
0x1400d7905  mov     ecx, 0C0000094h
0x1400d790a  bt      ecx, eax
0x1400d790d  jb      short loc_1400D7918
0x1400d790f  cmp     eax, 20h ; ' '
0x1400d7912  jnz     loc_1400D7A46
0x1400d7918  lea     rbx, [rsi+30h]
0x1400d791c  mov     r15, [rbx]
0x1400d791f  xorps   xmm0, xmm0
0x1400d7922  xor     eax, eax
0x1400d7924  movups  xmmword ptr [rbx], xmm0
0x1400d7927  movups  xmmword ptr [rbx+10h], xmm0
0x1400d792b  mov     [rbx+20h], rax
0x1400d792f  mov     rcx, rsi; this
0x1400d7932  call    ?MmsGetUndoIndexEntry@SmsUndoRecord@@QEAAPEAU_SmsIndexEntry@@XZ; SmsUndoRecord::MmsGetUndoIndexEntry(void)
0x1400d7937  lea     rdx, [rbp+170h+var_70]
0x1400d793e  mov     rcx, rax
0x1400d7941  call    ?ToKey@_SmsIndexEntry@@QEAA?AU_CmsKey@@XZ; _SmsIndexEntry::ToKey(void)
0x1400d7946  mov     r8, rax
0x1400d7949  xor     r9d, r9d
0x1400d794c  mov     [rsp+270h+var_238], r9
0x1400d7951  lea     rax, [rsp+270h+var_204]
0x1400d7956  mov     [rsp+270h+var_240], rax
0x1400d795b  mov     byte ptr [rsp+270h+var_248], r9b
0x1400d7960  mov     dword ptr [rsp+270h+var_250], 1
0x1400d7968  mov     r9, rbx
0x1400d796b  mov     rdx, r14
0x1400d796e  mov     rcx, r13
0x1400d7971  call    ?FindFirstIndexEntry@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@AEBU_CmsKey@@PEAUSmsLookupStack@@W4EmsPinRowFlags@@EPEAKPEAU_SmsQuickIndex@@@Z; CmsBPlusTable::FindFirstIndexEntry(CmsTransactionContext *,_CmsKey const &,SmsLookupStack *,EmsPinRowFlags,uchar,ulong *,_SmsQuickIndex *)
0x1400d7976  mov     [rsp+270h+var_208], eax
0x1400d797a  mov     rcx, [rbx]
0x1400d797d  inc     dword ptr [rcx+184h]
0x1400d7983  xor     r11d, r11d
0x1400d7986  test    r15, r15
0x1400d7989  jz      loc_1400D7A39
0x1400d798f  mov     r13, [r14+8]
0x1400d7993  lea     r9d, [r11+7]; unsigned int
0x1400d7997  mov     r12, r11
0x1400d799a  mov     ebx, r9d
0x1400d799d  mov     r10, [r15+130h]
0x1400d79a4  test    r10, r10
0x1400d79a7  jz      short loc_1400D7A15
0x1400d79a9  lea     rcx, [r15+138h]
0x1400d79b0  test    r9b, 1
0x1400d79b4  jz      short loc_1400D79E2
0x1400d79b6  mov     r8d, [rcx]
0x1400d79b9  cmp     [r15+180h], r8d
0x1400d79c0  jnz     short loc_1400D79E2
0x1400d79c2  mov     r12, r10
0x1400d79c5  lea     rdx, [r15+13Ch]
0x1400d79cc  test    r9b, 4
0x1400d79d0  jz      short loc_1400D7A04
0x1400d79d2  mov     eax, [rdx]
0x1400d79d4  cmp     [r15+184h], eax
0x1400d79db  jz      short loc_1400D7A00
0x1400d79dd  and     ebx, 0FFFFFFFBh
0x1400d79e0  jmp     short loc_1400D7A04
0x1400d79e2  test    r9b, 4
0x1400d79e6  jz      short loc_1400D7A15
0x1400d79e8  lea     rdx, [r15+13Ch]
0x1400d79ef  mov     eax, [rdx]
0x1400d79f1  cmp     [r15+184h], eax
0x1400d79f8  jnz     short loc_1400D7A15
0x1400d79fa  mov     r8d, [rcx]
0x1400d79fd  mov     r12, r10
0x1400d7a00  dec     eax
0x1400d7a02  mov     [rdx], eax
0x1400d7a04  lea     eax, [r8-1]
0x1400d7a08  mov     [rcx], eax
0x1400d7a0a  test    eax, eax
0x1400d7a0c  jnz     short loc_1400D7A15
0x1400d7a0e  mov     [r15+130h], r11
0x1400d7a15  mov     r8, r15; struct SmsPage *
0x1400d7a18  mov     rdx, r14; struct CmsTransactionCore *
0x1400d7a1b  mov     rcx, r13; this
0x1400d7a1e  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x1400d7a23  mov     r15, r12
0x1400d7a26  mov     r9d, ebx
0x1400d7a29  xor     r11d, r11d
0x1400d7a2c  test    r12, r12
0x1400d7a2f  jnz     loc_1400D7997
0x1400d7a35  mov     r13, qword ptr [rbp+170h+var_1D0.SizeOfBitMap]
0x1400d7a39  mov     r12d, [rsp+270h+var_208]
0x1400d7a3e  xor     r15d, r15d
0x1400d7a41  jmp     loc_1400D7AF5
0x1400d7a46  mov     r12d, r15d
0x1400d7a49  mov     [rsp+270h+var_208], r15d
0x1400d7a4e  lea     rbx, [rsi+30h]
0x1400d7a52  mov     r8, [rbx]; struct SmsPage *
0x1400d7a55  test    r8, r8
0x1400d7a58  jz      short loc_1400D7A73
0x1400d7a5a  mov     rdx, r14; struct CmsTransactionContext *
0x1400d7a5d  mov     rcx, [r13+70h]; this
0x1400d7a61  call    ?FindIndexHeaderInPage@CmsCompositeBase@@QEAAPEAU_SmsIndexHeader@@PEAVCmsTransactionContext@@PEAUSmsPage@@G@Z; CmsCompositeBase::FindIndexHeaderInPage(CmsTransactionContext *,SmsPage *,ushort)
0x1400d7a66  mov     [rsi+38h], rax
0x1400d7a6a  mov     [rsi+40h], r15
0x1400d7a6e  jmp     loc_1400D7AFE
0x1400d7a73  mov     ecx, [rdi]
0x1400d7a75  lea     eax, [rcx-5]
0x1400d7a78  cmp     eax, 1
0x1400d7a7b  jbe     short loc_1400D7ADE
0x1400d7a7d  cmp     ecx, 14h
0x1400d7a80  jnz     short loc_1400D7AB4
0x1400d7a82  mov     [rsp+270h+var_248], rbx
0x1400d7a87  mov     dword ptr [rsp+270h+var_250], 4
0x1400d7a8f  lea     r9, [rbp+170h+var_1A0]
0x1400d7a93  mov     r8, r13
0x1400d7a96  mov     rdx, r14
0x1400d7a99  mov     rcx, [r13+70h]
0x1400d7a9d  call    ?PinRoot@CmsCompositeBase@@QEAAJPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAPEAU_SmsIndexRoot@@W4_EMS_PIN_FLAGS@@PEAPEAUSmsPage@@@Z; CmsCompositeBase::PinRoot(CmsTransactionContext *,CmsBPlusTable *,_SmsIndexRoot * *,_EMS_PIN_FLAGS,SmsPage * *)
0x1400d7aa2  mov     r12d, eax
0x1400d7aa5  mov     [rsp+270h+var_208], eax
0x1400d7aa9  mov     rax, [rbx]
0x1400d7aac  inc     dword ptr [rax+184h]
0x1400d7ab2  jmp     short loc_1400D7AF5
0x1400d7ab4  cmp     ecx, 0Ch
0x1400d7ab7  jnz     short loc_1400D7B09
0x1400d7ab9  mov     [rsp+270h+var_248], rbx
0x1400d7abe  lea     rax, [rsp+270h+var_208]
0x1400d7ac3  mov     [rsp+270h+var_250], rax
0x1400d7ac8  lea     r9, [rsp+270h+var_200]
0x1400d7acd  lea     r8d, [rcx-8]
0x1400d7ad1  mov     rdx, r14
0x1400d7ad4  mov     rcx, r13
0x1400d7ad7  call    ?PinDataWithRoot@CmsBPlusTable@@UEAAJPEAVCmsTransactionContext@@W4_EMS_PIN_FLAGS@@PEAPEAXPEAKPEAUSmsLookupStack@@@Z; CmsBPlusTable::PinDataWithRoot(CmsTransactionContext *,_EMS_PIN_FLAGS,void * *,ulong *,SmsLookupStack *)
0x1400d7adc  jmp     short loc_1400D7AA2
0x1400d7ade  mov     rbx, [rsi+18h]
0x1400d7ae2  mov     r8, [rbx+8]; struct SmsPage *
0x1400d7ae6  mov     rdx, r14; struct CmsTransactionContext *
0x1400d7ae9  mov     rcx, [r13+70h]; this
0x1400d7aed  call    ?FindIndexHeaderInPage@CmsCompositeBase@@QEAAPEAU_SmsIndexHeader@@PEAVCmsTransactionContext@@PEAUSmsPage@@G@Z; CmsCompositeBase::FindIndexHeaderInPage(CmsTransactionContext *,SmsPage *,ushort)
0x1400d7af2  mov     [rbx], rax
0x1400d7af5  test    r12d, r12d
0x1400d7af8  js      loc_1400D7BAF
0x1400d7afe  mov     r10d, 2
0x1400d7b04  mov     rdx, [rsp+270h+var_200]; struct SmsTrashCleanerEntry *
0x1400d7b09  xorps   xmm0, xmm0
0x1400d7b0c  movups  [rbp+170h+var_198], xmm0
0x1400d7b10  mov     dword ptr [rbp+170h+var_188], r15d
0x1400d7b14  mov     qword ptr [rbp+170h+var_188+8], r15
0x1400d7b18  mov     ecx, [rdi]; this
0x1400d7b1a  cmp     ecx, 1Bh
0x1400d7b1d  jg      loc_1400D8AB9
0x1400d7b23  jz      loc_1400D8A98
0x1400d7b29  cmp     ecx, 0Dh
0x1400d7b2c  jg      loc_1400D86E0
0x1400d7b32  jz      loc_1400D86B9
0x1400d7b38  cmp     ecx, 7
0x1400d7b3b  jg      loc_1400D7DBB
0x1400d7b41  jz      loc_1400D83C6
0x1400d7b47  sub     ecx, 1; this
0x1400d7b4a  jz      loc_1400D7D83
0x1400d7b50  sub     ecx, 1
0x1400d7b53  jz      loc_1400D7C5A
0x1400d7b59  sub     ecx, 1
0x1400d7b5c  jz      loc_1400D7C5A
0x1400d7b62  sub     ecx, 1; this
0x1400d7b65  jz      loc_1400D898A
0x1400d7b6b  sub     ecx, 1
0x1400d7b6e  jz      loc_1400D7C0A
0x1400d7b74  cmp     ecx, 1
0x1400d7b77  jnz     short loc_1400D7BAF
0x1400d7b79  mov     r8, [rsi+18h]
0x1400d7b7d  lea     rax, [r8+8]
0x1400d7b81  mov     [rsp+270h+var_210], rax
0x1400d7b86  mov     rax, [rax+8]
0x1400d7b8a  mov     rcx, [rax+68h]
0x1400d7b8e  add     rcx, 50h ; 'P'
0x1400d7b92  mov     r9d, [rcx]
0x1400d7b95  add     r9, rcx; struct _SmsIndexHeader *
0x1400d7b98  mov     r8, [r8]; struct _SmsIndexHeader *
0x1400d7b9b  mov     rcx, [rsi+28h]; this
0x1400d7b9f  call    ?PopIndexRoot@CmsBPlusTable@@AEAAXPEAVCmsTransactionContext@@PEAU_SmsIndexHeader@@1@Z; CmsBPlusTable::PopIndexRoot(CmsTransactionContext *,_SmsIndexHeader *,_SmsIndexHeader *)
0x1400d7ba4  mov     rax, [rsi+28h]
0x1400d7ba8  nop
0x1400d7ba9  lock dec qword ptr [rax+38h]
0x1400d7bae  nop
0x1400d7baf  xor     r11d, r11d
0x1400d7bb2  mov     r15, [rsp+270h+var_210]
0x1400d7bb7  mov     ecx, 1
0x1400d7bbc  test    r15, r15
0x1400d7bbf  mov     r13, [rsp+270h+var_220]
0x1400d7bc4  jz      loc_1400D78AE
0x1400d7bca  lea     eax, [rcx+1]
0x1400d7bcd  test    eax, eax
0x1400d7bcf  jz      loc_1400D9504
0x1400d7bd5  mov     eax, ecx
0x1400d7bd7  mov     rdx, [r15+rax*8]
0x1400d7bdb  test    rdx, rdx
0x1400d7bde  jz      loc_1400D94FD
0x1400d7be4  mov     r8d, [r15+rax*4+10h]
0x1400d7be9  cmp     r8d, 1
0x1400d7bed  jnz     loc_1400D94F0
0x1400d7bf3  mov     [rdx+150h], r11
0x1400d7bfa  mov     rax, [r15+rax*8]
0x1400d7bfe  mov     [rax+0F8h], r11
0x1400d7c05  jmp     loc_1400D94FD
0x1400d7c0a  mov     r8, [rsi+18h]
0x1400d7c0e  lea     rax, [r8+8]
0x1400d7c12  mov     [rsp+270h+var_210], rax
0x1400d7c17  mov     rax, [rax+8]
0x1400d7c1b  mov     rcx, [rax+68h]
0x1400d7c1f  add     rcx, 50h ; 'P'
0x1400d7c23  mov     edx, [rcx]
0x1400d7c25  add     rdx, rcx
0x1400d7c28  mov     rax, [r8+10h]
0x1400d7c2c  mov     [rsp+270h+var_248], rax; union _LCN_TUPLE *
0x1400d7c31  mov     [rsp+270h+var_250], rdx; struct _SmsIndexHeader *
0x1400d7c36  xor     r9d, r9d; struct SmsLookupStack *
0x1400d7c39  mov     r8, [r8]; struct _SmsIndexHeader *
0x1400d7c3c  mov     rdx, r14; struct CmsTransactionContext *
0x1400d7c3f  mov     rcx, [rsi+28h]; this
0x1400d7c43  call    ?PushIndexRoot@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsIndexHeader@@PEAUSmsLookupStack@@1PEBT_LCN_TUPLE@@@Z; CmsBPlusTable::PushIndexRoot(CmsTransactionContext *,_SmsIndexHeader *,SmsLookupStack *,_SmsIndexHeader *,_LCN_TUPLE const *)
0x1400d7c48  mov     r12d, eax
0x1400d7c4b  mov     rax, [rsi+28h]
0x1400d7c4f  nop
0x1400d7c50  lock inc qword ptr [rax+38h]
0x1400d7c55  jmp     loc_1400D7BAE
0x1400d7c5a  test    [rsi+14h], r10b
0x1400d7c5e  jz      short loc_1400D7CA1
0x1400d7c60  mov     rcx, [rsi+38h]
0x1400d7c64  cmp     [rcx+14h], r15d
0x1400d7c68  jnz     short loc_1400D7CA1
0x1400d7c6a  mov     r9b, [rsi+15h]
0x1400d7c6e  test    r9b, r9b
0x1400d7c71  jz      short loc_1400D7CA1
0x1400d7c73  mov     al, [rcx+0Dh]
0x1400d7c76  and     al, 0F7h
0x1400d7c78  or      al, 1
0x1400d7c7a  mov     rdx, [rsi+28h]
0x1400d7c7e  mov     [rsp+270h+var_248], r15
0x1400d7c83  mov     byte ptr [rsp+270h+var_250], al
0x1400d7c87  mov     r8d, [rcx+20h]
0x1400d7c8b  mov     rdx, [rdx+18h]
0x1400d7c8f  call    ?InitializeIndexHeader@_SmsIndexHeader@@QEAAXPEBU_SmsPropertyDef@@KEW4_EMS_INDEX_IH_FLAGS@@_K@Z; _SmsIndexHeader::InitializeIndexHeader(_SmsPropertyDef const *,ulong,uchar,_EMS_INDEX_IH_FLAGS,unsigned __int64)
0x1400d7c94  mov     rcx, [rsi+28h]
0x1400d7c98  mov     al, [rsi+15h]
0x1400d7c9b  mov     [rcx+0D4h], al
0x1400d7ca1  mov     rcx, rsi; this
0x1400d7ca4  call    ?MmsGetUndoIndexEntry@SmsUndoRecord@@QEAAPEAU_SmsIndexEntry@@XZ; SmsUndoRecord::MmsGetUndoIndexEntry(void)
0x1400d7ca9  lea     rdx, [rbp+170h+var_1C0]
0x1400d7cad  mov     rcx, rax
0x1400d7cb0  call    ?ToRow@_SmsIndexEntry@@QEAA?AU_CmsRow@@XZ; _SmsIndexEntry::ToRow(void)
0x1400d7cb5  movups  xmm0, xmmword ptr [rax]
  ... truncated ...
```
