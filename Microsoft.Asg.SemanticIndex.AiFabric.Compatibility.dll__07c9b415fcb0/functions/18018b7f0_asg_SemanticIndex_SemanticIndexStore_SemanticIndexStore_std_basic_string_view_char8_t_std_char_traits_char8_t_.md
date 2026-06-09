# asg::SemanticIndex::SemanticIndexStore::SemanticIndexStore(std::basic_string_view<char8_t,std::char_traits<char8_t>>,std::span<uchar const,-1>,asg::SemanticIndex::SemanticIndexStore::Options,asg::Guid,asg::SemanticRegistry::SemanticContentType,std::function<std::optional<asg::SemanticRegistry::VectorSpaceInfo> (asg::Guid const &)> const &)

- ea: `0x18018b7f0`
- end: `0x18018c87f`
- name: `??0SemanticIndexStore@SemanticIndex@asg@@AEAA@V?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@V?$span@$$CBE$0?0@4@UOptions@012@UGuid@2@W4SemanticContentType@SemanticRegistry@2@AEBV?$function@$$A6A?AV?$optional@VVectorSpaceInfo@SemanticRegistry@asg@@@std@@AEBUGuid@asg@@@Z@4@@Z`
- size: `4239`
- prototype: ``
- caller_count: `1`
- callee_count: `45`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180193b70`

## callees

- `0x180004140`
- `0x180006220`
- `0x180007740`
- `0x180007830`
- `0x180007a00`
- `0x180007ce0`
- `0x180007de0`
- `0x1800085c0`
- `0x180018c00`
- `0x180046a10`
- `0x180078ed0`
- `0x1800864e0`
- `0x180089c30`
- `0x1801793f0`
- `0x18017fa90`
- `0x1801831d0`
- `0x180188600`
- `0x18018b340`
- `0x18018b530`
- `0x18018b7f0`
- `0x18018ccd0`
- `0x18018d5f0`
- `0x18018d750`
- `0x180191a50`
- `0x180192380`
- `0x180193620`
- `0x180193d60`
- `0x18019caf0`
- `0x18019d550`
- `0x1801a1520`
- `0x1801a1990`
- `0x1801a1e60`
- `0x1801a3d10`
- `0x1801a3d90`
- `0x1801c12e0`
- `0x1801c1730`
- `0x1801c1920`
- `0x1801c7040`
- `0x1801d1320`
- `0x1801f7110`
- `0x1801f7190`
- `0x1801f7680`
- `0x1801f97e0`
- `0x180229ef0`
- `0x180242ca0`

## string_xrefs

- `0x18018c7e5`: `The vector space is not compatible with the database structure.`
- `0x18018c814`: `The database is not open.`
- `0x18018c865`: `__cdecl asg::SemanticIndex::SemanticIndexStore::SemanticIndexStore(class std::basic_string_view<char8_t,struct std::char_traits<char8_t> >,class std::span<unsigned char const ,-1>,struct asg::SemanticIndex::SemanticIndexStore::Options,struct asg::Guid,enum asg::SemanticRegistry::SemanticContentType,const class std::function<class std::optional<class asg::SemanticRegistry::VectorSpaceInfo> __cdecl(struct asg::Guid const &)> &)`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
__int64 __fastcall asg::SemanticIndex::SemanticIndexStore::SemanticIndexStore(
        __int64 a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4,
        __int128 *Buf1,
        unsigned int a6,
        __int64 a7)
{
  __int64 v10; // rax
  int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // r8
  unsigned __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // r13
  int v17; // r12d
  __int64 v18; // rcx
  __int64 v19; // rdx
  volatile signed __int32 *v20; // r15
  volatile signed __int32 *v21; // r15
  _OWORD *v22; // rax
  __int128 *v23; // r8
  __int64 v24; // rdx
  signed __int32 v25; // eax
  signed __int32 v26; // ett
  struct asg::Sqlite::DbConnection *v27; // rax
  __int128 v28; // xmm0
  int CurrentTableGroup; // r15d
  const struct asg::SemanticIndex::TableNames *v30; // rbx
  asg::SemanticIndex *v31; // rcx
  const struct asg::SemanticIndex::TableNames *v32; // rbx
  asg::SemanticIndex *v33; // rcx
  const struct asg::SemanticIndex::TableNames *v34; // rax
  asg::SemanticIndex *v35; // rcx
  const struct asg::SemanticIndex::TableNames *v36; // rax
  const struct asg::SemanticIndex::TableNames *v37; // rax
  asg::SemanticIndex *v38; // rcx
  __int64 v39; // rax
  __m128i *v40; // rax
  __m128i v41; // xmm6
  __m128i *v42; // rax
  __m128i v43; // xmm7
  int v44; // ebx
  int v45; // eax
  __int64 v46; // r13
  unsigned int v47; // r12d
  int v48; // ebx
  int v49; // eax
  int v50; // r13d
  __int128 *v51; // rcx
  __int64 v52; // rax
  volatile signed __int32 *v53; // rbx
  __int128 *v54; // rcx
  __int64 v55; // rax
  volatile signed __int32 *v56; // rbx
  unsigned int v57; // ebx
  __int64 GlobalCache; // rax
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rcx
  _WORD *v62; // r10
  unsigned int LatestSchemaVersion; // r8d
  __int16 *v64; // r10
  _QWORD *v65; // rax
  volatile signed __int32 *v66; // rbx
  volatile signed __int32 *v67; // rbx
  volatile signed __int32 *v68; // rbx
  __int64 v70; // rax
  __int64 v71; // [rsp+20h] [rbp-7F8h]
  char v72[8]; // [rsp+60h] [rbp-7B8h] BYREF
  __int128 *v73; // [rsp+68h] [rbp-7B0h]
  __int128 v74; // [rsp+70h] [rbp-7A8h] BYREF
  __int128 v75; // [rsp+80h] [rbp-798h]
  __int128 v76; // [rsp+A0h] [rbp-778h] BYREF
  _BYTE v77[48]; // [rsp+B0h] [rbp-768h] BYREF
  __int128 v78; // [rsp+E0h] [rbp-738h]
  __int64 v79; // [rsp+F0h] [rbp-728h]
  void *v80; // [rsp+F8h] [rbp-720h]
  __int128 v81; // [rsp+100h] [rbp-718h] BYREF
  __m128i si128; // [rsp+110h] [rbp-708h]
  __int64 v83; // [rsp+120h] [rbp-6F8h]
  const asg::Sqlite::DbException *v84; // [rsp+128h] [rbp-6F0h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+130h] [rbp-6E8h] BYREF
  _BYTE v86[24]; // [rsp+148h] [rbp-6D0h] BYREF
  _BYTE v87[24]; // [rsp+160h] [rbp-6B8h] BYREF
  _BYTE v88[24]; // [rsp+178h] [rbp-6A0h] BYREF
  _BYTE v89[24]; // [rsp+190h] [rbp-688h] BYREF
  _BYTE v90[24]; // [rsp+1A8h] [rbp-670h] BYREF
  _DWORD v91[2]; // [rsp+1C0h] [rbp-658h] BYREF
  _BYTE v92[32]; // [rsp+1C8h] [rbp-650h] BYREF
  _BYTE v93[32]; // [rsp+1E8h] [rbp-630h] BYREF
  _BYTE v94[32]; // [rsp+208h] [rbp-610h] BYREF
  _BYTE v95[32]; // [rsp+228h] [rbp-5F0h] BYREF
  _BYTE v96[40]; // [rsp+248h] [rbp-5D0h] BYREF
  _DWORD v97[2]; // [rsp+270h] [rbp-5A8h] BYREF
  _BYTE v98[32]; // [rsp+278h] [rbp-5A0h] BYREF
  _BYTE v99[32]; // [rsp+298h] [rbp-580h] BYREF
  _BYTE v100[32]; // [rsp+2B8h] [rbp-560h] BYREF
  _BYTE v101[32]; // [rsp+2D8h] [rbp-540h] BYREF
  _BYTE v102[40]; // [rsp+2F8h] [rbp-520h] BYREF
  _BYTE v103[64]; // [rsp+320h] [rbp-4F8h] BYREF
  _BYTE v104[64]; // [rsp+360h] [rbp-4B8h] BYREF
  char v105[168]; // [rsp+3A0h] [rbp-478h] BYREF
  __int64 v106; // [rsp+448h] [rbp-3D0h]
  asg::Sqlite::DbTransaction *v107[2]; // [rsp+450h] [rbp-3C8h] BYREF
  __int128 v108; // [rsp+468h] [rbp-3B0h] BYREF
  __int128 v109; // [rsp+478h] [rbp-3A0h] BYREF
  __int128 v110; // [rsp+488h] [rbp-390h] BYREF
  __int128 v111; // [rsp+498h] [rbp-380h]
  __int128 v112; // [rsp+4A8h] [rbp-370h]
  __m128i v113; // [rsp+4B8h] [rbp-360h]
  void (__fastcall **v114)(_QWORD, _QWORD); // [rsp+4D0h] [rbp-348h] BYREF
  __int128 v115; // [rsp+4D8h] [rbp-340h]
  __int128 v116; // [rsp+4E8h] [rbp-330h]
  int v117; // [rsp+4F8h] [rbp-320h]
  __int128 v118; // [rsp+500h] [rbp-318h]
  __m128i v119; // [rsp+510h] [rbp-308h]
  int v120; // [rsp+520h] [rbp-2F8h]
  __int128 v121; // [rsp+528h] [rbp-2F0h]
  __m128i v122; // [rsp+538h] [rbp-2E0h]
  unsigned __int8 v123[72]; // [rsp+548h] [rbp-2D0h] BYREF
  _OWORD v124[4]; // [rsp+590h] [rbp-288h] BYREF
  _QWORD v125[13]; // [rsp+5D0h] [rbp-248h] BYREF
  int v126; // [rsp+638h] [rbp-1E0h]
  char v127; // [rsp+688h] [rbp-190h]
  _BYTE v128[80]; // [rsp+690h] [rbp-188h] BYREF
  _BYTE v129[80]; // [rsp+6E0h] [rbp-138h] BYREF
  __int128 Buf2; // [rsp+730h] [rbp-E8h] BYREF
  __m128i v131; // [rsp+740h] [rbp-D8h]
  _BYTE v132[6]; // [rsp+75Ah] [rbp-BEh] BYREF
  _OWORD v133[2]; // [rsp+760h] [rbp-B8h] BYREF
  __m128i v134; // [rsp+780h] [rbp-98h] BYREF
  volatile signed __int32 *v135; // [rsp+798h] [rbp-80h]

  *(_QWORD *)&v76 = a2;
  v83 = a1;
  v106 = a4;
  v73 = Buf1;
  v79 = a7;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)a1 = &asg::SemanticIndex::SemanticIndexStore::`vftable';
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = a6;
  asg::SemanticIndex::SemanticIndexStore::Options::Options(
    (asg::SemanticIndex::SemanticIndexStore::Options *)(a1 + 48),
    (const struct asg::SemanticIndex::SemanticIndexStore::Options *)a4);
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_OWORD *)(a1 + 232) = 0;
  *(_QWORD *)(a1 + 248) = 0;
  *(_QWORD *)(a1 + 256) = 7;
  *(_WORD *)(a1 + 232) = 0;
  *(_OWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 280) = 0;
  *(_QWORD *)(a1 + 288) = 7;
  *(_WORD *)(a1 + 264) = 0;
  *(_OWORD *)(a1 + 296) = 0;
  *(_QWORD *)(a1 + 312) = 0;
  *(_QWORD *)(a1 + 320) = 7;
  *(_WORD *)(a1 + 296) = 0;
  *(_OWORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 352) = 7;
  *(_WORD *)(a1 + 328) = 0;
  *(_OWORD *)(a1 + 360) = 0;
  *(_QWORD *)(a1 + 376) = 0;
  *(_QWORD *)(a1 + 384) = 7;
  *(_WORD *)(a1 + 360) = 0;
  *(_OWORD *)(a1 + 392) = 0;
  *(_QWORD *)(a1 + 408) = 0;
  *(_QWORD *)(a1 + 416) = 7;
  *(_WORD *)(a1 + 392) = 0;
  *(_OWORD *)(a1 + 424) = 0;
  *(_QWORD *)(a1 + 440) = 0;
  *(_QWORD *)(a1 + 448) = 7;
  *(_WORD *)(a1 + 424) = 0;
  *(_OWORD *)(a1 + 456) = 0;
  *(_QWORD *)(a1 + 472) = 0;
  *(_QWORD *)(a1 + 480) = 7;
  *(_WORD *)(a1 + 456) = 0;
  *(_OWORD *)(a1 + 488) = 0;
  *(_QWORD *)(a1 + 504) = 0;
  *(_QWORD *)(a1 + 512) = 7;
  *(_WORD *)(a1 + 488) = 0;
  *(_OWORD *)(a1 + 520) = 0;
  *(_QWORD *)(a1 + 536) = 0;
  *(_QWORD *)(a1 + 544) = 7;
  *(_WORD *)(a1 + 520) = 0;
  *(_WORD *)(a1 + 552) = 1;
  *(_QWORD *)(a1 + 560) = 0;
  *(_QWORD *)(a1 + 568) = 0;
  *(_QWORD *)(a1 + 576) = 0;
  *(_QWORD *)(a1 + 584) = 0;
  *(_DWORD *)(a1 + 592) = 1000;
  if ( *((_QWORD *)a3 + 1) )
  {
    v10 = *((_QWORD *)a3 + 1);
    if ( v10 != 32 && v10 != 8 )
    {
      std::invalid_argument::invalid_argument((std::invalid_argument *)pExceptionObject, "invalid encryption key");
      throw (std::invalid_argument *)pExceptionObject;
    }
  }
  if ( a6 > 1 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)v86, "Invalid content type");
    throw (std::invalid_argument *)v86;
  }
  v11 = *(_DWORD *)(a4 + 4);
  if ( v11 && (unsigned int)(v11 - 1) > 1 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)v87, "Invalid CheckpointOnClose option");
    throw (std::invalid_argument *)v87;
  }
  if ( *(_DWORD *)a4 && (unsigned int)(*(_DWORD *)a4 - 1) > 1 )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)v88, "Invalid index quantization preference");
    throw (std::invalid_argument *)v88;
  }
  Buf2 = `asg::EmptyGuid'::`2'::empty;
  if ( !memcmp(Buf1, &Buf2, 0x10u) )
  {
    std::invalid_argument::invalid_argument((std::invalid_argument *)v89, "currentVectorSpaceId");
    throw (std::invalid_argument *)v89;
  }
  v12 = *(_QWORD *)(a7 + 56);
  if ( !v12 )
    std::_Xbad_function_call();
  (*(void (__fastcall **)(__int64, _QWORD *, __int128 *))(*(_QWORD *)v12 + 16LL))(v12, v125, Buf1);
  if ( !v127 )
  {
    std::string::string(&v74, "Can't get info for currentVectorSpaceId", v13);
    asg::SemanticRegistry::InvalidRegistryException::InvalidRegistryException(v90, &v74);
    throw (asg::SemanticRegistry::InvalidRegistryException *)v90;
  }
  v14 = v125[11];
  *(_QWORD *)(a1 + 208) = v125[12];
  *(_DWORD *)(a1 + 216) = v126;
  v111 = 0;
  v112 = 0;
  v113.m128i_i8[8] = 0;
  *(_QWORD *)v77 = ___7___Func_impl_no_alloc_V_lambda_1___8___0SemanticIndexStore_SemanticIndex_asg__AEAA_V__basic_string_view__QU__char_traits__Q_std___std__V__span___CBE_0_0_6_UOptions_234_UGuid_4_W4SemanticContentType_SemanticRegistry_4_AEBV__function___A6A_AV__optional_VVectorSpaceInfo_SemanticRegistry_asg___std__AEBUGuid_asg___Z_6__Z_XAEAVApplicationDb_34_AEAUDbConnection_Sqlite_4__N_std__6B_;
  *((_QWORD *)&v78 + 1) = v77;
  v80 = (void *)(a4 + 24);
  v15 = a4 + 24;
  if ( *(_QWORD *)(a4 + 48) > 0xFu )
    v15 = *(_QWORD *)(a4 + 24);
  try
  {
    *(_QWORD *)&Buf2 = v15;
    *((_QWORD *)&Buf2 + 1) = *(_QWORD *)(a4 + 40);
    v81 = *Buf1;
    v74 = *a3;
    v76 = *(_OWORD *)v76;
    v16 = asg::SemanticIndex::ApplicationDb::CreateOrOpen(
            (unsigned int)v133,
            *(_DWORD *)(a4 + 4),
            (unsigned int)&v76,
            (unsigned int)&v74,
            (__int64)&v81,
            v14,
            a6,
            *(_DWORD *)a4,
            a7,
            *(_QWORD *)(a4 + 16),
            (__int64)&Buf2,
            (__int64)v77);
    v17 = *(_DWORD *)(v16 + 64);
    v18 = *(_QWORD *)(v16 + 48);
    v19 = *(_QWORD *)(v16 + 56);
    *(_QWORD *)(v16 + 48) = 0;
    *(_QWORD *)(v16 + 56) = 0;
    *(_QWORD *)(a1 + 24) = v18;
    v20 = *(volatile signed __int32 **)(a1 + 32);
    *(_QWORD *)(a1 + 32) = v19;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v111 = *(_OWORD *)v16;
    v112 = *(_OWORD *)(v16 + 16);
    v113 = *(__m128i *)(v16 + 32);
    v21 = v135;
    if ( v135 )
    {
      if ( _InterlockedExchangeAdd(v135 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
      }
    }
  }
  catch ( const asg::Sqlite::DbException *v84 )
  {
    v70 = asg::SemanticIndex::AsSemanticIndexException(v77, v84);
    std::throw_with_nested<asg::SemanticIndex::SemanticIndexException>(v70);
  }
  if ( v17 != 3 && v17 )
  {
    asg::SemanticIndex::SemanticIndexException::SemanticIndexException(
      v103,
      "The vector space is not compatible with the database structure.",
      4);
    throw (asg::SemanticIndex::SemanticIndexException *)v103;
  }
  if ( !*(_QWORD *)(a1 + 24) )
  {
    asg::SemanticIndex::SemanticIndexException::SemanticIndexException(v104, "The database is not open.", 2);
    throw (asg::SemanticIndex::SemanticIndexException *)v104;
  }
  if ( *(_BYTE *)(a4 + 120) )
  {
    *(_OWORD *)v77 = *(_OWORD *)(a4 + 56);
    *(_OWORD *)&v77[16] = *(_OWORD *)(a4 + 72);
    *(_OWORD *)&v77[32] = *(_OWORD *)(a4 + 88);
    v78 = *(_OWORD *)(a4 + 104);
    v22 = v77;
  }
  else
  {
    v22 = (_OWORD *)asg::SemanticIndex::DiskAnn::IndexConfigBuilder::Default(v77);
  }
  v124[0] = *v22;
  v124[1] = v22[1];
  v124[2] = v22[2];
  v124[3] = v22[3];
  v110 = 0;
  v23 = *(__int128 **)(a1 + 24);
  v76 = 0;
  v24 = *((_QWORD *)v23 + 1);
  if ( !v24 || (v25 = *(_DWORD *)(v24 + 8)) == 0 )
LABEL_95:
    std::_Throw_bad_weak_ptr();
  while ( 1 )
  {
    v26 = v25;
    v25 = _InterlockedCompareExchange((volatile signed __int32 *)(v24 + 8), v25 + 1, v25);
    if ( v26 == v25 )
      break;
    if ( !v25 )
      goto LABEL_95;
  }
  v76 = *v23;
  asg::SemanticIndex::ReadWriteConnectionHandle::ReadWriteConnectionHandle(&v110, &v76);
  v27 = asg::SemanticIndex::ReadWriteConnectionHandle::Get((asg::SemanticIndex::ReadWriteConnectionHandle *)&v110);
  *(_OWORD *)v107 = 0;
  asg::Sqlite::DbConnection::BeginTransaction(v27, v107, 0);
  v28 = *v73;
  v111 = *v73;
  if ( !v17 )
  {
    v133[0] = v28;
    v133[1] = v112;
    v134 = v113;
    asg::SemanticIndex::MigrateToVectorSpace(v107[0], v133, v124);
  }
  CurrentTableGroup = asg::SemanticIndex::ApplicationDb::GetCurrentTableGroup(v107[0]);
  asg::SemanticIndex::DbDiskAnnEmbeddingStoreBase::TryReadConfig(v128, v107[0], 0);
  asg::SemanticIndex::DbDiskAnnEmbeddingStoreBase::TryReadConfig(v129, v107[0], 1);
  v97[0] = 0;
  v97[1] = CurrentTableGroup != 0;
  v30 = asg::SemanticIndex::BlueTableNames((asg::SemanticIndex *)(CurrentTableGroup != 0));
  std::basic_string<char16_t>::basic_string<char16_t>(v98, v30);
  std::basic_string<char16_t>::basic_string<char16_t>(v99, (char *)v30 + 32);
  std::basic_string<char16_t>::basic_string<char16_t>(v100, (char *)v30 + 64);
  std::basic_string<char16_t>::basic_string<char16_t>(v101, (char *)v30 + 96);
  std::basic_string<char16_t>::basic_string<char16_t>(v102, (char *)v30 + 128);
  v91[0] = 1;
  v91[1] = CurrentTableGroup != 1;
  v32 = asg::SemanticIndex::GreenTableNames(v31);
  std::basic_string<char16_t>::basic_string<char16_t>(v92, v32);
  std::basic_string<char16_t>::basic_string<char16_t>(v93, (char *)v32 + 32);
  std::basic_string<char16_t>::basic_string<char16_t>(v94, (char *)v32 + 64);
  std::basic_string<char16_t>::basic_string<char16_t>(v95, (char *)v32 + 96);
  std::basic_string<char16_t>::basic_string<char16_t>(v96, (char *)v32 + 128);
  if ( CurrentTableGroup )
  {
    v37 = asg::SemanticIndex::GreenTableNames(v33);
    asg::SemanticIndex::TableNames::operator=(a1 + 232, v37);
    v36 = asg::SemanticIndex::BlueTableNames(v38);
  }
  else
  {
    v34 = asg::SemanticIndex::BlueTableNames(v33);
    asg::SemanticIndex::TableNames::operator=(a1 + 232, v34);
    v36 = asg::SemanticIndex::GreenTableNames(v35);
  }
  asg::SemanticIndex::TableNames::operator=(a1 + 392, v36);
  if ( v17 == 3 && !v128[64] && !v129[64] )
  {
    if ( CurrentTableGroup )
    {
      *(_QWORD *)&v74 = 0xD000000DBLL;
      *((_QWORD *)&v74 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\libSemanticSearch\\SemanticIndexStore.cpp";
      *(_QWORD *)&v75 = "__cdecl asg::SemanticIndex::SemanticIndexStore::SemanticIndexStore(class std::basic_string_view<"
                        "char8_t,struct std::char_traits<char8_t> >,class std::span<unsigned char const ,-1>,struct asg::"
                        "SemanticIndex::SemanticIndexStore::Options,struct asg::Guid,enum asg::SemanticRegistry::Semantic"
                        "ContentType,const class std::function<class std::optional<class asg::SemanticRegistry::VectorSpa"
                        "ceInfo> __cdecl(struct asg::Guid const &)> &)";
      asg::details::AsgAssertFail(&v74);
    }
    asg::SemanticIndex::DbDiskAnnEmbeddingStoreBase::ResetConfig(v107[0], v124, 0);
    v39 = asg::SemanticIndex::DiskAnn::IndexConfigBuilder::Default(v77);
    asg::SemanticIndex::DbDiskAnnEmbeddingStoreBase::ResetConfig(v107[0], v39, 1);
  }
  v40 = (__m128i *)asg::SemanticIndex::ApplicationDb::ReadEmbeddingInfo(&v74, v107[0], 0);
  v133[0] = *v40;
  v41 = v40[1];
  v134 = v40[2];
  v42 = (__m128i *)asg::SemanticIndex::ApplicationDb::ReadEmbeddingInfo(&v74, v107[0], 1);
  v133[0] = *v42;
  v43 = v42[1];
  v134 = v42[2];
  v109 = 0;
  v44 = (int)v107[0];
  v45 = asg::SemanticIndex::GraphTableVersionInfo::GraphTableVersionInfo(
          (asg::SemanticIndex::GraphTableVersionInfo *)&v114,
          (const struct asg::SemanticIndex::GraphTableVersionInfo *)v97);
  v46 = v79;
  v47 = _mm_cvtsi128_si32(_mm_srli_si128(v41, 8));
  asg::SemanticIndex::DbDiskAnnEmbeddingStore::Open((unsigned int)&v109, v45, v44, v47, v79);
  v108 = 0;
  v48 = (int)v107[0];
  v49 = asg::SemanticIndex::GraphTableVersionInfo::GraphTableVersionInfo(
          (asg::SemanticIndex::GraphTableVersionInfo *)v105,
          (const struct asg::SemanticIndex::GraphTableVersionInfo *)v91);
  v71 = v46;
  v50 = _mm_cvtsi128_si32(_mm_srli_si128(v43, 8));
  asg::SemanticIndex::DbDiskAnnEmbeddingStore::Open((unsigned int)&v108, v49, v48, v50, v71);
  v51 = &v109;
  if ( CurrentTableGroup )
    v51 = &v108;
  v52 = *((_QWORD *)v51 + 1);
  if ( v52 )
    _InterlockedIncrement((volatile signed __int32 *)(v52 + 8));
  *(_QWORD *)(a1 + 176) = *(_QWORD *)v51;
  v53 = *(volatile signed __int32 **)(a1 + 184);
  *(_QWORD *)(a1 + 184) = *((_QWORD *)v51 + 1);
  if ( v53 )
  {
    if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
      if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
    }
  }
  v54 = &v108;
  if ( CurrentTableGroup )
    v54 = &v109;
  v55 = *((_QWORD *)v54 + 1);
  if ( v55 )
    _InterlockedIncrement((volatile signed __int32 *)(v55 + 8));
  *(_QWORD *)(a1 + 192) = *(_QWORD *)v54;
  v56 = *(volatile signed __int32 **)(a1 + 200);
  *(_QWORD *)(a1 + 200) = *((_QWORD *)v54 + 1);
  if ( v56 )
  {
    if ( _InterlockedExchangeAdd(v56 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
      if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
    }
  }
  v57 = v50;
  if ( !CurrentTableGroup )
    v57 = v47;
  GlobalCache = asg::SemanticIndex::MakeGlobalCache(&v74, v57);
  std::atomic<std::shared_ptr<asg::SemanticIndex::DiskAnn::GlobalNodeCache>>::operator=(a1 + 560, GlobalCache);
  if ( !CurrentTableGroup )
    v47 = v50;
  v59 = asg::SemanticIndex::MakeGlobalCache(&v74, v47);
  std::atomic<std::shared_ptr<asg::SemanticIndex::DiskAnn::GlobalNodeCache>>::operator=(a1 + 576, v59);
  v60 = *(_QWORD *)(a1 + 192);
  if ( v60 )
  {
    v74 = *(_OWORD *)(v60 + 200);
    v61 = *(_QWORD *)(v79 + 56);
    if ( !v61 )
      std::_Xbad_function_call();
    (*(void (__fastcall **)(__int64, void (__fastcall ***)(_QWORD, _QWORD), __int128 *))(*(_QWORD *)v61 + 16LL))(
      v61,
      &v114,
      &v74);
    if ( v123[64] )
    {
      *(_QWORD *)(a1 + 220) = *((_QWORD *)&v121 + 1);
      *(_DWORD *)(a1 + 228) = v122.m128i_i32[0];
      (*v114)(&v114, 0);
    }
  }
  asg::Sqlite::DbTransaction::Commit(v107[0]);
  asg::SemanticIndex::ApplicationDb::PerformCheckpoint(*(asg::SemanticIndex::ApplicationDb **)(a1 + 24), 0);
  v74 = 0;
  v75 = 0;
  std::basic_string<char16_t>::_Construct<1,char16_t const *>(&v74);
  LODWORD(v114) = 2;
  v115 = v74;
  v116 = v75;
  LOWORD(v74) = 0;
  *(_QWORD *)&v75 = 0;
  *((_QWORD *)&v75 + 1) = 7;
  v62 = v132;
  do
  {
    *--v62 = v14 % 0xA + 48;
    v14 /= 0xAu;
  }
  while ( v14 );
  std::basic_string<char16_t>::basic_string<char16_t>(&v81, v62, v132, v72);
  v117 = 0;
  v118 = v81;
  v119 = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v81) = 0;
  LatestSchemaVersion = asg::SemanticIndex::ApplicationDb::GetLatestSchemaVersion();
  v64 = &v134.m128i_i16[5];
  do
  {
    *--v64 = LatestSchemaVersion % 0xA + 48;
    LatestSchemaVersion /= 0xAu;
  }
  while ( LatestSchemaVersion );
  std::basic_string<char16_t>::basic_string<char16_t>(&Buf2, v64, (char *)&v134.m128i_u64[1] + 2, v72);
  v120 = 3;
  v121 = Buf2;
  v122 = v131;
  v131 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Buf2) = 0;
  *(_DWORD *)v77 = 0;
  *(_OWORD *)&v77[8] = 0;
  v65 = operator new(0x38u);
  *v65 = v65;
  v65[1] = v65;
  *(_QWORD *)&v77[8] = v65;
  memset(&v77[24], 0, 24);
  *(_QWORD *)&v78 = 7;
  *((_QWORD *)&v78 + 1) = 8;
  *(_DWORD *)v77 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::u8string_view const,asg::Sqlite::DbValue>>>>>>::_Assign_grow(
    &v77[24],
    16,
    v65);
  std::_Hash<std::_Umap_traits<enum asg::Telemetry::Property,std::basic_string<char16_t>,std::_Uhash_compare<enum asg::Telemetry::Property,std::hash<enum asg::Telemetry::Property>,std::equal_to<enum asg::Telemetry::Property>>,std::allocator<std::pair<enum asg::Telemetry::Property const,std::basic_string<char16_t>>>,0>>::_Insert_range_unchecked<std::pair<enum asg::Telemetry::Property const,std::basic_string<char16_t>> const *,std::pair<enum asg::Telemetry::Property const,std::basic_string<char16_t>> const *>(
    (__int64)v77,
    (unsigned __int8 *)&v114,
    v123);
  asg::Telemetry::Log(0, v77);
  std::vector<std::pair<unsigned int,unsigned int>>::_Tidy(&v77[24]);
  std::list<std::pair<enum asg::Telemetry::Property const,std::basic_string<char16_t>>>::~list<std::pair<enum asg::Telemetry::Property const,std::basic_string<char16_t>>>(&v77[8]);
  `eh vector destructor iterator'(
    &v114,
    0x28u,
    3u,
    std::pair<enum asg::Telemetry::Property const,std::basic_string<char16_t>>::~pair<enum asg::Telemetry::Property const,std::basic_string<char16_t>>);
  v66 = (volatile signed __int32 *)*((_QWORD *)&v108 + 1);
  if ( *((_QWORD *)&v108 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v108 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
      if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
    }
  }
  v67 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
  if ( *((_QWORD *)&v109 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v109 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
      if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
    }
  }
  std::basic_string<char16_t>::_Tidy_deallocate(v96);
  std::basic_string<char16_t>::_Tidy_deallocate(v95);
  std::basic_string<char16_t>::_Tidy_deallocate(v94);
  std::basic_string<char16_t>::_Tidy_deallocate(v93);
  std::basic_string<char16_t>::_Tidy_deallocate(v92);
  std::basic_string<char16_t>::_Tidy_deallocate(v102);
  std::basic_string<char16_t>::_Tidy_deallocate(v101);
  std::basic_string<char16_t>::_Tidy_deallocate(v100);
  std::basic_string<char16_t>::_Tidy_deallocate(v99);
  std::basic_string<char16_t>::_Tidy_deallocate(v98);
  v68 = (volatile signed __int32 *)v107[1];
  if ( v107[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v107[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v68)(v68);
      if ( _InterlockedExchangeAdd(v68 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v68 + 8LL))(v68);
    }
  }
  asg::SemanticIndex::ReadWriteConnectionHandle::~ReadWriteConnectionHandle((asg::SemanticIndex::ReadWriteConnectionHandle *)&v110);
  if ( v127 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v125[0])(v125, 0);
  std::basic_string<char8_t>::_Tidy_deallocate(v80);
  return a1;
}

```

## disassembly

```asm
0x18018b7f0  mov     rax, rsp
0x18018b7f3  push    rbx
0x18018b7f4  push    rsi
0x18018b7f5  push    rdi
0x18018b7f6  push    r12
0x18018b7f8  push    r13
0x18018b7fa  push    r14
0x18018b7fc  push    r15
0x18018b7fe  sub     rsp, 7E0h
0x18018b805  movaps  xmmword ptr [rax-48h], xmm6
0x18018b809  movaps  xmmword ptr [rax-58h], xmm7
0x18018b80d  mov     rax, cs:__security_cookie
0x18018b814  xor     rax, rsp
0x18018b817  mov     [rsp+818h+var_68], rax
0x18018b81f  mov     rbx, r9
0x18018b822  mov     r12, r8
0x18018b825  mov     qword ptr [rsp+818h+var_778], rdx
0x18018b82d  mov     r14, rcx
0x18018b830  mov     [rsp+818h+var_6F8], rcx
0x18018b838  mov     [rsp+818h+var_3D0], rbx
0x18018b840  mov     r15, [rsp+818h+Buf1]
0x18018b848  mov     [rsp+818h+var_7B0], r15
0x18018b84d  mov     esi, [rsp+818h+arg_28]
0x18018b854  mov     r13, [rsp+818h+arg_30]
0x18018b85c  mov     [rsp+818h+var_728], r13
0x18018b864  xor     edi, edi
0x18018b866  mov     [rcx+8], rdi
0x18018b86a  mov     [rcx+10h], rdi
0x18018b86e  lea     rax, ??_7SemanticIndexStore@SemanticIndex@asg@@6B@; const asg::SemanticIndex::SemanticIndexStore::`vftable'
0x18018b875  mov     [rcx], rax
0x18018b878  mov     [rcx+18h], rdi
0x18018b87c  mov     [rcx+20h], rdi
0x18018b880  mov     [rcx+28h], esi
0x18018b883  add     rcx, 30h ; '0'; this
0x18018b887  mov     rdx, r9; struct asg::SemanticIndex::SemanticIndexStore::Options *
0x18018b88a  call    ??0Options@SemanticIndexStore@SemanticIndex@asg@@QEAA@AEBU0123@@Z; asg::SemanticIndex::SemanticIndexStore::Options::Options(asg::SemanticIndex::SemanticIndexStore::Options const &)
0x18018b88f  nop
0x18018b890  mov     [r14+0B0h], rdi
0x18018b897  mov     [r14+0B8h], rdi
0x18018b89e  mov     [r14+0C0h], rdi
0x18018b8a5  mov     [r14+0C8h], rdi
0x18018b8ac  lea     rax, [r14+0E8h]
0x18018b8b3  xorps   xmm0, xmm0
0x18018b8b6  movups  xmmword ptr [rax], xmm0
0x18018b8b9  mov     [rax+10h], rdi
0x18018b8bd  mov     qword ptr [rax+18h], 7
0x18018b8c5  mov     [rax], di
0x18018b8c8  movups  xmmword ptr [rax+20h], xmm0
0x18018b8cc  mov     [rax+30h], rdi
0x18018b8d0  mov     qword ptr [rax+38h], 7
0x18018b8d8  mov     [rax+20h], di
0x18018b8dc  movups  xmmword ptr [rax+40h], xmm0
0x18018b8e0  mov     [rax+50h], rdi
0x18018b8e4  mov     qword ptr [rax+58h], 7
0x18018b8ec  mov     [rax+40h], di
0x18018b8f0  movups  xmmword ptr [rax+60h], xmm0
0x18018b8f4  mov     [rax+70h], rdi
0x18018b8f8  mov     qword ptr [rax+78h], 7
0x18018b900  mov     [rax+60h], di
0x18018b904  movups  xmmword ptr [rax+80h], xmm0
0x18018b90b  mov     [rax+90h], rdi
0x18018b912  mov     qword ptr [rax+98h], 7
0x18018b91d  mov     [rax+80h], di
0x18018b924  lea     rax, [r14+188h]
0x18018b92b  movups  xmmword ptr [rax], xmm0
0x18018b92e  mov     [rax+10h], rdi
0x18018b932  mov     qword ptr [rax+18h], 7
0x18018b93a  mov     [rax], di
0x18018b93d  movups  xmmword ptr [rax+20h], xmm0
0x18018b941  mov     [rax+30h], rdi
0x18018b945  mov     qword ptr [rax+38h], 7
0x18018b94d  mov     [rax+20h], di
0x18018b951  movups  xmmword ptr [rax+40h], xmm0
0x18018b955  mov     [rax+50h], rdi
0x18018b959  mov     qword ptr [rax+58h], 7
0x18018b961  mov     [rax+40h], di
0x18018b965  movups  xmmword ptr [rax+60h], xmm0
0x18018b969  mov     [rax+70h], rdi
0x18018b96d  mov     qword ptr [rax+78h], 7
0x18018b975  mov     [rax+60h], di
0x18018b979  movups  xmmword ptr [rax+80h], xmm0
0x18018b980  mov     [rax+90h], rdi
0x18018b987  mov     qword ptr [rax+98h], 7
0x18018b992  mov     [rax+80h], di
0x18018b999  mov     word ptr [r14+228h], 1
0x18018b9a3  mov     [r14+230h], rdi
0x18018b9aa  xor     ecx, ecx
0x18018b9ac  mov     [r14+238h], rcx
0x18018b9b3  mov     [r14+240h], rdi
0x18018b9ba  mov     [r14+248h], rcx
0x18018b9c1  mov     dword ptr [r14+250h], 3E8h
0x18018b9cc  cmp     [r12+8], rcx
0x18018b9d1  jz      short loc_18018B9E8
0x18018b9d3  mov     rax, [r12+8]
0x18018b9d8  cmp     rax, 20h ; ' '
0x18018b9dc  jz      short loc_18018B9E8
0x18018b9de  cmp     rax, 8
0x18018b9e2  jnz     loc_18018C6D3
0x18018b9e8  test    esi, esi
0x18018b9ea  jz      short loc_18018B9F5
0x18018b9ec  cmp     esi, 1
0x18018b9ef  jnz     loc_18018C6FC
0x18018b9f5  mov     ecx, [rbx+4]
0x18018b9f8  test    ecx, ecx
0x18018b9fa  jz      short loc_18018BA0A
0x18018b9fc  sub     ecx, 1
0x18018b9ff  jz      short loc_18018BA0A
0x18018ba01  cmp     ecx, 1
0x18018ba04  jnz     loc_18018C725
0x18018ba0a  mov     ecx, [rbx]
0x18018ba0c  test    ecx, ecx
0x18018ba0e  jz      short loc_18018BA1E
0x18018ba10  sub     ecx, 1
0x18018ba13  jz      short loc_18018BA1E
0x18018ba15  cmp     ecx, 1
0x18018ba18  jnz     loc_18018C74E
0x18018ba1e  movups  xmm0, cs:?empty@?1??EmptyGuid@asg@@YA?AUGuid@2@XZ@4U32@B; asg::Guid const `asg::EmptyGuid(void)'::`2'::empty
0x18018ba25  movups  [rsp+818h+Buf2], xmm0
0x18018ba2d  mov     r8d, 10h; Size
0x18018ba33  lea     rdx, [rsp+818h+Buf2]; Buf2
0x18018ba3b  mov     rcx, r15; Buf1
0x18018ba3e  call    memcmp
0x18018ba43  test    eax, eax
0x18018ba45  jz      loc_18018C777
0x18018ba4b  mov     rcx, [r13+38h]
0x18018ba4f  test    rcx, rcx
0x18018ba52  jz      loc_18018C7A0
0x18018ba58  mov     rax, [rcx]
0x18018ba5b  mov     r8, r15
0x18018ba5e  lea     rdx, [rsp+818h+var_248]
0x18018ba66  call    qword ptr [rax+10h]
0x18018ba69  nop
0x18018ba6a  cmp     [rsp+818h+var_190], 0
0x18018ba72  jz      loc_18018C7A6
0x18018ba78  mov     rdi, [rsp+818h+var_1F0]
0x18018ba80  movsd   xmm0, [rsp+818h+var_1E8]
0x18018ba89  movsd   qword ptr [r14+0D0h], xmm0
0x18018ba92  mov     eax, [rsp+818h+var_1E0]
0x18018ba99  mov     [r14+0D8h], eax
0x18018baa0  xorps   xmm0, xmm0
0x18018baa3  movups  [rsp+818h+var_380], xmm0
0x18018baab  movups  [rsp+818h+var_370], xmm0
0x18018bab3  mov     [rsp+818h+var_358], 0
0x18018babb  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?8???0SemanticIndexStore@SemanticIndex@asg@@AEAA@V?$basic_string_view@_QU?$char_traits@_Q@std@@@std@@V?$span@$$CBE$0?0@6@UOptions@234@UGuid@4@W4SemanticContentType@SemanticRegistry@4@AEBV?$function@$$A6A?AV?$optional@VVectorSpaceInfo@SemanticRegistry@asg@@@std@@AEBUGuid@asg@@@Z@6@@Z@XAEAVApplicationDb@34@AEAUDbConnection@Sqlite@4@_N@std@@6B@; const std::_Func_impl_no_alloc<`asg::SemanticIndex::SemanticIndexStore::SemanticIndexStore(std::u8string_view,std::span<uchar const,-1>,asg::SemanticIndex::SemanticIndexStore::Options,asg::Guid,asg::SemanticRegistry::SemanticContentType,std::function<std::optional<asg::SemanticRegistry::VectorSpaceInfo> (asg::Guid const &)> const &)'::`9'::_lambda_1_,void,asg::SemanticIndex::ApplicationDb &,asg::Sqlite::DbConnection &,bool>::`vftable'
0x18018bac2  mov     qword ptr [rsp+818h+var_768], rax
0x18018baca  lea     rax, [rsp+818h+var_768]
0x18018bad2  mov     [rsp+818h+var_730], rax
0x18018bada  lea     rcx, [rbx+18h]
0x18018bade  mov     [rsp+818h+var_720], rcx
0x18018bae6  mov     rax, rcx
0x18018bae9  cmp     qword ptr [rcx+18h], 0Fh
0x18018baee  jbe     short loc_18018BAF3
0x18018baf0  mov     rax, [rcx]
0x18018baf3  mov     qword ptr [rsp+818h+Buf2], rax
0x18018bafb  mov     rax, [rcx+10h]
0x18018baff  mov     qword ptr [rsp+818h+Buf2+8], rax
0x18018bb07  movups  xmm0, xmmword ptr [r15]
0x18018bb0b  movaps  [rsp+818h+var_718], xmm0
0x18018bb13  movups  xmm1, xmmword ptr [r12]
0x18018bb18  movaps  [rsp+818h+var_7A8], xmm1
0x18018bb1d  mov     rax, qword ptr [rsp+818h+var_778]
0x18018bb25  movups  xmm0, xmmword ptr [rax]
0x18018bb28  movaps  [rsp+818h+var_778], xmm0
0x18018bb30  lea     rax, [rsp+818h+var_768]
0x18018bb38  mov     [rsp+818h+var_7C0], rax
0x18018bb3d  lea     rax, [rsp+818h+Buf2]
0x18018bb45  mov     [rsp+818h+var_7C8], rax
0x18018bb4a  mov     rax, [rbx+10h]
0x18018bb4e  mov     [rsp+818h+var_7D0], rax
0x18018bb53  mov     [rsp+818h+var_7D8], r13
0x18018bb58  mov     eax, [rbx]
0x18018bb5a  mov     [rsp+818h+var_7E0], eax
0x18018bb5e  mov     [rsp+818h+var_7E8], esi
0x18018bb62  mov     [rsp+818h+var_7F0], rdi
0x18018bb67  lea     rax, [rsp+818h+var_718]
0x18018bb6f  mov     [rsp+818h+var_7F8], rax
0x18018bb74  lea     r9, [rsp+818h+var_7A8]
0x18018bb79  lea     r8, [rsp+818h+var_778]
0x18018bb81  mov     edx, [rbx+4]
0x18018bb84  lea     rcx, [rsp+818h+var_B8]
0x18018bb8c  call    ?CreateOrOpen@ApplicationDb@SemanticIndex@asg@@SA?AV?$tuple@W4VectorCompatibilityStatus@SemanticIndex@asg@@V?$shared_ptr@VApplicationDb@SemanticIndex@asg@@@std@@UEmbeddingInfo@SemanticRegistry@3@@std@@W4CheckpointOnCloseOption@23@V?$basic_string_view@_QU?$char_traits@_Q@std@@@5@V?$span@$$CBE$0?0@5@UGuid@3@_KW4SemanticContentType@SemanticRegistry@3@W4IndexQuantizationPreference@23@AEBV?$function@$$A6A?AV?$optional@VVectorSpaceInfo@SemanticRegistry@asg@@@std@@AEBUGuid@asg@@@Z@5@41V?$function@$$A6AXAEAVApplicationDb@SemanticIndex@asg@@AEAUDbConnection@Sqlite@3@_N@Z@5@@Z; asg::SemanticIndex::ApplicationDb::CreateOrOpen(asg::SemanticIndex::CheckpointOnCloseOption,std::u8string_view,std::span<uchar const,-1>,asg::Guid,unsigned __int64,asg::SemanticRegistry::SemanticContentType,asg::SemanticIndex::IndexQuantizationPreference,std::function<std::optional<asg::SemanticRegistry::VectorSpaceInfo> (asg::Guid const &)> const &,unsigned __int64,std::u8string_view,std::function<void (asg::SemanticIndex::ApplicationDb &,asg::Sqlite::DbConnection &,bool)>)
0x18018bb91  mov     r13, rax
0x18018bb94  mov     r12d, [rax+40h]
0x18018bb98  mov     rcx, [rax+30h]
0x18018bb9c  mov     rdx, [rax+38h]
0x18018bba0  xor     eax, eax
0x18018bba2  mov     [r13+30h], rax
0x18018bba6  mov     [r13+38h], rax
0x18018bbaa  mov     [r14+18h], rcx
0x18018bbae  mov     r15, [r14+20h]
0x18018bbb2  mov     [r14+20h], rdx
0x18018bbb6  mov     esi, 0FFFFFFFFh
0x18018bbbb  test    r15, r15
0x18018bbbe  jz      short loc_18018BBEB
0x18018bbc0  mov     eax, esi
0x18018bbc2  lock xadd [r15+8], eax
0x18018bbc8  cmp     eax, 1
0x18018bbcb  jnz     short loc_18018BBEB
0x18018bbcd  mov     rax, [r15]
0x18018bbd0  mov     rcx, r15
0x18018bbd3  call    qword ptr [rax]
0x18018bbd5  mov     eax, esi
0x18018bbd7  lock xadd [r15+0Ch], eax
0x18018bbdd  cmp     eax, 1
0x18018bbe0  jnz     short loc_18018BBEB
0x18018bbe2  mov     rax, [r15]
0x18018bbe5  mov     rcx, r15
0x18018bbe8  call    qword ptr [rax+8]
0x18018bbeb  movups  xmm0, xmmword ptr [r13+0]
0x18018bbf0  movups  [rsp+818h+var_380], xmm0
0x18018bbf8  movups  xmm1, xmmword ptr [r13+10h]
0x18018bbfd  movups  [rsp+818h+var_370], xmm1
0x18018bc05  movups  xmm0, xmmword ptr [r13+20h]
0x18018bc0a  movups  xmmword ptr [rsp+4B8h], xmm0
0x18018bc12  mov     r15, [rsp+818h+var_80]
0x18018bc1a  test    r15, r15
0x18018bc1d  jz      short loc_18018BC4B
0x18018bc1f  mov     eax, esi
0x18018bc21  lock xadd [r15+8], eax
0x18018bc27  cmp     eax, 1
0x18018bc2a  jnz     short loc_18018BC4B
0x18018bc2c  mov     rax, [r15]
0x18018bc2f  mov     rcx, r15
0x18018bc32  call    qword ptr [rax]
0x18018bc34  mov     eax, esi
0x18018bc36  lock xadd [r15+0Ch], eax
0x18018bc3c  cmp     eax, 1
0x18018bc3f  jnz     short loc_18018BC4B
0x18018bc41  mov     rax, [r15]
0x18018bc44  mov     rcx, r15
0x18018bc47  call    qword ptr [rax+8]
0x18018bc4a  nop
0x18018bc4b  cmp     r12d, 3
0x18018bc4f  jz      short loc_18018BC5A
0x18018bc51  test    r12d, r12d
0x18018bc54  jnz     loc_18018C7DF
0x18018bc5a  cmp     qword ptr [r14+18h], 0
0x18018bc5f  jz      loc_18018C80E
0x18018bc65  cmp     byte ptr [rbx+78h], 0
0x18018bc69  jz      short loc_18018BCA5
0x18018bc6b  movups  xmm0, xmmword ptr [rbx+38h]
0x18018bc6f  movups  [rsp+818h+var_768], xmm0
0x18018bc77  movups  xmm1, xmmword ptr [rbx+48h]
0x18018bc7b  movups  [rsp+818h+var_758], xmm1
0x18018bc83  movups  xmm0, xmmword ptr [rbx+58h]
0x18018bc87  movups  [rsp+818h+var_748], xmm0
0x18018bc8f  movups  xmm1, xmmword ptr [rbx+68h]
0x18018bc93  movups  xmmword ptr [rsp+0E0h], xmm1
0x18018bc9b  lea     rax, [rsp+818h+var_768]
0x18018bca3  jmp     short loc_18018BCB2
0x18018bca5  lea     rcx, [rsp+818h+var_768]
0x18018bcad  call    ?Default@IndexConfigBuilder@DiskAnn@SemanticIndex@asg@@SA?AUIndexConfig@234@XZ; asg::SemanticIndex::DiskAnn::IndexConfigBuilder::Default(void)
0x18018bcb2  movups  xmm0, xmmword ptr [rax]
0x18018bcb5  movaps  [rsp+818h+var_288], xmm0
0x18018bcbd  movups  xmm1, xmmword ptr [rax+10h]
0x18018bcc1  movaps  [rsp+818h+var_278], xmm1
0x18018bcc9  movups  xmm0, xmmword ptr [rax+20h]
0x18018bccd  movaps  [rsp+818h+var_268], xmm0
0x18018bcd5  movups  xmm1, xmmword ptr [rax+30h]
0x18018bcd9  movaps  [rsp+818h+var_258], xmm1
0x18018bce1  xorps   xmm0, xmm0
0x18018bce4  movups  [rsp+818h+var_390], xmm0
0x18018bcec  mov     r8, [r14+18h]
0x18018bcf0  movdqu  [rsp+818h+var_778], xmm0
0x18018bcf9  mov     rdx, [r8+8]
0x18018bcfd  test    rdx, rdx
0x18018bd00  jz      loc_18018C83D
0x18018bd06  mov     eax, [rdx+8]
0x18018bd09  test    eax, eax
0x18018bd0b  jz      loc_18018C83D
0x18018bd11  lea     ecx, [rax+1]
0x18018bd14  lock cmpxchg [rdx+8], ecx
0x18018bd19  jz      short loc_18018BD25
0x18018bd1b  test    eax, eax
0x18018bd1d  jz      loc_18018C83D
0x18018bd23  jmp     short loc_18018BD11
0x18018bd25  mov     rax, [r8]
0x18018bd28  mov     qword ptr [rsp+818h+var_778], rax
0x18018bd30  mov     rax, [r8+8]
0x18018bd34  mov     qword ptr [rsp+818h+var_778+8], rax
0x18018bd3c  lea     rdx, [rsp+818h+var_778]
0x18018bd44  lea     rcx, [rsp+818h+var_390]
0x18018bd4c  call    ??0ReadWriteConnectionHandle@SemanticIndex@asg@@QEAA@V?$shared_ptr@VApplicationDb@SemanticIndex@asg@@@std@@@Z; asg::SemanticIndex::ReadWriteConnectionHandle::ReadWriteConnectionHandle(std::shared_ptr<asg::SemanticIndex::ApplicationDb>)
0x18018bd51  nop
0x18018bd52  lea     rcx, [rsp+818h+var_390]; this
0x18018bd5a  call    ?Get@ReadWriteConnectionHandle@SemanticIndex@asg@@QEBAAEAUDbConnection@Sqlite@3@XZ; asg::SemanticIndex::ReadWriteConnectionHandle::Get(void)
0x18018bd5f  xorps   xmm0, xmm0
0x18018bd62  movups  xmmword ptr [rsp+818h+var_3C8], xmm0
0x18018bd6a  xor     r8d, r8d
0x18018bd6d  lea     rdx, [rsp+818h+var_3C8]
0x18018bd75  mov     rcx, rax
0x18018bd78  call    ?BeginTransaction@DbConnection@Sqlite@asg@@QEAA?AV?$shared_ptr@VDbTransaction@Sqlite@asg@@@std@@_N@Z; asg::Sqlite::DbConnection::BeginTransaction(bool)
0x18018bd7d  nop
0x18018bd7e  mov     rax, [rsp+818h+var_7B0]
0x18018bd83  movups  xmm0, xmmword ptr [rax]
0x18018bd86  movups  [rsp+818h+var_380], xmm0
0x18018bd8e  test    r12d, r12d
0x18018bd91  jnz     short loc_18018BDD8
0x18018bd93  movaps  [rsp+818h+var_B8], xmm0
0x18018bd9b  movups  xmm0, [rsp+818h+var_370]
  ... truncated ...
```
