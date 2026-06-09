# NtfsWriteRawEncrypted

- ea: `0x140280d1c`
- end: `0x140282a94`
- name: `NtfsWriteRawEncrypted`
- size: `7544`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1401f58e0`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d510`
- `0x14000eaa0`
- `0x14001e810`
- `0x140021910`
- `0x14002b680`
- `0x140030418`
- `0x140037db4`
- `0x14003ebc4`
- `0x140041d28`
- `0x14004a274`
- `0x140059330`
- `0x140059740`
- `0x1400bdce0`
- `0x1400bdd18`
- `0x1400bdd54`
- `0x1400bdd90`
- `0x14012c23c`
- `0x14013c320`
- `0x1401403d0`
- `0x140150c10`
- `0x140150cd0`
- `0x140151da4`
- `0x14015ec88`
- `0x140160c30`
- `0x1401623c0`
- `0x1401c0130`
- `0x1401c0904`
- `0x140280d1c`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140281b25`
- `ntoskrnl!IoFreeIrp` at `0x140281bb9`
- `ntoskrnl!IoFreeIrp` at `0x140281b25`
- `ntoskrnl!IoFreeIrp` at `0x140281bb9`
- `ntoskrnl!IoAllocateMdl` at `0x140281b0d`
- `ntoskrnl!IoAllocateMdl` at `0x140281b0d`
- `ntoskrnl!MmProbeAndLockPages` at `0x140281b66`
- `ntoskrnl!MmProbeAndLockPages` at `0x140281b66`
- `ntoskrnl!IoFreeMdl` at `0x140281ba2`
- `ntoskrnl!IoFreeMdl` at `0x140281ba2`
- `ntoskrnl!MmMdlPageContentsState` at `0x140281b7a`
- `ntoskrnl!MmMdlPageContentsState` at `0x140281b7a`
- `ntoskrnl!IofCallDriver` at `0x140281cb6`
- `ntoskrnl!IofCallDriver` at `0x140281cb6`
- `ntoskrnl!ProbeForRead` at `0x1402811d7`
- `ntoskrnl!ProbeForRead` at `0x1402811d7`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140281ab3`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140281ab3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140281ce2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140281ce2`
- `ntoskrnl!KeInitializeEvent` at `0x140280db9`
- `ntoskrnl!KeInitializeEvent` at `0x140280db9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028197b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028266b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc4e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028197b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028266b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc4e9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402819c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402819c5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140281552`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140281552`
- `ntoskrnl!ExReleaseResourceLite` at `0x140282650`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc4ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x140282650`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc4ce`
- `ntoskrnl!CcFlushCache` at `0x1402816a1`
- `ntoskrnl!CcFlushCache` at `0x1402816a1`

## pseudocode

```c
__int64 __fastcall NtfsWriteRawEncrypted(_DWORD *a1, __int64 a2)
{
  unsigned int v4; // r14d
  signed __int64 v5; // rbx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rcx
  struct _FILE_OBJECT *v9; // rax
  char *FsContext; // r15
  unsigned __int8 *FsContext2; // r10
  __int64 v12; // r11
  int v13; // eax
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // r8
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rdx
  unsigned __int16 v21; // r8
  SIZE_T v22; // rdx
  union _LARGE_INTEGER *v23; // r9
  DWORD ULongFromUser; // eax
  DWORD LowPart; // eax
  LONG HighPart; // eax
  unsigned __int16 UShortFromUser; // ax
  char UCharFromUser; // r12
  union _LARGE_INTEGER v29; // rax
  char v30; // al
  unsigned __int16 v31; // ax
  __int64 v32; // rax
  union _LARGE_INTEGER *v33; // rdi
  DWORD v34; // eax
  unsigned int v35; // eax
  DWORD v36; // eax
  char v37; // di
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // r9
  unsigned int i; // eax
  __int64 v42; // rcx
  __int16 v43; // cx
  __int64 v44; // r8
  int v45; // edi
  unsigned __int16 j; // r12
  __int64 v47; // rcx
  union _LARGE_INTEGER *v48; // rdx
  char *v49; // rax
  char v50; // r8
  int v51; // eax
  int v52; // eax
  __int64 v53; // rax
  __int64 v54; // r8
  unsigned __int16 v55; // dx
  LONGLONG QuadPart; // r8
  char v57; // di
  unsigned int v58; // ebx
  char *v59; // rbx
  unsigned int v60; // ecx
  ULONG v61; // r14d
  unsigned __int64 v62; // r12
  __int64 v63; // rdi
  unsigned __int64 v64; // r8
  unsigned __int64 PoolWithTag; // r9
  PIRP v66; // rax
  IRP *v67; // rdi
  struct _MDL *Mdl; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  __int64 v70; // r8
  NTSTATUS Status; // eax
  unsigned int v72; // eax
  __int16 v73; // ax
  unsigned int v74; // ebx
  __int64 v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rdi
  LONGLONG v78; // rbx
  _DWORD *v79; // r10
  LONGLONG v80; // rcx
  signed __int64 v81; // r9
  signed __int64 v82; // r8
  LONGLONG v83; // r8
  signed __int64 v84; // rdx
  __int64 v85; // rcx
  __int64 v86; // rdi
  int v87; // ecx
  __int64 v88; // rdx
  __int64 v89; // rcx
  LONGLONG v90; // r9
  LONGLONG v91; // rdi
  __int64 v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rbx
  __int64 v95; // r12
  LONGLONG v96; // rbx
  signed __int64 v97; // rcx
  signed __int64 v98; // r9
  signed __int64 v99; // r8
  __int64 v100; // rcx
  __int64 v101; // rdi
  signed __int64 v102; // rbx
  int v103; // r8d
  signed __int64 v104; // rcx
  signed __int64 v105; // rdx
  signed __int64 v106; // rax
  int v107; // r8d
  signed __int64 v108; // r9
  signed __int64 v109; // rdx
  int v110; // ecx
  signed __int64 v111; // r8
  signed __int64 v112; // rdx
  __int64 v113; // rcx
  __int64 v114; // rcx
  unsigned int v115; // eax
  unsigned int v116; // ebx
  unsigned int v117; // eax
  unsigned int v118; // ebx
  NTSTATUS v119; // [rsp+74h] [rbp-164h] BYREF
  char v120; // [rsp+78h] [rbp-160h]
  char v121; // [rsp+79h] [rbp-15Fh]
  unsigned __int16 v122; // [rsp+7Ah] [rbp-15Eh]
  unsigned __int16 v123; // [rsp+7Ch] [rbp-15Ch]
  DWORD v124; // [rsp+80h] [rbp-158h]
  char v125; // [rsp+84h] [rbp-154h]
  char v126; // [rsp+85h] [rbp-153h]
  union _LARGE_INTEGER StartingOffset; // [rsp+88h] [rbp-150h] BYREF
  union _LARGE_INTEGER *v128; // [rsp+90h] [rbp-148h]
  unsigned int v129; // [rsp+98h] [rbp-140h]
  int v130; // [rsp+9Ch] [rbp-13Ch]
  unsigned int v131; // [rsp+A0h] [rbp-138h]
  __int64 v132; // [rsp+A8h] [rbp-130h]
  __int64 v133; // [rsp+B0h] [rbp-128h]
  unsigned __int16 v134; // [rsp+B8h] [rbp-120h]
  char v135; // [rsp+BCh] [rbp-11Ch]
  unsigned int v136; // [rsp+C0h] [rbp-118h]
  int v137; // [rsp+C4h] [rbp-114h]
  __int64 v138; // [rsp+C8h] [rbp-110h]
  void *v139; // [rsp+D0h] [rbp-108h]
  unsigned int v140; // [rsp+D8h] [rbp-100h]
  int v141; // [rsp+DCh] [rbp-FCh]
  ULONG v142; // [rsp+E0h] [rbp-F8h]
  _QWORD *v143; // [rsp+E8h] [rbp-F0h]
  union _LARGE_INTEGER v144; // [rsp+F0h] [rbp-E8h]
  PVOID P; // [rsp+F8h] [rbp-E0h]
  struct _FILE_OBJECT *v146; // [rsp+100h] [rbp-D8h]
  unsigned __int16 v147; // [rsp+108h] [rbp-D0h]
  LONG v148; // [rsp+10Ch] [rbp-CCh]
  DWORD v149; // [rsp+110h] [rbp-C8h]
  PIRP Irp; // [rsp+118h] [rbp-C0h]
  unsigned __int64 v151; // [rsp+120h] [rbp-B8h]
  __int64 v152; // [rsp+128h] [rbp-B0h] BYREF
  __int64 v153; // [rsp+130h] [rbp-A8h]
  __int64 v154; // [rsp+138h] [rbp-A0h]
  __int64 v155; // [rsp+140h] [rbp-98h]
  __int64 v156; // [rsp+148h] [rbp-90h]
  __int64 v157; // [rsp+150h] [rbp-88h]
  union _LARGE_INTEGER *v158; // [rsp+158h] [rbp-80h]
  ULONG v159; // [rsp+160h] [rbp-78h]
  union _LARGE_INTEGER v160; // [rsp+168h] [rbp-70h]
  __int64 v161; // [rsp+170h] [rbp-68h]
  struct _KEVENT Object; // [rsp+178h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+190h] [rbp-48h] BYREF
  char v166; // [rsp+1F0h] [rbp+18h]
  signed __int64 v167; // [rsp+1F8h] [rbp+20h]
  char v168; // [rsp+1F8h] [rbp+20h]

  StartingOffset.QuadPart = 0;
  v160.QuadPart = 0;
  v149 = 0;
  v148 = 0;
  v137 = 0;
  v134 = 0;
  v125 = 0;
  memset(&Object, 0, sizeof(Object));
  IoStatusBlock = 0;
  v119 = 0;
  v126 = 0;
  v4 = 0;
  v5 = 0;
  v166 = *(_BYTE *)(a2 + 64);
  a1[3] |= 1u;
  KeInitializeEvent(&Object, SynchronizationEvent, 0);
  v8 = *(_QWORD *)(a2 + 184);
  v9 = *(struct _FILE_OBJECT **)(v8 + 48);
  v146 = v9;
  FsContext = (char *)v9->FsContext;
  if ( FsContext )
  {
    FsContext2 = (unsigned __int8 *)v9->FsContext2;
    v143 = FsContext2;
    v12 = *((_QWORD *)FsContext + 24);
    v132 = v12;
    v13 = *(_DWORD *)(v12 + 4);
    if ( (v13 & 1) == 0 && (!FsContext2 || FsContext2[88] != 4 || (v13 & 2) == 0) )
    {
      v115 = NtfsRaiseStatusInternal((_DWORD)a1, -1073741202, 0, 0, 0);
      v116 = v115;
      if ( NtfsStatusDebugFlags
        && v115
        && v115 != 294
        && v115 - 298 > 1
        && v115 < 0xFFFFFFED
        && v115 != -1073741802
        && v115 + 2147483643 > 1
        && v115 != -1073741807
        && v115 != 259
        && v115 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(0, v115, 1199389);
      }
      v119 = v116;
      if ( NtfsStatusDebugFlags
        && v116
        && v116 != 294
        && v116 - 298 > 1
        && v116 < 0xFFFFFFED
        && v116 != -1073741802
        && v116 + 2147483643 > 1
        && v116 != -1073741807
        && v116 != 259
        && v116 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, v116, 1199394);
      }
      v117 = NtfsRaiseStatusInternal((_DWORD)a1, v116, 0, 0, 1199394);
      v118 = v117;
      if ( NtfsStatusDebugFlags
        && v117
        && v117 != 294
        && v117 - 298 > 1
        && v117 < 0xFFFFFFED
        && v117 != -1073741802
        && v117 + 2147483643 > 1
        && v117 != -1073741807
        && v117 != 259
        && v117 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(0, v117, 1198533);
      }
      if ( NtfsStatusDebugFlags
        && v118
        && v118 != 294
        && v118 - 298 > 1
        && v118 < 0xFFFFFFED
        && v118 != -1073741802
        && v118 + 2147483643 > 1
        && v118 != -1073741807
        && v118 != 259
        && v118 != -1073741608 )
      {
        NtfsStatusTraceAndDebugInternal(a1, v118, 1198540);
      }
      return NtfsRaiseStatusInternal((_DWORD)a1, v118, 0, 0, 1198540);
    }
    if ( !FsContext2 )
    {
LABEL_10:
      v15 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1198326);
      LOBYTE(v7) = a2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v7, 0);
      if ( !NtfsStatusDebugFlags )
        return v15;
      v16 = 1198327;
LABEL_14:
      NtfsStatusTraceAndDebugInternal(0, v15, v16);
      return v15;
    }
    v133 = *((_QWORD *)FsContext + 23);
    v157 = v133;
    v14 = FsContext2[88];
  }
  else
  {
    v12 = 0;
    v132 = 0;
    FsContext2 = 0;
    v143 = 0;
    v133 = 0;
    v157 = 0;
    v14 = 1;
  }
  if ( v14 != 2 )
    goto LABEL_10;
  if ( (*(_DWORD *)(v12 + 4) & 0x2000000) != 0 )
  {
    v15 = -1073741662;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225634LL, 1198336);
    LOBYTE(v7) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225634LL, v7, 0);
    if ( !NtfsStatusDebugFlags )
      return v15;
    v16 = 1198337;
    goto LABEL_14;
  }
  a1[68] = *((_DWORD *)FsContext2 + 25);
  if ( !_bittest16((const signed __int16 *)FsContext + 230, 0xEu) )
  {
    v4 = -1073740633;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226663LL, 1198353);
    LOBYTE(v7) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221226663LL, v7, 0);
    if ( !NtfsStatusDebugFlags )
      return v4;
    v18 = 1198354;
LABEL_26:
    NtfsStatusTraceAndDebugInternal(0, v4, v18);
    return v4;
  }
  v19 = *((unsigned __int16 *)FsContext2 + 52);
  if ( (v19 & 0x12) == 0 )
  {
    if ( (a1[4] & 0x100000) == 0 && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      v20 = *(_QWORD *)(v12 + 248);
      v21 = *(_WORD *)(v20 + 6);
      if ( v21 > 0x40u || (v21 & 1) != 0 )
        v21 = 0;
      McTemplateU0ppwwpiwd_EtwWriteTransfer(
        v132,
        (unsigned int)fsctrl_c18715,
        (unsigned int)KeGetCurrentThread(),
        v132,
        *(_WORD *)(v12 + 7872) >> 1,
        *(_QWORD *)(v132 + 7880),
        v21 >> 1,
        v20 + 32,
        v133,
        *(_QWORD *)(v133 + 8),
        *((_WORD *)FsContext2 + 8) >> 1,
        v143[3],
        v19);
    }
    v15 = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225506LL, 1198378);
    LOBYTE(v19) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225506LL, v19, 0);
    if ( !NtfsStatusDebugFlags )
      return v15;
    v16 = 1198379;
    goto LABEL_14;
  }
  if ( (*(_DWORD *)(v12 + 24) & 0x40000) != 0 )
  {
    v15 = -1073740646;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226650LL, 1198388);
    LOBYTE(v19) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221226650LL, v19, 0);
    if ( !NtfsStatusDebugFlags )
      return v15;
    v16 = 1198389;
    goto LABEL_14;
  }
  v22 = *(unsigned int *)(v8 + 16);
  v136 = v22;
  v141 = v22;
  if ( (unsigned int)v22 < 0x20 )
  {
    v15 = -1073741789;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225507LL, 1198405);
    LOBYTE(v19) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225507LL, v19, 0);
    if ( !NtfsStatusDebugFlags )
      return v15;
    v16 = 1198406;
    goto LABEL_14;
  }
  v23 = *(union _LARGE_INTEGER **)(v8 + 32);
  v128 = v23;
  v158 = v23;
  if ( *(_DWORD *)(v8 - 64) == -1 )
  {
    v121 = 0;
    *(_DWORD *)(v8 - 64) = 0;
    *(_DWORD *)(v8 - 56) = *((_DWORD *)FsContext + 10);
    *(_DWORD *)(v8 - 48) = *((_DWORD *)FsContext + 11);
  }
  else
  {
    v121 = 1;
    LODWORD(v167) = *(_DWORD *)(v8 - 56);
    HIDWORD(v167) = *(_DWORD *)(v8 - 48);
    v5 = v167;
  }
  if ( *(_BYTE *)(a2 + 64) )
  {
    ProbeForRead(v23, v22, 1u);
    v23 = v128;
  }
  if ( v166 )
  {
    ULongFromUser = RtlReadULongFromUser(&v23[1]);
    v23 = v128;
  }
  else
  {
    ULongFromUser = v23[1].LowPart;
  }
  v129 = ULongFromUser;
  v137 = ULongFromUser;
  if ( v166 )
  {
    LowPart = RtlReadULongFromUser(&v23[2]);
    v23 = v128;
  }
  else
  {
    LowPart = v23[2].LowPart;
  }
  v124 = LowPart;
  v149 = LowPart;
  if ( v166 )
  {
    HighPart = RtlReadULongFromUser((char *)&v23[1].QuadPart + 4);
    v23 = v128;
  }
  else
  {
    HighPart = v23[1].HighPart;
  }
  v131 = HighPart;
  v148 = HighPart;
  if ( v166 )
  {
    UShortFromUser = RtlReadUShortFromUser((char *)&v23[3].u.LowPart + 2);
    v23 = v128;
  }
  else
  {
    UShortFromUser = HIWORD(v23[3].u.LowPart);
  }
  v122 = UShortFromUser;
  v134 = UShortFromUser;
  if ( v166 )
  {
    UCharFromUser = RtlReadUCharFromUser((char *)&v23[3].LowPart + 1);
    v23 = v128;
  }
  else
  {
    UCharFromUser = BYTE1(v23[3].LowPart);
  }
  v135 = UCharFromUser;
  LOBYTE(v6) = v166;
  if ( v166 )
  {
    v29.QuadPart = RtlReadULong64FromUser(v23);
    v23 = v128;
    LOBYTE(v6) = v166;
  }
  else
  {
    v29 = *v23;
  }
  v144 = v29;
  StartingOffset = v29;
  v160 = v29;
  if ( (_BYTE)v6 )
  {
    v30 = RtlReadUCharFromUser((char *)&v23[2].QuadPart + 6);
    v23 = v128;
    LOBYTE(v6) = v166;
  }
  else
  {
    v30 = BYTE6(v23[2].QuadPart);
  }
  v168 = v30;
  v125 = v30;
  if ( (_BYTE)v6 )
  {
    RtlReadUCharFromUser((char *)&v23[2].QuadPart + 7);
    v23 = v128;
    LOBYTE(v6) = v166;
  }
  if ( (_BYTE)v6 )
  {
    v31 = RtlReadUShortFromUser((char *)&v23[2].QuadPart + 4);
    v23 = v128;
    LOBYTE(v6) = v166;
  }
  else
  {
    v31 = WORD2(v23[2].QuadPart);
  }
  v123 = v31;
  v147 = v31;
  v32 = 4 * (unsigned int)v122 + 28;
  if ( (unsigned int)v32 <= v129 && (unsigned int)v32 <= v136 )
  {
    if ( v32 + 16 <= (unsigned __int64)v129
      && v32 + 16 <= (unsigned __int64)v136
      && ((v33 = (union _LARGE_INTEGER *)((char *)v23 + v32), !(_BYTE)v6)
        ? (v34 = v33->LowPart)
        : (v34 = RtlReadULongFromUser((char *)v23 + v32), LOBYTE(v6) = v166),
          v34 == ExtendedEncryptedDataInfoSignature) )
    {
      if ( (_BYTE)v6 )
      {
        v35 = RtlReadULongFromUser((char *)&v33->QuadPart + 4);
        LOBYTE(v6) = v166;
      }
      else
      {
        v35 = v33->HighPart;
      }
      if ( v35 < 0x10 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 3221226666LL, 1198520);
        LOBYTE(v23) = a2 != 0;
        NtfsExtendedCompleteRequestInternal(a1, a2, 3221226666LL, v23, 0);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3221226666LL, 1198521);
        return 3221226666LL;
      }
      if ( (_BYTE)v6 )
        LOBYTE(v36) = RtlReadULongFromUser(&v33[1]);
      else
        v36 = v33[1].LowPart;
      v37 = v119;
      if ( (v36 & 1) != 0 )
        v37 = 1;
      v126 = v37;
    }
    else
    {
      v37 = v119;
    }
    if ( (unsigned __int8)(UCharFromUser - 1) > 1u )
    {
      v15 = -1073741637;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221225659LL, 1198557);
      LOBYTE(v23) = a2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, a2, 3221225659LL, v23, 0);
      if ( !NtfsStatusDebugFlags )
        return v15;
      v16 = 1198558;
      goto LABEL_14;
    }
    if ( v124 > v131 || v123 || !v122 || (v138 = 0, v139 = 0, P = 0, v142 = 0, v120 = 0, v129 > v136) )
    {
      v4 = -1073740630;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 3221226666LL, 1198566);
      LOBYTE(v23) = a2 != 0;
      NtfsExtendedCompleteRequestInternal(a1, a2, 3221226666LL, v23, 0);
      if ( !NtfsStatusDebugFlags )
        return v4;
      v18 = 1198567;
      goto LABEL_26;
    }
    v38 = v133;
    v156 = v133 + 328;
    v39 = *(_QWORD *)(v133 + 328);
    if ( v39 )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v39 + 136), 1u);
      v120 = 1;
      if ( (*(_DWORD *)(*(_QWORD *)v156 + 4LL) & 1) != 0 || (unsigned __int8)TxfIsCurrentHandleInTransaction(a1, v143) )
      {
        v4 = -1072103362;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 3222863934LL, 1198606);
        v119 = -1072103362;
LABEL_318:
        if ( v120 )
          ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)v156 + 136LL));
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( NtfsStatusDebugFlags
          && v4
          && v4 != 294
          && v4 - 298 > 1
          && v4 < 0xFFFFFFED
          && v4 != -1073741802
          && v4 + 2147483643 > 1
          && v4 != -1073741807
          && v4 != 259
          && v4 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, v4, 1199412);
        }
        LOBYTE(v40) = a2 != 0;
        NtfsExtendedCompleteRequestInternal(a1, a2, v4, v40, (v4 & 0x80000000) == 0);
        return v4;
      }
      v38 = v133;
    }
    LOBYTE(v6) = 1;
    if ( (unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, v38, v6) )
    {
      v140 = 0;
      for ( i = 0; ; ++i )
      {
        v140 = i;
        if ( i >= 2 )
          break;
        v42 = *(_QWORD *)&a1[2 * i + 12];
        if ( !v42 || v42 == v133 )
        {
          *(_QWORD *)&a1[2 * i + 12] = v133;
          break;
        }
      }
    }
    NtfsAcquireExclusiveScbEx(a1, FsContext, 0);
    SetFlagInterlocked(FsContext + 200, 0x1000000);
    v43 = *((_WORD *)FsContext + 230);
    if ( (v43 & 0x4000) == 0 )
    {
      v4 = -1073740633;
      if ( NtfsStatusDebugFlags )
      {
        v44 = 1198638;
        goto LABEL_316;
      }
      goto LABEL_317;
    }
    if ( v37 && v43 >= 0 )
      NtfsChangeAttributeCompression((int)a1, v43 | 0x8000);
    CcFlushCache((PSECTION_OBJECT_POINTERS)(*((_QWORD *)FsContext + 36) + 16LL), 0, 0, (PIO_STATUS_BLOCK)(a2 + 48));
    NtfsNormalizeAndCleanupTransaction(a1, a2 + 48);
    if ( !(unsigned __int8)NtfsPurgeCacheSection(a1, FsContext, 0, 0, 0) )
    {
      v4 = -1073741797;
      if ( NtfsStatusDebugFlags )
      {
        v44 = 1198661;
        goto LABEL_316;
      }
      goto LABEL_317;
    }
    if ( StartingOffset.QuadPart > *((_QWORD *)FsContext + 4) || StartingOffset.QuadPart < 0 )
    {
      v4 = -1073740632;
      if ( NtfsStatusDebugFlags )
      {
        v44 = 1198674;
        goto LABEL_316;
      }
LABEL_317:
      v119 = v4;
      goto LABEL_318;
    }
    v45 = 0;
    v130 = 0;
    for ( j = 0; j < v122; ++j )
    {
      v47 = j;
      v48 = v128;
      v49 = (char *)&v128->QuadPart + 4 * j;
      v50 = v166;
      if ( v166 )
      {
        v51 = RtlReadULongFromUser(v49 + 28);
        v47 = j;
        v48 = v128;
        v50 = v166;
      }
      else
      {
        v51 = *((_DWORD *)v49 + 7);
      }
      if ( v51 )
      {
        v53 = (__int64)v48 + 4 * v47;
        if ( v50 )
          v52 = RtlReadULongFromUser(v53 + 28);
        else
          v52 = *(_DWORD *)(v53 + 28);
      }
      else
      {
        v52 = 1 << v168;
      }
      v45 += v52;
      v130 = v45;
    }
    if ( v124 != v45 )
    {
      if ( !v121 )
        v5 = *((_QWORD *)FsContext + 5);
      if ( v144.QuadPart + v124 < v5 )
      {
        v4 = -1073740631;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_317;
        v54 = 1198721;
        goto LABEL_151;
      }
    }
    NtfsCheckpointCurrentTransaction(a1);
    NtfsFreeSnapshotsForFcb(a1, v133);
    v55 = 0;
    QuadPart = StartingOffset.QuadPart;
    v40 = 0;
    while ( 1 )
    {
      v123 = v55;
      if ( v55 >= v122 )
      {
        if ( (v4 & 0x80000000) != 0 )
          goto LABEL_318;
        v101 = v131;
        if ( v131 == v40 && v124 >= v40 )
          goto LABEL_318;
        v102 = v144.QuadPart + v124;
        NtfsSnapshotScb(a1, FsContext);
        v103 = *((_DWORD *)FsContext + 50);
        if ( (v103 & 0x20000) != 0 )
        {
          v104 = v101 + v144.QuadPart;
          if ( *((_QWORD *)FsContext + 4) < v101 + v144.QuadPart )
          {
            v105 = *((_QWORD *)FsContext + 58);
            if ( v104 >= v105 )
              v104 = *((_QWORD *)FsContext + 58);
            v106 = *((_QWORD *)FsContext + 5);
            if ( v104 > v106 )
            {
              if ( (v103 & 0x200) != 0 )
              {
                v105 = *((_QWORD *)FsContext + 58);
                v106 = *((_QWORD *)FsContext + 5);
              }
              v107 = *((_DWORD *)FsContext + 50);
              if ( (v107 & 0x20000) != 0 )
              {
                if ( v105 < v104 )
                  goto LABEL_294;
                if ( v106 <= v104 )
                  goto LABEL_295;
                if ( !*(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) || v104 == 0x7FFFFFFFFFFFFFFFLL )
                {
LABEL_294:
                  *((_QWORD *)FsContext + 58) = v104;
                }
                else
                {
                  v108 = (v104 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                  if ( v108 < v105 )
                    *((_QWORD *)FsContext + 58) = v108;
                }
              }
LABEL_295:
              *((_QWORD *)FsContext + 5) = v104;
            }
          }
        }
        *((_QWORD *)FsContext + 4) = v101 + v144.QuadPart;
        v109 = *((_QWORD *)FsContext + 5);
        if ( v102 < v109 )
        {
          if ( (*((_DWORD *)FsContext + 50) & 0x200) != 0 )
            v109 = *((_QWORD *)FsContext + 5);
          v110 = *((_DWORD *)FsContext + 50);
          if ( (v110 & 0x20000) != 0 )
          {
            v111 = *((_QWORD *)FsContext + 58);
            if ( v111 < v102 )
              goto LABEL_306;
            if ( v109 <= v102 )
              goto LABEL_307;
            if ( !*(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) || v102 == 0x7FFFFFFFFFFFFFFFLL )
            {
LABEL_306:
              *((_QWORD *)FsContext + 58) = v102;
            }
            else
            {
              v112 = (v102 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v112 < v111 )
                *((_QWORD *)FsContext + 58) = v112;
            }
          }
LABEL_307:
          *((_QWORD *)FsContext + 5) = v102;
        }
        NtfsWriteFileSizes((_DWORD)a1, (_DWORD)FsContext, 0, 0, 1, 1);
        v113 = *((_QWORD *)FsContext + 5);
        if ( *((_QWORD *)FsContext + 58) > v113 && (FsContext[460] || (*((_DWORD *)FsContext + 128) & 1) != 0) )
          *((_QWORD *)FsContext + 58) = v113;
        v114 = *((_QWORD *)FsContext + 35);
        if ( v114 )
          NtfsSetCcFileSizes(v114, FsContext, FsContext + 24);
        goto LABEL_318;
      }
      v40 = v124;
      if ( v124
        || (v57 = v168, *((_DWORD *)FsContext + 113) > (unsigned int)(1 << v168))
        || *((__int16 *)FsContext + 230) >= 0 )
      {
        v59 = (char *)&v128->QuadPart + 4 * v55;
        if ( v166 )
        {
          v58 = RtlReadULongFromUser(v59 + 28);
          v40 = v124;
        }
        else
        {
          v58 = *((_DWORD *)v59 + 7);
        }
        v130 = v58;
        v57 = v168;
        QuadPart = StartingOffset.QuadPart;
      }
      else
      {
        v58 = 0;
        v130 = 0;
      }
      if ( !v58 )
        break;
      if ( (_DWORD)v40 )
      {
        v60 = v129 + v58;
        if ( v129 + v58 < v129 )
        {
          v137 = -1;
LABEL_202:
          v4 = -1073740630;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_317;
          v54 = 1198791;
          goto LABEL_151;
        }
        v61 = v58;
        v62 = (unsigned __int64)v128 + v129;
        v129 += v58;
        v137 = v60;
        if ( v60 > v136 )
          goto LABEL_202;
        v63 = v132;
        v64 = *(unsigned int *)(v132 + 364);
        if ( v58 % (unsigned int)v64 || v62 % v64 )
        {
          v61 = -(int)v64 & (v58 + v64 - 1);
          if ( v61 < v58 )
          {
            v4 = -1073740630;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_317;
            v54 = 1198823;
LABEL_151:
            NtfsStatusTraceAndDebugInternal(0, v4, v54);
            goto LABEL_317;
          }
          PoolWithTag = (unsigned __int64)v139;
          if ( !v139 )
            goto LABEL_176;
          if ( v142 < v61 )
          {
            ExFreePoolWithTag(P, 0);
            PoolWithTag = 0;
            v139 = 0;
            v151 = 0;
            P = 0;
          }
          if ( !PoolWithTag )
          {
LABEL_176:
            PoolWithTag = (unsigned __int64)ExAllocatePoolWithTag(
                                              (POOL_TYPE)(PoolType | 0x10),
                                              v61 + *(_DWORD *)(v63 + 364) - 1,
                                              0x6646744Eu);
            v139 = (void *)PoolWithTag;
            P = (PVOID)PoolWithTag;
            v151 = PoolWithTag;
            v142 = v61;
            v159 = v61;
            if ( PoolWithTag % *(unsigned int *)(v63 + 364) )
            {
              PoolWithTag = -*(_DWORD *)(v63 + 364) & (*(_DWORD *)(v63 + 364) - 1 + PoolWithTag);
              v139 = (void *)PoolWithTag;
              v151 = PoolWithTag;
            }
          }
          if ( v166 )
            RtlCopyFromUser((void *)PoolWithTag, (void *)v62, v58);
          else
            RtlCopyVolatileMemory((void *)PoolWithTag, (const void *)v62, v58);
          v62 = (unsigned __int64)v139;
          memset((char *)v139 + v58, 0, v61 - v58);
          v63 = v132;
        }
        v66 = IoBuildSynchronousFsdRequest(
                4u,
                *(PDEVICE_OBJECT *)(*(_QWORD *)(v63 + 248) + 8LL),
                (PVOID)v62,
                v61,
                &StartingOffset,
                &Object,
                &IoStatusBlock);
        v67 = v66;
        Irp = v66;
        if ( !v66 )
        {
          v4 = -1073741670;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_317;
          v54 = 1198861;
          goto LABEL_151;
        }
        if ( (void *)v62 == v139 )
        {
          Mdl = IoAllocateMdl((PVOID)v62, v61, 0, 0, 0);
          v67->MdlAddress = Mdl;
          if ( !Mdl )
          {
            IoFreeIrp(v67);
            Irp = 0;
            v4 = -1073741670;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_317;
            v54 = 1198874;
            goto LABEL_151;
          }
          MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
          MmMdlPageContentsState(v67->MdlAddress, 1);
          v67->UserBuffer = 0;
          v67->RequestorMode = 0;
        }
        else
        {
          v66->UserBuffer = (PVOID)v62;
          v66->RequestorMode = *(_BYTE *)(a2 + 64);
        }
        v67->Flags |= 5u;
        CurrentStackLocation = v67->Tail.Overlay.CurrentStackLocation;
        v70 = v132;
        CurrentStackLocation[-1].DeviceObject = *(PDEVICE_OBJECT *)(*(_QWORD *)(v132 + 248) + 8LL);
        CurrentStackLocation[-1].Parameters.Read.ByteOffset = StartingOffset;
        CurrentStackLocation[-1].Parameters.Read.Length = v58;
        CurrentStackLocation[-1].FileObject = v146;
        v119 = IofCallDriver(*(PDEVICE_OBJECT *)(*(_QWORD *)(v70 + 248) + 8LL), v67);
        if ( v119 == 259 )
        {
          Status = KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
          v119 = Status;
          if ( !Status )
            Status = IoStatusBlock.Status;
          v119 = Status;
        }
        NtfsNormalizeAndCleanupTransaction(a1, &v119);
        v40 = v58 + v138;
        v138 = v40;
        v155 = v40;
        QuadPart = v58 + StartingOffset.QuadPart;
        StartingOffset.QuadPart = QuadPart;
        if ( v58 >= 1 << v168 || v131 <= v124 )
        {
          v72 = 0;
          v4 = v119;
        }
        else
        {
          v4 = v119;
          if ( *((__int16 *)FsContext + 230) >= 0 )
            v72 = v131 - v124;
          else
            v72 = (1 << v168) - v58;
        }
      }
      else
      {
        v72 = v58;
        v40 = v138;
      }
LABEL_243:
      v86 = v72;
      v154 = v72;
      if ( !v72 )
        goto LABEL_276;
      v152 = 0;
      v153 = 0;
      if ( *((__int16 *)FsContext + 230) >= 0 )
        v87 = *(_DWORD *)(v132 + 356);
      else
        v87 = *((_DWORD *)FsContext + 113);
      v88 = -v87;
      v89 = v87 - 1;
      v90 = v88 & (v89 + QuadPart);
      v91 = v88 & (QuadPart + v89 + v72);
      v92 = *((_QWORD *)FsContext + 24);
      LOBYTE(v89) = *(_BYTE *)(v92 + 488);
      v93 = *(unsigned int *)(v92 + 480);
      v161 = (v93 + *((_QWORD *)FsContext + 3)) >> v89;
      v94 = (v93 + v90) >> v89;
      v153 = v94;
      v95 = (v93 + v91) >> v89;
      NtfsPreloadAllocationInternal((_DWORD)a1, v95 - 1, 0);
      if ( *((__int16 *)FsContext + 230) < 0 )
      {
        if ( (unsigned __int8)NtfsIsRangeAllocated((_DWORD)FsContext, v94, v95, 0, (__int64)&v152)
          && v152 == (v154 + *(unsigned int *)(*((_QWORD *)FsContext + 24) + 480LL)) >> *(_BYTE *)(*((_QWORD *)FsContext + 24)
                                                                                                 + 488LL) )
        {
          goto LABEL_258;
        }
      }
      else if ( *((_QWORD *)FsContext + 3) >= v91 )
      {
        goto LABEL_258;
      }
      if ( *((__int16 *)FsContext + 230) >= 0 )
      {
        if ( v161 > v94 )
          v94 = v161;
        v153 = v94;
      }
      if ( v94 <= v95 )
      {
        NtfsDeleteAllocation((_DWORD)a1, v95, 1, 1);
        NtfsAddAllocation((_DWORD)a1, v95 - v94 + 1, 0, 0);
      }
LABEL_258:
      v86 = v154;
      v96 = v154 + StartingOffset.QuadPart;
      NtfsSnapshotScb(a1, FsContext);
      if ( v96 > *((_QWORD *)FsContext + 4) )
      {
        if ( (*((_DWORD *)FsContext + 50) & 0x20000) != 0 )
        {
          v97 = *((_QWORD *)FsContext + 58);
          if ( v96 < v97 )
            v97 = v96;
          if ( v97 > *((_QWORD *)FsContext + 5) )
          {
            if ( (*((_DWORD *)FsContext + 50) & 0x20000) == 0 )
              goto LABEL_271;
            v98 = *((_QWORD *)FsContext + 58);
            if ( v98 < v97 )
              goto LABEL_270;
            if ( *((_QWORD *)FsContext + 5) <= v97 )
              goto LABEL_271;
            if ( !*(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) || v97 == 0x7FFFFFFFFFFFFFFFLL )
            {
LABEL_270:
              *((_QWORD *)FsContext + 58) = v97;
            }
            else
            {
              v99 = (v97 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v99 < v98 )
                *((_QWORD *)FsContext + 58) = v99;
            }
LABEL_271:
            *((_QWORD *)FsContext + 5) = v97;
          }
        }
        *((_QWORD *)FsContext + 4) = v96;
      }
      NtfsWriteFileSizes((_DWORD)a1, (_DWORD)FsContext, 0, 0, 1, 1);
      v100 = *((_QWORD *)FsContext + 35);
      if ( v100 )
        NtfsSetCcFileSizes(v100, FsContext, FsContext + 24);
      NtfsCheckpointCurrentTransaction(a1);
      NtfsReleaseSharedResources(a1);
      NtfsFreeSnapshotsForFcb(a1, v133);
      v40 = v86 + v138;
      v138 = v40;
      v155 = v40;
      QuadPart = StartingOffset.QuadPart;
LABEL_276:
      QuadPart += v86;
      StartingOffset.QuadPart = QuadPart;
      v55 = v123 + 1;
    }
    v73 = *((_WORD *)FsContext + 230);
    if ( v73 >= 0 )
    {
      NtfsChangeAttributeCompression((int)a1, v73 | 0x8000);
      QuadPart = StartingOffset.QuadPart;
    }
    v74 = 1 << v57;
    v130 = 1 << v57;
    v75 = *((unsigned int *)FsContext + 113);
    if ( (1 << v57) % (unsigned int)v75 || QuadPart % v75 )
    {
      v4 = -1073740630;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_317;
      v44 = 1199073;
LABEL_316:
      NtfsStatusTraceAndDebugInternal(0, v4, v44);
      goto LABEL_317;
    }
    v76 = *((_QWORD *)FsContext + 3);
    if ( v76 && *((_QWORD *)FsContext + 4) != v76 )
      NtfsDeleteAllocation((_DWORD)a1, 0x7FFFFFFFFFFFFFFFLL, 1, 1);
    v77 = v74;
    NtfsAddSparseAllocation((_DWORD)a1, v74);
    v78 = v74 + StartingOffset.QuadPart;
    NtfsSnapshotScb(a1, FsContext);
    v79 = FsContext + 200;
    if ( v78 <= *((_QWORD *)FsContext + 4) )
    {
LABEL_227:
      if ( !v124 || v78 <= *((_QWORD *)FsContext + 5) )
        goto LABEL_238;
      *v79 = *v79;
      if ( (*v79 & 0x20000) != 0 )
      {
        v83 = *((_QWORD *)FsContext + 58);
        if ( v83 < v78 )
        {
LABEL_236:
          *((_QWORD *)FsContext + 58) = v78;
          goto LABEL_237;
        }
        if ( *((_QWORD *)FsContext + 5) > v78 )
        {
          if ( *(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) && v78 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v84 = (v78 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v84 < v83 )
              *((_QWORD *)FsContext + 58) = v84;
            goto LABEL_237;
          }
          goto LABEL_236;
        }
      }
LABEL_237:
      *((_QWORD *)FsContext + 5) = v78;
LABEL_238:
      NtfsWriteFileSizes((_DWORD)a1, (_DWORD)FsContext, 0, 0, 1, 1);
      v85 = *((_QWORD *)FsContext + 35);
      if ( v85 )
        NtfsSetCcFileSizes(v85, FsContext, FsContext + 24);
      NtfsCheckpointCurrentTransaction(a1);
      NtfsReleaseSharedResources(a1);
      NtfsFreeSnapshotsForFcb(a1, v133);
      v40 = v77 + v138;
      v138 = v40;
      v155 = v40;
      QuadPart = v77 + StartingOffset.QuadPart;
      StartingOffset.QuadPart += v77;
      v72 = 0;
      goto LABEL_243;
    }
    if ( (*v79 & 0x20000) == 0 )
      goto LABEL_226;
    v80 = *((_QWORD *)FsContext + 58);
    if ( v78 < v80 )
      v80 = v78;
    if ( v80 <= *((_QWORD *)FsContext + 5) )
    {
LABEL_226:
      *((_QWORD *)FsContext + 4) = v78;
      goto LABEL_227;
    }
    if ( (*v79 & 0x20000) != 0 )
    {
      v81 = *((_QWORD *)FsContext + 58);
      if ( v81 < v80 )
      {
LABEL_224:
        *((_QWORD *)FsContext + 58) = v80;
        goto LABEL_225;
      }
      if ( *((_QWORD *)FsContext + 5) > v80 )
      {
        if ( *(_QWORD *)(*((_QWORD *)FsContext + 36) + 16LL) && v80 != 0x7FFFFFFFFFFFFFFFLL )
        {
          v82 = (v80 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          if ( v82 < v81 )
            *((_QWORD *)FsContext + 58) = v82;
          goto LABEL_225;
        }
        goto LABEL_224;
      }
    }
LABEL_225:
    *((_QWORD *)FsContext + 5) = v80;
    goto LABEL_226;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 3221226666LL, 1198494);
  LOBYTE(v23) = a2 != 0;
  NtfsExtendedCompleteRequestInternal(a1, a2, 3221226666LL, v23, 0);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221226666LL, 1198495);
  return 3221226666LL;
}

```

## disassembly

```asm
0x140280d1c  mov     r11, rsp
0x140280d1f  mov     [r11+10h], rdx
0x140280d23  mov     [r11+8], rcx
0x140280d27  push    rbx
0x140280d28  push    rsi
0x140280d29  push    rdi
0x140280d2a  push    r12
0x140280d2c  push    r13
0x140280d2e  push    r14
0x140280d30  push    r15
0x140280d32  sub     rsp, 1A0h
0x140280d39  mov     rdi, rdx
0x140280d3c  mov     r13, rcx
0x140280d3f  xor     esi, esi
0x140280d41  mov     [r11-150h], rsi
0x140280d48  mov     [r11-70h], rsi
0x140280d4c  mov     [rsp+1D8h+var_C8], esi
0x140280d53  mov     [rsp+1D8h+var_CC], esi
0x140280d5a  mov     [rsp+1D8h+var_114], esi
0x140280d61  mov     [rsp+1D8h+var_120], si
0x140280d69  mov     [rsp+1D8h+var_168], sil
0x140280d6e  mov     [rsp+1D8h+var_154], sil
0x140280d76  xorps   xmm0, xmm0
0x140280d79  xor     eax, eax
0x140280d7b  movups  xmmword ptr [r11-60h], xmm0
0x140280d80  mov     [r11-50h], rax
0x140280d84  movups  xmmword ptr [r11-48h], xmm0
0x140280d89  mov     [rsp+1D8h+var_164], eax
0x140280d8d  mov     [rsp+1D8h+var_153], al
0x140280d94  mov     r14d, esi
0x140280d97  mov     ebx, esi
0x140280d99  mov     [r11+20h], rbx
0x140280d9d  mov     al, [rdx+40h]
0x140280da0  mov     [rsp+1D8h+arg_10], al
0x140280da7  lea     r12d, [rsi+1]
0x140280dab  or      [rcx+0Ch], r12d
0x140280daf  xor     r8d, r8d; State
0x140280db2  mov     edx, r12d; Type
0x140280db5  lea     rcx, [r11-60h]; Event
0x140280db9  call    cs:__imp_KeInitializeEvent
0x140280dc0  nop     dword ptr [rax+rax+00h]
0x140280dc5  mov     rcx, [rdi+0B8h]
0x140280dcc  mov     rax, [rcx+30h]
0x140280dd0  mov     [rsp+1D8h+var_D8], rax
0x140280dd8  mov     r15, [rax+18h]
0x140280ddc  test    r15, r15
0x140280ddf  jz      short loc_140280E44
0x140280de1  mov     r10, [rax+20h]
0x140280de5  mov     [rsp+1D8h+var_F0], r10
0x140280ded  mov     r11, [r15+0C0h]
0x140280df4  mov     [rsp+1D8h+var_130], r11
0x140280dfc  mov     eax, [r11+4]
0x140280e00  test    r12b, al
0x140280e03  jnz     short loc_140280E21
0x140280e05  test    r10, r10
0x140280e08  jz      loc_140282864
0x140280e0e  cmp     byte ptr [r10+58h], 4
0x140280e13  jnz     loc_140282864
0x140280e19  test    al, 2
0x140280e1b  jz      loc_140282864
0x140280e21  test    r10, r10
0x140280e24  jz      short loc_140280E75
0x140280e26  mov     rdx, [r15+0B8h]
0x140280e2d  mov     [rsp+1D8h+var_128], rdx
0x140280e35  mov     [rsp+1D8h+var_88], rdx
0x140280e3d  movzx   eax, byte ptr [r10+58h]
0x140280e42  jmp     short loc_140280E70
0x140280e44  mov     r11, rsi
0x140280e47  mov     [rsp+1D8h+var_130], rsi
0x140280e4f  mov     r10, rsi
0x140280e52  mov     [rsp+1D8h+var_F0], rsi
0x140280e5a  mov     rax, rsi
0x140280e5d  mov     [rsp+1D8h+var_128], rax
0x140280e65  mov     [rsp+1D8h+var_88], rax
0x140280e6d  mov     eax, r12d
0x140280e70  cmp     eax, 2
0x140280e73  jz      short loc_140280ECE
0x140280e75  mov     al, cs:NtfsStatusDebugFlags
0x140280e7b  mov     ebx, 0C000000Dh
0x140280e80  test    al, al
0x140280e82  jz      short loc_140280E94
0x140280e84  mov     r8d, 1248F6h
0x140280e8a  mov     edx, ebx
0x140280e8c  mov     rcx, r13
0x140280e8f  call    NtfsStatusTraceAndDebugInternal
0x140280e94  test    rdi, rdi
0x140280e97  setnz   r9b
0x140280e9b  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x140280e9f  mov     r8d, ebx
0x140280ea2  mov     rdx, rdi
0x140280ea5  mov     rcx, r13
0x140280ea8  call    NtfsExtendedCompleteRequestInternal
0x140280ead  mov     cl, cs:NtfsStatusDebugFlags
0x140280eb3  test    cl, cl
0x140280eb5  jz      short loc_140280EC6
0x140280eb7  mov     r8d, 1248F7h
0x140280ebd  mov     edx, ebx
0x140280ebf  xor     ecx, ecx
0x140280ec1  call    NtfsStatusTraceAndDebugInternal
0x140280ec6  mov     eax, ebx
0x140280ec8  jmp     loc_140282A81
0x140280ece  test    dword ptr [r11+4], 2000000h
0x140280ed6  jz      short loc_140280F22
0x140280ed8  mov     al, cs:NtfsStatusDebugFlags
0x140280ede  mov     ebx, 0C00000A2h
0x140280ee3  test    al, al
0x140280ee5  jz      short loc_140280EF7
0x140280ee7  mov     r8d, 124900h
0x140280eed  mov     edx, ebx
0x140280eef  mov     rcx, r13
0x140280ef2  call    NtfsStatusTraceAndDebugInternal
0x140280ef7  test    rdi, rdi
0x140280efa  setnz   r9b
0x140280efe  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x140280f02  mov     r8d, ebx
0x140280f05  mov     rdx, rdi
0x140280f08  mov     rcx, r13
0x140280f0b  call    NtfsExtendedCompleteRequestInternal
0x140280f10  mov     cl, cs:NtfsStatusDebugFlags
0x140280f16  test    cl, cl
0x140280f18  jz      short loc_140280EC6
0x140280f1a  mov     r8d, 124901h
0x140280f20  jmp     short loc_140280EBD
0x140280f22  mov     eax, [r10+64h]
0x140280f26  mov     [r13+110h], eax
0x140280f2d  bt      word ptr [r15+1CCh], 0Eh
0x140280f37  jb      short loc_140280F95
0x140280f39  mov     al, cs:NtfsStatusDebugFlags
0x140280f3f  mov     r14d, 0C00004A7h
0x140280f45  test    al, al
0x140280f47  jz      short loc_140280F5A
0x140280f49  mov     r8d, 124911h
0x140280f4f  mov     edx, r14d
0x140280f52  mov     rcx, r13
0x140280f55  call    NtfsStatusTraceAndDebugInternal
0x140280f5a  test    rdi, rdi
0x140280f5d  setnz   r9b
0x140280f61  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x140280f65  mov     r8d, r14d
0x140280f68  mov     rdx, rdi
0x140280f6b  mov     rcx, r13
0x140280f6e  call    NtfsExtendedCompleteRequestInternal
0x140280f73  mov     al, cs:NtfsStatusDebugFlags
0x140280f79  test    al, al
0x140280f7b  jz      short loc_140280F8D
0x140280f7d  mov     r8d, 124912h
0x140280f83  mov     edx, r14d
0x140280f86  xor     ecx, ecx
0x140280f88  call    NtfsStatusTraceAndDebugInternal
0x140280f8d  mov     eax, r14d
0x140280f90  jmp     loc_140282A81
0x140280f95  movzx   r9d, word ptr [r10+68h]
0x140280f9a  test    r9b, 12h
0x140280f9e  jnz     loc_1402810B6
0x140280fa4  mov     eax, [r13+10h]
0x140280fa8  bt      rax, 14h
0x140280fad  jb      loc_140281065
0x140280fb3  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x140280fba  test    al, 20h
0x140280fbc  jz      loc_140281065
0x140280fc2  mov     rdx, [r11+0F8h]
0x140280fc9  movzx   r8d, word ptr [rdx+6]
0x140280fce  cmp     r8w, 40h ; '@'
0x140280fd3  ja      short loc_140280FDA
0x140280fd5  test    r12b, r8b
0x140280fd8  jz      short loc_140280FDD
0x140280fda  mov     r8d, esi
0x140280fdd  movzx   ecx, word ptr [r10+10h]
0x140280fe2  shr     ecx, 1
0x140280fe4  add     rdx, 20h ; ' '
0x140280fe8  movzx   r10d, r8w
0x140280fec  shr     r10d, 1
0x140280fef  movzx   r11d, word ptr [r11+1EC0h]
0x140280ff7  shr     r11d, 1
0x140280ffa  mov     r8, gs:188h
0x140281003  mov     [rsp+1D8h+var_178], r9d
0x140281008  mov     rax, [rsp+1D8h+var_F0]
0x140281010  mov     rax, [rax+18h]
0x140281014  mov     [rsp+1D8h+var_180], rax
0x140281019  mov     [rsp+1D8h+var_188], ecx
0x14028101d  mov     rcx, [rsp+1D8h+var_128]
0x140281025  mov     rax, [rcx+8]
0x140281029  mov     [rsp+1D8h+var_190], rax
0x14028102e  mov     [rsp+1D8h+var_198], rcx
0x140281033  mov     [rsp+1D8h+var_1A0], rdx
0x140281038  mov     dword ptr [rsp+1D8h+IoStatusBlock], r10d
0x14028103d  mov     rcx, [rsp+1D8h+var_130]
0x140281045  mov     rax, [rcx+1EC8h]
0x14028104c  mov     [rsp+1D8h+Event], rax
0x140281051  mov     dword ptr [rsp+1D8h+StartingOffset], r11d
0x140281056  mov     r9, rcx
0x140281059  lea     rdx, fsctrl_c18715
0x140281060  call    McTemplateU0ppwwpiwd_EtwWriteTransfer
0x140281065  mov     al, cs:NtfsStatusDebugFlags
0x14028106b  mov     ebx, 0C0000022h
0x140281070  test    al, al
0x140281072  jz      short loc_140281084
0x140281074  mov     r8d, 12492Ah
0x14028107a  mov     edx, ebx
0x14028107c  mov     rcx, r13
0x14028107f  call    NtfsStatusTraceAndDebugInternal
0x140281084  test    rdi, rdi
0x140281087  setnz   r9b
0x14028108b  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x14028108f  mov     r8d, ebx
0x140281092  mov     rdx, rdi
0x140281095  mov     rcx, r13
0x140281098  call    NtfsExtendedCompleteRequestInternal
0x14028109d  mov     cl, cs:NtfsStatusDebugFlags
0x1402810a3  test    cl, cl
0x1402810a5  jz      loc_140280EC6
0x1402810ab  mov     r8d, 12492Bh
0x1402810b1  jmp     loc_140280EBD
0x1402810b6  test    dword ptr [r11+18h], 40000h
0x1402810be  jz      short loc_140281111
0x1402810c0  mov     al, cs:NtfsStatusDebugFlags
0x1402810c6  mov     ebx, 0C000049Ah
0x1402810cb  test    al, al
0x1402810cd  jz      short loc_1402810DF
0x1402810cf  mov     r8d, 124934h
0x1402810d5  mov     edx, ebx
0x1402810d7  mov     rcx, r13
0x1402810da  call    NtfsStatusTraceAndDebugInternal
0x1402810df  test    rdi, rdi
0x1402810e2  setnz   r9b
0x1402810e6  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x1402810ea  mov     r8d, ebx
0x1402810ed  mov     rdx, rdi
0x1402810f0  mov     rcx, r13
0x1402810f3  call    NtfsExtendedCompleteRequestInternal
0x1402810f8  mov     cl, cs:NtfsStatusDebugFlags
0x1402810fe  test    cl, cl
0x140281100  jz      loc_140280EC6
0x140281106  mov     r8d, 124935h
0x14028110c  jmp     loc_140280EBD
0x140281111  mov     edx, [rcx+10h]; Length
0x140281114  mov     [rsp+1D8h+var_118], edx
0x14028111b  mov     [rsp+1D8h+var_FC], edx
0x140281122  cmp     edx, 20h ; ' '
0x140281125  jnb     short loc_140281178
0x140281127  mov     al, cs:NtfsStatusDebugFlags
0x14028112d  mov     ebx, 0C0000023h
0x140281132  test    al, al
0x140281134  jz      short loc_140281146
0x140281136  mov     r8d, 124945h
0x14028113c  mov     edx, ebx
0x14028113e  mov     rcx, r13
0x140281141  call    NtfsStatusTraceAndDebugInternal
0x140281146  test    rdi, rdi
0x140281149  setnz   r9b
0x14028114d  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x140281151  mov     r8d, ebx
0x140281154  mov     rdx, rdi
0x140281157  mov     rcx, r13
0x14028115a  call    NtfsExtendedCompleteRequestInternal
0x14028115f  mov     cl, cs:NtfsStatusDebugFlags
0x140281165  test    cl, cl
0x140281167  jz      loc_140280EC6
0x14028116d  mov     r8d, 124946h
0x140281173  jmp     loc_140280EBD
0x140281178  mov     r9, [rcx+20h]
0x14028117c  mov     [rsp+1D8h+var_148], r9
0x140281184  mov     [rsp+1D8h+var_80], r9
0x14028118c  cmp     dword ptr [rcx-40h], 0FFFFFFFFh
0x140281190  jnz     short loc_1402811AA
0x140281192  mov     [rsp+1D8h+var_15F], sil
0x140281197  mov     [rcx-40h], esi
0x14028119a  mov     eax, [r15+28h]
0x14028119e  mov     [rcx-38h], eax
0x1402811a1  mov     eax, [r15+2Ch]
0x1402811a5  mov     [rcx-30h], eax
0x1402811a8  jmp     short loc_1402811CB
0x1402811aa  mov     [rsp+1D8h+var_15F], r12b
0x1402811af  mov     eax, [rcx-38h]
0x1402811b2  mov     dword ptr [rsp+1D8h+arg_18], eax
0x1402811b9  mov     eax, [rcx-30h]
0x1402811bc  mov     dword ptr [rsp+1D8h+arg_18+4], eax
0x1402811c3  mov     rbx, [rsp+1D8h+arg_18]
0x1402811cb  cmp     [rdi+40h], sil
0x1402811cf  jz      short loc_1402811EB
0x1402811d1  mov     r8d, r12d; Alignment
0x1402811d4  mov     rcx, r9; Address
0x1402811d7  call    cs:__imp_ProbeForRead
0x1402811de  nop     dword ptr [rax+rax+00h]
0x1402811e3  mov     r9, [rsp+1D8h+var_148]
0x1402811eb  mov     r12b, [rsp+1D8h+arg_10]
0x1402811f3  test    r12b, r12b
0x1402811f6  jz      short loc_14028120B
0x1402811f8  lea     rcx, [r9+8]
0x1402811fc  call    RtlReadULongFromUser
0x140281201  mov     r9, [rsp+1D8h+var_148]
0x140281209  jmp     short loc_14028120F
0x14028120b  mov     eax, [r9+8]
0x14028120f  mov     [rsp+1D8h+var_140], eax
0x140281216  mov     [rsp+1D8h+var_114], eax
0x14028121d  test    r12b, r12b
0x140281220  jz      short loc_140281235
0x140281222  lea     rcx, [r9+10h]
0x140281226  call    RtlReadULongFromUser
0x14028122b  mov     r9, [rsp+1D8h+var_148]
  ... truncated ...
```
