# CmsVolume::MakePageResident(CmsTransactionContext *,CmsBPlusTable *,SmsPage *,SmsChecksumBlob *,SmsPagingContext *,uchar)

- ea: `0x14007b9c0`
- end: `0x14007c388`
- name: `?MakePageResident@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAUSmsPage@@PEAUSmsChecksumBlob@@PEAUSmsPagingContext@@E@Z`
- size: `2504`
- prototype: `__int64 __usercall@<rax>(CmsVolume *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct CmsBPlusTable *@<r8>, struct SmsPage *@<r9>, struct SmsChecksumBlob *, struct SmsPagingContext *, unsigned __int8)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14007b390`

## callees

- `0x14000f670`
- `0x140010950`
- `0x140016f60`
- `0x140016f80`
- `0x140016f90`
- `0x140017020`
- `0x1400173c0`
- `0x140018360`
- `0x14006caf0`
- `0x14007b9c0`
- `0x14007c390`
- `0x1400f927c`
- `0x14011ac34`
- `0x14011acc4`
- `0x14011c310`
- `0x14011d2f0`
- `0x14011d318`
- `0x140127054`
- `0x1401270a8`
- `0x140129e84`
- `0x14012ad7c`
- `0x14012de60`
- `0x14012df10`
- `0x14017c804`
- `0x1401f3fc0`
- `0x1401f40a0`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1401ffb15`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401ffbe2`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401ffcaf`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401ffd7c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401fff9a`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401ffb15`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401ffbe2`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401ffcaf`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401ffd7c`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401fff9a`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1401ff9e4`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1401ff9e4`
- `ntoskrnl!ExAllocatePool2` at `0x1401fffff`
- `ntoskrnl!ExAllocatePool2` at `0x1401fffff`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14007c043`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14007c043`
- `ntoskrnl!ExReleasePushLockEx` at `0x14007bfff`
- `ntoskrnl!ExReleasePushLockEx` at `0x14007bfff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140200126`
- `ntoskrnl!ExFreePoolWithTag` at `0x140200126`

## pseudocode

```c
__int64 __fastcall CmsVolume::MakePageResident(
        CmsVolume *this,
        struct CmsTransactionContext *a2,
        CmsBPlusTable **a3,
        struct SmsPage *a4,
        struct SmsChecksumBlob *a5,
        struct SmsPagingContext *a6,
        unsigned __int8 a7)
{
  CmsBPlusTable **v8; // r13
  CmsVolume *v9; // r15
  char v10; // r12
  char v11; // si
  bool v12; // di
  NTSTATUS v13; // r14d
  unsigned int v14; // r9d
  struct CmsTransactionCore *v15; // rdx
  struct CmsTransactionContext *v16; // r10
  _WORD *v18; // r14
  __int16 v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // r10
  __int64 v22; // rdx
  unsigned __int64 v23; // rax
  bool v24; // r8
  bool v25; // r9
  CmsBPlusTable **k; // rax
  _DWORD *v27; // rdx
  char v28; // cl
  __int64 v29; // r9
  _DWORD *v30; // r10
  __int128 v31; // xmm1
  unsigned int m; // ecx
  unsigned int n; // ecx
  unsigned __int64 v34; // r8
  unsigned __int64 v35; // r8
  __int64 v36; // rdx
  struct CmsTransactionContext *v37; // rcx
  unsigned int v38; // r9d
  bool v39; // zf
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 *jj; // r9
  __int64 v43; // rax
  __int64 v44; // rax
  unsigned int v45; // esi
  __int128 *v46; // r8
  __int128 *v47; // rcx
  unsigned int j; // edx
  __int64 v49; // r9
  unsigned int v50; // edx
  int v51; // r8d
  unsigned int v52; // esi
  _QWORD *v53; // r8
  __int128 *v54; // rcx
  unsigned int kk; // edx
  __int64 v56; // r9
  __int64 v57; // r11
  __int64 v58; // rax
  struct CmsBPlusTable *v59; // rax
  __int64 v60; // rdx
  unsigned __int16 v61; // si
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  struct CmsBPlusTable *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r10
  unsigned int v67; // r9d
  struct CmsTransactionContext *v68; // r10
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r13
  __int64 v73; // rax
  __int64 v74; // r14
  void *v75; // r15
  __int64 v76; // r12
  char v77; // si
  CmsBPlusTable *v78; // rdx
  int v79; // edi
  __int64 v80; // rdx
  __int64 v81; // rcx
  int ActivityIdThread; // eax
  int v83; // edx
  __int64 v84; // r13
  __int64 v85; // rax
  __int64 v86; // r14
  __int64 v87; // r15
  __int64 v88; // r12
  char v89; // si
  CmsBPlusTable *v90; // rdx
  int v91; // edi
  __int64 v92; // rdx
  __int64 v93; // rcx
  int v94; // eax
  int v95; // edx
  __int64 v96; // r13
  __int64 v97; // rax
  __int64 v98; // r14
  __int64 v99; // r15
  __int64 v100; // r12
  char v101; // si
  CmsBPlusTable *v102; // rdx
  int v103; // edi
  __int64 v104; // rdx
  __int64 v105; // rcx
  int v106; // eax
  int v107; // edx
  __int64 v108; // r13
  __int64 v109; // rax
  __int64 v110; // r14
  __int64 v111; // r15
  __int64 v112; // r12
  char v113; // si
  CmsBPlusTable *v114; // rdx
  int v115; // edi
  __int64 v116; // rdx
  __int64 v117; // rcx
  int v118; // eax
  int v119; // edx
  __int128 v120; // xmm0
  __int128 v121; // xmm1
  unsigned int i; // ecx
  struct CmsBPlusTable *v123; // rax
  __int64 v124; // rdx
  bool v125; // r8
  _BOOL8 v126; // r9
  __int64 v127; // rcx
  struct CmsBPlusTable *v128; // rax
  __int64 v129; // rdx
  CmsBPlusTable **v130; // rdi
  void *v131; // rsi
  __int64 v132; // rax
  __int64 v133; // rdx
  char v134; // al
  __int64 Pool2; // rax
  __int64 v136; // rsi
  _DWORD *v137; // rax
  char v138; // cl
  struct CmsBPlusTable *v139; // rax
  __int64 v140; // rdx
  unsigned __int8 v141; // r9
  int v142; // esi
  unsigned int v143; // edi
  union _LCN_TUPLE *v144; // [rsp+20h] [rbp-1F8h]
  unsigned int v145; // [rsp+28h] [rbp-1F0h]
  unsigned __int8 v146; // [rsp+50h] [rbp-1C8h]
  char v147; // [rsp+80h] [rbp-198h]
  char v148; // [rsp+81h] [rbp-197h]
  int v149; // [rsp+84h] [rbp-194h] BYREF
  unsigned __int8 v150[8]; // [rsp+88h] [rbp-190h] BYREF
  struct CmsTransactionContext *v151; // [rsp+90h] [rbp-188h]
  unsigned int v152; // [rsp+9Ch] [rbp-17Ch]
  struct _IO_REMOVE_LOCK *v153; // [rsp+A0h] [rbp-178h]
  unsigned int v154; // [rsp+A8h] [rbp-170h]
  int ii; // [rsp+ACh] [rbp-16Ch]
  _DWORD *v156; // [rsp+B0h] [rbp-168h]
  __int64 v157; // [rsp+B8h] [rbp-160h]
  struct SmsChecksumBlob *v158; // [rsp+C0h] [rbp-158h]
  __int64 v159; // [rsp+C8h] [rbp-150h]
  NTSTATUS v160; // [rsp+D0h] [rbp-148h]
  _QWORD v161[2]; // [rsp+E0h] [rbp-138h] BYREF
  __int64 v162; // [rsp+F0h] [rbp-128h]
  struct CmsBPlusTable *v163; // [rsp+F8h] [rbp-120h]
  _QWORD v164[2]; // [rsp+100h] [rbp-118h] BYREF
  __int128 v165; // [rsp+110h] [rbp-108h] BYREF
  __int128 v166; // [rsp+120h] [rbp-F8h]
  _OWORD v167[2]; // [rsp+130h] [rbp-E8h]
  __int128 v168; // [rsp+150h] [rbp-C8h] BYREF
  __int128 v169; // [rsp+160h] [rbp-B8h]
  __int128 v170; // [rsp+170h] [rbp-A8h] BYREF
  __int128 v171; // [rsp+180h] [rbp-98h]
  __int128 v172; // [rsp+190h] [rbp-88h] BYREF
  _OWORD v173[2]; // [rsp+1A0h] [rbp-78h] BYREF
  __int128 v174; // [rsp+1C0h] [rbp-58h] BYREF

  v8 = a3;
  v161[0] = a3;
  v151 = a2;
  v9 = this;
  v153 = (struct _IO_REMOVE_LOCK *)this;
  v164[0] = this;
  v163 = (struct CmsBPlusTable *)a3;
  *(_QWORD *)&v168 = a4;
  v158 = a5;
  v156 = a6;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v150[0] = 0;
  if ( !a7 )
  {
    v13 = MsKmeLockPages(*((void **)a4 + 13), *((_DWORD *)a4 + 80), (void **)a4 + 84);
    v14 = v156[40];
    v149 = v14;
    v15 = (struct CmsTransactionCore *)(v14 >> 1);
    v12 = (v14 & 2) != 0;
    v148 = v12;
    if ( v13 < 0 )
      goto LABEL_11;
    v10 = 1;
    v16 = v151;
    if ( *((CmsBPlusTable ***)v151 + 422) != v8
      || (v57 = *((_QWORD *)v151 + 423)) != 0
      && (v58 = *(unsigned __int8 *)(v57 + 6), (unsigned __int8)v58 < 0xAu)
      && *(_QWORD *)a4 == *(_QWORD *)(v57 + 8 * v58 + 24) )
    {
      if ( (v14 & 2) == 0 )
      {
        _InterlockedIncrement(&dword_140269594);
        goto LABEL_6;
      }
    }
    else
    {
      v61 = *(_WORD *)(*(_QWORD *)(v57 + 856) + 4LL);
      v156[40] = v14 & 0xFFFFFFEE;
      v12 = 1;
      v148 = 1;
      v62 = *(_OWORD *)a4;
      v168 = *(_OWORD *)a4;
      v63 = *((_OWORD *)a4 + 1);
      v169 = v63;
      if ( (*(_BYTE *)(*((_QWORD *)a4 + 12) + 16LL) & 4) == 0 )
      {
        v165 = v62;
        v166 = v63;
        LOBYTE(v144) = 0;
        v13 = CmsVolumeContainer::PinContainerRange(*((_QWORD *)v9 + 409), v16, &v165, &v168);
        if ( v13 < 0 )
          goto LABEL_121;
      }
      v64 = CmsBPlusTable::BindableUnitTable(v8[4]);
      v13 = CmsVolume::SmartIoScrubPage(
              v9,
              *(void **)(*(_QWORD *)(v65 + 40) + 72LL),
              (union SmsBigIdentifier *)(*((_QWORD *)v64 + 9) + 376LL),
              (const union _LCN_TUPLE *)&v168,
              *((void **)a4 + 13),
              v145,
              v158,
              v67,
              *(struct _SmsScrubIoOutput **)(v66 + 848),
              *(struct _SCRUB_PARITY_EXTENT_DATA **)(v66 + 856),
              v146,
              v150);
      *(_QWORD *)(*((_QWORD *)v151 + 423) + 864LL) += *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v151 + 423) + 848LL) + 24LL);
      if ( FsRtlIsTotalDeviceFailure(v13) )
        goto LABEL_121;
      v68 = v151;
      if ( v13 >= 0 )
      {
        v69 = *((_QWORD *)v151 + 423);
        if ( v69 )
        {
          if ( *(_BYTE *)(v69 + 6) < 0xAu )
            *(_QWORD *)(v69 + 8LL * *(unsigned __int8 *)(v69 + 6) + 24) = *(_QWORD *)a4;
        }
      }
      if ( (unsigned __int8)MsScrubIoFoundError(*(_QWORD *)(*((_QWORD *)v68 + 423) + 848LL))
        || *(_WORD *)(*(_QWORD *)(v71 + 856) + 4LL) > v61 )
      {
        MsScrubContextCaptureError(v71, v70);
      }
      if ( !v150[0] || v13 < 0 || (v149 & 1) != 0 || (v156[40] & 2) == 0 )
      {
LABEL_121:
        v11 = 1;
        goto LABEL_11;
      }
      v11 = 1;
    }
    _InterlockedIncrement(&dword_140269590);
    _InterlockedIncrement(&dword_140269504);
    if ( *((_BYTE *)v158 + 2) != *((_BYTE *)v9 + 88) )
    {
      v13 = -1073740520;
      goto LABEL_12;
    }
    v18 = (_WORD *)*((_QWORD *)v9 + 442);
    v19 = v18[4];
    v156 = v18 + 6;
    if ( v19 )
    {
      v20 = (unsigned __int64)*(unsigned int *)(*((_QWORD *)v16 + 1) + 3332LL) >> ((unsigned __int8)v18[10]
                                                                                 - *((_BYTE *)v18 + 12));
      v156 = v18 + 6;
    }
    else
    {
      LODWORD(v20) = 0;
    }
    if ( *((_DWORD *)v158 + 1) != (_DWORD)v20 )
    {
      v13 = -1073740520;
      goto LABEL_12;
    }
    v21 = *((_QWORD *)a4 + 13);
    *(_QWORD *)&v168 = (char *)v158 + *((unsigned __int8 *)v158 + 3);
    v163 = *(struct CmsBPlusTable **)(*(_QWORD *)v18 + 40LL);
    v22 = *((unsigned int *)a4 + 80);
    if ( v19 )
      v23 = (unsigned __int64)(unsigned int)v22 >> ((unsigned __int8)v18[10] - *(_BYTE *)v156);
    else
      v23 = 0;
    *((_QWORD *)&v168 + 1) = v23;
    v164[0] = v21;
    v164[1] = v22;
    v13 = ((__int64 (__fastcall *)(_WORD *, _QWORD *, __int128 *, _QWORD, _QWORD, _QWORD))v163)(
            v18,
            v164,
            &v168,
            0,
            0,
            0);
    if ( v13 >= 0 )
    {
      v13 = CmsBPlusTable::CheckPage(*((CmsBPlusTable **)a4 + 12), a4, v24, v25);
      v149 = v13;
      if ( v13 < 0 )
      {
        v59 = CmsBPlusTable::BindableUnitTable(v8[4]);
        ProcessCheckPageFailure(
          *((struct _VCB **)v9 + 6),
          *(void **)(*(_QWORD *)(v60 + 40) + 72LL),
          (union SmsBigIdentifier *)(*((_QWORD *)v59 + 9) + 376LL),
          &v149);
        v13 = v149;
      }
    }
    v16 = v151;
LABEL_6:
    if ( v13 >= 0 )
    {
LABEL_7:
      if ( v11 )
        CmsVolume::CleanBackingPage(v9, v15, a4);
      _InterlockedOr((volatile signed __int32 *)a4 + 138, 4u);
      return (unsigned int)v13;
    }
    v170 = 0;
    v171 = 0;
    v172 = 0;
    if ( v13 == -1073740688 && dword_1402473A4 == 1 )
    {
      if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
      {
        v149 = *((_QWORD *)v16 + 422) == (_QWORD)v8;
        v72 = *((_QWORD *)v9 + 258);
        v73 = *((_QWORD *)a4 + 13);
        v74 = *(_QWORD *)(v73 + 16);
        v75 = *(void **)a4;
        v76 = *(_QWORD *)(v73 + 32);
        v77 = CmsBPlusTable::EtwTableIdLow(*((CmsBPlusTable **)a4 + 12));
        v79 = CmsBPlusTable::EtwTableIdHigh(v78);
        ActivityIdThread = IoGetActivityIdThread(v81, v80);
        McTemplateK0iiiiiit_EtwWriteTransfer(
          (unsigned int)MinstoreEventProvider_Context,
          v83,
          ActivityIdThread,
          v79,
          v77,
          v76,
          (char)v75,
          v74,
          v72,
          v149);
        v12 = v148;
        v9 = (CmsVolume *)v153;
        v8 = (CmsBPlusTable **)v161[0];
        v10 = 1;
        v16 = v151;
      }
      if ( dword_1402473A4 == 1 )
      {
        if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
        {
          v149 = *((_QWORD *)v16 + 422) == (_QWORD)v8;
          v84 = *((_QWORD *)v9 + 258);
          v85 = *((_QWORD *)a4 + 13);
          v86 = *(_QWORD *)(v85 + 16);
          v87 = *((_QWORD *)a4 + 1);
          v88 = *(_QWORD *)(v85 + 40);
          v89 = CmsBPlusTable::EtwTableIdLow(*((CmsBPlusTable **)a4 + 12));
          v91 = CmsBPlusTable::EtwTableIdHigh(v90);
          v94 = IoGetActivityIdThread(v93, v92);
          McTemplateK0iiiiiit_EtwWriteTransfer(
            (unsigned int)MinstoreEventProvider_Context,
            v95,
            v94,
            v91,
            v89,
            v88,
            v87,
            v86,
            v84,
            v149);
          v12 = v148;
          v9 = (CmsVolume *)v153;
          v8 = (CmsBPlusTable **)v161[0];
          v10 = 1;
          v16 = v151;
        }
        if ( dword_1402473A4 == 1 )
        {
          if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
          {
            v149 = *((_QWORD *)v16 + 422) == (_QWORD)v8;
            v96 = *((_QWORD *)v9 + 258);
            v97 = *((_QWORD *)a4 + 13);
            v98 = *(_QWORD *)(v97 + 16);
            v99 = *((_QWORD *)a4 + 2);
            v100 = *(_QWORD *)(v97 + 48);
            v101 = CmsBPlusTable::EtwTableIdLow(*((CmsBPlusTable **)a4 + 12));
            v103 = CmsBPlusTable::EtwTableIdHigh(v102);
            v106 = IoGetActivityIdThread(v105, v104);
            McTemplateK0iiiiiit_EtwWriteTransfer(
              (unsigned int)MinstoreEventProvider_Context,
              v107,
              v106,
              v103,
              v101,
              v100,
              v99,
              v98,
              v96,
              v149);
            v12 = v148;
            v9 = (CmsVolume *)v153;
            v8 = (CmsBPlusTable **)v161[0];
            v10 = 1;
            v16 = v151;
          }
          if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
          {
            v149 = *((_QWORD *)v16 + 422) == (_QWORD)v8;
            v108 = *((_QWORD *)v9 + 258);
            v109 = *((_QWORD *)a4 + 13);
            v110 = *(_QWORD *)(v109 + 16);
            v111 = *((_QWORD *)a4 + 3);
            v112 = *(_QWORD *)(v109 + 56);
            v113 = CmsBPlusTable::EtwTableIdLow(*((CmsBPlusTable **)a4 + 12));
            v115 = CmsBPlusTable::EtwTableIdHigh(v114);
            v118 = IoGetActivityIdThread(v117, v116);
            McTemplateK0iiiiiit_EtwWriteTransfer(
              (unsigned int)MinstoreEventProvider_Context,
              v119,
              v118,
              v115,
              v113,
              v112,
              v111,
              v110,
              v108,
              v149);
            v12 = v148;
            v9 = (CmsVolume *)v153;
            v8 = (CmsBPlusTable **)v161[0];
            v10 = 1;
            v16 = v151;
          }
        }
      }
    }
    v120 = *(_OWORD *)a4;
    v168 = *(_OWORD *)a4;
    v121 = *((_OWORD *)a4 + 1);
    v169 = v121;
    if ( (*(_BYTE *)(*((_QWORD *)a4 + 12) + 16LL) & 4) == 0 )
    {
      v165 = v120;
      v166 = v121;
      LOBYTE(v144) = 0;
      v13 = CmsVolumeContainer::PinContainerRange(*((_QWORD *)v9 + 409), v16, &v165, &v168);
      if ( v13 < 0 )
      {
LABEL_142:
        v11 = 1;
        goto LABEL_11;
      }
      for ( i = 0; i < 4; ++i )
      {
        if ( *((__int64 *)&v168 + i) < 0 )
        {
          v13 = -1073740688;
          goto LABEL_142;
        }
      }
    }
    v147 = 1;
    v170 = 0;
    v171 = 0;
    v172 = 0;
    if ( (_QWORD)v168 )
    {
      v45 = 1;
      v46 = &v170;
      v47 = &v172;
      *(_QWORD *)&v170 = v168;
      LODWORD(v172) = 1;
      for ( j = 1; j < 4; ++j )
      {
        v49 = *((_QWORD *)&v168 + j);
        if ( !v49 )
          break;
        if ( v49 == *(_QWORD *)v46 + *(unsigned int *)v47 )
        {
          ++*(_DWORD *)v47;
        }
        else
        {
          v46 = (__int128 *)((char *)v46 + 8);
          v47 = (__int128 *)((char *)v47 + 4);
          ++v45;
          *(_QWORD *)v46 = v49;
          *(_DWORD *)v47 = 1;
        }
      }
      if ( v45 )
      {
        v50 = 0;
        v51 = *((_DWORD *)v9 + 16);
        do
        {
          *((_QWORD *)&v170 + v50) <<= v51;
          *((_DWORD *)&v173[-1] + v50++) <<= v51;
        }
        while ( v50 < v45 );
      }
    }
    v123 = CmsBPlusTable::BindableUnitTable(v8[4]);
    v144 = (union _LCN_TUPLE *)&v170;
    v13 = CmsVolume::SmartIoReadAndRepair(
            v9,
            *(_QWORD *)(*(_QWORD *)(v124 + 40) + 72LL),
            *((_QWORD *)v123 + 9) + 376LL,
            0);
    if ( v13 >= 0 )
    {
      v13 = CmsBPlusTable::CheckPage(*((CmsBPlusTable **)a4 + 12), a4, v125, v126);
      v149 = v13;
      if ( v13 < 0 )
      {
        v128 = CmsBPlusTable::BindableUnitTable(v8[4]);
        ProcessCheckPageFailure(
          *((struct _VCB **)v9 + 6),
          *(void **)(*(_QWORD *)(v129 + 40) + 72LL),
          (union SmsBigIdentifier *)(*((_QWORD *)v128 + 9) + 376LL),
          &v149);
        v13 = v149;
      }
      if ( v13 < 0 )
        goto LABEL_153;
      if ( dword_1402473A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
      {
        v130 = (CmsBPlusTable **)*((_QWORD *)v151 + 422);
        v131 = *(void **)a4;
        v132 = IoGetActivityIdThread(v127, v15);
        LOBYTE(v144) = v130 == v8;
        McTemplateK0it_EtwWriteTransfer(MinstoreEventProvider_Context, v133, v132, v131);
        v12 = v148;
      }
    }
    if ( v13 >= 0 )
    {
      v134 = 1;
      goto LABEL_154;
    }
LABEL_153:
    v12 = 1;
    v134 = 0;
    v13 = -1073740688;
    v147 = 0;
LABEL_154:
    if ( v134 || (*(_BYTE *)v151 & 0x20) == 0 )
    {
      Pool2 = ExAllocatePool2(66, 256, 1766871885, v126);
      v136 = Pool2;
      if ( Pool2 )
      {
        *(_DWORD *)Pool2 = 10;
        *(_QWORD *)(Pool2 + 8) = *((_QWORD *)v9 + 6);
        *(_DWORD *)(Pool2 + 16) = v13;
        *(_OWORD *)(Pool2 + 24) = *(_OWORD *)(*((_QWORD *)CmsBPlusTable::BindableUnitTable(v8[4]) + 9) + 376LL);
        *(_BYTE *)(v136 + 40) = v147;
        *(_BYTE *)(v136 + 41) = 1;
        *(_WORD *)(v136 + 42) = 4;
        *(_QWORD *)(v136 + 48) = a4;
        v137 = (_DWORD *)*((_QWORD *)a4 + 13);
        if ( *v137 == 725766989 )
        {
          *(_QWORD *)(v136 + 56) = v137 + 8;
          *(_QWORD *)(v136 + 64) = *((_QWORD *)a4 + 13) + 64LL;
          *(_DWORD *)(v136 + 72) = **((_DWORD **)a4 + 13);
          *(_QWORD *)(v136 + 80) = *(_QWORD *)(*((_QWORD *)a4 + 13) + 16LL);
          *(_DWORD *)(v136 + 88) = *(_DWORD *)(*((_QWORD *)a4 + 13) + 12LL);
          v138 = *(_BYTE *)(*((_QWORD *)a4 + 13) + 8LL);
        }
        else
        {
          *(_QWORD *)(v136 + 56) = 0;
          *(_QWORD *)(v136 + 64) = 0;
          *(_DWORD *)(v136 + 72) = 0;
          *(_QWORD *)(v136 + 80) = 0;
          *(_DWORD *)(v136 + 88) = 0;
          v138 = 0;
        }
        *(_BYTE *)(v136 + 92) = v138;
        *(_BYTE *)(v136 + 93) = (*((_DWORD *)v9 + 849) & 0x40000000) != 0;
        *(_QWORD *)(v136 + 96) = *((_QWORD *)v9 + 258);
      }
      v139 = CmsBPlusTable::BindableUnitTable(v8[4]);
      MsKmeChecksumEventNotification(
        *((struct _VCB **)v9 + 6),
        *(void **)(*(_QWORD *)(v140 + 40) + 72LL),
        (union SmsBigIdentifier *)(*((_QWORD *)v139 + 9) + 376LL),
        v13,
        v141,
        (struct _MS_TELEMETRY_DATA *)v136);
      if ( v136 )
        ExFreePoolWithTag((PVOID)v136, 0);
    }
    v11 = 1;
    goto LABEL_11;
  }
  v13 = MsKmeLockPages(*((void **)a4 + 13), *((_DWORD *)a4 + 80), (void **)a4 + 84);
  v149 = v13;
  if ( v13 < 0 )
    goto LABEL_11;
  memset(*((void **)a4 + 13), 0, 0xA0u);
  memset((void *)(*((_QWORD *)a4 + 13) + 4096LL), 0, 0x50u);
  memset((void *)(*((_QWORD *)a4 + 13) + 0x2000LL), 0, 0x50u);
  memset((void *)(*((_QWORD *)a4 + 13) + 12288LL), 0, 0x50u);
  for ( k = v8; k[8] != (CmsBPlusTable *)k; k = (CmsBPlusTable **)k[8] )
    ;
  v158 = (CmsBPlusTable *)((char *)k[9] + 376);
  v156 = (_DWORD *)*((_QWORD *)a4 + 13);
  memset(v156, 0, 0x50u);
  v27 = v156;
  *v156 = 725766989;
  v27[3] = *((_DWORD *)v9 + 832);
  *((_QWORD *)v27 + 2) = *((_QWORD *)v9 + 258);
  *((_QWORD *)v27 + 3) = *((_QWORD *)v9 + 260);
  *((_OWORD *)v27 + 2) = *(_OWORD *)a4;
  *((_OWORD *)v27 + 3) = *((_OWORD *)a4 + 1);
  *((_BYTE *)v27 + 4) = 2;
  if ( v158 )
    *((_OWORD *)v27 + 4) = *(_OWORD *)v158;
  v28 = -1;
  if ( *((_DWORD *)v9 + 855) < 0xFFu )
    v28 = *((_DWORD *)v9 + 855);
  *((_BYTE *)v27 + 8) = v28;
  if ( *((_BYTE *)a4 + 392) != 0xF8 )
  {
    v44 = *((_QWORD *)a4 + 13);
    *(_QWORD *)(v44 + 80) = 0;
    *(_DWORD *)(v44 + 80) = 8;
  }
  v15 = (struct SmsPage *)((char *)a4 + 32);
  if ( (*(_BYTE *)(*((_QWORD *)a4 + 12) + 16LL) & 4) != 0 )
  {
    *(_OWORD *)v15 = *(_OWORD *)a4;
    *((_OWORD *)a4 + 3) = *((_OWORD *)a4 + 1);
LABEL_60:
    v41 = *((_QWORD *)v151 + 423);
    if ( v41 )
      *(_QWORD *)(v41 + 864) += *((unsigned int *)a4 + 80);
  }
  else
  {
    v13 = CmsVolumeContainer::SetContainerStationaryVolatile(
            *((CmsVolumeContainer **)v9 + 409),
            v151,
            a4,
            1,
            (struct SmsPage *)((char *)a4 + 32));
    v149 = v13;
    if ( v13 >= 0 )
    {
      _InterlockedOr((volatile signed __int32 *)a4 + 138, 0x40u);
      v30 = (_DWORD *)*((_QWORD *)v9 + 409);
      v156 = v30;
      v31 = *((_OWORD *)a4 + 1);
      v167[0] = *(_OWORD *)a4;
      v167[1] = v31;
      v13 = 0;
      v160 = 0;
      v158 = 0;
      v159 = 0;
      v154 = 0;
      for ( m = 0; ; ++m )
      {
        v154 = m;
        if ( m >= 4 )
          break;
        v15 = (struct CmsTransactionCore *)*((_QWORD *)v167 + m);
        v158 = v15;
        v159 = 1;
        if ( v15 )
        {
          v161[0] = v15;
          v161[1] = 1;
          LOBYTE(v144) = 0;
          LOBYTE(v29) = 1;
          v13 = CmsVolumeContainer::PinContainerRange(v30, v151, v161, v29);
          v160 = v13;
          if ( v13 < 0 )
            break;
          m = v154;
          v30 = v156;
        }
      }
      v149 = v13;
      if ( v13 >= 0 )
      {
        v15 = (struct CmsTransactionCore *)*((_QWORD *)v9 + 409);
        v153 = (struct _IO_REMOVE_LOCK *)v15;
        v165 = *(_OWORD *)a4;
        v166 = *((_OWORD *)a4 + 1);
        v156 = 0;
        v157 = 0;
        for ( n = 0; ; ++n )
        {
          v152 = n;
          if ( n >= 4 )
            goto LABEL_60;
          v34 = *((_QWORD *)&v165 + n);
          if ( v34 )
            break;
LABEL_59:
          ;
        }
        v156 = (_DWORD *)*((_QWORD *)&v165 + n);
        v157 = 1;
        v35 = v34 >> ((unsigned __int8)*(_DWORD *)(*((_QWORD *)v15 + 1) + 80LL) + 1);
        v36 = 0;
        v162 = 0;
        ii = 0;
        v37 = v151;
        if ( v151 )
        {
          v38 = 0;
          for ( ii = 0; ; ii = v38 )
          {
            v39 = v38 == 4;
            if ( v38 >= 4 )
              break;
            v40 = *((_QWORD *)v151 + v38 + 37);
            if ( v40 && *(_QWORD *)(v40 + 592) == v35 )
            {
              v36 = *((_QWORD *)v151 + v38 + 37);
              v162 = v36;
              v39 = (*((_DWORD *)v151 + v38 + 84))-- == 1;
              if ( !v39 )
                goto LABEL_58;
              *((_QWORD *)v37 + v38 + 37) = 0;
              v39 = v38 == 4;
              break;
            }
            ++v38;
          }
          if ( !v39 )
            goto LABEL_54;
        }
        else
        {
          ii = 4;
        }
        for ( jj = (__int64 *)*((_QWORD *)v37 + 41); jj; jj = (__int64 *)*jj )
        {
          v43 = jj[1];
          if ( v43 && *(_QWORD *)(v43 + 592) == v35 )
          {
            v36 = jj[1];
            v162 = v36;
            v39 = (*((_DWORD *)jj + 4))-- == 1;
            if ( !v39 )
              goto LABEL_58;
            jj[1] = 0;
            break;
          }
        }
LABEL_54:
        ExReleasePushLockEx(v36 + 120, 2);
        if ( v151 )
          --*((_DWORD *)v151 + 89);
        _InterlockedDecrement((volatile signed __int32 *)(v162 + 92));
        IoReleaseRemoveLockEx(v153 + 15, 0, 0x20u);
        if ( v151 )
          --*((_DWORD *)v151 + 88);
LABEL_58:
        v15 = (struct CmsTransactionCore *)v153;
        n = v152;
        goto LABEL_59;
      }
    }
  }
LABEL_11:
  if ( v13 >= 0 )
    goto LABEL_7;
LABEL_12:
  if ( v10 )
  {
    MsKmeUnlockPages(*((PMDL *)a4 + 84));
    *((_QWORD *)a4 + 84) = 0;
  }
  if ( v12 )
  {
    memset(v173, 0, sizeof(v173));
    v174 = 0;
    v142 = 0;
    CmsChecksum::GenerateChecksum(*((_QWORD *)a4 + 13), (char *)a4 + 120);
    if ( *((_QWORD *)a4 + 16) )
    {
      MsKmeUnpinData();
      v143 = 0;
      *((_QWORD *)a4 + 16) = 0;
      *((_QWORD *)a4 + 15) = 0;
      v142 = 1;
    }
    else
    {
      v143 = 0;
    }
    if ( *((_QWORD *)a4 + 20) )
    {
      MsKmeUnpinData();
      *((_QWORD *)a4 + 20) = 0;
      *((_QWORD *)a4 + 19) = 0;
      ++v142;
    }
    if ( *((_QWORD *)a4 + 24) )
    {
      MsKmeUnpinData();
      *((_QWORD *)a4 + 24) = 0;
      *((_QWORD *)a4 + 23) = 0;
      ++v142;
    }
    if ( *((_QWORD *)a4 + 28) )
    {
      MsKmeUnpinData();
      *((_QWORD *)a4 + 28) = 0;
      *((_QWORD *)a4 + 27) = 0;
      ++v142;
    }
    if ( v142 )
    {
      _InterlockedAnd((volatile signed __int32 *)a4 + 138, 0xFFFFFFFD);
      MsKmeFreeBaseAddressFromTuple(*((void **)a4 + 13), *((void **)a4 + 14), (struct SmsPage *)((char *)a4 + 120));
      *((_QWORD *)a4 + 13) = 0;
      *((_QWORD *)a4 + 14) = 0;
      _InterlockedDecrement((volatile signed __int32 *)&DbgCounts);
    }
    if ( *(_QWORD *)a4 )
    {
      v52 = 1;
      v53 = v173;
      v54 = &v174;
      *(_QWORD *)&v173[0] = *(_QWORD *)a4;
      LODWORD(v174) = 1;
      for ( kk = 1; kk < 4; ++kk )
      {
        v56 = *((_QWORD *)a4 + kk);
        if ( !v56 )
          break;
        if ( v56 == *v53 + *(unsigned int *)v54 )
        {
          ++*(_DWORD *)v54;
        }
        else
        {
          ++v53;
          v54 = (__int128 *)((char *)v54 + 4);
          ++v52;
          *v53 = v56;
          *(_DWORD *)v54 = 1;
        }
      }
    }
    else
    {
      v52 = 0;
    }
    if ( v52 )
    {
      do
      {
        *(_QWORD *)&v168 = *((_QWORD *)v173 + v143);
        *((_QWORD *)&v168 + 1) = *((unsigned int *)&v174 + v143);
        CmsVolume::Purge(
          v9,
          (struct CmsTransactionCore *)v143++,
          (struct CmsBPlusTable *)v8,
          (const struct _RANGE *)&v168,
          (unsigned __int8)v144);
      }
      while ( v143 < v52 );
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14007b9c0  push    rbx
0x14007b9c2  push    rsi
0x14007b9c3  push    rdi
0x14007b9c4  push    r12
0x14007b9c6  push    r13
0x14007b9c8  push    r14
0x14007b9ca  push    r15
0x14007b9cc  sub     rsp, 1E0h
0x14007b9d3  mov     rax, cs:__security_cookie
0x14007b9da  xor     rax, rsp
0x14007b9dd  mov     [rsp+218h+var_48], rax
0x14007b9e5  mov     rbx, r9
0x14007b9e8  mov     r13, r8
0x14007b9eb  mov     [rsp+218h+var_138], r8
0x14007b9f3  mov     [rsp+218h+var_188], rdx
0x14007b9fb  mov     r15, rcx
0x14007b9fe  mov     [rsp+218h+var_178], rcx
0x14007ba06  mov     [rsp+218h+var_118], rcx
0x14007ba0e  mov     [rsp+218h+var_120], r8
0x14007ba16  mov     qword ptr [rsp+218h+var_C8], rbx
0x14007ba1e  mov     rax, [rsp+218h+arg_20]
0x14007ba26  mov     [rsp+218h+var_158], rax
0x14007ba2e  mov     rax, [rsp+218h+arg_28]
0x14007ba36  mov     [rsp+218h+var_168], rax
0x14007ba3e  xor     r12b, r12b
0x14007ba41  xor     sil, sil
0x14007ba44  xor     dil, dil
0x14007ba47  mov     [rsp+218h+var_190], sil
0x14007ba4f  cmp     [rsp+218h+arg_30], sil
0x14007ba57  jnz     loc_14007BC6C
0x14007ba5d  lea     r8, [r9+2A0h]; void **
0x14007ba64  mov     edx, [r9+140h]; unsigned int
0x14007ba6b  mov     rcx, [r9+68h]; void *
0x14007ba6f  call    ?MsKmeLockPages@@YAJPEAXKPEAPEAX@Z; MsKmeLockPages(void *,ulong,void * *)
0x14007ba74  mov     r14d, eax
0x14007ba77  mov     r8, [rsp+218h+var_168]
0x14007ba7f  mov     r9d, [r8+0A0h]
0x14007ba86  mov     [rsp+218h+var_194], r9d
0x14007ba8e  mov     edx, r9d
0x14007ba91  shr     edx, 1; struct CmsTransactionCore *
0x14007ba93  movzx   edi, dl
0x14007ba96  and     dil, 1
0x14007ba9a  mov     [rsp+218h+var_197], dil
0x14007baa2  test    eax, eax
0x14007baa4  js      short loc_14007BB1A
0x14007baa6  mov     r12b, 1
0x14007baa9  mov     [rsp+218h+var_198], r12b
0x14007bab1  mov     r10, [rsp+218h+var_188]
0x14007bab9  cmp     [r10+0D30h], r13
0x14007bac0  jz      loc_14007C2EA
0x14007bac6  test    r12b, dl
0x14007bac9  jnz     short loc_14007BB46
0x14007bacb  nop
0x14007bacc  lock inc cs:dword_140269594
0x14007bad3  nop
0x14007bad4  xor     r11d, r11d
0x14007bad7  test    r14d, r14d
0x14007bada  js      loc_1401FFA8F
0x14007bae0  test    sil, sil
0x14007bae3  jnz     loc_14007C378
0x14007bae9  nop
0x14007baea  lock or dword ptr [rbx+228h], 4
0x14007baf2  nop
0x14007baf3  mov     eax, r14d
0x14007baf6  mov     rcx, [rsp+218h+var_48]
0x14007bafe  xor     rcx, rsp; StackCookie
0x14007bb01  call    __security_check_cookie
0x14007bb06  add     rsp, 1E0h
0x14007bb0d  pop     r15
0x14007bb0f  pop     r14
0x14007bb11  pop     r13
0x14007bb13  pop     r12
0x14007bb15  pop     rdi
0x14007bb16  pop     rsi
0x14007bb17  pop     rbx
0x14007bb18  retn
0x14007bb1a  xor     r11d, r11d
0x14007bb1d  test    r14d, r14d
0x14007bb20  jns     short loc_14007BAE0
0x14007bb22  test    r12b, r12b
0x14007bb25  jz      loc_140200138
0x14007bb2b  mov     rcx, [rbx+2A0h]; Mdl
0x14007bb32  call    ?MsKmeUnlockPages@@YAXPEAX@Z; MsKmeUnlockPages(void *)
0x14007bb37  xor     r11d, r11d
0x14007bb3a  mov     [rbx+2A0h], r11
0x14007bb41  jmp     loc_140200138
0x14007bb46  nop
0x14007bb47  lock inc cs:dword_140269590
0x14007bb4e  nop
0x14007bb4f  nop
0x14007bb50  lock inc cs:dword_140269504
0x14007bb57  nop
0x14007bb58  movzx   eax, byte ptr [r15+58h]
0x14007bb5d  mov     rdx, [rsp+218h+var_158]
0x14007bb65  cmp     [rdx+2], al
0x14007bb68  jnz     loc_14007C31A
0x14007bb6e  mov     r14, [r15+0DD0h]
0x14007bb75  movzx   r8d, word ptr [r14+8]
0x14007bb7a  lea     r11, [r14+0Ch]
0x14007bb7e  mov     [rsp+218h+var_168], r11
0x14007bb86  test    r8w, r8w
0x14007bb8a  jnz     loc_14007C185
0x14007bb90  xor     r11d, r11d
0x14007bb93  mov     eax, r11d
0x14007bb96  cmp     [rdx+4], eax
0x14007bb99  jnz     loc_14007C328
0x14007bb9f  mov     r10, [rbx+68h]
0x14007bba3  movzx   eax, byte ptr [rdx+3]
0x14007bba7  add     rax, rdx
0x14007bbaa  mov     qword ptr [rsp+218h+var_C8], rax
0x14007bbb2  mov     rax, [r14]
0x14007bbb5  mov     rax, [rax+28h]
0x14007bbb9  mov     [rsp+218h+var_120], rax
0x14007bbc1  mov     edx, [rbx+140h]
0x14007bbc7  test    r8w, r8w
0x14007bbcb  jz      loc_14007C17D
0x14007bbd1  movzx   ecx, word ptr [r14+14h]
0x14007bbd6  mov     rax, [rsp+218h+var_168]
0x14007bbde  sub     ecx, [rax]
0x14007bbe0  mov     eax, edx
0x14007bbe2  shr     rax, cl
0x14007bbe5  mov     rcx, qword ptr [rsp+218h+var_C8]
0x14007bbed  mov     qword ptr [rsp+218h+var_C8], rcx
0x14007bbf5  mov     qword ptr [rsp+218h+var_C8+8], rax
0x14007bbfd  mov     [rsp+218h+var_118], r10
0x14007bc05  mov     [rsp+218h+var_110], rdx
0x14007bc0d  mov     [rsp+218h+var_1F0], r11
0x14007bc12  mov     [rsp+218h+var_1F8], r11
0x14007bc17  xor     r9d, r9d
0x14007bc1a  lea     r8, [rsp+218h+var_C8]
0x14007bc22  lea     rdx, [rsp+218h+var_118]
0x14007bc2a  mov     rcx, r14
0x14007bc2d  mov     rax, [rsp+218h+var_120]
0x14007bc35  call    _guard_dispatch_icall
0x14007bc3a  mov     r14d, eax
0x14007bc3d  test    eax, eax
0x14007bc3f  js      short loc_14007BC5F
0x14007bc41  mov     rdx, rbx; struct SmsPage *
0x14007bc44  mov     rcx, [rbx+60h]; this
0x14007bc48  call    ?CheckPage@CmsBPlusTable@@QEAAJAEAUSmsPage@@_N1@Z; CmsBPlusTable::CheckPage(SmsPage &,bool,bool)
0x14007bc4d  mov     r14d, eax
0x14007bc50  mov     [rsp+218h+var_194], eax
0x14007bc57  test    eax, eax
0x14007bc59  js      loc_14007C333
0x14007bc5f  mov     r10, [rsp+218h+var_188]
0x14007bc67  jmp     loc_14007BAD4
0x14007bc6c  lea     r8, [r9+2A0h]; void **
0x14007bc73  mov     edx, [r9+140h]; unsigned int
0x14007bc7a  mov     rcx, [r9+68h]; void *
0x14007bc7e  call    ?MsKmeLockPages@@YAJPEAXKPEAPEAX@Z; MsKmeLockPages(void *,ulong,void * *)
0x14007bc83  mov     r14d, eax
0x14007bc86  mov     [rsp+218h+var_194], eax
0x14007bc8d  test    eax, eax
0x14007bc8f  js      loc_14007C0F8
0x14007bc95  xor     edx, edx; Val
0x14007bc97  mov     r8d, 0A0h; Size
0x14007bc9d  mov     rcx, [rbx+68h]; void *
0x14007bca1  call    memset
0x14007bca6  mov     rcx, [rbx+68h]
0x14007bcaa  add     rcx, 1000h; void *
0x14007bcb1  xor     edx, edx; Val
0x14007bcb3  mov     r8d, 50h ; 'P'; Size
0x14007bcb9  call    memset
0x14007bcbe  mov     rcx, [rbx+68h]
0x14007bcc2  add     rcx, 2000h; void *
0x14007bcc9  xor     edx, edx; Val
0x14007bccb  mov     r8d, 50h ; 'P'; Size
0x14007bcd1  call    memset
0x14007bcd6  mov     rcx, [rbx+68h]
0x14007bcda  add     rcx, 3000h; void *
0x14007bce1  xor     edx, edx; Val
0x14007bce3  mov     r8d, 50h ; 'P'; Size
0x14007bce9  call    memset
0x14007bcee  mov     rax, r13
0x14007bcf1  mov     rcx, [rax+40h]
0x14007bcf5  cmp     rcx, rax
0x14007bcf8  jz      short loc_14007BCFF
0x14007bcfa  mov     rax, rcx
0x14007bcfd  jmp     short loc_14007BCF1
0x14007bcff  mov     rax, [rax+48h]
0x14007bd03  add     rax, 178h
0x14007bd09  mov     [rsp+218h+var_158], rax
0x14007bd11  mov     rcx, [rbx+68h]; void *
0x14007bd15  mov     [rsp+218h+var_168], rcx
0x14007bd1d  xor     edx, edx; Val
0x14007bd1f  mov     r8d, 50h ; 'P'; Size
0x14007bd25  call    memset
0x14007bd2a  mov     rdx, [rsp+218h+var_168]
0x14007bd32  mov     dword ptr [rdx], 2B42534Dh
0x14007bd38  mov     eax, [r15+0D00h]
0x14007bd3f  mov     [rdx+0Ch], eax
0x14007bd42  mov     rax, [r15+810h]
0x14007bd49  mov     [rdx+10h], rax
0x14007bd4d  mov     rax, [r15+820h]
0x14007bd54  mov     [rdx+18h], rax
0x14007bd58  movups  xmm0, xmmword ptr [rbx]
0x14007bd5b  movups  xmmword ptr [rdx+20h], xmm0
0x14007bd5f  movups  xmm1, xmmword ptr [rbx+10h]
0x14007bd63  movups  xmmword ptr [rdx+30h], xmm1
0x14007bd67  mov     byte ptr [rdx+4], 2
0x14007bd6b  mov     rax, [rsp+218h+var_158]
0x14007bd73  test    rax, rax
0x14007bd76  jz      short loc_14007BD7F
0x14007bd78  movups  xmm0, xmmword ptr [rax]
0x14007bd7b  movups  xmmword ptr [rdx+40h], xmm0
0x14007bd7f  mov     eax, [r15+0D5Ch]
0x14007bd86  mov     ecx, 0FFh
0x14007bd8b  cmp     eax, ecx
0x14007bd8d  cmovb   ecx, eax
0x14007bd90  mov     [rdx+8], cl
0x14007bd93  xor     r11d, r11d
0x14007bd96  cmp     byte ptr [rbx+188h], 0F8h
0x14007bd9d  jnz     loc_14007C100
0x14007bda3  lea     rdx, [rbx+20h]
0x14007bda7  mov     rax, [rbx+60h]
0x14007bdab  test    byte ptr [rax+10h], 4
0x14007bdaf  jnz     loc_14007C136
0x14007bdb5  mov     [rsp+218h+var_1F8], rdx; union _LCN_TUPLE *
0x14007bdba  mov     r9b, 1; bool
0x14007bdbd  mov     r8, rbx; union _LCN_TUPLE *
0x14007bdc0  mov     rdx, [rsp+218h+var_188]; struct CmsTransactionContext *
0x14007bdc8  mov     rcx, [r15+0CC8h]; this
0x14007bdcf  call    ?SetContainerStationaryVolatile@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAT_LCN_TUPLE@@_N1@Z; CmsVolumeContainer::SetContainerStationaryVolatile(CmsTransactionContext *,_LCN_TUPLE *,bool,_LCN_TUPLE *)
0x14007bdd4  mov     r14d, eax
0x14007bdd7  mov     [rsp+218h+var_194], eax
0x14007bdde  test    eax, eax
0x14007bde0  js      loc_14007C114
0x14007bde6  nop
0x14007bde7  lock or dword ptr [rbx+228h], 40h
0x14007bdef  nop
0x14007bdf0  mov     r10, [r15+0CC8h]
0x14007bdf7  mov     [rsp+218h+var_168], r10
0x14007bdff  movups  xmm0, xmmword ptr [rbx]
0x14007be02  movups  xmm1, xmmword ptr [rbx+10h]
0x14007be06  movaps  [rsp+218h+var_E8], xmm0
0x14007be0e  movaps  [rsp+218h+var_D8], xmm1
0x14007be16  xor     r11d, r11d
0x14007be19  mov     r14d, r11d
0x14007be1c  mov     [rsp+218h+var_148], r11d
0x14007be24  mov     [rsp+218h+var_158], r11
0x14007be2c  mov     [rsp+218h+var_150], r11
0x14007be34  mov     [rsp+218h+var_170], r11d
0x14007be3c  mov     ecx, r11d
0x14007be3f  mov     [rsp+218h+var_170], ecx
0x14007be46  cmp     ecx, 4
0x14007be49  jnb     loc_14007BEE1
0x14007be4f  mov     eax, ecx
0x14007be51  mov     rdx, qword ptr [rsp+rax*8+218h+var_E8]
0x14007be59  mov     [rsp+218h+var_158], rdx
0x14007be61  mov     [rsp+218h+var_150], 1
0x14007be6d  test    rdx, rdx
0x14007be70  jz      short loc_14007BEDA
0x14007be72  mov     [rsp+218h+var_138], rdx
0x14007be7a  mov     [rsp+218h+var_130], 1
0x14007be86  mov     byte ptr [rsp+218h+var_1D8], 0
0x14007be8b  mov     qword ptr [rsp+218h+var_1E0], r11
0x14007be90  mov     [rsp+218h+var_1E8], r11
0x14007be95  mov     [rsp+218h+var_1F0], r11
0x14007be9a  mov     [rsp+218h+var_1F8], r11
0x14007be9f  mov     r9b, 1
0x14007bea2  lea     r8, [rsp+218h+var_138]
0x14007beaa  mov     rdx, [rsp+218h+var_188]
0x14007beb2  mov     rcx, r10
0x14007beb5  call    ?PinContainerRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@EPEAU3@PEAU_SmsContainerOverflowPinList@@PEAE4E@Z; CmsVolumeContainer::PinContainerRange(CmsTransactionContext *,_RANGE,uchar,_RANGE *,_SmsContainerOverflowPinList *,uchar *,uchar *,uchar)
0x14007beba  mov     r14d, eax
0x14007bebd  mov     [rsp+218h+var_148], eax
0x14007bec4  xor     r11d, r11d
0x14007bec7  test    eax, eax
0x14007bec9  js      short loc_14007BEE1
0x14007becb  mov     ecx, [rsp+218h+var_170]
0x14007bed2  mov     r10, [rsp+218h+var_168]
0x14007beda  inc     ecx
0x14007bedc  jmp     loc_14007BE3F
0x14007bee1  mov     [rsp+218h+var_194], r14d
0x14007bee9  test    r14d, r14d
0x14007beec  js      loc_14007BB1D
0x14007bef2  mov     rdx, [r15+0CC8h]
0x14007bef9  mov     [rsp+218h+var_178], rdx
0x14007bf01  movups  xmm0, xmmword ptr [rbx]
0x14007bf04  movaps  [rsp+218h+var_108], xmm0
0x14007bf0c  movups  xmm1, xmmword ptr [rbx+10h]
0x14007bf10  movaps  [rsp+218h+var_F8], xmm1
0x14007bf18  mov     [rsp+218h+var_168], r11
0x14007bf20  mov     [rsp+218h+var_160], r11
0x14007bf28  mov     ecx, r11d
0x14007bf2b  mov     r9d, 4
0x14007bf31  mov     [rsp+218h+var_17C], ecx
0x14007bf38  cmp     ecx, 4
0x14007bf3b  jnb     loc_14007C081
0x14007bf41  mov     eax, ecx
0x14007bf43  mov     r8, qword ptr [rsp+rax*8+218h+var_108]
0x14007bf4b  test    r8, r8
0x14007bf4e  jz      loc_14007C07A
0x14007bf54  mov     [rsp+218h+var_168], r8
0x14007bf5c  mov     [rsp+218h+var_160], 1
0x14007bf68  mov     rax, [rdx+8]
0x14007bf6c  mov     ecx, [rax+50h]
0x14007bf6f  inc     ecx
0x14007bf71  shr     r8, cl
0x14007bf74  mov     rdx, r11
  ... truncated ...
```
