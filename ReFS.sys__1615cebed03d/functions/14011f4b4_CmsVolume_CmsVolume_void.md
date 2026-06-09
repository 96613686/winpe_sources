# CmsVolume::~CmsVolume(void)

- ea: `0x14011f4b4`
- end: `0x14011fa39`
- name: `??1CmsVolume@@MEAA@XZ`
- size: `1413`
- prototype: `void __fastcall(CmsVolume *__hidden this)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14011d2b0`

## callees

- `0x140049050`
- `0x14004b980`
- `0x14006ad20`
- `0x140075624`
- `0x140085900`
- `0x1400cf87c`
- `0x1400d31c8`
- `0x1400d3f20`
- `0x14011575c`
- `0x14011d138`
- `0x14011d158`
- `0x14011d178`
- `0x14011d1d8`
- `0x14011f3a0`
- `0x14011f3d0`
- `0x14011f440`
- `0x14011f4b4`
- `0x14011fa40`
- `0x14011fb04`
- `0x14011fb2c`
- `0x14011fb54`
- `0x14011fb7c`
- `0x14011fba8`
- `0x14011fc0c`
- `0x14011fc34`
- `0x14011fc64`
- `0x14011fc8c`

## import_xrefs

- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f90e`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f921`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f94c`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f95f`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f9fd`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011fa10`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f90e`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f921`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f94c`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f95f`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011f9fd`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x14011fa10`
- `ntoskrnl!ExDeleteFastResource` at `0x14011f71f`
- `ntoskrnl!ExDeleteFastResource` at `0x14011f883`
- `ntoskrnl!ExDeleteFastResource` at `0x14011f8f2`
- `ntoskrnl!ExDeleteFastResource` at `0x14011f71f`
- `ntoskrnl!ExDeleteFastResource` at `0x14011f883`
- `ntoskrnl!ExDeleteFastResource` at `0x14011f8f2`

## pseudocode

```c
void __fastcall CmsVolume::~CmsVolume(CmsVolume *this, struct CmsTransactionCore *a2)
{
  bool v2; // zf
  void *v4; // rdi
  void *v5; // rcx
  CmsBlockRefcount *v6; // rcx
  CmsVolumeAnalyzer *v7; // rcx
  void *v8; // rcx
  CmsIntegrityState *v9; // rcx
  CmsSchemaTable *v10; // rcx
  CmsRangeMap *v11; // rcx
  CmsRangeMap *v12; // rcx
  void **v13; // rax
  void *v14; // rcx
  MsAllocator::RangeArrayStrategy::State *v15; // rcx
  MsAllocator::RangeArrayStrategy::State *v16; // rcx
  MsAllocator::RangeArrayStrategy::State *v17; // rcx
  void *v18; // rcx
  void *v19; // rcx
  MsAllocator::RangeArrayStrategy::State *v20; // rcx
  void *v21; // rcx
  MsAllocator::SmrStrategy::State *v22; // rcx
  unsigned int i; // esi
  struct CmsTransactionCore *v24; // rdx
  struct SmsCheckpointState *CheckpointState; // rdi
  CmsContainerRangeMap *v26; // rcx
  CmsContainerRangeMap *v27; // rcx
  CmsContainerRangeMap *v28; // rcx
  CmsContainerRangeMap *v29; // rcx
  char *v30; // rsi
  void *v31; // rcx
  void *v32; // rcx
  CmsRangeMap *v33; // rcx
  CmsRangeMap *v34; // rcx
  CmsRangeMap *v35; // rcx
  CmsRangeMap *v36; // rcx
  CmsRangeMap *v37; // rcx
  CmsRangeMap *v38; // rcx
  void *v39; // rcx
  CmsCachedRuns *v40; // rcx
  char *v41; // rdi
  void *v42; // rcx
  void *v43; // rdi

  v2 = (*((_DWORD *)this + 849) & 0x10000) == 0;
  *(_QWORD *)this = &CmsVolume::`vftable';
  if ( v2 )
  {
    v4 = (void *)*((_QWORD *)this + 283);
    if ( v4 )
    {
      CmsThinProvisioning::~CmsThinProvisioning(*((CmsThinProvisioning **)this + 283));
      operator delete(v4);
      *((_QWORD *)this + 283) = 0;
    }
    v5 = (void *)*((_QWORD *)this + 418);
    if ( v5 )
    {
      operator delete(v5);
      *((_QWORD *)this + 418) = 0;
    }
    v6 = (CmsBlockRefcount *)*((_QWORD *)this + 413);
    if ( v6 )
    {
      CmsBlockRefcount::`scalar deleting destructor'(v6, (unsigned int)a2);
      *((_QWORD *)this + 413) = 0;
    }
    v7 = (CmsVolumeAnalyzer *)*((_QWORD *)this + 411);
    if ( v7 )
    {
      CmsVolumeAnalyzer::`scalar deleting destructor'(v7, (unsigned int)a2);
      *((_QWORD *)this + 411) = 0;
    }
    v8 = (void *)*((_QWORD *)this + 409);
    if ( v8 )
    {
      CmsVolumeContainer::`scalar deleting destructor'(v8, (unsigned int)a2);
      *((_QWORD *)this + 409) = 0;
    }
    v9 = (CmsIntegrityState *)*((_QWORD *)this + 410);
    if ( v9 )
    {
      CmsIntegrityState::`scalar deleting destructor'(v9, (unsigned int)a2);
      *((_QWORD *)this + 410) = 0;
    }
    v10 = (CmsSchemaTable *)*((_QWORD *)this + 423);
    if ( v10 )
    {
      CmsSchemaTable::`scalar deleting destructor'(v10, (unsigned int)a2);
      *((_QWORD *)this + 423) = 0;
    }
    v11 = (CmsRangeMap *)*((_QWORD *)this + 284);
    if ( v11 )
    {
      if ( *((_QWORD *)v11 + 3) )
        CmsRangeMap::DeleteAll(v11, a2);
      v12 = (CmsRangeMap *)*((_QWORD *)this + 284);
      if ( v12 )
        CmsRangeMap::`scalar deleting destructor'(v12, (unsigned int)a2);
      *((_QWORD *)this + 284) = 0;
    }
    v13 = (void **)*((_QWORD *)this + 327);
    if ( v13 )
    {
      if ( *v13 )
      {
        operator delete(*v13);
        **((_QWORD **)this + 327) = 0;
      }
      v14 = *(void **)(*((_QWORD *)this + 327) + 8LL);
      if ( v14 )
      {
        operator delete(v14);
        *(_QWORD *)(*((_QWORD *)this + 327) + 8LL) = 0;
      }
      v15 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 327) + 16LL);
      if ( v15 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v15, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 327) + 16LL) = 0;
      }
      v16 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 327) + 24LL);
      if ( v16 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v16, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 327) + 24LL) = 0;
      }
      v17 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 327) + 32LL);
      if ( v17 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v17, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 327) + 32LL) = 0;
      }
      v18 = *(void **)(*((_QWORD *)this + 327) + 72LL);
      if ( v18 )
      {
        operator delete(v18);
        *(_QWORD *)(*((_QWORD *)this + 327) + 72LL) = 0;
      }
      v19 = *(void **)(*((_QWORD *)this + 327) + 88LL);
      if ( v19 )
      {
        operator delete(v19);
        *(_QWORD *)(*((_QWORD *)this + 327) + 88LL) = 0;
      }
      v20 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 327) + 40LL);
      if ( v20 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v20, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 327) + 40LL) = 0;
      }
      v21 = *(void **)(*((_QWORD *)this + 327) + 56LL);
      if ( v21 )
      {
        operator delete(v21);
        *(_QWORD *)(*((_QWORD *)this + 327) + 56LL) = 0;
      }
      v22 = *(MsAllocator::SmrStrategy::State **)(*((_QWORD *)this + 327) + 64LL);
      if ( v22 )
      {
        MsAllocator::SmrStrategy::State::`scalar deleting destructor'(v22, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 327) + 64LL) = 0;
      }
      operator delete(*((void **)this + 327));
      *((_QWORD *)this + 327) = 0;
    }
    ExDeleteFastResource((char *)this + 1176);
    for ( i = 0; i < 5; ++i )
    {
      CheckpointState = CmsVolume::GetCheckpointState(this, i);
      if ( *(_QWORD *)CheckpointState )
      {
        CmsContainerRangeMap::DeleteAll(*(CmsContainerRangeMap **)CheckpointState, 0);
        if ( *(_QWORD *)CheckpointState )
          CmsContainerRangeMap::`scalar deleting destructor'(
            *(CmsContainerRangeMap **)CheckpointState,
            (unsigned int)v24);
        *(_QWORD *)CheckpointState = 0;
      }
      v26 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 1);
      if ( v26 )
      {
        CmsContainerRangeMap::DeleteAll(v26, 0);
        v27 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 1);
        if ( v27 )
          CmsContainerRangeMap::`scalar deleting destructor'(v27, (unsigned int)v24);
        *((_QWORD *)CheckpointState + 1) = 0;
      }
      v28 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 2);
      if ( v28 )
      {
        CmsContainerRangeMap::DeleteAll(v28, 0);
        v29 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 2);
        if ( v29 )
          CmsContainerRangeMap::`scalar deleting destructor'(v29, (unsigned int)v24);
        *((_QWORD *)CheckpointState + 2) = 0;
      }
    }
    v30 = (char *)this + 1664;
    v31 = (void *)*((_QWORD *)this + 208);
    *((_QWORD *)this + 208) = 0;
    if ( v31 )
      operator delete(v31);
    v32 = (void *)*((_QWORD *)this + 267);
    if ( v32 )
      operator delete(v32);
    if ( *((_QWORD *)this + 67) )
      MspCleanupIoBatchLookaside(this);
    v33 = (CmsRangeMap *)*((_QWORD *)this + 485);
    if ( v33 )
    {
      CmsRangeMap::DeleteAll(v33, v24);
      v34 = (CmsRangeMap *)*((_QWORD *)this + 485);
      if ( v34 )
        CmsRangeMap::`scalar deleting destructor'(v34, (unsigned int)v24);
    }
    v35 = (CmsRangeMap *)*((_QWORD *)this + 486);
    if ( v35 )
    {
      CmsRangeMap::DeleteAll(v35, v24);
      v36 = (CmsRangeMap *)*((_QWORD *)this + 486);
      if ( v36 )
        CmsRangeMap::`scalar deleting destructor'(v36, (unsigned int)v24);
      *((_QWORD *)this + 486) = 0;
    }
    v37 = (CmsRangeMap *)*((_QWORD *)this + 489);
    if ( v37 )
    {
      CmsRangeMap::DeleteAll(v37, v24);
      v38 = (CmsRangeMap *)*((_QWORD *)this + 489);
      if ( v38 )
        CmsRangeMap::`scalar deleting destructor'(v38, (unsigned int)v24);
    }
    v39 = (void *)*((_QWORD *)this + 491);
    if ( v39 )
      operator delete(v39);
    v40 = (CmsCachedRuns *)*((_QWORD *)this + 351);
    if ( v40 )
    {
      CmsCachedRuns::`scalar deleting destructor'(v40, (unsigned int)v24);
      *((_QWORD *)this + 351) = 0;
    }
    v41 = (char *)*((_QWORD *)this + 425);
    if ( v41 )
    {
      ExDeleteFastResource(v41 + 24);
      operator delete(v41);
      *((_QWORD *)this + 425) = 0;
    }
    v42 = (void *)*((_QWORD *)this + 428);
    if ( v42 != qword_14026E168 )
    {
      operator delete(v42);
      *((_QWORD *)this + 428) = 0;
    }
    v43 = (void *)*((_QWORD *)this + 402);
    if ( v43 )
    {
      CmsAllocationZones::~CmsAllocationZones(*((CmsAllocationZones **)this + 402));
      operator delete(v43);
    }
    *((_QWORD *)this + 408) = 0;
    *((_QWORD *)this + 406) = 0;
    *((_QWORD *)this + 407) = 0;
    ExDeleteFastResource((char *)this + 3432);
  }
  else
  {
    v30 = (char *)this + 1664;
  }
  ExCleanupAutoExpandPushLock((char *)this + 3944);
  ExCleanupAutoExpandPushLock((char *)this + 3856);
  utl::unique_ptr<CmsHmac,utl::default_delete<CmsHmac>>::~unique_ptr<CmsHmac,utl::default_delete<CmsHmac>>((char *)this + 3608);
  SmsChecksumObjects::~SmsChecksumObjects((CmsVolume *)((char *)this + 3536));
  ExCleanupAutoExpandPushLock((char *)this + 3368);
  ExCleanupAutoExpandPushLock((char *)this + 3352);
  `vector destructor iterator'(
    (char *)this + 3224,
    8u,
    3u,
    utl::unique_ptr<CmsAllocator,utl::default_delete<CmsAllocator>>::~unique_ptr<CmsAllocator,utl::default_delete<CmsAllocator>>);
  CmsVolume::SmsTrim::~SmsTrim((CmsVolume *)((char *)this + 2152));
  utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit((char *)this + 2104);
  `vector destructor iterator'(
    (char *)this + 1992,
    0x18u,
    3u,
    utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::~vector<enum utl::byte,utl::allocator<enum utl::byte>>);
  __1__unique_ptr_V__CmsChecksumBase_V__CmsSimpleChecksum__MP6AKPEBX_KK_Z1_Crc32C_ClMulIntrinsic__YAK01K_Z__U__PARITY_ENCODER_VFAST_FINITE_FIELD__K____U__default_delete_V__CmsChecksumBase_V__CmsSimpleChecksum__MP6AKPEBX_KK_Z1_Crc32C_ClMulIntrinsic__YAK01K_Z__U__PARITY_ENCODER_VFAST_FINITE_FIELD__K_____utl___utl__QEAA_XZ(v30);
  `vector destructor iterator'(
    (char *)this + 1280,
    0xB0u,
    2u,
    (void (*)(void *))SmsCheckpointContext::~SmsCheckpointContext);
  utl::unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>::~unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>((char *)this + 1160);
  utl::unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>::~unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>((char *)this + 1152);
  ExCleanupAutoExpandPushLock((char *)this + 432);
  ExCleanupAutoExpandPushLock((char *)this + 328);
  CmsVolume::_unnamed_type_ReservedPools_::__unnamed_type_ReservedPools_((CmsVolume *)((char *)this + 96));
  *(_QWORD *)this = &CmsReferenced::`vftable';
}

```

## disassembly

```asm
0x14011f4b4  push    rbx
0x14011f4b6  push    rbp
0x14011f4b7  push    rsi
0x14011f4b8  push    rdi
0x14011f4b9  sub     rsp, 28h
0x14011f4bd  test    dword ptr [rcx+0D44h], 10000h
0x14011f4c7  lea     rax, ??_7CmsVolume@@6B@; const CmsVolume::`vftable'
0x14011f4ce  mov     [rcx], rax
0x14011f4d1  mov     rbx, rcx
0x14011f4d4  jnz     loc_14011F900
0x14011f4da  mov     rdi, [rcx+8D8h]
0x14011f4e1  xor     ebp, ebp
0x14011f4e3  test    rdi, rdi
0x14011f4e6  jz      short loc_14011F4FF
0x14011f4e8  mov     rcx, rdi; this
0x14011f4eb  call    ??1CmsThinProvisioning@@QEAA@XZ; CmsThinProvisioning::~CmsThinProvisioning(void)
0x14011f4f0  mov     rcx, rdi; void *
0x14011f4f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f4f8  mov     [rbx+8D8h], rbp
0x14011f4ff  mov     rcx, [rbx+0D10h]; void *
0x14011f506  test    rcx, rcx
0x14011f509  jz      short loc_14011F517
0x14011f50b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f510  mov     [rbx+0D10h], rbp
0x14011f517  mov     rcx, [rbx+0CE8h]; this
0x14011f51e  test    rcx, rcx
0x14011f521  jz      short loc_14011F52F
0x14011f523  call    ??_GCmsBlockRefcount@@QEAAPEAXI@Z; CmsBlockRefcount::`scalar deleting destructor'(uint)
0x14011f528  mov     [rbx+0CE8h], rbp
0x14011f52f  mov     rcx, [rbx+0CD8h]; this
0x14011f536  test    rcx, rcx
0x14011f539  jz      short loc_14011F547
0x14011f53b  call    ??_GCmsVolumeAnalyzer@@QEAAPEAXI@Z; CmsVolumeAnalyzer::`scalar deleting destructor'(uint)
0x14011f540  mov     [rbx+0CD8h], rbp
0x14011f547  mov     rcx, [rbx+0CC8h]; P
0x14011f54e  test    rcx, rcx
0x14011f551  jz      short loc_14011F55F
0x14011f553  call    ??_GCmsVolumeContainer@@QEAAPEAXI@Z; CmsVolumeContainer::`scalar deleting destructor'(uint)
0x14011f558  mov     [rbx+0CC8h], rbp
0x14011f55f  mov     rcx, [rbx+0CD0h]; this
0x14011f566  test    rcx, rcx
0x14011f569  jz      short loc_14011F577
0x14011f56b  call    ??_GCmsIntegrityState@@QEAAPEAXI@Z; CmsIntegrityState::`scalar deleting destructor'(uint)
0x14011f570  mov     [rbx+0CD0h], rbp
0x14011f577  mov     rcx, [rbx+0D38h]; this
0x14011f57e  test    rcx, rcx
0x14011f581  jz      short loc_14011F58F
0x14011f583  call    ??_GCmsSchemaTable@@QEAAPEAXI@Z; CmsSchemaTable::`scalar deleting destructor'(uint)
0x14011f588  mov     [rbx+0D38h], rbp
0x14011f58f  mov     rcx, [rbx+8E0h]; this
0x14011f596  test    rcx, rcx
0x14011f599  jz      short loc_14011F5BE
0x14011f59b  cmp     [rcx+18h], rbp
0x14011f59f  jz      short loc_14011F5A6
0x14011f5a1  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14011f5a6  mov     rcx, [rbx+8E0h]; this
0x14011f5ad  test    rcx, rcx
0x14011f5b0  jz      short loc_14011F5B7
0x14011f5b2  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14011f5b7  mov     [rbx+8E0h], rbp
0x14011f5be  mov     rax, [rbx+0A38h]
0x14011f5c5  test    rax, rax
0x14011f5c8  jz      loc_14011F718
0x14011f5ce  mov     rcx, [rax]; void *
0x14011f5d1  test    rcx, rcx
0x14011f5d4  jz      short loc_14011F5E5
0x14011f5d6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f5db  mov     rax, [rbx+0A38h]
0x14011f5e2  mov     [rax], rbp
0x14011f5e5  mov     rax, [rbx+0A38h]
0x14011f5ec  mov     rcx, [rax+8]; void *
0x14011f5f0  test    rcx, rcx
0x14011f5f3  jz      short loc_14011F605
0x14011f5f5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f5fa  mov     rax, [rbx+0A38h]
0x14011f601  mov     [rax+8], rbp
0x14011f605  mov     rax, [rbx+0A38h]
0x14011f60c  mov     rcx, [rax+10h]; this
0x14011f610  test    rcx, rcx
0x14011f613  jz      short loc_14011F625
0x14011f615  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14011f61a  mov     rax, [rbx+0A38h]
0x14011f621  mov     [rax+10h], rbp
0x14011f625  mov     rax, [rbx+0A38h]
0x14011f62c  mov     rcx, [rax+18h]; this
0x14011f630  test    rcx, rcx
0x14011f633  jz      short loc_14011F645
0x14011f635  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14011f63a  mov     rax, [rbx+0A38h]
0x14011f641  mov     [rax+18h], rbp
0x14011f645  mov     rax, [rbx+0A38h]
0x14011f64c  mov     rcx, [rax+20h]; this
0x14011f650  test    rcx, rcx
0x14011f653  jz      short loc_14011F665
0x14011f655  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14011f65a  mov     rax, [rbx+0A38h]
0x14011f661  mov     [rax+20h], rbp
0x14011f665  mov     rax, [rbx+0A38h]
0x14011f66c  mov     rcx, [rax+48h]; void *
0x14011f670  test    rcx, rcx
0x14011f673  jz      short loc_14011F685
0x14011f675  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f67a  mov     rax, [rbx+0A38h]
0x14011f681  mov     [rax+48h], rbp
0x14011f685  mov     rax, [rbx+0A38h]
0x14011f68c  mov     rcx, [rax+58h]; void *
0x14011f690  test    rcx, rcx
0x14011f693  jz      short loc_14011F6A5
0x14011f695  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f69a  mov     rax, [rbx+0A38h]
0x14011f6a1  mov     [rax+58h], rbp
0x14011f6a5  mov     rax, [rbx+0A38h]
0x14011f6ac  mov     rcx, [rax+28h]; this
0x14011f6b0  test    rcx, rcx
0x14011f6b3  jz      short loc_14011F6C5
0x14011f6b5  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14011f6ba  mov     rax, [rbx+0A38h]
0x14011f6c1  mov     [rax+28h], rbp
0x14011f6c5  mov     rax, [rbx+0A38h]
0x14011f6cc  mov     rcx, [rax+38h]; void *
0x14011f6d0  test    rcx, rcx
0x14011f6d3  jz      short loc_14011F6E5
0x14011f6d5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f6da  mov     rax, [rbx+0A38h]
0x14011f6e1  mov     [rax+38h], rbp
0x14011f6e5  mov     rax, [rbx+0A38h]
0x14011f6ec  mov     rcx, [rax+40h]; this
0x14011f6f0  test    rcx, rcx
0x14011f6f3  jz      short loc_14011F705
0x14011f6f5  call    ??_GState@SmrStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::SmrStrategy::State::`scalar deleting destructor'(uint)
0x14011f6fa  mov     rax, [rbx+0A38h]
0x14011f701  mov     [rax+40h], rbp
0x14011f705  mov     rcx, [rbx+0A38h]; void *
0x14011f70c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f711  mov     [rbx+0A38h], rbp
0x14011f718  lea     rcx, [rbx+498h]
0x14011f71f  call    cs:__imp_ExDeleteFastResource
0x14011f726  nop     dword ptr [rax+rax+00h]
0x14011f72b  mov     esi, ebp
0x14011f72d  mov     edx, esi; unsigned int
0x14011f72f  mov     rcx, rbx; this
0x14011f732  call    ?GetCheckpointState@CmsVolume@@AEAAPEAUSmsCheckpointState@@K@Z; CmsVolume::GetCheckpointState(ulong)
0x14011f737  mov     rdi, rax
0x14011f73a  mov     rcx, [rax]; this
0x14011f73d  test    rcx, rcx
0x14011f740  jz      short loc_14011F759
0x14011f742  xor     edx, edx; unsigned __int8
0x14011f744  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14011f749  mov     rcx, [rdi]; this
0x14011f74c  test    rcx, rcx
0x14011f74f  jz      short loc_14011F756
0x14011f751  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14011f756  mov     [rdi], rbp
0x14011f759  mov     rcx, [rdi+8]; this
0x14011f75d  test    rcx, rcx
0x14011f760  jz      short loc_14011F77B
0x14011f762  xor     edx, edx; unsigned __int8
0x14011f764  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14011f769  mov     rcx, [rdi+8]; this
0x14011f76d  test    rcx, rcx
0x14011f770  jz      short loc_14011F777
0x14011f772  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14011f777  mov     [rdi+8], rbp
0x14011f77b  mov     rcx, [rdi+10h]; this
0x14011f77f  test    rcx, rcx
0x14011f782  jz      short loc_14011F79D
0x14011f784  xor     edx, edx; unsigned __int8
0x14011f786  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14011f78b  mov     rcx, [rdi+10h]; this
0x14011f78f  test    rcx, rcx
0x14011f792  jz      short loc_14011F799
0x14011f794  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14011f799  mov     [rdi+10h], rbp
0x14011f79d  inc     esi
0x14011f79f  cmp     esi, 5
0x14011f7a2  jb      short loc_14011F72D
0x14011f7a4  lea     rsi, [rbx+680h]
0x14011f7ab  mov     rcx, [rsi]; void *
0x14011f7ae  mov     [rsi], rbp
0x14011f7b1  test    rcx, rcx
0x14011f7b4  jz      short loc_14011F7BB
0x14011f7b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f7bb  mov     rcx, [rbx+858h]; void *
0x14011f7c2  test    rcx, rcx
0x14011f7c5  jz      short loc_14011F7CC
0x14011f7c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f7cc  cmp     [rbx+218h], rbp
0x14011f7d3  jz      short loc_14011F7DD
0x14011f7d5  mov     rcx, rbx; struct CmsVolume *
0x14011f7d8  call    ?MspCleanupIoBatchLookaside@@YAXPEAVCmsVolume@@@Z; MspCleanupIoBatchLookaside(CmsVolume *)
0x14011f7dd  mov     rcx, [rbx+0F28h]; this
0x14011f7e4  test    rcx, rcx
0x14011f7e7  jz      short loc_14011F7FF
0x14011f7e9  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14011f7ee  mov     rcx, [rbx+0F28h]; this
0x14011f7f5  test    rcx, rcx
0x14011f7f8  jz      short loc_14011F7FF
0x14011f7fa  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14011f7ff  mov     rcx, [rbx+0F30h]; this
0x14011f806  test    rcx, rcx
0x14011f809  jz      short loc_14011F828
0x14011f80b  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14011f810  mov     rcx, [rbx+0F30h]; this
0x14011f817  test    rcx, rcx
0x14011f81a  jz      short loc_14011F821
0x14011f81c  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14011f821  mov     [rbx+0F30h], rbp
0x14011f828  mov     rcx, [rbx+0F48h]; this
0x14011f82f  test    rcx, rcx
0x14011f832  jz      short loc_14011F84A
0x14011f834  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14011f839  mov     rcx, [rbx+0F48h]; this
0x14011f840  test    rcx, rcx
0x14011f843  jz      short loc_14011F84A
0x14011f845  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14011f84a  mov     rcx, [rbx+0F58h]; void *
0x14011f851  test    rcx, rcx
0x14011f854  jz      short loc_14011F85B
0x14011f856  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f85b  mov     rcx, [rbx+0AF8h]; this
0x14011f862  test    rcx, rcx
0x14011f865  jz      short loc_14011F873
0x14011f867  call    ??_GCmsCachedRuns@@QEAAPEAXI@Z; CmsCachedRuns::`scalar deleting destructor'(uint)
0x14011f86c  mov     [rbx+0AF8h], rbp
0x14011f873  mov     rdi, [rbx+0D48h]
0x14011f87a  test    rdi, rdi
0x14011f87d  jz      short loc_14011F89E
0x14011f87f  lea     rcx, [rdi+18h]
0x14011f883  call    cs:__imp_ExDeleteFastResource
0x14011f88a  nop     dword ptr [rax+rax+00h]
0x14011f88f  mov     rcx, rdi; void *
0x14011f892  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f897  mov     [rbx+0D48h], rbp
0x14011f89e  mov     rcx, [rbx+0D60h]; void *
0x14011f8a5  cmp     rcx, cs:qword_14026E168
0x14011f8ac  jz      short loc_14011F8BA
0x14011f8ae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f8b3  mov     [rbx+0D60h], rbp
0x14011f8ba  mov     rdi, [rbx+0C90h]
0x14011f8c1  test    rdi, rdi
0x14011f8c4  jz      short loc_14011F8D6
0x14011f8c6  mov     rcx, rdi; this
0x14011f8c9  call    ??1CmsAllocationZones@@QEAA@XZ; CmsAllocationZones::~CmsAllocationZones(void)
0x14011f8ce  mov     rcx, rdi; void *
0x14011f8d1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14011f8d6  lea     rcx, [rbx+0D68h]
0x14011f8dd  mov     [rbx+0CC0h], rbp
0x14011f8e4  mov     [rbx+0CB0h], rbp
0x14011f8eb  mov     [rbx+0CB8h], rbp
0x14011f8f2  call    cs:__imp_ExDeleteFastResource
0x14011f8f9  nop     dword ptr [rax+rax+00h]
0x14011f8fe  jmp     short loc_14011F907
0x14011f900  lea     rsi, [rcx+680h]
0x14011f907  lea     rcx, [rbx+0F68h]
0x14011f90e  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011f915  nop     dword ptr [rax+rax+00h]
0x14011f91a  lea     rcx, [rbx+0F10h]
0x14011f921  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011f928  nop     dword ptr [rax+rax+00h]
0x14011f92d  lea     rcx, [rbx+0E18h]
0x14011f934  call    ??1?$unique_ptr@VCmsHmac@@U?$default_delete@VCmsHmac@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CmsHmac,utl::default_delete<CmsHmac>>::~unique_ptr<CmsHmac,utl::default_delete<CmsHmac>>(void)
0x14011f939  lea     rcx, [rbx+0DD0h]; this
0x14011f940  call    ??1SmsChecksumObjects@@QEAA@XZ; SmsChecksumObjects::~SmsChecksumObjects(void)
0x14011f945  lea     rcx, [rbx+0D28h]
0x14011f94c  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011f953  nop     dword ptr [rax+rax+00h]
0x14011f958  lea     rcx, [rbx+0D18h]
0x14011f95f  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011f966  nop     dword ptr [rax+rax+00h]
0x14011f96b  mov     edi, 3
0x14011f970  lea     rcx, [rbx+0C98h]; void *
0x14011f977  lea     r9, ??1?$unique_ptr@VCmsAllocator@@U?$default_delete@VCmsAllocator@@@utl@@@utl@@QEAA@XZ; void (*)(void *)
0x14011f97e  mov     r8d, edi; unsigned __int64
0x14011f981  lea     edx, [rdi+5]; unsigned __int64
0x14011f984  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14011f989  lea     rcx, [rbx+868h]; this
0x14011f990  call    ??1SmsTrim@CmsVolume@@QEAA@XZ; CmsVolume::SmsTrim::~SmsTrim(void)
0x14011f995  lea     rcx, [rbx+838h]
0x14011f99c  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x14011f9a1  lea     rcx, [rbx+7C8h]; void *
0x14011f9a8  mov     r8d, edi; unsigned __int64
0x14011f9ab  lea     r9, ??1?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@QEAA@XZ; void (*)(void *)
0x14011f9b2  lea     edx, [rdi+15h]; unsigned __int64
0x14011f9b5  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14011f9ba  mov     rcx, rsi; void *
0x14011f9bd  call    ??1?$unique_ptr@V?$CmsChecksumBase@V?$CmsSimpleChecksum@$MP6AKPEBX_KK@Z1?Crc32C_ClMulIntrinsic@@YAK01K@Z@@U?$PARITY_ENCODER@VFAST_FINITE_FIELD@@K@@@@U?$default_delete@V?$CmsChecksumBase@V?$CmsSimpleChecksum@$MP6AKPEBX_KK@Z1?Crc32C_ClMulIntrinsic@@YAK01K@Z@@U?$PARITY_ENCODER@VFAST_FINITE_FIELD@@K@@@@@utl@@@utl@@QEAA@XZ
0x14011f9c2  lea     rcx, [rbx+500h]; void *
0x14011f9c9  mov     edx, 0B0h; unsigned __int64
0x14011f9ce  lea     r9, ??1SmsCheckpointContext@@QEAA@XZ; void (*)(void *)
0x14011f9d5  lea     r8d, [rdi-1]; unsigned __int64
0x14011f9d9  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14011f9de  lea     rcx, [rbx+488h]
0x14011f9e5  call    ??1?$unique_ptr@VCmsVolumeAttestation@@U?$default_delete@VCmsVolumeAttestation@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>::~unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>(void)
0x14011f9ea  lea     rcx, [rbx+480h]
0x14011f9f1  call    ??1?$unique_ptr@VCmsRollbackProtection@@U?$default_delete@VCmsRollbackProtection@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>::~unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>(void)
0x14011f9f6  lea     rcx, [rbx+1B0h]
0x14011f9fd  call    cs:__imp_ExCleanupAutoExpandPushLock
0x14011fa04  nop     dword ptr [rax+rax+00h]
0x14011fa09  lea     rcx, [rbx+148h]
0x14011fa10  call    cs:__imp_ExCleanupAutoExpandPushLock
  ... truncated ...
```
