# CDsmPropertyCache::~CDsmPropertyCache(void)

- ea: `0x180030e44`
- end: `0x180030eac`
- name: `??1CDsmPropertyCache@@UEAA@XZ`
- size: `104`
- prototype: `void __fastcall(RTL_SRWLOCK *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030eb4`
- `0x180030f30`

## callees

- `0x180005df0`
- `0x18000d818`
- `0x180030e44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030e7a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180030e7a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030e5e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180030e5e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030e8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180030e8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CDsmPropertyCache::~CDsmPropertyCache(RTL_SRWLOCK *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  PVOID Ptr; // rcx

  this->Ptr = &CDsmPropertyCache::`vftable';
  AcquireSRWLockExclusive(this + 1);
  CDsmPropertyCache::_PurgePropertyList(v2, &this[2]);
  CDsmPropertyCache::_PurgePropertyList(v3, &this[8]);
  ReleaseSRWLockExclusive(this + 1);
  Ptr = this[26].Ptr;
  if ( Ptr )
    CoTaskMemFree(Ptr);
  ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::RemoveAll(&this[8]);
  ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::RemoveAll(&this[2]);
}

```

## disassembly

```asm
0x180030e44  push    rbx
0x180030e46  push    rbp
0x180030e47  push    rsi
0x180030e48  push    rdi
0x180030e49  sub     rsp, 28h
0x180030e4d  mov     rdi, rcx
0x180030e50  lea     rax, ??_7CDsmPropertyCache@@6B@; const CDsmPropertyCache::`vftable'
0x180030e57  mov     [rcx], rax
0x180030e5a  add     rcx, 8; SRWLock
0x180030e5e  call    cs:__imp_AcquireSRWLockExclusive
0x180030e64  lea     rdx, [rdi+10h]
0x180030e68  call    ?_PurgePropertyList@CDsmPropertyCache@@AEAAXAEAV?$CAtlList@PEAVCPropertySet@CDsmPropertyCache@@V?$CElementTraits@PEAVCPropertySet@CDsmPropertyCache@@@ATL@@@ATL@@@Z; CDsmPropertyCache::_PurgePropertyList(ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>> &)
0x180030e6d  lea     rdx, [rdi+40h]
0x180030e71  call    ?_PurgePropertyList@CDsmPropertyCache@@AEAAXAEAV?$CAtlList@PEAVCPropertySet@CDsmPropertyCache@@V?$CElementTraits@PEAVCPropertySet@CDsmPropertyCache@@@ATL@@@ATL@@@Z; CDsmPropertyCache::_PurgePropertyList(ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>> &)
0x180030e76  lea     rcx, [rdi+8]; SRWLock
0x180030e7a  call    cs:__imp_ReleaseSRWLockExclusive
0x180030e80  mov     rcx, [rdi+0D0h]; pv
0x180030e87  test    rcx, rcx
0x180030e8a  jz      short loc_180030E92
0x180030e8c  call    cs:__imp_CoTaskMemFree
0x180030e92  lea     rcx, [rdi+40h]
0x180030e96  call    ?RemoveAll@?$CAtlList@PEAVCPropertySet@CDsmPropertyCache@@V?$CElementTraits@PEAVCPropertySet@CDsmPropertyCache@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::RemoveAll(void)
0x180030e9b  lea     rcx, [rdi+10h]
0x180030e9f  add     rsp, 28h
0x180030ea3  pop     rdi
0x180030ea4  pop     rsi
0x180030ea5  pop     rbp
0x180030ea6  pop     rbx
0x180030ea7  jmp     ?RemoveAll@?$CAtlList@PEAVCPropertySet@CDsmPropertyCache@@V?$CElementTraits@PEAVCPropertySet@CDsmPropertyCache@@@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<CDsmPropertyCache::CPropertySet *,ATL::CElementTraits<CDsmPropertyCache::CPropertySet *>>::RemoveAll(void)
```
