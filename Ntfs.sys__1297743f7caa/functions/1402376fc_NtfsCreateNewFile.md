# NtfsCreateNewFile

- ea: `0x1402376fc`
- end: `0x14023a0ec`
- name: `NtfsCreateNewFile`
- size: `10736`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `71`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401a2d00`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000cb80`
- `0x14000ea70`
- `0x140012e70`
- `0x14001c8c0`
- `0x140025a40`
- `0x140029cb0`
- `0x14002fe24`
- `0x14003efc4`
- `0x14003f358`
- `0x1400410a8`
- `0x1400592c0`
- `0x1400593e0`
- `0x140059740`
- `0x1400e724c`
- `0x140128da0`
- `0x14012bb48`
- `0x14012d1a0`
- `0x14012f980`
- `0x1401305a0`
- `0x14013f3c4`
- `0x1401403d0`
- `0x140141400`
- `0x140145b48`
- `0x14014b5f8`
- `0x14014ea90`
- `0x140153b00`
- `0x140154920`
- `0x140154d60`
- `0x1401560d0`
- `0x1401597b8`
- `0x14015b490`
- `0x14015d0d0`
- `0x140160c30`
- `0x140162110`
- `0x140163420`
- `0x140166564`
- `0x14017ff5c`
- `0x140185c50`
- `0x140187df0`
- `0x1401924c0`
- `0x140193894`
- `0x140194210`
- `0x140198300`
- `0x140199140`
- `0x14019b380`
- `0x14019c170`
- `0x14019cad0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402399ff`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402b72fb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402399ff`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1402b72fb`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x140237fc4`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x140237fc4`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140237b33`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x140237b33`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140238043`
- `ntoskrnl!RtlGetOwnerSecurityDescriptor` at `0x140238043`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x1402388b6`
- `ntoskrnl!FsRtlIsEcpFromUserMode` at `0x1402388b6`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1402391bf`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1402391e0`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1402391bf`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1402391e0`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402381cb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140238245`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b7197`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402381cb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140238245`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b7197`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402381e1`
- `ntoskrnl!ExReleasePushLockEx` at `0x14023825b`
- `ntoskrnl!ExReleasePushLockEx` at `0x140239a25`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b71b0`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b7322`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402381e1`
- `ntoskrnl!ExReleasePushLockEx` at `0x14023825b`
- `ntoskrnl!ExReleasePushLockEx` at `0x140239a25`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b71b0`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b7322`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140239977`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7273`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140239977`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7273`
- `ntoskrnl!ExFreePoolWithTag` at `0x14023868f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140239928`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7218`
- `ntoskrnl!ExFreePoolWithTag` at `0x14023868f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140239928`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7218`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402389f6`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402389f6`
- `ntoskrnl!CcUnpinData` at `0x1402398ca`
- `ntoskrnl!CcUnpinData` at `0x1402b7138`
- `ntoskrnl!CcUnpinData` at `0x1402398ca`
- `ntoskrnl!CcUnpinData` at `0x1402b7138`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402389ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x140238a5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b711f`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402389ac`
- `ntoskrnl!ExReleaseResourceLite` at `0x140238a5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b711f`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402394c6`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1402394c6`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14023895b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14023895b`

## pseudocode

```c
__int64 __fastcall NtfsCreateNewFile(
        __int64 a1,
        IRP *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        __int64 a7,
        int a8,
        __int64 *a9,
        __int64 a10,
        __int64 *a11)
{
  __int64 v13; // rsi
  int v14; // ebx
  _DWORD *Fcb; // r14
  __int64 result; // rax
  int v17; // eax
  int v18; // eax
  __int16 v19; // dx
  __int64 v20; // r8
  __int64 v21; // rax
  __int16 v22; // cx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rdx
  unsigned int CurrentFileInfo; // eax
  __int64 v29; // rcx
  __int64 v30; // r11
  __int64 v31; // rbx
  __int64 v32; // rdx
  unsigned __int16 v33; // ax
  unsigned int v34; // ebx
  __int64 OwnerId; // r12
  _DWORD *v36; // rbx
  int v37; // ecx
  int v38; // edx
  int v39; // eax
  int v40; // eax
  __int64 v41; // r8
  unsigned __int16 *v42; // rbx
  unsigned int v43; // edx
  int v44; // r9d
  __int64 v45; // rax
  int v46; // eax
  int v47; // r9d
  __int64 v48; // rax
  __int64 v49; // r8
  _DWORD *v50; // rbx
  int v51; // r9d
  int v52; // edx
  int v53; // ecx
  _DWORD *v54; // r15
  int v55; // r11d
  __int64 v56; // r10
  __int64 v57; // r9
  int v58; // eax
  __int64 v59; // r8
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int16 v64; // cx
  __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // eax
  int v68; // ebx
  __int64 v69; // rcx
  __int16 v70; // ax
  __int64 v71; // rcx
  int v72; // r11d
  __int64 v73; // r8
  __int16 v74; // cx
  __int64 v75; // r9
  __int64 v76; // rdx
  int v77; // eax
  __int16 v78; // cx
  BOOLEAN IsEcpFromUserMode; // al
  int v80; // ecx
  __int64 v81; // rcx
  int v82; // eax
  char v83; // bl
  int v84; // ebx
  unsigned int v85; // r15d
  _DWORD *v86; // r15
  struct _ERESOURCE *v87; // r12
  __int64 v88; // rdx
  unsigned int v89; // r15d
  struct _ERESOURCE *v90; // r12
  int v91; // eax
  __int64 v92; // rcx
  _QWORD *v93; // r15
  int v94; // eax
  int v95; // eax
  unsigned int v96; // ebx
  __int64 v97; // rcx
  int v98; // eax
  __int64 v99; // rcx
  __int64 v100; // rcx
  int v101; // eax
  int v102; // ebx
  __int64 v103; // rcx
  int v104; // ecx
  int v105; // r8d
  int v106; // edx
  int v107; // eax
  __int64 v108; // r9
  int v109; // ecx
  __int64 v110; // rcx
  __int64 v111; // r15
  __int64 v112; // rcx
  int v113; // eax
  int v114; // edx
  __int64 v115; // rbx
  __int64 v116; // rax
  int v117; // ecx
  bool v118; // cf
  char v119; // cl
  UNICODE_STRING *v120; // rdx
  union _LARGE_INTEGER v121; // r12
  PIRP v122; // rbx
  _QWORD *v123; // rbx
  _DWORD *v124; // r12
  __int64 v125; // rdx
  int v126; // ebx
  __int64 v127; // rax
  __int64 v128; // rax
  __int64 v129; // rbx
  char v130; // al
  int v131; // r9d
  char v132; // cl
  int v133; // r8d
  IRP *v134; // r15
  __int64 v135; // rax
  __int64 v136; // r12
  __int64 v137; // rax
  _WORD *v138; // r8
  __int64 v139; // rcx
  __int64 v140; // rcx
  __int64 v141; // rax
  PVOID *v142; // r12
  __int64 v143; // r9
  __int64 NextChildScb; // rdx
  signed __int64 v145; // rcx
  signed __int64 v146; // r10
  signed __int64 v147; // r9
  __int64 v148; // r8
  __int64 v149; // rax
  __int64 v150; // r11
  __int64 v151; // r10
  unsigned __int16 v152; // ax
  unsigned __int16 v153; // cx
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+20h] [rbp-328h]
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutinea; // [rsp+20h] [rbp-328h]
  int *CompletionRoutineb; // [rsp+20h] [rbp-328h]
  POPLOCK_FS_PREPOST_IRP PostIrpRoutine; // [rsp+28h] [rbp-320h]
  int *FileOffset; // [rsp+30h] [rbp-318h]
  int FileOffseta; // [rsp+30h] [rbp-318h]
  int ReparseBuffer; // [rsp+40h] [rbp-308h]
  __int64 QuadPart; // [rsp+48h] [rbp-300h]
  unsigned __int8 v162; // [rsp+80h] [rbp-2C8h] BYREF
  char v163; // [rsp+81h] [rbp-2C7h] BYREF
  char v164; // [rsp+82h] [rbp-2C6h]
  __int16 v165; // [rsp+83h] [rbp-2C5h]
  char v166; // [rsp+85h] [rbp-2C3h] BYREF
  unsigned __int8 v167; // [rsp+86h] [rbp-2C2h]
  char v168; // [rsp+87h] [rbp-2C1h] BYREF
  char v169; // [rsp+88h] [rbp-2C0h]
  _DWORD *v170; // [rsp+90h] [rbp-2B8h]
  char v171; // [rsp+98h] [rbp-2B0h] BYREF
  char v172; // [rsp+99h] [rbp-2AFh]
  int v173; // [rsp+9Ch] [rbp-2ACh] BYREF
  unsigned int v174; // [rsp+A0h] [rbp-2A8h]
  unsigned __int8 OwnerDefaulted[4]; // [rsp+A4h] [rbp-2A4h] BYREF
  unsigned int v176; // [rsp+A8h] [rbp-2A0h] BYREF
  int v177; // [rsp+ACh] [rbp-29Ch]
  int v178; // [rsp+B0h] [rbp-298h]
  int v179[2]; // [rsp+B8h] [rbp-290h] BYREF
  PIRP Irp; // [rsp+C0h] [rbp-288h]
  __int16 v181[2]; // [rsp+C8h] [rbp-280h]
  int v182; // [rsp+CCh] [rbp-27Ch]
  __int64 Lcb; // [rsp+D0h] [rbp-278h]
  PVOID Bcb; // [rsp+D8h] [rbp-270h] BYREF
  __int64 v185; // [rsp+E0h] [rbp-268h] BYREF
  char v186; // [rsp+E8h] [rbp-260h]
  PVOID v187; // [rsp+F0h] [rbp-258h] BYREF
  __int64 v188; // [rsp+F8h] [rbp-250h] BYREF
  unsigned __int16 *v189; // [rsp+100h] [rbp-248h]
  int v190; // [rsp+108h] [rbp-240h]
  int v191; // [rsp+10Ch] [rbp-23Ch] BYREF
  int v192; // [rsp+110h] [rbp-238h] BYREF
  _DWORD *v193; // [rsp+118h] [rbp-230h]
  __int64 v194; // [rsp+120h] [rbp-228h]
  _DWORD *v195; // [rsp+128h] [rbp-220h]
  _QWORD *v196; // [rsp+130h] [rbp-218h] BYREF
  __int64 v197; // [rsp+138h] [rbp-210h]
  PVOID P[2]; // [rsp+140h] [rbp-208h] BYREF
  PSID Owner; // [rsp+150h] [rbp-1F8h] BYREF
  unsigned __int16 *v200; // [rsp+158h] [rbp-1F0h]
  __int64 v201; // [rsp+160h] [rbp-1E8h] BYREF
  union _LARGE_INTEGER v202; // [rsp+168h] [rbp-1E0h] BYREF
  __int64 v203; // [rsp+170h] [rbp-1D8h] BYREF
  __int64 *v204; // [rsp+178h] [rbp-1D0h]
  __int64 v205; // [rsp+180h] [rbp-1C8h]
  __int64 v206; // [rsp+188h] [rbp-1C0h]
  __int64 v207[2]; // [rsp+190h] [rbp-1B8h] BYREF
  __int64 v208; // [rsp+1A0h] [rbp-1A8h] BYREF
  __int64 *v209; // [rsp+1A8h] [rbp-1A0h]
  __int64 v210; // [rsp+1B0h] [rbp-198h]
  __int64 v211; // [rsp+1B8h] [rbp-190h]
  __int64 v212; // [rsp+1C0h] [rbp-188h]
  __int64 v213; // [rsp+1C8h] [rbp-180h]
  _BYTE v214[96]; // [rsp+1D0h] [rbp-178h] BYREF
  _QWORD v215[24]; // [rsp+230h] [rbp-118h] BYREF
  char v216; // [rsp+2F0h] [rbp-58h] BYREF

  v194 = a4;
  Irp = a2;
  v13 = a10;
  v200 = a5;
  v189 = a6;
  v206 = a1;
  v212 = a3;
  v201 = a7;
  v204 = a9;
  v211 = (__int64)a9;
  v205 = a10;
  v209 = a11;
  v213 = (__int64)a11;
  v14 = 0;
  Bcb = 0;
  v202.QuadPart = 0;
  *(_QWORD *)v179 = 0;
  v187 = 0;
  v192 = 0;
  v191 = 0;
  v188 = 0;
  v185 = 0;
  Owner = 0;
  *(_OWORD *)v207 = 0;
  v208 = 0;
  v203 = 0;
  v166 = 0;
  v162 = 0;
  v163 = 0;
  OwnerDefaulted[0] = 0;
  v168 = 0;
  memset(v215, 0, sizeof(v215));
  memset(v214, 0, 0x58u);
  Fcb = *(_DWORD **)(a3 + 192);
  v170 = Fcb;
  if ( (Fcb[1] & 0x2000000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225634LL, 665472);
    return 3221225634LL;
  }
  v17 = *(_DWORD *)(a3 + 512);
  if ( (v17 & 0x4000000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225865LL, 665486);
    return 3221225865LL;
  }
  if ( (v17 & 0x10000) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221226094LL, 665491);
    return 3221226094LL;
  }
  *(_DWORD *)(a1 + 504) = 28;
  v215[1] = &v215[4];
  v215[3] = &v215[7];
  LODWORD(v215[0]) = 1572864;
  LODWORD(v215[2]) = 3407872;
  v18 = *(_DWORD *)(v13 + 156);
  if ( (v18 & 1) != 0 )
    v14 = 0x20000;
  v173 = v14;
  result = NtfsCheckValidAttributeAccess(
             a1,
             *(_QWORD *)(v13 + 176),
             (_DWORD)Fcb,
             0,
             (__int64)&v201,
             (__int64)&a8,
             v18,
             (__int64)&v173,
             (__int64)&v162);
  v174 = result;
  if ( (int)result >= 0 )
  {
    if ( v162 )
    {
      v19 = *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL);
      if ( (v19 & 0x100) != 0 )
      {
        if ( NtfsStatusDebugFlags )
        {
          v20 = 665557;
LABEL_37:
          NtfsStatusTraceAndDebugInternal(0, 3221225485LL, v20);
          return 3221225485LL;
        }
        return 3221225485LL;
      }
      v21 = *(_QWORD *)(v13 + 224);
      if ( v21 )
      {
        v22 = *(_WORD *)(v21 + 2);
        if ( (v22 & 0xD) != 0
          || (v22 & 0x40) != 0 && _bittest((const signed __int32 *)(v21 + 56), 9u) && (v19 & 0x200) != 0 )
        {
          if ( NtfsStatusDebugFlags )
          {
            v20 = 665573;
            goto LABEL_37;
          }
          return 3221225485LL;
        }
      }
    }
    else
    {
      v23 = *(_QWORD *)(v13 + 224);
      if ( v23 )
      {
        if ( *(char *)(v23 + 2) >= 0 )
          LOBYTE(v24) = 0;
        else
          v24 = *(_DWORD *)(v23 + 60);
        if ( (v24 & 1) != 0 )
          v25 = *(_DWORD *)(v23 + 76);
        else
          LOBYTE(v25) = 0;
        if ( (v25 & 1) != 0 )
        {
          if ( NtfsStatusDebugFlags )
          {
            v20 = 665586;
            goto LABEL_37;
          }
          return 3221225485LL;
        }
      }
    }
    v26 = *(_QWORD *)(v13 + 176);
    if ( (*(_DWORD *)(v26 + 16) & 0x1000) != 0 && (*(_BYTE *)(v26 + 24) & 1) != 0 && (*(_BYTE *)(v26 + 2) & 0x40) == 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225761LL, 665598);
      return 3221225761LL;
    }
    v27 = *(_QWORD *)(a3 + 184);
    if ( (*(_DWORD *)(v27 + 176) & 0x10000000) != 0
      && (TxfGetCurrentFileInfo(a1, v27, 1, 1, *(_QWORD *)(v13 + 184)) & 0x400) != 0 )
    {
      CurrentFileInfo = TxfGetCurrentFileInfo(a1, *(_QWORD *)(v13 + 96), 0, 1, *(_QWORD *)(v13 + 184));
      if ( !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(CurrentFileInfo) )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221226113LL, 665619);
        return 3221226113LL;
      }
    }
    v29 = *(_QWORD *)(a3 + 184);
    if ( ((*(_DWORD *)(v29 + 4) & 0x100) != 0 && a3 != *((_QWORD *)Fcb + 4) || ((a8 - 128) & 0xFFFFFFDF) != 0)
      && (*(int *)(v29 + 176) >= 0
       || _InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v29 + 320) + 132LL), 4, 4)
       || (int)TxfConvertMungedNameToTxfFileId(0, a6, 0, 0) < 0) )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v30 = *(_QWORD *)(a3 + 184);
        v31 = *(_QWORD *)(v30 + 96);
        v32 = *(_QWORD *)(v31 + 248);
        v33 = *(_WORD *)(v32 + 6);
        if ( v33 > 0x40u || (v33 & 1) != 0 )
          v33 = 0;
        McTemplateU0ppwwpiddd_EtwWriteTransfer(
          *(_QWORD *)(v30 + 320),
          (unsigned int)create_c10289,
          (unsigned int)KeGetCurrentThread(),
          v31,
          *(_WORD *)(v31 + 7872) >> 1,
          *(_QWORD *)(v31 + 7880),
          v33 >> 1,
          v32 + 32,
          v30,
          *(_QWORD *)(v30 + 8),
          *(_DWORD *)(v30 + 4),
          *(_DWORD *)(*(_QWORD *)(v30 + 320) + 132LL),
          a8);
      }
      v34 = -1073741790;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225506LL, 665665);
      return v34;
    }
    v195 = Fcb;
    Lcb = 0;
    v197 = 0;
    v193 = 0;
    LODWORD(OwnerId) = 0;
    *(_DWORD *)v181 = 0;
    v172 = 0;
    v169 = 0;
    v164 = 0;
    v167 = 0;
    LOBYTE(v178) = 0;
    v165 = 0;
    v196 = 0;
    if ( (Fcb[6] & 0x40000) != 0 && (*(_WORD *)(a3 + 460) & 0x40FF) != 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221226650LL, 665679);
      return 3221226650LL;
    }
    *(_DWORD *)(v13 + 196) |= 0x100u;
    v36 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 8LL) + 8LL);
    v37 = v162 != 0 ? 4 : 2;
    v190 = v37;
    v38 = v36[4];
    if ( (v38 & 0x1000000) != 0 )
    {
      v37 |= 0x1000000u;
      v190 = v37;
    }
    if ( (v36[3] & 4) != 0 )
    {
      v36[5] |= v38 & 0xFEFFFFFF;
      v36[4] = v38 & ~v36[5];
      v37 = 0;
      v190 = 0;
    }
    NtfsAccessCheck(a1, v13, *(_QWORD **)(a3 + 184), 0, (__int64)Irp, v37, 1u, 1, 0);
    v36[5] |= v36[4];
    v39 = v36[5];
    if ( (v39 & 0x2000000) != 0 )
    {
      v40 = v39 | 0x1F01FF;
      v36[5] = v40;
      v36[5] = v40 & 0xFDFFFFFF;
    }
    v36[4] = 0;
    v185 = NtfsCacheSharedSecurityForCreate(a1);
    v41 = 0;
    if ( !*(_WORD *)(a3 + 656) )
      NtfsBuildNormalizedNameWithTxfIsolation(a1, *(_QWORD *)(a3 + 184), a3, 0, 0, 0, a3 + 656);
    v42 = v189;
    v43 = *v189 + *(unsigned __int16 *)(a3 + 656);
    if ( a3 != *((_QWORD *)Fcb + 4) )
      v43 += 2;
    if ( v43 > 0xFFFE )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225734LL, 665818);
      NtfsRaiseStatusInternal(a1, -1073741562, 0, 0, 665818);
    }
    else
    {
      LOBYTE(v41) = 1;
      TxfSetupTransactionContextForCreate(a1, v13, v41, *(_QWORD *)(a3 + 184));
      if ( (*(_DWORD *)(v13 + 156) & 0x400000) == 0 )
      {
        if ( !*(_QWORD *)(a1 + 400) )
        {
LABEL_86:
          *(_DWORD *)(a1 + 436) |= 6u;
          if ( !v162 && (int)Fcb[1] >= 0 && (*(_DWORD *)(v13 + 156) & 0x20) != 0 )
          {
            v191 = 80;
            v45 = *(_QWORD *)(v13 + 232);
            if ( v45 && *(_WORD *)v45 >= 8u && (*(_DWORD *)(v45 + 4) & 8) != 0
              || (v46 = 1, (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 16LL) & 0x400) == 0) )
            {
              v46 = 0;
            }
            FileOffset = &v191;
            LODWORD(PostIrpRoutine) = v46;
            if ( (unsigned __int8)FsRtlFindInTunnelCacheEx(
                                    Fcb + 1180,
                                    *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
                                    v42,
                                    v215,
                                    &v215[2]) )
            {
              v164 = 1;
              v186 = 1;
              if ( LOBYTE(v215[23]) )
              {
                NtfsAcquireExclusiveScbEx(a1, *((_QWORD *)Fcb + 20), 0);
                *(_DWORD *)(v13 + 156) |= 0x80u;
                *(_DWORD *)(v13 + 196) |= 0x80000u;
              }
            }
          }
          if ( (Fcb[1126] & 0x10) == 0 )
          {
LABEL_101:
            *(_QWORD *)v179 = NtfsAllocateMftRecord(a1);
            LOBYTE(v47) = 1;
            NtfsPinMftRecord(a1, (int)Fcb, (int)v179, v47, &Bcb, &v187, (union _LARGE_INTEGER)&v202);
            HIWORD(v179[1]) = *((_WORD *)v187 + 8);
            if ( !HIWORD(v179[1]) )
              HIWORD(v179[1]) = 1;
            v48 = *(_QWORD *)(a3 + 184);
            v49 = *(_QWORD *)(v48 + 320);
            if ( !v49 )
              v49 = *(_QWORD *)(*(_QWORD *)(v48 + 96) + 6248LL);
            PostIrpRoutine = (POPLOCK_FS_PREPOST_IRP)&v192;
            LODWORD(CompletionRoutine) = (v162 != 0 ? 2 : 0)
                                       | (((*(_BYTE *)(*(_QWORD *)(v13 + 176) + 2LL) & 2) != 0) + 36);
            Fcb = NtfsCreateFcb(a1, (__int64)Fcb, v49, *(_QWORD *)v179, CompletionRoutine);
            v193 = Fcb;
            HIBYTE(v165) = (v192 & 4) != 0;
            if ( (v192 & 2) == 0 )
            {
              v50 = v170 + 164;
              if ( (v192 & 1) != 0 )
              {
                ExAcquirePushLockSharedEx(v170 + 164, 0);
                _InterlockedDecrement(Fcb + 7);
                ExReleasePushLockEx(v50, 0);
                HIBYTE(v165) = 0;
                v193 = 0;
                v52 = 2;
                LOBYTE(FileOffset) = 0;
                v53 = a1;
                PostIrpRoutine = 0;
                CompletionRoutineb = v179;
                if ( *(int *)(a1 + 24) >= 0 )
                {
LABEL_445:
                  v68 = 666096;
                  NtfsAttachCorruption_BadOrOrphanFRS(
                    v53,
                    v52,
                    666096,
                    v51,
                    (__int64)CompletionRoutineb,
                    (__int64)PostIrpRoutine,
                    (char)FileOffset);
                  NtfsAttachRepairInfoPriv(a1, 256, 0, 0x170000A29F0LL);
                  NtfsPostAsyncRepairRequest(a1);
                  *(_QWORD *)(a1 + 16) |= 0x10000000uLL;
                  NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 666101);
LABEL_446:
                  if ( NtfsStatusDebugFlags
                    && (unsigned int)v68 < 0xFFFFFFED
                    && v68 != -1073741802
                    && (unsigned int)(v68 + 2147483643) > 1
                    && v68 != -1073741807
                    && v68 != -1073741608 )
                  {
                    NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v68, 666353);
                  }
                  NtfsRaiseStatusInternal(a1, v68, 0, 0, 666353);
LABEL_454:
                  if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
                    && ((unsigned __int8)Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
                      & (unsigned __int8)OwnerId) != 0 )
                  {
                    v150 = *(_QWORD *)(a3 + 192);
                    v151 = *(_QWORD *)(v150 + 248);
                    v152 = *(_WORD *)(v151 + 6);
                    if ( v152 > (unsigned __int16)v68 || (v152 & 1) != 0 )
                    {
                      v153 = v114;
                      v178 = v114;
                    }
                    else
                    {
                      v153 = *(_WORD *)(v151 + 6);
                      v178 = v153;
                    }
                    LOWORD(v209) = v153;
                    v210 = v151 + 32;
                    McTemplateU0ppwwpidd_EtwWriteTransfer(
                      v153 >> 1,
                      (unsigned int)create_c11501,
                      (unsigned int)KeGetCurrentThread(),
                      v150,
                      *(_WORD *)(v150 + 7872) >> 1,
                      *(_QWORD *)(v150 + 7880),
                      v153 >> 1,
                      v151 + 32,
                      *(_QWORD *)(a3 + 184),
                      *(_QWORD *)(*(_QWORD *)(a3 + 184) + 8LL),
                      *(_DWORD *)(*(_QWORD *)(a3 + 184) + 4LL),
                      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 184) + 320LL) + 132LL));
                  }
                  v126 = -1073741790;
                  if ( NtfsStatusDebugFlags )
                    NtfsStatusTraceAndDebugInternal(a1, 3221225506LL, 666876);
                  NtfsRaiseStatusInternal(a1, -1073741790, 0, 0, 666876);
                  goto LABEL_464;
                }
LABEL_442:
                NtfsAttachCorruption_BadOrOrphanFRS(
                  v53,
                  v52,
                  666080,
                  v51,
                  (__int64)CompletionRoutineb,
                  (__int64)PostIrpRoutine,
                  (char)FileOffset);
                NtfsAttachRepairInfoPriv(a1, 256, 0, 0x1A8000A29E0LL);
                if ( NtfsStatusDebugFlags )
                  NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 666080);
                NtfsRaiseStatusInternal(a1, -1073741566, (unsigned int)v179, 0, 666080);
                goto LABEL_445;
              }
              *(_DWORD *)(a1 + 4) |= 0x10000u;
              NtfsAcquireFcbWithPaging(a1, Fcb, 0, 4);
              ExAcquirePushLockSharedEx(v50, 0);
              _InterlockedDecrement(Fcb + 7);
              ExReleasePushLockEx(v50, 0);
              HIBYTE(v165) = 0;
              LOBYTE(CompletionRoutinea) = 0;
              NtfsVerifyFileRecordIsNotInUse(
                a1,
                (_DWORD)Fcb,
                (_DWORD)v187,
                (unsigned int)v179,
                (__int64)CompletionRoutinea);
              v54 = v170;
              NtfsInitializeMftRecord(a1, (_DWORD)v170, (unsigned int)v179, (_DWORD)v187, (__int64)Bcb, v162);
              *((_WORD *)v187 + 11) |= 1u;
              _InterlockedAdd(Fcb + 6, 1u);
              v172 = 1;
              if ( Irp->AssociatedIrp.MasterIrp )
              {
                if ( *(_QWORD *)(v13 + 184) )
                {
                  v34 = -1073741745;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_123;
                  v59 = 666186;
LABEL_122:
                  NtfsStatusTraceAndDebugInternal(0, v34, v59);
LABEL_123:
                  v174 = v34;
                  goto LABEL_368;
                }
                v55 = *(_DWORD *)(*(_QWORD *)(v13 + 176) + 16LL);
                if ( (v55 & 0x200) != 0 || (v173 & 2) == 0 )
                {
                  if ( (*(_DWORD *)(a1 + 16) & 0x100000) != 0
                    || (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) == 0 )
                  {
                    v54 = v170;
                  }
                  else
                  {
                    v56 = *((_QWORD *)Fcb + 12);
                    v57 = *(_QWORD *)(v56 + 248);
                    v58 = *(unsigned __int16 *)(v57 + 6);
                    if ( (unsigned __int16)v58 > 0x40u || (v58 & 1) != 0 )
                      v58 = 0;
                    v182 = v58;
                    LOWORD(P[0]) = v58;
                    P[1] = (PVOID)(v57 + 32);
                    v54 = v170;
                    McTemplateU0ppwwpidd_EtwWriteTransfer(
                      (unsigned __int16)v58 >> 1,
                      (unsigned int)create_c10805,
                      (unsigned int)KeGetCurrentThread(),
                      (_DWORD)v170,
                      *(_WORD *)(v56 + 7872) >> 1,
                      *(_QWORD *)(v56 + 7880),
                      (unsigned __int16)v58 >> 1,
                      v57 + 32,
                      (char)Fcb,
                      *((_QWORD *)Fcb + 1),
                      v55,
                      v173);
                  }
                  v34 = -1073741790;
                  if ( !NtfsStatusDebugFlags )
                    goto LABEL_123;
                  v59 = 666180;
                  goto LABEL_122;
                }
              }
              if ( *(_QWORD *)(*((_QWORD *)Fcb + 12) + 104LL) )
              {
                v60 = v185;
                Fcb[70] = *(_DWORD *)(v185 + 12);
                *((_QWORD *)Fcb + 26) = v60;
                v185 = 0;
              }
              v61 = v188;
              if ( v188 )
              {
                Fcb[66] = OwnerId;
                *((_QWORD *)Fcb + 15) = v61;
                v188 = 0;
              }
              if ( (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 4LL) & 8) == 0 )
                NtfsUpdateFcbInfoFromDisk(a1, 0, 0);
              *((_QWORD *)Fcb + 29) = *(_QWORD *)(*(_QWORD *)(a3 + 184) + 232LL);
              v62 = *(_QWORD *)(v13 + 224);
              if ( (!v62 || (*(_BYTE *)(v62 + 2) & 0x40) == 0 || (*(_DWORD *)(v62 + 56) & 0x20) == 0) && !v162 )
                *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) |= 0x20u;
              v63 = *(_QWORD *)(v13 + 224);
              if ( v63
                && ((v64 = *(_WORD *)(v63 + 2), (v64 & 1) != 0)
                 || (v64 & 0x40) != 0
                 && (*(_DWORD *)(v63 + 56) & 0x200) != 0
                 && (*(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) & 0x200) != 0) )
              {
                *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) |= 0x200u;
                v182 = 1;
              }
              else
              {
                *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) &= ~0x200u;
                v182 = 0;
              }
              v65 = *(_QWORD *)(v13 + 176);
              if ( (*(_DWORD *)(v65 + 16) & 0x8000) != 0
                || (*(_BYTE *)(v65 + 2) & 2) != 0
                || (dword_1400956B8 & 0x400) != 0 )
              {
LABEL_163:
                v69 = *(_QWORD *)(v13 + 176);
                v70 = *(_WORD *)(v69 + 24);
                if ( v167 )
                {
                  *(_WORD *)(v69 + 24) = v70 | 0x800;
                  if ( (unsigned __int8)*(_WORD *)(a3 + 460) )
                    v181[0] = (unsigned __int8)*(_WORD *)(a3 + 460);
                  else
                    v181[0] = 1;
                }
                else
                {
                  *(_WORD *)(v69 + 24) = v70 & 0xF7FF;
                }
                v71 = *(_QWORD *)(v13 + 224);
                if ( !v71 || (*(_BYTE *)(v71 + 2) & 0x40) == 0 || (*(_DWORD *)(v71 + 56) & 0x2000) == 0 )
                {
                  *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) &= ~0x2000u;
                  *(_WORD *)(*(_QWORD *)(v13 + 176) + 24LL) |= *(_WORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x2000;
                }
                v72 = *(unsigned __int16 *)(*(_QWORD *)(v13 + 176) + 24LL);
                v177 = v72;
                v73 = *(_QWORD *)(v13 + 224);
                if ( v73 && (v74 = *(_WORD *)(v73 + 2), (v74 & 0x40) != 0) && (*(_DWORD *)(v73 + 56) & 0x20000) != 0 )
                {
                  v75 = *(_QWORD *)(v13 + 224);
                  v76 = v75;
                  if ( (v74 & 0x20) != 0 )
                  {
                    if ( (*(_DWORD *)(v73 + 40) & 0x20000) != 0 )
                    {
                      v77 = 1;
                      goto LABEL_181;
                    }
                    v76 = *(_QWORD *)(v13 + 224);
                  }
                  v77 = 0;
                }
                else
                {
                  v77 = *(_DWORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x20000;
                  v75 = *(_QWORD *)(v13 + 224);
                  v76 = v75;
                }
LABEL_181:
                if ( v77 )
                {
                  v72 |= *(_DWORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x20000;
                  v177 = v72;
                }
                if ( v73 )
                {
                  v78 = *(_WORD *)(v73 + 2);
                  if ( (v78 & 0x20) != 0 && (v75 = v76, (*(_DWORD *)(v76 + 40) & 0x180000) != 0)
                    || (v76 = v75, (v78 & 0x40) != 0) && (*(_DWORD *)(v75 + 56) & 0x180000) != 0 )
                  {
                    if ( (v78 & 0x20) != 0 )
                    {
                      v72 |= *(_DWORD *)(v75 + 40) & 0x180000;
LABEL_194:
                      v177 = v72;
                      goto LABEL_195;
                    }
                    goto LABEL_195;
                  }
                }
                else
                {
                  v76 = v75;
                }
                if ( v162 || (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x180000) != 0x100000 )
                {
                  v72 |= *(_DWORD *)(*(_QWORD *)(a3 + 184) + 176LL) & 0x180000;
                  goto LABEL_194;
                }
LABEL_195:
                if ( v76 && (*(_BYTE *)(v76 + 2) & 0x20) != 0 )
                {
                  v177 = *(_DWORD *)(v76 + 40) & 0x400000 | v72;
                  IsEcpFromUserMode = FsRtlIsEcpFromUserMode((PVOID)v76);
                  v80 = (unsigned __int8)v178;
                  if ( !IsEcpFromUserMode )
                    v80 = 1;
                  v178 = v80;
                }
                if ( v162
                  && (dword_140095AD4 & 1) != 0
                  && (v81 = *(_QWORD *)(a3 + 184), (*(_DWORD *)(v81 + 16) & 0x400) != 0) )
                {
                  v82 = 1;
                }
                else
                {
                  v82 = 0;
                  v81 = *(_QWORD *)(a3 + 184);
                }
                v176 = v82;
                if ( v162 )
                  v83 = *(_BYTE *)(v81 + 36);
                else
                  v83 = 0;
                v84 = v82 ^ ((unsigned __int8)v82 ^ (unsigned __int8)(2 * v83)) & 0xE;
                v176 = v84;
                v85 = v84;
                if ( *(_BYTE *)(v81 + 38) )
                {
                  v86 = v170;
                  v87 = (struct _ERESOURCE *)(v170 + 2672);
                  ExAcquireResourceSharedLite((PERESOURCE)(v170 + 2672), 1u);
                  LOBYTE(v165) = 1;
                  v88 = *(unsigned __int8 *)(*(_QWORD *)(a3 + 184) + 38LL);
                  if ( (*(_DWORD *)(*(_QWORD *)&v86[2 * v88 + 2726] + 4LL) & 2) == 0 )
                  {
                    v84 ^= ((unsigned __int16)v84 ^ (unsigned __int16)((_WORD)v88 << 8)) & 0xF00;
                    v176 = v84;
                  }
                  v85 = v84;
                  ExReleaseResourceLite(v87);
                  LOBYTE(v165) = 0;
                }
                v89 = (v85 >> 8) & 0xF;
                if ( v89 && (v170[2724] & 1) != 0 )
                {
                  v90 = (struct _ERESOURCE *)(v170 + 2672);
                  ExAcquireResourceExclusiveLite((PERESOURCE)(v170 + 2672), 1u);
                  LOBYTE(v165) = 1;
                  if ( (v170[2724] & 1) != 0 && (*((_QWORD *)Fcb + 1) & 0xFFFFFFFFFFFFuLL) < *((_QWORD *)v170 + 1441) )
                  {
                    v91 = *((unsigned __int16 *)v170 + 5762);
                    if ( _bittest(&v91, v89) )
                    {
                      if ( (int)v170[2880] >= 0 )
                        v170[2880] = -1073740624;
                    }
                  }
                  ExReleaseResourceLite(v90);
                  LOBYTE(v165) = 0;
                }
                v92 = *(_QWORD *)(v13 + 224);
                if ( v92 && (*(_BYTE *)(v92 + 2) & 0x10) != 0 )
                  v93 = *(_QWORD **)(v92 + 32);
                else
                  v93 = v196;
                if ( v92 )
                {
                  if ( *(char *)(v92 + 2) >= 0 )
                    LOBYTE(v94) = 0;
                  else
                    v94 = *(_DWORD *)(v92 + 60);
                  if ( (v94 & 1) != 0 )
                    v95 = *(_DWORD *)(v92 + 76);
                  else
                    LOBYTE(v95) = 0;
                  if ( (v95 & 1) != 0 )
                  {
                    if ( (*(_DWORD *)(v92 + 80) & 1) != 0 )
                    {
                      if ( (dword_140095AD4 & 1) == 0 )
                        goto LABEL_237;
                      v96 = v84 | 1;
                    }
                    else
                    {
                      v96 = v84 & 0xFFFFFFFE;
                    }
                    v176 = v96;
                  }
                }
LABEL_237:
                NtfsInitializeFcbAndStdInfo(a1, (_DWORD)Fcb, v162, 0, v167, v182, v177, (__int64)&v176, v178);
                v34 = TxfOpenFileProcessing(
                        a1,
                        (__int64)Fcb,
                        0,
                        0,
                        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 8LL) + 8LL) + 20LL) | 2u,
                        0,
                        *(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL),
                        v13,
                        0);
                v174 = v34;
                if ( !v34 )
                {
                  v97 = *(_QWORD *)(v13 + 224);
                  if ( v97 )
                  {
                    if ( (*(_BYTE *)(v97 + 2) & 0x10) != 0 )
                    {
                      v98 = v173;
                      if ( v93[1] == -1 )
                      {
                        v98 = v173 | 0x40;
                        v173 |= 0x40u;
                      }
                      if ( v93[2] == -1 )
                      {
                        v98 |= 0x10u;
                        v173 = v98;
                      }
                      if ( v93[3] == -1 )
                        v173 = v98 | 0x20;
                      *(_WORD *)(v97 + 4) |= 0x10u;
                    }
                    v99 = *(_QWORD *)(v13 + 224);
                    LOBYTE(OwnerId) = 32;
                    if ( (*(_BYTE *)(v99 + 2) & 0x20) != 0 )
                      *(_WORD *)(v99 + 4) |= 0x20u;
                    if ( (v176 & 1) != 0 )
                    {
                      v100 = *(_QWORD *)(v13 + 224);
                      if ( *(char *)(v100 + 2) >= 0 )
                        LOBYTE(v101) = 0;
                      else
                        v101 = *(_DWORD *)(v100 + 60);
                      if ( (v101 & 1) != 0 )
                        *(_DWORD *)(v100 + 84) |= 1u;
                    }
                  }
                  else
                  {
                    LOBYTE(OwnerId) = 32;
                  }
                  if ( v162 )
                  {
                    v54 = v170;
                    NtfsCreateIndex(a1, (int)Fcb, v170[88], *((_BYTE *)v170 + 348), 0, v181[0], 1, 0);
                    v102 = v173;
                  }
                  else
                  {
                    v102 = v173;
                    if ( (v173 & 2) == 0 )
                    {
                      v196 = (_QWORD *)*(int *)(*((_QWORD *)Fcb + 12) + 360LL);
                      NtfsConditionallyUpdateQuota(a1, (_DWORD)Fcb, (unsigned int)&v196, 0, 1);
                      memset(v214, 0, 0x58u);
                      v169 = 1;
                      LOBYTE(ReparseBuffer) = 0;
                      LOWORD(FileOffseta) = v181[0];
                      NtfsCreateAttributeWithValue(a1, Fcb, 128, 0, 0, 0, FileOffseta, 0, ReparseBuffer, v214);
                      NtfsCleanupAttributeContext(v103, v214);
                      v169 = 0;
                      *((_QWORD *)Fcb + 20) = 0;
                      *((_QWORD *)Fcb + 21) = 0;
                      *(_DWORD *)(v13 + 196) |= 0x200000u;
                    }
                    v54 = v170;
                  }
                  Lcb = NtfsCreateLcb(a1, a3, (_DWORD)Fcb, (_DWORD)v189, 0, 0);
                  v197 = Lcb;
                  v104 = *(_DWORD *)(v13 + 156) & 0x40;
                  if ( a8 == 160 )
                  {
                    v105 = v102;
                    if ( v104 )
                    {
                      v105 = v102 | 8;
                      v106 = 0;
                    }
                    else
                    {
                      v106 = *v200 - *v189;
                    }
                    v107 = NtfsOpenAttribute(
                             a1,
                             (__int64)Fcb,
                             v106,
                             (__int64)&NtfsFileNameIndex,
                             160,
                             2,
                             3,
                             1,
                             v105,
                             0,
                             v13 + 104,
                             v13,
                             v13 + 112);
                  }
                  else
                  {
                    if ( v104 )
                      v109 = 0;
                    else
                      v109 = *v200 - *v189;
                    v107 = NtfsOpenNewAttr(a1, v109, v201, a8, 1, v102, (__int64)&v163, v13);
                  }
                  v174 = v107;
                  v34 = v107;
                  if ( v107 >= 0 )
                  {
                    v110 = *(_QWORD *)(v13 + 224);
                    LOWORD(v68) = 64;
                    if ( v110 && (*(_BYTE *)(v110 + 2) & 0x40) != 0 )
                    {
                      *(_DWORD *)(v110 + 56) &= 0xFF254048;
                      *(_WORD *)(*(_QWORD *)(v13 + 224) + 4LL) |= 0x40u;
                    }
                    v111 = *(_QWORD *)(v13 + 104);
                    if ( !v162 )
                    {
                      if ( (*(_DWORD *)(v111 + 200) & 0x20) == 0 )
                        NtfsUpdateScbFromAttribute(a1, *(_QWORD *)(v13 + 104), 0);
                      v112 = *(_QWORD *)(v13 + 176);
                      if ( (*(_DWORD *)(v112 + 16) & 8) == 0 )
                        *(_DWORD *)(*(_QWORD *)(v112 + 48) + 80LL) |= 0x40u;
                      if ( (*(_DWORD *)(v111 + 200) & 0x10) != 0 )
                      {
                        *((_QWORD *)Fcb + 20) = *(_QWORD *)(v111 + 472);
                        *((_QWORD *)Fcb + 21) = *(_QWORD *)(v111 + 32);
                      }
                    }
                    if ( *(_QWORD *)(a1 + 400) )
                    {
                      WORD1(v207[0]) = 24;
                      v207[1] = (__int64)&v216;
                    }
                    if ( *(int *)(*(_QWORD *)(a3 + 184) + 176LL) < 0 )
                    {
                      v113 = TxfConvertMungedNameToTxfFileId(0, v189, 0, v108);
                      v114 = 0;
                      if ( v113 < 0 )
                        goto LABEL_454;
                      if ( (*(_DWORD *)(a1 + 436) & 0x80008) == 0 )
                      {
                        v114 = 0;
                        if ( _InterlockedCompareExchange(
                               (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(a3 + 184) + 320LL) + 132LL),
                               4,
                               4) )
                        {
                          goto LABEL_454;
                        }
                      }
                    }
                    v115 = Lcb;
                    NtfsAddLink(
                      a1,
                      (_DWORD)Fcb,
                      v194,
                      (__int64)&v163,
                      (__int64)&v168,
                      Lcb + 152,
                      (unsigned __int64)v207 & -(__int64)(*(_QWORD *)(a1 + 400) != 0),
                      (unsigned __int64)v215 & -(__int64)(v164 != 0),
                      *v204);
                    if ( *(_QWORD *)(a1 + 400) )
                    {
                      v117 = 0;
                      if ( (*(_DWORD *)(v13 + 156) & 0x20) != 0
                        && ((v116 = *(_QWORD *)(v13 + 232)) != 0
                         && *(_WORD *)v116 >= 8u
                         && (*(_DWORD *)(v116 + 4) & 8) != 0
                         || (*(_DWORD *)(*(_QWORD *)(a3 + 184) + 16LL) & 0x400) == 0) )
                      {
                        v117 = 1;
                      }
                      v118 = v164 != 0;
                      v164 = -v164;
                      TxfNewFileCreate(
                        a1,
                        (unsigned __int64)v215 & -(__int64)v118,
                        (__int64)v207,
                        v117,
                        v111,
                        (__int64)&v163);
                    }
                    else if ( *((_QWORD *)Fcb + 40) != *(_QWORD *)(*(_QWORD *)(*((_QWORD *)Fcb + 40) + 16LL) + 6248LL) )
                    {
                      TxfAddTxfDataAttribute(a1, 0, 0, 0);
                    }
                    v119 = v168;
                    *(_BYTE *)(*(_QWORD *)(v115 + 192) + 65LL) = v168;
                    *(_BYTE *)(v194 + 65) = v119;
                    if ( v119 == 2 )
                    {
                      RtlUpcaseUnicodeString((PUNICODE_STRING)(v115 + 72), (PCUNICODE_STRING)(v115 + 72), 0);
                      v120 = (UNICODE_STRING *)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL) + 88LL);
                      RtlUpcaseUnicodeString(v120, v120, 0);
                    }
                    Fcb[46] = 0;
                    Fcb[1] &= ~0x10u;
                    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL) + 80LL) &= 0xFFF7CFFF;
                    ClearFlagInterlocked(*(_QWORD *)(v13 + 112) + 4LL, 40894464);
                    v121 = v202;
                    v122 = Irp;
                    NtfsAssignSecurity(a1, (__int64)v187, (__int64)Bcb, v202.QuadPart, (__int64)&v163);
                    if ( v163 )
                    {
                      v124 = v170;
                    }
                    else
                    {
                      v123 = v187;
                      QuadPart = v121.QuadPart;
                      v124 = v170;
                      v123[1] = NtfsWriteLog(
                                  a1,
                                  *((_QWORD *)v170 + 6),
                                  (_DWORD)Bcb,
                                  2,
                                  (__int64)v187,
                                  *((_DWORD *)v187 + 6),
                                  0,
                                  0,
                                  0,
                                  QuadPart,
                                  0,
                                  0,
                                  v170[90]);
                      v163 = 1;
                      v122 = Irp;
                    }
                    v125 = *(_QWORD *)(v13 + 224);
                    if ( v125 && (*(_BYTE *)(v125 + 2) & 2) != 0 )
                    {
                      v126 = NtfsSetReparsePointInternal(
                               a1,
                               (__int64)v122,
                               v111,
                               *(_QWORD *)(v13 + 112),
                               0,
                               0,
                               0,
                               *(unsigned __int16 *)(v125 + 6),
                               *(PREPARSE_DATA_BUFFER *)(v125 + 8));
                      v174 = v126;
                      v127 = *(_QWORD *)(v13 + 224);
                      if ( v126 < 0 )
                      {
                        if ( !_bittest16((const signed __int16 *)(v127 + 2), 8u) )
                        {
LABEL_464:
                          if ( NtfsStatusDebugFlags
                            && (unsigned int)v126 < 0xFFFFFFED
                            && v126 != -1073741802
                            && (unsigned int)(v126 + 2147483643) > 1
                            && v126 != -1073741807
                            && v126 != -1073741608 )
                          {
                            NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v126, 667049);
                          }
                          NtfsRaiseStatusInternal(a1, v126, 0, 0, 667049);
                          goto LABEL_472;
                        }
                      }
                      else
                      {
                        *(_WORD *)(v127 + 4) |= 2u;
                        *(_DWORD *)(v13 + 196) |= 0x100000u;
                      }
                    }
                    if ( Irp->AssociatedIrp.MasterIrp )
                      NtfsAddEa(a1, *(_DWORD *)(*(_QWORD *)(v13 + 176) + 32LL), (__int64)&Irp->IoStatus);
                    v128 = *(_QWORD *)(v13 + 224);
                    if ( !v128 || !_bittest16((const signed __int16 *)(v128 + 2), 9u) )
                      NtfsUpdateFcbTimestamps(*(_QWORD *)(a3 + 184), 2684354576LL);
                    if ( (Fcb[1] & 4) != 0 )
                    {
                      v129 = *(__int64 *)(v111 + 24) >> *(_DWORD *)(*(_QWORD *)(v111 + 192) + 488LL);
                      NtfsPreloadAllocationInternal(a1, v129, 0);
                      v130 = NtfsLookupLastNtfsMcbEntry(v111 + 400, &v203, &v208);
                      v132 = 0;
                      if ( !v130 || v203 + 1 != v129 )
                      {
LABEL_472:
                        NtfsAttachCorruption_BadOrOrphanFRS(a1, 2, 667107, v131, (__int64)(Fcb + 2), (__int64)Fcb, v132);
                        NtfsAttachRepairInfoPriv(a1, 256, 0, 0x6A000A2DE3LL);
                        if ( NtfsStatusDebugFlags )
                          NtfsStatusTraceAndDebugInternal(a1, 3221225730LL, 667107);
                        result = NtfsRaiseStatusInternal(a1, -1073741566, (int)Fcb + 8, (_DWORD)Fcb, 667107);
                        __debugbreak();
                        return result;
                      }
                      v133 = v111;
                      v134 = Irp;
                      NtfsPrepareForCriticalIo(a1, (_DWORD)Irp, v133, 0, *((_QWORD *)v124 + 972), 3);
                    }
                    else
                    {
                      v134 = Irp;
                    }
                    v34 = FsRtlCheckOplockEx((POPLOCK)(a3 + 88), v134, 0x10u, 0, 0, 0);
                    v174 = v34;
                    if ( (v34 & 0x80000000) != 0 )
                    {
                      if ( NtfsStatusDebugFlags
                        && v34 < 0xFFFFFFED
                        && v34 != -1073741802
                        && v34 + 2147483643 > 1
                        && v34 != -1073741807
                        && v34 != -1073741608 )
                      {
                        NtfsStatusTraceAndDebugInternal(0, v34, 667140);
                      }
                      goto LABEL_327;
                    }
                    *(_QWORD *)(v13 + 96) = Fcb;
                    NtfsEncryptionCreateCallback(
                      a1,
                      (_DWORD)v134,
                      *(_QWORD *)(v13 + 104),
                      *(_QWORD *)(v13 + 112),
                      *(_QWORD *)(a3 + 184),
                      v13,
                      1);
                    *(_QWORD *)(v13 + 96) = 0;
                    if ( *((_BYTE *)Fcb + 232) && (int)NtfsSetDesiredStorageClass(a1) >= 0 )
                      *(_DWORD *)(v13 + 196) |= 0x1000000u;
                    v135 = *(_QWORD *)(v13 + 224);
                    v136 = Lcb;
                    if ( v135 && _bittest16((const signed __int16 *)(v135 + 2), 0xCu) )
                    {
                      NtfsUpdateDuplicateInfo(a1, (int)Fcb);
                      *(_DWORD *)(v13 + 196) |= 0x80000000;
                    }
                    NtfsPostUsnChangeWithOverrideOption(a1, *(_QWORD *)(v13 + 104), *(_DWORD *)(v13 + 196), 0, 0, 0, 0);
                    v137 = *(_QWORD *)(v13 + 224);
                    if ( v137 && *(int *)(v13 + 196) < 0 )
                      *(_WORD *)(v137 + 4) |= 0x800u;
                    v138 = *(_WORD **)(v13 + 104);
                    if ( *v138 == 1795 && !v138[328] && *(_WORD *)(a3 + 656) )
                      NtfsUpdateNormalizedName(a1, 0);
                    if ( *(_QWORD *)(a1 + 240) )
                    {
                      NtfsWriteUsnJournalChanges(a1);
                      NtfsCheckpointCurrentTransaction(a1);
                    }
                    v139 = *(_QWORD *)(v13 + 224);
                    if ( v139 )
                    {
                      if ( (*(_BYTE *)(v139 + 2) & 0x10) != 0 )
                      {
                        **(_QWORD **)(v139 + 32) = *((_QWORD *)Fcb + 16);
                        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 224) + 32LL) + 8LL) = *((_QWORD *)Fcb + 19);
                        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 224) + 32LL) + 16LL) = *((_QWORD *)Fcb + 17);
                        *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 224) + 32LL) + 24LL) = *((_QWORD *)Fcb + 18);
                        *(_WORD *)(*(_QWORD *)(v13 + 224) + 4LL) |= 0x100u;
                      }
                      v140 = *(_QWORD *)(v13 + 224);
                      if ( *(_WORD *)v140 >= 0x2Cu )
                      {
                        *(_DWORD *)(v140 + 40) = Fcb[44];
                        *(_WORD *)(*(_QWORD *)(v13 + 224) + 4LL) |= 0x200u;
                      }
                      v139 = *(_QWORD *)(v13 + 224);
                      if ( *(_WORD *)v139 >= 0x38u )
                      {
                        *(_QWORD *)(v139 + 48) = *((_QWORD *)Fcb + 36);
                        v139 = 4096;
                        *(_WORD *)(*(_QWORD *)(v13 + 224) + 4LL) |= 0x1000u;
                      }
                    }
                    if ( (*(_DWORD *)(v13 + 156) & 0x40) == 0 )
                    {
                      v141 = *(_QWORD *)(v13 + 224);
                      if ( !v141 || !_bittest16((const signed __int16 *)(v141 + 2), 0xAu) )
                        NtfsReportDirNotify(
                          a1,
                          *(_QWORD *)(*(_QWORD *)(v13 + 112) + 72LL),
                          *((_QWORD *)Fcb + 12),
                          *(_QWORD *)(v13 + 112) + 16,
                          *(unsigned __int16 *)(*(_QWORD *)(v13 + 112) + 32LL),
                          0,
                          (v162 != 0) + 1,
                          1,
                          *(_QWORD *)(a3 + 184),
                          0);
                    }
                    if ( *(int *)(v13 + 196) < 0 )
                    {
                      Fcb[46] = 0;
                      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL) + 80LL) &= 0xFFF7CFFF;
                      ClearFlagInterlocked(*(_QWORD *)(v13 + 112) + 4LL, 40894464);
                    }
                    if ( !*(_DWORD *)(v13 + 76)
                      || (*(_DWORD *)(v13 + 156) & 0x201000) != 0
                      || (v173 & 0x20000) != 0
                      || (LOBYTE(v139) = *(_BYTE *)(*(_QWORD *)(v136 + 192) + 65LL) & 3, (_BYTE)v139 == 2)
                      || *(_QWORD *)(a1 + 400) )
                    {
                      v54 = v170;
                    }
                    else
                    {
                      if ( (*(_DWORD *)(v136 + 4) & 0x20) != 0 )
                      {
                        NtfsRemoveHashEntry(
                          a1,
                          *(_QWORD *)(*(_QWORD *)(v136 + 48) + 96LL) + 4968LL,
                          *(unsigned int *)(v136 + 184),
                          v136);
                        *(_DWORD *)(v136 + 184) = 0;
                        ClearFlagInterlocked(v136 + 4, 32);
                      }
                      v54 = v170;
                      NtfsInsertPrefixHashEntry(
                        a1,
                        (_DWORD)v170 + 4968,
                        v136,
                        *(_DWORD *)(v13 + 76),
                        *(_DWORD *)(v13 + 72));
                    }
                    if ( !*(_QWORD *)(v13 + 184) )
                      NtfsInsertPrefix(v139, v136);
                    Irp->IoStatus.Information = 2;
                  }
LABEL_368:
                  if ( Bcb )
                  {
                    CcUnpinData(Bcb);
                    Bcb = 0;
                  }
                  NtfsDecrementFcbCloseCount(Fcb);
                  if ( (*(_DWORD *)(v13 + 156) & 0x80u) != 0 )
                  {
                    NtfsReleaseFcbEx(a1, *(_QWORD *)(*((_QWORD *)v54 + 20) + 184LL), 0);
                    *(_DWORD *)(v13 + 156) &= ~0x80u;
                  }
                  if ( (_QWORD *)v215[3] != &v215[7] )
                    ExFreePoolWithTag((PVOID)v215[3], 0);
                  if ( v185 )
                    NtfsDereferenceSharedSecurity(&v185);
                  if ( (v34 & 0x80000000) == 0 )
                    goto LABEL_419;
                  v142 = (PVOID *)v204;
                  if ( *v204 )
                  {
                    NtfsCleanupIndexContext(a1, *v204);
                    ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, *v142);
                    *v142 = 0;
                  }
                  v143 = *(_QWORD *)(v13 + 104);
                  if ( v143 && *(_QWORD *)(v13 + 112) )
                    NtfsBackoutFailedOpensPriv(
                      a1,
                      *(_QWORD *)(*(_QWORD *)(v13 + 176) + 48LL),
                      (_DWORD)Fcb,
                      v143,
                      v13 + 112);
                  if ( v188 )
                    NtfsDereferenceQuotaControlBlock(v54, &v188, 0);
                  if ( Fcb )
                  {
                    Fcb[1] &= ~8u;
                    ExAcquirePushLockExclusiveEx(*(_QWORD *)(a1 + 104) + 656LL, 0);
                    Fcb[1] |= 0x2000001u;
                    ExReleasePushLockEx(*(_QWORD *)(a1 + 104) + 656LL, 0);
                    *(_QWORD *)(a1 + 16) |= 0x20uLL;
                    NextChildScb = NtfsGetNextChildScb(Fcb, 0, 1);
                    if ( NextChildScb )
                    {
                      while ( 1 )
                      {
                        if ( *(_BYTE *)(NextChildScb + 460) || (*(_DWORD *)(NextChildScb + 512) & 1) != 0 )
                          *(_QWORD *)(NextChildScb + 464) = 0;
                        if ( (*(_DWORD *)(NextChildScb + 200) & 0x20000) != 0
                          && *(__int64 *)(NextChildScb + 24) > 0
                          && *(__int64 *)(NextChildScb + 464) > 0 )
                        {
                          *(_QWORD *)(NextChildScb + 464) = 0;
                        }
                        *(_QWORD *)(NextChildScb + 24) = 0;
                        if ( (*(_DWORD *)(NextChildScb + 200) & 0x20000) == 0 || *(__int64 *)(NextChildScb + 32) >= 0 )
                          goto LABEL_406;
                        v145 = 0;
                        if ( *(__int64 *)(NextChildScb + 464) <= 0 )
                          v145 = *(_QWORD *)(NextChildScb + 464);
                        if ( v145 <= *(_QWORD *)(NextChildScb + 40) )
                          goto LABEL_406;
                        if ( (*(_DWORD *)(NextChildScb + 200) & 0x20000) != 0 )
                        {
                          v146 = *(_QWORD *)(NextChildScb + 464);
                          if ( v146 < v145 )
                            goto LABEL_409;
                          if ( *(_QWORD *)(NextChildScb + 40) > v145 )
                            break;
                        }
LABEL_405:
                        *(_QWORD *)(NextChildScb + 40) = v145;
LABEL_406:
                        *(_QWORD *)(NextChildScb + 32) = 0;
                        *(_DWORD *)(NextChildScb + 200) = *(_DWORD *)(NextChildScb + 200);
                        if ( (*(_DWORD *)(NextChildScb + 200) & 0x20000) != 0 )
                        {
                          v148 = *(_QWORD *)(NextChildScb + 464);
                          if ( v148 < 0
                            || *(__int64 *)(NextChildScb + 40) > 0
                            && (!*(_QWORD *)(*(_QWORD *)(NextChildScb + 288) + 16LL) || v148 > 0) )
                          {
                            *(_QWORD *)(NextChildScb + 464) = 0;
                          }
                        }
                        *(_QWORD *)(NextChildScb + 40) = 0;
                        *(_DWORD *)(NextChildScb + 512) |= 0x40u;
                        NextChildScb = NtfsGetNextChildScb(Fcb, NextChildScb, 1);
                        if ( !NextChildScb )
                          goto LABEL_415;
                      }
                      if ( *(_QWORD *)(*(_QWORD *)(NextChildScb + 288) + 16LL) && v145 != 0x7FFFFFFFFFFFFFFFLL )
                      {
                        v147 = (v145 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                        if ( v147 < v146 )
                          *(_QWORD *)(NextChildScb + 464) = v147;
                        goto LABEL_405;
                      }
LABEL_409:
                      *(_QWORD *)(NextChildScb + 464) = v145;
                      goto LABEL_405;
                    }
LABEL_415:
                    *(_QWORD *)(v13 + 104) = 0;
                    _InterlockedIncrement((volatile signed __int32 *)(a3 + 208));
                    NtfsTeardownStructures(a1, (int)Fcb, (__int64)&v166);
                    if ( v166 )
                    {
                      Fcb = 0;
                      v149 = 0;
                    }
                    else
                    {
                      v149 = Lcb;
                    }
                    _InterlockedDecrement((volatile signed __int32 *)(a3 + 208));
                  }
                  else
                  {
LABEL_419:
                    v149 = Lcb;
                  }
                  if ( Fcb && v149 )
                  {
                    *v209 = v149;
                    *(_QWORD *)(v13 + 96) = Fcb;
                  }
                  return v34;
                }
LABEL_327:
                v54 = v170;
                goto LABEL_368;
              }
              v66 = *(_QWORD *)(v13 + 224);
              if ( v66 && (*(_BYTE *)(v66 + 2) & 0x40) != 0 )
              {
                LOBYTE(OwnerId) = 0;
                if ( (*(_DWORD *)(v66 + 56) & 0x800) != 0 )
                {
                  v67 = *(_WORD *)(v65 + 24) & 0x800;
                  goto LABEL_153;
                }
              }
              else
              {
                LOBYTE(OwnerId) = 0;
              }
              v67 = (unsigned __int8)*(_WORD *)(a3 + 460);
LABEL_153:
              if ( v67 )
              {
                v171 = 0;
                if ( (dword_1400956B8 & 0x80u) != 0 )
                {
                  if ( *((_QWORD *)&xmmword_140095770 + 1) )
                  {
                    if ( a8 != 160 )
                    {
                      if ( byte_1400957C0 )
                      {
                        *(_OWORD *)P = 0;
                        NtfsBuildNormalizedNameWithTxfIsolation(a1, *(_QWORD *)(v13 + 96), 0, 0, 0, 0, (__int64)P);
                        if ( P[1] )
                        {
                          v68 = (*((__int64 (__fastcall **)(_QWORD, PIRP, _QWORD, PVOID *, char *))&xmmword_140095770 + 1))(
                                  *(_QWORD *)(v13 + 176),
                                  Irp,
                                  0,
                                  P,
                                  &v171);
                          ExFreePoolWithTag(P[1], 0);
                          if ( v68 < 0 )
                            goto LABEL_446;
                        }
                      }
                    }
                  }
                }
                if ( v171 )
                  *(_DWORD *)(*(_QWORD *)(v13 + 176) + 16LL) |= 0x8000u;
                else
                  v167 = 1;
              }
              goto LABEL_163;
            }
LABEL_441:
            NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 666048);
            goto LABEL_442;
          }
          LODWORD(v42) = RtlGetOwnerSecurityDescriptor((PSECURITY_DESCRIPTOR)(v185 + 28), &Owner, OwnerDefaulted);
          v174 = (unsigned int)v42;
          if ( (int)v42 >= 0 )
          {
            if ( Owner )
            {
              OwnerId = (unsigned int)NtfsGetOwnerId(a1, Owner);
              v188 = NtfsInitializeQuotaControlBlock(Fcb, OwnerId);
              NtfsAcquireQuotaControl(a1, v188);
              goto LABEL_101;
            }
LABEL_438:
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 3221225562LL, 665968);
            NtfsRaiseStatusInternal(a1, -1073741734, 0, 0, 665968);
            goto LABEL_441;
          }
LABEL_430:
          if ( NtfsStatusDebugFlags
            && (unsigned int)v42 < 0xFFFFFFED
            && (_DWORD)v42 != -1073741802
            && (unsigned int)((_DWORD)v42 + 2147483643) > 1
            && (_DWORD)v42 != -1073741807
            && (_DWORD)v42 != -1073741608 )
          {
            NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v42, 665963);
          }
          NtfsRaiseStatusInternal(a1, (_DWORD)v42, 0, 0, 665963);
          goto LABEL_438;
        }
        LODWORD(v42) = *(_DWORD *)(*(_QWORD *)(a3 + 184) + 4LL);
        TxfPrepareFileForTxfLogging(a1, v13, 0, 1, 0);
        v44 = 0;
        if ( ((unsigned int)v42 & 0x40000) != 0 )
        {
          v42 = v189;
          goto LABEL_86;
        }
LABEL_429:
        NtfsRaiseStatusInternal(a1, -1073741608, 0, v44, 665870);
        goto LABEL_430;
      }
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3222863873LL, 665835);
    NtfsRaiseStatusInternal(a1, -1072103423, 0, 0, 665835);
    goto LABEL_429;
  }
  return result;
}

```

## disassembly

```asm
0x1402376fc  mov     r11, rsp
0x1402376ff  push    rbx
0x140237700  push    rsi
0x140237701  push    rdi
0x140237702  push    r12
0x140237704  push    r13
0x140237706  push    r14
0x140237708  push    r15
0x14023770a  sub     rsp, 310h
0x140237711  mov     rax, cs:__security_cookie
0x140237718  xor     rax, rsp
0x14023771b  mov     [rsp+348h+var_40], rax
0x140237723  mov     [rsp+348h+var_228], r9
0x14023772b  mov     r13, r8
0x14023772e  mov     [rsp+348h+Irp], rdx
0x140237736  mov     rdi, rcx
0x140237739  mov     rsi, [rsp+348h+arg_48]
0x140237741  mov     rax, [rsp+348h+arg_20]
0x140237749  mov     [rsp+348h+var_1F0], rax
0x140237751  mov     r12, [rsp+348h+arg_28]
0x140237759  mov     [rsp+348h+var_248], r12
0x140237761  mov     [rsp+348h+var_1C0], rcx
0x140237769  mov     [rsp+348h+var_188], r8
0x140237771  mov     rax, [rsp+348h+arg_30]
0x140237779  mov     [r11-1E8h], rax
0x140237780  mov     rax, [rsp+348h+arg_40]
0x140237788  mov     [rsp+348h+var_1D0], rax
0x140237790  mov     [rsp+348h+var_190], rax
0x140237798  mov     [rsp+348h+var_1C8], rsi
0x1402377a0  mov     rax, [rsp+348h+arg_50]
0x1402377a8  mov     [rsp+348h+var_1A0], rax
0x1402377b0  mov     [rsp+348h+var_180], rax
0x1402377b8  xor     r15d, r15d
0x1402377bb  mov     ebx, r15d
0x1402377be  mov     [r11-270h], r15
0x1402377c5  mov     [r11-1E0h], r15
0x1402377cc  mov     [r11-290h], r15
0x1402377d3  mov     [r11-258h], r15
0x1402377da  mov     [r11-238h], r15d
0x1402377e1  mov     [r11-23Ch], r15d
0x1402377e8  mov     [r11-250h], r15
0x1402377ef  mov     [r11-268h], r15
0x1402377f6  mov     [r11-1F8h], r15
0x1402377fd  xorps   xmm0, xmm0
0x140237800  movups  xmmword ptr [rsp+348h+var_1B8], xmm0
0x140237808  mov     [r11-1A8h], r15
0x14023780f  mov     [r11-1D8h], r15
0x140237816  mov     [r11-2C3h], r15b
0x14023781d  mov     [r11-2C8h], r15b
0x140237824  mov     [r11-2C7h], r15b
0x14023782b  mov     [r11-2A4h], r15b
0x140237832  mov     [r11-2C1h], r15b
0x140237839  xor     edx, edx; Val
0x14023783b  lea     r8d, [r15+70h]; Size
0x14023783f  lea     rcx, [r11-118h]; void *
0x140237846  call    memset
0x14023784b  xor     edx, edx; Val
0x14023784d  lea     r8d, [r15+50h]; Size
0x140237851  lea     rcx, [rsp+348h+var_A8]; void *
0x140237859  call    memset
0x14023785e  xor     edx, edx; Val
0x140237860  lea     r8d, [r15+58h]; Size
0x140237864  lea     rcx, [rsp+348h+var_178]; void *
0x14023786c  call    memset
0x140237871  mov     r14, [r13+0C0h]
0x140237878  mov     [rsp+348h+var_2B8], r14
0x140237880  test    dword ptr [r14+4], 2000000h
0x140237888  jz      short loc_1402378B1
0x14023788a  mov     al, cs:NtfsStatusDebugFlags
0x140237890  test    al, al
0x140237892  jz      short loc_1402378A6
0x140237894  mov     edx, 0C00000A2h
0x140237899  xor     ecx, ecx
0x14023789b  mov     r8d, 0A2780h
0x1402378a1  call    NtfsStatusTraceAndDebugInternal
0x1402378a6  mov     eax, 0C00000A2h
0x1402378ab  jmp     loc_14023A0C9
0x1402378b1  mov     eax, [r13+200h]
0x1402378b8  bt      eax, 1Ah
0x1402378bc  jnb     short loc_1402378E4
0x1402378be  mov     al, cs:NtfsStatusDebugFlags
0x1402378c4  test    al, al
0x1402378c6  jz      short loc_1402378DA
0x1402378c8  mov     edx, 0C0000189h
0x1402378cd  xor     ecx, ecx
0x1402378cf  mov     r8d, 0A278Eh
0x1402378d5  call    NtfsStatusTraceAndDebugInternal
0x1402378da  mov     eax, 0C0000189h
0x1402378df  jmp     loc_14023A0C9
0x1402378e4  bt      eax, 10h
0x1402378e8  jnb     short loc_140237910
0x1402378ea  mov     al, cs:NtfsStatusDebugFlags
0x1402378f0  test    al, al
0x1402378f2  jz      short loc_140237906
0x1402378f4  mov     edx, 0C000026Eh
0x1402378f9  xor     ecx, ecx
0x1402378fb  mov     r8d, 0A2793h
0x140237901  call    NtfsStatusTraceAndDebugInternal
0x140237906  mov     eax, 0C000026Eh
0x14023790b  jmp     loc_14023A0C9
0x140237910  mov     dword ptr [rdi+1F8h], 1Ch
0x14023791a  lea     rax, [rsp+348h+var_F8]
0x140237922  mov     [rsp+348h+var_110], rax
0x14023792a  lea     rax, [rsp+348h+var_E0]
0x140237932  mov     [rsp+348h+var_100], rax
0x14023793a  mov     [rsp+348h+var_118], 180000h
0x140237945  mov     [rsp+348h+var_108], 340000h
0x140237950  mov     eax, [rsi+9Ch]
0x140237956  test    al, 1
0x140237958  mov     ecx, 20000h
0x14023795d  cmovnz  ebx, ecx
0x140237960  mov     [rsp+348h+var_2AC], ebx
0x140237967  lea     rcx, [rsp+348h+var_2C8]
0x14023796f  mov     [rsp+348h+ReparseBuffer], rcx
0x140237974  lea     rcx, [rsp+348h+var_2AC]
0x14023797c  mov     qword ptr [rsp+348h+BufferLength], rcx
0x140237981  mov     dword ptr [rsp+348h+FileOffset], eax
0x140237985  lea     rax, [rsp+348h+arg_38]
0x14023798d  mov     [rsp+348h+PostIrpRoutine], rax
0x140237992  lea     rax, [rsp+348h+var_1E8]
0x14023799a  mov     [rsp+348h+CompletionRoutine], rax
0x14023799f  xor     r9d, r9d
0x1402379a2  mov     r8, r14
0x1402379a5  mov     rdx, [rsi+0B0h]
0x1402379ac  mov     rcx, rdi
0x1402379af  call    NtfsCheckValidAttributeAccess
0x1402379b4  mov     [rsp+348h+var_2A8], eax
0x1402379bb  test    eax, eax
0x1402379bd  js      loc_14023A0C9
0x1402379c3  cmp     [rsp+348h+var_2C8], r15b
0x1402379cb  jz      short loc_140237A3C
0x1402379cd  mov     rax, [rsi+0B0h]
0x1402379d4  movzx   edx, word ptr [rax+18h]
0x1402379d8  mov     ebx, 100h
0x1402379dd  test    bx, dx
0x1402379e0  jz      short loc_1402379F8
0x1402379e2  mov     al, cs:NtfsStatusDebugFlags
0x1402379e8  test    al, al
0x1402379ea  jz      loc_140237A83
0x1402379f0  mov     r8d, 0A27D5h
0x1402379f6  jmp     short loc_140237A77
0x1402379f8  mov     rax, [rsi+0E0h]
0x1402379ff  test    rax, rax
0x140237a02  jz      loc_140237A92
0x140237a08  movzx   ecx, word ptr [rax+2]
0x140237a0c  test    cl, 0Dh
0x140237a0f  jnz     short loc_140237A2A
0x140237a11  mov     r15d, 40h ; '@'
0x140237a17  test    r15b, cl
0x140237a1a  jz      short loc_140237A98
0x140237a1c  bt      dword ptr [rax+38h], 9
0x140237a21  jnb     short loc_140237A98
0x140237a23  bt      dx, 9
0x140237a28  jnb     short loc_140237A98
0x140237a2a  mov     al, cs:NtfsStatusDebugFlags
0x140237a30  test    al, al
0x140237a32  jz      short loc_140237A83
0x140237a34  mov     r8d, 0A27E5h
0x140237a3a  jmp     short loc_140237A77
0x140237a3c  mov     rcx, [rsi+0E0h]
0x140237a43  test    rcx, rcx
0x140237a46  jz      short loc_140237A8D
0x140237a48  mov     al, [rcx+2]
0x140237a4b  test    al, al
0x140237a4d  jns     short loc_140237A54
0x140237a4f  mov     eax, [rcx+3Ch]
0x140237a52  jmp     short loc_140237A57
0x140237a54  mov     eax, r15d
0x140237a57  test    al, 1
0x140237a59  jz      short loc_140237A60
0x140237a5b  mov     eax, [rcx+4Ch]
0x140237a5e  jmp     short loc_140237A63
0x140237a60  mov     eax, r15d
0x140237a63  test    al, 1
0x140237a65  jz      short loc_140237A8D
0x140237a67  mov     al, cs:NtfsStatusDebugFlags
0x140237a6d  test    al, al
0x140237a6f  jz      short loc_140237A83
0x140237a71  mov     r8d, 0A27F2h
0x140237a77  mov     edx, 0C000000Dh
0x140237a7c  xor     ecx, ecx
0x140237a7e  call    NtfsStatusTraceAndDebugInternal
0x140237a83  mov     eax, 0C000000Dh
0x140237a88  jmp     loc_14023A0C9
0x140237a8d  mov     ebx, 100h
0x140237a92  mov     r15d, 40h ; '@'
0x140237a98  mov     rcx, [rsi+0B0h]
0x140237a9f  test    dword ptr [rcx+10h], 1000h
0x140237aa6  jz      short loc_140237ADA
0x140237aa8  test    byte ptr [rcx+18h], 1
0x140237aac  jz      short loc_140237ADA
0x140237aae  test    [rcx+2], r15b
0x140237ab2  jnz     short loc_140237ADA
0x140237ab4  mov     al, cs:NtfsStatusDebugFlags
0x140237aba  test    al, al
0x140237abc  jz      short loc_140237AD0
0x140237abe  mov     edx, 0C0000121h
0x140237ac3  xor     ecx, ecx
0x140237ac5  mov     r8d, 0A27FEh
0x140237acb  call    NtfsStatusTraceAndDebugInternal
0x140237ad0  mov     eax, 0C0000121h
0x140237ad5  jmp     loc_14023A0C9
0x140237ada  mov     rdx, [r13+0B8h]
0x140237ae1  test    dword ptr [rdx+0B0h], 10000000h
0x140237aeb  jz      short loc_140237B6C
0x140237aed  mov     rax, [rsi+0B8h]
0x140237af4  mov     [rsp+348h+CompletionRoutine], rax
0x140237af9  mov     r9d, 1
0x140237aff  mov     r8d, r9d
0x140237b02  mov     rcx, rdi
0x140237b05  call    TxfGetCurrentFileInfo
0x140237b0a  bt      eax, 0Ah
0x140237b0e  jnb     short loc_140237B6C
0x140237b10  mov     rax, [rsi+0B8h]
0x140237b17  mov     [rsp+348h+CompletionRoutine], rax
0x140237b1c  mov     r9d, 1
0x140237b22  xor     r8d, r8d
0x140237b25  mov     rdx, [rsi+60h]
0x140237b29  mov     rcx, rdi
0x140237b2c  call    TxfGetCurrentFileInfo
0x140237b31  mov     ecx, eax
0x140237b33  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x140237b3a  nop     dword ptr [rax+rax+00h]
0x140237b3f  xor     r9d, r9d
0x140237b42  test    al, al
0x140237b44  jnz     short loc_140237B6F
0x140237b46  mov     al, cs:NtfsStatusDebugFlags
0x140237b4c  test    al, al
0x140237b4e  jz      short loc_140237B62
0x140237b50  mov     edx, 0C0000281h
0x140237b55  xor     ecx, ecx
0x140237b57  mov     r8d, 0A2813h
0x140237b5d  call    NtfsStatusTraceAndDebugInternal
0x140237b62  mov     eax, 0C0000281h
0x140237b67  jmp     loc_14023A0C9
0x140237b6c  xor     r9d, r9d
0x140237b6f  mov     rcx, [r13+0B8h]
0x140237b76  test    [rcx+4], ebx
0x140237b79  jz      short loc_140237B81
0x140237b7b  cmp     r13, [r14+20h]
0x140237b7f  jnz     short loc_140237B96
0x140237b81  mov     eax, [rsp+348h+arg_38]
0x140237b88  add     eax, 0FFFFFF80h
0x140237b8b  test    eax, 0FFFFFFDFh
0x140237b90  jz      loc_140237CB1
0x140237b96  cmp     [rcx+0B0h], r9d
0x140237b9d  jge     short loc_140237BD1
0x140237b9f  mov     rcx, [rcx+140h]
0x140237ba6  mov     edx, 4
0x140237bab  mov     eax, edx
0x140237bad  lock cmpxchg [rcx+84h], edx
0x140237bb5  test    eax, eax
0x140237bb7  jnz     short loc_140237BD1
0x140237bb9  xor     r8d, r8d
0x140237bbc  mov     rdx, r12
0x140237bbf  xor     ecx, ecx
0x140237bc1  call    TxfConvertMungedNameToTxfFileId
0x140237bc6  xor     r9d, r9d
0x140237bc9  test    eax, eax
0x140237bcb  jns     loc_140237CB1
0x140237bd1  mov     eax, [rdi+10h]
0x140237bd4  bt      rax, 14h
0x140237bd9  jb      loc_140237C8C
0x140237bdf  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x140237be6  test    al, 20h
0x140237be8  jz      loc_140237C8C
0x140237bee  mov     r11, [r13+0B8h]
0x140237bf5  mov     rbx, [r11+60h]
0x140237bf9  mov     rdx, [rbx+0F8h]
0x140237c00  movzx   eax, word ptr [rdx+6]
0x140237c04  cmp     ax, r15w
0x140237c08  ja      short loc_140237C0E
0x140237c0a  test    al, 1
0x140237c0c  jz      short loc_140237C11
0x140237c0e  mov     eax, r9d
0x140237c11  mov     rcx, [r11+140h]
0x140237c18  add     rdx, 20h ; ' '
0x140237c1c  movzx   r9d, ax
0x140237c20  shr     r9d, 1
0x140237c23  movzx   r10d, word ptr [rbx+1EC0h]
0x140237c2b  shr     r10d, 1
0x140237c2e  mov     r8, gs:188h
0x140237c37  mov     eax, [rsp+348h+arg_38]
0x140237c3e  mov     dword ptr [rsp+348h+var_2E8], eax
0x140237c42  mov     eax, [rcx+84h]
0x140237c48  mov     dword ptr [rsp+348h+var_2F0], eax
0x140237c4c  mov     eax, [r11+4]
0x140237c50  mov     dword ptr [rsp+348h+var_2F8], eax
0x140237c54  mov     rax, [r11+8]
0x140237c58  mov     qword ptr [rsp+348h+var_300], rax
0x140237c5d  mov     [rsp+348h+ReparseBuffer], r11
0x140237c62  mov     qword ptr [rsp+348h+BufferLength], rdx
0x140237c67  mov     dword ptr [rsp+348h+FileOffset], r9d
0x140237c6c  mov     rax, [rbx+1EC8h]
0x140237c73  mov     [rsp+348h+PostIrpRoutine], rax
0x140237c78  mov     dword ptr [rsp+348h+CompletionRoutine], r10d
0x140237c7d  mov     r9, rbx
0x140237c80  lea     rdx, create_c10289
0x140237c87  call    McTemplateU0ppwwpiddd_EtwWriteTransfer
0x140237c8c  mov     al, cs:NtfsStatusDebugFlags
  ... truncated ...
```
