# CmsVolume::~CmsVolume(void)

- ea: `0x14008bca0`
- end: `0x14008c1f9`
- name: `??1CmsVolume@@MEAA@XZ`
- size: `1369`
- prototype: `void __fastcall(CmsVolume *__hidden this)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14008c770`

## callees

- `0x1400048a0`
- `0x140004be0`
- `0x140004c60`
- `0x14006c100`
- `0x14007e658`
- `0x140083a24`
- `0x14008ba40`
- `0x14008baf0`
- `0x14008bb30`
- `0x14008bb50`
- `0x14008bb7c`
- `0x14008bc18`
- `0x14008bca0`
- `0x14008c27c`
- `0x14008c2ac`
- `0x14008c628`
- `0x14008c658`
- `0x14008c684`
- `0x14008c6b0`
- `0x14008c6e0`
- `0x14008c704`
- `0x14008c7c4`
- `0x14008c7f0`
- `0x14008c820`
- `0x14008c84c`
- `0x14008c870`
- `0x140090ea8`
- `0x1400ab1fc`
- `0x1400d2650`
- `0x1400e0248`
- `0x140118088`
- `0x140130e40`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x14008bf24`
- `ntdll!RtlDeleteResource` at `0x14008c116`
- `ntdll!RtlDeleteResource` at `0x14008bf24`
- `ntdll!RtlDeleteResource` at `0x14008c116`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CmsVolume::~CmsVolume(CmsVolume *this, struct CmsTransactionCore *a2)
{
  void *v3; // rdi
  CmsObjectTable *v4; // rcx
  CmsBlockRefcount *v5; // rcx
  CmsVolumeAnalyzer *v6; // rcx
  CmsVolumeContainer *v7; // rcx
  CmsIntegrityState *v8; // rcx
  CmsSchemaTable *v9; // rcx
  CmsRangeMap *v10; // rcx
  CmsRangeMap *v11; // rcx
  MsAllocator::SmallAllocatorStrategy::State **v12; // rax
  MsAllocator::SmallAllocatorStrategy::State *v13; // rcx
  MsAllocator::RangeArrayStrategy::State *v14; // rcx
  MsAllocator::RangeArrayStrategy::State *v15; // rcx
  MsAllocator::RangeArrayStrategy::State *v16; // rcx
  void *v17; // rcx
  void *v18; // rcx
  MsAllocator::RangeArrayStrategy::State *v19; // rcx
  void *v20; // rcx
  MsAllocator::SmrStrategy::State *v21; // rcx
  unsigned int i; // esi
  struct SmsCheckpointState *CheckpointState; // rdi
  unsigned int v24; // edx
  CmsContainerRangeMap *v25; // rcx
  unsigned int v26; // edx
  CmsContainerRangeMap *v27; // rcx
  CmsContainerRangeMap *v28; // rcx
  unsigned int v29; // edx
  CmsContainerRangeMap *v30; // rcx
  char *v31; // rsi
  void *v32; // rcx
  const struct std::nothrow_t *v33; // rdx
  void *v34; // rcx
  CmsRangeMap *v35; // rcx
  CmsRangeMap *v36; // rcx
  CmsRangeMap *v37; // rcx
  CmsRangeMap *v38; // rcx
  CmsRangeMap *v39; // rcx
  CmsRangeMap *v40; // rcx
  void *v41; // rcx
  CmsCachedRuns *v42; // rcx
  void *v43; // rdi
  void *v44; // rcx
  void *v45; // rdi

  *(_QWORD *)this = &CmsVolume::`vftable';
  if ( (*((_DWORD *)this + 821) & 0x10000) != 0 )
  {
    v31 = (char *)this + 1688;
  }
  else
  {
    v3 = (void *)*((_QWORD *)this + 281);
    if ( v3 )
    {
      CmsThinProvisioning::~CmsThinProvisioning(*((CmsThinProvisioning **)this + 281));
      operator delete(v3, (const struct std::nothrow_t *)0xF8);
      *((_QWORD *)this + 281) = 0;
    }
    v4 = (CmsObjectTable *)*((_QWORD *)this + 406);
    if ( v4 )
    {
      CmsObjectTable::`scalar deleting destructor'(v4, (unsigned int)a2);
      *((_QWORD *)this + 406) = 0;
    }
    v5 = (CmsBlockRefcount *)*((_QWORD *)this + 401);
    if ( v5 )
    {
      CmsBlockRefcount::`scalar deleting destructor'(v5, (unsigned int)a2);
      *((_QWORD *)this + 401) = 0;
    }
    v6 = (CmsVolumeAnalyzer *)*((_QWORD *)this + 399);
    if ( v6 )
    {
      CmsVolumeAnalyzer::`scalar deleting destructor'(v6, (unsigned int)a2);
      *((_QWORD *)this + 399) = 0;
    }
    v7 = (CmsVolumeContainer *)*((_QWORD *)this + 397);
    if ( v7 )
    {
      CmsVolumeContainer::`scalar deleting destructor'(v7, (unsigned int)a2);
      *((_QWORD *)this + 397) = 0;
    }
    v8 = (CmsIntegrityState *)*((_QWORD *)this + 398);
    if ( v8 )
    {
      CmsIntegrityState::`scalar deleting destructor'(v8, (unsigned int)a2);
      *((_QWORD *)this + 398) = 0;
    }
    v9 = (CmsSchemaTable *)*((_QWORD *)this + 409);
    if ( v9 )
    {
      CmsSchemaTable::`scalar deleting destructor'(v9, (unsigned int)a2);
      *((_QWORD *)this + 409) = 0;
    }
    v10 = (CmsRangeMap *)*((_QWORD *)this + 282);
    if ( v10 )
    {
      if ( *((_QWORD *)v10 + 3) )
        CmsRangeMap::DeleteAll(v10, a2);
      v11 = (CmsRangeMap *)*((_QWORD *)this + 282);
      if ( v11 )
        CmsRangeMap::`scalar deleting destructor'(v11, (unsigned int)a2);
      *((_QWORD *)this + 282) = 0;
    }
    v12 = (MsAllocator::SmallAllocatorStrategy::State **)*((_QWORD *)this + 325);
    if ( v12 )
    {
      if ( *v12 )
      {
        MsAllocator::SmallAllocatorStrategy::State::`scalar deleting destructor'(*v12, (unsigned int)a2);
        **((_QWORD **)this + 325) = 0;
      }
      v13 = *(MsAllocator::SmallAllocatorStrategy::State **)(*((_QWORD *)this + 325) + 8LL);
      if ( v13 )
      {
        MsAllocator::SmallAllocatorStrategy::State::`scalar deleting destructor'(v13, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 325) + 8LL) = 0;
      }
      v14 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 325) + 16LL);
      if ( v14 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v14, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 325) + 16LL) = 0;
      }
      v15 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 325) + 24LL);
      if ( v15 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v15, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 325) + 24LL) = 0;
      }
      v16 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 325) + 32LL);
      if ( v16 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v16, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 325) + 32LL) = 0;
      }
      v17 = *(void **)(*((_QWORD *)this + 325) + 72LL);
      if ( v17 )
      {
        operator delete(v17, (const struct std::nothrow_t *)0x10);
        *(_QWORD *)(*((_QWORD *)this + 325) + 72LL) = 0;
      }
      v18 = *(void **)(*((_QWORD *)this + 325) + 88LL);
      if ( v18 )
      {
        operator delete(v18, (const struct std::nothrow_t *)0x10);
        *(_QWORD *)(*((_QWORD *)this + 325) + 88LL) = 0;
      }
      v19 = *(MsAllocator::RangeArrayStrategy::State **)(*((_QWORD *)this + 325) + 40LL);
      if ( v19 )
      {
        MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(v19, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 325) + 40LL) = 0;
      }
      v20 = *(void **)(*((_QWORD *)this + 325) + 56LL);
      if ( v20 )
      {
        operator delete(v20, (const struct std::nothrow_t *)0x18);
        *(_QWORD *)(*((_QWORD *)this + 325) + 56LL) = 0;
      }
      v21 = *(MsAllocator::SmrStrategy::State **)(*((_QWORD *)this + 325) + 64LL);
      if ( v21 )
      {
        MsAllocator::SmrStrategy::State::`scalar deleting destructor'(v21, (unsigned int)a2);
        *(_QWORD *)(*((_QWORD *)this + 325) + 64LL) = 0;
      }
      operator delete(*((void **)this + 325), (const struct std::nothrow_t *)0x60);
      *((_QWORD *)this + 325) = 0;
    }
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 1200));
    MsDeleteEvent((CmsVolume *)((char *)this + 1656));
    for ( i = 0; i < 5; ++i )
    {
      CheckpointState = CmsVolume::GetCheckpointState(this, i);
      if ( *(_QWORD *)CheckpointState )
      {
        CmsContainerRangeMap::DeleteAll(*(CmsContainerRangeMap **)CheckpointState, 0);
        if ( *(_QWORD *)CheckpointState )
          CmsContainerRangeMap::`scalar deleting destructor'(*(CmsContainerRangeMap **)CheckpointState, v24);
        *(_QWORD *)CheckpointState = 0;
      }
      v25 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 1);
      if ( v25 )
      {
        CmsContainerRangeMap::DeleteAll(v25, 0);
        v27 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 1);
        if ( v27 )
          CmsContainerRangeMap::`scalar deleting destructor'(v27, v26);
        *((_QWORD *)CheckpointState + 1) = 0;
      }
      v28 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 2);
      if ( v28 )
      {
        CmsContainerRangeMap::DeleteAll(v28, 0);
        v30 = (CmsContainerRangeMap *)*((_QWORD *)CheckpointState + 2);
        if ( v30 )
          CmsContainerRangeMap::`scalar deleting destructor'(v30, v29);
        *((_QWORD *)CheckpointState + 2) = 0;
      }
    }
    v31 = (char *)this + 1688;
    v32 = (void *)*((_QWORD *)this + 211);
    *((_QWORD *)this + 211) = 0;
    if ( v32 )
      operator delete(v32);
    MsDeleteEvent((CmsVolume *)((char *)this + 2648));
    v34 = (void *)*((_QWORD *)this + 270);
    if ( v34 )
      operator delete(v34, v33);
    if ( *((_QWORD *)this + 70) )
      MspCleanupIoBatchLookaside(this);
    v35 = (CmsRangeMap *)*((_QWORD *)this + 469);
    if ( v35 )
    {
      CmsRangeMap::DeleteAll(v35, v33);
      v36 = (CmsRangeMap *)*((_QWORD *)this + 469);
      if ( v36 )
        CmsRangeMap::`scalar deleting destructor'(v36, (unsigned int)v33);
    }
    v37 = (CmsRangeMap *)*((_QWORD *)this + 470);
    if ( v37 )
    {
      CmsRangeMap::DeleteAll(v37, v33);
      v38 = (CmsRangeMap *)*((_QWORD *)this + 470);
      if ( v38 )
        CmsRangeMap::`scalar deleting destructor'(v38, (unsigned int)v33);
      *((_QWORD *)this + 470) = 0;
    }
    v39 = (CmsRangeMap *)*((_QWORD *)this + 473);
    if ( v39 )
    {
      CmsRangeMap::DeleteAll(v39, v33);
      v40 = (CmsRangeMap *)*((_QWORD *)this + 473);
      if ( v40 )
        CmsRangeMap::`scalar deleting destructor'(v40, (unsigned int)v33);
    }
    v41 = (void *)*((_QWORD *)this + 475);
    if ( v41 )
      operator delete(v41, v33);
    v42 = (CmsCachedRuns *)*((_QWORD *)this + 344);
    if ( v42 )
    {
      CmsCachedRuns::`scalar deleting destructor'(v42, (unsigned int)v33);
      *((_QWORD *)this + 344) = 0;
    }
    v43 = (void *)*((_QWORD *)this + 411);
    if ( v43 )
    {
      CmsTrashTable::~CmsTrashTable(*((CmsTrashTable **)this + 411));
      operator delete(v43, (const struct std::nothrow_t *)0xC8);
      *((_QWORD *)this + 411) = 0;
    }
    v44 = (void *)*((_QWORD *)this + 414);
    if ( v44 != qword_140243B00 )
    {
      operator delete(v44, (const struct std::nothrow_t *)0x20000);
      *((_QWORD *)this + 414) = 0;
    }
    v45 = (void *)*((_QWORD *)this + 390);
    if ( v45 )
    {
      CmsAllocationZones::~CmsAllocationZones(*((CmsAllocationZones **)this + 390));
      operator delete(v45, (const struct std::nothrow_t *)0x38);
    }
    *((_QWORD *)this + 396) = 0;
    *((_QWORD *)this + 394) = 0;
    *((_QWORD *)this + 395) = 0;
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 3320));
  }
  MsDeleteEvent((CmsVolume *)((char *)this + 3872));
  utl::unique_ptr<CDatabaseContext,utl::default_delete<CDatabaseContext>>::~unique_ptr<CDatabaseContext,utl::default_delete<CDatabaseContext>>((char *)this + 3488);
  SmsChecksumObjects::~SmsChecksumObjects((CmsVolume *)((char *)this + 3416));
  `eh vector destructor iterator'(
    (char *)this + 3128,
    8u,
    3u,
    utl::unique_ptr<CmsAllocator,utl::default_delete<CmsAllocator>>::~unique_ptr<CmsAllocator,utl::default_delete<CmsAllocator>>);
  CmsVolume::SmsTrim::~SmsTrim((CmsVolume *)((char *)this + 2176));
  utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit((char *)this + 2128);
  `eh vector destructor iterator'(
    (char *)this + 2016,
    0x18u,
    3u,
    utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::~vector<enum utl::byte,utl::allocator<enum utl::byte>>);
  utl::unique_ptr<SmsPersistentRollbackProtectionInformation,tlx::generic_delete<SmsPersistentRollbackProtectionInformation,tlx::operator_delete_deallocate>>::~unique_ptr<SmsPersistentRollbackProtectionInformation,tlx::generic_delete<SmsPersistentRollbackProtectionInformation,tlx::operator_delete_deallocate>>(v31);
  `eh vector destructor iterator'(
    (char *)this + 1296,
    0xB0u,
    2u,
    (void (*)(void *))SmsCheckpointContext::~SmsCheckpointContext);
  utl::unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>::~unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>((char *)this + 1184);
  utl::unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>::~unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>((char *)this + 1176);
  CmsVolume::_unnamed_type_ReservedPools_::__unnamed_type_ReservedPools_((CmsVolume *)((char *)this + 112));
  *(_QWORD *)this = &CmsReferenced::`vftable';
}

```

## disassembly

```asm
0x14008bca0  push    rbx
0x14008bca2  push    rbp
0x14008bca3  push    rsi
0x14008bca4  push    rdi
0x14008bca5  sub     rsp, 28h
0x14008bca9  mov     rbx, rcx
0x14008bcac  lea     rax, ??_7CmsVolume@@6B@; const CmsVolume::`vftable'
0x14008bcb3  mov     [rcx], rax
0x14008bcb6  test    dword ptr [rcx+0CD4h], 10000h
0x14008bcc0  jnz     loc_14008C124
0x14008bcc6  mov     rdi, [rcx+8C8h]
0x14008bccd  xor     ebp, ebp
0x14008bccf  test    rdi, rdi
0x14008bcd2  jz      short loc_14008BCF0
0x14008bcd4  mov     rcx, rdi; this
0x14008bcd7  call    ??1CmsThinProvisioning@@QEAA@XZ; CmsThinProvisioning::~CmsThinProvisioning(void)
0x14008bcdc  mov     edx, 0F8h; struct std::nothrow_t *
0x14008bce1  mov     rcx, rdi; void *
0x14008bce4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008bce9  mov     [rbx+8C8h], rbp
0x14008bcf0  mov     rcx, [rbx+0CB0h]; this
0x14008bcf7  test    rcx, rcx
0x14008bcfa  jz      short loc_14008BD08
0x14008bcfc  call    ??_GCmsObjectTable@@QEAAPEAXI@Z; CmsObjectTable::`scalar deleting destructor'(uint)
0x14008bd01  mov     [rbx+0CB0h], rbp
0x14008bd08  mov     rcx, [rbx+0C88h]; this
0x14008bd0f  test    rcx, rcx
0x14008bd12  jz      short loc_14008BD20
0x14008bd14  call    ??_GCmsBlockRefcount@@QEAAPEAXI@Z; CmsBlockRefcount::`scalar deleting destructor'(uint)
0x14008bd19  mov     [rbx+0C88h], rbp
0x14008bd20  mov     rcx, [rbx+0C78h]; this
0x14008bd27  test    rcx, rcx
0x14008bd2a  jz      short loc_14008BD38
0x14008bd2c  call    ??_GCmsVolumeAnalyzer@@QEAAPEAXI@Z; CmsVolumeAnalyzer::`scalar deleting destructor'(uint)
0x14008bd31  mov     [rbx+0C78h], rbp
0x14008bd38  mov     rcx, [rbx+0C68h]; this
0x14008bd3f  test    rcx, rcx
0x14008bd42  jz      short loc_14008BD50
0x14008bd44  call    ??_GCmsVolumeContainer@@QEAAPEAXI@Z; CmsVolumeContainer::`scalar deleting destructor'(uint)
0x14008bd49  mov     [rbx+0C68h], rbp
0x14008bd50  mov     rcx, [rbx+0C70h]; this
0x14008bd57  test    rcx, rcx
0x14008bd5a  jz      short loc_14008BD68
0x14008bd5c  call    ??_GCmsIntegrityState@@QEAAPEAXI@Z; CmsIntegrityState::`scalar deleting destructor'(uint)
0x14008bd61  mov     [rbx+0C70h], rbp
0x14008bd68  mov     rcx, [rbx+0CC8h]; this
0x14008bd6f  test    rcx, rcx
0x14008bd72  jz      short loc_14008BD80
0x14008bd74  call    ??_GCmsSchemaTable@@QEAAPEAXI@Z; CmsSchemaTable::`scalar deleting destructor'(uint)
0x14008bd79  mov     [rbx+0CC8h], rbp
0x14008bd80  mov     rcx, [rbx+8D0h]; this
0x14008bd87  test    rcx, rcx
0x14008bd8a  jz      short loc_14008BDAF
0x14008bd8c  cmp     [rcx+18h], rbp
0x14008bd90  jz      short loc_14008BD97
0x14008bd92  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14008bd97  mov     rcx, [rbx+8D0h]; this
0x14008bd9e  test    rcx, rcx
0x14008bda1  jz      short loc_14008BDA8
0x14008bda3  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14008bda8  mov     [rbx+8D0h], rbp
0x14008bdaf  mov     rax, [rbx+0A28h]
0x14008bdb6  test    rax, rax
0x14008bdb9  jz      loc_14008BF1D
0x14008bdbf  mov     rcx, [rax]; this
0x14008bdc2  test    rcx, rcx
0x14008bdc5  jz      short loc_14008BDD6
0x14008bdc7  call    ??_GState@SmallAllocatorStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::SmallAllocatorStrategy::State::`scalar deleting destructor'(uint)
0x14008bdcc  mov     rax, [rbx+0A28h]
0x14008bdd3  mov     [rax], rbp
0x14008bdd6  mov     rax, [rbx+0A28h]
0x14008bddd  mov     rcx, [rax+8]; this
0x14008bde1  test    rcx, rcx
0x14008bde4  jz      short loc_14008BDF6
0x14008bde6  call    ??_GState@SmallAllocatorStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::SmallAllocatorStrategy::State::`scalar deleting destructor'(uint)
0x14008bdeb  mov     rax, [rbx+0A28h]
0x14008bdf2  mov     [rax+8], rbp
0x14008bdf6  mov     rax, [rbx+0A28h]
0x14008bdfd  mov     rcx, [rax+10h]; this
0x14008be01  test    rcx, rcx
0x14008be04  jz      short loc_14008BE16
0x14008be06  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14008be0b  mov     rax, [rbx+0A28h]
0x14008be12  mov     [rax+10h], rbp
0x14008be16  mov     rax, [rbx+0A28h]
0x14008be1d  mov     rcx, [rax+18h]; this
0x14008be21  test    rcx, rcx
0x14008be24  jz      short loc_14008BE36
0x14008be26  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14008be2b  mov     rax, [rbx+0A28h]
0x14008be32  mov     [rax+18h], rbp
0x14008be36  mov     rax, [rbx+0A28h]
0x14008be3d  mov     rcx, [rax+20h]; this
0x14008be41  test    rcx, rcx
0x14008be44  jz      short loc_14008BE56
0x14008be46  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14008be4b  mov     rax, [rbx+0A28h]
0x14008be52  mov     [rax+20h], rbp
0x14008be56  mov     rax, [rbx+0A28h]
0x14008be5d  mov     rcx, [rax+48h]; void *
0x14008be61  mov     edi, 10h
0x14008be66  test    rcx, rcx
0x14008be69  jz      short loc_14008BE7D
0x14008be6b  mov     edx, edi; struct std::nothrow_t *
0x14008be6d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008be72  mov     rax, [rbx+0A28h]
0x14008be79  mov     [rax+48h], rbp
0x14008be7d  mov     rax, [rbx+0A28h]
0x14008be84  mov     rcx, [rax+58h]; void *
0x14008be88  test    rcx, rcx
0x14008be8b  jz      short loc_14008BEA0
0x14008be8d  mov     rdx, rdi; struct std::nothrow_t *
0x14008be90  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008be95  mov     rax, [rbx+0A28h]
0x14008be9c  mov     [rax+58h], rbp
0x14008bea0  mov     rax, [rbx+0A28h]
0x14008bea7  mov     rcx, [rax+28h]; this
0x14008beab  test    rcx, rcx
0x14008beae  jz      short loc_14008BEC0
0x14008beb0  call    ??_GState@RangeArrayStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::RangeArrayStrategy::State::`scalar deleting destructor'(uint)
0x14008beb5  mov     rax, [rbx+0A28h]
0x14008bebc  mov     [rax+28h], rbp
0x14008bec0  mov     rax, [rbx+0A28h]
0x14008bec7  mov     rcx, [rax+38h]; void *
0x14008becb  test    rcx, rcx
0x14008bece  jz      short loc_14008BEE5
0x14008bed0  mov     edx, 18h; struct std::nothrow_t *
0x14008bed5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008beda  mov     rax, [rbx+0A28h]
0x14008bee1  mov     [rax+38h], rbp
0x14008bee5  mov     rax, [rbx+0A28h]
0x14008beec  mov     rcx, [rax+40h]; this
0x14008bef0  test    rcx, rcx
0x14008bef3  jz      short loc_14008BF05
0x14008bef5  call    ??_GState@SmrStrategy@MsAllocator@@QEAAPEAXI@Z; MsAllocator::SmrStrategy::State::`scalar deleting destructor'(uint)
0x14008befa  mov     rax, [rbx+0A28h]
0x14008bf01  mov     [rax+40h], rbp
0x14008bf05  mov     edx, 60h ; '`'; struct std::nothrow_t *
0x14008bf0a  mov     rcx, [rbx+0A28h]; void *
0x14008bf11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008bf16  mov     [rbx+0A28h], rbp
0x14008bf1d  lea     rcx, [rbx+4B0h]; Resource
0x14008bf24  call    cs:__imp_RtlDeleteResource
0x14008bf2b  nop     dword ptr [rax+rax+00h]
0x14008bf30  lea     rcx, [rbx+678h]; struct MS_EVENT_USERMODE *
0x14008bf37  call    ?MsDeleteEvent@@YAXPEAUMS_EVENT_USERMODE@@@Z; MsDeleteEvent(MS_EVENT_USERMODE *)
0x14008bf3c  mov     esi, ebp
0x14008bf3e  mov     edx, esi; unsigned int
0x14008bf40  mov     rcx, rbx; this
0x14008bf43  call    ?GetCheckpointState@CmsVolume@@AEAAPEAUSmsCheckpointState@@K@Z; CmsVolume::GetCheckpointState(ulong)
0x14008bf48  mov     rdi, rax
0x14008bf4b  mov     rcx, [rax]; this
0x14008bf4e  test    rcx, rcx
0x14008bf51  jz      short loc_14008BF6A
0x14008bf53  xor     edx, edx; unsigned __int8
0x14008bf55  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14008bf5a  mov     rcx, [rdi]; this
0x14008bf5d  test    rcx, rcx
0x14008bf60  jz      short loc_14008BF67
0x14008bf62  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14008bf67  mov     [rdi], rbp
0x14008bf6a  mov     rcx, [rdi+8]; this
0x14008bf6e  test    rcx, rcx
0x14008bf71  jz      short loc_14008BF8C
0x14008bf73  xor     edx, edx; unsigned __int8
0x14008bf75  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14008bf7a  mov     rcx, [rdi+8]; this
0x14008bf7e  test    rcx, rcx
0x14008bf81  jz      short loc_14008BF88
0x14008bf83  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14008bf88  mov     [rdi+8], rbp
0x14008bf8c  mov     rcx, [rdi+10h]; this
0x14008bf90  test    rcx, rcx
0x14008bf93  jz      short loc_14008BFAE
0x14008bf95  xor     edx, edx; unsigned __int8
0x14008bf97  call    ?DeleteAll@CmsContainerRangeMap@@QEAAXE@Z; CmsContainerRangeMap::DeleteAll(uchar)
0x14008bf9c  mov     rcx, [rdi+10h]; this
0x14008bfa0  test    rcx, rcx
0x14008bfa3  jz      short loc_14008BFAA
0x14008bfa5  call    ??_GCmsContainerRangeMap@@QEAAPEAXI@Z; CmsContainerRangeMap::`scalar deleting destructor'(uint)
0x14008bfaa  mov     [rdi+10h], rbp
0x14008bfae  inc     esi
0x14008bfb0  cmp     esi, 5
0x14008bfb3  jb      short loc_14008BF3E
0x14008bfb5  lea     rsi, [rbx+698h]
0x14008bfbc  mov     rcx, [rsi]; Block
0x14008bfbf  mov     [rsi], rbp
0x14008bfc2  test    rcx, rcx
0x14008bfc5  jz      short loc_14008BFCC
0x14008bfc7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14008bfcc  lea     rcx, [rbx+0A58h]; struct MS_EVENT_USERMODE *
0x14008bfd3  call    ?MsDeleteEvent@@YAXPEAUMS_EVENT_USERMODE@@@Z; MsDeleteEvent(MS_EVENT_USERMODE *)
0x14008bfd8  mov     rcx, [rbx+870h]; void *
0x14008bfdf  test    rcx, rcx
0x14008bfe2  jz      short loc_14008BFE9
0x14008bfe4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008bfe9  cmp     [rbx+230h], rbp
0x14008bff0  jz      short loc_14008BFFA
0x14008bff2  mov     rcx, rbx; struct CmsVolume *
0x14008bff5  call    ?MspCleanupIoBatchLookaside@@YAXPEAVCmsVolume@@@Z; MspCleanupIoBatchLookaside(CmsVolume *)
0x14008bffa  mov     rcx, [rbx+0EA8h]; this
0x14008c001  test    rcx, rcx
0x14008c004  jz      short loc_14008C01C
0x14008c006  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14008c00b  mov     rcx, [rbx+0EA8h]; this
0x14008c012  test    rcx, rcx
0x14008c015  jz      short loc_14008C01C
0x14008c017  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14008c01c  mov     rcx, [rbx+0EB0h]; this
0x14008c023  test    rcx, rcx
0x14008c026  jz      short loc_14008C045
0x14008c028  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14008c02d  mov     rcx, [rbx+0EB0h]; this
0x14008c034  test    rcx, rcx
0x14008c037  jz      short loc_14008C03E
0x14008c039  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14008c03e  mov     [rbx+0EB0h], rbp
0x14008c045  mov     rcx, [rbx+0EC8h]; this
0x14008c04c  test    rcx, rcx
0x14008c04f  jz      short loc_14008C067
0x14008c051  call    ?DeleteAll@CmsRangeMap@@QEAAXPEAVCmsTransactionCore@@@Z; CmsRangeMap::DeleteAll(CmsTransactionCore *)
0x14008c056  mov     rcx, [rbx+0EC8h]; this
0x14008c05d  test    rcx, rcx
0x14008c060  jz      short loc_14008C067
0x14008c062  call    ??_GCmsRangeMap@@QEAAPEAXI@Z; CmsRangeMap::`scalar deleting destructor'(uint)
0x14008c067  mov     rcx, [rbx+0ED8h]; void *
0x14008c06e  test    rcx, rcx
0x14008c071  jz      short loc_14008C078
0x14008c073  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008c078  mov     rcx, [rbx+0AC0h]; this
0x14008c07f  test    rcx, rcx
0x14008c082  jz      short loc_14008C090
0x14008c084  call    ??_GCmsCachedRuns@@QEAAPEAXI@Z; CmsCachedRuns::`scalar deleting destructor'(uint)
0x14008c089  mov     [rbx+0AC0h], rbp
0x14008c090  mov     rdi, [rbx+0CD8h]
0x14008c097  test    rdi, rdi
0x14008c09a  jz      short loc_14008C0B8
0x14008c09c  mov     rcx, rdi; this
0x14008c09f  call    ??1CmsTrashTable@@QEAA@XZ; CmsTrashTable::~CmsTrashTable(void)
0x14008c0a4  mov     edx, 0C8h; struct std::nothrow_t *
0x14008c0a9  mov     rcx, rdi; void *
0x14008c0ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008c0b1  mov     [rbx+0CD8h], rbp
0x14008c0b8  mov     rcx, [rbx+0CF0h]; void *
0x14008c0bf  cmp     rcx, cs:qword_140243B00
0x14008c0c6  jz      short loc_14008C0D9
0x14008c0c8  mov     edx, 20000h; struct std::nothrow_t *
0x14008c0cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008c0d2  mov     [rbx+0CF0h], rbp
0x14008c0d9  mov     rdi, [rbx+0C30h]
0x14008c0e0  test    rdi, rdi
0x14008c0e3  jz      short loc_14008C0FA
0x14008c0e5  mov     rcx, rdi; this
0x14008c0e8  call    ??1CmsAllocationZones@@QEAA@XZ; CmsAllocationZones::~CmsAllocationZones(void)
0x14008c0ed  mov     edx, 38h ; '8'; struct std::nothrow_t *
0x14008c0f2  mov     rcx, rdi; void *
0x14008c0f5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14008c0fa  mov     [rbx+0C60h], rbp
0x14008c101  mov     [rbx+0C50h], rbp
0x14008c108  mov     [rbx+0C58h], rbp
0x14008c10f  lea     rcx, [rbx+0CF8h]; Resource
0x14008c116  call    cs:__imp_RtlDeleteResource
0x14008c11d  nop     dword ptr [rax+rax+00h]
0x14008c122  jmp     short loc_14008C12B
0x14008c124  lea     rsi, [rcx+698h]
0x14008c12b  lea     rcx, [rbx+0F20h]; struct MS_EVENT_USERMODE *
0x14008c132  call    ?MsDeleteEvent@@YAXPEAUMS_EVENT_USERMODE@@@Z; MsDeleteEvent(MS_EVENT_USERMODE *)
0x14008c137  lea     rcx, [rbx+0DA0h]; void *
0x14008c13e  call    ??1?$unique_ptr@VCDatabaseContext@@U?$default_delete@VCDatabaseContext@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CDatabaseContext,utl::default_delete<CDatabaseContext>>::~unique_ptr<CDatabaseContext,utl::default_delete<CDatabaseContext>>(void)
0x14008c143  lea     rcx, [rbx+0D58h]; this
0x14008c14a  call    ??1SmsChecksumObjects@@QEAA@XZ; SmsChecksumObjects::~SmsChecksumObjects(void)
0x14008c14f  lea     rcx, [rbx+0C38h]; void *
0x14008c156  lea     r9, ??1?$unique_ptr@VCmsAllocator@@U?$default_delete@VCmsAllocator@@@utl@@@utl@@QEAA@XZ; void (*)(void *)
0x14008c15d  mov     edi, 3
0x14008c162  mov     r8d, edi; unsigned __int64
0x14008c165  lea     edx, [rdi+5]; unsigned __int64
0x14008c168  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14008c16d  lea     rcx, [rbx+880h]; this
0x14008c174  call    ??1SmsTrim@CmsVolume@@QEAA@XZ; CmsVolume::SmsTrim::~SmsTrim(void)
0x14008c179  lea     rcx, [rbx+850h]
0x14008c180  call    ?_Uninit@?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@AEAAXXZ; utl::vector<utl::byte,utl::allocator<utl::byte>>::_Uninit(void)
0x14008c185  nop
0x14008c186  lea     rcx, [rbx+7E0h]; void *
0x14008c18d  lea     r9, ??1?$vector@W4byte@utl@@V?$allocator@W4byte@utl@@@2@@utl@@QEAA@XZ; void (*)(void *)
0x14008c194  mov     r8d, edi; unsigned __int64
0x14008c197  lea     edx, [rdi+15h]; unsigned __int64
0x14008c19a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14008c19f  nop
0x14008c1a0  mov     rcx, rsi; void *
0x14008c1a3  call    ??1?$unique_ptr@USmsPersistentRollbackProtectionInformation@@U?$generic_delete@USmsPersistentRollbackProtectionInformation@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAA@XZ; utl::unique_ptr<SmsPersistentRollbackProtectionInformation,tlx::generic_delete<SmsPersistentRollbackProtectionInformation,tlx::operator_delete_deallocate>>::~unique_ptr<SmsPersistentRollbackProtectionInformation,tlx::generic_delete<SmsPersistentRollbackProtectionInformation,tlx::operator_delete_deallocate>>(void)
0x14008c1a8  lea     rcx, [rbx+510h]; void *
0x14008c1af  lea     r9, ??1SmsCheckpointContext@@QEAA@XZ; void (*)(void *)
0x14008c1b6  mov     edx, 0B0h; unsigned __int64
0x14008c1bb  lea     r8d, [rdi-1]; unsigned __int64
0x14008c1bf  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14008c1c4  lea     rcx, [rbx+4A0h]
0x14008c1cb  call    ??1?$unique_ptr@VCmsVolumeAttestation@@U?$default_delete@VCmsVolumeAttestation@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>::~unique_ptr<CmsVolumeAttestation,utl::default_delete<CmsVolumeAttestation>>(void)
0x14008c1d0  lea     rcx, [rbx+498h]
0x14008c1d7  call    ??1?$unique_ptr@VCmsRollbackProtection@@U?$default_delete@VCmsRollbackProtection@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>::~unique_ptr<CmsRollbackProtection,utl::default_delete<CmsRollbackProtection>>(void)
0x14008c1dc  lea     rcx, [rbx+70h]; this
  ... truncated ...
```
