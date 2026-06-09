# Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch::OnPoll(uint *)

- ea: `0x1806b4110`
- end: `0x1806b4d1d`
- name: `?OnPoll@CObjectSpaceStoreOnCellStorage_GetRevisionBatch@Jot@@MEAAXPEAI@Z`
- size: `3085`
- prototype: `void __fastcall(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `25`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180032260`
- `0x18007293c`
- `0x18007b364`
- `0x18008ee00`
- `0x1801fcbf0`
- `0x1802ad2b0`
- `0x1802ba034`
- `0x1802e2870`
- `0x1802e3f10`
- `0x1802e4a58`
- `0x1802e4c00`
- `0x1802e5060`
- `0x1802e5170`
- `0x1802e5190`
- `0x180485a14`
- `0x1804a7e94`
- `0x18055fb9c`
- `0x1806b4110`
- `0x1806b4d20`
- `0x1806b5034`
- `0x1806b5098`
- `0x1806b50c0`
- `0x18076396c`
- `0x1808b9b60`
- `0x1808e7bd4`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x1806b4bcb`
- `KERNEL32!GetTickCount64` at `0x1806b4bcb`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1806b4176`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1806b43be`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1806b4bae`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1806b4176`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1806b43be`
- `KERNEL32!QueryUnbiasedInterruptTime` at `0x1806b4bae`
- `MSVCP140!_Mtx_unlock` at `0x1806b499b`
- `MSVCP140!_Mtx_unlock` at `0x1806b499b`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1806b49c7`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1806b4ab6`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1806b49c7`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1806b4ab6`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1806b4312`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1806b4386`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1806b4312`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1806b4386`
- `Csi!?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z` at `0x1806b44fe`
- `Csi!?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z` at `0x1806b451d`
- `Csi!?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z` at `0x1806b44fe`
- `Csi!?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z` at `0x1806b451d`
- `Csi!?FGetCellKnowledge@Csi@@YA_NPEAUIKnowledge@1@PEAPEAUICellKnowledge@CsiCell@@@Z` at `0x1806b45b7`
- `Csi!?FGetCellKnowledge@Csi@@YA_NPEAUIKnowledge@1@PEAPEAUICellKnowledge@CsiCell@@@Z` at `0x1806b45b7`

## pseudocode

```c
void __fastcall Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch::OnPoll(
        Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *this,
        unsigned int *a2)
{
  _QWORD *v3; // rcx
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rbx
  const void *v7; // rax
  char v8; // al
  _QWORD *v9; // rbx
  __int64 v10; // rax
  __int128 *v11; // rdx
  const void *v12; // rax
  struct Csi::IKnowledge **v13; // rdx
  _QWORD *v14; // rcx
  __int64 v15; // rax
  Csi **v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rax
  Csi *v19; // rdi
  void (__fastcall *v20)(Csi *, __int64); // rbx
  __int64 v21; // rax
  struct CsiCell::ICellKnowledge **v22; // r8
  __int64 v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rbx
  void (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // r9
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  void (__fastcall ***v30)(_QWORD, GUID *, Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch **); // rcx
  __int64 v31; // rax
  struct _Mtx_internal_imp_t *v32; // r14
  __int64 RefFromNonNull; // r14
  __int64 v34; // r15
  __int64 v35; // rsi
  void (__fastcall ***v36)(_QWORD); // rsi
  Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *v37; // rsi
  int v38; // eax
  __int64 v39; // rax
  struct Jot::IObjectSpaceRevisionCache *v40; // r14
  __int64 v41; // r15
  _QWORD *v42; // rsi
  Jot::CObjectSpaceRevisionStoreInCellStorage *v43; // rcx
  void (__fastcall *v44)(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *, __int128 *); // rsi
  void (__fastcall *v45)(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *, __int128 *); // rbx
  __int64 v46; // rdi
  __int64 v47; // rcx
  Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *v48; // rbx
  __int64 v49; // rax
  struct Jot::IObjectSpaceRevisionCache *v50; // rbx
  __int64 v51; // rcx
  __int64 v52; // rdx
  unsigned __int64 v53; // rdx
  unsigned int v54; // r8d
  ULONGLONG *v55; // rdi
  __int64 v56; // r12
  __int64 v57; // rax
  __int64 v58; // rax
  Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *v59; // rdi
  _QWORD *v60; // rsi
  __int64 v61; // [rsp+28h] [rbp-E0h]
  __int64 v62; // [rsp+30h] [rbp-D8h]
  __int64 v63; // [rsp+38h] [rbp-D0h]
  __int64 v64; // [rsp+40h] [rbp-C8h]
  __int128 v65; // [rsp+78h] [rbp-90h] BYREF
  char v66; // [rsp+88h] [rbp-80h] BYREF
  char v67; // [rsp+89h] [rbp-7Fh]
  char v68; // [rsp+8Ah] [rbp-7Eh]
  __int64 v69; // [rsp+90h] [rbp-78h] BYREF
  __int64 v70; // [rsp+98h] [rbp-70h] BYREF
  Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *v71; // [rsp+A0h] [rbp-68h] BYREF
  Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *v72; // [rsp+A8h] [rbp-60h] BYREF
  _Mtx_t v73; // [rsp+B0h] [rbp-58h] BYREF
  struct Jot::IObjectSpaceRevisionCache *v74; // [rsp+B8h] [rbp-50h] BYREF
  void (__fastcall ***v75)(_QWORD); // [rsp+C0h] [rbp-48h] BYREF
  __int64 v76; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v77; // [rsp+D0h] [rbp-38h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v79; // [rsp+E0h] [rbp-28h] BYREF
  char ***v80; // [rsp+E8h] [rbp-20h] BYREF
  const char *v81; // [rsp+F0h] [rbp-18h]
  void **v82; // [rsp+F8h] [rbp-10h] BYREF
  void **v83; // [rsp+100h] [rbp-8h]
  const wchar_t *v84; // [rsp+108h] [rbp+0h]
  __int64 v85; // [rsp+110h] [rbp+8h]
  _Mtx_t *v86; // [rsp+118h] [rbp+10h]
  __int16 v87; // [rsp+120h] [rbp+18h]
  void **v88; // [rsp+128h] [rbp+20h] BYREF
  void **v89; // [rsp+130h] [rbp+28h]
  char *v90; // [rsp+138h] [rbp+30h]
  __int64 v91; // [rsp+140h] [rbp+38h]
  Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch **v92; // [rsp+148h] [rbp+40h]
  __int16 v93; // [rsp+150h] [rbp+48h]
  __int64 v94; // [rsp+158h] [rbp+50h]
  __int64 v95; // [rsp+160h] [rbp+58h]
  char v96[8]; // [rsp+168h] [rbp+60h] BYREF
  __int64 *v97; // [rsp+170h] [rbp+68h]
  __int64 *v98; // [rsp+178h] [rbp+70h]
  char *v99; // [rsp+180h] [rbp+78h]
  __int64 *v100; // [rsp+188h] [rbp+80h]
  __int64 *v101; // [rsp+190h] [rbp+88h]
  _QWORD v102[5]; // [rsp+198h] [rbp+90h] BYREF
  __int16 v103; // [rsp+1C0h] [rbp+B8h]
  __int128 v104; // [rsp+1E0h] [rbp+D8h] BYREF
  char *v105; // [rsp+1F0h] [rbp+E8h]

  v71 = this;
  switch ( *a2 )
  {
    case 0xAu:
      *(_QWORD *)&v65 = &off_1810FB000;
      *((_QWORD *)&v65 + 1) = "COSRS/CS::GetRevisionsInBatch_Started";
      Jot::Logging::LogTraceTag<>(19169755, &v65, 100);
      (*(void (__fastcall **)(_QWORD, void (__fastcall ****)(_QWORD)))(**((_QWORD **)this + 49) + 200LL))(
        *((_QWORD *)this + 49),
        &v75);
      if ( v75 )
      {
        v45 = *(void (__fastcall **)(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *, __int128 *))(*(_QWORD *)this + 96LL);
        v65 = 0;
        __ExceptionPtrCreate(&v65);
        v45(this, &v65);
      }
      else
      {
        v46 = Jot::EDP::Identity::Identity(
                (Jot::EDP::Identity *)&v88,
                (const struct Jot::EDP::Identity *)(*((_QWORD *)this + 49) + 352LL));
        v72 = 0;
        v47 = *((_QWORD *)this + 49);
        v48 = *(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch **)(v47 + 16);
        if ( v48 )
          (**(void (__fastcall ***)(_QWORD))v48)(*(_QWORD *)(v47 + 16));
        v72 = v48;
        Jot::CreateCellStorageCacheOnLocalStore(&v74, *(_QWORD *)(*((_QWORD *)this + 49) + 144LL), &v72, v46);
        v49 = 0;
        v70 = 0;
        v50 = v74;
        if ( v74 )
        {
          (**(void (__fastcall ***)(struct Jot::IObjectSpaceRevisionCache *, GUID *, __int64 *))v74)(
            v74,
            &GUID_431c255b_a1ee_4683_81ff_0b82b915f89d,
            &v70);
          v49 = v70;
        }
        v51 = 0;
        v70 = 0;
        v52 = *((_QWORD *)this + 58);
        *((_QWORD *)this + 58) = v49;
        if ( v52 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
          v51 = v70;
        }
        if ( v51 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        QueryUnbiasedInterruptTime((PULONGLONG)this + 61);
        v55 = (ULONGLONG *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)8, v53, v54);
        *(_QWORD *)&v65 = v55;
        if ( v55 )
          *v55 = GetTickCount64();
        else
          v55 = 0;
        MsoCF::COwnerPtr<Jot::CCellStorageRequestExecutionTimer,MsoCF::COwnerPtr_Delete_Auto<Jot::CCellStorageRequestExecutionTimer>>::Attach(
          (char *)this + 456,
          v55);
        v56 = *((_QWORD *)this + 58);
        v57 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v71 + 49) + 144LL))(*((_QWORD *)v71 + 49));
        v58 = Jot::ExecuteQueryChanges(&v79, v57, v56, (char *)v71 + 400);
        v59 = v71;
        v60 = (_QWORD *)((char *)v71 + 448);
        Mso::TCntPtr<Mso::Async::IDispatchQueue>::operator=((char *)v71 + 448, v58);
        if ( v79 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v79 + 16LL))(v79);
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign((char *)v59 + 376, *v60);
        *((_DWORD *)v59 + 96) = 11;
        *((_DWORD *)v59 + 97) = 12;
        *((_DWORD *)v59 + 93) = 3;
        if ( v50 )
          (*(void (__fastcall **)(struct Jot::IObjectSpaceRevisionCache *))(*(_QWORD *)v50 + 16LL))(v50);
      }
      MsoCF::CIPtr<Jot::IObjectSpaceRevisionCache,Jot::IObjectSpaceRevisionCache>::Release(v75);
      break;
    case 0xBu:
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 112LL))(*((_QWORD *)this + 56)) )
      {
        QueryUnbiasedInterruptTime((PULONGLONG)this + 62);
        v73 = (_Mtx_t)(100LL * (*((_QWORD *)this + 62) - *((_QWORD *)this + 61)) / 1000000);
        v102[0] = &Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Logging::IStructuredTrace'};
        v102[1] = &Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Telemetry::IDataField'};
        v102[2] = L"CSITimeInMSec";
        v102[3] = -1;
        v102[4] = &v73;
        v103 = 4;
        v14 = (_QWORD *)*((_QWORD *)this + 57);
        if ( v14 )
          v15 = MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::MsecsSince(*v14);
        else
          v15 = 0;
        v71 = (Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *)v15;
        v82 = &Jot::Logging::details::StructuredTraceImplementation<unsigned __int64>::`vftable'{for `Mso::Logging::IStructuredTrace'};
        v83 = &Jot::Logging::details::StructuredTraceImplementation<unsigned __int64>::`vftable'{for `Mso::Telemetry::IDataField'};
        v84 = L"TimeInMSec";
        v85 = -1;
        v86 = &v71;
        v87 = 4;
        v80 = &off_1810FB000;
        v81 = "ExecuteQueryChangesSuccess";
        *(_QWORD *)&v65 = &v82;
        *((_QWORD *)&v65 + 1) = v102;
        v88 = &Mso::Logging::CompositeStructuredTrace::`vftable';
        v89 = (void **)&v65;
        v90 = &v66;
        Jot::Logging::details::SendStructuredTraceTag(19169757, 50, &v80, &v88, v61, v62, v63, v64);
      }
      v70 = 0;
      v16 = (Csi **)((char *)this + 472);
      if ( *((_QWORD *)this + 59) )
      {
        Csi::CreateKnowledge((Csi *)&v70, v13);
        (*(void (__fastcall **)(__int64, Csi *))(*(_QWORD *)v70 + 80LL))(v70, *v16);
      }
      else
      {
        Csi::CreateKnowledge((Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *)((char *)this + 472), v13);
      }
      v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 96LL))(*((_QWORD *)this + 56));
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 120LL))(v17);
      v104 = *(_OWORD *)v18;
      LODWORD(v105) = *(_DWORD *)(v18 + 16);
      if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 144LL))(*((_QWORD *)this + 56)) )
      {
        v19 = *v16;
        v20 = *(void (__fastcall **)(Csi *, __int64))(*(_QWORD *)*v16 + 80LL);
        v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 144LL))(*((_QWORD *)this + 56));
        v20(v19, v21);
        v69 = 0;
        if ( Csi::FGetCellKnowledge(*v16, (struct Csi::IKnowledge *)&v69, v22) )
          (*(void (__fastcall **)(__int64, void *))(*(_QWORD *)v69 + 72LL))(v69, &CsiCell::c_snNull);
        if ( v69 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      }
      (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 56) + 152LL))(*((_QWORD *)this + 56), &v65);
      if ( BYTE8(v65) )
      {
        v23 = std::_Optional_construct_base<MsoCF::CIRef<Jot::File::IStandardIoFile>>::operator*(&v65);
        sub_18076396C(*((_QWORD *)this + 49), (char *)this + 400, 0, v23);
      }
      v24 = 0;
      v94 = 0;
      v25 = 0;
      v95 = 0;
      if ( *((_BYTE *)this + 483) )
      {
        v26 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 56);
        v27 = 0;
        v69 = 0;
        if ( v26 )
        {
          (**v26)(v26, &GUID_3e297d19_4e53_492c_a9ee_e135e589136c, &v69);
          v27 = v69;
        }
        v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 96LL))(v27);
        v24 = v28;
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
        v94 = v24;
        v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 104LL))(v69);
        v25 = v29;
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
        v95 = v25;
        if ( v69 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
      }
      v30 = (void (__fastcall ***)(_QWORD, GUID *, Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch **))*((_QWORD *)this + 58);
      v72 = 0;
      if ( v30 )
        (**v30)(v30, &GUID_f71641a1_fc0d_75a5_be7f_ab9b995046fe, &v72);
      v74 = (struct Jot::IObjectSpaceRevisionCache *)&v69;
      v69 = 0;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
      v69 = v25;
      v97 = &v76;
      v76 = 0;
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
      v76 = v24;
      v66 = *((_BYTE *)this + 483);
      v98 = &v77;
      v77 = 0;
      MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(&v77, *((_QWORD *)this + 58));
      v67 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 160LL))(*((_QWORD *)this + 56));
      v68 = *((_BYTE *)this + 482);
      v99 = v96;
      v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 136LL))(*((_QWORD *)this + 56));
      v32 = (struct _Mtx_internal_imp_t *)v31;
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
      v73 = v32;
      RefFromNonNull = MsoCF::MakeRefFromNonNullPtr<IMsoUrl>(v96, &v73);
      v100 = &v79;
      v34 = MsoCF::CIPtr<OneNoteJscomApiImpl::IPageContentInstance,OneNoteJscomApiImpl::IPageContentInstance>::CIPtr<OneNoteJscomApiImpl::IPageContentInstance,OneNoteJscomApiImpl::IPageContentInstance>(
              &v79,
              (char *)this + 472);
      v101 = &v78;
      v78 = 0;
      v35 = v70;
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 8LL))(v70);
      v78 = v35;
      v80 = (char ***)&v75;
      v75 = 0;
      v36 = *(void (__fastcall ****)(_QWORD))(*((_QWORD *)this + 49) + 16LL);
      if ( v36 )
        (**v36)(*(_QWORD *)(*((_QWORD *)this + 49) + 16LL));
      v75 = v36;
      *(_QWORD *)&v65 = &v71;
      v71 = 0;
      v37 = v72;
      if ( v72 )
        (*(void (__fastcall **)(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *))(*(_QWORD *)v72 + 8LL))(v72);
      v71 = v37;
      v38 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 49) + 136LL))(*((_QWORD *)this + 49));
      Jot::CreateRevisionCacheWithCellStorageData(
        (unsigned int)&v74,
        v38,
        (unsigned int)&v71,
        (unsigned int)&v75,
        (__int64)&v78,
        v34,
        RefFromNonNull,
        (__int64)&v104,
        v68,
        v67,
        (__int64)&v77,
        v66,
        (__int64)&v76,
        (__int64)&v69);
      if ( v73 )
        (*(void (__fastcall **)(_Mtx_t))(*(_QWORD *)v73 + 16LL))(v73);
      v39 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 104LL))(*((_QWORD *)this + 56));
      v40 = v74;
      if ( v39 )
      {
        v41 = *((_QWORD *)this + 49) + 152LL;
        *(_QWORD *)&v65 = v41;
        v73 = (_Mtx_t)(v41 + 88);
        MsoCF::CMsoCfCriticalSectionObject::lock((MsoCF::CMsoCfCriticalSectionObject *)(v41 + 88));
        *((_QWORD *)&v65 + 1) = v41;
        v42 = **(_QWORD ***)(v41 + 16);
        while ( v42 != *(_QWORD **)(v41 + 16) )
        {
          v43 = (Jot::CObjectSpaceRevisionStoreInCellStorage *)v42[5];
          v42 = (_QWORD *)*v42;
          Jot::CObjectSpaceRevisionStoreInCellStorage::EnsureRootStore(v43, v40);
        }
        _Mtx_unlock(v73);
      }
      Jot::CObjectSpaceStoreInCellStorage::SetObjectSpaceRevisionCache(
        *((Jot::CObjectSpaceStoreInCellStorage **)this + 49),
        v40);
      v44 = *(void (__fastcall **)(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *, __int128 *))(*(_QWORD *)this + 96LL);
      v65 = 0;
      __ExceptionPtrCreate(&v65);
      v44(this, &v65);
      MsoCF::CIPtr<Jot::IObjectSpaceRevisionCache,Jot::IObjectSpaceRevisionCache>::Release(v40);
      if ( v72 )
        (*(void (__fastcall **)(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *))(*(_QWORD *)v72 + 16LL))(v72);
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      if ( v70 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v70 + 16LL))(v70);
      break;
    case 0xCu:
      QueryUnbiasedInterruptTime((PULONGLONG)this + 62);
      v73 = (_Mtx_t)(100LL * (*((_QWORD *)this + 62) - *((_QWORD *)this + 61)) / 1000000);
      v82 = &Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Logging::IStructuredTrace'};
      v83 = &Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Telemetry::IDataField'};
      v84 = L"CSITimeInMSec";
      v85 = -1;
      v86 = &v73;
      v87 = 4;
      v3 = (_QWORD *)*((_QWORD *)this + 57);
      if ( v3 )
        v4 = MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::MsecsSince(*v3);
      else
        v4 = 0;
      v72 = (Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *)v4;
      v88 = &Jot::Logging::details::StructuredTraceImplementation<unsigned __int64>::`vftable'{for `Mso::Logging::IStructuredTrace'};
      v89 = &Jot::Logging::details::StructuredTraceImplementation<unsigned __int64>::`vftable'{for `Mso::Telemetry::IDataField'};
      v90 = (char *)L"TimeInMSec";
      v91 = -1;
      v92 = &v72;
      v93 = 4;
      v80 = &off_1810FB000;
      v81 = "ExecuteQueryChangesFailure";
      *(_QWORD *)&v65 = &v88;
      *((_QWORD *)&v65 + 1) = &v82;
      *(_QWORD *)&v104 = &Mso::Logging::CompositeStructuredTrace::`vftable';
      *((_QWORD *)&v104 + 1) = &v65;
      v105 = &v66;
      Jot::Logging::details::SendStructuredTraceTag(19169760, 50, &v80, &v104, v61, v62, v63, v64);
      (*(void (__fastcall **)(_QWORD, __int128 *))(**((_QWORD **)this + 56) + 152LL))(*((_QWORD *)this + 56), &v65);
      if ( BYTE8(v65) )
      {
        v5 = std::_Optional_construct_base<MsoCF::CIRef<Jot::File::IStandardIoFile>>::operator*(&v65);
        sub_18076396C(*((_QWORD *)this + 49), (char *)this + 400, 0, v5);
      }
      v6 = *((_QWORD *)this + 49);
      v7 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 80LL))(*((_QWORD *)this + 56));
      v65 = 0;
      __ExceptionPtrCopy(&v65, v7);
      v8 = sub_18055FB9C(&v65, v6);
      v9 = *(_QWORD **)this;
      if ( v8 )
      {
        v10 = Jot::ErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed::ErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed(
                v102,
                19169762);
        v11 = (__int128 *)std::make_exception_ptr<Jot::ErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed>(&v65, v10);
      }
      else
      {
        v12 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 80LL))(*((_QWORD *)this + 56));
        v65 = 0;
        __ExceptionPtrCopy(&v65, v12);
        v11 = &v65;
      }
      ((void (__fastcall *)(Jot::CObjectSpaceStoreOnCellStorage_GetRevisionBatch *, __int128 *))v9[12])(this, v11);
      break;
  }
}

```

## disassembly

```asm
0x1806b4110  mov     rax, rsp
0x1806b4113  mov     [rax+10h], rbx
0x1806b4117  mov     [rax+18h], rsi
0x1806b411b  mov     [rax+20h], rdi
0x1806b411f  push    rbp
0x1806b4120  push    r12
0x1806b4122  push    r13
0x1806b4124  push    r14
0x1806b4126  push    r15
0x1806b4128  lea     rbp, [rax-128h]
0x1806b412f  sub     rsp, 200h
0x1806b4136  mov     rax, cs:__security_cookie
0x1806b413d  xor     rax, rsp
0x1806b4140  mov     [rbp+120h+var_30], rax
0x1806b4147  mov     r12, rcx
0x1806b414a  mov     [rbp+120h+var_188], rcx
0x1806b414e  mov     ecx, [rdx]
0x1806b4150  sub     ecx, 0Ah
0x1806b4153  jz      loc_1806B4A48
0x1806b4159  sub     ecx, 1
0x1806b415c  jz      loc_1806B4393
0x1806b4162  cmp     ecx, 1
0x1806b4165  jnz     loc_1806B4CED
0x1806b416b  lea     rbx, [r12+1F0h]
0x1806b4173  mov     rcx, rbx; UnbiasedTime
0x1806b4176  call    cs:__imp_QueryUnbiasedInterruptTime
0x1806b417c  mov     rax, [rbx]
0x1806b417f  sub     rax, [r12+1E8h]
0x1806b4187  imul    rcx, rax, 64h ; 'd'
0x1806b418b  mov     rax, 431BDE82D7B634DBh
0x1806b4195  imul    rcx
0x1806b4198  sar     rdx, 12h
0x1806b419c  mov     rax, rdx
0x1806b419f  shr     rax, 3Fh
0x1806b41a3  add     rdx, rax
0x1806b41a6  mov     [rbp+120h+var_178], rdx
0x1806b41aa  lea     rax, ??_7?$StructuredTraceImplementation@_J@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1806b41b1  mov     [rbp+120h+var_130], rax
0x1806b41b5  lea     rax, ??_7?$StructuredTraceImplementation@_J@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Telemetry::IDataField'}
0x1806b41bc  mov     [rbp+120h+var_128], rax
0x1806b41c0  lea     rax, aCsitimeinmsec; "CSITimeInMSec"
0x1806b41c7  mov     [rbp+120h+var_120], rax
0x1806b41cb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1806b41cf  mov     [rbp+120h+var_118], rbx
0x1806b41d3  lea     rax, [rbp+120h+var_178]
0x1806b41d7  mov     [rbp+120h+var_110], rax
0x1806b41db  lea     edi, [rbx+5]
0x1806b41de  mov     [rbp+120h+var_108], di
0x1806b41e2  mov     rcx, [r12+1C8h]
0x1806b41ea  xor     r13d, r13d
0x1806b41ed  test    rcx, rcx
0x1806b41f0  jz      short loc_1806B41FC
0x1806b41f2  mov     rcx, [rcx]
0x1806b41f5  call    ?MsecsSince@?$CTickCountBase@UGetTickCountAPIs@Jot@@@MsoCF@@SA_KV12@@Z; MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::MsecsSince(MsoCF::CTickCountBase<Jot::GetTickCountAPIs>)
0x1806b41fa  jmp     short loc_1806B41FF
0x1806b41fc  mov     rax, r13
0x1806b41ff  mov     [rbp+120h+var_180], rax
0x1806b4203  lea     rax, ??_7?$StructuredTraceImplementation@_K@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<unsigned __int64>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1806b420a  mov     [rbp+120h+var_100], rax
0x1806b420e  lea     rax, ??_7?$StructuredTraceImplementation@_K@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<unsigned __int64>::`vftable'{for `Mso::Telemetry::IDataField'}
0x1806b4215  mov     [rbp+120h+var_F8], rax
0x1806b4219  lea     rax, aTimeinmsec; "TimeInMSec"
0x1806b4220  mov     [rbp+120h+var_F0], rax
0x1806b4224  mov     [rbp+120h+var_E8], rbx
0x1806b4228  lea     rax, [rbp+120h+var_180]
0x1806b422c  mov     [rbp+120h+var_E0], rax
0x1806b4230  mov     [rbp+120h+var_D8], di
0x1806b4234  lea     rax, off_1810FB000
0x1806b423b  mov     [rbp+120h+var_140], rax
0x1806b423f  lea     rax, aExecutequerych_0; "ExecuteQueryChangesFailure"
0x1806b4246  mov     [rbp+120h+var_138], rax
0x1806b424a  lea     rax, [rbp+120h+var_100]
0x1806b424e  mov     qword ptr [rsp+220h+var_1B8+8], rax
0x1806b4253  lea     rax, [rbp+120h+var_130]
0x1806b4257  mov     [rsp+220h+var_1A8], rax
0x1806b425c  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x1806b4263  mov     qword ptr [rbp+120h+var_48], rax
0x1806b426a  lea     rax, [rsp+220h+var_1B8+8]
0x1806b426f  mov     qword ptr [rbp+120h+var_48+8], rax
0x1806b4276  lea     rax, [rbp+120h+var_1A0]
0x1806b427a  mov     [rbp+120h+var_38], rax
0x1806b4281  lea     r9, [rbp+120h+var_48]
0x1806b4288  lea     r8, [rbp+120h+var_140]
0x1806b428c  mov     edx, 32h ; '2'
0x1806b4291  mov     ecx, 12481E0h
0x1806b4296  call    ?SendStructuredTraceTag@details@Logging@Jot@@YAXKW4Severity@2Mso@@AEBUEventName@Telemetry@5@AEBUIStructuredTrace@25@@Z; Jot::Logging::details::SendStructuredTraceTag(ulong,Mso::Logging::Severity,Mso::Telemetry::EventName const &,Mso::Logging::IStructuredTrace const &)
0x1806b429b  mov     rcx, [r12+1C0h]
0x1806b42a3  mov     rax, [rcx]
0x1806b42a6  lea     rdx, [rsp+220h+var_1B8+8]
0x1806b42ab  mov     rax, [rax+98h]
0x1806b42b2  call    cs:__guard_dispatch_icall_fptr
0x1806b42b8  cmp     byte ptr [rsp+220h+var_1A8], r13b
0x1806b42bd  jz      short loc_1806B42E4
0x1806b42bf  lea     rcx, [rsp+220h+var_1B8+8]
0x1806b42c4  call    ??D?$_Optional_construct_base@V?$CIRef@UIStandardIoFile@File@Jot@@@MsoCF@@@std@@QEHAA$$QEAV?$CIRef@UIStandardIoFile@File@Jot@@@MsoCF@@XZ; std::_Optional_construct_base<MsoCF::CIRef<Jot::File::IStandardIoFile>>::operator*(void)
0x1806b42c9  lea     rdx, [r12+190h]
0x1806b42d1  mov     r9, rax
0x1806b42d4  xor     r8d, r8d
0x1806b42d7  mov     rcx, [r12+188h]
0x1806b42df  call    sub_18076396C
0x1806b42e4  mov     rbx, [r12+188h]
0x1806b42ec  mov     rcx, [r12+1C0h]
0x1806b42f4  mov     rax, [rcx]
0x1806b42f7  mov     rax, [rax+50h]
0x1806b42fb  call    cs:__guard_dispatch_icall_fptr
0x1806b4301  xorps   xmm0, xmm0
0x1806b4304  movdqu  [rsp+220h+var_1B8+8], xmm0
0x1806b430a  mov     rdx, rax
0x1806b430d  lea     rcx, [rsp+220h+var_1B8+8]
0x1806b4312  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1806b4318  mov     rdx, rbx
0x1806b431b  lea     rcx, [rsp+220h+var_1B8+8]
0x1806b4320  call    sub_18055FB9C
0x1806b4325  mov     rbx, [r12]
0x1806b4329  test    al, al
0x1806b432b  jz      short loc_1806B4360
0x1806b432d  mov     edx, 12481E2h
0x1806b4332  lea     rcx, [rbp+120h+var_90]
0x1806b4339  call    ??0ErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed@Jot@@QEAA@VExceptionTag@1@@Z; Jot::ErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed::ErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed(Jot::ExceptionTag)
0x1806b433e  mov     rdx, rax
0x1806b4341  lea     rcx, [rsp+220h+var_1B8+8]
0x1806b4346  call    ??$make_exception_ptr@UErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed@Jot@@@std@@YA?AVexception_ptr@0@UErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed@Jot@@@Z; std::make_exception_ptr<Jot::ErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed>(Jot::ErrStorageUrl_CobaltUnavailableWithNoFallbackAllowed)
0x1806b434b  mov     rdx, rax
0x1806b434e  mov     rcx, r12
0x1806b4351  mov     rax, [rbx+60h]
0x1806b4355  call    cs:__guard_dispatch_icall_fptr
0x1806b435b  jmp     loc_1806B4CED
0x1806b4360  mov     rcx, [r12+1C0h]
0x1806b4368  mov     rax, [rcx]
0x1806b436b  mov     rax, [rax+50h]
0x1806b436f  call    cs:__guard_dispatch_icall_fptr
0x1806b4375  xorps   xmm0, xmm0
0x1806b4378  movdqu  [rsp+220h+var_1B8+8], xmm0
0x1806b437e  mov     rdx, rax
0x1806b4381  lea     rcx, [rsp+220h+var_1B8+8]
0x1806b4386  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1806b438c  lea     rdx, [rsp+220h+var_1B8+8]
0x1806b4391  jmp     short loc_1806B434E
0x1806b4393  mov     rcx, [r12+1C0h]
0x1806b439b  mov     rax, [rcx]
0x1806b439e  mov     rax, [rax+70h]
0x1806b43a2  call    cs:__guard_dispatch_icall_fptr
0x1806b43a8  xor     r13d, r13d
0x1806b43ab  test    al, al
0x1806b43ad  jz      loc_1806B44E9
0x1806b43b3  lea     rbx, [r12+1F0h]
0x1806b43bb  mov     rcx, rbx; UnbiasedTime
0x1806b43be  call    cs:__imp_QueryUnbiasedInterruptTime
0x1806b43c4  mov     rax, [rbx]
0x1806b43c7  sub     rax, [r12+1E8h]
0x1806b43cf  imul    rcx, rax, 64h ; 'd'
0x1806b43d3  mov     rax, 431BDE82D7B634DBh
0x1806b43dd  imul    rcx
0x1806b43e0  sar     rdx, 12h
0x1806b43e4  mov     rax, rdx
0x1806b43e7  shr     rax, 3Fh
0x1806b43eb  add     rdx, rax
0x1806b43ee  mov     [rbp+120h+var_178], rdx
0x1806b43f2  lea     rax, ??_7?$StructuredTraceImplementation@_J@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1806b43f9  mov     [rbp+120h+var_90], rax
0x1806b4400  lea     rax, ??_7?$StructuredTraceImplementation@_J@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<__int64>::`vftable'{for `Mso::Telemetry::IDataField'}
0x1806b4407  mov     [rbp+120h+var_88], rax
0x1806b440e  lea     rax, aCsitimeinmsec; "CSITimeInMSec"
0x1806b4415  mov     [rbp+120h+var_80], rax
0x1806b441c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1806b4420  mov     [rbp+120h+var_78], rbx
0x1806b4427  lea     rax, [rbp+120h+var_178]
0x1806b442b  mov     [rbp+120h+var_70], rax
0x1806b4432  lea     edi, [rbx+5]
0x1806b4435  mov     [rbp+120h+var_68], di
0x1806b443c  mov     rcx, [r12+1C8h]
0x1806b4444  test    rcx, rcx
0x1806b4447  jz      short loc_1806B4453
0x1806b4449  mov     rcx, [rcx]
0x1806b444c  call    ?MsecsSince@?$CTickCountBase@UGetTickCountAPIs@Jot@@@MsoCF@@SA_KV12@@Z; MsoCF::CTickCountBase<Jot::GetTickCountAPIs>::MsecsSince(MsoCF::CTickCountBase<Jot::GetTickCountAPIs>)
0x1806b4451  jmp     short loc_1806B4456
0x1806b4453  mov     rax, r13
0x1806b4456  mov     [rbp+120h+var_188], rax
0x1806b445a  lea     rax, ??_7?$StructuredTraceImplementation@_K@details@Logging@Jot@@6BIStructuredTrace@2Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<unsigned __int64>::`vftable'{for `Mso::Logging::IStructuredTrace'}
0x1806b4461  mov     [rbp+120h+var_130], rax
0x1806b4465  lea     rax, ??_7?$StructuredTraceImplementation@_K@details@Logging@Jot@@6BIDataField@Telemetry@Mso@@@; const Jot::Logging::details::StructuredTraceImplementation<unsigned __int64>::`vftable'{for `Mso::Telemetry::IDataField'}
0x1806b446c  mov     [rbp+120h+var_128], rax
0x1806b4470  lea     rax, aTimeinmsec; "TimeInMSec"
0x1806b4477  mov     [rbp+120h+var_120], rax
0x1806b447b  mov     [rbp+120h+var_118], rbx
0x1806b447f  lea     rax, [rbp+120h+var_188]
0x1806b4483  mov     [rbp+120h+var_110], rax
0x1806b4487  mov     [rbp+120h+var_108], di
0x1806b448b  lea     rax, off_1810FB000
0x1806b4492  mov     [rbp+120h+var_140], rax
0x1806b4496  lea     rax, aExecutequerych; "ExecuteQueryChangesSuccess"
0x1806b449d  mov     [rbp+120h+var_138], rax
0x1806b44a1  lea     rax, [rbp+120h+var_130]
0x1806b44a5  mov     qword ptr [rsp+220h+var_1B8+8], rax
0x1806b44aa  lea     rax, [rbp+120h+var_90]
0x1806b44b1  mov     [rsp+220h+var_1A8], rax
0x1806b44b6  lea     rax, ??_7CompositeStructuredTrace@Logging@Mso@@6B@; const Mso::Logging::CompositeStructuredTrace::`vftable'
0x1806b44bd  mov     [rbp+120h+var_100], rax
0x1806b44c1  lea     rax, [rsp+220h+var_1B8+8]
0x1806b44c6  mov     [rbp+120h+var_F8], rax
0x1806b44ca  lea     rax, [rbp+120h+var_1A0]
0x1806b44ce  mov     [rbp+120h+var_F0], rax
0x1806b44d2  lea     r9, [rbp+120h+var_100]
0x1806b44d6  lea     r8, [rbp+120h+var_140]
0x1806b44da  mov     edx, 32h ; '2'
0x1806b44df  mov     ecx, 12481DDh
0x1806b44e4  call    ?SendStructuredTraceTag@details@Logging@Jot@@YAXKW4Severity@2Mso@@AEBUEventName@Telemetry@5@AEBUIStructuredTrace@25@@Z; Jot::Logging::details::SendStructuredTraceTag(ulong,Mso::Logging::Severity,Mso::Telemetry::EventName const &,Mso::Logging::IStructuredTrace const &)
0x1806b44e9  mov     [rbp+120h+var_190], r13
0x1806b44ed  lea     rsi, [r12+1D8h]
0x1806b44f5  cmp     [rsi], r13
0x1806b44f8  jz      short loc_1806B451A
0x1806b44fa  lea     rcx, [rbp+120h+var_190]
0x1806b44fe  call    cs:__imp_?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z; Csi::CreateKnowledge(Csi::IKnowledge * *)
0x1806b4504  mov     rcx, [rbp+120h+var_190]
0x1806b4508  mov     rax, [rcx]
0x1806b450b  mov     rdx, [rsi]
0x1806b450e  mov     rax, [rax+50h]
0x1806b4512  call    cs:__guard_dispatch_icall_fptr
0x1806b4518  jmp     short loc_1806B4523
0x1806b451a  mov     rcx, rsi
0x1806b451d  call    cs:__imp_?CreateKnowledge@Csi@@YAXPEAPEAUIKnowledge@1@@Z; Csi::CreateKnowledge(Csi::IKnowledge * *)
0x1806b4523  mov     rcx, [r12+1C0h]
0x1806b452b  mov     rax, [rcx]
0x1806b452e  mov     rax, [rax+60h]
0x1806b4532  call    cs:__guard_dispatch_icall_fptr
0x1806b4538  mov     rdx, rax
0x1806b453b  mov     rcx, [rax]
0x1806b453e  mov     rax, [rcx+78h]
0x1806b4542  mov     rcx, rdx
0x1806b4545  call    cs:__guard_dispatch_icall_fptr
0x1806b454b  movups  xmm0, xmmword ptr [rax]
0x1806b454e  movups  [rbp+120h+var_48], xmm0
0x1806b4555  mov     eax, [rax+10h]
0x1806b4558  mov     dword ptr [rbp+120h+var_38], eax
0x1806b455e  mov     rcx, [r12+1C0h]
0x1806b4566  mov     rax, [rcx]
0x1806b4569  mov     rax, [rax+90h]
0x1806b4570  call    cs:__guard_dispatch_icall_fptr
0x1806b4576  test    rax, rax
0x1806b4579  jz      short loc_1806B45F0
0x1806b457b  mov     rdi, [rsi]
0x1806b457e  mov     rax, [rdi]
0x1806b4581  mov     rbx, [rax+50h]
0x1806b4585  mov     rcx, [r12+1C0h]
0x1806b458d  mov     rdx, [rcx]
0x1806b4590  mov     rax, [rdx+90h]
0x1806b4597  call    cs:__guard_dispatch_icall_fptr
0x1806b459d  mov     rdx, rax
0x1806b45a0  mov     rcx, rdi
0x1806b45a3  mov     rax, rbx
0x1806b45a6  call    cs:__guard_dispatch_icall_fptr
0x1806b45ac  mov     [rbp+120h+var_198], r13
0x1806b45b0  lea     rdx, [rbp+120h+var_198]
0x1806b45b4  mov     rcx, [rsi]
0x1806b45b7  call    cs:__imp_?FGetCellKnowledge@Csi@@YA_NPEAUIKnowledge@1@PEAPEAUICellKnowledge@CsiCell@@@Z; Csi::FGetCellKnowledge(Csi::IKnowledge *,CsiCell::ICellKnowledge * *)
0x1806b45bd  test    al, al
0x1806b45bf  jz      short loc_1806B45DA
0x1806b45c1  mov     rcx, [rbp+120h+var_198]
0x1806b45c5  mov     rax, [rcx]
0x1806b45c8  lea     rdx, ?c_snNull@CsiCell@@3USerialNumber@1@B; CsiCell::SerialNumber const CsiCell::c_snNull
0x1806b45cf  mov     rax, [rax+48h]
0x1806b45d3  call    cs:__guard_dispatch_icall_fptr
0x1806b45d9  nop
0x1806b45da  mov     rcx, [rbp+120h+var_198]
0x1806b45de  test    rcx, rcx
0x1806b45e1  jz      short loc_1806B45F0
0x1806b45e3  mov     rax, [rcx]
0x1806b45e6  mov     rax, [rax+10h]
0x1806b45ea  call    cs:__guard_dispatch_icall_fptr
0x1806b45f0  mov     rcx, [r12+1C0h]
0x1806b45f8  mov     rax, [rcx]
0x1806b45fb  lea     rdx, [rsp+220h+var_1B8+8]
0x1806b4600  mov     rax, [rax+98h]
0x1806b4607  call    cs:__guard_dispatch_icall_fptr
0x1806b460d  cmp     byte ptr [rsp+220h+var_1A8], r13b
0x1806b4612  jz      short loc_1806B4639
0x1806b4614  lea     rcx, [rsp+220h+var_1B8+8]
0x1806b4619  call    ??D?$_Optional_construct_base@V?$CIRef@UIStandardIoFile@File@Jot@@@MsoCF@@@std@@QEHAA$$QEAV?$CIRef@UIStandardIoFile@File@Jot@@@MsoCF@@XZ; std::_Optional_construct_base<MsoCF::CIRef<Jot::File::IStandardIoFile>>::operator*(void)
0x1806b461e  lea     rdx, [r12+190h]
0x1806b4626  mov     r9, rax
0x1806b4629  xor     r8d, r8d
0x1806b462c  mov     rcx, [r12+188h]
0x1806b4634  call    sub_18076396C
0x1806b4639  mov     rdi, r13
0x1806b463c  mov     [rbp+120h+var_D0], r13
0x1806b4640  mov     rbx, r13
0x1806b4643  mov     [rbp+120h+var_C8], rbx
0x1806b4647  cmp     [r12+1E3h], r13b
0x1806b464f  jz      loc_1806B46F3
0x1806b4655  mov     r9, [r12+1C0h]
0x1806b465d  mov     rcx, r13
0x1806b4660  mov     [rbp+120h+var_198], rcx
0x1806b4664  test    r9, r9
0x1806b4667  jz      short loc_1806B4687
0x1806b4669  mov     rax, [r9]
0x1806b466c  lea     r8, [rbp+120h+var_198]
0x1806b4670  lea     rdx, _GUID_3e297d19_4e53_492c_a9ee_e135e589136c
0x1806b4677  mov     rcx, r9
0x1806b467a  mov     rax, [rax]
0x1806b467d  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
