# MpAmPostCreate

- ea: `0x140051af0`
- end: `0x140053f18`
- name: `MpAmPostCreate`
- size: `9256`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14002e850`

## callees

- `0x1400018a4`
- `0x1400026c0`
- `0x140002d40`
- `0x1400034e0`
- `0x140003650`
- `0x140003d20`
- `0x140003f10`
- `0x1400051bc`
- `0x14000583c`
- `0x140006234`
- `0x1400067d0`
- `0x140009b14`
- `0x140009bf0`
- `0x14000a24c`
- `0x14000a364`
- `0x14000a7d8`
- `0x14000ae58`
- `0x14000b4e8`
- `0x14000b704`
- `0x14000b7dc`
- `0x14000f42c`
- `0x14000f4d0`
- `0x140011890`
- `0x1400118d0`
- `0x140011bc0`
- `0x1400510e4`
- `0x140051160`
- `0x1400516f4`
- `0x140051af0`
- `0x140053f20`
- `0x1400544a0`
- `0x140054670`
- `0x1400549c0`
- `0x140054ad0`
- `0x140055eb0`
- `0x14006ffac`
- `0x14007af3c`
- `0x14007b128`
- `0x140084030`
- `0x140084780`
- `0x140084be8`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140052f54`
- `ntoskrnl!KeSetTimer` at `0x140052f54`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140052368`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140052d2b`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140052368`
- `ntoskrnl!KeQueryTimeIncrement` at `0x140052d2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005240b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14005240b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400523ff`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400523ff`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400521c4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400521c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400521a7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400521a7`
- `ntoskrnl!IoThreadToProcess` at `0x1400520d0`
- `ntoskrnl!IoThreadToProcess` at `0x140052109`
- `ntoskrnl!IoThreadToProcess` at `0x1400520d0`
- `ntoskrnl!IoThreadToProcess` at `0x140052109`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400523d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400523d1`
- `FLTMGR!FltReleaseContext` at `0x14005314e`
- `FLTMGR!FltReleaseContext` at `0x140053eac`
- `FLTMGR!FltReleaseContext` at `0x140053eeb`
- `FLTMGR!FltReleaseContext` at `0x14008c9d5`
- `FLTMGR!FltReleaseContext` at `0x14008c9ee`
- `FLTMGR!FltReleaseContext` at `0x14005314e`
- `FLTMGR!FltReleaseContext` at `0x140053eac`
- `FLTMGR!FltReleaseContext` at `0x140053eeb`
- `FLTMGR!FltReleaseContext` at `0x14008c9d5`
- `FLTMGR!FltReleaseContext` at `0x14008c9ee`
- `FLTMGR!FltAcquirePushLockShared` at `0x1400528ed`
- `FLTMGR!FltAcquirePushLockShared` at `0x140052af5`
- `FLTMGR!FltAcquirePushLockShared` at `0x140052bca`
- `FLTMGR!FltAcquirePushLockShared` at `0x140053965`
- `FLTMGR!FltAcquirePushLockShared` at `0x140053aec`
- `FLTMGR!FltAcquirePushLockShared` at `0x1400528ed`
- `FLTMGR!FltAcquirePushLockShared` at `0x140052af5`
- `FLTMGR!FltAcquirePushLockShared` at `0x140052bca`
- `FLTMGR!FltAcquirePushLockShared` at `0x140053965`
- `FLTMGR!FltAcquirePushLockShared` at `0x140053aec`
- `FLTMGR!FltReleasePushLock` at `0x1400523e4`
- `FLTMGR!FltReleasePushLock` at `0x14005292c`
- `FLTMGR!FltReleasePushLock` at `0x140052b27`
- `FLTMGR!FltReleasePushLock` at `0x140052c0c`
- `FLTMGR!FltReleasePushLock` at `0x1400539b3`
- `FLTMGR!FltReleasePushLock` at `0x140053b13`
- `FLTMGR!FltReleasePushLock` at `0x1400523e4`
- `FLTMGR!FltReleasePushLock` at `0x14005292c`
- `FLTMGR!FltReleasePushLock` at `0x140052b27`
- `FLTMGR!FltReleasePushLock` at `0x140052c0c`
- `FLTMGR!FltReleasePushLock` at `0x1400539b3`
- `FLTMGR!FltReleasePushLock` at `0x140053b13`
- `FLTMGR!FltIsEcpFromUserMode` at `0x140052a53`
- `FLTMGR!FltIsEcpFromUserMode` at `0x140052a53`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140051dc2`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005259d`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x140051dc2`
- `FLTMGR!FltGetEcpListFromCallbackData` at `0x14005259d`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140051e3f`
- `FLTMGR!FltIsEcpAcknowledged` at `0x140051e3f`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140051e13`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400525e2`
- `FLTMGR!FltFindExtraCreateParameter` at `0x140051e13`
- `FLTMGR!FltFindExtraCreateParameter` at `0x1400525e2`
- `FLTMGR!FltGetStreamContext` at `0x140051bcd`
- `FLTMGR!FltGetStreamContext` at `0x140051bcd`
- `FLTMGR!FltCancelFileOpen` at `0x140053c0b`
- `FLTMGR!FltCancelFileOpen` at `0x140053e8a`
- `FLTMGR!FltCancelFileOpen` at `0x140053c0b`
- `FLTMGR!FltCancelFileOpen` at `0x140053e8a`
- `FLTMGR!FltQueryInformationFile` at `0x140053052`
- `FLTMGR!FltQueryInformationFile` at `0x140053052`
- `FLTMGR!FltGetInstanceContext` at `0x1400530c7`
- `FLTMGR!FltGetInstanceContext` at `0x1400530c7`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140052305`
- `FLTMGR!FltAcquirePushLockExclusive` at `0x140052305`

## string_xrefs

- `0x140053e20`: `blocked access`

## pseudocode

```c
PFLT_CONTEXT __fastcall MpAmPostCreate(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        _BYTE *a3,
        struct _KTHREAD *a4,
        PFLT_CONTEXT *a5)
{
  _DWORD *v8; // r14
  __int64 v9; // rbx
  char v10; // si
  __int64 v11; // rdx
  int v12; // ecx
  __int64 v13; // r8
  __int64 v14; // r8
  ULONG_PTR Information; // rax
  PFLT_CONTEXT v16; // rsi
  __int64 v17; // rcx
  int v18; // eax
  PETHREAD Thread; // rsi
  unsigned __int16 *v20; // rdi
  PECP_LIST v21; // rdx
  NTSTATUS EcpListFromCallbackData; // ebx
  int v23; // edi
  int v24; // eax
  char *v25; // rsi
  __int64 v26; // rdx
  _QWORD *v27; // rbx
  __int64 v28; // rdx
  int *v29; // rbx
  int v30; // ebx
  int v31; // eax
  int v32; // eax
  int v33; // eax
  struct _KTHREAD *v34; // rsi
  unsigned int v35; // eax
  __int64 v36; // rcx
  unsigned int v37; // esi
  __int64 v38; // r8
  __int64 *i; // rcx
  PDEVICE_OBJECT v40; // r10
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rsi
  PVOID v45; // rsi
  bool v46; // si
  unsigned __int8 (__fastcall *v47)(PFLT_CALLBACK_DATA, __int64, PFLT_CONTEXT, struct _KTHREAD *); // rax
  _DWORD *v48; // rbx
  struct _KTHREAD *v49; // rbx
  int v50; // ecx
  ULONG_PTR v51; // r8
  ULONG v52; // edx
  int v53; // ecx
  const char *v54; // rcx
  struct _FLT_FILTER *v55; // rsi
  NTSTATUS v56; // eax
  PFLT_CONTEXT v57; // rbx
  unsigned int v58; // eax
  int v59; // ecx
  _QWORD *PoolWithTag; // rax
  __int64 v61; // rdx
  int v62; // r8d
  __int64 v63; // rax
  int v64; // eax
  unsigned int v65; // eax
  int v66; // ecx
  unsigned __int64 *v67; // rsi
  __int64 v68; // rcx
  char *v69; // rcx
  int v70; // eax
  __int64 v71; // rcx
  signed __int64 v72; // rax
  int IsFileLockByTransaction; // eax
  __int64 v74; // rsi
  _QWORD *v75; // r8
  unsigned __int8 *v76; // r9
  __int64 v77; // r10
  __int64 v78; // rcx
  __int64 v79; // rcx
  _QWORD *v80; // rcx
  __int64 v81; // r8
  __int64 (__fastcall *v82)(_QWORD, PFLT_CALLBACK_DATA, __int64, int *); // rax
  NTSTATUS v83; // ecx
  int v84; // ecx
  int v85; // edx
  char *v86; // rax
  char *v87; // rsi
  __int64 v88; // r9
  __int64 *v89; // r9
  unsigned int MpFileStateWithSeq_0; // eax
  __int64 v91; // r10
  __int64 v92; // r11
  int CsvRevisionECP; // eax
  __int64 v94; // rdx
  signed __int64 v95; // rbx
  signed __int64 v96; // rdi
  int v97; // eax
  __int64 v98; // rdx
  signed __int64 v99; // rax
  int v100; // eax
  PFLT_CONTEXT v101; // rdi
  int v102; // r8d
  int v103; // eax
  unsigned __int64 *v104; // rbx
  NTSTATUS v105; // ecx
  int v106; // ecx
  int v107; // ecx
  NTSTATUS v108; // ecx
  NTSTATUS ProcessBlockExecStatus; // eax
  PFLT_CONTEXT result; // rax
  int EcpContextSize; // [rsp+20h] [rbp-278h]
  char v112[4]; // [rsp+60h] [rbp-238h] BYREF
  NTSTATUS StreamContext; // [rsp+64h] [rbp-234h]
  int v114; // [rsp+68h] [rbp-230h]
  int v115; // [rsp+6Ch] [rbp-22Ch]
  int v116; // [rsp+70h] [rbp-228h]
  __int64 v117; // [rsp+78h] [rbp-220h]
  bool v118; // [rsp+80h] [rbp-218h]
  int v119; // [rsp+84h] [rbp-214h]
  int v120; // [rsp+88h] [rbp-210h]
  _DWORD *v121; // [rsp+90h] [rbp-208h] BYREF
  int v122; // [rsp+98h] [rbp-200h]
  int v123; // [rsp+9Ch] [rbp-1FCh]
  __int64 *v124; // [rsp+A0h] [rbp-1F8h]
  PVOID P; // [rsp+A8h] [rbp-1F0h]
  struct _KTHREAD *CurrentThread; // [rsp+B0h] [rbp-1E8h]
  int v127; // [rsp+B8h] [rbp-1E0h]
  int v128; // [rsp+BCh] [rbp-1DCh]
  int v129; // [rsp+C0h] [rbp-1D8h]
  int v130; // [rsp+C4h] [rbp-1D4h]
  PFLT_CONTEXT v131; // [rsp+C8h] [rbp-1D0h] BYREF
  __int64 v132; // [rsp+D0h] [rbp-1C8h]
  _BYTE v133[24]; // [rsp+D8h] [rbp-1C0h] BYREF
  __int16 v134; // [rsp+F0h] [rbp-1A8h]
  __int64 v135; // [rsp+F8h] [rbp-1A0h]
  int v136; // [rsp+100h] [rbp-198h]
  __int64 v137; // [rsp+108h] [rbp-190h]
  __int64 v138; // [rsp+110h] [rbp-188h] BYREF
  _BYTE v139[40]; // [rsp+118h] [rbp-180h] BYREF
  __int64 v140; // [rsp+140h] [rbp-158h]
  PVOID v141; // [rsp+148h] [rbp-150h]
  int v142; // [rsp+150h] [rbp-148h]
  NTSTATUS v143; // [rsp+154h] [rbp-144h]
  PFLT_CONTEXT *v144; // [rsp+158h] [rbp-140h]
  signed __int64 v145; // [rsp+160h] [rbp-138h]
  signed __int64 v146; // [rsp+168h] [rbp-130h]
  __int64 v147; // [rsp+170h] [rbp-128h]
  PETHREAD v148; // [rsp+178h] [rbp-120h]
  PETHREAD v149; // [rsp+180h] [rbp-118h]
  PETHREAD v150; // [rsp+188h] [rbp-110h]
  struct _KTHREAD *v151; // [rsp+190h] [rbp-108h]
  __int64 v152; // [rsp+198h] [rbp-100h]
  __int64 v153; // [rsp+1A0h] [rbp-F8h]
  __int64 v154; // [rsp+1A8h] [rbp-F0h]
  PETHREAD v155; // [rsp+1B0h] [rbp-E8h]
  signed __int64 v156; // [rsp+1B8h] [rbp-E0h]
  __int64 v157; // [rsp+1C0h] [rbp-D8h]
  __int64 v158; // [rsp+1C8h] [rbp-D0h]
  __int64 v159; // [rsp+1D0h] [rbp-C8h]
  signed __int64 v160; // [rsp+1D8h] [rbp-C0h]
  signed __int64 v161; // [rsp+1E0h] [rbp-B8h]
  PFLT_CONTEXT Context; // [rsp+1E8h] [rbp-B0h] BYREF
  PVOID v163; // [rsp+1F0h] [rbp-A8h] BYREF
  PECP_LIST v164; // [rsp+1F8h] [rbp-A0h] BYREF
  PVOID EcpContext; // [rsp+200h] [rbp-98h] BYREF
  PFLT_CONTEXT v166; // [rsp+208h] [rbp-90h] BYREF
  PECP_LIST EcpList; // [rsp+210h] [rbp-88h] BYREF
  ULONG v168; // [rsp+218h] [rbp-80h] BYREF
  int v169; // [rsp+21Ch] [rbp-7Ch] BYREF
  ULONG v170; // [rsp+220h] [rbp-78h] BYREF
  __int128 FileInformation; // [rsp+228h] [rbp-70h] BYREF
  __int128 v172; // [rsp+238h] [rbp-60h]
  __int64 v173; // [rsp+248h] [rbp-50h]

  CurrentThread = a4;
  v144 = a5;
  Context = 0;
  v131 = 0;
  v115 = 0;
  v114 = 0;
  v8 = 0;
  v121 = 0;
  v9 = 0;
  v132 = 0;
  v10 = 0;
  v112[0] = 0;
  memset(v139, 0, sizeof(v139));
  FileInformation = 0;
  v172 = 0;
  v173 = 0;
  v11 = 0;
  v12 = 0;
  v169 = 0;
  if ( (*a3 & 1) == 0 )
  {
    v81 = 0;
    if ( (*(_DWORD *)(MpData + 864) & 0x400) != 0 )
    {
      v82 = *(__int64 (__fastcall **)(_QWORD, PFLT_CALLBACK_DATA, __int64, int *))(MpData + 96);
      if ( v82 )
      {
        v11 = v82(*(_QWORD *)(MpData + 16), CallbackData, 1, &v169);
        v152 = v11;
        v81 = v11;
        v12 = v169;
      }
    }
    if ( v81 && v12 == 72 )
    {
      FileInformation = *(_OWORD *)(v11 + 8);
      v172 = *(_OWORD *)(v11 + 24);
      v84 = *(_DWORD *)(v11 + 56);
      LODWORD(v173) = v84;
    }
    else
    {
      v83 = FltQueryInformationFile(
              *(PFLT_INSTANCE *)(a2 + 24),
              *(PFILE_OBJECT *)(a2 + 32),
              &FileInformation,
              0x28u,
              FileBasicInformation,
              0);
      StreamContext = v83;
      if ( v83 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          CurrentThread = KeGetCurrentThread();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            32,
            WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
            CurrentThread,
            v83);
        }
        goto LABEL_402;
      }
      v84 = v173;
    }
    v119 = v84;
    v166 = 0;
    if ( CallbackData->IoStatus.Information == 2 )
    {
      v123 = v84 & 0x10;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      {
        v89 = &qword_14001BD28;
        if ( (v84 & 0x10) == 0 )
          v89 = (__int64 *)L"\b\n";
        WPP_SF_ZZD(
          WPP_GLOBAL_Control->AttachedDevice,
          v84 & 0x10,
          (_DWORD)WPP_GLOBAL_Control,
          (_DWORD)v89,
          *(_QWORD *)(a2 + 32) + 88LL,
          v84);
      }
      if ( FltGetInstanceContext(*(PFLT_INSTANCE *)(a2 + 24), &v166) >= 0 )
      {
        v85 = 0;
        v136 = 0;
        if ( !v123 || (v85 = 1024, v136 = 1024, (*(_DWORD *)(MpData + 3908) & 1) != 0) )
          MpSendFileAsyncMessage(
            0,
            (_DWORD)CallbackData,
            a2,
            *((_DWORD *)v166 + 21),
            v119,
            v85,
            *(_QWORD *)(a2 + 40),
            0,
            (__int64)CurrentThread,
            (__int64)(a3 + 24),
            0);
        FltReleaseContext(v166);
      }
      LOBYTE(v84) = v173;
    }
    if ( (v84 & 0x10) != 0 )
      goto LABEL_402;
  }
  v13 = *(_QWORD *)(a2 + 40);
  if ( v13 )
  {
    LOBYTE(v11) = 1;
    v70 = MpTxfGetContext(a2, v11, v13, &v121);
    StreamContext = v70;
    if ( v70 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          (unsigned int)v70);
      goto LABEL_198;
    }
    _mm_lfence();
    v8 = v121;
    IsFileLockByTransaction = MpTxfIsFileLockByTransaction(a2, v121, v112, (unsigned int)v70);
    StreamContext = IsFileLockByTransaction;
    if ( IsFileLockByTransaction < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          (unsigned int)IsFileLockByTransaction);
      goto LABEL_402;
    }
    v115 = v114;
    v9 = v132;
    v10 = v112[0];
  }
  StreamContext = FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
  if ( StreamContext >= 0 )
  {
    StreamContext = MpPostCreateUpdateStreamContext(
                      (_DWORD)CallbackData,
                      a2,
                      (_DWORD)v8,
                      (_DWORD)a3,
                      (__int64)Context,
                      v10);
    if ( StreamContext >= 0 )
      goto LABEL_5;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_402;
    v61 = 35;
    goto LABEL_156;
  }
  v56 = MpCreateStreamContext(CallbackData, v10, (__int64)&Context);
  StreamContext = v56;
  if ( (int)(v56 + 0x80000000) >= 0 && v56 != -1071906814 )
  {
    if ( v56 == -1073741638
      || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
    {
      goto LABEL_402;
    }
    v61 = 37;
LABEL_156:
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      v61,
      WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
      CallbackData->Thread,
      StreamContext);
LABEL_198:
    v8 = v121;
    goto LABEL_402;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_qdZidD(
      WPP_GLOBAL_Control->AttachedDevice,
      *((_QWORD *)Context + 1),
      *(_DWORD *)(a2 + 32) + 88,
      (_DWORD)Context,
      *(_DWORD *)(*((_QWORD *)Context + 1) + 4LL),
      *(_QWORD *)(a2 + 32) + 88LL,
      *((_QWORD *)Context + 21),
      v10,
      *((_DWORD *)Context + 12));
  if ( v8 )
  {
    if ( v10 )
    {
      v62 = MpTxfAddStream(a2, v8, *(unsigned __int16 *)(a2 + 2), Context);
      StreamContext = v62;
      if ( v62 < 0 )
      {
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_402;
        v41 = 39;
        EcpContextSize = v62;
LABEL_335:
        WPP_SF_qD(
          v40->AttachedDevice,
          v41,
          WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          CallbackData->Thread,
          EcpContextSize);
        goto LABEL_402;
      }
    }
  }
  if ( dword_140026A00 == 1 )
    MpCopyStreamStateFromFileStateGenericTable(Context, 27, MpCopyCsvStreamStateFromCacheEntry);
  if ( dword_140026A04 == 1 )
    MpCopyStreamStateFromFileStateGenericTable(Context, 28, MpCopyRefsStreamStateFromCacheEntry);
  if ( dword_140026A08 == 1 )
    MpCopyStreamStateFromFileStateGenericTable(Context, 2, MpCopyNtfsStreamStateFromCacheEntry);
  if ( CallbackData->IoStatus.Information == 2 )
    *((_DWORD *)Context + 12) |= 0x1000u;
LABEL_5:
  if ( Context == (PFLT_CONTEXT)BreakOnStream )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        40,
        (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        CallbackData->Thread,
        (__int64)Context,
        *(_QWORD *)(a2 + 32));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      MpFileStateWithSeq_0 = GetMpFileStateWithSeq_0((char *)Context + 32, *((_QWORD *)Context + 1));
      WPP_SF_Di(v92, 41, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids, MpFileStateWithSeq_0, v91);
    }
    __debugbreak();
  }
  if ( (*((_BYTE *)Context + 48) & 1) != 0 || (*(_QWORD *)a3 & 0x2000LL) != 0 )
    goto LABEL_402;
  MpUpdateHandleContextOnPostCreate(CallbackData, a2, a3, &v131);
  if ( v131 )
  {
    if ( a3[24] )
      _InterlockedIncrement((volatile signed __int32 *)Context + 158);
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
  {
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      42,
      WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
      CallbackData->Thread);
  }
  Information = CallbackData->IoStatus.Information;
  if ( Information == 2 || !Information || Information == 3 )
    _InterlockedCompareExchange((volatile signed __int32 *)Context + 13, CallbackData->IoStatus.Information, -1);
  v16 = Context;
  if ( !v8 )
  {
    v9 = _InterlockedCompareExchange64((volatile signed __int64 *)Context + 22, 0, 0);
    v153 = v9;
    v132 = v9;
LABEL_15:
    LODWORD(v17) = 0;
    v127 = 0;
    v18 = 0;
    goto LABEL_16;
  }
  if ( (v8[42] & 1) == 0 )
  {
    if ( (unsigned __int16)(*(_WORD *)(a2 + 2) - 1) > 0xFFFCu )
    {
      v163 = (char *)Context + 192;
      FltAcquirePushLockShared((PULONG_PTR)Context + 24);
      v71 = *((_QWORD *)v16 + 26);
      if ( v71 )
      {
        v72 = _InterlockedCompareExchange64((volatile signed __int64 *)(v71 + 32), 0, 0);
        v145 = v72;
      }
      else
      {
        v72 = _InterlockedCompareExchange64((volatile signed __int64 *)v16 + 22, 0, 0);
        v156 = v72;
      }
      v132 = v72;
      v9 = v72;
      FltReleasePushLock((PULONG_PTR)v163);
    }
    else
    {
      v9 = _InterlockedCompareExchange64((volatile signed __int64 *)Context + 22, 0, 0);
      v154 = v9;
      v132 = v9;
    }
    goto LABEL_15;
  }
  LODWORD(v17) = -1073741595;
  v127 = -1073741595;
  v18 = -1073741595;
LABEL_16:
  StreamContext = v17;
  if ( v18 < 0 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_402;
    v41 = 43;
    goto LABEL_334;
  }
  if ( (*(_DWORD *)a3 & 0x104LL) == 0 && CallbackData->IoStatus.Information == 1 )
  {
    v164 = *(PECP_LIST *)(a2 + 32);
    if ( (*((_DWORD *)v164 + 20) & 8) == 0 )
    {
      if ( v9 )
      {
        if ( (*(_DWORD *)(*((_QWORD *)Context + 1) + 84LL) & 0x10) == 0 )
        {
          Thread = CallbackData->Thread;
          if ( Thread )
          {
            P = 0;
            FltAcquirePushLockExclusive(&PushLock);
            v43 = MpSeqDetectCtxLookupEntry(v42, Thread);
            v163 = (PVOID)v43;
            if ( v43 )
            {
              if ( *(_QWORD *)(v43 + 32) )
                *(_WORD *)(v43 + 42) = 0;
              *(_QWORD *)(v43 + 32) = v164;
              *(_QWORD *)(v43 + 24) = v9;
              *(_QWORD *)(v43 + 16) = 0;
              v44 = MEMORY[0xFFFFF78000000320];
              v135 = MEMORY[0xFFFFF78000000320];
              v135 = v44 * KeQueryTimeIncrement() / 10000000;
              v134 = v135;
              *((_WORD *)v163 + 20) = v135;
              v45 = P;
            }
            else if ( qword_140026C28 || (int)MpSeqDetectCtxAllocResources() >= 0 )
            {
              PoolWithTag = (_QWORD *)MpAllocatePoolWithTag(1, 48, 1953714253);
              P = PoolWithTag;
              if ( PoolWithTag )
              {
                PoolWithTag[1] = Thread;
                PoolWithTag[4] = v164;
                PoolWithTag[3] = v9;
                v74 = MEMORY[0xFFFFF78000000320];
                v137 = MEMORY[0xFFFFF78000000320];
                v137 = v74 * KeQueryTimeIncrement() / 10000000;
                LOWORD(v116) = v137;
                v75 = P;
                *((_WORD *)P + 20) = v137;
                v138 = v75[1] & (-1LL << (BYTE4(MpSeqDetectCtx) & 0x1F));
                v45 = 0;
                v76 = (unsigned __int8 *)&v138;
                v124 = &v138;
                v77 = 8;
                v140 = 8;
                v78 = 314159;
                v117 = 314159;
                while ( v77 >= 8 )
                {
                  v117 = *v76 + 37 * v78;
                  v117 = v76[1] + 37 * v117;
                  v117 = v76[2] + 37 * v117;
                  v117 = v76[3] + 37 * v117;
                  v117 = v76[4] + 37 * v117;
                  v117 = v76[5] + 37 * v117;
                  v117 = v76[6] + 37 * v117;
                  v78 = 37 * v117 + v76[7];
                  v117 = v78;
                  v76 += 8;
                  v124 = (__int64 *)v76;
                  v77 -= 8;
                  v140 = v77;
                }
                if ( v77 != 2 )
                {
                  switch ( v77 )
                  {
                    case 1LL:
                      goto LABEL_221;
                    case 3LL:
                      goto LABEL_296;
                    case 4LL:
                      goto LABEL_295;
                    case 5LL:
                      goto LABEL_294;
                    case 6LL:
                      goto LABEL_293;
                    case 7LL:
                      v78 = *v76 + 37 * v78;
                      v117 = v78;
                      v124 = (__int64 *)++v76;
LABEL_293:
                      v78 = *v76 + 37 * v78;
                      v117 = v78;
                      v124 = (__int64 *)++v76;
LABEL_294:
                      v78 = *v76 + 37 * v78;
                      v117 = v78;
                      v124 = (__int64 *)++v76;
LABEL_295:
                      v78 = *v76 + 37 * v78;
                      v117 = v78;
                      v124 = (__int64 *)++v76;
LABEL_296:
                      v78 = *v76 + 37 * v78;
                      v117 = v78;
                      v124 = (__int64 *)++v76;
                      break;
                    default:
                      goto LABEL_222;
                  }
                }
                v78 = *v76 + 37 * v78;
                v117 = v78;
                v124 = (__int64 *)++v76;
LABEL_221:
                v78 = *v76 + 37 * v78;
                v117 = v78;
                v124 = (__int64 *)(v76 + 1);
LABEL_222:
                v147 = v78;
                v157 = v78;
                v158 = v78;
                v159 = v78;
                v79 = ((HIDWORD(MpSeqDetectCtx) >> 5) - 1) & (unsigned int)v78;
                v142 = v79;
                v80 = (char *)qword_140026C28 + 8 * v79;
                *v75 = *v80;
                *v80 = v75;
                LODWORD(MpSeqDetectCtx) = MpSeqDetectCtx + 1;
                P = 0;
                if ( (_DWORD)MpSeqDetectCtx == 1 && !byte_140026CF8 )
                  KeSetTimer(&Timer, (LARGE_INTEGER)-300000000LL, &Dpc);
              }
              else
              {
                v45 = 0;
              }
            }
            else
            {
              v45 = P;
            }
            if ( v45 )
              ExFreePoolWithTag(v45, 0x7473504Du);
            FltReleasePushLock(&PushLock);
          }
        }
      }
    }
  }
  if ( v9 <= 4 )
  {
    v57 = Context;
    if ( v8 )
    {
      if ( (v8[42] & 1) == 0 && (unsigned __int16)(*(_WORD *)(a2 + 2) - 1) > 0xFFFCu )
      {
        FltAcquirePushLockShared((PULONG_PTR)Context + 24);
        v63 = *((_QWORD *)v57 + 26);
        if ( v63 )
        {
          *(_DWORD *)(v63 + 24) = 3;
          *(_DWORD *)(*((_QWORD *)v57 + 26) + 28LL) = *(_DWORD *)(*((_QWORD *)v57 + 1) + 144LL);
        }
        else
        {
          *((_DWORD *)v57 + 8) = 3;
          *((_DWORD *)v57 + 9) = *(_DWORD *)(*((_QWORD *)v57 + 1) + 144LL);
          v65 = *((_DWORD *)v57 + 8);
          if ( v65 != 3 )
          {
            if ( v65 > 7 || (v66 = 148, !_bittest(&v66, v65)) )
              _InterlockedAnd((volatile signed __int32 *)v57 + 12, 0xFFFFBFFF);
          }
        }
        FltReleasePushLock((PULONG_PTR)v57 + 24);
      }
    }
    else
    {
      *((_DWORD *)Context + 8) = 3;
      *((_DWORD *)v57 + 9) = *(_DWORD *)(*((_QWORD *)v57 + 1) + 144LL);
      v58 = *((_DWORD *)v57 + 8);
      if ( v58 != 3 )
      {
        if ( v58 > 7 || (v59 = 148, !_bittest(&v59, v58)) )
          _InterlockedAnd((volatile signed __int32 *)v57 + 12, 0xFFFFBFFF);
      }
    }
    goto LABEL_402;
  }
  if ( (*(_DWORD *)a3 & 0x104LL) != 0 )
    goto LABEL_402;
  v20 = 0;
  v141 = 0;
  if ( (*(_DWORD *)(MpData + 864) & 0x10) != 0 )
  {
    memset(v139, 0, sizeof(v139));
    v122 = 0;
    EcpList = 0;
    EcpContext = 0;
    v170 = 0;
    EcpListFromCallbackData = FltGetEcpListFromCallbackData(*(PFLT_FILTER *)(MpData + 16), CallbackData, &EcpList);
    v122 = EcpListFromCallbackData;
    if ( EcpListFromCallbackData < 0 )
      goto LABEL_31;
    v21 = EcpList;
    if ( !EcpList )
      goto LABEL_30;
    EcpListFromCallbackData = FltFindExtraCreateParameter(
                                *(PFLT_FILTER *)(MpData + 16),
                                EcpList,
                                &GUID_ECP_CREATE_REDIRECTION,
                                &EcpContext,
                                &v170);
    v122 = EcpListFromCallbackData;
    if ( EcpListFromCallbackData < 0 )
      goto LABEL_31;
    if ( FltIsEcpAcknowledged(*(PFLT_FILTER *)(MpData + 16), EcpContext) )
    {
      v20 = (unsigned __int16 *)EcpContext;
      v141 = EcpContext;
    }
    else
    {
LABEL_30:
      EcpListFromCallbackData = -1073741823;
      v122 = -1073741823;
    }
LABEL_31:
    v143 = EcpListFromCallbackData;
    if ( !EcpListFromCallbackData )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Diiii(
          WPP_GLOBAL_Control->AttachedDevice,
          v21,
          v14,
          v20[1],
          *(_QWORD *)(v20 + 2),
          *(_QWORD *)(v20 + 6),
          *(_QWORD *)(v20 + 10),
          *(_QWORD *)(v20 + 14));
      *(_DWORD *)v139 = 1;
      *(_WORD *)&v139[4] = v20[1];
      *(_OWORD *)&v139[8] = *(_OWORD *)(v20 + 10);
      *(_OWORD *)&v139[24] = *(_OWORD *)(v20 + 2);
      v64 = 1;
      v14 = 3;
      if ( (v139[4] & 9) == 1 )
        v64 = 3;
      *(_DWORD *)v139 = v64;
    }
  }
  v23 = 0;
  v116 = 0;
  v120 = 0;
  if ( *(_BYTE *)(MpData + 4049) && CurrentThread && (*((_DWORD *)CurrentThread + 72) & 0x40) != 0 )
  {
    if ( (*(_BYTE *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 0x20) != 0 )
      v23 = 32;
    v116 = v23;
    v120 = v23;
  }
  v24 = *(_DWORD *)(MpData + 864);
  if ( (v24 & 0x10) != 0 )
  {
    v55 = *(struct _FLT_FILTER **)(MpData + 16);
    v164 = 0;
    v163 = 0;
    v168 = 0;
    if ( FltGetEcpListFromCallbackData(v55, CallbackData, &v164) >= 0 && v164 )
    {
      _mm_lfence();
      if ( FltFindExtraCreateParameter(v55, v164, &GUID_ECP_CREATE_USER_PROCESS, &v163, &v168) >= 0 )
      {
        _mm_lfence();
        if ( !FltIsEcpFromUserMode(v55, v163) )
        {
          v112[0] = 1;
          v23 |= 0x40020u;
          v115 = v114;
          v8 = v121;
LABEL_186:
          v120 = v23;
          v116 = v23;
          goto LABEL_37;
        }
      }
      v115 = v114;
      v8 = v121;
    }
    v112[0] = 0;
    goto LABEL_37;
  }
  if ( (v24 & 2) != 0 && (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 0x20) != 0 )
  {
    v23 |= 0x40020u;
    goto LABEL_186;
  }
LABEL_37:
  v25 = (char *)Context;
  v26 = *((_QWORD *)Context + 1);
  if ( *(_DWORD *)(v26 + 100) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        56,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        *(_QWORD *)(a2 + 32) + 88LL);
    goto LABEL_67;
  }
  if ( dword_140026A00 == 1 )
  {
    memset(v133, 0, sizeof(v133));
    if ( (*(_DWORD *)(MpData + 864) & 4) != 0 && *(_DWORD *)(v26 + 120) == 27 )
    {
      CsvRevisionECP = MpReadCsvRevisionECP(CallbackData, v133);
      if ( CsvRevisionECP < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        {
          _mm_lfence();
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            26,
            WPP_da25ed7ac0df3f6c27bc2dc1e0325faa_Traceguids,
            (unsigned int)CsvRevisionECP);
          v115 = v114;
          v8 = v121;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_iii(
            WPP_GLOBAL_Control->AttachedDevice,
            v94,
            v14,
            *(_QWORD *)v133,
            *(_QWORD *)&v133[8],
            *(_QWORD *)&v133[16]);
        if ( *(_QWORD *)v133
          && *(_QWORD *)&v133[8]
          && *(_QWORD *)&v133[16]
          && *(_QWORD *)v133 == *((_QWORD *)v25 + 27)
          && *(_OWORD *)&v133[8] == *((_OWORD *)v25 + 14) )
        {
          goto LABEL_41;
        }
      }
      *((_DWORD *)v25 + 8) = 0;
      _InterlockedAnd((volatile signed __int32 *)v25 + 12, 0xFFFFBFFF);
      *(_OWORD *)(v25 + 216) = *(_OWORD *)v133;
      *((_QWORD *)v25 + 29) = *(_QWORD *)&v133[16];
    }
  }
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    WPP_SF_DZ(
      WPP_GLOBAL_Control->AttachedDevice,
      44,
      (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
      *(_DWORD *)(*((_QWORD *)Context + 1) + 4LL),
      (__int64)Context + 240);
  v27 = Context;
  if ( !v8 )
  {
    v28 = *((_QWORD *)Context + 1);
    v29 = (int *)((char *)Context + 32);
    if ( Context == (PFLT_CONTEXT)-32LL || !v28 )
      goto LABEL_92;
    if ( *v29 == 5 && (*(_DWORD *)(MpData + 868) & 0x8000) == 0 )
    {
      v30 = 5;
      goto LABEL_50;
    }
    if ( *((_DWORD *)Context + 9) == *(_DWORD *)(v28 + 144) )
      v30 = *v29;
    else
LABEL_92:
      v30 = 0;
LABEL_50:
    v115 = v30;
    v114 = v30;
LABEL_51:
    v17 = 0;
    v128 = 0;
    v31 = 0;
    goto LABEL_52;
  }
  if ( (v8[42] & 1) == 0 )
  {
    if ( (unsigned __int16)(*(_WORD *)(a2 + 2) - 1) <= 0xFFFCu )
    {
      v30 = 0;
      v114 = 0;
    }
    else
    {
      v67 = (unsigned __int64 *)((char *)Context + 192);
      FltAcquirePushLockShared((PULONG_PTR)Context + 24);
      v68 = v27[26];
      if ( v68 )
        v69 = (char *)(v68 + 24);
      else
        v69 = (char *)(v27 + 4);
      v114 = GetMpFileStateWithSeq_0(v69, v27[1]);
      v30 = v114;
      FltReleasePushLock(v67);
    }
    goto LABEL_51;
  }
  v31 = -1073741595;
  v17 = 3221225701LL;
  v128 = -1073741595;
  v30 = v115;
LABEL_52:
  StreamContext = v17;
  if ( v31 < 0 )
  {
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_402;
    v41 = 45;
LABEL_334:
    EcpContextSize = v17;
    goto LABEL_335;
  }
  if ( v30 == 7 || (unsigned int)(v30 - 2) <= 2 )
  {
    v23 |= 0x40u;
    v116 = v23;
    v120 = v23;
    if ( *(_DWORD *)(*((_QWORD *)Context + 1) + 120LL) == 2 && ((__int64)WPP_MAIN_CB.DeviceExtension & 2) != 0 )
      McTemplateK0x_EtwWriteTransfer(v17, AMFilter_CacheHitEvent, v14, *((unsigned int *)Context + 42));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        46,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        *(_QWORD *)(a2 + 32) + 88LL);
    v32 = *(_DWORD *)(*((_QWORD *)Context + 1) + 120LL);
    switch ( v32 )
    {
      case 2:
        _InterlockedIncrement((volatile signed __int32 *)(MpData + 2888));
        break;
      case 28:
        _InterlockedIncrement((volatile signed __int32 *)(MpData + 2960));
        break;
      case 27:
        _InterlockedIncrement((volatile signed __int32 *)(MpData + 2924));
        break;
    }
    if ( (v23 & 0x20) == 0 || (*((_DWORD *)Context + 12) & 0x4000) != 0 || v30 != 3 )
    {
      if ( (v23 & 0x20) == 0 || v30 != 7 )
        goto LABEL_402;
      if ( !*(_BYTE *)(MpData + 4008) )
      {
        MpSendBlockProcessExecMessage(CallbackData, *((unsigned int *)Context + 64));
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_qZd(
            WPP_GLOBAL_Control->AttachedDevice,
            49,
            (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
            CallbackData->Thread,
            *(_QWORD *)(a2 + 32) + 88LL,
            7);
        CallbackData->IoStatus.Status = MpGetProcessBlockExecStatus(CurrentThread);
        goto LABEL_399;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_Z(
          WPP_GLOBAL_Control->AttachedDevice,
          48,
          WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
          *(_QWORD *)(a2 + 32) + 88LL);
      goto LABEL_402;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(
        WPP_GLOBAL_Control->AttachedDevice,
        47,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        *(_QWORD *)(a2 + 32) + 88LL);
  }
  if ( v30 == 5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_qZd(
        WPP_GLOBAL_Control->AttachedDevice,
        50,
        (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        CallbackData->Thread,
        *(_QWORD *)(a2 + 32) + 88LL,
        5);
    CallbackData->IoStatus.Status = -1073741790;
    CallbackData->IoStatus.Information = 0;
    goto LABEL_401;
  }
  if ( v30 == 16 )
  {
    v95 = 0;
    v96 = MEMORY[0xFFFFF78000000320];
    v138 = (__int64)Context;
    if ( !v8 )
    {
      v95 = _InterlockedCompareExchange64((volatile signed __int64 *)Context + 5, 0, 0);
      v160 = v95;
      LODWORD(v17) = 0;
      v129 = 0;
      v97 = 0;
LABEL_330:
      StreamContext = v17;
      if ( v97 >= 0 )
      {
        if ( !*(_QWORD *)(MpData + 600) || v96 < v95 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_qLZ(
              WPP_GLOBAL_Control->AttachedDevice,
              52,
              (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
              CallbackData->Thread,
              *((_DWORD *)Context + 42),
              (__int64)Context + 240);
          }
          FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
          v105 = -1073739514;
          if ( (*(_DWORD *)(MpData + 864) & 4) == 0 )
            v105 = -1073741790;
          CallbackData->IoStatus.Status = v105;
          CallbackData->IoStatus.Information = 0;
          goto LABEL_402;
        }
        v100 = MpSetStreamState_1(v8, *(unsigned __int16 *)(a2 + 2), Context, 17);
        StreamContext = v100;
        if ( v100 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              53,
              WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
              CallbackData->Thread,
              v100);
          }
          goto LABEL_402;
        }
        v101 = Context;
        if ( v8 )
        {
          if ( (v8[42] & 1) != 0 )
          {
            v102 = -1073741595;
            v130 = -1073741595;
            v103 = -1073741595;
          }
          else
          {
            if ( (unsigned __int16)(*(_WORD *)(a2 + 2) - 1) > 0xFFFCu )
            {
              v104 = (unsigned __int64 *)((char *)Context + 192);
              FltAcquirePushLockShared((PULONG_PTR)Context + 24);
              if ( *((_QWORD *)v101 + 26) )
                v101 = (PFLT_CONTEXT)*((_QWORD *)v101 + 26);
              _InterlockedExchange64((volatile __int64 *)v101 + 5, 0);
              FltReleasePushLock(v104);
            }
            v103 = 0;
            v130 = 0;
            v102 = 0;
          }
        }
        else
        {
          _InterlockedExchange64((volatile __int64 *)Context + 5, 0);
          v102 = 0;
          v130 = 0;
          v103 = 0;
        }
        StreamContext = v102;
        if ( v103 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              54,
              WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
              CallbackData->Thread,
              v102);
          }
          goto LABEL_402;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          WPP_SF_Z(
            WPP_GLOBAL_Control->AttachedDevice,
            55,
            WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
            (char *)Context + 240);
        v23 = v116;
        goto LABEL_67;
      }
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_402;
      v41 = 51;
      goto LABEL_334;
    }
    if ( (v8[42] & 1) != 0 )
    {
      v97 = -1073741595;
    }
    else
    {
      if ( (unsigned __int16)(*(_WORD *)(a2 + 2) - 1) <= 0xFFFCu )
      {
        LODWORD(v17) = 0;
        v129 = 0;
        v97 = 0;
        goto LABEL_330;
      }
      v163 = (char *)Context + 192;
      FltAcquirePushLockShared((PULONG_PTR)Context + 24);
      v98 = *(_QWORD *)(v138 + 208);
      if ( v98 )
      {
        v99 = _InterlockedCompareExchange64((volatile signed __int64 *)(v98 + 40), 0, 0);
        v161 = v99;
      }
      else
      {
        v99 = _InterlockedCompareExchange64((volatile signed __int64 *)(v138 + 40), 0, 0);
        v146 = v99;
      }
      v95 = v99;
      FltReleasePushLock((PULONG_PTR)v163);
      v97 = 0;
    }
    v129 = v97;
    LODWORD(v17) = v97;
    goto LABEL_330;
  }
LABEL_67:
  v33 = *(_DWORD *)(*((_QWORD *)Context + 1) + 120LL);
  switch ( v33 )
  {
    case 2:
      _InterlockedIncrement((volatile signed __int32 *)(MpData + 2884));
      break;
    case 28:
      _InterlockedIncrement((volatile signed __int32 *)(MpData + 2956));
      break;
    case 27:
      _InterlockedIncrement((volatile signed __int32 *)(MpData + 2920));
      break;
  }
  if ( (*(_DWORD *)(MpData + 868) & 0x10) != 0 && !*(_BYTE *)(MpData + 208) )
  {
    v155 = KeGetCurrentThread();
    v148 = v155;
    if ( IoThreadToProcess(v155) != *(PEPROCESS *)(MpData + 232) )
    {
      v149 = KeGetCurrentThread();
      v150 = v149;
      if ( IoThreadToProcess(v149) != *(PEPROCESS *)(MpData + 256) )
      {
        if ( *(_DWORD *)(MpData + 2440) != 1 )
        {
          v34 = CurrentThread;
          if ( !CurrentThread )
            goto LABEL_111;
          if ( (*((_DWORD *)CurrentThread + 14) & 1) == 0 )
          {
LABEL_108:
            if ( v34 )
            {
              v47 = (unsigned __int8 (__fastcall *)(PFLT_CALLBACK_DATA, __int64, PFLT_CONTEXT, struct _KTHREAD *))*((_QWORD *)v34 + 11);
              if ( v47 && v47(CallbackData, a2, Context, v34) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_qZZ(
                    WPP_GLOBAL_Control->AttachedDevice,
                    57,
                    (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
                    CallbackData->Thread,
                    *(_QWORD *)(a2 + 32) + 88LL,
                    *((_QWORD *)v34 + 16));
                }
                goto LABEL_402;
              }
              if ( (*((_DWORD *)v34 + 14) & 0x4000000) != 0 )
              {
                v23 |= 0x100u;
                v120 = v23;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_Z(
                    WPP_GLOBAL_Control->AttachedDevice,
                    58,
                    WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
                    *(_QWORD *)(a2 + 32) + 88LL);
                }
              }
            }
LABEL_111:
            v48 = v131;
            if ( v131 && (*((_DWORD *)v131 + 10) & 0x200) != 0 )
            {
              v86 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(MpData + 4224));
              v87 = v86;
              if ( v86 )
              {
                memset(v86, 0, 0x60u);
                _InterlockedOr((volatile signed __int32 *)v87, 1u);
                *((_DWORD *)v87 + 2) = CallbackData->Iopb->Parameters.Create.ShareAccess;
                *((_DWORD *)v87 + 3) = CallbackData->Iopb->Parameters.Create.Options;
                *((_DWORD *)v87 + 1) = v23;
                *((_OWORD *)v87 + 1) = FileInformation;
                *((_OWORD *)v87 + 2) = v172;
                *((_QWORD *)v87 + 6) = v173;
                *(_OWORD *)(v87 + 56) = *(_OWORD *)v139;
                *(_OWORD *)(v87 + 72) = *(_OWORD *)&v139[16];
                *((_QWORD *)v87 + 11) = *(_QWORD *)&v139[32];
                *((_QWORD *)v131 + 12) = v87;
                if ( !(unsigned __int8)IsThisCallBeingThrottled() )
                  MpSendOSCopyHintTelemetry(0);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
                {
                  WPP_SF_qZ(
                    WPP_GLOBAL_Control->AttachedDevice,
                    60,
                    (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
                    CallbackData->Thread,
                    *(_QWORD *)(a2 + 32) + 88LL);
                }
                goto LABEL_402;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
              {
                v151 = KeGetCurrentThread();
                WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids, v151);
              }
              v48[10] &= ~0x200u;
            }
            v123 = 0;
            v49 = CurrentThread;
            v50 = MpScanFile(
                    v8,
                    CallbackData,
                    a2,
                    3,
                    v23,
                    0,
                    &FileInformation,
                    *(_DWORD *)(*(_QWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 8) + 12LL),
                    v139,
                    Context,
                    CurrentThread,
                    v131);
            v114 = v50;
            v51 = 0;
            v52 = 0;
            v168 = 0;
            v123 = 0;
            if ( v50 == 7 )
            {
              if ( (v23 & 0x20) == 0 )
              {
                v119 = 0;
                v53 = 0;
                goto LABEL_116;
              }
              if ( *(_BYTE *)(MpData + 4008) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
                {
                  if ( v49 )
                    v88 = *((_QWORD *)v49 + 16);
                  else
                    v88 = 0;
                  WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_ddfeb2d17970385cb7e6e54739bfb2ed_Traceguids, v88);
                  v52 = v168;
                  v51 = 0;
                }
                v119 = 0;
                v53 = 0;
                goto LABEL_116;
              }
            }
            if ( (unsigned int)(v50 - 5) > 2 && v50 != 16 )
            {
              v53 = 2;
              v119 = 2;
LABEL_116:
              if ( v53 != 1 )
                goto LABEL_402;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
              {
                goto LABEL_400;
              }
              switch ( v52 )
              {
                case 1u:
                  v54 = "bad";
                  break;
                case 2u:
                  v54 = "HIPS blocked for execution";
                  break;
                case 3u:
                  v54 = "blocked access";
                  break;
                default:
                  v54 = "blocked for execution";
                  if ( v52 != 4 )
                    v54 = "unknown";
                  break;
              }
              WPP_SF_qsDZ(
                WPP_GLOBAL_Control->AttachedDevice,
                61,
                (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
                CallbackData->Thread,
                (__int64)v54,
                *((_DWORD *)Context + 42),
                (__int64)Context + 240);
LABEL_399:
              v51 = 0;
LABEL_400:
              CallbackData->IoStatus.Information = v51;
LABEL_401:
              FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
              goto LABEL_402;
            }
            v106 = v50 - 5;
            if ( v106 )
            {
              v107 = v106 - 1;
              if ( v107 )
              {
                if ( v107 != 1 )
                {
                  v52 = 1;
                  v108 = -1073739514;
                  if ( (*(_DWORD *)(MpData + 864) & 4) == 0 )
                    v108 = -1073741790;
                  CallbackData->IoStatus.Status = v108;
                  goto LABEL_391;
                }
                ProcessBlockExecStatus = MpGetProcessBlockExecStatus(v49);
LABEL_390:
                CallbackData->IoStatus.Status = ProcessBlockExecStatus;
LABEL_391:
                CallbackData->IoStatus.Information = v51;
                v123 = v52;
                v119 = 1;
                v53 = 1;
                goto LABEL_116;
              }
              v52 = 2;
            }
            else
            {
              v52 = 3;
            }
            ProcessBlockExecStatus = -1073741790;
            goto LABEL_390;
          }
        }
        if ( !*(_BYTE *)(MpData + 4008) )
        {
          v35 = *((_DWORD *)Context + 42);
          v36 = *((_QWORD *)Context + 1);
          v163 = (PVOID)v36;
          v37 = v35;
          v168 = v35 % dword_1400269F0;
          if ( *(_DWORD *)(v36 + 120) == 2 && *(_QWORD *)(v36 + 440) )
          {
            KeEnterCriticalRegion();
            ExAcquireResourceSharedLite((PERESOURCE)((char *)v163 + 288), 1u);
            v38 = *((_QWORD *)v163 + 55);
            for ( i = *(__int64 **)(v38 + 16LL * v168); ; i = (__int64 *)*i )
            {
              if ( i == (__int64 *)(v38 + 16LL * v168) )
              {
                v46 = 0;
                goto LABEL_104;
              }
              if ( *((_DWORD *)i + 4) == v37 )
                break;
            }
            v46 = 1;
LABEL_104:
            ExReleaseResourceLite((PERESOURCE)((char *)v163 + 288));
            KeLeaveCriticalRegion();
          }
          else
          {
            v46 = byte_1400269F4 == 0;
          }
          v118 = v46;
          if ( v46 || (v23 & 0x20) != 0 )
          {
            v34 = CurrentThread;
            goto LABEL_108;
          }
        }
      }
    }
  }
LABEL_402:
  if ( v8 )
    FltReleaseContext(v8);
  if ( v131 )
    FltReleaseContext(v131);
  result = Context;
  *a5 = Context;
  return result;
}

```

## disassembly

```asm
0x140051af0  mov     r11, rsp
0x140051af3  push    rbx
0x140051af4  push    rsi
0x140051af5  push    rdi
0x140051af6  push    r12
0x140051af8  push    r13
0x140051afa  push    r14
0x140051afc  push    r15
0x140051afe  sub     rsp, 260h
0x140051b05  mov     rax, cs:__security_cookie
0x140051b0c  xor     rax, rsp
0x140051b0f  mov     [rsp+298h+var_48], rax
0x140051b17  mov     [rsp+298h+var_1E8], r9
0x140051b1f  mov     rdi, r8
0x140051b22  mov     r15, rdx
0x140051b25  mov     r13, rcx
0x140051b28  mov     r12, [rsp+298h+arg_20]
0x140051b30  mov     [rsp+298h+var_140], r12
0x140051b38  xor     r9d, r9d
0x140051b3b  mov     [r11-0B0h], r9
0x140051b42  mov     [r11-1D0h], r9
0x140051b49  mov     eax, r9d
0x140051b4c  mov     [rsp+298h+var_22C], eax
0x140051b50  mov     [rsp+298h+var_230], eax
0x140051b54  mov     r14d, r9d
0x140051b57  mov     [r11-208h], r9
0x140051b5e  mov     ebx, r9d
0x140051b61  mov     [rsp+298h+var_1C8], rbx
0x140051b69  xor     sil, sil
0x140051b6c  mov     [rsp+298h+var_238], sil
0x140051b71  xorps   xmm0, xmm0
0x140051b74  movups  [rsp+298h+var_180], xmm0
0x140051b7c  movups  [rsp+298h+var_170], xmm0
0x140051b84  mov     [r11-160h], rax
0x140051b8b  xorps   xmm1, xmm1
0x140051b8e  movups  xmmword ptr [r11-70h], xmm1
0x140051b93  movups  xmmword ptr [r11-60h], xmm1
0x140051b98  mov     [r11-50h], rax
0x140051b9c  mov     edx, r9d
0x140051b9f  mov     ecx, r9d
0x140051ba2  mov     [r11-7Ch], ecx
0x140051ba6  test    byte ptr [r8], 1
0x140051baa  jz      loc_140052FD3
0x140051bb0  mov     r8, [r15+28h]
0x140051bb4  test    r8, r8
0x140051bb7  jnz     loc_140052B57
0x140051bbd  lea     r8, [rsp+298h+Context]; Context
0x140051bc5  mov     rdx, [r15+20h]; FileObject
0x140051bc9  mov     rcx, [r15+18h]; Instance
0x140051bcd  call    cs:__imp_FltGetStreamContext
0x140051bd4  nop     dword ptr [rax+rax+00h]
0x140051bd9  mov     [rsp+298h+var_234], eax
0x140051bdd  mov     rdx, r15
0x140051be0  mov     rcx, r13; CallbackData
0x140051be3  test    eax, eax
0x140051be5  js      loc_140052613
0x140051beb  mov     byte ptr [rsp+298h+LengthReturned], sil
0x140051bf0  mov     rax, [rsp+298h+Context]
0x140051bf8  mov     [rsp+298h+EcpContextSize], rax
0x140051bfd  mov     r9, rdi
0x140051c00  mov     r8, r14
0x140051c03  call    MpPostCreateUpdateStreamContext
0x140051c08  mov     [rsp+298h+var_234], eax
0x140051c0c  test    eax, eax
0x140051c0e  js      loc_140053474
0x140051c14  mov     rsi, [rsp+298h+Context]
0x140051c1c  cmp     rsi, cs:BreakOnStream
0x140051c23  jz      loc_1400534EA
0x140051c29  lea     rsi, WPP_GLOBAL_Control
0x140051c30  mov     rax, [rsp+298h+Context]
0x140051c38  test    byte ptr [rax+30h], 1
0x140051c3c  setz    cl
0x140051c3f  test    qword ptr [rdi], 2000h
0x140051c46  setz    al
0x140051c49  test    al, cl
0x140051c4b  jz      loc_140053E97
0x140051c51  lea     r9, [rsp+298h+var_1D0]
0x140051c59  mov     r8, rdi
0x140051c5c  mov     rdx, r15
0x140051c5f  mov     rcx, r13
0x140051c62  call    MpUpdateHandleContextOnPostCreate
0x140051c67  cmp     [rsp+298h+var_1D0], 0
0x140051c70  jz      loc_14005358F
0x140051c76  movzx   eax, byte ptr [rdi+18h]
0x140051c7a  test    al, al
0x140051c7c  jnz     loc_1400535C8
0x140051c82  mov     rax, [r13+20h]
0x140051c86  mov     edx, eax
0x140051c88  cmp     rax, 2
0x140051c8c  jz      loc_1400522A7
0x140051c92  test    rax, rax
0x140051c95  jz      loc_1400522A7
0x140051c9b  cmp     rax, 3
0x140051c9f  jz      loc_1400522A7
0x140051ca5  mov     rsi, [rsp+298h+Context]
0x140051cad  movzx   ecx, word ptr [r15+2]
0x140051cb2  test    r14, r14
0x140051cb5  jnz     loc_140052A95
0x140051cbb  xor     eax, eax
0x140051cbd  xor     edx, edx
0x140051cbf  lock cmpxchg [rsi+0B0h], rdx
0x140051cc8  mov     rbx, rax
0x140051ccb  mov     [rsp+298h+var_F8], rax
0x140051cd3  mov     [rsp+298h+var_1C8], rax
0x140051cdb  mov     ecx, edx
0x140051cdd  mov     [rsp+298h+var_1E0], edx
0x140051ce4  mov     eax, edx
0x140051ce6  mov     [rsp+298h+var_234], ecx
0x140051cea  test    eax, eax
0x140051cec  js      loc_140052210
0x140051cf2  mov     eax, [rdi]
0x140051cf4  test    rax, 104h
0x140051cfa  jnz     short loc_140051D3B
0x140051cfc  cmp     qword ptr [r13+20h], 1
0x140051d01  jnz     short loc_140051D3B
0x140051d03  mov     rax, [r15+20h]
0x140051d07  mov     [rsp+298h+var_A0], rax
0x140051d0f  mov     eax, [rax+50h]
0x140051d12  test    al, 8
0x140051d14  jnz     short loc_140051D3B
0x140051d16  test    rbx, rbx
0x140051d19  jz      short loc_140051D3B
0x140051d1b  mov     rax, [rsp+298h+Context]
0x140051d23  mov     rcx, [rax+8]
0x140051d27  mov     eax, [rcx+54h]
0x140051d2a  test    al, 10h
0x140051d2c  jnz     short loc_140051D3B
0x140051d2e  mov     rsi, [r13+8]
0x140051d32  test    rsi, rsi
0x140051d35  jnz     loc_1400522EE
0x140051d3b  cmp     rbx, 4
0x140051d3f  jle     loc_1400526FD
0x140051d45  mov     eax, [rdi]
0x140051d47  test    rax, 104h
0x140051d4d  jnz     loc_140053E97
0x140051d53  xor     r9d, r9d
0x140051d56  mov     edi, r9d
0x140051d59  mov     [rsp+298h+var_150], r9
0x140051d61  mov     rcx, cs:MpData
0x140051d68  mov     eax, [rcx+360h]
0x140051d6e  test    al, 10h
0x140051d70  jz      loc_140051E71
0x140051d76  xorps   xmm0, xmm0
0x140051d79  xor     eax, eax
0x140051d7b  movups  [rsp+298h+var_180], xmm0
0x140051d83  movups  [rsp+298h+var_170], xmm0
0x140051d8b  mov     [rsp+298h+var_160], rax
0x140051d93  mov     [rsp+298h+var_200], r9d
0x140051d9b  mov     [rsp+298h+EcpList], r9
0x140051da3  mov     [rsp+298h+EcpContext], r9
0x140051dab  mov     [rsp+298h+var_78], r9d
0x140051db3  lea     r8, [rsp+298h+EcpList]; EcpList
0x140051dbb  mov     rdx, r13; CallbackData
0x140051dbe  mov     rcx, [rcx+10h]; Filter
0x140051dc2  call    cs:__imp_FltGetEcpListFromCallbackData
0x140051dc9  nop     dword ptr [rax+rax+00h]
0x140051dce  mov     ebx, eax
0x140051dd0  mov     [rsp+298h+var_200], eax
0x140051dd7  test    eax, eax
0x140051dd9  js      loc_140051E5F
0x140051ddf  mov     rdx, [rsp+298h+EcpList]; EcpList
0x140051de7  test    rdx, rdx
0x140051dea  jz      short loc_140051E53
0x140051dec  lea     rax, [rsp+298h+var_78]
0x140051df4  mov     [rsp+298h+EcpContextSize], rax; EcpContextSize
0x140051df9  lea     r9, [rsp+298h+EcpContext]; EcpContext
0x140051e01  lea     r8, GUID_ECP_CREATE_REDIRECTION; EcpType
0x140051e08  mov     rcx, cs:MpData
0x140051e0f  mov     rcx, [rcx+10h]; Filter
0x140051e13  call    cs:__imp_FltFindExtraCreateParameter
0x140051e1a  nop     dword ptr [rax+rax+00h]
0x140051e1f  mov     ebx, eax
0x140051e21  mov     [rsp+298h+var_200], eax
0x140051e28  test    eax, eax
0x140051e2a  js      short loc_140051E5F
0x140051e2c  mov     rdx, [rsp+298h+EcpContext]; EcpContext
0x140051e34  mov     rcx, cs:MpData
0x140051e3b  mov     rcx, [rcx+10h]; Filter
0x140051e3f  call    cs:__imp_FltIsEcpAcknowledged
0x140051e46  nop     dword ptr [rax+rax+00h]
0x140051e4b  test    al, al
0x140051e4d  jnz     loc_140052A30
0x140051e53  mov     ebx, 0C0000001h
0x140051e58  mov     [rsp+298h+var_200], ebx
0x140051e5f  mov     [rsp+298h+var_144], ebx
0x140051e66  test    ebx, ebx
0x140051e68  jz      loc_14005293D
0x140051e6e  xor     r9d, r9d
0x140051e71  lea     rbx, WPP_GLOBAL_Control
0x140051e78  mov     edi, r9d
0x140051e7b  mov     [rsp+298h+var_228], r9d
0x140051e80  mov     [rsp+298h+var_210], r9d
0x140051e88  mov     rdx, cs:MpData
0x140051e8f  cmp     byte ptr [rdx+0FD1h], 0
0x140051e96  jz      short loc_140051EB3
0x140051e98  mov     rax, [rsp+298h+var_1E8]
0x140051ea0  test    rax, rax
0x140051ea3  jz      short loc_140051EB3
0x140051ea5  mov     eax, [rax+120h]
0x140051eab  test    al, 40h
0x140051ead  jnz     loc_140052C28
0x140051eb3  mov     eax, [rdx+360h]
0x140051eb9  test    al, 10h
0x140051ebb  jnz     loc_140052573
0x140051ec1  test    al, 2
0x140051ec3  jnz     loc_1400536DE
0x140051ec9  mov     rsi, [rsp+298h+Context]
0x140051ed1  mov     rdx, [rsi+8]
0x140051ed5  cmp     dword ptr [rdx+64h], 0
0x140051ed9  jnz     loc_140052754
0x140051edf  cmp     cs:dword_140026A00, 1
0x140051ee6  jnz     short loc_140051F19
0x140051ee8  xorps   xmm0, xmm0
0x140051eeb  xor     eax, eax
0x140051eed  movups  xmmword ptr [rsp+298h+var_1C0], xmm0
0x140051ef5  mov     qword ptr [rsp+298h+var_1C0+10h], rax
0x140051efd  mov     rax, cs:MpData
0x140051f04  mov     ecx, [rax+360h]
0x140051f0a  test    cl, 4
0x140051f0d  jz      short loc_140051F19
0x140051f0f  cmp     dword ptr [rdx+78h], 1Bh
0x140051f13  jz      loc_1400536FC
0x140051f19  mov     rcx, cs:WPP_GLOBAL_Control
0x140051f20  cmp     rcx, rbx
0x140051f23  jz      short loc_140051F30
0x140051f25  mov     eax, [rcx+2Ch]
0x140051f28  test    al, 4
0x140051f2a  jnz     loc_140053817
0x140051f30  mov     rbx, [rsp+298h+Context]
0x140051f38  movzx   ecx, word ptr [r15+2]
0x140051f3d  test    r14, r14
0x140051f40  jnz     loc_140052A0A
0x140051f46  mov     rdx, [rbx+8]
0x140051f4a  add     rbx, 20h ; ' '
0x140051f4e  jz      loc_14005229F
0x140051f54  test    rdx, rdx
0x140051f57  jz      loc_14005229F
0x140051f5d  cmp     dword ptr [rbx], 5
0x140051f60  jz      loc_1400528A5
0x140051f66  mov     eax, [rdx+90h]
0x140051f6c  cmp     [rbx+4], eax
0x140051f6f  jnz     loc_14005229F
0x140051f75  mov     ebx, [rbx]
0x140051f77  mov     [rsp+298h+var_22C], ebx
0x140051f7b  mov     [rsp+298h+var_230], ebx
0x140051f7f  mov     ecx, r9d
0x140051f82  mov     [rsp+298h+var_1DC], ecx
0x140051f89  mov     eax, r9d
0x140051f8c  mov     [rsp+298h+var_234], ecx
0x140051f90  test    eax, eax
0x140051f92  js      loc_140053850
0x140051f98  cmp     ebx, 7
0x140051f9b  jz      short loc_140051FA9
0x140051f9d  lea     eax, [rbx-2]
0x140051fa0  cmp     eax, 2
0x140051fa3  ja      loc_1400526F1
0x140051fa9  or      edi, 40h
0x140051fac  mov     [rsp+298h+var_228], edi
0x140051fb0  mov     [rsp+298h+var_210], edi
0x140051fb7  mov     rsi, [rsp+298h+Context]
0x140051fbf  mov     rax, [rsi+8]
0x140051fc3  cmp     dword ptr [rax+78h], 2
0x140051fc7  jnz     short loc_140051FD6
0x140051fc9  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 2
0x140051fd0  jnz     loc_140052F65
0x140051fd6  mov     rcx, cs:WPP_GLOBAL_Control
0x140051fdd  lea     rsi, WPP_GLOBAL_Control
0x140051fe4  cmp     rcx, rsi
0x140051fe7  jnz     loc_1400522BE
0x140051fed  mov     rax, [rsp+298h+Context]
0x140051ff5  mov     rcx, [rax+8]
0x140051ff9  mov     eax, [rcx+78h]
0x140051ffc  cmp     eax, 2
0x140051fff  jnz     loc_140052B3B
0x140052005  mov     rax, cs:MpData
0x14005200c  lock inc dword ptr [rax+0B48h]
0x140052013  mov     edx, edi
0x140052015  and     edx, 20h
0x140052018  jz      loc_14005223D
0x14005201e  mov     rax, [rsp+298h+Context]
0x140052026  test    dword ptr [rax+30h], 4000h
0x14005202d  jnz     loc_14005223D
0x140052033  cmp     ebx, 3
0x140052036  jnz     loc_14005223D
0x14005203c  mov     rcx, cs:WPP_GLOBAL_Control
0x140052043  cmp     rcx, rsi
0x140052046  jnz     loc_140052F80
0x14005204c  cmp     ebx, 5
0x14005204f  jz      loc_14005387D
0x140052055  cmp     ebx, 10h
0x140052058  jz      loc_1400538D3
0x14005205e  lea     rbx, WPP_GLOBAL_Control
0x140052065  mov     rax, [rsp+298h+Context]
0x14005206d  mov     rcx, [rax+8]
0x140052071  mov     eax, [rcx+78h]
0x140052074  cmp     eax, 2
0x140052077  jnz     loc_1400529EE
0x14005207d  mov     rax, cs:MpData
0x140052084  lock inc dword ptr [rax+0B44h]
0x14005208b  mov     rax, cs:MpData
  ... truncated ...
```
