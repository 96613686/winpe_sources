# NtfsCommonCreate

- ea: `0x1401a2d00`
- end: `0x1401a5d5d`
- name: `NtfsCommonCreate`
- size: `12381`
- prototype: `__int64 __fastcall(int, PIRP Irp)`
- caller_count: `4`
- callee_count: `65`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140015d10`
- `0x1401a0500`
- `0x1401a0d10`
- `0x1401a1e10`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x140009c10`
- `0x140009c80`
- `0x14000c290`
- `0x14000eaa0`
- `0x140012e70`
- `0x14001c2e0`
- `0x14001e810`
- `0x140020de0`
- `0x140021e60`
- `0x14002b350`
- `0x14003e734`
- `0x14003ee84`
- `0x14003f220`
- `0x140044568`
- `0x1400592c0`
- `0x140059440`
- `0x140059740`
- `0x140059c60`
- `0x1400cafac`
- `0x1400f5a44`
- `0x14011e59c`
- `0x1401215e0`
- `0x140128da0`
- `0x14012be50`
- `0x14012f980`
- `0x14013af60`
- `0x1401403d0`
- `0x140148f80`
- `0x140153960`
- `0x140153b00`
- `0x140163420`
- `0x140164c20`
- `0x140182310`
- `0x140182c80`
- `0x140184220`
- `0x140185c50`
- `0x14019a768`
- `0x14019f270`
- `0x14019f350`
- `0x1401a0ba0`
- `0x1401a2d00`
- `0x1401a5f50`
- `0x1401aab70`
- `0x1401d2c84`
- `0x1401e7934`
- `0x1401ecbc0`
- `0x1401efbe8`
- `0x1401f1d80`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401a2f08`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x1401a2f08`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a2f40`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a2f76`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a37ee`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a382f`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a2f40`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a2f76`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a37ee`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x1401a382f`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1401a2f8e`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1401a3806`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1401a2f8e`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x1401a3806`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401a42ae`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401a4c5c`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401a42ae`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1401a4c5c`
- `ntoskrnl!TmIsTransactionActive` at `0x1401a5af0`
- `ntoskrnl!TmIsTransactionActive` at `0x1401a5af0`
- `ntoskrnl!IoGetCurrentProcess` at `0x1401a56f3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1402ad28f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1401a56f3`
- `ntoskrnl!IoGetCurrentProcess` at `0x1402ad28f`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401a5702`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402ad29e`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1401a5702`
- `ntoskrnl!PsGetProcessImageFileName` at `0x1402ad29e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401a4e55`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401a53c9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402acf01`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401a4e55`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1401a53c9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402acf01`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401a47ea`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1401a47ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a3988`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401a3988`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a53e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a5507`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a5a7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402acf1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad090`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad6aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a53e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a5507`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401a5a7c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402acf1c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad090`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402ad6aa`
- `ntoskrnl!CcUnpinData` at `0x1401a4a65`
- `ntoskrnl!CcUnpinData` at `0x1401a5080`
- `ntoskrnl!CcUnpinData` at `0x1401a5391`
- `ntoskrnl!CcUnpinData` at `0x1402acec1`
- `ntoskrnl!CcUnpinData` at `0x1401a4a65`
- `ntoskrnl!CcUnpinData` at `0x1401a5080`
- `ntoskrnl!CcUnpinData` at `0x1401a5391`
- `ntoskrnl!CcUnpinData` at `0x1402acec1`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401a5977`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402ad58a`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1401a5977`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402ad58a`

## pseudocode

```c
__int64 __fastcall NtfsCommonCreate(__int64 a1, PIRP Irp, __int64 a3)
{
  __int64 v3; // rdi
  PIRP v4; // r13
  __int64 v5; // rsi
  __int64 v6; // r15
  __int64 v7; // r9
  __int64 v8; // r10
  int v9; // ebx
  int v10; // r11d
  __int64 v11; // r8
  __int64 v12; // r9
  struct _ECP_LIST *v13; // rcx
  unsigned __int16 **v14; // r14
  __int64 v15; // r9
  unsigned __int16 *v16; // rdx
  unsigned __int16 v17; // cx
  unsigned __int16 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 *v21; // rax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rax
  unsigned int InformationForQueryOpen; // ebx
  PIRP v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rax
  PIRP v29; // rdx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  __int64 v33; // rax
  PIRP v34; // rdx
  __int64 v35; // rax
  PIRP v36; // rdx
  __int64 v37; // rax
  PIRP v38; // rdx
  __int64 v39; // rax
  PIRP v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rbx
  unsigned __int8 v43; // al
  __int64 v44; // r9
  __int64 v45; // rax
  PIRP v46; // rdx
  unsigned __int16 *v48; // rcx
  int v49; // eax
  __int64 v50; // rax
  PIRP v51; // rdx
  void *v52; // rcx
  __int64 v53; // rcx
  __int64 QuadPart; // rax
  __int64 v55; // rbx
  __int64 v56; // rax
  PIRP v57; // rdx
  int v58; // eax
  __int64 v59; // rax
  PIRP v60; // rdx
  __int128 v61; // xmm0
  __int64 v62; // rcx
  __int64 v63; // r9
  __int64 v64; // r8
  __int64 v65; // r8
  int v66; // r9d
  __int64 v67; // r8
  int v68; // r14d
  __int64 v69; // rdx
  unsigned int v70; // eax
  unsigned __int16 v71; // cx
  __int64 v72; // rdx
  unsigned __int8 v73; // r10
  int v74; // r8d
  unsigned __int8 v75; // r9
  __int64 v76; // rcx
  int v77; // edx
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rax
  __int16 v81; // cx
  __int64 *v82; // rax
  __int64 v83; // rax
  __int64 *v84; // rax
  unsigned int v85; // eax
  __int64 v86; // r8
  int v87; // r8d
  unsigned __int16 v88; // ax
  _WORD *v89; // rcx
  unsigned __int64 v90; // r9
  _WORD **v91; // r8
  __int64 v92; // rax
  unsigned __int64 v93; // rcx
  int v94; // edx
  unsigned int v95; // edx
  int StartingNode; // eax
  unsigned int v97; // ecx
  __int128 v98; // xmm6
  char v99; // bl
  unsigned int v100; // ecx
  unsigned int v101; // eax
  __int64 v102; // rdx
  bool v103; // zf
  unsigned int v104; // ecx
  __int64 v105; // r8
  __int16 v106; // dx
  __int16 v107; // ax
  __int16 v108; // cx
  int ReparsePointValue; // eax
  __int64 Scb; // r15
  __int64 v111; // rcx
  __int64 v112; // rdx
  int v113; // ecx
  int v114; // r9d
  __int64 v115; // rdx
  PVOID v116; // rdx
  _OWORD *v117; // rbx
  __int64 v118; // rax
  char v119; // al
  int v120; // ecx
  unsigned int v121; // ecx
  int v122; // r10d
  __int64 v123; // rax
  BOOL v124; // r9d
  __int64 v125; // r14
  unsigned int v126; // eax
  int v127; // eax
  __int16 v128; // dx
  unsigned int v129; // eax
  __int64 v130; // rcx
  __int64 v131; // rax
  unsigned int CurrentFileInfo; // eax
  unsigned int v133; // eax
  unsigned int v134; // eax
  int v135; // ecx
  __int64 v136; // r14
  __int64 v137; // rax
  __int64 v138; // rdx
  __int64 v139; // rax
  __int64 v140; // rdx
  __int64 v141; // rax
  __int64 v142; // rdx
  __int64 v143; // rdx
  __int64 v144; // rax
  _DWORD *v145; // rcx
  __int64 v146; // rdx
  __int64 v147; // rax
  _BYTE *v148; // rcx
  int v149; // r11d
  __int64 v150; // r8
  __int64 v151; // rax
  unsigned __int8 v152; // r15
  PEPROCESS CurrentProcess; // rax
  __int64 ProcessImageFileName; // rax
  __int64 v155; // rdx
  __int64 v156; // rax
  __int64 v157; // rcx
  __int64 v158; // r8
  unsigned int v159; // ecx
  int v160; // r10d
  int v161; // r9d
  __int64 v162; // rdx
  __int64 v163; // rdx
  int v164; // eax
  __int64 v165; // r9
  __int64 v166; // rdx
  int v167; // eax
  __int64 v168; // r14
  void *v169; // rcx
  _OWORD *v170; // r15
  struct _KTRANSACTION *v171; // rcx
  struct _FILE_OBJECT *v172; // rcx
  __int64 v173; // rax
  PIRP v174; // rdx
  unsigned __int8 v175; // [rsp+FCh] [rbp-164h]
  char v176; // [rsp+FDh] [rbp-163h] BYREF
  char v177; // [rsp+FEh] [rbp-162h]
  __int16 v178; // [rsp+FFh] [rbp-161h] BYREF
  char v179; // [rsp+101h] [rbp-15Fh]
  __int64 v180; // [rsp+108h] [rbp-158h] BYREF
  char v181; // [rsp+110h] [rbp-150h]
  __int64 v182; // [rsp+118h] [rbp-148h]
  PVOID Entry; // [rsp+120h] [rbp-140h] BYREF
  PVOID Bcb; // [rsp+128h] [rbp-138h] BYREF
  __int64 v185; // [rsp+130h] [rbp-130h] BYREF
  int v186; // [rsp+138h] [rbp-128h] BYREF
  __int64 v187; // [rsp+140h] [rbp-120h] BYREF
  char v188; // [rsp+148h] [rbp-118h]
  int v189; // [rsp+14Ch] [rbp-114h] BYREF
  int v190; // [rsp+150h] [rbp-110h]
  __int128 v191; // [rsp+158h] [rbp-108h] BYREF
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+168h] [rbp-F8h] BYREF
  __int64 v193; // [rsp+170h] [rbp-F0h]
  void *v194[2]; // [rsp+178h] [rbp-E8h] BYREF
  __int64 v195; // [rsp+188h] [rbp-D8h]
  __int64 v196; // [rsp+190h] [rbp-D0h]
  __int64 v197; // [rsp+198h] [rbp-C8h]
  __int64 v198; // [rsp+1A0h] [rbp-C0h] BYREF
  PVOID P; // [rsp+1A8h] [rbp-B8h] BYREF
  __int64 v200; // [rsp+1B0h] [rbp-B0h]
  PIRP v201; // [rsp+1B8h] [rbp-A8h]
  __int64 v202[2]; // [rsp+1C0h] [rbp-A0h] BYREF
  __int64 v203; // [rsp+1D0h] [rbp-90h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+1D8h] [rbp-88h]
  POPLOCK_FS_PREPOST_IRP v205; // [rsp+1E0h] [rbp-80h]
  __int128 v206; // [rsp+1E8h] [rbp-78h]
  __int64 v207[2]; // [rsp+1F8h] [rbp-68h] BYREF
  __int64 v208; // [rsp+208h] [rbp-58h]

  v3 = a3;
  v4 = Irp;
  v5 = a1;
  v195 = a1;
  v201 = Irp;
  v200 = a3;
  *(_OWORD *)v202 = 0;
  v186 = 0;
  v187 = 0;
  v180 = 0;
  LOWORD(v189) = 0;
  P = 0;
  v198 = 0;
  Bcb = 0;
  *(_OWORD *)v207 = 0;
  v208 = 0;
  v185 = 0;
  Entry = 0;
  v176 = 1;
  v191 = 0;
  *(_OWORD *)v194 = 0;
  v178 = 0;
  ExtraCreateParameter = 0;
  v6 = *(_QWORD *)(a1 + 104);
  v182 = v6;
  v197 = v6;
  v7 = *(_QWORD *)(a3 + 176);
  v8 = *(_QWORD *)(v7 + 48);
  *(_QWORD *)(a3 + 32) = v8;
  *(_DWORD *)(a3 + 40) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL) + 16LL);
  *(_DWORD *)(a3 + 44) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 8) + 8LL) + 20LL);
  v9 = *(_DWORD *)(*(_QWORD *)(v7 + 8) + 16LL);
  *(_DWORD *)(a3 + 48) = v9;
  *(_DWORD *)(a3 + 64) = 0;
  *(_QWORD *)(a3 + 128) = 0;
  if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0 )
  {
    v10 = *(_DWORD *)(v7 + 16);
    if ( (v10 & 0x2000) != 0 )
    {
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000) != 0 )
        McTemplateU0pppppeddddd_EtwWriteTransfer(
          *(unsigned __int16 *)(v7 + 26),
          *(unsigned __int16 *)(v7 + 24),
          (_DWORD)Irp,
          a1,
          v6,
          v8,
          *(_QWORD *)(v8 + 64),
          *(_WORD *)(v8 + 88),
          *(_QWORD *)(v8 + 96),
          v10,
          *(_WORD *)(v7 + 24),
          v9,
          *(_WORD *)(v7 + 26),
          *(_DWORD *)(v7 + 32));
    }
    else if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x4000) != 0 )
    {
      McTemplateU0pppppwddddd_EtwWriteTransfer(
        *(unsigned __int16 *)(v7 + 26),
        *(unsigned __int16 *)(v7 + 24),
        (_DWORD)Irp,
        a1,
        v6,
        v8,
        *(_QWORD *)(v8 + 64),
        *(_WORD *)(v8 + 88) >> 1,
        *(_QWORD *)(v8 + 96),
        v10,
        *(_WORD *)(v7 + 24),
        v9,
        *(_WORD *)(v7 + 26),
        *(_DWORD *)(v7 + 32));
    }
  }
  if ( IoGetIrpExtraCreateParameter(v4, &ExtraCreateParameter) >= 0 )
  {
    v13 = ExtraCreateParameter;
    if ( ExtraCreateParameter )
    {
      if ( !v4->RequestorMode )
      {
        if ( FsRtlFindExtraCreateParameter(ExtraCreateParameter, &ECP_TYPE_CLFS_CREATE_CONTAINER, 0, 0) >= 0 )
          *(_DWORD *)(v5 + 436) |= 0x100000u;
        v13 = ExtraCreateParameter;
      }
      v14 = (unsigned __int16 **)(v3 + 224);
      FsRtlFindExtraCreateParameter(v13, &GUID_ECP_ATOMIC_CREATE, (PVOID *)(v3 + 224), 0);
      if ( !*(_QWORD *)(v3 + 224) )
      {
LABEL_192:
        FsRtlFindExtraCreateParameter(ExtraCreateParameter, &GUID_ECP_OPEN_PARAMETERS, (PVOID *)(v3 + 232), 0);
        v52 = *(void **)(v3 + 232);
        if ( v52 )
          FsRtlAcknowledgeEcp(v52);
        FsRtlFindExtraCreateParameter(
          ExtraCreateParameter,
          &GUID_ECP_QUERY_ON_CREATE,
          (PVOID *)(v3 + 208),
          (ULONG *)(v3 + 204));
        goto LABEL_195;
      }
      FsRtlAcknowledgeEcp(*(PVOID *)(v3 + 224));
      v16 = *v14;
      v17 = **v14;
      if ( v17 >= 6u )
      {
        v18 = v16[1];
        if ( (v18 & 2) == 0 || v17 >= 0x10u )
        {
          v15 = v18;
          LOWORD(v15) = v16[1] & 4;
          if ( (v18 & 4) == 0 || v17 >= 0x18u && (v19 = *((_QWORD *)v16 + 2), v19 >= 0) && v19 <= *(_QWORD *)(v6 + 7776) )
          {
            if ( (v18 & 8) == 0
              || v17 >= 0x20u && (v20 = *((_QWORD *)v16 + 3), v20 >= 0) && (v18 & 4) != 0 && v20 <= *((_QWORD *)v16 + 2) )
            {
              if ( (v18 & 0x10) == 0
                || v17 >= 0x28u
                && (v21 = (__int64 *)*((_QWORD *)v16 + 4), *v21 >= -1)
                && v21[1] >= -1
                && v21[2] >= -1
                && v21[3] >= -1 )
              {
                if ( ((v18 & 0x20) == 0 || v17 >= 0x2Cu)
                  && ((v18 & 0x800) == 0 || v17 >= 0x30u && (*((_DWORD *)v16 + 11) & 0xFFFFFFF0) == 0) )
                {
                  v15 = v18;
                  LOWORD(v15) = v16[1] & 0x40;
                  if ( (v18 & 0x40) == 0
                    || v17 >= 0x3Cu
                    && (v22 = *((_DWORD *)v16 + 14), (v22 & 0xFF250048) == 0)
                    && ((v23 = v22 & 0x180000) == 0 || v23 == 1572864) )
                  {
                    if ( (v18 & 0x80) != 0 && (v17 < 0x44u || (*((_DWORD *)v16 + 15) & 1) != 0 && v17 < 0x58u) )
                    {
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        InformationForQueryOpen = -1073741811;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 679952);
                        LOBYTE(v15) = 1;
                        v26 = 0;
                      }
                      else
                      {
                        v24 = *(_QWORD *)(v5 + 16);
                        InformationForQueryOpen = -1073741811;
                        if ( (v24 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v24 | 2;
                          goto LABEL_57;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 679975);
                        LOBYTE(v15) = v4 != 0;
                        v26 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v26, 3221225485LL, v15, 0);
LABEL_57:
                      if ( NtfsStatusDebugFlags )
                      {
                        v27 = 658102;
LABEL_742:
                        NtfsStatusTraceAndDebugInternal(0, InformationForQueryOpen, v27);
                        return InformationForQueryOpen;
                      }
                      return InformationForQueryOpen;
                    }
                    if ( (v18 & 0x8000u) != 0 && v17 < 0x4Cu )
                    {
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        InformationForQueryOpen = -1073741811;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 679952);
                        LOBYTE(v15) = 1;
                        v29 = 0;
                      }
                      else
                      {
                        v28 = *(_QWORD *)(v5 + 16);
                        InformationForQueryOpen = -1073741811;
                        if ( (v28 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v28 | 2;
                          goto LABEL_72;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 679975);
                        LOBYTE(v15) = v4 != 0;
                        v29 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v29, 3221225485LL, v15, 0);
LABEL_72:
                      if ( NtfsStatusDebugFlags )
                      {
                        v27 = 658117;
                        goto LABEL_742;
                      }
                      return InformationForQueryOpen;
                    }
                    if ( (v18 & 0x100) == 0 )
                    {
                      v30 = (v18 & 0x80) != 0 ? *((_DWORD *)v16 + 15) : 0;
                      if ( (v30 & 0xFFFFFFFE) != 0
                        || ((v18 & 0x80) == 0 ? (LOBYTE(v31) = 0) : (v31 = *((_DWORD *)v16 + 15)),
                            (v31 & 1) == 0 ? (LOBYTE(v32) = 0) : (v32 = *((_DWORD *)v16 + 19)),
                            (v32 & 1) != 0 && (*((_DWORD *)v16 + 20) & 1) != 0 && (dword_140095AD4 & 1) == 0) )
                      {
                        if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                        {
                          InformationForQueryOpen = -1073741637;
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 679952);
                          LOBYTE(v15) = 1;
                          v34 = 0;
                        }
                        else
                        {
                          v33 = *(_QWORD *)(v5 + 16);
                          InformationForQueryOpen = -1073741637;
                          if ( (v33 & 1) != 0 )
                          {
                            *(_QWORD *)(v5 + 16) = v33 | 2;
                            goto LABEL_99;
                          }
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 679975);
                          LOBYTE(v15) = v4 != 0;
                          v34 = v4;
                        }
                        NtfsExtendedCompleteRequestInternal(v5, v34, 3221225659LL, v15, 0);
LABEL_99:
                        if ( NtfsStatusDebugFlags )
                        {
                          v27 = 658146;
                          goto LABEL_742;
                        }
                        return InformationForQueryOpen;
                      }
                    }
                    if ( (v18 & 0x100) == 0 && (v18 & 0x40) != 0 && (*((_DWORD *)v16 + 14) & 0xFF254048) != 0 )
                    {
                      *((_DWORD *)v16 + 14) &= 0xFF254048;
                      (*v14)[2] |= 0x40u;
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        InformationForQueryOpen = -1073741637;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 679952);
                        LOBYTE(v15) = 1;
                        v36 = 0;
                      }
                      else
                      {
                        v35 = *(_QWORD *)(v5 + 16);
                        InformationForQueryOpen = -1073741637;
                        if ( (v35 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v35 | 2;
                          goto LABEL_115;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 679975);
                        LOBYTE(v15) = v4 != 0;
                        v36 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v36, 3221225659LL, v15, 0);
LABEL_115:
                      if ( NtfsStatusDebugFlags )
                      {
                        v27 = 658164;
                        goto LABEL_742;
                      }
                      return InformationForQueryOpen;
                    }
                    if ( (v18 & 0x40) != 0
                      && (*((_DWORD *)v16 + 14) & 0x800) != 0
                      && _bittest16((const signed __int16 *)(*(_QWORD *)(v3 + 176) + 24LL), 0xEu) )
                    {
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        InformationForQueryOpen = -1073741637;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 679952);
                        LOBYTE(v15) = 1;
                        v38 = 0;
                      }
                      else
                      {
                        v37 = *(_QWORD *)(v5 + 16);
                        InformationForQueryOpen = -1073741637;
                        if ( (v37 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v37 | 2;
                          goto LABEL_131;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221225659LL, 679975);
                        LOBYTE(v15) = v4 != 0;
                        v38 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v38, 3221225659LL, v15, 0);
LABEL_131:
                      if ( NtfsStatusDebugFlags )
                      {
                        v27 = 658176;
                        goto LABEL_742;
                      }
                      return InformationForQueryOpen;
                    }
                    if ( (*(_DWORD *)(v182 + 24) & 0x40000) != 0
                      && ((v18 & 1) != 0
                       || (v18 & 0x40) != 0 && (v16[28] & *(_WORD *)(*(_QWORD *)(v3 + 176) + 24LL) & 0xA00) != 0) )
                    {
                      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                      {
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221226650LL, 679952);
                        LOBYTE(v15) = 1;
                        v40 = 0;
                      }
                      else
                      {
                        v39 = *(_QWORD *)(v5 + 16);
                        if ( (v39 & 1) != 0 )
                        {
                          *(_QWORD *)(v5 + 16) = v39 | 2;
                          goto LABEL_148;
                        }
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(v5, 3221226650LL, 679975);
                        LOBYTE(v15) = v4 != 0;
                        v40 = v4;
                      }
                      NtfsExtendedCompleteRequestInternal(v5, v40, 3221226650LL, v15, 0);
LABEL_148:
                      if ( NtfsStatusDebugFlags )
                      {
                        v41 = 658190;
LABEL_213:
                        NtfsStatusTraceAndDebugInternal(0, 3221226650LL, v41);
                        return 3221226650LL;
                      }
                      return 3221226650LL;
                    }
                    if ( (v18 & 8) != 0
                      && *((__int64 *)v16 + 3) > 0
                      && (v18 & 1) == 0
                      && ((v18 & 0x40) == 0 || (v16[28] & *(_WORD *)(*(_QWORD *)(v3 + 176) + 24LL) & 0xA00) == 0) )
                    {
                      v42 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL);
                      v43 = NtfsEffectiveMode(v4);
                      if ( !(unsigned __int8)NtfsPrivilegeCheck(28, v42 + 32, v43) )
                      {
                        if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
                        {
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal(v5, 3221225569LL, 679952);
                          LOBYTE(v44) = 1;
                          v46 = 0;
                        }
                        else
                        {
                          v45 = *(_QWORD *)(v5 + 16);
                          if ( (v45 & 1) != 0 )
                          {
                            *(_QWORD *)(v5 + 16) = v45 | 2;
LABEL_167:
                            if ( NtfsStatusDebugFlags )
                              NtfsStatusTraceAndDebugInternal(0, 3221225569LL, 658209);
                            return 3221225569LL;
                          }
                          if ( NtfsStatusDebugFlags )
                            NtfsStatusTraceAndDebugInternal(v5, 3221225569LL, 679975);
                          LOBYTE(v44) = v4 != 0;
                          v46 = v4;
                        }
                        NtfsExtendedCompleteRequestInternal(v5, v46, 3221225569LL, v44, 0);
                        goto LABEL_167;
                      }
                    }
                    if ( _bittest16((const signed __int16 *)*v14 + 1, 0xBu) )
                    {
                      *(_DWORD *)(v5 + 272) = *((_DWORD *)*v14 + 11);
                      (*v14)[2] |= 0x400u;
                    }
                    if ( *((char *)*v14 + 2) < 0 )
                      (*v14)[2] |= 0x80u;
                    v48 = *v14;
                    if ( *((char *)*v14 + 2) >= 0 )
                      LOBYTE(v49) = 0;
                    else
                      v49 = *((_DWORD *)v48 + 15);
                    if ( (v49 & 1) != 0 )
                    {
                      *((_DWORD *)v48 + 16) |= 1u;
                      *((_DWORD *)*v14 + 21) = 0;
                    }
                    goto LABEL_192;
                  }
                }
              }
            }
          }
        }
      }
      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
      {
        InformationForQueryOpen = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 679952);
        LOBYTE(v15) = 1;
        v51 = 0;
      }
      else
      {
        v50 = *(_QWORD *)(v5 + 16);
        InformationForQueryOpen = -1073741811;
        if ( (v50 & 1) != 0 )
        {
          *(_QWORD *)(v5 + 16) = v50 | 2;
          goto LABEL_190;
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 679975);
        LOBYTE(v15) = v4 != 0;
        v51 = v4;
      }
      NtfsExtendedCompleteRequestInternal(v5, v51, 3221225485LL, v15, 0);
LABEL_190:
      if ( NtfsStatusDebugFlags )
      {
        v27 = 658084;
        goto LABEL_742;
      }
      return InformationForQueryOpen;
    }
  }
LABEL_195:
  v53 = *(_QWORD *)(v3 + 176);
  if ( (*(_BYTE *)(v53 + 16) & 0x41) == 0x41
    || (QuadPart = v4->Overlay.AllocationSize.QuadPart, v55 = v182, QuadPart > *(_QWORD *)(v182 + 7776))
    || QuadPart < 0 )
  {
    if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
    {
      InformationForQueryOpen = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 679952);
      LOBYTE(v12) = 1;
      v174 = 0;
    }
    else
    {
      v173 = *(_QWORD *)(v5 + 16);
      InformationForQueryOpen = -1073741811;
      if ( (v173 & 1) != 0 )
      {
        *(_QWORD *)(v5 + 16) = v173 | 2;
        goto LABEL_740;
      }
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v5, 3221225485LL, 679975);
      LOBYTE(v12) = v4 != 0;
      v174 = v4;
    }
    NtfsExtendedCompleteRequestInternal(v5, v174, 3221225485LL, v12, 0);
LABEL_740:
    if ( NtfsStatusDebugFlags )
    {
      v27 = 658274;
      goto LABEL_742;
    }
    return InformationForQueryOpen;
  }
  if ( (*(_DWORD *)(v182 + 24) & 0x40000) != 0 )
  {
    if ( (*(_WORD *)(v53 + 24) & 0x4000) != 0 )
    {
      if ( (*(_DWORD *)(v5 + 12) & 2) != 0 || *(_QWORD *)(v3 + 136) )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 3221226650LL, 679952);
        LOBYTE(v12) = 1;
        v57 = 0;
      }
      else
      {
        v56 = *(_QWORD *)(v5 + 16);
        if ( (v56 & 1) != 0 )
        {
          *(_QWORD *)(v5 + 16) = v56 | 2;
          goto LABEL_211;
        }
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(v5, 3221226650LL, 679975);
        LOBYTE(v12) = v4 != 0;
        v57 = v4;
      }
      NtfsExtendedCompleteRequestInternal(v5, v57, 3221226650LL, v12, 0);
LABEL_211:
      if ( NtfsStatusDebugFlags )
      {
        v41 = 658288;
        goto LABEL_213;
      }
      return 3221226650LL;
    }
  }
  else if ( (*(_WORD *)(v53 + 24) & 0x4000) != 0 )
  {
    *(_DWORD *)(v53 + 16) |= 0x8000u;
  }
  v58 = *(_DWORD *)(v5 + 12);
  if ( (v58 & 1) == 0 )
    return NtfsPostRequest((PVOID)v5);
  if ( (v58 & 0x200000) != 0 )
  {
    KeWaitForSingleObject(&NtfsEncryptionPendingEvent, Executive, 0, 0, 0);
    *(_DWORD *)(v5 + 12) &= ~0x200000u;
    v58 = *(_DWORD *)(v5 + 12);
  }
  if ( !v4->Cancel )
  {
    v190 = 0;
    v175 = 0;
    v179 = 0;
    v177 = 0;
    v193 = v3;
    v196 = v3 + 16;
    LOWORD(v202[0]) = 0;
    *(_QWORD *)(v5 + 208) = v3;
    v61 = *(_OWORD *)(*(_QWORD *)(v3 + 32) + 88LL);
    *(_OWORD *)v3 = v61;
    *(_OWORD *)(v3 + 16) = v61;
    if ( (*(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 2) != 0 )
    {
      *(_DWORD *)(v5 + 12) |= 0x100u;
      LOBYTE(v11) = 1;
    }
    else
    {
      if ( !*(_BYTE *)(v55 + 8417)
        && *(_DWORD *)(v55 + 8428) + *(_DWORD *)(v55 + 8420) <= (unsigned int)NtfsThrottleCreates )
      {
LABEL_242:
        LOBYTE(v11) = 1;
        if ( (*(_DWORD *)(v5 + 12) & 0x100) != 0 )
          NtfsAcquireExclusiveVcb(v5, v55, v11);
        else
          NtfsAcquireSharedVcb(v5, v55, v11);
        *(_DWORD *)(v3 + 156) |= 0x800u;
        v63 = *(unsigned int *)(v3 + 156);
        v64 = *(unsigned int *)(v55 + 4);
        if ( (v64 & 0x802) != 0 )
        {
          if ( (v64 & 0x800) != 0 && (*(_DWORD *)(v5 + 12) & 0x100) == 0 )
          {
            NtfsReleaseVcb(v5, v55);
            *(_DWORD *)(v3 + 156) &= ~0x800u;
            *(_DWORD *)(v5 + 12) |= 0x100u;
            LOBYTE(v65) = 1;
            NtfsAcquireExclusiveVcb(v5, v55, v65);
            *(_DWORD *)(v3 + 156) |= 0x800u;
          }
          v66 = *(_DWORD *)(v55 + 4);
          if ( (v66 & 1) != 0 )
          {
            if ( (*(_DWORD *)(v5 + 16) & 0x100000) == 0
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
            {
              v69 = *(_QWORD *)(v55 + 248);
              v70 = *(unsigned __int16 *)(v69 + 6);
              if ( v70 > 0x40 || (v70 & 1) != 0 )
              {
                v71 = 0;
                v189 = 0;
                LOWORD(v70) = 0;
              }
              else
              {
                v71 = *(_WORD *)(v69 + 6);
                v189 = v71;
              }
              LOWORD(CompletionRoutine) = v71;
              v205 = (POPLOCK_FS_PREPOST_IRP)(v69 + 32);
              McTemplateU0ppwwd_EtwWriteTransfer(
                *(unsigned __int16 *)(v55 + 7872) >> 1,
                (unsigned int)create_c3106,
                (unsigned int)KeGetCurrentThread(),
                v55,
                *(_WORD *)(v55 + 7872) >> 1,
                *(_QWORD *)(v55 + 7880),
                (unsigned __int16)v70 >> 1,
                v69 + 32,
                v66);
            }
            InformationForQueryOpen = -1073741790;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_253;
            v67 = 658477;
          }
          else
          {
            InformationForQueryOpen = -1073741202;
            if ( !NtfsStatusDebugFlags )
            {
LABEL_253:
              v68 = 8;
LABEL_587:
              *(_DWORD *)(v3 + 156) |= 0x100u;
              v139 = *(_QWORD *)(v5 + 144);
              v140 = *(unsigned int *)(v139 + 24);
              if ( (int)v140 < 0 )
              {
                if ( NtfsStatusDebugFlags
                  && (unsigned int)v140 < 0xFFFFFFED
                  && (_DWORD)v140 != -1073741802
                  && (unsigned int)(v140 + 2147483643) > 1
                  && (_DWORD)v140 != -1073741807
                  && (_DWORD)v140 != -1073741608 )
                {
                  NtfsStatusTraceAndDebugInternal(v5, v140, 660209);
                }
                NtfsRaiseStatusInternal(v5, *(_DWORD *)(*(_QWORD *)(v5 + 144) + 24LL), 0, 0, 660209);
              }
              else if ( (InformationForQueryOpen & 0x80000000) == 0 || !*(_DWORD *)(v139 + 28) )
              {
                NtfsCheckpointCurrentTransaction(v5);
                goto LABEL_592;
              }
              if ( NtfsStatusDebugFlags
                && InformationForQueryOpen < 0xFFFFFFED
                && InformationForQueryOpen != -1073741802
                && InformationForQueryOpen + 2147483643 > 1
                && InformationForQueryOpen != -1073741807
                && InformationForQueryOpen != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(v5, InformationForQueryOpen, 660209);
              }
              NtfsRaiseStatusInternal(v5, InformationForQueryOpen, 0, 0, 660209);
LABEL_760:
              *(_DWORD *)(v5 + 4) |= 0x200000u;
              NtfsRaiseStatusInternal(v5, -1073741608, 0, 0, 658585);
              __debugbreak();
              JUMPOUT(0x1401A5D5DLL);
            }
            v67 = 658462;
          }
LABEL_252:
          NtfsStatusTraceAndDebugInternal(0, InformationForQueryOpen, v67);
          goto LABEL_253;
        }
        v72 = *(_QWORD *)(v3 + 176);
        v73 = *(_BYTE *)(v72 + 19);
        v175 = v73;
        if ( *(_DWORD *)(v55 + 272)
          && ((*(_DWORD *)(*(_QWORD *)(v72 + 8) + 16LL) & 0x116) != 0
           || v73 != 1 && v73 < 6u
           || (*(_DWORD *)(v72 + 16) & 0x1000) != 0) )
        {
          InformationForQueryOpen = -1073740589;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_253;
          v67 = 658506;
          goto LABEL_252;
        }
        if ( (v64 & 0x20) != 0 )
        {
          InformationForQueryOpen = -1073741431;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_253;
          v67 = 658516;
          goto LABEL_252;
        }
        if ( *(char *)(v72 + 2) >= 0 )
        {
          v63 = (unsigned int)v63 | 0x20;
          *(_DWORD *)(v3 + 156) = v63;
        }
        if ( (*(_DWORD *)(v72 + 16) & 0x2000) != 0 )
          *(_DWORD *)(v3 + 156) |= 0x40u;
        if ( *(_QWORD *)(v3 + 224) )
        {
          if ( v73 == 1 )
          {
            if ( !(unsigned int)Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline(v62, v72, v64, v63)
              || *(_WORD *)(*(_QWORD *)(v3 + 224) + 2LL) != 0x2000 )
            {
              InformationForQueryOpen = -1073741811;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_253;
              v67 = 658559;
              goto LABEL_252;
            }
          }
          else if ( v73 != 2 )
          {
            InformationForQueryOpen = -1073741637;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_253;
            v67 = 658565;
            goto LABEL_252;
          }
        }
        if ( (*(_DWORD *)(v55 + 4) & 1) == 0 || !(unsigned __int8)NtfsPingVolume(v5, v55, 0, v63) )
          goto LABEL_760;
        v75 = v175;
        if ( (v175 & 0xFA) == 0 && v175 != 1
          || (v76 = *(_QWORD *)(v3 + 176), (*(_DWORD *)(v76 + 16) & 8) != 0)
          || (v74 = *(_DWORD *)(v5 + 436), (v74 & 0x10000) != 0)
          || *(_QWORD *)(v3 + 184)
          && ((v77 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 8) + 8LL) + 16LL)
                   | *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v76 + 8) + 8LL) + 24LL),
               (v77 & 0x2000000) != 0)
           || (v74 & 6) != 0
           || (v77 & 0x10D0116) != 0) )
        {
          *(_DWORD *)(v5 + 4) |= 0x10000u;
        }
        if ( (*(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 2) != 0 )
        {
          LOBYTE(v74) = 1;
          NtfsFspCloseInternal(0, v55, v74, 0, 0);
          v75 = v175;
        }
        v78 = *(_QWORD *)(v3 + 32);
        v79 = *(_QWORD *)(v78 + 64);
        if ( v79 )
        {
          *(_QWORD *)(v78 + 16) = *(_QWORD *)(v79 + 16);
          if ( *(_WORD *)v3 && **(_WORD **)(v3 + 8) == 58 && (unsigned __int8)(v75 - 2) <= 1u )
            *(_DWORD *)(v5 + 4) |= 0x10000u;
          v78 = *(_QWORD *)(v3 + 32);
          v80 = *(_QWORD *)(*(_QWORD *)(v78 + 64) + 32LL);
          if ( v80 && (*(_DWORD *)(v80 + 8) & 0x10) != 0 )
            *(_DWORD *)(v3 + 156) |= 0x400000u;
        }
        if ( (*(_DWORD *)(v3 + 156) & 0x40) != 0 )
        {
          v81 = *(_WORD *)v3;
          if ( ((*(_WORD *)v3 - 8) & 0xFFFD) != 0 )
          {
            if ( ((v81 - 16) & 0xFFFD) != 0 )
            {
              InformationForQueryOpen = -1073741811;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_253;
              v67 = 658744;
              goto LABEL_252;
            }
            if ( v81 == 16 )
            {
              v82 = *(__int64 **)(v78 + 96);
              if ( !v82[1] )
              {
                v83 = *v82;
LABEL_327:
                v185 = v83;
                goto LABEL_328;
              }
            }
            if ( v81 != 18 || (v84 = *(__int64 **)(v78 + 96), *(__int64 *)((char *)v84 + 10)) )
            {
              if ( !*(_QWORD *)(v55 + 160) )
              {
                InformationForQueryOpen = -1073741811;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_253;
                v67 = 658739;
                goto LABEL_252;
              }
              if ( (int)NtfsLookupObjectId(v5) < 0 )
              {
                InformationForQueryOpen = -1073741772;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_253;
                v67 = 658732;
                goto LABEL_252;
              }
              _InterlockedIncrement((volatile signed __int32 *)(v55 + 8552));
              v78 = *(_QWORD *)(v3 + 32);
LABEL_328:
              *(_QWORD *)(v78 + 96) = 0;
              *(_WORD *)(*(_QWORD *)(v3 + 32) + 88LL) = 0;
              v85 = NtfsOpenFcbById(v5, (__int64)&NtfsEmptyString, 0, v3);
              InformationForQueryOpen = v85;
              if ( v85 != 259 && v85 != 871 )
              {
                v87 = *(_DWORD *)(v3 + 156);
                if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL) + 12LL) & 1) != 0 )
                  v86 = v87 & 0xFFFFFFEF;
                else
                  v86 = v87 | 0x10u;
                *(_DWORD *)(v3 + 156) = v86;
                *(_QWORD *)(*(_QWORD *)(v3 + 32) + 96LL) = *(_QWORD *)(v3 + 8);
                *(_WORD *)(*(_QWORD *)(v3 + 32) + 88LL) = *(_WORD *)v3;
              }
LABEL_580:
              v68 = 8;
LABEL_581:
              if ( !InformationForQueryOpen )
              {
                if ( v190 <= 0 || (InformationForQueryOpen = 0, v190 == 264) )
                  InformationForQueryOpen = v190;
              }
              if ( InformationForQueryOpen == 259 || InformationForQueryOpen == 871 )
              {
                v5 = 0;
                v195 = 0;
                v4 = 0;
                v201 = 0;
                v3 = 0;
                v200 = 0;
LABEL_592:
                if ( Bcb )
                {
                  CcUnpinData(Bcb);
                  Bcb = 0;
                }
                if ( Entry )
                {
                  NtfsCleanupIndexContext(v5, Entry);
                  ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, Entry);
                }
                if ( P )
                  ExFreePoolWithTag(P, 0);
                if ( InformationForQueryOpen == 259 )
                  return InformationForQueryOpen;
                if ( InformationForQueryOpen == 871 )
                {
LABEL_711:
                  if ( InformationForQueryOpen == 259 || InformationForQueryOpen == 871 )
                    return InformationForQueryOpen;
                  if ( (InformationForQueryOpen & 0x80000000) != 0 )
                  {
                    v171 = *(struct _KTRANSACTION **)(v3 + 184);
                    if ( v171 )
                    {
                      if ( !TmIsTransactionActive(v171) )
                      {
                        InformationForQueryOpen = -1072103421;
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(0, 3222863875LL, 660844);
                      }
                    }
                  }
                  if ( (*(_DWORD *)(v5 + 4) & 1) != 0 )
                  {
                    if ( (InformationForQueryOpen & 0x80000000) != 0 )
                      goto LABEL_728;
                    InformationForQueryOpen = NtfsCompleteLargeAllocation(
                                                v5,
                                                (_DWORD)v4,
                                                v180,
                                                *(_QWORD *)(v3 + 104),
                                                *(_QWORD *)(v3 + 112),
                                                *(_DWORD *)(v3 + 156));
                    if ( !InformationForQueryOpen )
                    {
                      if ( v190 > 0 && v190 != 264 )
                      {
                        InformationForQueryOpen = 0;
                        goto LABEL_726;
                      }
                      InformationForQueryOpen = v190;
                    }
                  }
                  if ( (InformationForQueryOpen & 0x80000000) == 0 )
                  {
LABEL_726:
                    v172 = *(struct _FILE_OBJECT **)(*(_QWORD *)(v3 + 176) + 48LL);
                    if ( v172->SectionObjectPointer )
                      NtfsUpdateBackingFileObject(v172, ChangeDataControlArea);
                  }
LABEL_728:
                  NtfsCompleteCreateRequest(v5, v3, v4, InformationForQueryOpen);
                  return InformationForQueryOpen;
                }
                if ( (*(_DWORD *)(v3 + 156) & 0x400) != 0 )
                {
                  v141 = *(_QWORD *)(v3 + 128);
                  if ( !v141 || (v142 = *(_QWORD *)(v141 + 184), v142 == *(_QWORD *)(v3 + 96)) )
                  {
                    v143 = *(_QWORD *)(v3 + 96);
                    if ( v143 )
                    {
                      NtfsReleaseFcbWithPaging(v5, v143);
                      *(_QWORD *)(v3 + 96) = 0;
                    }
                  }
                  else
                  {
                    NtfsReleaseFcbWithPaging(v5, v142);
                  }
                }
                if ( (InformationForQueryOpen & 0x80000000) != 0 || InformationForQueryOpen == 260 )
                {
                  if ( (*(_DWORD *)(*(_QWORD *)(v3 + 176) + 16LL) & 0x10000) != 0
                    && InformationForQueryOpen != -1073739511 )
                  {
                    v163 = *(_QWORD *)(v3 + 104);
                    if ( v163 )
                    {
                      if ( (v164 = *(_DWORD *)(v163 + 256), v164 == 128) && *(_WORD *)v163 == 1797
                        || v164 == 160
                        && *(_WORD *)(v163 + 264) == 8
                        && **(_QWORD **)(v163 + 272) == 0x30003300490024LL
                        && (unsigned __int16)(*(_WORD *)v163 - 1795) <= 1u )
                      {
                        FsRtlCheckOplockEx((POPLOCK)(v163 + 88), *(PIRP *)(v5 + 112), 4u, 0, 0, 0);
                      }
                    }
                  }
                  if ( (*(_DWORD *)(v3 + 156) & 0x100) != 0 )
                  {
                    v165 = *(_QWORD *)(v3 + 104);
                    if ( v165 )
                    {
                      if ( *(_QWORD *)(v3 + 112) )
                        NtfsBackoutFailedOpensPriv(
                          v5,
                          *(_QWORD *)(*(_QWORD *)(v3 + 176) + 48LL),
                          *(_QWORD *)(v3 + 96),
                          v165,
                          v3 + 112);
                    }
                  }
                  v166 = *(_QWORD *)(v3 + 96);
                  if ( v166 )
                  {
                    v167 = *(_DWORD *)(v166 + 8);
                    if ( v167 == 6 || !v167 )
                    {
                      NtfsReleaseFcbEx(v5, v166, 0);
                    }
                    else
                    {
                      if ( *(_QWORD *)(v3 + 104) )
                        v166 = *(_QWORD *)(v3 + 104);
                      NtfsTeardownStructures(v5, v166, 0);
                    }
                  }
                  if ( InformationForQueryOpen == -1073741432
                    || InformationForQueryOpen == -1073741608
                    || InformationForQueryOpen == 260 )
                  {
                    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL) + 16LL) = *(_DWORD *)(v3 + 40);
                    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL) + 20LL) = *(_DWORD *)(v3 + 44);
                    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 16LL) = *(_DWORD *)(v3 + 48);
                  }
                  v168 = v196;
                  v169 = *(void **)(v196 + 8);
                  v170 = (_OWORD *)v193;
                  if ( v169 && *(void **)(v193 + 8) != v169 )
                  {
                    ExFreePoolWithTag(v169, 0);
                    *(_QWORD *)(v168 + 8) = 0;
                  }
                  *(_OWORD *)(*(_QWORD *)(v3 + 32) + 88LL) = *v170;
                  *(_DWORD *)(v5 + 4) &= ~1u;
                  goto LABEL_708;
                }
                if ( !v177 )
                {
                  v144 = *(_QWORD *)(v3 + 104);
                  if ( *(_WORD *)(v144 + 264)
                    && *(_DWORD *)(v144 + 256) == 128
                    && (unsigned __int8)NtfsTelemetryGuard(512) )
                  {
                    NtfsTelemetryNamedStreams(v182, *(_QWORD *)(*(_QWORD *)(v3 + 104) + 32LL));
                  }
                  if ( (unsigned __int8)NtfsTelemetryGuard(512) )
                    NtfsTelemetryCreateFile(v182, v3, v175);
                }
                if ( *(_QWORD *)(v3 + 208) )
                  NtfsQueryInformationForCreate(v5);
                v145 = *(_DWORD **)(v193 + 8);
                if ( v145 && v145 != *(_DWORD **)(v196 + 8) && v145 != *(_DWORD **)(*(_QWORD *)(v3 + 32) + 96LL) )
                  ExFreePoolWithTag(v145, 0);
                if ( *(_QWORD *)(v3 + 136) )
                {
                  if ( !v177 )
                  {
                    InformationForQueryOpen = NtfsQueryInformationForQueryOpen(v5);
                    v162 = *(_QWORD *)(v3 + 104);
                    if ( !*(_DWORD *)(v162 + 208) && !*(_DWORD *)(*(_QWORD *)(v162 + 184) + 268LL) )
                    {
                      LOBYTE(v161) = 1;
                      if ( !(unsigned __int8)NtfsAddScbToFspClose(v5, v162, 1, v161, 0) )
                        NtfsTeardownStructures(v5, *(_QWORD *)(v3 + 96), 0);
                    }
                    if ( NtfsStatusDebugFlags
                      && InformationForQueryOpen
                      && InformationForQueryOpen != 294
                      && InformationForQueryOpen - 298 > 1
                      && InformationForQueryOpen < 0xFFFFFFED
                      && InformationForQueryOpen != -1073741802
                      && InformationForQueryOpen + 2147483643 > 1
                      && InformationForQueryOpen != -1073741807
                      && InformationForQueryOpen != 259
                      && InformationForQueryOpen != -1073741608 )
                    {
                      NtfsStatusTraceAndDebugInternal(0, InformationForQueryOpen, 660686);
                    }
                    v4->IoStatus.Status = InformationForQueryOpen;
                  }
                  goto LABEL_708;
                }
                v146 = *(_QWORD *)(*(_QWORD *)(v3 + 112) + 72LL);
                v180 = v146;
                if ( (*(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 2) != 0 )
                {
                  LOBYTE(v86) = 1;
                  NtfsDeleteInternalAttributeStream(v5, *(_QWORD *)(v3 + 104), v86, 0);
                  v146 = v180;
                }
                if ( (*(_DWORD *)(v5 + 4) & 1) != 0 )
                {
                  v145 = (_DWORD *)*(unsigned int *)(*(_QWORD *)(v3 + 112) + 4LL);
                  if ( ((unsigned __int8)v145 & 2) != 0 )
                  {
                    if ( v146 )
                    {
                      --*(_WORD *)(*(_QWORD *)(v3 + 96) + 188LL);
                      SetFlagInterlocked(v180 + 4, 1);
                      if ( (*(_BYTE *)(*(_QWORD *)(v180 + 192) + 65LL) & 3) != 0 )
                      {
                        v145 = *(_DWORD **)(v180 + 48);
                        v145[1] |= 0x20u;
                      }
                    }
                  }
                  else
                  {
                    SetFlagInterlocked(*(_QWORD *)(v3 + 104) + 200LL, 2);
                  }
                }
                if ( (*(_DWORD *)(v3 + 156) & 0x20) != 0 )
                  SetFlagInterlocked(*(_QWORD *)(v3 + 112) + 4LL, 1);
                v147 = *(_QWORD *)(v3 + 232);
                if ( v147 && *(_WORD *)v147 >= 8u && (*(_DWORD *)(v147 + 4) & 8) != 0 )
                  SetFlagInterlocked(*(_QWORD *)(v3 + 112) + 4LL, 0x4000000);
                if ( (*(_DWORD *)(v3 + 156) & 0x10) != 0 )
                  SetFlagInterlocked(*(_QWORD *)(v3 + 112) + 4LL, 128);
                NtfsSetCcbAccessFlags(v145, v4, v3);
                if ( (*(_DWORD *)(*(_QWORD *)(v3 + 176) + 16LL) & 0x1000) != 0 )
                {
                  v148 = (_BYTE *)(*(_QWORD *)(v3 + 112) + 4LL);
                  v149 = v182;
                  if ( (*v148 & 0xA) == 0xA )
                    goto LABEL_650;
                  v150 = *(_QWORD *)(v3 + 96);
                  if ( v150 == *(_QWORD *)(*(_QWORD *)(v182 + 136) + 184LL)
                    || v150 == *(_QWORD *)(*(_QWORD *)(v182 + 152) + 184LL)
                    || v150 == *(_QWORD *)(*(_QWORD *)(v182 + 160) + 184LL) )
                  {
                    goto LABEL_650;
                  }
                  *(_DWORD *)(v3 + 156) |= 4u;
                  if ( (*(_DWORD *)(v5 + 4) & 1) == 0 )
                    SetFlagInterlocked(v148, 0x40000);
                  if ( !v180 )
                    goto LABEL_650;
                  v151 = *(_QWORD *)(v180 + 24);
                  if ( !v151 )
                    goto LABEL_650;
                  v152 = *(_BYTE *)(*(_QWORD *)(v151 + 184) + 36LL);
                  if ( (unsigned __int8)(v152 - 1) > 6u )
                    goto LABEL_650;
                  CurrentProcess = IoGetCurrentProcess();
                  ProcessImageFileName = PsGetProcessImageFileName(CurrentProcess);
                  FsLibTelemetryAddDeleteFileTableEntry(v182 + 9576, ProcessImageFileName, v152);
                }
                v149 = v182;
LABEL_650:
                v155 = *(_QWORD *)(v3 + 112);
                if ( (*(_DWORD *)(v155 + 4) & 8) == 0 )
                {
                  v156 = *(_QWORD *)(v3 + 224);
                  if ( !v156 || (*(_WORD *)(v156 + 2) & 0x400) == 0 )
                  {
                    v157 = *(_QWORD *)(v3 + 104);
                    v158 = v157 + 264;
                    if ( *(_WORD *)(v157 + 264) )
                    {
                      if ( *(_DWORD *)(v157 + 256) == 128 )
                      {
                        v159 = *(_DWORD *)(v157 + 512);
                        if ( (v159 & 0x1A00) != 0 )
                        {
                          v160 = 512;
                          if ( (v159 & 0x200) != 0 )
                          {
                            v68 = 6;
                          }
                          else
                          {
                            v160 = (v159 >> 1) & 0x400 | 0x800;
                            if ( (v159 & 0x1000) == 0 )
                              v160 = (v159 >> 1) & 0x400;
                          }
                          NtfsReportDirNotify(
                            v5,
                            *(_QWORD *)(v155 + 72),
                            v149,
                            v155 + 16,
                            *(unsigned __int16 *)(v155 + 32),
                            v158,
                            v160,
                            v68,
                            0,
                            0);
                        }
                      }
                    }
                  }
                }
                *(_DWORD *)(*(_QWORD *)(v3 + 104) + 512LL) &= 0xFFFFE1FF;
LABEL_708:
                if ( (*(_DWORD *)(v3 + 156) & 0x800) != 0 && (*(_BYTE *)(v5 + 16) & 0x20) == 0 )
                {
                  NtfsReleaseVcb(v5, v182);
                  *(_DWORD *)(v3 + 156) &= ~0x800u;
                }
                goto LABEL_711;
              }
              goto LABEL_587;
            }
          }
          else
          {
            v84 = *(__int64 **)(v78 + 96);
            if ( v81 == 8 )
            {
              v83 = *v84;
              goto LABEL_327;
            }
          }
          v83 = *(__int64 *)((char *)v84 + 2);
          goto LABEL_327;
        }
        v88 = *(_WORD *)(v78 + 88);
        if ( v88 > 2u )
        {
          v89 = *(_WORD **)(v78 + 96);
          if ( v89[1] == 92 && *v89 == 92 )
          {
            *(_WORD *)(v78 + 88) = v88 - 2;
            memmove(
              *(void **)(*(_QWORD *)(v3 + 32) + 96LL),
              (const void *)(*(_QWORD *)(*(_QWORD *)(v3 + 32) + 96LL) + 2LL),
              *(unsigned __int16 *)(*(_QWORD *)(v3 + 32) + 88LL));
            v78 = *(_QWORD *)(v3 + 32);
            if ( *(_WORD *)(v78 + 88) > 2u && *(_WORD *)(*(_QWORD *)(v78 + 96) + 2LL) == 92 )
            {
              InformationForQueryOpen = -1073741773;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_253;
              v67 = 658814;
              goto LABEL_252;
            }
          }
        }
        v90 = *(unsigned __int16 *)(v78 + 88);
        if ( (_WORD)v90 )
        {
          v91 = (_WORD **)(v78 + 96);
          if ( *(_QWORD *)(v78 + 64) && **v91 == 92 )
          {
            InformationForQueryOpen = -1073741811;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_253;
            v67 = 658828;
            goto LABEL_252;
          }
          if ( (*v91)[(v90 >> 1) - 1] == 92 && (unsigned int)v90 > 2 )
          {
            *(_DWORD *)(v3 + 156) |= 8u;
            *(_WORD *)(v78 + 88) -= 2;
            v92 = *(_QWORD *)(v3 + 32);
            v93 = *(unsigned __int16 *)(v92 + 88);
            if ( (_WORD)v93 )
            {
              if ( *(_WORD *)(*(_QWORD *)(v92 + 96) + 2 * (v93 >> 1) - 2) == 92 )
              {
                InformationForQueryOpen = -1073741773;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_253;
                v67 = 658850;
                goto LABEL_252;
              }
            }
          }
        }
        v94 = *(_DWORD *)(v3 + 156);
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v3 + 176) + 8LL) + 8LL) + 12LL) & 1) != 0 )
          v95 = v94 & 0xFFFFFFEF;
        else
          v95 = v94 | 0x10;
        *(_DWORD *)(v3 + 156) = v95;
        StartingNode = NtfsFindStartingNode(v5, (__int64)&v186, (__int64)&v180, (__int64)&v187, v3);
        InformationForQueryOpen = StartingNode;
        if ( StartingNode < 0 || StartingNode == 259 || StartingNode == 871 )
        {
          v68 = 8;
          goto LABEL_581;
        }
        if ( !(_WORD)v191 )
        {
          v68 = 8;
          goto LABEL_581;
        }
        v190 = StartingNode;
        v97 = *(_DWORD *)(v3 + 156) | 0x2000;
        *(_DWORD *)(v3 + 156) = v97;
        while ( 1 )
        {
          v98 = 0;
          if ( (v97 & 0x80000) != 0
            || (v97 & 0x200) != 0
            && (TxfGetCurrentFileInfo(v5, *(_QWORD *)(v3 + 96), 1, 1, *(_QWORD *)(v3 + 184)) & 0x400) != 0 )
          {
            break;
          }
LABEL_404:
          if ( (*(_DWORD *)(*(_QWORD *)(v3 + 96) + 176LL) & 0x10000000) == 0 )
          {
            InformationForQueryOpen = -1073741766;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3221225530LL, 659219);
            v68 = 8;
            goto LABEL_581;
          }
          InformationForQueryOpen = NtfsDissectName(&v191, v194, &v191);
          if ( (InformationForQueryOpen & 0x80000000) != 0 )
          {
            v68 = 8;
            goto LABEL_581;
          }
          if ( LOWORD(v194[0]) > 0x1FEu )
          {
            if ( (_WORD)v191 )
            {
              InformationForQueryOpen = -1073741766;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 3221225530LL, 659249);
              v68 = 8;
            }
            else
            {
              InformationForQueryOpen = -1073741773;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 3221225523LL, 659245);
              v68 = 8;
            }
            goto LABEL_581;
          }
          if ( LOWORD(v194[0]) == 2 && *(_WORD *)v194[1] == 46 )
          {
            if ( (_WORD)v191 )
            {
              InformationForQueryOpen = -1073741766;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 3221225530LL, 659263);
              v68 = 8;
            }
            else
            {
              InformationForQueryOpen = -1073741773;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 3221225523LL, 659271);
              v68 = 8;
            }
            goto LABEL_581;
          }
          Scb = NtfsCreateScb(v5, *(_QWORD *)(v3 + 96), 160, (unsigned int)&NtfsFileNameIndex, 0, 0, 0);
          v203 = Scb;
          if ( (*(_DWORD *)(*(_QWORD *)(Scb + 184) + 16LL) & 0x400) != 0 )
          {
            v111 = *(_QWORD *)(v3 + 232);
            if ( v111 && *(_WORD *)v111 >= 8u && (*(_DWORD *)(v111 + 4) & 0x10) != 0 )
            {
              InformationForQueryOpen = -1073740614;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 3221226682LL, 659314);
              v68 = 8;
              goto LABEL_581;
            }
            *(_DWORD *)(v3 + 156) |= 0x1000u;
          }
          v112 = *(_QWORD *)(v3 + 128);
          if ( v112 && !*(_WORD *)(Scb + 656) && *(_WORD *)(v112 + 656) )
            NtfsUpdateNormalizedName(v5, 0);
          if ( v180 )
          {
            if ( (*(_DWORD *)(*(_QWORD *)(v180 + 48) + 4LL) & 0x20100) == 0 )
            {
              v113 = *(_DWORD *)(v3 + 156);
              if ( (v113 & 0x201000) == 0 )
              {
                v114 = *(_DWORD *)(v3 + 84);
                if ( v114 )
                {
                  if ( !(_WORD)v191
                    && (*(_DWORD *)(v180 + 4) & 0x20) == 0
                    && (v113 & 1) == 0
                    && (*(_BYTE *)(*(_QWORD *)(v180 + 192) + 65LL) & 3) != 2 )
                  {
                    NtfsInsertPrefixHashEntry(v5, v182 + 4968, v180, v114, *(_DWORD *)(v3 + 80));
                  }
                }
              }
            }
          }
          v115 = *(_QWORD *)(v3 + 128);
          if ( v115 )
            *(_DWORD *)(v3 + 156) &= ~0x400u;
          if ( (*(_DWORD *)(v3 + 156) & 0x2000) == 0 )
          {
            NtfsReleaseFcbWithPaging(v5, *(_QWORD *)(v115 + 184));
            *(_QWORD *)(v3 + 128) = 0;
          }
          if ( (*(_DWORD *)(v3 + 156) & 0x10) != 0 )
            NtfsAccessCheck(v5, v3, *(_QWORD **)(v3 + 96), 0, (__int64)v4, 32, 1u, 0, 1);
          if ( !(unsigned __int8)NtfsIsFileNameValid(v194, 0) )
          {
            InformationForQueryOpen = -1073741773;
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3221225523LL, 659417);
            v68 = 8;
            goto LABEL_581;
          }
          v116 = Entry;
          if ( !Entry )
          {
            v117 = ExAllocateFromLookasideListEx(&NtfsIndexContextLookasideList);
            Entry = v117;
            memset((char *)v117 + 88, 0, 0x118u);
            *v117 = 0;
            v117[1] = 0;
            v117[2] = 0;
            v117[3] = 0;
            v117[4] = 0;
            *((_QWORD *)v117 + 10) = 0;
            *((_QWORD *)v117 + 12) = v117 + 7;
            *((_WORD *)v117 + 164) = 3;
            v116 = Entry;
          }
          LOBYTE(v86) = (*(_DWORD *)(v3 + 156) & 0x20) != 0
                     && ((v118 = *(_QWORD *)(v3 + 232)) != 0 && *(_WORD *)v118 >= 8u && (*(_DWORD *)(v118 + 4) & 8) != 0
                      || (*(_DWORD *)(*(_QWORD *)(Scb + 184) + 16LL) & 0x400) == 0);
          v119 = NtfsLookupEntry(
                   v5,
                   Scb,
                   v86,
                   (unsigned int)v194,
                   (__int64)&P,
                   (__int64)&v189,
                   (__int64)v207,
                   (__int64)&v198,
                   (__int64)&Bcb,
                   (__int64)v116);
          v120 = *(_DWORD *)(v3 + 156);
          if ( v119 )
            v121 = v120 | 0x4000;
          else
            v121 = v120 & 0xFFFFBFFF;
          *(_DWORD *)(v3 + 156) = v121;
          if ( *(_DWORD *)(v5 + 28) )
          {
            NtfsCheckpointCurrentTransaction(v5);
            NtfsReleaseSharedResources(v5);
          }
          v122 = *(_DWORD *)(v3 + 156);
          *(_DWORD *)(v3 + 156) = v122 & 0xFFEFFFFF;
          if ( !*(_QWORD *)(Scb + 528) )
            goto LABEL_495;
          v124 = 0;
          if ( (v122 & 0x20) != 0
            && ((v123 = *(_QWORD *)(v3 + 232)) != 0 && *(_WORD *)v123 >= 8u && (*(_DWORD *)(v123 + 4) & 8) != 0
             || (*(_DWORD *)(*(_QWORD *)(Scb + 184) + 16LL) & 0x400) == 0) )
          {
            v124 = 1;
          }
          InformationForQueryOpen = TxfCheckPathComponent(
                                      v5,
                                      v3,
                                      Scb,
                                      v194,
                                      v122 & 0x4000,
                                      (_WORD)v191 == 0,
                                      v175,
                                      *(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 4,
                                      v122 & 0x400000,
                                      v124,
                                      &v185,
                                      (char *)&v178 + 1,
                                      &v178);
          if ( (_BYTE)v178 )
            *(_DWORD *)(v3 + 156) |= 0x200000u;
          if ( InformationForQueryOpen )
          {
            if ( InformationForQueryOpen != -1 )
            {
              v68 = 8;
              goto LABEL_581;
            }
            if ( HIBYTE(v178) )
              *(_DWORD *)(v3 + 156) |= 0x400000u;
            *(_DWORD *)(v3 + 156) |= 0x4000u;
            HIDWORD(v207[0]) = 0;
            NtfsRemoveFromFileRecordCache(v5, *(unsigned int *)(*(_QWORD *)(Scb + 184) + 8LL));
            if ( Bcb )
            {
              CcUnpinData(Bcb);
              Bcb = 0;
            }
            v125 = 0;
            v198 = 0;
            NtfsReleaseFcbWithPaging(v5, *(_QWORD *)(v3 + 96));
            *(_QWORD *)(v3 + 96) = 0;
            Scb = 0;
            v203 = 0;
            v126 = *(_DWORD *)(v3 + 156) & 0xFFFFFBFF;
            *(_DWORD *)(v3 + 156) = v126;
            v127 = v126 | 0x100000;
            *(_DWORD *)(v3 + 156) = v127;
            v128 = v191;
            if ( !(_WORD)v191 )
            {
              *(_DWORD *)(v3 + 156) = v127 | 0x40;
              v129 = NtfsOpenFcbById(v5, (__int64)v202, 0, v3);
              InformationForQueryOpen = v129;
              if ( v129 == 259 || v129 == 871 || (v130 = *(_QWORD *)(v3 + 112)) == 0 )
              {
                v68 = 8;
              }
              else
              {
                v68 = 8;
                SetFlagInterlocked(v130 + 8, 8);
              }
              goto LABEL_581;
            }
          }
          else
          {
LABEL_495:
            v125 = v198;
            v128 = v191;
          }
          v97 = *(_DWORD *)(v3 + 156);
          if ( (v97 & 0x4000) != 0 )
          {
            if ( (v97 & 0xA0000) == 0x80000 )
              goto LABEL_498;
            if ( (v97 & 0x100020) == 0x20
              && ((v131 = *(_QWORD *)(v3 + 232)) != 0 && *(_WORD *)v131 >= 8u && (*(_DWORD *)(v131 + 4) & 8) != 0
               || (*(_DWORD *)(*(_QWORD *)(Scb + 184) + 16LL) & 0x400) == 0) )
            {
              memmove(v194[1], (const void *)(v125 + 82), LOWORD(v194[0]));
            }
LABEL_524:
            v133 = *(_DWORD *)(v3 + 156) & 0xFFF7FFFF;
            *(_DWORD *)(v3 + 156) = v133;
            if ( !(_WORD)v191 )
            {
              if ( (v133 & 0x4000) != 0 )
              {
                NtfsCleanupIndexContext(v5, Entry);
                ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, Entry);
                Entry = 0;
                *(_QWORD *)(v3 + 128) = Scb;
                if ( *(_QWORD *)(v3 + 136) )
                {
                  v134 = *(_DWORD *)(v3 + 152) - 68;
                  if ( v134 <= 9 )
                  {
                    v135 = 517;
                    if ( _bittest(&v135, v134) )
                    {
                      if ( !*(_QWORD *)(v3 + 208) )
                        v176 = 0;
                    }
                  }
                }
                InformationForQueryOpen = NtfsOpenFile(
                                            v5,
                                            (__int64)&Bcb,
                                            (__int64)v194,
                                            (int)v202,
                                            v186,
                                            (__int64)v207,
                                            v3,
                                            (__int64)&v187,
                                            (__int64)&v176);
                if ( InformationForQueryOpen == -1073741792 )
                {
                  InformationForQueryOpen = NtfsFillStatInfoFromMftRecord(v5, *(_DWORD *)(v3 + 152), v125);
                  if ( (InformationForQueryOpen & 0x80000000) != 0 )
                  {
                    v176 = 1;
                    InformationForQueryOpen = NtfsOpenFile(
                                                v5,
                                                (__int64)&Bcb,
                                                (__int64)v194,
                                                (int)v202,
                                                v186,
                                                (__int64)v207,
                                                v3,
                                                (__int64)&v187,
                                                (__int64)&v176);
                  }
                  else
                  {
                    v177 = 1;
                    if ( NtfsStatusDebugFlags
                      && InformationForQueryOpen
                      && InformationForQueryOpen != 294
                      && InformationForQueryOpen - 298 > 1
                      && InformationForQueryOpen != 259 )
                    {
                      NtfsStatusTraceAndDebugInternal(0, InformationForQueryOpen, 660127);
                    }
                    v4->IoStatus.Status = InformationForQueryOpen;
                    v4->IoStatus.Information = **(unsigned int **)(v3 + 144);
                  }
                }
              }
              else
              {
                *(_QWORD *)(v3 + 128) = Scb;
                if ( *(_QWORD *)(v3 + 136) )
                {
                  InformationForQueryOpen = -1073741772;
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(0, 3221225524LL, 660024);
                  *(_DWORD *)(v3 + 156) |= 2u;
                }
                else
                {
                  InformationForQueryOpen = NtfsCreateNewFile(
                                              v5,
                                              v196,
                                              (__int64)v194,
                                              (__int64)v202,
                                              v186,
                                              (__int64)&Entry,
                                              v3,
                                              (__int64)&v187);
                  *(_DWORD *)(v3 + 156) |= 2u;
                }
              }
              v136 = v182;
              if ( (InformationForQueryOpen & 0x80000000) == 0
                && *(_QWORD *)(v3 + 184)
                && (unsigned __int8)NtfsTelemetryGuard(512) )
              {
                NtfsTelemetryTxf(v136);
              }
              goto LABEL_580;
            }
            if ( (v133 & 0x100000) == 0 )
            {
              NtfsRemoveFromFileRecordCache(v5, *(unsigned int *)(*(_QWORD *)(Scb + 184) + 8LL));
              v185 = *(_QWORD *)v125;
              v179 = *(_BYTE *)(v125 + 81);
              v188 = v179;
              if ( Bcb )
              {
                CcUnpinData(Bcb);
                Bcb = 0;
              }
              v198 = 0;
            }
            NtfsReinitializeIndexContext(v5, Entry);
            *(_QWORD *)(v3 + 128) = Scb;
            v137 = NtfsOpenSubdirectory(v5, v179, v3, (__int64)&v187);
            v180 = v137;
            *(_DWORD *)(v3 + 156) |= 0x200u;
            if ( (v137
               && ((*(_DWORD *)(v137 + 4) & 1) != 0
                || (*(_BYTE *)(*(_QWORD *)(v137 + 192) + 65LL) & 3) != 0
                && (*(_DWORD *)(*(_QWORD *)(v137 + 48) + 4LL) & 0x20) != 0)
               || !*(_WORD *)(*(_QWORD *)(v3 + 96) + 188LL))
              && !(unsigned __int8)TxfCheckOpenThroughDeletedComponent(v5, v3, *(_QWORD *)(v3 + 96)) )
            {
              InformationForQueryOpen = -1073741738;
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 3221225558LL, 659944);
              v68 = 8;
              goto LABEL_581;
            }
            v138 = v180;
            if ( v180 )
            {
              if ( (*(_DWORD *)(*(_QWORD *)(v180 + 48) + 4LL) & 0x20100) == 0 && (*(_DWORD *)(v3 + 156) & 0x200000) == 0 )
              {
                NtfsInsertPrefix();
                v138 = v180;
              }
              *(_OWORD *)(v138 + 152) = *(_OWORD *)v207;
              *(_QWORD *)(v138 + 168) = v208;
              if ( (*(_BYTE *)(*(_QWORD *)(v180 + 192) + 65LL) & 3) == 2 )
                *(_DWORD *)(v3 + 156) |= 1u;
              v97 = *(_DWORD *)(v3 + 156) & 0xFFFFDFFF;
            }
            else
            {
              v97 = *(_DWORD *)(v3 + 156) | 0x2000;
            }
            *(_DWORD *)(v3 + 156) = v97;
          }
          else
          {
            if ( (v97 & 0xC0000) != 0x80000 )
            {
              if ( v128 || (*(_BYTE *)(*(_QWORD *)(v3 + 176) + 2LL) & 4) != 0 )
              {
                InformationForQueryOpen = -1073741766;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 3221225530LL, 659798);
                v68 = 8;
                goto LABEL_581;
              }
              if ( (TxfGetCurrentFileInfo(v5, *(_QWORD *)(v3 + 96), 1, 1, *(_QWORD *)(v3 + 184)) & 0x400) != 0 )
              {
                CurrentFileInfo = TxfGetCurrentFileInfo(v5, *(_QWORD *)(v3 + 96), 0, 1, *(_QWORD *)(v3 + 184));
                if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(CurrentFileInfo) )
                {
                  InformationForQueryOpen = -1073741183;
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(0, 3221226113LL, 659820);
                  v68 = 8;
                  goto LABEL_581;
                }
              }
              if ( v175 == 1 || v175 == 4 )
              {
                InformationForQueryOpen = -1073741772;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 3221225524LL, 659825);
                v68 = 8;
                goto LABEL_581;
              }
              if ( (*(_DWORD *)(*(_QWORD *)(v3 + 176) + 16LL) & 1) != 0 && v175 == 5 )
              {
                InformationForQueryOpen = -1073741773;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 3221225523LL, 659833);
                v68 = 8;
                goto LABEL_581;
              }
              if ( (*(_DWORD *)(v182 + 4) & 0x2000000) != 0 )
              {
                InformationForQueryOpen = -1073741662;
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(0, 3221225634LL, 659838);
                v68 = 8;
                goto LABEL_581;
              }
              goto LABEL_524;
            }
LABEL_498:
            v191 = v98;
          }
        }
        v99 = 1;
        v181 = 1;
        v100 = *(_DWORD *)(v3 + 156);
        if ( (v100 & 0x80000) != 0 )
        {
LABEL_386:
          if ( v99 )
          {
            if ( (v100 & 0x10) != 0 )
            {
              v105 = *(_QWORD *)(v3 + 96);
              if ( (*(_DWORD *)(v105 + 176) & 0x10000000) != 0 )
                NtfsAccessCheck(v5, v3, (_QWORD *)v105, 0, (__int64)v4, 32, 1u, 0, 1);
              else
                NtfsAccessCheck(v5, v3, (_QWORD *)v105, 0, (__int64)v4, 1179785, 1u, 0, 0);
            }
            if ( *(_QWORD *)(v3 + 136) )
            {
              if ( NtfsStatusDebugFlags )
                NtfsStatusTraceAndDebugInternal(0, 260, 659160);
              InformationForQueryOpen = 260;
              v68 = 8;
              goto LABEL_581;
            }
            v106 = *(_WORD *)(v3 + 64);
            v107 = *(_WORD *)(v3 + 66);
            v108 = v106 + v107;
            if ( v107 )
            {
              v108 += 4;
            }
            else if ( v106 )
            {
              v108 += 2;
            }
            if ( (_WORD)v191 )
              v108 += 2;
            ReparsePointValue = NtfsGetReparsePointValue(v5, (unsigned __int16)v191 + v108, 0);
            InformationForQueryOpen = ReparsePointValue;
            if ( ReparsePointValue < 0 || ReparsePointValue == 260 )
            {
              v68 = 8;
              goto LABEL_581;
            }
          }
          goto LABEL_404;
        }
        v101 = TxfGetCurrentFileInfo(v5, *(_QWORD *)(v3 + 96), 0, 1, *(_QWORD *)(v3 + 184));
        NtfsLookupOpenReparseEcp(v5, v3, v101, 0);
        if ( (*(_DWORD *)(*(_QWORD *)(v3 + 96) + 176LL) & 0x10000000) != 0
          && (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(v3 + 200)) )
        {
          v86 = 1;
          v102 = *(_QWORD *)(v3 + 216);
          if ( !v102 )
          {
LABEL_373:
            v104 = *(_DWORD *)(v3 + 156) | 0x20000;
            goto LABEL_375;
          }
          v103 = (*(_DWORD *)(v102 + 20) & 2) == 0;
        }
        else
        {
          LOBYTE(v86) = 0;
          v102 = *(_QWORD *)(v3 + 216);
          if ( !v102 )
            goto LABEL_374;
          v103 = (*(_DWORD *)(v102 + 20) & 0x10) == 0;
        }
        if ( v103 )
          goto LABEL_373;
LABEL_374:
        v104 = *(_DWORD *)(v3 + 156) & 0xFFFDFFFF;
LABEL_375:
        *(_DWORD *)(v3 + 156) = v104;
        if ( (_BYTE)v86 )
        {
          if ( !v102 || (*(_DWORD *)(v102 + 20) & 4) == 0 )
            goto LABEL_382;
        }
        else if ( v102 && (*(_DWORD *)(v102 + 20) & 0x10) == 0 )
        {
LABEL_382:
          v100 = v104 | 0x40000;
          goto LABEL_383;
        }
        v100 = v104 & 0xFFFBFFFF;
LABEL_383:
        *(_DWORD *)(v3 + 156) = v100;
        if ( (v100 & 0x60000) != 0 )
        {
          v99 = 0;
          v181 = 0;
          if ( (v100 & 0x60000) != 0x60000 )
          {
            v100 |= 0x80000u;
            *(_DWORD *)(v3 + 156) = v100;
            v98 = v191;
            v206 = v191;
          }
        }
        goto LABEL_386;
      }
      LODWORD(v11) = 0;
    }
    NtfsFspCloseInternal(0, v55, v11, 0, 0);
    goto LABEL_242;
  }
  if ( (v58 & 2) != 0 || *(_QWORD *)(v3 + 136) )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225760LL, 679952);
    LOBYTE(v12) = 1;
    v60 = 0;
    goto LABEL_232;
  }
  v59 = *(_QWORD *)(v5 + 16);
  if ( (v59 & 1) == 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v5, 3221225760LL, 679975);
    LOBYTE(v12) = v4 != 0;
    v60 = v4;
LABEL_232:
    NtfsExtendedCompleteRequestInternal(v5, v60, 3221225760LL, v12, 0);
    goto LABEL_233;
  }
  *(_QWORD *)(v5 + 16) = v59 | 2;
LABEL_233:
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225760LL, 658355);
  return 3221225760LL;
}

```

## disassembly

```asm
0x1401a2d00  mov     r11, rsp
0x1401a2d03  push    rbx
0x1401a2d04  push    rsi
0x1401a2d05  push    rdi
0x1401a2d06  push    r12
0x1401a2d08  push    r13
0x1401a2d0a  push    r14
0x1401a2d0c  push    r15
0x1401a2d0e  sub     rsp, 1A0h
0x1401a2d15  movaps  xmmword ptr [r11-48h], xmm6
0x1401a2d1a  mov     rax, cs:__security_cookie
0x1401a2d21  xor     rax, rsp
0x1401a2d24  mov     [rsp+1D8h+var_50], rax
0x1401a2d2c  mov     rdi, r8
0x1401a2d2f  mov     r13, rdx
0x1401a2d32  mov     rsi, rcx
0x1401a2d35  mov     [r11-0D8h], rcx
0x1401a2d3c  mov     [r11-0A8h], rdx
0x1401a2d43  mov     [r11-0B0h], r8
0x1401a2d4a  xorps   xmm0, xmm0
0x1401a2d4d  movups  xmmword ptr [rsp+1D8h+var_A0], xmm0
0x1401a2d55  xor     r12d, r12d
0x1401a2d58  mov     [r11-128h], r12d
0x1401a2d5f  mov     [r11-120h], r12
0x1401a2d66  mov     [r11-158h], r12
0x1401a2d6d  mov     [r11-114h], r12w
0x1401a2d75  mov     [r11-0B8h], r12
0x1401a2d7c  mov     [r11-0C0h], r12
0x1401a2d83  mov     [r11-138h], r12
0x1401a2d8a  xor     eax, eax
0x1401a2d8c  movups  xmmword ptr [r11-68h], xmm0
0x1401a2d91  mov     [r11-58h], rax
0x1401a2d95  mov     [r11-130h], r12
0x1401a2d9c  mov     [r11-140h], r12
0x1401a2da3  mov     byte ptr [rsp+1D8h+var_163+3], al
0x1401a2da7  mov     byte ptr [rsp+1D8h+var_163], 1
0x1401a2dac  movups  [rsp+1D8h+var_108], xmm0
0x1401a2db4  xorps   xmm1, xmm1
0x1401a2db7  movups  xmmword ptr [rsp+1D8h+var_E8], xmm1
0x1401a2dbf  mov     byte ptr [rsp+1D8h+var_163+2], al
0x1401a2dc3  mov     [r11-0F8h], r12
0x1401a2dca  mov     r15, [rcx+68h]
0x1401a2dce  mov     [rsp+1D8h+var_148], r15
0x1401a2dd6  mov     [rsp+1D8h+var_C8], r15
0x1401a2dde  mov     r9, [r8+0B0h]
0x1401a2de5  mov     r10, [r9+30h]
0x1401a2de9  mov     [r8+20h], r10
0x1401a2ded  mov     rax, [r9+8]
0x1401a2df1  mov     rcx, [rax+8]
0x1401a2df5  mov     eax, [rcx+10h]
0x1401a2df8  mov     [r8+28h], eax
0x1401a2dfc  mov     rax, [r9+8]
0x1401a2e00  mov     rcx, [rax+8]
0x1401a2e04  mov     eax, [rcx+14h]
0x1401a2e07  mov     [r8+2Ch], eax
0x1401a2e0b  mov     rax, [r9+8]
0x1401a2e0f  mov     ebx, [rax+10h]
0x1401a2e12  mov     [r8+30h], ebx
0x1401a2e16  mov     [r8+40h], r12d
0x1401a2e1a  mov     [r8+80h], r12
0x1401a2e21  mov     eax, [rsi+10h]
0x1401a2e24  bt      rax, 14h
0x1401a2e29  jb      loc_1401A2EFD
0x1401a2e2f  mov     r11d, [r9+10h]
0x1401a2e33  bt      r11d, 0Dh
0x1401a2e38  jnb     short loc_1401A2E9D
0x1401a2e3a  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+1, 40h
0x1401a2e41  jz      loc_1401A2EFD
0x1401a2e47  movzx   ecx, word ptr [r9+1Ah]
0x1401a2e4c  movzx   edx, word ptr [r9+18h]
0x1401a2e51  movzx   r8d, word ptr [r10+58h]
0x1401a2e56  mov     eax, [r9+20h]
0x1401a2e5a  mov     [rsp+1D8h+var_170], eax
0x1401a2e5e  mov     dword ptr [rsp+1D8h+var_178], ecx
0x1401a2e62  mov     dword ptr [rsp+1D8h+var_180], ebx
0x1401a2e66  mov     dword ptr [rsp+1D8h+var_188], edx
0x1401a2e6a  mov     dword ptr [rsp+1D8h+var_190], r11d
0x1401a2e6f  mov     rax, [r10+60h]
0x1401a2e73  mov     [rsp+1D8h+var_198], rax
0x1401a2e78  mov     [rsp+1D8h+var_1A0], r8d
0x1401a2e7d  mov     rax, [r10+40h]
0x1401a2e81  mov     [rsp+1D8h+var_1A8], rax
0x1401a2e86  mov     [rsp+1D8h+PostIrpRoutine], r10
0x1401a2e8b  mov     [rsp+1D8h+Timeout], r15
0x1401a2e90  mov     r9, rsi
0x1401a2e93  mov     r8, r13
0x1401a2e96  call    McTemplateU0pppppeddddd_EtwWriteTransfer
0x1401a2e9b  jmp     short loc_1401A2EFD
0x1401a2e9d  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+1, 40h
0x1401a2ea4  jz      short loc_1401A2EFD
0x1401a2ea6  movzx   ecx, word ptr [r9+1Ah]
0x1401a2eab  movzx   edx, word ptr [r9+18h]
0x1401a2eb0  movzx   r8d, word ptr [r10+58h]
0x1401a2eb5  shr     r8d, 1
0x1401a2eb8  mov     eax, [r9+20h]
0x1401a2ebc  mov     [rsp+1D8h+var_170], eax
0x1401a2ec0  mov     dword ptr [rsp+1D8h+var_178], ecx
0x1401a2ec4  mov     dword ptr [rsp+1D8h+var_180], ebx
0x1401a2ec8  mov     dword ptr [rsp+1D8h+var_188], edx
0x1401a2ecc  mov     dword ptr [rsp+1D8h+var_190], r11d
0x1401a2ed1  mov     rax, [r10+60h]
0x1401a2ed5  mov     [rsp+1D8h+var_198], rax
0x1401a2eda  mov     [rsp+1D8h+var_1A0], r8d
0x1401a2edf  mov     rax, [r10+40h]
0x1401a2ee3  mov     [rsp+1D8h+var_1A8], rax
0x1401a2ee8  mov     [rsp+1D8h+PostIrpRoutine], r10
0x1401a2eed  mov     [rsp+1D8h+Timeout], r15
0x1401a2ef2  mov     r9, rsi
0x1401a2ef5  mov     r8, r13
0x1401a2ef8  call    McTemplateU0pppppwddddd_EtwWriteTransfer
0x1401a2efd  lea     rdx, [rsp+1D8h+ExtraCreateParameter]; ExtraCreateParameter
0x1401a2f05  mov     rcx, r13; Irp
0x1401a2f08  call    cs:__imp_IoGetIrpExtraCreateParameter
0x1401a2f0f  nop     dword ptr [rax+rax+00h]
0x1401a2f14  test    eax, eax
0x1401a2f16  js      loc_1401A383D
0x1401a2f1c  mov     rcx, [rsp+1D8h+ExtraCreateParameter]; EcpList
0x1401a2f24  test    rcx, rcx
0x1401a2f27  jz      loc_1401A383D
0x1401a2f2d  cmp     [r13+40h], r12b
0x1401a2f31  jnz     short loc_1401A2F62
0x1401a2f33  xor     r9d, r9d; EcpContextSize
0x1401a2f36  xor     r8d, r8d; EcpContext
0x1401a2f39  lea     rdx, ECP_TYPE_CLFS_CREATE_CONTAINER; EcpType
0x1401a2f40  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1401a2f47  nop     dword ptr [rax+rax+00h]
0x1401a2f4c  test    eax, eax
0x1401a2f4e  js      short loc_1401A2F5A
0x1401a2f50  or      dword ptr [rsi+1B4h], 100000h
0x1401a2f5a  mov     rcx, [rsp+1D8h+ExtraCreateParameter]; EcpList
0x1401a2f62  lea     r14, [rdi+0E0h]
0x1401a2f69  xor     r9d, r9d; EcpContextSize
0x1401a2f6c  mov     r8, r14; EcpContext
0x1401a2f6f  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x1401a2f76  call    cs:__imp_FsRtlFindExtraCreateParameter
0x1401a2f7d  nop     dword ptr [rax+rax+00h]
0x1401a2f82  mov     rcx, [r14]; EcpContext
0x1401a2f85  test    rcx, rcx
0x1401a2f88  jz      loc_1401A37C9
0x1401a2f8e  call    cs:__imp_FsRtlAcknowledgeEcp
0x1401a2f95  nop     dword ptr [rax+rax+00h]
0x1401a2f9a  mov     rdx, [r14]
0x1401a2f9d  movzx   ecx, word ptr [rdx]
0x1401a2fa0  cmp     cx, 6
0x1401a2fa4  jb      loc_1401A372C
0x1401a2faa  movzx   r8d, word ptr [rdx+2]
0x1401a2faf  test    r8b, 2
0x1401a2fb3  jz      short loc_1401A2FBF
0x1401a2fb5  cmp     cx, 10h
0x1401a2fb9  jb      loc_1401A372C
0x1401a2fbf  movzx   r9d, r8w
0x1401a2fc3  and     r9w, 4
0x1401a2fc8  jz      short loc_1401A2FEE
0x1401a2fca  cmp     cx, 18h
0x1401a2fce  jb      loc_1401A372C
0x1401a2fd4  mov     rax, [rdx+10h]
0x1401a2fd8  test    rax, rax
0x1401a2fdb  js      loc_1401A372C
0x1401a2fe1  cmp     rax, [r15+1E60h]
0x1401a2fe8  jg      loc_1401A372C
0x1401a2fee  movzx   r15d, r8w
0x1401a2ff2  and     r15w, 8
0x1401a2ff7  jz      short loc_1401A3024
0x1401a2ff9  cmp     cx, 20h ; ' '
0x1401a2ffd  jb      loc_1401A372C
0x1401a3003  mov     rax, [rdx+18h]
0x1401a3007  test    rax, rax
0x1401a300a  js      loc_1401A372C
0x1401a3010  test    r9w, r9w
0x1401a3014  jz      loc_1401A372C
0x1401a301a  cmp     rax, [rdx+10h]
0x1401a301e  jg      loc_1401A372C
0x1401a3024  test    r8b, 10h
0x1401a3028  jz      short loc_1401A3063
0x1401a302a  cmp     cx, 28h ; '('
0x1401a302e  jb      loc_1401A372C
0x1401a3034  mov     rax, [rdx+20h]
0x1401a3038  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1401a303c  jl      loc_1401A372C
0x1401a3042  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x1401a3047  jl      loc_1401A372C
0x1401a304d  cmp     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x1401a3052  jl      loc_1401A372C
0x1401a3058  cmp     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1401a305d  jl      loc_1401A372C
0x1401a3063  test    r8b, 20h
0x1401a3067  jz      short loc_1401A3073
0x1401a3069  cmp     cx, 2Ch ; ','
0x1401a306d  jb      loc_1401A372C
0x1401a3073  bt      r8w, 0Bh
0x1401a3079  jnb     short loc_1401A3092
0x1401a307b  cmp     cx, 30h ; '0'
0x1401a307f  jb      loc_1401A372C
0x1401a3085  test    dword ptr [rdx+2Ch], 0FFFFFFF0h
0x1401a308c  jnz     loc_1401A372C
0x1401a3092  movzx   r9d, r8w
0x1401a3096  and     r9w, 40h
0x1401a309b  movzx   ebx, r9w
0x1401a309f  jz      short loc_1401A30CB
0x1401a30a1  cmp     cx, 3Ch ; '<'
0x1401a30a5  jb      loc_1401A372C
0x1401a30ab  mov     eax, [rdx+38h]
0x1401a30ae  test    eax, 0FF250048h
0x1401a30b3  jnz     loc_1401A372C
0x1401a30b9  and     eax, 180000h
0x1401a30be  jz      short loc_1401A30CB
0x1401a30c0  cmp     eax, 180000h
0x1401a30c5  jnz     loc_1401A372C
0x1401a30cb  mov     eax, 80h
0x1401a30d0  movzx   r10d, r8w
0x1401a30d4  and     r10w, ax
0x1401a30d8  jz      loc_1401A3196
0x1401a30de  cmp     cx, 44h ; 'D'
0x1401a30e2  jb      short loc_1401A30F9
0x1401a30e4  mov     eax, [rdx+3Ch]
0x1401a30e7  test    al, 1
0x1401a30e9  jz      loc_1401A3196
0x1401a30ef  cmp     cx, 58h ; 'X'
0x1401a30f3  jnb     loc_1401A3196
0x1401a30f9  mov     eax, [rsi+0Ch]
0x1401a30fc  test    al, 2
0x1401a30fe  jnz     short loc_1401A3147
0x1401a3100  cmp     [rdi+88h], r12
0x1401a3107  jnz     short loc_1401A3147
0x1401a3109  mov     rax, [rsi+10h]
0x1401a310d  mov     ebx, 0C000000Dh
0x1401a3112  test    al, 1
0x1401a3114  jz      short loc_1401A3120
0x1401a3116  or      rax, 2
0x1401a311a  mov     [rsi+10h], rax
0x1401a311e  jmp     short loc_1401A317C
0x1401a3120  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a3127  test    al, al
0x1401a3129  jz      short loc_1401A313B
0x1401a312b  mov     r8d, 0A6027h
0x1401a3131  mov     edx, ebx
0x1401a3133  mov     rcx, rsi
0x1401a3136  call    NtfsStatusTraceAndDebugInternal
0x1401a313b  test    r13, r13
0x1401a313e  setnz   r9b
0x1401a3142  mov     rdx, r13
0x1401a3145  jmp     short loc_1401A316C
0x1401a3147  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a314e  mov     ebx, 0C000000Dh
0x1401a3153  test    al, al
0x1401a3155  jz      short loc_1401A3167
0x1401a3157  mov     r8d, 0A6010h
0x1401a315d  mov     edx, ebx
0x1401a315f  mov     rcx, rsi
0x1401a3162  call    NtfsStatusTraceAndDebugInternal
0x1401a3167  mov     r9b, 1
0x1401a316a  xor     edx, edx
0x1401a316c  mov     dword ptr [rsp+1D8h+Timeout], r12d
0x1401a3171  mov     r8d, ebx
0x1401a3174  mov     rcx, rsi
0x1401a3177  call    NtfsExtendedCompleteRequestInternal
0x1401a317c  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a3183  test    al, al
0x1401a3185  jz      loc_1401A5C45
0x1401a318b  mov     r8d, 0A0AB6h
0x1401a3191  jmp     loc_1401A5C3C
0x1401a3196  test    r8w, r8w
0x1401a319a  jns     loc_1401A3247
0x1401a31a0  cmp     cx, 4Ch ; 'L'
0x1401a31a4  jnb     loc_1401A3247
0x1401a31aa  mov     eax, [rsi+0Ch]
0x1401a31ad  test    al, 2
0x1401a31af  jnz     short loc_1401A31F8
0x1401a31b1  cmp     [rdi+88h], r12
0x1401a31b8  jnz     short loc_1401A31F8
0x1401a31ba  mov     rax, [rsi+10h]
0x1401a31be  mov     ebx, 0C000000Dh
0x1401a31c3  test    al, 1
0x1401a31c5  jz      short loc_1401A31D1
0x1401a31c7  or      rax, 2
0x1401a31cb  mov     [rsi+10h], rax
0x1401a31cf  jmp     short loc_1401A322D
0x1401a31d1  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a31d8  test    al, al
0x1401a31da  jz      short loc_1401A31EC
0x1401a31dc  mov     r8d, 0A6027h
0x1401a31e2  mov     edx, ebx
0x1401a31e4  mov     rcx, rsi
0x1401a31e7  call    NtfsStatusTraceAndDebugInternal
0x1401a31ec  test    r13, r13
0x1401a31ef  setnz   r9b
0x1401a31f3  mov     rdx, r13
0x1401a31f6  jmp     short loc_1401A321D
0x1401a31f8  movzx   eax, cs:NtfsStatusDebugFlags
0x1401a31ff  mov     ebx, 0C000000Dh
0x1401a3204  test    al, al
0x1401a3206  jz      short loc_1401A3218
0x1401a3208  mov     r8d, 0A6010h
0x1401a320e  mov     edx, ebx
0x1401a3210  mov     rcx, rsi
0x1401a3213  call    NtfsStatusTraceAndDebugInternal
0x1401a3218  mov     r9b, 1
0x1401a321b  xor     edx, edx
0x1401a321d  mov     dword ptr [rsp+1D8h+Timeout], r12d
0x1401a3222  mov     r8d, ebx
  ... truncated ...
```
