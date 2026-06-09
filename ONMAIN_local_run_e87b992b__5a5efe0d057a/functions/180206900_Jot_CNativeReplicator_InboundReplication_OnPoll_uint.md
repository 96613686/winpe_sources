# Jot::CNativeReplicator_InboundReplication::OnPoll(uint *)

- ea: `0x180206900`
- end: `0x180209cf8`
- name: `?OnPoll@CNativeReplicator_InboundReplication@Jot@@MEAAXPEAI@Z`
- size: `13304`
- prototype: `void __fastcall(Jot::CNativeReplicator_InboundReplication *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `142`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x18002efb0`
- `0x18002fdcc`
- `0x180030ef0`
- `0x180032260`
- `0x18004f8cc`
- `0x180054864`
- `0x18005ac04`
- `0x18005fdcc`
- `0x180062a34`
- `0x18006bb90`
- `0x18006f0e0`
- `0x180071c90`
- `0x18007293c`
- `0x180073ca0`
- `0x180074020`
- `0x18007685c`
- `0x180078d30`
- `0x18007b2e4`
- `0x18007c280`
- `0x18007c4e0`
- `0x18007cad0`
- `0x18007cdf0`
- `0x18007d0a0`
- `0x18007d478`
- `0x18007d75c`
- `0x18007d810`
- `0x1800806c4`
- `0x180090cb0`
- `0x180092a8c`
- `0x180092ac4`
- `0x1800933c0`
- `0x18009342c`
- `0x1800982ed`
- `0x180098690`
- `0x18009cd7c`
- `0x18009dcf0`
- `0x18009dec0`
- `0x1800aeef0`
- `0x1800af7bc`
- `0x1800afb94`
- `0x1800b051c`
- `0x1800b0a50`
- `0x1800b0d70`
- `0x1800b50d0`
- `0x1800c4978`
- `0x1800c49e0`
- `0x1800c5b10`
- `0x1800c5d60`
- `0x1800c6068`
- `0x1800c60c0`

## import_xrefs

- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180209572`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180209572`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1802081b8`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1802081b8`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1802076bc`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1802094ca`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1802076bc`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1802094ca`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1802096d7`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1802096d7`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18020820d`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180208b34`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1802096b5`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18020820d`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180208b34`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1802096b5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802095a3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802095a3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18020878a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180208cc8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18020878a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180208cc8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180207587`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180207587`

## pseudocode

```c
void __fastcall Jot::CNativeReplicator_InboundReplication::OnPoll(Jot::RevisionTimeLogger **this, unsigned int *a2)
{
  unsigned int *v2; // rsi
  Jot::RevisionTimeLogger *v4; // r14
  struct Jot::CNetworkStatus *OneNoteDotComNetworkStatusInstance; // rax
  Jot *v6; // rcx
  void (__fastcall ***v7)(_QWORD, GUID *, struct Jot::IGraphNode **); // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  void (__fastcall ***v10)(_QWORD, GUID *, struct Jot::IGraphNode **); // rax
  struct Jot::IGraphNode *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 BackingRevisionStore; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  _QWORD *v21; // rbx
  Jot::RevisionTimeLogger *v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  Jot::RevisionTimeLogger *v27; // rcx
  __int64 v28; // rax
  struct Jot::IGraphSpaceNode *v29; // rdx
  __int64 v30; // r8
  Jot::StaticContextReplication *v31; // rax
  char v32; // bl
  char v33; // di
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  Jot::StaticContextReplication *v37; // rax
  struct Jot::IGraphNode *v38; // rcx
  char v39; // bl
  __m128i si128; // xmm9
  const wchar_t *v41; // xmm8_8
  __m128i *v42; // rax
  __m128i v43; // xmm6
  __m128i v44; // xmm7
  const wchar_t *v45; // rdx
  const wchar_t *v46; // r9
  bool v47; // bl
  void (__fastcall *v48)(Jot::RevisionTimeLogger **, __int64); // rbx
  __int64 v49; // rax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // r9d
  __int64 v53; // rax
  unsigned int v54; // edx
  MsoCF *v55; // rcx
  struct Jot::IGraphNode *v56; // rbx
  const struct MsoCF::PropertyInfo *v57; // rax
  unsigned int v58; // edx
  struct Jot::IGraphNode *v59; // rbx
  const struct MsoCF::PropertyInfo *v60; // rdi
  __int64 v61; // r9
  char v62; // al
  unsigned __int64 v63; // r9
  _DWORD *v64; // rax
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rax
  _DWORD *v69; // rax
  Jot::StaticContextReplication *v70; // rcx
  __int64 (*v71)(void); // rax
  Jot::StaticContextReplication *v72; // rdi
  __int64 v73; // rax
  Jot::StaticContextReplication *v74; // rbx
  __int64 v75; // rax
  _QWORD *v76; // rax
  _QWORD *v77; // rsi
  void *const *TailAddr; // rax
  __int64 *v79; // rsi
  void *v80; // rax
  void *v81; // rdx
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rdx
  struct Jot::IGraphNode *v86; // rax
  struct Jot::IGraphNode *v87; // rcx
  void (__fastcall *v88)(struct Jot::IGraphNode *, GUID *, Jot::StaticContextReplication **); // rax
  void (__fastcall *v89)(struct Jot::IGraphNode *, GUID *, Jot **); // rax
  unsigned int v90; // edx
  bool v91; // r8
  unsigned int v92; // eax
  void *v93; // rdx
  int v94; // eax
  struct Jot::IGraphNode *v95; // rbx
  bool (*v96)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *); // r9
  char v97; // al
  unsigned int v98; // edx
  Jot *v99; // rax
  void (__fastcall *v100)(Jot::RevisionTimeLogger **, __m128i *); // rbx
  Jot::StaticContextReplication *v101; // rsi
  Jot::StaticContextReplication *v102; // rcx
  void (__fastcall *v103)(Jot::RevisionTimeLogger **, __m128i *); // rbx
  __int64 v104; // rax
  __m128i *v105; // rdx
  Jot::StaticContextReplication *v106; // rcx
  bool (*v107)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *); // r9
  char v108; // al
  int v109; // ecx
  __int32 v110; // edx
  Jot::RevisionTimeLogger *v111; // r8
  struct Jot::IServerRevisionStore *v112; // rdi
  __int64 (__fastcall *v113)(struct Jot::IServerRevisionStore *, Jot::StaticContextReplication **, __int64, __int64); // rbx
  __int64 v114; // rax
  __int64 v115; // rax
  _QWORD *v116; // rax
  __int64 v117; // rax
  struct Jot::IServerRevisionStore *v118; // rax
  _QWORD *v119; // rax
  __int64 v120; // rax
  __int64 v121; // rax
  __int64 v122; // r8
  _QWORD *v123; // rax
  Jot::StaticContextReplication *v124; // rbx
  _QWORD *v125; // rax
  __int64 Child; // rax
  Jot::StaticContextReplication *v127; // rbx
  Jot::StaticContextReplication *v128; // rcx
  __int64 v129; // rax
  Jot *v130; // r15
  _QWORD *v131; // rbx
  __int64 v132; // rax
  __int64 v133; // rax
  __int64 ContainingSection; // rax
  __int64 v135; // rcx
  Jot::CGraphIterator *v136; // rdi
  __int64 v137; // r15
  __int64 v138; // r14
  __int64 v139; // rsi
  _QWORD *v140; // rbx
  _QWORD *v141; // rax
  Jot::CReplicatorWithBranchBase *v142; // rsi
  __int64 v143; // rax
  char v144; // bl
  __int64 v145; // r8
  struct Jot::IRevision_MayNotBeOptimal *v146; // rbx
  struct Jot::IRevision **v147; // r14
  struct Jot::IRevision_MayNotBeOptimal *v148; // r8
  struct Jot::IGraphNode *v149; // rdx
  void (__fastcall ***v150)(_QWORD, GUID *, struct Jot::IGraphNode **); // rax
  Jot::StaticContextReplication *v151; // rbx
  unsigned int v152; // edx
  bool v153; // r8
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 v156; // rax
  Jot *v157; // rax
  const void *v158; // rax
  Jot *v159; // rax
  const struct std::exception_ptr *v160; // rdx
  const void *v161; // rax
  _QWORD *v162; // rax
  MsoCF::IAtom *v163; // rcx
  unsigned int v164; // ebx
  __int64 v165; // rax
  struct Jot::IGraphSpaceNode **v166; // r9
  Jot::StaticContextReplication *v167; // rbx
  void (__fastcall *v168)(Jot::StaticContextReplication *, _QWORD); // rdi
  _QWORD *v169; // rax
  void (__fastcall *v170)(Jot::RevisionTimeLogger **, __int64); // rbx
  __int64 v171; // rax
  __int64 v172; // rax
  void (__fastcall *v173)(Jot::RevisionTimeLogger **, __int64); // rbx
  __int64 v174; // rax
  __int64 v175; // rax
  unsigned int v176; // eax
  __int64 v177; // rax
  int v178; // eax
  __int64 v179; // rax
  _QWORD *v180; // rax
  Jot::StaticContextReplication *v181; // rbx
  char v182; // al
  int v183; // esi
  void (__fastcall ***v184)(_QWORD, GUID *, Jot::StaticContextReplication **); // rax
  Jot::StaticContextReplication *v185; // rax
  Jot::StaticContextReplication *v186; // rcx
  Jot::RevisionTimeLogger **v187; // rax
  Jot::RevisionTimeLogger *v188; // rdx
  Jot::RevisionTimeLogger *v189; // rcx
  __int64 v190; // rbx
  _QWORD *v191; // rax
  _QWORD *v192; // rbx
  void (__fastcall *v193)(Jot::RevisionTimeLogger **, __int64); // rbx
  __int64 v194; // rax
  __int64 v195; // rax
  __int64 v196; // rax
  __int64 v197; // rax
  __int64 v198; // rax
  Jot::StaticContextReplication *v199; // rbx
  Jot *v200; // rcx
  const struct MsoCF::ExtendedGUID *v201; // rdi
  __int64 v202; // rax
  struct Jot::IObjectSpaceRevisionCache *v203; // rax
  const struct _GUID *v204; // r9
  __int64 v205; // rax
  void (__fastcall ***v206)(_QWORD, GUID *, struct Jot::IGraphNode **); // rax
  __int64 v207; // rax
  Jot::RevisionTimeLogger *v208; // rcx
  const void *v209; // rax
  __int64 v210; // rax
  Jot::StaticContextReplication **KnowledgeFromPropertySet; // rax
  __int64 v212; // rax
  __int64 v213; // rax
  int v214; // edx
  int v215; // r8d
  int v216; // r9d
  unsigned int v217; // ebx
  Jot::GraphSpaceEditor *v218; // rax
  unsigned int v219; // r8d
  bool (*v220)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *); // r10
  char v221; // al
  __int32 v222; // edx
  int v223; // ebx
  struct Jot::IRevision *v224; // rdx
  bool v225; // r8
  __int64 v226; // rax
  __int64 v227; // rax
  __int64 CachedFileIdentifier; // rax
  __int64 v229; // rax
  __int64 v230; // rax
  struct Jot::IGraphNode *v231; // rax
  Jot::StaticContextReplication *v232; // rcx
  unsigned int v233; // edx
  const struct MsoCF::PropertyInfo *v234; // rdx
  bool (*v235)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *); // r9
  char v236; // al
  void (__fastcall ***v237)(_QWORD, GUID *, Jot::StaticContextReplication **); // rax
  __int64 v238; // rax
  __int64 v239; // rax
  __int64 v240; // rax
  unsigned int v241; // r8d
  unsigned int v242; // r8d
  struct Jot::IGraphNode *v243; // rdx
  _QWORD *BranchBaseRevision; // rax
  Jot::RevisionTimeLogger *v245; // rcx
  __int64 v246; // rax
  Jot::RevisionTimeLogger *v247; // rcx
  Jot::RevisionTimeLogger *v248; // rcx
  __int64 v249; // rax
  const void *v250; // rax
  unsigned int v251; // r9d
  int v252; // edx
  int v253; // ecx
  int v254; // r8d
  int v255; // r9d
  void (__fastcall *v256)(struct Jot::IGraphNode *, GUID *, Jot **); // rax
  Jot::CReplicatorWithBranchBase *v257; // rcx
  void (__fastcall *v258)(Jot::RevisionTimeLogger **, _OWORD *); // rbx
  struct Jot::IGraphSpace *v259; // rax
  __int64 v260; // rax
  __int64 v261; // rax
  __int64 v262; // rax
  struct Csi::IKnowledge *v263; // r9
  const struct MsoCF::PropertyInfo *v264; // r8
  bool v265; // r9
  __int64 v266; // rax
  char v267; // al
  unsigned int v268; // edx
  unsigned int TrackingPropertyFromReplicatorRole; // eax
  unsigned int v270; // r8d
  const struct MsoCF::ExtendedGUID *v271; // r9
  char v272; // al
  __int64 v273; // rcx
  __int64 v274; // r8
  struct Jot::IGraphSpaceNode *v275; // rdx
  void (__fastcall ***v276)(_QWORD, GUID *, Jot::CReplicatorWithBranchBase **); // rcx
  Jot *v277; // rbx
  __int64 v278; // rdx
  void (__fastcall *v279)(Jot *, __int64, __int64, Jot::CReplicatorWithBranchBase **, _DWORD); // rsi
  __int64 v280; // rdi
  __int64 v281; // rax
  unsigned int v282; // edx
  void (__fastcall ***v283)(_QWORD, GUID *, Jot::StaticContextReplication **); // rcx
  unsigned int v284; // eax
  unsigned int v285; // r8d
  const struct MsoCF::ExtendedGUID *v286; // r9
  void (__fastcall *v287)(struct Jot::IGraphNode *, GUID *, Jot **); // rax
  _QWORD *v288; // rbx
  _QWORD *v289; // rax
  struct Jot::EDP::Identity *v290; // [rsp+20h] [rbp-438h]
  struct Jot::CGraphIterator *v291; // [rsp+40h] [rbp-418h] BYREF
  Jot *v292; // [rsp+48h] [rbp-410h] BYREF
  struct Jot::IGraphNode *v293; // [rsp+50h] [rbp-408h] BYREF
  MsoCF::IAtom *v294; // [rsp+58h] [rbp-400h] BYREF
  struct Jot::IGraphNode *v295; // [rsp+60h] [rbp-3F8h] BYREF
  struct Jot::IGraphNode *v296; // [rsp+68h] [rbp-3F0h] BYREF
  Jot::StaticContextReplication *v297; // [rsp+70h] [rbp-3E8h] BYREF
  Jot::StaticContextReplication *v298[2]; // [rsp+78h] [rbp-3E0h] BYREF
  Jot::StaticContextReplication *v299; // [rsp+88h] [rbp-3D0h] BYREF
  Jot::StaticContextReplication *v300[2]; // [rsp+90h] [rbp-3C8h] BYREF
  Jot::CReplicatorWithBranchBase *v301; // [rsp+A0h] [rbp-3B8h] BYREF
  char v302; // [rsp+A8h] [rbp-3B0h]
  char v303; // [rsp+A9h] [rbp-3AFh]
  Jot::CGraphIterator *v304; // [rsp+B0h] [rbp-3A8h] BYREF
  unsigned int *v305; // [rsp+B8h] [rbp-3A0h]
  _QWORD v306[4]; // [rsp+C0h] [rbp-398h] BYREF
  Jot *v307; // [rsp+E0h] [rbp-378h] BYREF
  char v308[72]; // [rsp+E8h] [rbp-370h] BYREF
  __int128 Buf1; // [rsp+130h] [rbp-328h] BYREF
  int v310; // [rsp+140h] [rbp-318h]
  __m128i v311; // [rsp+148h] [rbp-310h] BYREF
  __m128i v312; // [rsp+158h] [rbp-300h]
  _OWORD v313[2]; // [rsp+168h] [rbp-2F0h] BYREF
  int v314[2]; // [rsp+190h] [rbp-2C8h] BYREF
  int v315; // [rsp+198h] [rbp-2C0h] BYREF
  void ***v316; // [rsp+1A0h] [rbp-2B8h] BYREF
  Mso::Memory *v317; // [rsp+1A8h] [rbp-2B0h]
  _DWORD v318[12]; // [rsp+1B0h] [rbp-2A8h] BYREF
  __int64 v319; // [rsp+1E0h] [rbp-278h] BYREF
  _BYTE v320[88]; // [rsp+1E8h] [rbp-270h] BYREF
  __int32 v321; // [rsp+240h] [rbp-218h]
  char v322; // [rsp+288h] [rbp-1D0h]
  char IsEducationNotebook; // [rsp+290h] [rbp-1C8h]
  __int64 v324; // [rsp+2E0h] [rbp-178h] BYREF
  _BYTE v325[248]; // [rsp+2E8h] [rbp-170h] BYREF

  v2 = a2;
  v305 = a2;
  v298[0] = (Jot::StaticContextReplication *)this;
  LODWORD(v294) = 0;
  v4 = this[50];
  v301 = v4;
  if ( !v4 )
  {
    v193 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
    v194 = Jot::ErrNativeReplicator_ReplicationNotAllowed::ErrNativeReplicator_ReplicationNotAllowed(v314, 17065680);
    v195 = std::make_exception_ptr<Jot::ErrNativeReplicator_ReplicationNotAllowed>(&v311, v194);
LABEL_309:
    v193(this, v195);
    return;
  }
  OneNoteDotComNetworkStatusInstance = Jot::GetOneNoteDotComNetworkStatusInstance((Jot *)this);
  v6 = (Jot *)(unsigned int)(*(_DWORD *)((**(__int64 (__fastcall ***)(struct Jot::CNetworkStatus *))OneNoteDotComNetworkStatusInstance)(OneNoteDotComNetworkStatusInstance)
                                       + 88)
                           - 1);
  if ( (unsigned int)v6 <= 1 && !Jot::CanSyncOnMeteredNetwork(v6) )
  {
    v193 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
    v196 = Jot::ErrCannotSyncOnMeteredNetwork::ErrCannotSyncOnMeteredNetwork(v314, 17377498);
    v195 = std::make_exception_ptr<Jot::ErrCannotSyncOnMeteredNetwork>(&v311, v196);
    goto LABEL_309;
  }
  v7 = (void (__fastcall ***)(_QWORD, GUID *, struct Jot::IGraphNode **))(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
  v293 = 0;
  if ( v7 )
  {
    if ( (char *)**v7 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
      MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
        v7,
        &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
        &v293);
    else
      (**v7)(v7, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v293);
  }
  if ( v293 )
  {
    v8 = *v2;
    if ( *v2 <= 0x14 )
    {
      if ( v8 == 20 )
      {
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 59, 0);
        LOBYTE(v224) = Jot::CNativeReplicator::IsSyncingToOneDrive(v4);
        Jot::RevisionTimeLogger::LogLegacySyncRevisionInbound(this[52], v224, v225);
        *v2 = 22;
        goto LABEL_26;
      }
      if ( v8 <= 0xF )
      {
        if ( v8 != 15 )
        {
          v9 = v8 - 10;
          if ( !v9 )
          {
            v10 = (void (__fastcall ***)(_QWORD, GUID *, struct Jot::IGraphNode **))(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
            v295 = 0;
            if ( v10 )
            {
              if ( (char *)**v10 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
                MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
                  v10,
                  &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
                  &v295);
              else
                (**v10)(v10, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v295);
            }
            if ( !(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25)) )
            {
              if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 112LL))(*((_QWORD *)v4 + 25)) )
              {
                v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 112LL))(*((_QWORD *)v4 + 25));
                if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 136LL))(v34) )
                {
                  v35 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 112LL))(*((_QWORD *)v4 + 25));
                  v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 136LL))(v35);
                  (*(void (__fastcall **)(__int64, struct Jot::IGraphNode **))(*(_QWORD *)v36 + 208LL))(v36, &v296);
                  v37 = 0;
                  v298[0] = 0;
                  v38 = v296;
                  if ( v296
                    && ((**(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot::StaticContextReplication **))v296)(
                          v296,
                          &GUID_9f7ae2e4_9cb0_45c1_9e5a_95fdd6d001ee,
                          v298),
                        v37 = v298[0],
                        v38 = v296,
                        v39 = 1,
                        v298[0])
                    || (v39 = 0, v37) )
                  {
                    (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v37 + 16LL))(v37);
                    v38 = v296;
                  }
                  if ( !v39 )
                  {
                    v311 = 0;
                    si128 = _mm_load_si128((const __m128i *)&_xmm);
                    v312 = si128;
                    v311.m128i_i16[0] = 0;
                    v41 = (const wchar_t *)v311.m128i_i64[0];
                    v313[0] = v311;
                    v313[1] = si128;
                    std::wstring::~wstring(&v311);
                    v42 = (__m128i *)std::wstring::wstring(v306, (char *)v4 + 80);
                    v43 = *v42;
                    v311 = *v42;
                    v44 = v42[1];
                    v312 = v44;
                    v42->m128i_i16[0] = 0;
                    v42[1].m128i_i64[0] = 0;
                    v42[1].m128i_i64[1] = 7;
                    std::wstring::~wstring(v42);
                    v45 = (const wchar_t *)v313;
                    if ( _mm_srli_si128(si128, 8).m128i_u64[0] > 7 )
                      v45 = v41;
                    v46 = (const wchar_t *)&v311;
                    if ( _mm_srli_si128(v44, 8).m128i_u64[0] > 7 )
                      v46 = (const wchar_t *)v43.m128i_i64[0];
                    if ( v44.m128i_i64[0] == si128.m128i_i64[0] )
                    {
                      if ( v44.m128i_i64[0] )
                        v47 = wmemcmp(v46, v45, v44.m128i_u64[0]) == 0;
                      else
                        v47 = 1;
                    }
                    else
                    {
                      v47 = 0;
                    }
                    std::wstring::~wstring(&v311);
                    std::wstring::~wstring(v313);
                    if ( !v47 )
                    {
                      v48 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
                      Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v314, 0);
                      *(_QWORD *)v314 = &Jot::ErrEDP_SectionSyncViaDavUnsupported::`vftable';
                      v49 = std::make_exception_ptr<Jot::ErrEDP_SectionSyncViaDavUnsupported>(&v311, v314);
                      v48(this, v49);
                      if ( v296 )
                        (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v296 + 16LL))(v296);
                      if ( v295 )
                        (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v295 + 16LL))(v295);
                      goto LABEL_80;
                    }
                    v38 = v296;
                  }
                  if ( v38 )
                    (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v38 + 16LL))(v38);
                }
              }
            }
            if ( *((_QWORD *)v4 + 35) )
            {
              MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *((_QWORD *)v4 + 35));
              *((_DWORD *)this + 96) = 10;
              *((_DWORD *)this + 97) = 10;
              *((_DWORD *)this + 93) = 3;
LABEL_22:
              v11 = v295;
              goto LABEL_23;
            }
            MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign((char *)v4 + 280, this + 33);
            this[62] = 0;
            if ( *((_DWORD *)v4 + 77) )
            {
              v95 = v293;
              v311.m128i_i64[0] = 0;
              if ( v293 )
              {
                v96 = *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(*(_QWORD *)v293 + 48LL);
                if ( v96 == MsoCF::CPropertySet::FGetProperty_Imp )
                {
                  v97 = MsoCF::CPropertySet::FGetProperty_Imp(
                          v293,
                          (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot11::priLastModifiedTimeStamp,
                          &v311);
                }
                else if ( (char *)v96 == (char *)Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp )
                {
                  v97 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(
                          v293,
                          Jot::PropertySpace_Jot11::priLastModifiedTimeStamp,
                          &v311);
                }
                else
                {
                  v97 = (char *)v96 == (char *)Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp
                      ? Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(
                          v293,
                          Jot::PropertySpace_Jot11::priLastModifiedTimeStamp,
                          &v311)
                      : (*(unsigned __int64 (__fastcall **)(struct Jot::IGraphNode *, char *, __m128i *))(*(_QWORD *)v293 + 48LL))(
                          v293,
                          Jot::PropertySpace_Jot11::priLastModifiedTimeStamp,
                          &v311);
                }
                v98 = v97 != 0 ? dword_181548AAC : 0;
                v95 = v293;
              }
              else
              {
                v98 = 0;
              }
              v311.m128i_i32[2] = v98;
              if ( v98 )
              {
                if ( v98 != 2031647 )
                {
                  v106 = MsoCF::LookupProperty((MsoCF *)*((unsigned int *)v4 + 77), v98);
                  v300[0] = v106;
                  *(_QWORD *)&v313[0] = 0;
                  if ( v95
                    && ((v107 = *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(*(_QWORD *)v95 + 48LL),
                         v107 != MsoCF::CPropertySet::FGetProperty_Imp)
                      ? ((char *)v107 != (char *)Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp
                       ? ((char *)v107 != (char *)Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp
                        ? (v108 = (*(__int64 (__fastcall **)(struct Jot::IGraphNode *, Jot::StaticContextReplication *, _OWORD *))(*(_QWORD *)v95 + 48LL))(
                                    v95,
                                    v106,
                                    v313))
                        : (v108 = Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(v95, v106, v313)))
                       : (v108 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(v95, v106, v313)))
                      : (v108 = MsoCF::CPropertySet::FGetProperty_Imp(v95, v106, v313)),
                        v108) )
                  {
                    v109 = *((_DWORD *)v300[0] + 1);
                  }
                  else
                  {
                    v109 = 0;
                  }
                  DWORD2(v313[0]) = v109;
                  if ( !v109 || v109 == 2031647 )
                  {
                    v110 = v311.m128i_i32[2];
                    v111 = (Jot::RevisionTimeLogger *)v311.m128i_i64[0];
                  }
                  else
                  {
                    v110 = v311.m128i_i32[2];
                    if ( v311.m128i_i32[2] != 17170499 || v109 != 17170499 )
                    {
LABEL_287:
                      CrashWithRecovery(0x65756E73u, 0);
                      __debugbreak();
                    }
                    v111 = (Jot::RevisionTimeLogger *)v311.m128i_i64[0];
                    if ( v311.m128i_i64[0] == *(_QWORD *)&v313[0] )
                      goto LABEL_18;
                  }
                  if ( v110 != 17170499 )
                    goto LABEL_287;
                  this[62] = v111;
                }
              }
            }
LABEL_18:
            if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25)) )
            {
              v210 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25));
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v210 + 176LL))(v210, (__int64)v4 + 8);
            }
            if ( *((_BYTE *)this + 409) )
            {
              v72 = 0;
              v298[0] = 0;
              v73 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
              v74 = (Jot::StaticContextReplication *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 384LL))(v73);
              MsoCF::CIPtr<Jot::IGraphNode,Jot::IGraphNode>::AddRef(v74);
              v300[0] = v74;
              while ( v74 )
              {
                if ( MsoCF::IPropertySet::HasProperty(
                       v74,
                       (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot11::priLastRevisionSetOnGS) )
                {
                  LOBYTE(v291) = 0;
                  if ( (unsigned __int8)MsoCF::Properties::Raw<Jot::PropertySpace_Jot14::prtidPrimaryStorageIsCellStorage>::FGet(
                                          v74,
                                          &v291) )
                  {
                    if ( (_BYTE)v291 == 1 )
                    {
                      KnowledgeFromPropertySet = (Jot::StaticContextReplication **)Jot::GetKnowledgeFromPropertySet(
                                                                                     &v292,
                                                                                     v74,
                                                                                     469775403);
                      v72 = *KnowledgeFromPropertySet;
                      *KnowledgeFromPropertySet = 0;
                      v298[0] = v72;
                      if ( v292 )
                        (*(void (__fastcall **)(Jot *))(*(_QWORD *)v292 + 16LL))(v292);
                      break;
                    }
                  }
                }
                v101 = Jot::IGraphSpaceNode::UseParentGraphSpaceGraphNodeOf(v74);
                MsoCF::CIPtr<Jot::IGraphNode,Jot::IGraphNode>::AddRef(v101);
                v102 = v74;
                v74 = v101;
                v300[0] = v101;
                (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v102 + 16LL))(v102);
              }
              v75 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 88LL))((__int64)v4 + 128);
              v76 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, Jot **, Jot::StaticContextReplication *, _QWORD, _BYTE, _BYTE, _BYTE))(*(_QWORD *)v75 + 56LL))(
                                v75,
                                &v292,
                                v72,
                                0,
                                0,
                                0,
                                0);
              v77 = this + 53;
              Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 53, *v76);
              if ( v292 )
                (*(void (__fastcall **)(Jot *))(*(_QWORD *)v292 + 16LL))(v292);
              if ( *v77 )
              {
                MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *v77);
                *((_DWORD *)this + 96) = 13;
                *((_DWORD *)this + 97) = 11;
                *((_DWORD *)this + 93) = 3;
              }
              else
              {
                *v305 = 14;
              }
              if ( v74 )
                (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v74 + 16LL))(v74);
              if ( v72 )
                (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v72 + 16LL))(v72);
            }
            else
            {
              *v2 = 14;
            }
            goto LABEL_22;
          }
          v14 = v9 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                if ( v16 != 1 )
                  goto LABEL_26;
                v17 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
                BackingRevisionStore = Jot::IGraphSpace::GetBackingRevisionStore(v17, v300);
                MsoCF::CIPtr<Jot::IServerStore,Jot::IServerStore>::operator=<Jot::IObjectSpaceStoreOnCellStorage,Jot::IObjectSpaceStoreOnCellStorage>(
                  this + 58,
                  BackingRevisionStore);
                if ( v300[0] )
                  (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v300[0] + 8LL))(v300[0]);
                if ( this[58] )
                {
                  *v2 = 12;
                  goto LABEL_26;
                }
LABEL_246:
                *v2 = 16;
                goto LABEL_26;
              }
              v197 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 88LL))((__int64)v4 + 128);
              v198 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v197 + 120LL))(v197);
              MsoCF::CIPtr<Jot::IStoreRevisionBatch,Jot::IStoreRevisionBatch>::CIPtr<Jot::IStoreRevisionBatch,Jot::IStoreRevisionBatch>(
                v298,
                v198);
              v199 = v298[0];
              if ( *((_BYTE *)v4 + 288) && v298[0] )
              {
                (*(void (__fastcall **)(Jot::StaticContextReplication *, Jot **))(*(_QWORD *)v298[0] + 200LL))(
                  v298[0],
                  &v292);
                v200 = v292;
                if ( v292 )
                {
                  v201 = (const struct MsoCF::ExtendedGUID *)(*(__int64 (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v199 + 136LL))(v199);
                  v202 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
                  v203 = (struct Jot::IObjectSpaceRevisionCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v202 + 24LL))(v202);
                  Jot::EnsureObjectSpaceRootStoreInCellStorage(v292, v203, v201, v204);
                  v200 = v292;
                }
                MsoCF::CIPtr<Jot::IObjectSpaceRevisionCache,Jot::IObjectSpaceRevisionCache>::Release(v200);
              }
              *v2 = 14;
              if ( !v199 )
                goto LABEL_26;
              v71 = *(__int64 (**)(void))(*(_QWORD *)v199 + 8LL);
              v70 = v199;
              if ( (char *)v71 == (char *)MsoCF::IThreadSafeBaseImpl<Jot::IObjectSpaceStoreOnCellStorage>::Release )
              {
                MsoCF::IThreadSafeBaseImpl<Jot::IObjectSpaceStoreOnCellStorage>::Release(v199);
                goto LABEL_26;
              }
LABEL_320:
              ((void (__fastcall *)(Jot::StaticContextReplication *))v71)(v70);
              goto LABEL_26;
            }
            v65 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25));
            v67 = v65;
            if ( v65 )
              (*(void (__fastcall **)(__int64, struct Jot::IGraphNode **))(*(_QWORD *)v65 + 200LL))(v65, &v295);
            else
              v295 = 0;
            if ( !(*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)v4 + 25) + 120LL))(
                    *((_QWORD *)v4 + 25),
                    v66,
                    v67)
              && *((_BYTE *)this + 408)
              || (v70 = v295) != 0 )
            {
              v68 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
              v69 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 32LL))(v68);
              if ( !v69[4] && !memcmp_0(v69, &Jot::c_gctxidRuntimeDefault, 0x10u) )
              {
                v118 = Jot::CNativeReplicator::UseRevStoreAttached(v4);
                v119 = (_QWORD *)(*(__int64 (__fastcall **)(struct Jot::IServerRevisionStore *, Jot::StaticContextReplication **, __int64, _QWORD, _BYTE))(*(_QWORD *)v118 + 80LL))(
                                   v118,
                                   v300,
                                   1,
                                   0,
                                   0);
                Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncResult_HierarchicalContentLoader>::operator=(
                  this + 55,
                  *v119);
                if ( v300[0] )
                  (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v300[0] + 16LL))(v300[0]);
                MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[55]);
                *((_DWORD *)this + 96) = 15;
                *((_DWORD *)this + 97) = 4;
                *((_DWORD *)this + 93) = 3;
                v70 = v295;
                goto LABEL_106;
              }
              v70 = v295;
            }
            *v2 = 16;
LABEL_106:
            if ( !v70 )
              goto LABEL_26;
            v71 = *(__int64 (**)(void))(*(_QWORD *)v70 + 8LL);
            if ( v71 == MsoCF::IThreadSafeBaseImpl<Jot::CObjectSpaceRevisionCacheInCellStorage>::Release )
            {
              MsoCF::IThreadSafeBaseImpl<Jot::CObjectSpaceRevisionCacheInCellStorage>::Release();
              goto LABEL_26;
            }
            goto LABEL_320;
          }
          v205 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[53] + 80LL))(this[53]);
          if ( (unsigned __int8)Jot::IsError<Jot::ErrObjectSpaceStore_NoLatestRevision>(v205) )
          {
            v206 = (void (__fastcall ***)(_QWORD, GUID *, struct Jot::IGraphNode **))(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
            v296 = 0;
            if ( v206 )
            {
              if ( (char *)**v206 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
                MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
                  v206,
                  &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
                  &v296);
              else
                (**v206)(v206, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v296);
            }
            if ( !MsoCF::IPropertySet::HasProperty(
                    v296,
                    (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot14::priPrimaryStorageLastRevGenCount) )
            {
              if ( MsoCF::IPropertySet::HasProperty(
                     v296,
                     (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot11::priLastRevisionSetOnGS)
                || (v207 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4),
                    (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v207 + 40LL))(v207)) )
              {
                *v2 = 27;
                v11 = v296;
LABEL_23:
                if ( v11 )
                {
                  v12 = *(_QWORD *)v11;
LABEL_25:
                  (*(void (**)(void))(v12 + 16))();
                }
LABEL_26:
                MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v293);
                return;
              }
            }
            if ( v296 )
              (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v296 + 16LL))(v296);
          }
          v208 = this[53];
          goto LABEL_333;
        }
        v187 = (Jot::RevisionTimeLogger **)sub_18020016C(v300);
        v188 = *v187;
        *v187 = 0;
        v189 = this[56];
        this[56] = v188;
        if ( v189 )
          (*(void (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v189 + 8LL))(v189);
        if ( v300[0] )
          (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v300[0] + 8LL))(v300[0]);
        v190 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[55] + 96LL))(this[55]);
        MsoCF::CIPtr<Jot::COpenedFileTracker,Jot::COpenedFileTracker>::CIPtr<Jot::COpenedFileTracker,Jot::COpenedFileTracker>(
          v314,
          this + 58);
        std::vector<std::pair<MsoCF::ExtendedGUID,MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>>::vector<std::pair<MsoCF::ExtendedGUID,MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>>(
          &v315,
          v190);
        Jot::EDP::Identity::Identity((Jot::EDP::Identity *)v318, (Jot::RevisionTimeLogger *)((char *)v4 + 80));
        v191 = (_QWORD *)sub_1802127F4(v300, v314);
        v192 = this + 57;
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 57, *v191);
        if ( v300[0] )
          (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v300[0] + 16LL))(v300[0]);
        std::wstring::~wstring(v318);
        std::vector<std::pair<MsoCF::ExtendedGUID,MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>>::~vector<std::pair<MsoCF::ExtendedGUID,MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>>(&v315);
        if ( *(_QWORD *)v314 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v314 + 8LL))(*(_QWORD *)v314);
        if ( !*v192 )
          goto LABEL_246;
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *v192);
        *((_DWORD *)this + 96) = 16;
        goto LABEL_265;
      }
      v50 = v8 - 16;
      if ( !v50 )
      {
        v112 = Jot::CNativeReplicator::UseRevStoreAttached(v4);
        v113 = *(__int64 (__fastcall **)(struct Jot::IServerRevisionStore *, Jot::StaticContextReplication **, __int64, __int64))(*(_QWORD *)v112 + 24LL);
        v114 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
        v115 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v114 + 32LL))(v114);
        v116 = (_QWORD *)v113(v112, v300, 1, v115);
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncResult_HierarchicalContentLoader>::operator=(this + 54, *v116);
        if ( v300[0] )
          (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v300[0] + 16LL))(v300[0]);
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[54]);
        *((_DWORD *)this + 96) = 17;
        *((_DWORD *)this + 97) = 18;
        goto LABEL_136;
      }
      v51 = v50 - 1;
      if ( !v51 )
      {
        if ( !*(_QWORD *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[54] + 96LL))(this[54]) )
        {
          if ( *((_BYTE *)v4 + 112) )
          {
            if ( Jot::ShouldLogTtid((Jot *)0x4C5292, 0x100EEu, 3u, v52) )
            {
              v213 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *, __m128i *))(*(_QWORD *)v4 + 112LL))(
                       v4,
                       &v311);
              Jot::Log_Impl<wchar_t [75],std::wstring,bool>((_DWORD)v4 + 288, v214, v215, v216, v213, (__int64)v4 + 288);
              std::wstring::~wstring(&v311);
            }
            (*(void (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 40LL))((__int64)v4 + 128);
            if ( *((_DWORD *)v4 + 76) )
            {
              if ( !(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4) )
              {
                CrashWithRecovery(0x11586C5u, 0);
                __debugbreak();
              }
              v217 = *((_DWORD *)v4 + 76);
              v218 = (Jot::GraphSpaceEditor *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
              Jot::GraphSpaceEditor::HandleMergeOfDeletedContent(v218, (struct Jot::IGraphSpace *)v217, v219);
            }
          }
          v103 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __m128i *))*((_QWORD *)*this + 12);
          v104 = Jot::ErrObjectSpaceStore_NoLatestRevision::ErrObjectSpaceStore_NoLatestRevision(v314, 18667042);
          v105 = (__m128i *)std::make_exception_ptr<Jot::ErrObjectSpaceStore_NoLatestRevision>(&v311, v104);
          goto LABEL_171;
        }
        v53 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[54] + 96LL))(this[54]);
        MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::operator=(this + 52, v53);
        v55 = (MsoCF *)*((unsigned int *)v4 + 76);
        if ( !(_DWORD)v55 )
          goto LABEL_98;
        if ( !*((_BYTE *)v4 + 112) )
          goto LABEL_98;
        if ( !*((_BYTE *)this + 408) )
          goto LABEL_98;
        v56 = v293;
        v57 = MsoCF::LookupProperty(v55, v54);
        if ( !MsoCF::IPropertySet::HasProperty(v56, v57) )
          goto LABEL_98;
        Buf1 = 0;
        v310 = 0;
        v59 = v293;
        if ( !v293 )
          goto LABEL_98;
        v294 = 0;
        v60 = MsoCF::LookupProperty((MsoCF *)0x1C001DA5, v58);
        v61 = *(_QWORD *)v59;
        if ( *((_DWORD *)v60 + 1) == 117899271 )
        {
          if ( *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(v61 + 48) == MsoCF::CPropertySet::FGetProperty_Imp )
          {
            v62 = MsoCF::CPropertySet::FGetProperty_Imp(v59, v60, &v294);
          }
          else if ( *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v61 + 48) == Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp )
          {
            v62 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(v59, v60, &v294);
          }
          else if ( *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v61 + 48) == Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp )
          {
            v62 = Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(v59, v60, &v294);
          }
          else
          {
            v62 = (*(__int64 (__fastcall **)(struct Jot::IGraphNode *, const struct MsoCF::PropertyInfo *, MsoCF::IAtom **))(v61 + 48))(
                    v59,
                    v60,
                    &v294);
          }
          goto LABEL_93;
        }
        v311.m128i_i64[0] = 0;
        v220 = *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(v61 + 48);
        if ( v220 == MsoCF::CPropertySet::FGetProperty_Imp )
        {
          v221 = MsoCF::CPropertySet::FGetProperty_Imp(v59, v60, &v311);
        }
        else if ( (char *)v220 == (char *)Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp )
        {
          v221 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(v59, v60, &v311);
        }
        else if ( (char *)v220 == (char *)Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp )
        {
          v221 = Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(v59, v60, &v311);
        }
        else
        {
          v221 = (*(__int64 (__fastcall **)(struct Jot::IGraphNode *, const struct MsoCF::PropertyInfo *, __m128i *))(v61 + 48))(
                   v59,
                   v60,
                   &v311);
        }
        if ( v221 )
          v222 = *((_DWORD *)v60 + 1);
        else
          v222 = 0;
        v311.m128i_i32[2] = v222;
        if ( !v222 || v222 == 2031647 )
          goto LABEL_251;
        if ( v222 == 117899271 )
        {
          v294 = (MsoCF::IAtom *)v311.m128i_i64[0];
          MsoCF::CPropertyData::Copy_MakeDeep_ComplexType(&v294, 117899271);
          goto LABEL_362;
        }
        *(_QWORD *)&v313[0] = 0;
        MsoCF::CPropertyValue::WritePrvPrt_DifferentTypes(v313, &v311, 117899271);
        v223 = DWORD2(v313[0]);
        if ( !DWORD2(v313[0]) || DWORD2(v313[0]) == 2031647 )
        {
          if ( !MsoCF::CPropertyGlobals::g_fNoTypeSafety_HackHackHack )
          {
            if ( (v311.m128i_i32[2] & 0x2000000) != 0 )
              MsoCF::CPropertyData::FreeAndZero_ComplexType(&v311);
            v62 = 0;
LABEL_93:
            if ( v62 )
            {
LABEL_94:
              if ( (*((_DWORD *)v294 + 1) & 0x3FFFFFFF) == 0x14 )
              {
                MsoCF::Memory::Copy((MsoCF::IAtom *)((char *)v294 + 8), &Buf1, (void *)0x14, v63);
                if ( v294 )
                  MsoCF::IAtom::Release(v294);
                v64 = (_DWORD *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[52] + 160LL))(this[52]);
                if ( v310 == v64[4] && !memcmp_0(&Buf1, v64, 0x10u) )
                {
                  Jot::CNativeReplicator_InboundReplication::EnsureBaseAndBranchInSyncWith(
                    (Jot::CNativeReplicator_InboundReplication *)this,
                    this[52]);
                  *v2 = 27;
                  goto LABEL_80;
                }
LABEL_98:
                *v2 = this[58] != 0 ? 19 : 22;
                goto LABEL_26;
              }
              v163 = v294;
LABEL_292:
              MsoCF::IAtom::Release(v163);
              goto LABEL_98;
            }
LABEL_251:
            v163 = v294;
            if ( !v294 )
              goto LABEL_98;
            goto LABEL_292;
          }
          *(_QWORD *)&v313[0] = v311.m128i_i64[0];
          MsoCF::CPropertyData::Copy_MakeDeep_ComplexType(v313, 117899271);
          DWORD2(v313[0]) = 117899271;
          v294 = *(MsoCF::IAtom **)&v313[0];
          MsoCF::CPropertyData::Copy_MakeDeep_ComplexType(&v294, 117899271);
        }
        else
        {
          v294 = *(MsoCF::IAtom **)&v313[0];
          MsoCF::CPropertyData::Copy_MakeDeep_ComplexType(&v294, 117899271);
          if ( (v223 & 0x2000000) == 0 )
          {
LABEL_362:
            if ( (v311.m128i_i32[2] & 0x2000000) != 0 )
              MsoCF::CPropertyData::FreeAndZero_ComplexType(&v311);
            goto LABEL_94;
          }
        }
        MsoCF::CPropertyData::FreeAndZero_ComplexType(v313);
        goto LABEL_362;
      }
      v176 = v51 - 1;
      if ( v176 )
      {
        if ( v176 != 1 )
          goto LABEL_26;
        v177 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
        v178 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v177 + 32LL))(v177);
        v179 = sub_1808DE538(
                 (int)v314,
                 (int)this + 464,
                 (int)this + 416,
                 v178,
                 (Jot::RevisionTimeLogger *)((char *)v4 + 80));
        v180 = (_QWORD *)sub_180775CD4(v300, v179);
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 59, *v180);
        MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v300[0]);
        sub_1801AD9A4(v314);
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[59]);
        *((_DWORD *)this + 96) = 20;
LABEL_265:
        *((_DWORD *)this + 97) = 21;
        goto LABEL_136;
      }
      v212 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[54] + 80LL))(this[54]);
      if ( !(unsigned __int8)Jot::IsError<Jot::ErrObjectSpaceStore_NoNewerRevision>(v212) )
      {
        v208 = this[54];
LABEL_333:
        v103 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __m128i *))*((_QWORD *)*this + 12);
        v209 = (const void *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v208 + 80LL))(v208);
        v311 = 0;
        __ExceptionPtrCopy(&v311, v209);
        v105 = &v311;
LABEL_171:
        v103(this, v105);
        goto LABEL_26;
      }
LABEL_188:
      *v2 = 27;
      goto LABEL_26;
    }
    if ( v8 > 0x1A )
    {
      v13 = v8 - 27;
      if ( !v13 )
      {
        if ( !*((_BYTE *)this + 408) && !*((_BYTE *)this + 411) )
        {
          *v2 = 29;
          goto LABEL_26;
        }
        v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25));
        v30 = v28;
        if ( v28 )
        {
          (*(void (__fastcall **)(__int64, Jot::StaticContextReplication **))(*(_QWORD *)v28 + 200LL))(v28, v298);
          v31 = v298[0];
        }
        else
        {
          v298[0] = 0;
          v31 = 0;
        }
        v32 = 32;
        if ( !v31 )
          goto LABEL_57;
        v292 = 0;
        if ( v293 )
        {
          v287 = **(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot **))v293;
          if ( (char *)v287 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
            MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
              v293,
              &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
              &v292);
          else
            v287(v293, &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b, &v292);
        }
        v32 = 96;
        LODWORD(v294) = 1120;
        v33 = 1;
        if ( !Jot::StaticContextReplication::IsStaticContextParent(v292, v29) )
LABEL_57:
          v33 = 0;
        if ( (v32 & 0x40) != 0 )
        {
          v32 &= ~0x40u;
          if ( v292 )
            (*(void (__fastcall **)(Jot *, struct Jot::IGraphSpaceNode *, __int64))(*(_QWORD *)v292 + 16LL))(
              v292,
              v29,
              v30);
        }
        if ( (v32 & 0x20) != 0 )
          MsoCF::CIPtr<Jot::IObjectSpaceRevisionCache,Jot::IObjectSpaceRevisionCache>::Release(v298[0]);
        if ( !v33 )
          goto LABEL_62;
        v288 = this + 61;
        if ( !this[61] )
        {
          v289 = (_QWORD *)(***((__int64 (__fastcall ****)(_QWORD, __int128 *, __int64))v4 + 8))(
                             *((_QWORD *)v4 + 8),
                             &Buf1,
                             1);
          Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 61, *v289);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
        }
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, struct Jot::IGraphSpaceNode *, __int64))(*(_QWORD *)*v288 + 32LL))(
               *v288,
               v29,
               v30) )
        {
LABEL_62:
          *v2 = 28;
          goto LABEL_26;
        }
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *v288);
        *((_DWORD *)this + 96) = 28;
        *((_DWORD *)this + 97) = 29;
LABEL_136:
        *((_DWORD *)this + 93) = 3;
        goto LABEL_26;
      }
      v19 = v13 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          if ( v20 == 1 )
          {
            v99 = 0;
            v292 = 0;
            LOBYTE(v291) = 0;
            if ( *((_BYTE *)this + 409) )
            {
              v262 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 88LL))((__int64)v4 + 128);
              (*(void (__fastcall **)(__int64, Jot **, struct Jot::CGraphIterator **))(*(_QWORD *)v262 + 64LL))(
                v262,
                &v292,
                &v291);
              v99 = v292;
            }
            if ( *((_BYTE *)v4 + 288) && *((_BYTE *)this + 408) )
            {
              if ( v99 && !Jot::CAsyncResultBase::HasPendingError((Jot::CAsyncResultBase *)this) )
              {
                Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v293, 0x3FFFu);
                Jot::SetKnowledgeInPropertySet(v293, (struct MsoCF::IPropertySet *)0x1C00342B, (unsigned int)v292, v263);
                Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)&Buf1);
              }
              if ( *((_BYTE *)this + 409) )
              {
                Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v293, 0x3FFFu);
                if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25))
                  && (LOBYTE(v264) = (_BYTE)v291) != 0 )
                {
                  Jot::FSetBoolIfDifferent(v293, (struct MsoCF::IPropertySet *)0x80034AC, (unsigned int)v264, v265);
                }
                else
                {
                  Jot::RemovePropertyIfExist(
                    v293,
                    (struct MsoCF::IPropertySet *)Jot::PropertySpace_Jot14::priSectionHasHotboxContent,
                    v264);
                }
                Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)&Buf1);
              }
            }
            if ( !Jot::CAsyncResultBase::HasPendingError((Jot::CAsyncResultBase *)this) )
            {
              Jot::CNativeReplicator::UpdateStoreNeedOptimizeIfNeeded(v4, 0);
              v298[0] = 0;
              v164 = *((_DWORD *)v4 + 18);
              v165 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
              MsoCF::QI_OrNull<Jot::IGraphSpaceNode,&__s_GUID const _GUID_4c161eeb_0e6f_4c83_921d_3102a717501b>(
                v300,
                v165);
              LOBYTE(v164) = Jot::StaticContextReplication::ShouldUseEfficientStaticContextReplicationChild(
                               v300[0],
                               (struct Jot::IGraphSpaceNode *)v164,
                               (unsigned int)v298,
                               v166);
              MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v300[0]);
              if ( (_BYTE)v164 )
              {
                Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v293, 0x3FFFu);
                v266 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
                v267 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v266 + 32LL))(v266);
                LOBYTE(v268) = 1;
                TrackingPropertyFromReplicatorRole = Jot::StaticContextReplication::GetTrackingPropertyFromReplicatorRole(
                                                       (Jot::StaticContextReplication *)*((unsigned int *)v4 + 18),
                                                       v268,
                                                       v267);
                v167 = v298[0];
                Jot::StaticContextReplication::RemoveTrackedContext(
                  v298[0],
                  (struct Jot::IGraphSpaceNode *)TrackingPropertyFromReplicatorRole,
                  v270,
                  v271);
                Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)&Buf1);
              }
              else
              {
                v167 = v298[0];
              }
              MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v167);
            }
            v100 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __m128i *))*((_QWORD *)*this + 12);
            v311 = 0;
            __ExceptionPtrCreate(&v311);
            v100(this, &v311);
            MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v292);
          }
          goto LABEL_26;
        }
        v21 = this + 65;
        v22 = this[65];
        if ( v22 )
        {
          v158 = (const void *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v22 + 80LL))(v22);
          if ( __ExceptionPtrToBool(v158) )
          {
            v159 = (Jot *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 80LL))(*v21);
            if ( !Jot::FSuppressSyncError(v159, v160) )
            {
              v161 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 80LL))(*v21);
              v311 = 0;
              __ExceptionPtrCopy(&v311, v161);
              Jot::CAsyncResultBase::SetErrorForCompletion(this, &v311);
            }
          }
        }
        while ( 1 )
        {
          if ( !*((_DWORD *)this + 128) )
          {
            *v305 = 30;
            goto LABEL_26;
          }
          TailAddr = Ofc::CListImpl::GetTailAddr((Ofc::CListImpl *)(this + 63));
          if ( TailAddr )
            v79 = (__int64 *)*TailAddr;
          else
            v79 = 0;
          if ( v79 )
            (*(void (__fastcall **)(__int64 *))(*v79 + 8))(v79);
          *(_QWORD *)&v313[0] = v79;
          v80 = Ofc::CListImpl::RemoveTail((Ofc::CListImpl *)(this + 63));
          v81 = v80;
          if ( v80 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v80 + 16LL))(v80);
          v82 = (*(__int64 (__fastcall **)(__int64 *, void *))(*v79 + 24))(v79, v81);
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v82 + 64LL))(v82) )
            break;
          (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
        }
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 65, 0);
        v120 = (*(__int64 (__fastcall **)(__int64 *))(*v79 + 24))(v79);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v120 + 72LL))(v120, (__int64)v4 + 8);
        v121 = (*(__int64 (__fastcall **)(__int64 *))(*v79 + 24))(v79);
        LOBYTE(v122) = 1;
        v123 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, _BYTE, _BYTE))(*(_QWORD *)v121 + 80LL))(
                           v121,
                           &Buf1,
                           v122,
                           0,
                           0,
                           0);
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 65, *v123);
        MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
        v298[0] = 0;
        (*(void (__fastcall **)(__int64 *, GUID *, Jot::StaticContextReplication **))*v79)(
          v79,
          &GUID_4408663d_efc7_4f6f_8a9b_51bf50f25979,
          v298);
        v124 = v298[0];
        if ( v298[0] )
        {
          v168 = *(void (__fastcall **)(Jot::StaticContextReplication *, _QWORD))(*(_QWORD *)v298[0] + 48LL);
          v169 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, Jot **))(*((_QWORD *)v4 + 17) + 56LL))(
                             (__int64)v4 + 136,
                             &v307);
          v168(v124, *v169);
        }
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[65]);
        *((_DWORD *)this + 96) = 29;
        *((_DWORD *)this + 97) = 29;
        *((_DWORD *)this + 93) = 3;
        if ( v298[0] )
          (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v298[0] + 16LL))(v298[0]);
        v12 = *v79;
        goto LABEL_25;
      }
      v83 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v83 + 368LL))(v83, 1);
      Jot::CGraphIterator::CGraphIterator((Jot::CGraphIterator *)&v319, v293);
      v84 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25));
      if ( v84 )
      {
        (*(void (__fastcall **)(__int64, struct Jot::IGraphNode **))(*(_QWORD *)v84 + 200LL))(v84, &v295);
        LODWORD(v294) = 2048;
        v86 = v295;
      }
      else
      {
        v86 = 0;
        v295 = 0;
        LODWORD(v294) = 2048;
      }
      if ( !v86 )
      {
        if ( *((_BYTE *)this + 411) )
        {
          v297 = 0;
          v87 = v293;
          if ( v293 )
          {
            v88 = **(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot::StaticContextReplication **))v293;
            if ( (char *)v88 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
              MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
                v293,
                &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
                &v297);
            else
              v88(v293, &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b, &v297);
            v87 = v293;
          }
          v292 = 0;
          if ( v87 )
          {
            v89 = **(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot **))v87;
            if ( (char *)v89 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
              MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
                v87,
                &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b,
                &v292);
            else
              v89(v87, &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b, &v292);
          }
          *(_QWORD *)v314 = &v316;
          v315 = 0;
          v316 = &off_181515648;
          v317 = 0;
          v318[0] = 0;
          ((void (__fastcall *)(void ***, void ****, __int64))*off_181515648)(&off_181515648, &v316, 80);
          LOBYTE(v90) = 1;
          v92 = Jot::StaticContextReplication::GetTrackingPropertyFromReplicatorRole(
                  (Jot::StaticContextReplication *)*((unsigned int *)v4 + 18),
                  v90,
                  v91);
          Jot::StaticContextReplication::GetTrackedContexts(v297, v92, v314);
          v94 = 0;
          LODWORD(v294) = 0;
          if ( v315 > 0 )
          {
            do
            {
              v301 = 0;
              v277 = v292;
              v278 = *(_QWORD *)v292;
              v279 = *(void (__fastcall **)(Jot *, __int64, __int64, Jot::CReplicatorWithBranchBase **, _DWORD))(*(_QWORD *)v292 + 392LL);
              v306[0] = 20LL * v94;
              v280 = v306[0] + *(_QWORD *)(*(_QWORD *)v314 + 8LL);
              v281 = (*(__int64 (__fastcall **)(Jot *))(v278 + 24))(v292);
              LOBYTE(v290) = 0;
              v279(v277, v281, v280, &v301, (_DWORD)v290);
              if ( v301 )
              {
                v283 = *(void (__fastcall ****)(_QWORD, GUID *, Jot::StaticContextReplication **))(*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *, __int128 *, _QWORD))(*(_QWORD *)v301 + 528LL))(
                                                                                                    v301,
                                                                                                    &Buf1,
                                                                                                    *((unsigned int *)v4 + 18));
                v298[0] = 0;
                if ( v283 )
                  (**v283)(v283, &GUID_9d4c9098_ea4a_40d4_a98a_762d383e902e, v298);
                Ofc::TCntPtrList<Jot::INativeReplicator>::InsertHead((Ofc::CListImpl *)(this + 63));
                if ( v298[0] )
                  (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v298[0] + 16LL))(v298[0]);
                MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
              }
              else
              {
                LOBYTE(v282) = 1;
                v284 = Jot::StaticContextReplication::GetTrackingPropertyFromReplicatorRole(
                         (Jot::StaticContextReplication *)*((unsigned int *)v4 + 18),
                         v282,
                         *(_BYTE *)(*(_QWORD *)v314 + 8LL) + LOBYTE(v306[0]));
                Jot::StaticContextReplication::RemoveTrackedContext(
                  v297,
                  (struct Jot::IGraphSpaceNode *)v284,
                  v285,
                  v286);
              }
              MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v301);
              v94 = (_DWORD)v294 + 1;
              LODWORD(v294) = v94;
            }
            while ( v94 < v315 );
            v2 = v305;
          }
          v315 = 0;
          Mso::Memory::Free(v317, v93);
          MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v292);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v297);
        }
        else
        {
          v300[0] = 0;
          Child = Jot::CGraphIteratorImpl<Jot::CUsableAsGraphIterator<Jot::CGraphSpaceHierarchyFilter>>::PGoFirstChild((Jot::CGraphPath *)&v319);
          MsoCF::QI_OrNull<Jot::IGraphSpace,&__s_GUID const _GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b>(v298, Child);
          v127 = v298[0];
          v128 = 0;
          while ( 1 )
          {
            v300[0] = v127;
            v298[0] = 0;
            MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v128);
            MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v298[0]);
            if ( !v127 )
              break;
            Jot::CNativeReplicator::GetChildReplicatorForChild(v4, &Buf1, v127);
            Ofc::TCntPtrList<Jot::INativeReplicator>::InsertHead((Ofc::CListImpl *)(this + 63));
            MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
            v129 = Jot::CGraphIteratorImpl<Jot::CUsableAsGraphIterator<Jot::CGraphSpaceHierarchyFilter>>::PGoNextSiblingOrPop(
                     &v319,
                     0);
            MsoCF::QI_OrNull<Jot::IGraphSpace,&__s_GUID const _GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b>(v298, v129);
            v128 = v127;
            v127 = v298[0];
          }
          MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(0);
        }
LABEL_150:
        *v2 = 29;
        MsoCF::CIPtr<Jot::IObjectSpaceRevisionCache,Jot::IObjectSpaceRevisionCache>::Release(v295);
        Jot::CGraphIteratorBase::DisconnectFromGraph((Jot::CGraphIteratorBase *)&v319);
        Jot::CGraphPath::~CGraphPath((Jot::CGraphPath *)&v319);
        goto LABEL_26;
      }
      v311.m128i_i64[0] = (__int64)&v319;
      v311.m128i_i32[2] = v321;
      v312.m128i_i8[0] = 0;
      v181 = 0;
      *(_QWORD *)&Buf1 = 0;
      v182 = 0;
      v183 = (int)v294;
      while ( 1 )
      {
        LOBYTE(v85) = v182;
        v184 = (void (__fastcall ***)(_QWORD, GUID *, Jot::StaticContextReplication **))Jot::CPreOrderTraverser<Jot::CGraphIteratorGraphSpaceHierarchy>::UseNext(
                                                                                          &v311,
                                                                                          v85);
        v297 = 0;
        if ( v184 )
        {
          if ( (char *)**v184 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
            MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
              v184,
              &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b,
              &v297);
          else
            (**v184)(v184, &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b, &v297);
        }
        v185 = v297;
        v297 = 0;
        v186 = v181;
        v181 = v185;
        *(_QWORD *)&Buf1 = v185;
        MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v186);
        MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v297);
        if ( !v181 )
        {
          MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(0);
          v2 = v305;
          goto LABEL_150;
        }
        v302 = 0;
        v300[0] = (Jot::StaticContextReplication *)(*(__int64 (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v181 + 24LL))(v181);
        v306[0] = (*(__int64 (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v181 + 32LL))(v181);
        v272 = MsoCF::ExtendedGUID::operator==(v306[0], &Jot::c_gctxidRuntimeDefault);
        v274 = v273;
        if ( v272 )
          v274 = 0;
        v303 = (*(__int64 (__fastcall **)(struct Jot::IGraphNode *, Jot::StaticContextReplication *, __int64))(*(_QWORD *)v295 + 32LL))(
                 v295,
                 v300[0],
                 v274);
        if ( v303 )
          goto LABEL_458;
        v292 = 0;
        if ( **(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v181 == MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
          MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
            v181,
            &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
            &v292);
        else
          (**(void (__fastcall ***)(Jot::StaticContextReplication *, GUID *, Jot **))v181)(
            v181,
            &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
            &v292);
        v183 |= 0x80u;
        LODWORD(v294) = v183;
        LOBYTE(v291) = 1;
        if ( !Jot::StaticContextReplication::IsStaticContextParent(v292, v275) )
LABEL_458:
          LOBYTE(v291) = 0;
        if ( (v183 & 0x80u) != 0 )
        {
          v183 &= ~0x80u;
          if ( v292 )
            (*(void (__fastcall **)(Jot *))(*(_QWORD *)v292 + 16LL))(v292);
        }
        if ( (_BYTE)v291 )
        {
          if ( (*(unsigned __int8 (__fastcall **)(struct Jot::IGraphNode *, Jot::StaticContextReplication *, void *, _QWORD))(*(_QWORD *)v295 + 40LL))(
                 v295,
                 v300[0],
                 &Jot::c_gctxidRuntimeDefault,
                 v306[0]) )
          {
            goto LABEL_467;
          }
          v182 = 1;
        }
        else
        {
          v182 = v302;
        }
        if ( v303 )
        {
LABEL_467:
          v276 = *(void (__fastcall ****)(_QWORD, GUID *, Jot::CReplicatorWithBranchBase **))(*(__int64 (__fastcall **)(Jot::StaticContextReplication *, Jot::StaticContextReplication **, _QWORD))(*(_QWORD *)v181 + 528LL))(
                                                                                               v181,
                                                                                               &v299,
                                                                                               *((unsigned int *)v4 + 18));
          v301 = 0;
          if ( v276 )
            (**v276)(v276, &GUID_9d4c9098_ea4a_40d4_a98a_762d383e902e, &v301);
          Ofc::TCntPtrList<Jot::INativeReplicator>::InsertHead((Ofc::CListImpl *)(this + 63));
          if ( v301 )
            (*(void (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v301 + 16LL))(v301);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v299);
          v182 = 1;
        }
      }
    }
    if ( v8 == 26 )
    {
      v117 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 88LL))((__int64)v4 + 128);
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v117 + 120LL))(v117) )
      {
        v259 = (struct Jot::IGraphSpace *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
        Jot::CHandleSectionRenameByONO::CHandleSectionRenameByONO((Jot::CHandleSectionRenameByONO *)v314, v259);
        if ( v317 )
        {
          v260 = Jot::ErrFilePendingRename::ErrFilePendingRename(v308, 17065686);
          v261 = std::make_exception_ptr<Jot::ErrFilePendingRename>(&v311, v260);
          Jot::CAsyncResultBase::SetErrorForCompletion(this, v261);
          Jot::CHandleSectionRenameByONO::PerformRename((Jot::CHandleSectionRenameByONO *)v314);
          Jot::CHandleSectionRenameByONO::~CHandleSectionRenameByONO((Jot::CHandleSectionRenameByONO *)v314);
          goto LABEL_26;
        }
        Jot::CHandleSectionRenameByONO::~CHandleSectionRenameByONO((Jot::CHandleSectionRenameByONO *)v314);
      }
      goto LABEL_188;
    }
    v23 = v8 - 21;
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( !v26 )
          {
            v27 = this[52];
            if ( v27 )
            {
              v125 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *, __int128 *))(*(_QWORD *)v27 + 128LL))(
                                 v27,
                                 &Buf1);
              MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *v125);
              *((_DWORD *)this + 96) = 25;
              *((_DWORD *)this + 97) = 4;
              *((_DWORD *)this + 93) = 3;
              MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
            }
            else
            {
              *v2 = 25;
            }
            goto LABEL_26;
          }
          if ( v26 != 1 )
            goto LABEL_26;
          v130 = (Jot *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[61] + 96LL))(this[61]);
          v292 = v130;
          MsoCF::CIPtr<Jot::IGraphSpaceContent,Jot::IGraphSpaceContent>::AddRef(v130);
          v307 = v130;
          *(_QWORD *)&Buf1 = this + 52;
          if ( !this[52] )
            goto LABEL_237;
          v322 = 0;
          IsEducationNotebook = 0;
          v295 = (Jot::RevisionTimeLogger *)((char *)v4 + 136);
          v131 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*((_QWORD *)v4 + 17) + 56LL))(
                             (__int64)v4 + 136,
                             v306);
          v319 = (*(_QWORD *)std::chrono::steady_clock::now(v300) - *v131) / 1000000LL;
          v132 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
          v133 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v132 + 384LL))(v132);
          ContainingSection = Jot::SectionEditor::GetContainingSection(v306, v133);
          v304 = 0;
          Jot::CGiRef<Jot::CNodeRef<Jot::CSemNotebookTrait>,Jot::CSemNotebookTrait>::operator=(&v304, ContainingSection);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v306[0]);
          v136 = v304;
          if ( v304
            && (unsigned __int8)Jot::CSemNotebookGraphSpaceTrait_RejectDeleted<Jot::ISectionMetaData,131121>::IsValidGI_CheckedAlways_Throws(
                                  v135,
                                  v304) )
          {
            v226 = Jot::CGiRef<Jot::CNodeRef<Jot::CSemFolderTrait>,Jot::CSemFolderGSTrait>::UseNode(&v304);
            Jot::NotebookEditor::GetContainingNotebook(&v299, v226);
            v227 = Jot::CNodeRef<Jot::CSemPageContentTrait>::CNodeRef<Jot::CSemPageContentTrait>(v300, &v299);
            CachedFileIdentifier = Jot::NotebookEditor::GetCachedFileIdentifier(&v324, v227);
            if ( *(_BYTE *)(CachedFileIdentifier + 160) )
            {
              v229 = std::_Optional_construct_base<Jot::InkAnalyzer::CWord>::operator*(CachedFileIdentifier);
              std::_Optional_construct_base<Jot::FileIdentifier>::_Assign<Jot::FileIdentifier>(v320, v229);
            }
            else
            {
              std::_Optional_destruct_base<Jot::FileIdentifier,0>::reset(v320);
            }
            std::_Optional_destruct_base<Jot::FileIdentifier,0>::~_Optional_destruct_base<Jot::FileIdentifier,0>(&v324);
            v230 = Jot::CNodeRef<Jot::CSemPageContentTrait>::CNodeRef<Jot::CSemPageContentTrait>(&v297, &v299);
            IsEducationNotebook = Jot::NotebookEditor::IsEducationNotebook(v230);
            MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v299);
          }
          v324 = v319;
          std::optional<Jot::FileIdentifier>::optional<Jot::FileIdentifier>((Jot::FileIdentifier *)v325);
          v325[168] = IsEducationNotebook;
          Jot::CLegacyInboundLatencyLogger::OnEvent(&v324);
          v137 = Jot::OnInboundOfBelowSectionCompletedSuccessfully();
          v138 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
          v139 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[52] + 160LL))(this[52]);
          v140 = (_QWORD *)(*(__int64 (__fastcall **)(struct Jot::IGraphNode *, Jot::StaticContextReplication **))(*(_QWORD *)v295 + 56LL))(
                             v295,
                             v300);
          v141 = (_QWORD *)std::chrono::steady_clock::now(&v299);
          Jot::CNotifierHelper<Jot::CNotifierSingleThreadedConfig,std::chrono::duration<__int64,std::ratio<1,1000>> const,MsoCF::ExtendedGUID const &,Jot::IGraphSpace &>::Fire(
            v137,
            (*v141 - *v140) / 1000000LL,
            v139,
            v138);
          LOBYTE(v291) = 0;
          v142 = v301;
          v143 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v301 + 64LL))(v301);
          v144 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v143 + 40LL))(v143);
          v130 = v292;
          if ( (*(unsigned __int8 (__fastcall **)(Jot *))(*(_QWORD *)v292 + 136LL))(v292) )
          {
            v170 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
            v171 = Jot::ErrGraphSpace_ContentLockPresent::ErrGraphSpace_ContentLockPresent(v314, 17065685);
            v172 = std::make_exception_ptr<Jot::ErrGraphSpace_ContentLockPresent>(&v311, v171);
            v170(this, v172);
            if ( v136 )
            {
              Jot::CTextImporter::~CTextImporter(v136);
              operator delete(v136);
            }
            std::_Optional_destruct_base<Jot::FileIdentifier,0>::~_Optional_destruct_base<Jot::FileIdentifier,0>(v320);
LABEL_238:
            v12 = *(_QWORD *)v130;
            goto LABEL_25;
          }
          if ( *((_BYTE *)v142 + 112) )
          {
            v146 = (struct Jot::IRevision_MayNotBeOptimal *)*((_QWORD *)v142 + 15);
            v295 = v146;
            MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::AddRef(v146);
            *(_QWORD *)&v313[0] = v146;
            v147 = this + 52;
            if ( !Jot::AreEqualRevisions(this[52], v146, v148) )
            {
              MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::Assign((char *)v142 + 120, *v147);
              v150 = (void (__fastcall ***)(_QWORD, GUID *, struct Jot::IGraphNode **))(*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v142 + 64LL))(v142);
              v296 = 0;
              if ( v150 )
              {
                if ( (char *)**v150 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
                  MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
                    v150,
                    &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
                    &v296);
                else
                  (**v150)(v150, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v296);
              }
              v300[0] = 0;
              Jot::CGraphIterator::CGraphIterator((Jot::CGraphIterator *)&v324, v296);
              if ( Jot::CGraphIteratorBase::FRootAtMainGraphRoot((Jot::CGraphIteratorBase *)&v324) )
              {
                v231 = Jot::CGraphIteratorBase::PPopToParent((Jot::CGraphIteratorBase *)&v324);
                v232 = (Jot::StaticContextReplication *)&v324;
                if ( !v231 )
                  v232 = 0;
                v300[0] = v232;
              }
              v151 = *(Jot::StaticContextReplication **)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[60] + 96LL))(this[60]);
              MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::AddRef(v151);
              v297 = v151;
              v311.m128i_i64[0] = 0;
              v311.m128i_i32[2] = 0;
              if ( *((_BYTE *)this + 411) )
              {
                LOBYTE(v152) = 1;
                LODWORD(v294) = Jot::StaticContextReplication::GetTrackingPropertyFromReplicatorRole(
                                  (Jot::StaticContextReplication *)*((unsigned int *)v142 + 18),
                                  v152,
                                  v153);
                *(_QWORD *)&Buf1 = v296;
                v234 = MsoCF::LookupProperty((MsoCF *)(unsigned int)v294, v233);
                v299 = v234;
                if ( (v311.m128i_i32[2] & 0x2000000) != 0 )
                {
                  MsoCF::CPropertyData::FreeAndZero_ComplexType(&v311);
                  v234 = v299;
                }
                else
                {
                  v311.m128i_i64[0] = 0;
                }
                if ( (_QWORD)Buf1
                  && ((v235 = *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(*(_QWORD *)Buf1 + 48LL),
                       v235 != MsoCF::CPropertySet::FGetProperty_Imp)
                    ? ((char *)v235 != (char *)Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp
                     ? ((char *)v235 != (char *)Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp
                      ? (v236 = (*(__int64 (__fastcall **)(_QWORD, const struct MsoCF::PropertyInfo *, __m128i *))(*(_QWORD *)Buf1 + 48LL))(
                                  Buf1,
                                  v234,
                                  &v311))
                      : (v236 = Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(Buf1, v234, &v311)))
                     : (v236 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(Buf1, v234, &v311)))
                    : (v236 = MsoCF::CPropertySet::FGetProperty_Imp((MsoCF::CPropertySet *)Buf1, v234, &v311)),
                      v236) )
                {
                  v311.m128i_i32[2] = *((_DWORD *)v299 + 1);
                }
                else
                {
                  v311.m128i_i32[2] = 0;
                }
                *(_QWORD *)&Buf1 = *v147;
                v237 = (void (__fastcall ***)(_QWORD, GUID *, Jot::StaticContextReplication **))(*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v142 + 64LL))(v142);
                v299 = 0;
                if ( v237 )
                {
                  if ( (char *)**v237 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
                    MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
                      v237,
                      &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
                      &v299);
                  else
                    (**v237)(v237, &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b, &v299);
                }
                Jot::StaticContextReplication::AddTrackedContextsFromReferenceDelta(
                  v299,
                  (struct Jot::IGraphSpaceNode *)(unsigned int)v294,
                  (unsigned int)v151,
                  (struct Jot::IRevision *)Buf1,
                  v290);
                if ( v299 )
                  (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v299 + 16LL))(v299);
              }
              if ( *((_QWORD *)v142 + 23) )
              {
                v238 = MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::CIPtr<Jot::IRevision,Jot::IRevision>(
                         &Buf1,
                         this + 52);
                if ( (unsigned __int8)Jot::CNativeReplicator::IsRevisionInTransitList(v142, v238) )
                {
                  MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::operator=(&v297, this + 52);
                  v239 = MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::CIPtr<Jot::IRevision,Jot::IRevision>(
                           &Buf1,
                           this + 52);
                  Jot::CNativeReplicator::RemoveRevisionFromTransitList(v142, v239, 0);
                  v151 = v297;
                }
                else
                {
                  std::deque<MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>::_Tidy((char *)v142 + 152);
                }
              }
              *(_QWORD *)&Buf1 = *v147;
              v154 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v142 + 64LL))(v142);
              v299 = (Jot::StaticContextReplication *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v154 + 704LL))(
                                                        v154,
                                                        v314);
              v155 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v142 + 64LL))(v142);
              v294 = (MsoCF::IAtom *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v155 + 32LL))(v155);
              v156 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v142 + 64LL))(v142);
              v157 = (Jot *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v156 + 24LL))(v156);
              Jot::IntegrateBranchChanges(
                v157,
                v294,
                v299,
                0,
                (struct Jot::IRevision_MayNotBeOptimal *)Buf1,
                v292,
                v151,
                v300[0],
                v291);
              std::wstring::~wstring(v314);
              Jot::CReplicatorWithBranchBase::SetBranchBaseRevision(v142, *v147);
              if ( *((_BYTE *)this + 411) )
              {
                v240 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v142 + 64LL))(v142);
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v240 + 368LL))(v240, 1);
              }
              LOBYTE(v291) = 1;
              if ( (v311.m128i_i32[2] & 0x2000000) != 0 )
                MsoCF::CPropertyData::FreeAndZero_ComplexType(&v311);
              if ( v151 )
                (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v151 + 8LL))(v151);
              Jot::CGraphIteratorBase::DisconnectFromGraph((Jot::CGraphIteratorBase *)&v324);
              Jot::CGraphPath::~CGraphPath((Jot::CGraphPath *)&v324);
              if ( v296 )
                (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v296 + 16LL))(v296);
              v146 = v295;
            }
            if ( v146 )
              (*(void (__fastcall **)(struct Jot::IRevision_MayNotBeOptimal *))(*(_QWORD *)v146 + 8LL))(v146);
          }
          else
          {
            if ( v144 )
            {
              v147 = (struct Jot::IRevision **)Buf1;
            }
            else
            {
              LOBYTE(v145) = 1;
              v147 = this + 52;
              (*(void (__fastcall **)(Jot *, Jot::RevisionTimeLogger *, __int64, _QWORD))(*(_QWORD *)v292 + 80LL))(
                v292,
                this[52],
                v145,
                0);
              LOBYTE(v291) = 1;
            }
            MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::operator=((char *)v142 + 272, v147);
          }
          if ( !(_BYTE)v291 )
          {
LABEL_234:
            if ( v136 )
            {
              Jot::CTextImporter::~CTextImporter(v136);
              operator delete(v136);
            }
            std::_Optional_destruct_base<Jot::FileIdentifier,0>::~_Optional_destruct_base<Jot::FileIdentifier,0>(v320);
            v2 = v305;
LABEL_237:
            *v2 = 26;
            if ( !v130 )
              goto LABEL_26;
            goto LABEL_238;
          }
          if ( *((_DWORD *)v142 + 76) )
          {
            if ( (*(unsigned __int8 (__fastcall **)(Jot *, struct Jot::IRevision *))(*(_QWORD *)v292 + 88LL))(
                   v292,
                   *v147) )
            {
              Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v293, 0x3FFFu);
              Jot::GraphSpaceEditor::SetLastGenerationAsCurrent(
                v293,
                (struct Jot::IGraphNode *)*((unsigned int *)v142 + 76),
                v242);
LABEL_414:
              Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)&Buf1);
              goto LABEL_415;
            }
            if ( Jot::GraphSpaceEditor::HasPendingChildGraphSpaceDeletes(v293, 0, v241) )
            {
              Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v293, 0x3FFFu);
              Jot::GraphSpaceEditor::FinalizeChildGraphSpaceDeletes(v293, v243);
              goto LABEL_414;
            }
          }
LABEL_415:
          Jot::UnreadEditor::OnGraphSpaceInbound(v293, v149);
          goto LABEL_234;
        }
        if ( !*((_BYTE *)v4 + 112) )
        {
          *v2 = 24;
          goto LABEL_26;
        }
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[60]);
        *((_DWORD *)this + 96) = 24;
      }
      else
      {
        if ( *((_BYTE *)v4 + 112) )
        {
          BranchBaseRevision = (_QWORD *)Jot::CReplicatorWithBranchBase::GetBranchBaseRevision(v4, &Buf1);
          Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncResult_HierarchicalContentLoader>::operator=(
            this + 60,
            *BranchBaseRevision);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
        }
        if ( !this[61] )
        {
          v162 = (_QWORD *)(***((__int64 (__fastcall ****)(_QWORD, __int128 *, __int64))v4 + 8))(
                             *((_QWORD *)v4 + 8),
                             &Buf1,
                             1);
          Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 61, *v162);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
        }
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[61]);
        *((_DWORD *)this + 96) = 23;
      }
      *((_DWORD *)this + 97) = 4;
      goto LABEL_136;
    }
    v311 = 0;
    __ExceptionPtrCreate(&v311);
    v245 = this[59];
    if ( v245
      && (*(unsigned __int8 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v245 + 32LL))(v245)
      && (v246 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[59] + 80LL))(this[59]),
          !(unsigned __int8)std::operator==(v246)) )
    {
      v247 = this[59];
    }
    else
    {
      v248 = this[57];
      if ( !v248 )
        goto LABEL_425;
      if ( !(*(unsigned __int8 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v248 + 32LL))(v248) )
        goto LABEL_425;
      v249 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[57] + 80LL))(this[57]);
      if ( (unsigned __int8)std::operator==(v249) )
        goto LABEL_425;
      v247 = this[57];
    }
    v250 = (const void *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v247 + 80LL))(v247);
    __ExceptionPtrAssign(&v311, v250);
LABEL_425:
    if ( (unsigned __int8)Jot::IsError<Jot::ErrObjectSpaceStoreInCellStorage_MissingRevisionManifest>(&v311)
      || (unsigned __int8)Jot::IsError<Jot::ErrObjectSpaceStoreInCellStorage_MissingObjectGroup>(&v311) )
    {
      MsoShipAssertTagProc(1650537061);
      if ( Jot::ShouldLogTtid((Jot *)0x40B593, 0x1008Fu, 4u, v251) )
        Jot::Log_Impl<wchar_t [90],std::exception_ptr>(v253, v252, v254, v255, (__int64)&v311);
      v292 = 0;
      if ( v293 )
      {
        v256 = **(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot **))v293;
        if ( (char *)v256 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
          MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
            v293,
            &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b,
            &v292);
        else
          v256(v293, &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b, &v292);
      }
      sub_1803FA270(&v301, v292);
      MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v292);
      v257 = v301;
      if ( v301 )
      {
        Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)v306, v301, 0x3FFFu);
        *(_QWORD *)&Buf1 = v301;
        MsoCF::IPropertySet::CEntryBase<Jot::PropertySpace_Jot14::prtidLastSynchedRevisionKnowledge,MsoCF::CIPtr<MsoCF::IAtom,MsoCF::IAtom>>::Remove(&Buf1);
        Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)v306);
        v257 = v301;
      }
      MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v257);
    }
    v258 = (void (__fastcall *)(Jot::RevisionTimeLogger **, _OWORD *))*((_QWORD *)*this + 12);
    v313[0] = 0;
    __ExceptionPtrCopy(v313, &v311);
    v258(this, v313);
    __ExceptionPtrDestroy(&v311);
    goto LABEL_26;
  }
  v173 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
  v174 = Jot::ErrNativeReplicator_ReplicationNotAllowed::ErrNativeReplicator_ReplicationNotAllowed(v314, 17065681);
  v175 = std::make_exception_ptr<Jot::ErrNativeReplicator_ReplicationNotAllowed>(&v311, v174);
  v173(this, v175);
LABEL_80:
  if ( v293 )
    (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v293 + 16LL))(v293);
}

```

## disassembly

```asm
0x180206900  mov     rax, rsp
0x180206903  mov     [rax+18h], rbx
0x180206907  mov     [rax+20h], rsi
0x18020690b  push    rdi
0x18020690c  push    r12
0x18020690e  push    r13
0x180206910  push    r14
0x180206912  push    r15
0x180206914  sub     rsp, 430h
0x18020691b  movaps  xmmword ptr [rax-38h], xmm6
0x18020691f  movaps  xmmword ptr [rax-48h], xmm7
0x180206923  movaps  xmmword ptr [rax-58h], xmm8
0x180206928  movaps  xmmword ptr [rax-68h], xmm9
0x18020692d  mov     rax, cs:__security_cookie
0x180206934  xor     rax, rsp
0x180206937  mov     [rsp+458h+var_78], rax
0x18020693f  mov     rsi, rdx
0x180206942  mov     [rsp+458h+var_3A0], rdx
0x18020694a  mov     r13, rcx
0x18020694d  mov     [rsp+458h+var_3E0], rcx
0x180206952  xor     r12d, r12d
0x180206955  mov     dword ptr [rsp+458h+var_400], r12d
0x18020695a  mov     r14, [rcx+190h]
0x180206961  mov     [rsp+458h+var_3B8], r14
0x180206969  test    r14, r14
0x18020696c  jz      loc_1802088A7
0x180206972  call    ?GetOneNoteDotComNetworkStatusInstance@Jot@@YAAEAVCNetworkStatus@1@XZ; Jot::GetOneNoteDotComNetworkStatusInstance(void)
0x180206977  mov     rdx, rax
0x18020697a  mov     rcx, [rax]
0x18020697d  mov     rax, [rcx]
0x180206980  mov     rcx, rdx
0x180206983  call    cs:__guard_dispatch_icall_fptr
0x180206989  mov     ecx, [rax+58h]
0x18020698c  dec     ecx; this
0x18020698e  lea     r15d, [r12+1]
0x180206993  cmp     ecx, r15d
0x180206996  jbe     loc_180208910
0x18020699c  mov     rax, [r14]
0x18020699f  mov     rcx, r14
0x1802069a2  mov     rax, [rax+40h]
0x1802069a6  call    cs:__guard_dispatch_icall_fptr
0x1802069ac  mov     [rsp+458h+var_408], r12
0x1802069b1  lea     rbx, ?QueryInterface@?$CJotComObjectForMakeComObject@VCRootGraphSpace@Jot@@@MsoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(_GUID const &,void * *)
0x1802069b8  test    rax, rax
0x1802069bb  jz      short loc_1802069E1
0x1802069bd  mov     rcx, [rax]
0x1802069c0  mov     r9, [rcx]
0x1802069c3  lea     r8, [rsp+458h+var_408]
0x1802069c8  lea     rdx, _GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75
0x1802069cf  mov     rcx, rax
0x1802069d2  cmp     r9, rbx
0x1802069d5  jnz     loc_180206BF6
0x1802069db  call    ?QueryInterface@?$CJotComObjectForMakeComObject@VCRootGraphSpace@Jot@@@MsoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(_GUID const &,void * *)
0x1802069e0  nop
0x1802069e1  cmp     [rsp+458h+var_408], r12
0x1802069e6  jz      loc_180208444
0x1802069ec  mov     eax, [rsi]
0x1802069ee  cmp     eax, 14h
0x1802069f1  ja      loc_180206B3B
0x1802069f7  jz      loc_180208EE9
0x1802069fd  cmp     eax, 0Fh
0x180206a00  ja      loc_180206F8C
0x180206a06  jz      loc_180208619
0x180206a0c  mov     edi, 0Ah
0x180206a11  sub     eax, edi
0x180206a13  jnz     loc_180206B6F
0x180206a19  mov     rax, [r14]
0x180206a1c  mov     rcx, r14
0x180206a1f  mov     rax, [rax+40h]
0x180206a23  call    cs:__guard_dispatch_icall_fptr
0x180206a29  mov     [rsp+458h+var_3F8], r12
0x180206a2e  test    rax, rax
0x180206a31  jz      short loc_180206A57
0x180206a33  mov     rcx, [rax]
0x180206a36  mov     r9, [rcx]
0x180206a39  lea     r8, [rsp+458h+var_3F8]
0x180206a3e  lea     rdx, _GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75
0x180206a45  mov     rcx, rax
0x180206a48  cmp     r9, rbx
0x180206a4b  jnz     loc_180207310
0x180206a51  call    ?QueryInterface@?$CJotComObjectForMakeComObject@VCRootGraphSpace@Jot@@@MsoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(_GUID const &,void * *)
0x180206a56  nop
0x180206a57  mov     rcx, [r14+0C8h]
0x180206a5e  mov     rax, [rcx]
0x180206a61  mov     rax, [rax+78h]
0x180206a65  call    cs:__guard_dispatch_icall_fptr
0x180206a6b  test    rax, rax
0x180206a6e  jz      loc_180206CED
0x180206a74  lea     rax, [r14+118h]
0x180206a7b  cmp     [rax], r12
0x180206a7e  jnz     loc_1802072E3
0x180206a84  lea     rdx, [r13+108h]
0x180206a8b  mov     rcx, rax
0x180206a8e  call    ?Assign@?$CIPtr@UICellStorage@CsiCell@@U12@@MsoCF@@QEAAXPEAUICellStorage@CsiCell@@@Z; MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(CsiCell::ICellStorage *)
0x180206a93  mov     [r13+1F0h], r12
0x180206a9a  cmp     [r14+134h], r12d
0x180206aa1  jnz     loc_1802075D7
0x180206aa7  mov     rcx, [r14+0C8h]
0x180206aae  mov     rax, [rcx]
0x180206ab1  mov     rax, [rax+78h]
0x180206ab5  call    cs:__guard_dispatch_icall_fptr
0x180206abb  test    rax, rax
0x180206abe  jnz     loc_180208B51
0x180206ac4  cmp     [r13+199h], r12b
0x180206acb  jnz     loc_1802071C0
0x180206ad1  mov     dword ptr [rsi], 0Eh
0x180206ad7  mov     rcx, [rsp+458h+var_3F8]
0x180206adc  test    rcx, rcx
0x180206adf  jz      short loc_180206AF0
0x180206ae1  mov     rax, [rcx]
0x180206ae4  mov     rax, [rax+10h]
0x180206ae8  call    cs:__guard_dispatch_icall_fptr
0x180206aee  nop
0x180206aef  nop
0x180206af0  mov     rcx, [rsp+458h+var_408]
0x180206af5  call    ?Release@?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@CAXPEAUIProgress@ProgressUI@OneNote@@@Z; MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(OneNote::ProgressUI::IProgress *)
0x180206afa  mov     rcx, [rsp+458h+var_78]
0x180206b02  xor     rcx, rsp; StackCookie
0x180206b05  call    __security_check_cookie
0x180206b0a  lea     r11, [rsp+458h+var_28]
0x180206b12  mov     rbx, [r11+40h]
0x180206b16  mov     rsi, [r11+48h]
0x180206b1a  movaps  xmm6, xmmword ptr [r11-10h]
0x180206b1f  movaps  xmm7, xmmword ptr [r11-20h]
0x180206b24  movaps  xmm8, xmmword ptr [r11-30h]
0x180206b29  movaps  xmm9, xmmword ptr [r11-40h]
0x180206b2e  mov     rsp, r11
0x180206b31  pop     r15
0x180206b33  pop     r14
0x180206b35  pop     r13
0x180206b37  pop     r12
0x180206b39  pop     rdi
0x180206b3a  retn
0x180206b3b  cmp     eax, 1Ah
0x180206b3e  jbe     loc_180206C49
0x180206b44  sub     eax, 1Bh
0x180206b47  jnz     loc_180206C04
0x180206b4d  cmp     [r13+198h], r12b
0x180206b54  jnz     loc_180206C8E
0x180206b5a  cmp     [r13+19Bh], r12b
0x180206b61  jnz     loc_180206C8E
0x180206b67  mov     dword ptr [rsi], 1Dh
0x180206b6d  jmp     short loc_180206AF0
0x180206b6f  sub     eax, 1
0x180206b72  jz      loc_180208A17
0x180206b78  sub     eax, 1
0x180206b7b  jz      loc_180207112
0x180206b81  sub     eax, 1
0x180206b84  jz      loc_18020891F
0x180206b8a  cmp     eax, 1
0x180206b8d  jnz     loc_180206AF0
0x180206b93  mov     rax, [r14]
0x180206b96  mov     rcx, r14
0x180206b99  mov     rax, [rax+40h]
0x180206b9d  call    cs:__guard_dispatch_icall_fptr
0x180206ba3  lea     rdx, [rsp+458h+var_3C8]
0x180206bab  mov     rcx, rax
0x180206bae  call    ?GetBackingRevisionStore@IGraphSpace@Jot@@QEAA?AV?$CIPtr@UICacheRevisionStore@Jot@@U12@@MsoCF@@XZ; Jot::IGraphSpace::GetBackingRevisionStore(void)
0x180206bb3  mov     rdx, rax
0x180206bb6  lea     rcx, [r13+1D0h]
0x180206bbd  call    ??$?4UIObjectSpaceStoreOnCellStorage@Jot@@U01@@?$CIPtr@UIServerStore@Jot@@U12@@MsoCF@@QEAAAEAV01@$$QEAV?$CIPtr@UIObjectSpaceStoreOnCellStorage@Jot@@U12@@1@@Z; MsoCF::CIPtr<Jot::IServerStore,Jot::IServerStore>::operator=<Jot::IObjectSpaceStoreOnCellStorage,Jot::IObjectSpaceStoreOnCellStorage>(MsoCF::CIPtr<Jot::IObjectSpaceStoreOnCellStorage,Jot::IObjectSpaceStoreOnCellStorage> &&)
0x180206bc2  nop
0x180206bc3  mov     rcx, [rsp+458h+var_3C8]
0x180206bcb  test    rcx, rcx
0x180206bce  jz      short loc_180206BDE
0x180206bd0  mov     rax, [rcx]
0x180206bd3  mov     rax, [rax+8]
0x180206bd7  call    cs:__guard_dispatch_icall_fptr
0x180206bdd  nop
0x180206bde  cmp     [r13+1D0h], r12
0x180206be5  jz      loc_180208255
0x180206beb  mov     dword ptr [rsi], 0Ch
0x180206bf1  jmp     loc_180206AF0
0x180206bf6  mov     rax, r9
0x180206bf9  call    cs:__guard_dispatch_icall_fptr
0x180206bff  jmp     loc_1802069E1
0x180206c04  sub     eax, 1
0x180206c07  jz      loc_180207403
0x180206c0d  sub     eax, 1
0x180206c10  jnz     loc_180207660
0x180206c16  lea     rbx, [r13+208h]
0x180206c1d  mov     rcx, [rbx]
0x180206c20  test    rcx, rcx
0x180206c23  jnz     loc_1802081A8
0x180206c29  cmp     [r13+200h], r12d
0x180206c30  jnz     loc_18020731E
0x180206c36  mov     rax, [rsp+458h+var_3A0]
0x180206c3e  mov     dword ptr [rax], 1Eh
0x180206c44  jmp     loc_180206AF0
0x180206c49  jz      loc_18020792D
0x180206c4f  sub     eax, 15h
0x180206c52  jz      loc_1802094B6
0x180206c58  sub     eax, 1
0x180206c5b  jz      loc_1802073B4
0x180206c61  sub     eax, 1
0x180206c64  jz      loc_180207705
0x180206c6a  sub     eax, 1
0x180206c6d  jnz     loc_180207C78
0x180206c73  mov     rcx, [r13+1A0h]
0x180206c7a  test    rcx, rcx
0x180206c7d  jnz     loc_180207B41
0x180206c83  mov     dword ptr [rsi], 19h
0x180206c89  jmp     loc_180206AF0
0x180206c8e  mov     rcx, [r14+0C8h]
0x180206c95  mov     rax, [rcx]
0x180206c98  mov     rax, [rax+78h]
0x180206c9c  call    cs:__guard_dispatch_icall_fptr
0x180206ca2  mov     r8, rax
0x180206ca5  test    rax, rax
0x180206ca8  jnz     loc_180208233
0x180206cae  mov     [rsp+458h+var_3E0], r12
0x180206cb3  mov     rax, r12
0x180206cb6  mov     ebx, 420h
0x180206cbb  test    rax, rax
0x180206cbe  jnz     loc_180209BF5
0x180206cc4  mov     dil, r12b
0x180206cc7  test    bl, 40h
0x180206cca  jnz     loc_180209C53
0x180206cd0  test    bl, 20h
0x180206cd3  jnz     loc_1802076E5
0x180206cd9  test    dil, dil
0x180206cdc  jnz     loc_180209C76
0x180206ce2  mov     dword ptr [rsi], 1Ch
0x180206ce8  jmp     loc_180206AF0
0x180206ced  mov     rcx, [r14+0C8h]
0x180206cf4  mov     rax, [rcx]
0x180206cf7  mov     rax, [rax+70h]
0x180206cfb  call    cs:__guard_dispatch_icall_fptr
0x180206d01  test    rax, rax
0x180206d04  jz      loc_180206A74
0x180206d0a  mov     rcx, [r14+0C8h]
0x180206d11  mov     rax, [rcx]
0x180206d14  mov     rax, [rax+70h]
0x180206d18  call    cs:__guard_dispatch_icall_fptr
0x180206d1e  mov     rdx, rax
0x180206d21  mov     rcx, [rax]
0x180206d24  mov     rax, [rcx+88h]
0x180206d2b  mov     rcx, rdx
0x180206d2e  call    cs:__guard_dispatch_icall_fptr
0x180206d34  test    rax, rax
0x180206d37  jz      loc_180206A74
0x180206d3d  mov     rcx, [r14+0C8h]
0x180206d44  mov     rax, [rcx]
0x180206d47  mov     rax, [rax+70h]
0x180206d4b  call    cs:__guard_dispatch_icall_fptr
0x180206d51  mov     rdx, rax
0x180206d54  mov     rcx, [rax]
0x180206d57  mov     rax, [rcx+88h]
0x180206d5e  mov     rcx, rdx
0x180206d61  call    cs:__guard_dispatch_icall_fptr
0x180206d67  mov     r8, rax
0x180206d6a  mov     rcx, [rax]
0x180206d6d  mov     rax, [rcx+0D0h]
0x180206d74  lea     rdx, [rsp+458h+var_3F0]
0x180206d79  mov     rcx, r8
0x180206d7c  call    cs:__guard_dispatch_icall_fptr
0x180206d82  nop
0x180206d83  mov     rax, r12
0x180206d86  mov     [rsp+458h+var_3E0], rax
0x180206d8b  mov     rcx, [rsp+458h+var_3F0]
0x180206d90  test    rcx, rcx
0x180206d93  jz      loc_1802076F4
0x180206d99  mov     rax, [rcx]
0x180206d9c  lea     r8, [rsp+458h+var_3E0]
0x180206da1  lea     rdx, _GUID_9f7ae2e4_9cb0_45c1_9e5a_95fdd6d001ee
0x180206da8  mov     rax, [rax]
0x180206dab  call    cs:__guard_dispatch_icall_fptr
0x180206db1  mov     rax, [rsp+458h+var_3E0]
0x180206db6  mov     rcx, [rsp+458h+var_3F0]
0x180206dbb  test    rax, rax
0x180206dbe  mov     bl, r15b
0x180206dc1  jz      loc_1802076F4
0x180206dc7  mov     rcx, [rax]
0x180206dca  mov     rdx, [rcx+10h]
0x180206dce  mov     rcx, rax
0x180206dd1  mov     rax, rdx
0x180206dd4  call    cs:__guard_dispatch_icall_fptr
0x180206dda  mov     rcx, [rsp+458h+var_3F0]
0x180206ddf  test    bl, bl
0x180206de1  jnz     loc_180207968
0x180206de7  xorps   xmm0, xmm0
0x180206dea  movups  [rsp+458h+var_310], xmm0
0x180206df2  movdqa  xmm9, cs:__xmm@00000000000000070000000000000000
0x180206dfb  movdqu  [rsp+458h+var_300], xmm9
0x180206e05  mov     word ptr [rsp+458h+var_310], r12w
0x180206e0e  movups  xmm8, [rsp+458h+var_310]
0x180206e17  movups  [rsp+458h+var_2F0], xmm8
0x180206e20  movups  [rsp+458h+var_2E0], xmm9
0x180206e29  lea     rcx, [rsp+458h+var_310]; void *
0x180206e31  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180206e36  lea     rdx, [r14+50h]
0x180206e3a  lea     rcx, [rsp+458h+var_398]
0x180206e42  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180206e47  movups  xmm6, xmmword ptr [rax]
0x180206e4a  movups  [rsp+458h+var_310], xmm6
0x180206e52  movups  xmm7, xmmword ptr [rax+10h]
0x180206e56  movups  [rsp+458h+var_300], xmm7
0x180206e5e  mov     [rax], r12w
0x180206e62  mov     [rax+10h], r12
0x180206e66  mov     qword ptr [rax+18h], 7
  ... truncated ...
```
